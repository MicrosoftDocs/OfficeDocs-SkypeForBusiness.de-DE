---
title: Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App
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
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109691"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Konfigurieren der Integration zwischen lokalen Skype for Business Server und Outlook Web App

**Zusammenfassung:** Integrieren sie Skype for Business Server und Outlook Web App.

Kunden, die lokale Skype for Business Server-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online Hybridbereitstellungsmodus konfigurieren. Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu aktivieren, müssen Sie den Edgeserver in Ihrer lokalen Skype for Business Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

- Konfigurieren eines freigegebenen SIP-Adressraums

- Konfigurieren eines Hostinganbieters auf dem Edgeserver

- Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Um den lokalen Skype for Business Server in Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Der gleiche SIP-Domänenadressenbereich wird sowohl von Skype for Business Server als auch vom Exchange Online-Dienst unterstützt.

Konfigurieren Sie den Edgeserver mithilfe der Skype for Business Server-Verwaltungsshell für den Verbund, indem Sie das **Cmdlet Set-CSAccessEdgeConfiguration** mithilfe der im folgenden Beispiel angezeigten Parameter ausführen:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Der **AllowFederatedUsers**-Parameter gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem szenario für gemeinsam genutzten SIP-Adressraum mit Skype for Business Server und Exchange Online kommunizieren können.

Weitere Informationen zur Verwendung der Skype for Business Server-Verwaltungsshell finden Sie unter [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Konfigurieren Sie mithilfe der Skype for Business Server-Verwaltungsshell einen Hostinganbieter auf dem Edgeserver, indem Sie das **Cmdlet New-CsHostingProvider** ausführen, indem Sie die Parameter im folgenden Beispiel verwenden:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Wenn Sie Microsoft 365 oder Office 365 verwenden, das von 21Vianet in China betrieben wird, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.outlook.com") durch den FQDN für den von 21Vianet betriebenen Dienst: "exap.um.partner.outlook.cn". Wenn Sie Microsoft 365 oder Office 365 GCC High verwenden, ersetzen Sie den Wert für den ProxyFqdn-Parameter in diesem Beispiel ("exap.um.outlook.com") durch den FQDN für GCC High: "exap.um.office365.us".

- **Identity** gibt eine eindeutige Zeichenfolgenwert-ID für den Hostinganbieter an, den Sie erstellen (z. B. "Exchange Online"). Werte, die Leerzeichen enthalten, müssen in Anführungszeichen gesetzt werden.

- **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dieser Parameter muss auf TRUE festgelegt werden.

- **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dieser Parameter muss auf TRUE festgelegt werden.

- **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder Skype for Business Server verwendet wird. Dieser Parameter muss auf FALSE festgelegt werden.

- **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN "exap.um.outlook.com".

- **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxyserver in Ihrer Skype for Business Server-Topologie enthalten ist. Dieser Parameter muss auf FALSE festgelegt werden.

- **VerificationLevel** Gibt die Überprüfungsstufe an, die für Nachrichten zulässig ist, die an und vom gehosteten Anbieter gesendet werden. Geben Sie den **UseSourceVerification**-Wert an, der von der Überprüfungsstufe in Nachrichten abhängt, die vom Hostinganbieter gesendet werden. Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mithilfe der Cmdlets in den vorherigen Abschnitten vorgenommen haben, werden automatisch auf den Edgeserver angewendet, und die Replikation dauert in der Regel weniger als eine Minute. Sie können den Replikationsstatus überprüfen und dann mit den folgenden Cmdlets bestätigen, dass die Änderungen auf den Edgeserver angewendet wurden.

Führen Sie zum Überprüfen von Replikationsupdates auf einem internen Server in Ihrer Skype for Business Server-Bereitstellung das folgende Cmdlet aus:

```powershell
Get-CsManagementStoreReplicationStatus
```
Überprüfen Sie, ob der UpToDate-Wert true für alle Replikate zeigt.

Führen Sie auf dem Edgeserver das folgende Cmdlet aus, um zu bestätigen, dass die Änderungen angewendet wurden:

```powershell
Get-CsHostingProvider -LocalStore
```
Überprüfen Sie, ob die angezeigten Informationen den in den vorherigen Schritten vorgenommenen Änderungen entspricht.

## <a name="see-also"></a>Siehe auch

[Bereitstellen von Voicemail für Skype for Business Server-Benutzer in gehosteten Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Gehostete Exchange Unified Messaging-Integration in Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)