---
title: Konfigurieren der lokalen lync-Server Integration in Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae1ba45ace830f33b239bf2f8ead1a75fcee3417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Konfigurieren der lokalen lync Server 2013-Integration in Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2018-03-30_

Kunden, die lokale lync Server 2013-Bereitstellungen verwenden, können in einem Hybrid Bereitstellungsmodus die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online konfigurieren. Zu den Interoperabilitätsfunktionen gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu aktivieren, müssen Sie den Edgeserver in Ihrer lokalen lync Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

  - Konfigurieren eines freigegebenen SIP-Adressraums

  - Konfigurieren eines Hostinganbieter auf dem Edgeserver

  - Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Wenn lync Server 2013 in Exchange Online integriert ist, wird ein Benutzer, der versucht, sich bei Chat von OWA anzumeldet, als Remote-oder externer Benutzer betrachtet. In diesem Szenario muss für diesen Benutzer eine Richtlinie für den externen Zugriff zugewiesen sein, auf der die folgende Option ausgewählt ist:

**Aktivieren der Kommunikation mit Remotebenutzern**

Aktivieren Sie diese Option, wenn Sie möchten, dass Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie Telecommuter und Benutzer, die unterwegs sind, eine Verbindung mit lync Server über das Internet herstellen können.

Weitere Informationen finden Sie unter [Verwalten von Richtlinien für den externen Zugriff in lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Zur Integration von lokalem lync Server 2013 in Exchange Online müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Derselbe SIP-Domänen Adressraum wird sowohl von lync Server als auch vom Exchange Online-Dienst unterstützt.

Konfigurieren Sie mithilfe der lync Server-Verwaltungsshell den Edgeserver für Federation, indem Sie das Cmdlet " **csaccessedgeconfiguration nicht angeben** " mit den Parametern ausführen, die im folgenden Beispiel angezeigt werden:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adressraum Szenario mit lync Server und Exchange Online kommunizieren können.

Ausführliche Informationen zur Verwendung der lync Server-Verwaltungsshell finden Sie unter [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Verwenden Sie die lync Server-Verwaltungsshell, um einen Hostinganbieter auf dem Edgeserver zu konfigurieren. Führen Sie dazu das Cmdlet **New-CsHostingProvider** aus, und verwenden Sie dazu die Parameter im folgenden Beispiel:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Wenn Sie Office 365 über 21Vianet in China nutzen, ersetzen Sie den Wert für den Parameter <STRONG>ProxyFqdn</STRONG> in diesem Beispiel („exap.um.outlook.com“) mit dem FQDN für den Dienst, der in China von 21Vianet bereitgestellt wird: „exap.um.partner.outlook.cn“.



</div>

  - **Identity** gibt einen eindeutigen Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise „Exchange Online“). Werte, die Leerzeichen enthalten, müssen in doppelten Anführungszeichen stehen.

  - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dies muss auf " **true**" festgelegt werden.

  - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dies muss auf " **true**" festgelegt werden.

  - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder lync Server verwendet wird. Dieser Wert muss auf " **false**" festgelegt werden.

  - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN „exap.um.outlook.com“.

  - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server-Topologie enthalten ist. Dieser Wert muss auf " **false**" festgelegt werden.

  - **"Verificationlevel"** gibt die Überprüfungsstufe für Nachrichten an, die an den und vom gehosteten Anbieter gesendet werden. Geben Sie **UseSourceVerification**. Diese Option basiert auf der Überprüfungsstufe, die in Nachrichten enthalten ist, die vom Hostinganbieter gesendet werden. Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mithilfe der Cmdlets in den vorhergehenden Abschnitten vorgenommen haben, werden automatisch auf den Edgeserver angewendet, und in der Regel dauert es weniger als eine Minute, bis Sie repliziert werden. Mithilfe der folgenden Cmdlets können Sie den Replikationsstatus überprüfen und die Änderungen auf den Edgeserver anwenden.

Führen Sie das folgende Cmdlet aus, um Replikationsupdates auf einem internen Server in ihrer lync Server-Bereitstellung zu überprüfen:

    Get-CsManagementStoreReplicationStatus

Führen Sie das folgende Cmdlet auf dem Edgeserver aus, um zu überprüfen, ob die Änderungen übernommen wurden:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Voicemail für Benutzer von Lync Server 2013 für gehostete Exchange Unified Messaging-Dienste](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Integration in gehostete Exchange Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

