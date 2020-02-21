---
title: 'Lync Server 2013: Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31aa51647fa19a11cb4944829c2ab5e8eb10f2e7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a>Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Dies ist eine vorläufige Dokumentation und kann jederzeit geändert werden. Leere Themen wurden als Platzhalter hinzugefügt.

Nachdem Sie einen oder mehrere Edgeserver bereitgestellt haben, müssen Sie die Typen des externen Domänen-oder Anbieter Zugriffs, den Remotebenutzerzugriff und den anonymen Benutzer Zugriff auf Konferenzen über die Edgeserver aktivieren, die für Ihre Organisation unterstützt werden.

Zu diesen Optionen gehören die folgenden Zugriffsarten, die auf der Seite **Zugriffs-Edgekonfiguration** konfiguriert werden können:

  - **Enable Federation and Public Chat Connectivity**   aktivieren Sie diese Option, wenn Sie den Benutzer Zugriff auf Verbundpartner Domänen unterstützen möchten. Diese Einstellung gilt gleichermaßen für SIP- und XMPP-Partnerverbunde, die auf der Seite **Externe Zugriffsrichtlinie** für die Bereiche "Global", "Standort" oder "Benutzer" konfiguriert sind. Damit die Partnerverbundeinstellungen gelten, müssen Sie die Partnerverbundunterstützung auf beiden Seiten konfigurieren.
    
    Es sind zwei Optionen vorhanden, bei denen es sich um optionale Einstellungen zur Erkennung von Verbundpartnern handelt. Damit wird auch festgelegt, ob Archivierungshaftungsausschlüsse (Benachrichtigung an Verbundkontakte, mit denen Sie kommunizieren, dass für Ihre Bereitstellung die Archivierung aktiviert ist und dass Kommunikationsdetails archiviert werden) an Kontakte gesendet werden.
    
      - **Partnerdomänen Ermittlung**   aktivieren Wenn Sie diese Option auswählen, wird die automatische Erkennung von Domänen aktiviert, mit denen Sie eine Föderation durcharbeiten können. Lync Server 2013 verwendet Domain Name System (DNS) Datensätze, um zu versuchen, Domänen zu ermitteln, die nicht in der Liste zugelassene Domänen aufgeführt sind, und den eingehenden Datenverkehr von erkannten Partner Partnern automatisch auswerten und den Datenverkehr basierend auf der Vertrauensebene einschränken oder blockieren Umfang des Datenverkehrs und Administratoreinstellungen. Wenn Sie diese Option nicht auswählen, wird der Verbundbenutzer Zugriff nur für Benutzer in den Domänen aktiviert, die Sie in die Liste zugelassene Domänen einschließen. Unabhängig davon, ob Sie diese Option auswählen, können Sie angeben, dass einzelne Domänen blockiert oder zugelassen werden sollen, einschließlich der Einschränkung des Zugriffs auf bestimmte Server, auf denen die Zugriffs-Edgedienst in der Verbunddomäne aufgeführt wird. Ausführliche Informationen finden Sie unter [Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).
    
      - **Archivierungs Disclaimer an Verbundpartner**   senden wenn Sie diese Option auswählen, wird das Senden einer Archivierungs haftungsaus Schluss Nachricht an Verbundpartner ermöglicht, die Ihnen mitteilen, dass Kommunikationsdetails aufgezeichnet werden. Wenn Sie die externe Kommunikation mit Verbundpartnerdomänen archivieren, sollten Sie die Benachrichtigung über den Archivierungshaftungsausschluss aktivieren, um die Partner über die Archivierung ihrer Nachrichten und Kommunikationsdetails durch Ihre Bereitstellung in Kenntnis zu setzen. Ausführliche Informationen zur Archivierung finden Sie unter [Definieren der Anforderungen für die Archivierung in lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).

  - **Remotebenutzerzugriff**   aktivieren aktivieren Sie diese Option, wenn Benutzer in Ihrer Organisation, die sich außerhalb Ihrer Firewall befinden, wie etwa Telearbeiter und Benutzer, die unterwegs sind, eine Verbindung mit lync Server herstellen können sollen. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

  - **Aktivieren anonymer Benutzer für den Zugriff auf Konferenzen**   aktivieren Sie diese Option, wenn interne Benutzer externe anonyme Benutzer zu Konferenzen einladen möchten, die Sie organisieren. Wenn Sie diese Einstellung aktivieren, sind nur anonyme Benutzer für Konferenzen zugelassen. Informationen zum Konfigurieren der Konferenzfunktionen und-Optionen, die definieren, wie und was Ihre Benutzer mit Konferenzen und für die Einbindung anonymer Benutzer tun können, finden Sie unter Details unter [Create or Modify Conferencing User Experience for a Site or users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing Policy Settings Reference for lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>


> [!NOTE]  
> Zusätzlich zur Unterstützung des Zugriffs externer Benutzer können Sie auch Richtlinien konfigurieren, mit denen die Verwendung des Remotebenutzerzugriffs in Ihrer Organisation gesteuert wird, bevor Benutzer den Zugriff für externe Benutzer verwenden können. Ausführliche Informationen zum Erstellen, konfigurieren und Anwenden von Richtlinien für den Zugriff durch externe Benutzer finden Sie unter <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage External Access Policy in lync Server 2013</A>.



</div>

**Anzeigen von Informationen zur Zugriffs-Edge-Konfiguration mithilfe von Windows PowerShell-Cmdlets**

  - Informationen zur Zugriffs-Edge-Konfiguration können mit Windows PowerShell und dem Cmdlet **Get-csaccessedgeconfiguration nicht angeben** angezeigt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.
    
    Geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Einstellungen für die Zugriffs-Edge-Konfiguration anzuzeigen:
    
        Get-CsAccessEdgeConfiguration
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Zugriffs anonymer Benutzer in lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

