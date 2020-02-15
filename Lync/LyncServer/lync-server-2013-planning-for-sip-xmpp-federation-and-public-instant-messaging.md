---
title: Planung für SIP, XMPP-Partnerverbund und öffentliche Sofortnachrichten
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
ms.openlocfilehash: d2070d9e977a730b7c667a2c49a7e896d1309eef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>Planung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-28_

Edgeserver können so konfiguriert werden, dass ihren internen und externen Benutzern der Zugriff auf Kontakte in Partnerorganisationen oder-Diensten ermöglicht wird. Diese Partnervereinbarung wird als Partnerverbund bezeichnet und stellt für Kontakte in Ihrer Organisation oder für Kontakte in der Partnerorganisation, die zum Partnerverbund gehören, beliebige oder alle der folgenden Funktionen bereit:

  - Chat und Anwesenheit

  - Zusammenarbeit und Konferenzen, z. B. Webkonferenz

  - Audiokonferenz, Videokonferenz oder beides

In einigen Fällen ist die Kommunikation, beispielsweise Chatnachrichten und Anwesenheitsinformationen zwischen einem Microsoft lync Server 2013 und einem XMPP-Kontakt (Extensible Messaging and Presence Protocol) nur Peer-zu-Peer-Unterstützung nur Sie und der Kontakt im Verbund Partner. In anderen Fällen, beispielsweise in einer lync Server, lync Server 2010 lync Server 2013 Partnerverbund können mehrere Teilnehmer eingeladen werden, um an der Unterhaltung teilzunehmen.

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server und Office Communications Server Partnerverbund

Partnerverbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server unterstützt Peer-to-Peer-und Mehrparteienkommunikation. Peer-zu-Peer-Unterhaltungen können an mehr Parteien Unterhaltungen weitergeleitet werden, sodass Ad-hoc-Besprechungen möglich sind. Besprechungen – Webkonferenzen oder Audio/visuelle Konferenzen – können so geplant werden, dass Sie Kontakte in Ihrer Organisation sowie Kontakte in Partnergruppen einbeziehen, mit denen Sie verbündet sind.

Der Verbund erschien zunächst in Microsoft Office Live Communications Server 2005 und unterstützte eine Art von Verbund, direktem Verbund. Für den direkten Verbund mussten Sie die SIP-Domäne (Session Initiation Protocol) des Partnerverbund Partners und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver des Partners kennen. Live Communications Server 2005 mit SP1 wurden zusätzliche Verbundtypen eingeführt, für die alle DNS-SRV-Einträge (Domain Name System) vom Partnerverbund veröffentlicht werden mussten, um Ihre Edgeserver zu finden. Die Terminologie für diese Version lautete:

  - *Open Enhanced Federation*: akzeptieren Sie einen beliebigen SIP-Domänennamen, und verwenden Sie DNS-SRV zum Auffinden der Partner Edgeserver

  - *Erweiterter Verbund*: Konfigurieren Sie den SIP-Domänennamen des Partners als Verbundpartner für Ihre Organisation, und verwenden Sie DNS-SRV, um den Partner zu finden Edgeserver

  - *Direkter Verbund*: Konfigurieren Sie den SIP-Domänennamen des Partners und den FQDN für den Edgeserver des Partners.

  - *Server Zulassungsliste*: akzeptieren einer beliebigen Domäne, verwenden von DNS-SRV zum Auffinden der Edgeserver eines Hostinganbieter oder eines Anbieters für öffentliche Chatnachrichten (Instant Messaging)

Microsoft Office Communications Server 2007 wurde die aktualisierte Benennung von Verbundtypen eingeführt, um besser zu definieren, was die einzelnen Verbundtypen tatsächlich erreicht haben:

  - Open Enhanced Federation wurde als *entdeckte Partner Domäne* bezeichnet

  - Erweiterter Verbund wurde als *zugelassene Partner Domäne* bezeichnet

  - Der direkte Verbund wurde als *zulässiger Partner Server* bezeichnet.

  - Server Zulassungsliste wurde als *Hostinganbieter* und *Öffentlicher Chat Anbieter* bezeichnet

Microsoft lync Server 2010 eine engere Definition des Hostinganbieter in Übereinstimmung mit Microsoft lync Online 2010 und Microsoft Office 365 eingeführt und unterliegt außerdem der gleichen zulässigen Liste, die vom Partner Domänen-Verbundtyp zulässig definiert wurde.

