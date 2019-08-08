---
title: Konfigurieren der Integration zwischen einer lokalen Skype for Business Server-Bereitstellung und Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Zusammenfassung: Integration von Skype for Business Server und Outlook Web App.'
ms.openlocfilehash: b7c279dc41515d9613d8c000ab9e81164a1ccaa6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244209"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Konfigurieren der Integration zwischen einer lokalen Skype for Business Server-Bereitstellung und Outlook Web App

**Zusammenfassung:** Integrieren Sie Skype for Business Server und Outlook Web App.

Kunden, die lokale Skype for Business Server-Bereitstellungen verwenden, können in einem Hybrid Bereitstellungsmodus die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online konfigurieren. Zu den Interoperabilitätsfunktionen gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu aktivieren, müssen Sie den Edgeserver in Ihrer lokalen Skype for Business Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

- Konfigurieren eines freigegebenen SIP-Adressraums

- Konfigurieren eines Hostinganbieter auf dem Edgeserver

- Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Wenn Sie lokale Skype for Business-Server in Exchange Online integrieren möchten, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Derselbe SIP-Domänen Adressraum wird von Skype for Business Server und dem Exchange Online-Dienst unterstützt.

Konfigurieren Sie mithilfe der Skype for Business Server-Verwaltungsshell den Edgeserver für Federation, indem Sie das Cmdlet " **Satz-csaccessedgeconfiguration nicht angeben** " mit den im folgenden Beispiel angezeigten Parametern ausführen:

```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adressraum Szenario mit Skype for Business Server und Exchange Online kommunizieren können.

Details zur Verwendung der Skype for Business Server-Verwaltungsshell finden Sie unter [Skype for Business Server-Verwaltungsshell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Konfigurieren Sie mithilfe der Skype for Business Server-Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das Cmdlet **New-CsHostingProvider** mithilfe der Parameter im folgenden Beispiel ausführen:

```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Wenn Sie Office 365 über 21Vianet in China nutzen, ersetzen Sie den Wert für den Parameter ProxyFqdn in diesem Beispiel („exap.um.outlook.com“) mit dem FQDN für den Dienst, der in China von 21Vianet bereitgestellt wird: „exap.um.partner.outlook.cn“. Wenn Sie Office 365 gcc-groß verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für gcc-Höchstwert: "exap.um.office365.US".

- **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise „Exchange Online“). Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf TRUE festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf TRUE festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype for Business Server verwendet wird. Dieser Parameter muss auf FALSE festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN „exap.um.outlook.com“.

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in Ihrer Skype for Business Server-Topologie enthalten ist. Dieser Parameter muss auf FALSE festgelegt werden.

- **"Verificationlevel"** Zeigt die zulässige Überprüfung für Nachrichten an, die an den und vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mithilfe der Cmdlets in den vorhergehenden Abschnitten vorgenommen haben, werden automatisch auf den Edgeserver angewendet, und in der Regel dauert es weniger als eine Minute, bis Sie repliziert werden. Sie können den Replikationsstatus überprüfen und dann überprüfen, ob die Änderungen mithilfe der folgenden Cmdlets auf Ihren Edgeserver angewendet wurden.

Führen Sie zum Überprüfen von Replikationsupdates auf einem Server, der in Ihrer Skype for Business Server-Bereitstellung intern ist, das folgende Cmdlet aus:

```
Get-CsManagementStoreReplicationStatus
```
Überprüfen Sie, ob uptodate-Wert für alle Replikate "true" angezeigt wird.

Um zu bestätigen, dass die Änderungen übernommen wurden, führen Sie auf dem Edgeserver das folgende Cmdlet aus:

```
Get-CsHostingProvider -LocalStore
```
Überprüfen Sie, ob die angezeigten Informationen mit den Änderungen übereinstimmen, die in den vorherigen Schritten zugesichert wurden.

## <a name="see-also"></a>Siehe auch

[Bereitstellen von Skype for Business Server-Benutzern Voicemail für gehostete Exchange um](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integration von Hosted Exchange Unified Messaging in Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
