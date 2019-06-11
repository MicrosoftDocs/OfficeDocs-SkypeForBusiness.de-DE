---
title: Planen der lync Server-und Office Communications Server-Föderation
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>Planen der lync Server 2013-und Office Communications Server-Föderation

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-13_

Der Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server unterstützt Peer-to-Peer-und Mehrparteienkommunikation. Peer-to-Peer-Unterhaltungen können an mehr Parteien Unterhaltungen eskaliert werden, was zu Ad-hoc-Besprechungen führt. Besprechungen – Webkonferenzen oder Audio/visuelle Konferenzen – können so geplant werden, dass Sie Kontakte innerhalb Ihrer Organisation sowie Kontakte in Partner einbeziehen, mit denen Sie eine Föderation aufnehmen.

Federation erschien zunächst in Microsoft Office Live Communications Server 2005 und unterstützte eine Art von Föderation, direkte Föderation. Für den direkten Verbund mussten Sie die SIP-Domäne (Session Initiation Protocol) des Partner Verbandes und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edge-Servers des Partners kennen. Mit Live Communications Server 2005 mit SP1 wurden zusätzliche Föderations Typen eingeführt, die alle DNS-SRV-Einträge (Domain Name System) benötigten, die von dem Partnerverbund zum Auffinden des Edgeserver veröffentlicht wurden. Die Terminologie für diese Version lautete:

  - *Erweiterte Föderation öffnen*: akzeptieren Sie einen beliebigen SIP-Domänennamen, und verwenden Sie DNS SRV zum Auffinden des Partner-Edge-Servers.

  - *Erweiterte Föderation*: Konfigurieren Sie den SIP-Domänennamen des Partners als Verbundpartner für Ihre Organisation, und verwenden Sie DNS SRV zum Auffinden des Partner-Edge-Servers.

  - *Direkter Verbund*: Konfigurieren Sie den SIP-Domänennamen und den FQDN des Partners auf dem Edgeserver des Partners.

  - *Server Zulassungsliste*: akzeptieren einer beliebigen Domäne, verwenden von DNS SRV zum Auffinden des Edgeserver eines Hostinganbieter oder eines öffentlichen Instant Messaging (im)-Verbindungs Anbieters

Microsoft Office Communications Server 2007 hat aktualisierte Namen für Verbundtypen eingeführt, um besser zu definieren, was die einzelnen Föderations Typen tatsächlich erreicht haben:

  - Open Enhanced Federation wurde als *erkannte Partner Domäne* bekannt

  - Erweiterte Föderation wurde als *zugelassene Partner Domäne* bekannt

  - Der direkte Verbund wurde als *zugelassener Partner Server* bekannt.

  - Server Zulassungsliste wurde als *Hostinganbieter* und *Öffentlicher Chat Anbieter* bekannt.

Microsoft lync Server 2010 hat eine schmalere Definition des Hostinganbieter-Anbieters in Übereinstimmung mit Microsoft lync Online 2010 und Microsoft Office 365 eingeführt und außerdem der gleichen zulässigen Liste unterzogen, die durch den Föderations zugelassene Partner Domäne definiert ist.

