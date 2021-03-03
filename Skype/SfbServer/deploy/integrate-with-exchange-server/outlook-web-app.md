---
title: Konfigurieren der Integration zwischen lokalem Skype for Business Server und Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 0a6358c93356bd059aeed34033b07916d856bf10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833965"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Konfigurieren der Integration zwischen lokalem Skype for Business Server und Outlook Web App

**Zusammenfassung:** Integrieren sie Skype for Business Server und Outlook Web App.

Kunden, die lokale Skype for Business Server-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online hybriden Bereitstellungsmodus konfigurieren. Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu aktivieren, müssen Sie den Edgeserver in Ihrer lokalen Skype for Business Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

- Konfigurieren eines freigegebenen SIP-Adressraums

- Konfigurieren eines Hostinganbieters auf dem Edgeserver

- Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Um den lokalen Skype for Business Server in Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Der gleiche Adressraum der SIP-Domäne wird sowohl von Skype for Business Server als auch vom Exchange Online-Dienst unterstützt.

Konfigurieren Sie mithilfe der Skype for Business Server-Verwaltungsshell den Edgeserver für den Verbund, indem Sie das Cmdlet **"Set-CSAccessEdgeConfiguration"** mit den im folgenden Beispiel angezeigten Parametern ausführen:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem Szenario mit freigegebenen SIP-Adressraumen mit Skype for Business Server und Exchange Online kommunizieren können.

Weitere Informationen zur Verwendung der Skype for Business Server-Verwaltungsshell finden Sie unter [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Konfigurieren Sie mithilfe der Skype for Business Server-Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das **Cmdlet "New-CsHostingProvider"** mit den Parametern im folgenden Beispiel ausführen:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Wenn Sie Microsoft 365 oder Office 365, betrieben von 21Vianet in China verwenden, ersetzen Sie den Wert für den Parameter "ProxyFqdn" in diesem Beispiel ("exap.um.outlook.com") durch den FQDN für den von 21Vianet betriebenen Dienst: "exap.um.partner.outlook.cn". Wenn Sie Microsoft 365 oder Office 365 GCC High verwenden, ersetzen Sie den Wert für den Parameter "ProxyFqdn" in diesem Beispiel ("exap.um.outlook.com") durch den FQDN für GCC High: "exap.um.office365.us".

- **Identity** gibt einen eindeutigen Zeichenfolgenwertbezeichner für den Hostinganbieter an, den Sie erstellen (z. B. "Exchange Online"). Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf TRUE festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf TRUE festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype for Business Server verwendet wird. Dieser Parameter muss auf FALSE festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN "exap.um.outlook.com".

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype for Business Server-Topologie enthalten ist. Dieser Parameter muss auf FALSE festgelegt werden.

- **VerificationLevel** Gibt die Überprüfungsstufe an, die für Nachrichten zulässig ist, die an den und vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Stufe nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mithilfe der Cmdlets in den vorherigen Abschnitten vorgenommen haben, werden automatisch auf den Edgeserver angewendet und dauern in der Regel weniger als eine Minute für die Replikation. Mithilfe der folgenden Cmdlets können Sie den Replikationsstatus überprüfen und dann bestätigen, dass die Änderungen auf den Edgeserver angewendet wurden.

Führen Sie zum Überprüfen von Replikationsupdates auf einem internen Server in Ihrer Skype for Business Server-Bereitstellung das folgende Cmdlet aus:

```powershell
Get-CsManagementStoreReplicationStatus
```
Überprüfen Sie, ob für alle Replikate der Wert "UpToDate" TRUE angezeigt wird.

Führen Sie auf dem Edgeserver das folgende Cmdlet aus, um zu bestätigen, dass die Änderungen angewendet wurden:

```powershell
Get-CsHostingProvider -LocalStore
```
Überprüfen Sie, ob die angezeigten Informationen den in den vorherigen Schritten vorgenommenen Änderungen entspricht.

## <a name="see-also"></a>Siehe auch

[Bereitstellen von Voicemail für Skype for Business Server-Benutzer in gehosteten Exchange UM](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integration gehosteter Exchange Unified Messaging in Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
