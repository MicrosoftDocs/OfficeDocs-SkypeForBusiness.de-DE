---
title: Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Zusammenfassung: Integrieren von Skype for Business Server und Outlook Web App.'
ms.openlocfilehash: 9555303ad5bcb3ad15702f0cf1768549330e33cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60738861"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App

**Zusammenfassung:** Integrieren sie Skype for Business Server und Outlook Web App.

Kunden, die lokale Skype for Business Server-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online im Hybridbereitstellungsmodus konfigurieren. Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu aktivieren, müssen Sie den Edgeserver in Ihrer lokalen Skype for Business Server Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

- Konfigurieren eines freigegebenen SIP-Adressraums

- Konfigurieren eines Hostinganbieters auf dem Edgeserver

- Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Um lokale Skype for Business Server in Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Derselbe SIP-Domänenadressraum wird sowohl von Skype for Business Server als auch vom Exchange Online-Dienst unterstützt.

Konfigurieren Sie mithilfe der Skype for Business Server Verwaltungsshell den Edgeserver für den Partnerverbund, indem Sie das Cmdlet **"Set-CSAccessEdgeConfiguration"** mithilfe der im folgenden Beispiel angezeigten Parameter ausführen:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem Szenario mit freigegebenen SIP-Adressraum mit Skype for Business Server und Exchange Online kommunizieren können.

Ausführliche Informationen zur Verwendung der Skype for Business Server-Verwaltungsshell finden Sie unter [Skype for Business Server Verwaltungsshell.](../../manage/management-shell.md)

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Konfigurieren Sie mithilfe der Skype for Business Server Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das Cmdlet **"New-CsHostingProvider"** ausführen, indem Sie die Parameter im folgenden Beispiel verwenden:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Wenn Sie Microsoft 365 oder Office 365 von 21Vianet in China verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.outlook.com") durch den FQDN für den von 21Vianet betriebenen Dienst: "exap.um.partner.outlook.cn". Wenn Sie Microsoft 365 oder Office 365 GCC High verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.outlook.com") durch den FQDN für GCC High: "exap.um.office365.us".

- **Identität** gibt einen eindeutigen Zeichenfolgenwertbezeichner für den Hostinganbieter an, den Sie erstellen (z. B. "Exchange Online"). Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf TRUE festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf TRUE festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten Office Communications Server oder Skype for Business Server verwendet wird. Dieser Parameter muss auf FALSE festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN "exap.um.outlook.com".

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype for Business Server Topologie enthalten ist. Dieser Parameter muss auf FALSE festgelegt werden.

- **VerificationLevel** Gibt die Überprüfungsstufe an, die für Nachrichten zulässig ist, die an den und vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Ebene nicht angegeben ist, wird die Nachricht als nicht verifizierbar abgelehnt.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mithilfe der Cmdlets in den vorherigen Abschnitten vorgenommen haben, werden automatisch auf den Edgeserver angewendet und in der Regel dauert die Replikation weniger als eine Minute. Sie können den Replikationsstatus überprüfen und dann mithilfe der folgenden Cmdlets bestätigen, dass die Änderungen auf den Edgeserver angewendet wurden.

Führen Sie zum Überprüfen von Replikationsupdates auf einem serverinternen Server in Ihrer Skype for Business Server Bereitstellung das folgende Cmdlet aus:

```powershell
Get-CsManagementStoreReplicationStatus
```
Überprüfen Sie, ob der UpToDate-Wert für alle Replikate TRUE anzeigt.

Um zu bestätigen, dass die Änderungen angewendet wurden, führen Sie auf dem Edgeserver das folgende Cmdlet aus:

```powershell
Get-CsHostingProvider -LocalStore
```
Überprüfen Sie, ob die angezeigten Informationen mit den in den vorherigen Schritten vorgenommenen Änderungen übereinstimmen.

## <a name="see-also"></a>Weitere Informationen

[Bereitstellen Skype for Business Server Voicemails von Benutzern auf gehosteten Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Integration von gehosteten Exchange Unified Messaging in Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)