Wenn Sie den Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server aktivieren, werden die Edgeserver und Reverse Proxys verwendet, um die von Ihnen definierten Regeln und zulässigen Partnerdomänen zu erzwingen. Aus Planungssicht erfordert die Zusammenarbeit mit anderen lync-Servern in Office Communications Server Folgendes:

  - Aktivieren der Föderation im Topologie-Generator Ausführliche Informationen finden Sie im Bereitstellungs Thema [Konfigurieren von SIP Federation, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Ermitteln Sie Ihre Anforderungen für die Föderationsdomänen Ermittlung:
    
      - <span></span>  
        Für die manuelle Konfiguration von Federation müssen Sie über den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edge-Servers des Partners und des Domänennamens oder des Online Domänennamens verfügen, der in der lync Server-Systemsteuerung, in der **Föderation und im externen Zugriff**, SIP eingegeben wird. ** Föderationsdomänen**. Erstellen Sie eine **neue** Richtlinie, oder **Bearbeiten** Sie eine vorhandene Richtlinie, damit Domänen nach FQDN zugelassen oder blockiert werden.
        
        <div>
        

        > [!WARNING]
        > Die manuelle Konfiguration des Edge-Servers eines Verbundpartners ist für den Fall anfällig, dass der Partner die IP-Adresse seines Edge-Servers ändert.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Für <STRONG>neue SIP-Verbunddomänen</STRONG>müssen Sie den <STRONG>Domänennamen (oder den FQDN)</STRONG> für Microsoft lync Online, Microsoft Office 365, angeben. Für Microsoft lync Server 2013, lync Server 2010 und Office Communications Server müssen Sie auch einen <STRONG>Access Edge Service (FQDN)</STRONG> bereitstellen.

        
        </div>
    
      - <span></span>  
        Für entdeckten Partnerverbund, in dem Partner ihren Edgeserver entdecken können, erstellen Sie einen SRV-Eintrag in Ihrem \_externen DNS-sipfederationtls. \_TCP.contoso.com – verweist auf den Port 5061 und den Host (A)-Eintrag Ihres Edge-Servers
        
        <div>
        

        > [!IMPORTANT]
        > Wenn Sie Microsoft lync Mobile-Clients auf Windows Phone oder Apple iPhone, iPad oder anderen Apple-Geräten unterstützen und den Push-Benachrichtigungsdienst oder den Push-Benachrichtigungsdienst verwenden, müssen Sie _sipfederationtls. _tcp planen. &lt;SIP-&gt; Domänen-SRV-Einträge für jede SIP-Domäne, auf der Sie lync Mobile-Clients haben. Android und Nokia Symbian lync Mobile verwenden keine Push-Benachrichtigung und unterliegen nicht dieser Anforderung.

        
        </div>

  - Konfigurieren von Richtlinien für den externen Benutzer Zugriff zur Unterstützung von Verbunddomänen

  - Öffnen Sie die Firewall-Ports für SIP (Session Initiation Protocol), Webkonferenzen und Audio/visuell, um die von Ihnen aktivierte Föderation oder Kontakte aufnehmen zu können. Ausführliche Informationen finden Sie unter: [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Die folgenden Informationen unterstützen Sie bei der Definition der Zertifikat-, Port/Protokoll-und DNS-Anforderungen für den Verbund mit Microsoft lync Server 2013 und lync Server 2010.

Die Planung für Zertifikate, Firewall-und Port/Protocol-Anforderungen und DNS-Anforderungen ist in der Regel ein geradliniger Prozess, wenn Sie Ihre Microsoft lync Server 2013-Edgeserver geplant oder bereitgestellt haben. Da es sich bei der Föderation um ein zusätzliches Feature handelt, das den vorhandenen Edgeserver verwendet, werden die Planungsanforderungen in der Regel von der Planung und Bereitstellung des Edge-Servers erfüllt. Verwenden Sie die folgenden Tabellen, um festzustellen, ob Ihre Anforderungen erfüllt sind, und nehmen Sie dementsprechend Änderungen an Port/Protokoll und DNS vor.

<div>


> [!IMPORTANT]
> Wenn Sie über einen Pool von Edge-Servern verfügen und mit lync Server 2013-oder lync Server 2010-Partnern zusammenarbeiten, können Sie entweder den DNS-Lastenausgleich oder Hardwarelastenausgleichs auf der internen und externen Seite der Edgeserver verwenden. Wenn Sie mit Office Communications Server 2007 oder Office Communications Server 2007 R2 eine Föderation durchführen, bietet der Hardwarelastenausgleich eine Failover-Unterstützung für den Fall eines Edgeserver. Office Communications Server 2007 und Office Communications Server 2007 R2 sind nicht für den DNS-Lastenausgleich bekannt. Die Partner-Edgeserver richten die Kommunikation mit dem ersten Edgeserver in Ihrem Pool ein, der antwortet. Wenn dieser Edge-Server ausfällt, wird die Kommunikation nicht automatisch Failover.



</div>

Die Zertifikatanforderungen werden in der Regel durch die Planung von Zertifikaten für den ausgewählten Edgeserver oder den Pooled Edge Server-Plan erfüllt.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Port Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

