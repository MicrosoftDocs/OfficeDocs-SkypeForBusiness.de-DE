---
title: Konfigurieren der lokalen lync Server Integration in Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cfa8caa0aa2cb7dac704123f2a099bd305aed5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Konfigurieren der lokalen lync Server 2013 Integration in Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2018-03-30_

Kunden, die lokale lync Server 2013-Bereitstellungen verwenden, können die Interoperabilität mit Microsoft Outlook Web App in Microsoft Exchange Online im Hybrid Bereitstellungsmodus konfigurieren. Zu den Interoperabilitätsfeatures gehören einmaliges Anmelden (SSO) und Sofortnachrichten sowie die Anwesenheitsintegration in die Outlook Web App-Schnittstelle. Um diese Integration zu ermöglichen, müssen Sie die Edgeserver in Ihrer lokalen lync Server-Bereitstellung konfigurieren, indem Sie die folgenden Aufgaben ausführen:

  - Konfigurieren eines freigegebenen SIP-Adressraums

  - Konfigurieren eines Host Anbieters im Edgeserver

  - Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Wenn lync Server 2013 in Exchange Online integriert ist, wird ein Benutzer, der sich bei OWA anmeldet, als ein Remote-oder externer Benutzer betrachtet. In diesem Szenario muss dem Benutzer eine externe Zugriffsrichtlinie zugewiesen sein, für die die folgende Option ausgewählt ist:

**Aktivieren der Kommunikation mit Remotebenutzern**

Aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie etwa Telearbeiter und Benutzer, die sich auf Reisen befinden, eine Verbindung mit lync Server über das Internet herstellen können sollen.

Weitere Informationen finden Sie unter [Verwalten von Richtlinien für den externen Zugriff in lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Konfigurieren eines freigegebenen SIP-Adressraums

Um lokale lync Server 2013 mit Exchange Online zu integrieren, müssen Sie einen freigegebenen SIP-Adressraum konfigurieren. Derselbe SIP-Domänen Adressraum wird sowohl von lync Server als auch vom Exchange Online Dienst unterstützt.

Konfigurieren Sie mithilfe der lync Server-Verwaltungsshell den Edgeserver für den Verbund, indem Sie das Cmdlet " **csaccessedgeconfiguration nicht angeben** " mit den im folgenden Beispiel angezeigten Parametern ausführen:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** gibt an, ob interne Benutzer mit Benutzern aus Partnerdomänen kommunizieren dürfen. Diese Eigenschaft bestimmt auch, ob interne Benutzer mit Benutzern in einem freigegebenen SIP-Adressraum Szenario mit lync Server und Exchange Online kommunizieren können.

Ausführliche Informationen zur Verwendung des lync Server-Verwaltungsshell finden Sie unter [lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Konfigurieren eines Hostinganbieters auf dem Edgeserver

Verwenden Sie die lync Server-Verwaltungsshell, um einen Hostinganbieter im Edgeserver zu konfigurieren. Führen Sie dazu das Cmdlet **New-CsHostingProvider** mit den Parametern im folgenden Beispiel aus:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Wenn Sie Office 365 betrieben von 21Vianet in China verwenden, ersetzen Sie den Wert für den Parameter <STRONG>ProxyFqdn</STRONG> in diesem Beispiel ("exap.um.Outlook.com") durch den FQDN für den Dienst, der von 21Vianet verwaltet wird: "exap.um.Partner.Outlook.cn".



</div>

  - **Identity** gibt einen eindeutigen Bezeichner für den Zeichenfolgenwert für den Hostinganbieter an, den Sie erstellen (beispielsweise "Exchange Online"). Werte, die Leerzeichen enthalten, müssen in doppelte Anführungszeichen gesetzt werden.

  - **Enabled** gibt an, ob die Netzwerkverbindung zwischen Ihrer Domäne und dem Hostinganbieter aktiviert ist. Dies muss auf **true**festgelegt werden.

  - **EnabledSharedAddressSpace** gibt an, ob der Hostinganbieter in einem Szenario mit freigegebenem SIP-Adressraum verwendet wird. Dies muss auf **true**festgelegt werden.

  - **HostsOCSUsers** gibt an, ob der Hostinganbieter zum Hosten von Office Communications Server oder lync Server verwendet wird. Dies muss auf **false**festgelegt werden.

  - **ProxyFQDN** gibt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des vom Hostinganbieter verwendeten Proxyservers an. Für Exchange Online ist der FQDN "exap.um.outlook.com".

  - **IsLocal** gibt an, ob der vom Hostinganbieter verwendete Proxy Server in ihrer lync Server Topologie enthalten ist. Dies muss auf **false**festgelegt werden.

  - **"Verificationlevel"** gibt die zulässige Überprüfungsebene für Nachrichten an, die vom gehosteten Anbieter gesendet werden. Geben Sie **UseSourceVerification**an. Diese Option beruht auf der Überprüfungsebene, die in Nachrichten enthalten ist, die vom Hostinganbieter gesendet werden. Wenn diese Ebene nicht angegeben wird, wird die Nachricht als nicht überprüfbar zurückgewiesen.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Überprüfen der Replikation des aktualisierten zentralen Verwaltungsspeichers

Die Änderungen, die Sie mit den Cmdlets in den vorhergehenden Abschnitten vorgenommen haben, werden automatisch auf die Edgeserver angewendet und dauern in der Regel weniger als eine Minute, um repliziert zu werden. Sie können den Replikationsstatus überprüfen und die Änderungen mithilfe der folgenden Cmdlets auf Ihre Edgeserver anwenden.

Führen Sie das folgende Cmdlet aus, um Replikationsupdates auf einem internen Server in ihrer lync Server-Bereitstellung zu überprüfen:

    Get-CsManagementStoreReplicationStatus

Führen Sie das folgende Cmdlet auf dem Edgeserver aus, um sicherzustellen, dass die Änderungen übernommen wurden:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Voicemail für lync Server 2013-Benutzer in gehosteten Exchange um](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Hosted Exchange Unified Messaging-Integration in lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
