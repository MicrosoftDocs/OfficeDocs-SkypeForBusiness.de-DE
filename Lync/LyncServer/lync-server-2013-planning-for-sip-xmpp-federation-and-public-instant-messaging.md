---
title: Planen von SIP, XMPP Federation und Public Instant Messaging
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 994a1395363c28976c8bbfe325edae99e97cdc48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planen von SIP, XMPP Federation und Public Instant Messaging in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-28_

Edgeserver können so konfiguriert werden, dass Sie Ihren internen und externen Benutzern den Zugriff auf Kontakte in Partnerorganisationen oder-Diensten gestatten. Föderationen können, wie diese Partnervereinbarungen bekannt sind, den Kontakten in Ihrer Organisation im Partnerverbund oder Kontakten in der Partner Föderation eine oder alle folgenden Informationen zur Verfügung stellen:

  - Chat und Anwesenheit

  - Zusammenarbeit und Konferenz, beispielsweise Web-Conferencing

  - Audiokonferenzen, Videokonferenzen oder beides

In einigen Fällen ist die Kommunikation, beispielsweise Instant Messaging (im) und Anwesenheitsinformationen zwischen einem Microsoft lync Server 2013 und einem Kontakt mit einem erweiterbaren Messaging-und Anwesenheits Protokoll (XMPP), nur Peer-to-Peer-Unterstützung nur von Ihnen und dem Kontakt im Verbund Partner. In anderen Fällen, wie lync Server, lync Server 2010, lync Server 2013 Federation können mehrere Teilnehmer eingeladen werden, an der Unterhaltung teilzunehmen.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server und Office Communications Server-Föderation

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
        Für die manuelle Konfiguration von Federation müssen Sie über den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edge-Servers des Partners und des Domänennamens oder des Online Domänennamens verfügen, der in der lync Server-Systemsteuerung, in der **Föderation und im externen Zugriff**, **SIP-Verbunddomänen**eingegeben wird. Erstellen Sie eine **neue** Richtlinie, oder **Bearbeiten** Sie eine vorhandene Richtlinie, damit Domänen nach FQDN zugelassen oder blockiert werden.
        
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

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Öffentliche Instant Messaging-Konnektivität

Die öffentliche Instant Messaging-Konnektivität ist eine Klasse des Föderations-und ist so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden hinzufügen können:

  - Messenger-Kontakte

  - Yahoo\! Kontakte

  - America Online (AOL)-Kontakte

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public Chat-Benutzerabonnementlizenz (PIC USL) nicht mehr für den Kauf für neue oder erneuernde Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger bis zum Shutdown-Datum des Diensts (das genaue Datum wird noch entschieden, aber frühestens Juni 2013).</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine pro Benutzer/Monat-Abonnementlizenz, die für lync Server oder Office Communications Server für die Föderation mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung nicht verlängert werden sollte.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen über Chat und Sprache zu erreichen.</P></LI></UL>



</div>

Für diese Föderations Klasse sind die folgenden Planungsüberlegungen erforderlich:

  - Benutzer von Windows Live Messenger können neben Instant Messaging auch eine Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern führen. Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen. Ausführliche Informationen finden Sie unter [ermitteln externer A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die normalerweise bei der Planung und Bereitstellung des typischen Edgeserver verwendet werden, der Föderation bereitstellt.

  - Für America Online ist es erforderlich, dass Ihr Edge-Server-Zertifikat, das dem Access-Edgedienst zugewiesen ist, über eine erweiterte Client-Schlüsselverwendung verfügt.

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>Extensible Messaging and Presence Protocol (XMPP)-Föderation

In früheren Versionen von lync Server und Office Communications Server wurde ein Extensible Messaging and Presence Protocol (XMPP)-Gateway bereitgestellt, das als separate Server Rolle bereitgestellt werden kann, um die Föderation mit XMPP-Bereitstellungen zu ermöglichen. In Microsoft lync Server 2013 kann die XMPP-Funktion als Feature bereitgestellt werden. Die XMPP-Funktionalität ist in zwei Teilen installiert: ein XMPP-Proxy, der auf dem Edgeserver ausgeführt wird, und das XMPP-Gateway, das auf den Front-End-Servern ausgeführt wird.

Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) , die Sie zur Unterstützung von xmpp in Ihrer Organisation planen, durch Definieren von Port-und Protokollregeln für Ihre Firewall, Konfiguration von Zertifikaten und Hinzufügen von DNS-Einträgen abgedeckt. In den folgenden Themen in diesem Abschnitt werden die Informationen zusammengefasst, die Sie benötigen, um die XMPP-Föderation für Ihre Bereitstellung erfolgreich zu planen.

<div>


> [!IMPORTANT]
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



</div>

<div>


> [!IMPORTANT]
> Die XMPP-Föderation wird für Benutzer nicht unterstützt, die sich auf Überlebenden Branch-Appliances befinden. Dies gilt sowohl für das Anzeigen von Anwesenheitsinformationen als auch für den Austausch von Chatnachrichten.



</div>

</div>

<div id="sectionSection3" class="section">

In den folgenden Themen finden Sie Anleitungen zum Definieren von Zertifikaten, Firewall-Ports und DNS-Einträgen für die Typen unterstützter Verbundszenarien.

  - <span></span>  
    [Zusammenfassung des Zertifikats – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Port Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [DNS-Zusammenfassung – SIP, XMPP Federation und Public Instant Messaging in lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