Das Aktivieren des Verbund zwischen Microsoft lync Server 2013, lync Server 2010 und Office Communications Server verwendet die Edgeserver und Reverse Proxies, um die von Ihnen definierten Regeln und zulässigen Partnerdomänen zu erzwingen. Aus Planungssicht und Verbund mit anderen lync Server erfordert Office Communications Server Folgendes:

  - Aktivieren Sie den Partnerverbund im Topologie-Generator. Ausführliche Informationen finden Sie im Bereitstellungs Thema [Konfigurieren des SIP-Verbunds, des XMPP-Verbunds und der öffentlichen Sofortnachrichten in lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Bestimmen der Anforderungen für die Verbunddomänen Ermittlung:
    
      - <span></span>  
        Für die manuelle Konfiguration des Verbunds benötigen Sie den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeserver und Domänennamens des Partners oder den Online Domänennamen, der in den **SIP-Verbunddomänen**lync Server-Systemsteuerung, Partner **Verbund und externer Zugriff**eingegeben wird. Erstellen Sie eine **neue** Richtlinie, oder **Bearbeiten** Sie eine vorhandene Richtlinie, um Domänen nach FQDN zuzulassen oder zu blockieren.
        
        <div>
        

        > [!WARNING]
        > Die manuelle Konfiguration des Edgeserver eines Partnerverbund Partners ist anfällig für den Fall, dass der Partner die IP-Adresse seiner Edgeserver ändert.

        
        </div>
        
        <div>
        

        > [!NOTE]
        > Für <STRONG>neue SIP-Verbunddomänen</STRONG>müssen Sie den <STRONG>Domänennamen (oder FQDN)</STRONG> für Microsoft lync Online Microsoft Office 365 angeben. Für Microsoft lync Server 2013, lync Server 2010 und Office Communications Server müssen Sie auch eine <STRONG>Zugriffs-Edgedienst (FQDN)</STRONG> bereitstellen.

        
        </div>
    
      - <span></span>  
        Für entdeckte Partnerverbund, in dem Partner ihre Edgeserver ermitteln können, erstellen Sie einen SRV-Eintrag in Ihrem externen \_DNS-sipfederationtls. \_TCP.contoso.com – der auf den Port 5061 und den Host (A)-Eintrag Ihrer Edgeserver zeigt
        
        <div>
        

        > [!IMPORTANT]
        > Wenn Sie Microsoft lync Mobile-Clients auf Windows Phone oder Apple iPhone, iPad oder anderen Apple-Geräten unterstützen und den Push-Benachrichtigungsdienst oder den Push-Benachrichtigungsdienst verwenden, müssen Sie _sipfederationtls. _tcp planen. &lt;SIP-&gt; Domänen-SRV-Einträge für jede SIP-Domäne, in der Sie lync Mobile-Clients haben. Android und Nokia Symbian lync Mobile verwenden keine Push-Benachrichtigung und unterliegen nicht dieser Anforderung.

        
        </div>

  - Konfigurieren von Richtlinien für den externen Benutzer Zugriff zur Unterstützung von Verbunddomänen

  - Öffnen Sie Firewall-Ports für SIP (Session Initiation Protocol), Webkonferenzen und Audio/visuell, um die zu aktivierende Föderation oder Kontakte aufzunehmen. Ausführliche Informationen finden Sie unter: [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Die folgenden Informationen helfen Ihnen beim Definieren der Zertifikate, Port/Protokoll-und DNS-Anforderungen für den Verbund mit Microsoft lync Server 2013 und lync Server 2010.

Die Planung von Zertifikaten, Firewall-und Port/Protocol-Anforderungen und DNS-Anforderungen ist in der Regel ein geradliniger Prozess, wenn Sie die Microsoft lync Server 2013-Edgeserver geplant oder bereitgestellt haben. Da es sich bei dem Verbund um ein zusätzliches Feature handelt, das die vorhandenen Edgeserver verwendet, werden die Planungsanforderungen im Allgemeinen von der Edgeserver Planung und Bereitstellung erfüllt. Verwenden Sie die folgenden Tabellen, um zu ermitteln, ob Ihre Anforderungen erfüllt sind, und ändern Sie entsprechend Port/Protocol und DNS.

<div>


> [!IMPORTANT]
> Wenn Sie einen Pool mit Edgeserver haben und mit lync Server 2013 oder lync Server 2010 Partnern zusammenschließen, können Sie entweder den DNS-Lastenausgleich oder Hardwarelastenausgleichs auf den internen und externen Seiten der Edgeserver verwenden. Wenn Sie einen Verbund mit Office Communications Server 2007 oder Office Communications Server 2007 R2 durchführen, bietet der Hardwarelastenausgleich im Fall eines Edgeserver eine Failover-Unterstützung. Office Communications Server 2007 und Office Communications Server 2007 R2 sind nicht mit dem DNS-Lastenausgleich vertraut. Die Partner-Edgeserver stellen die Kommunikation mit dem ersten Edgeserver in Ihrem Pool her, der antwortet. Wenn das Edgeserver fehlschlägt, wird bei der Kommunikation nicht automatisch ein Failover ausgeführt.



</div>

Zertifikatanforderungen werden normalerweise durch die Planung von Zertifikaten für den ausgewählten Edgeserver oder den Pooled Edgeserver-Plan erfüllt.

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>Verbindung mit öffentlichen Instant Messaging-Diensten

Die Verbindung mit öffentlichen Instant Messaging-Diensten ist eine Klasse von Verbund und wird so konfiguriert, dass Ihre internen und externen lync Server 2013-Benutzer Kontakte aus einem der folgenden Elemente hinzufügen können:

  - Messenger-Kontakte

  - Yahoo\! contacts

  - America Online (AOL)-Kontakte

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity User Subscription License (PIC USL) nicht mehr für den Kauf für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger bis zum Datum des Herunterfahrens des Diensts (das genaue Datum muss noch festgelegt werden, frühestens jedoch im Juni 2013).</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server erforderlich ist, um mit Yahoo! zu verbünden. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die nicht erneuert wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer über Chat und Voice Hunderte von Millionen von Benutzern erreichen können.</P></LI></UL>



</div>

Für diese Partnerverbundklasse sind die folgenden Planungsüberlegungen erforderlich:

  - Windows Live Messenger-Benutzer können über Peer-to-Peer-Audio/visuelle Kommunikation mit lync Server 2013-Benutzern sowie Chatnachrichten verfügen. Ihre Edgeserver müssen bestimmte Port-und Protokollanforderungen erfüllen. Ausführliche Informationen finden Sie unter [bestimmen der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md).

  - Yahoo Instant Messaging hat keine eindeutigen Anforderungen, außer denen, die in der Regel für die Planung und Bereitstellung der typischen Edgeserver verwendet werden, die den Verbund bereitstellt.

  - Für America Online ist es erforderlich, dass Ihr Edgeserver Zertifikat, das dem Zugriffs-Edgedienst zugewiesen ist, über eine verstärkte Schlüsselverwendung für Clients verfügt (EKU).

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>XMPP-Partnerverbund (Extensible Messaging and Presence Protocol)

In früheren Versionen von lync Server und Office Communications Server wurde ein XMPP-Gateway (Extensible Messaging and Presence Protocol) bereitgestellt, das als separate Server Rolle bereitgestellt werden könnte, um eine Verbundfunktion mit XMPP-Bereitstellungen zu ermöglichen. In Microsoft lync Server 2013 kann die XMPP-Funktionalität als Feature bereitgestellt werden. Die XMPP-Funktionalität wird in zwei Teilen installiert: einem XMPP-Proxy, der auf dem Edgeserver und dem XMPP-Gateway ausgeführt wird, das auf den Front-End-Servern ausgeführt wird.

Die Bereitstellung und Konfiguration von XMPP wird unter [Bereitstellen von externem Benutzer Zugriff in lync Server 2013](lync-server-2013-deploying-external-user-access.md) behandelt, in dem xmpp in Ihrer Organisation unterstützt werden soll, indem Sie Port-und Protokollregeln für Ihre Firewall, die Konfiguration von Zertifikaten und das Hinzufügen von DNS-Einträgen definieren. In den folgenden Themen in diesem Abschnitt werden die Informationen zusammengefasst, die Sie benötigen, um den XMPP-Partnerverbund für Ihre Bereitstellung erfolgreich zu planen.

<div>


> [!IMPORTANT]
> Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.



</div>

<div>


> [!IMPORTANT]
> Der XMPP-Verbund wird für Benutzer, die in Survivable Branch Appliances verwaltet werden, nicht unterstützt. Dies gilt sowohl für das Anzeigen von Anwesenheitsinformationen als auch für den Austausch von Chatnachrichten.



</div>

</div>

<div id="sectionSection3" class="section">

In den folgenden Themen finden Sie Anleitungen zum Definieren von Zertifikaten, Firewall-Ports und DNS-Einträgen für die Typen unterstützter Verbundszenarien.

  - <span></span>  
    [Zertifikatzusammenfassung für SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [Port Zusammenfassung-SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [DNS-Zusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatnachrichten in lync Server 2013](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Bestimmen der DNS-Anforderungen für lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation in lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

