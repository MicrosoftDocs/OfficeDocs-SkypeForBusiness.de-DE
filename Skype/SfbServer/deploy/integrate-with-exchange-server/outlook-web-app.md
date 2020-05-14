---
title: Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Zusammenfassung: Integrieren von Skype for Business Server und Outlook Web App.'
ms.openlocfilehash: ee5676c0dbe88568af78a1c278eea8a46457cb5c
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221185"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App

**Zusammenfassung:** Integrieren Sie Skype for Business Server und Outlook Web App.

Kunden, die lokale Skype for Business Server-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online im Hybrid Bereitstellungsmodus konfigurieren. Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu ermöglichen, müssen Sie die Edgeserver in Ihrer lokalen Skype for Business Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

- Konfigurieren eines freigegebenen SIP-Adressraums

- Konfigurieren eines Host Anbieters im Edgeserver

- Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Um lokale Skype for Business Server mit Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Derselbe SIP-Domänen Adressraum wird sowohl von Skype for Business Server als auch vom Exchange Online Dienst unterstützt.

Konfigurieren Sie mithilfe der Skype for Business Server Verwaltungsshell den Edgeserver für den Verbund, indem Sie das Cmdlet " **csaccessedgeconfiguration nicht angeben** " mit den im folgenden Beispiel angezeigten Parametern ausführen:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adressraum Szenario mit Skype for Business Server und Exchange Online kommunizieren können.

Ausführliche Informationen zur Verwendung der Skype for Business Server-Verwaltungsshell finden Sie unter [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Konfigurieren Sie mithilfe der Skype for Business Server Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das Cmdlet **New-CsHostingProvider** mit den Parametern im folgenden Beispiel ausführen:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Wenn Sie Microsoft 365 oder Office 365 betrieben von 21Vianet in China verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für den Dienst, der von 21Vianet verwaltet wird: "exap.um.Partner.Outlook.cn". Wenn Sie Microsoft 365 oder Office 365 gcc High verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für gcc High: "exap.um.office365.US".

- **Identity** gibt einen eindeutigen Bezeichner für den Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise "Exchange Online"). Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf TRUE festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf TRUE festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype for Business Server verwendet wird. Dieser Parameter muss auf FALSE festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN "exap.um.outlook.com".

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server Topologie enthalten ist. Dieser Parameter muss auf FALSE festgelegt werden.

- **"Verificationlevel"** Gibt die zulässige Überprüfungsebene für Nachrichten an, die vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mit den Cmdlets in den vorhergehenden Abschnitten vorgenommen haben, werden automatisch auf die Edgeserver angewendet und dauern in der Regel weniger als eine Minute, um repliziert zu werden. Sie können den Replikationsstatus überprüfen und anschließend überprüfen, ob die Änderungen auf Ihre Edgeserver mithilfe der folgenden Cmdlets angewendet wurden.

Führen Sie das folgende Cmdlet aus, um Replikationsupdates auf einem internen Server in Ihrer Skype for Business Server-Bereitstellung zu überprüfen:

```powershell
Get-CsManagementStoreReplicationStatus
```
Überprüfen Sie, ob uptodate-Wert true für alle Replikate angezeigt wird.

Um zu bestätigen, dass die Änderungen übernommen wurden, führen Sie im Edgeserver das folgende Cmdlet aus:

```powershell
Get-CsHostingProvider -LocalStore
```
Überprüfen Sie, ob die angezeigten Informationen mit den in den vorherigen Schritten zugesicherten Änderungen übereinstimmen.

## <a name="see-also"></a>Siehe auch

[Bereitstellen von Voicemail für Skype for Business Server-Benutzer in gehosteten Exchange um](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Hosted Exchange Unified Messaging-Integration in Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
