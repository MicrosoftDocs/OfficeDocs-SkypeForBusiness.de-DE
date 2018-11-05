---
title: Planen von Lync Server- und Office Communications Server-Partnerverbünden
TOCTitle: Planen von Lync Server- und Office Communications Server-Partnerverbünden
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205335(v=OCS.15)
ms:contentKeyID: 49295399
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von Lync Server- und Office Communications Server-Partnerverbünden

 

_**Letztes Änderungsdatum des Themas:** 2013-02-13_

Der Partnerverbund zwischen Microsoft Lync Server 2013, Lync Server 2010 und Office Communications Server unterstützt die Peer-zu-Peer-Kommunikation und die Kommunikation mit mehreren Teilnehmern. Peer-zu-Peer-Unterhaltungen können auf Unterhaltungen mit mehreren Teilnehmern ausgeweitet werden, wodurch spontane Besprechungen ermöglicht werden. Besprechungen – Webkonferenzen oder Audio/Videokonferenzen – können so geplant werden, dass Kontakte innerhalb Ihrer Organisation sowie Kontakte bei Partnern, mit denen Sie einen Partnerverbund eingegangen sind, einbezogen werden.

Der Partnerverbund wurde in Microsoft Office Live Communications Server 2005 eingeführt und unterstützte eine Art von Partnerverbund, nämlich den direkten Partnerverbund. Für den direkten Partnerverbund mussten Sie die SIP-Domäne (Session Initiation Protocol) und den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Edgeservers des Verbundpartners kennen. In Live Communications Server 2005 mit SP1 wurden zusätzliche Partnerverbundtypen eingeführt, für die DNS SRV-Einträge vom Verbundpartner veröffentlicht werden mussten, um den Edgeserver aufzufinden. Für diese Version wurde folgende Terminologie verwendet:

  - *Öffentlicher erweiterter Verbund*: Jeder SIP-Domänenname wird akzeptiert, und DNS SRV wird zum Auffinden des Edgeservers des Partners verwendet.

  - *Erweiterter Verbund*: Der SIP-Domänennamen des Partners wird als Verbundpartner für Ihre Organisation konfiguriert, und DNS SRV wird zum Auffinden des Edgeservers des Partners verwendet.

  - *Direkter Verbund*: Der SIP-Domänenname und der FQDN des Partners werden für den Edgeserver des Partners konfiguriert.

  - *Serverzulassungsliste*: Jede Domäne wird akzeptiert, DNS SRV wird zum Auffinden des Edgeservers eines Hostinganbieters oder eines Chatdienstanbieters verwendet.

In Microsoft Office Communications Server 2007 wurden aktualisierte Namen für Partnerverbundtypen eingeführt, um die Funktion der einzelnen Partnerverbundtypen besser zu definieren:

  - Aus dem öffentlichen erweiterten Verbund wurde die *erkannte Partnerdomäne*

  - Aus dem erweiterten Verbund wurde die *zulässige Partnerdomäne*

  - Aus dem direkten Verbund wurde der *zulässige Partnerserver*

  - Aus der Serverzulassungsliste wurde der *Hostinganbieter* und der *öffentliche Chatanbieter*

In Microsoft Lync Server 2010 wurde eine enger gefasste Definition des Hostinganbieters gemäß Microsoft Lync Online 2010 und Microsoft Office 365 eingeführt, und außerdem wurde die vom Verbundpartnertyp "zulässige Partnerdomäne" definierte Zulassungsliste verwendet.

Für den Partnerverbund zwischen Microsoft Lync Server 2013, Lync Server 2010 und Office Communications Server werden mit den Edgeservern und Reverseproxys die von Ihnen definierten Regeln und zulässigen Partnerdomänen erzwungen. Aus Sicht der Planung ist für den Partnerverbund mit anderen Lync Server-Instanzen für Office Communications Server Folgendes erforderlich:

  - Aktivieren Sie den Partnerverbund im Topologie-Generator. Ausführliche Informationen finden Sie im Bereitstellungsthema [Konfigurieren von SIP-Partnerverbünden, XMPP-Partnerverbünden und öffentlichem Chat in Lync Server 2013](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md).

  - Bestimmen Sie Ihre Anforderungen für die Erkennung von Partnerverbunddomänen:
    
      - Für die manuelle Konfiguration des Partnerverbunds benötigen Sie den vollqualifizierten Domänennamen (FQDN) des Edgeservers des Partners und den Domänennamen, oder Onlinedomänennamen, der in der Lync Server-Systemsteuerung unter **Partnerverbund und externer Zugriff**, **SIP-Partnerverbunddomänen** eingegeben wird. Erstellen Sie eine neueRichtlinie, oder bearbeitenSie eine vorhandene Richtlinie, um Domänen anhand des FQDN zuzulassen oder zu blockieren.
        

        > [!WARNING]
        > Die manuelle Konfiguration des Edgeservers eines Verbundpartners ist fehleranfällig, falls der Partner die IP-Adresse des Edgeservers ändert.

        

        > [!NOTE]
        > Für neue SIP-Partnerverbunddomänenmüssen Sie eine Eingabe in <STRONG>Domänenname (oder FQDN)</STRONG> für Microsoft Lync Online, Microsoft Office 365 vornehmen. Für Microsoft Lync Server 2013, Lync Server 2010 und Office Communications Server müssen Sie auch eine Eingabe für <STRONG>Zugriffs-Edgedienst (FQDN)</STRONG> vornehmen.

    
      - Für die Partnerverbunderkennung, bei der Partner Ihren Edgeserver erkennen können, erstellen Sie einen SRV-Eintrag in Ihrem externen DNS (\_sipfederationtls.\_tcp.contoso.com), der auf Port 5061 und den Hosteintrag (A) Ihres Edgeservers verweist.
        

        > [!IMPORTANT]
        > Wenn Sie Microsoft Lync Mobile-Clients unter Windows Phone oder Apple iPhone, iPad oder sonstigen Apple-Geräten unterstützen und den Pushbenachrichtigungsdienst oder Pushbenachrichtigungsdienst verwenden, müssen Sie _sipfederationtls._tcp. <EM>&lt;SIP-Domäne&gt;</EM>-SRV-Einträge für jede SIP-Domäne einplanen, für die Sie über Lync Mobile-Clients verfügen. Android und Nokia Symbian Lync Mobile verwenden die Pushbenachrichtigung nicht, weshalb diese Anforderung in diesem Falle nicht zutrifft.



  - Konfigurieren Sie Richtlinien für den Zugriff durch externe Benutzer, um Partnerverbunddomänen zu unterstützen.

  - Öffnen Sie Firewallports für SIP (Session Initiation Protocol), Webkonferenzen und Audio/Video, um den Partnerverbund oder die Kontakte, die Sie aktivieren, zu ermöglichen. Ausführliche Informationen finden Sie unter [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

Die folgenden Informationen helfen Ihnen beim Definieren der Zertifikat-, Port/Protokoll- und DNS-Anforderungen für den Partnerverbund mit Microsoft Lync Server 2013 und Lync Server 2010.

Das Planen der Zertifikat-, Firewall-, Port/Protokoll- und DNS-Anforderungen ist im Allgemeinen ein einfacher Vorgang, wenn Sie Ihre Microsoft Lync Server 2013-Edgeserver geplant oder bereitgestellt haben. Da es sich beim Partnerverbund um ein zusätzliches Feature handelt, das den vorhandenen Edgeserver verwendet, werden die Planungsanforderungen im Allgemeinen von der Planung und Bereitstellung der Edgeserver erfüllt. Sie sollten anhand der folgenden Tabellen bestimmen, ob Ihre Anforderungen erfüllt sind, und entsprechend Änderungen im Hinblick auf Port/Protokoll und DNS vornehmen.


> [!IMPORTANT]
> Wenn Sie einen Pool von Edgeservers verwenden und einen Partnerverbund mit Lync Server 2013- oder Lync Server 2010-Partnern einrichten, können Sie den DNS-Lastenausgleich oder Hardwaregeräte zum Lastenausgleich auf der internen und externen Seite der Edgeserver verwenden. Wenn Sie einen Partnerverbund mit Office Communications Server 2007 oder Office Communications Server 2007 R2 einrichten, unterstützen Hardwaregeräte zum Lastenausgleich das Failover für einen Edgeserver. Office Communications Server 2007 und Office Communications Server 2007 R2 unterstützen den DNS-Lastenausgleich nicht. Die Partner-Edgeserver stellen die Kommunikation mit dem ersten Edgeserver im Pool her, der antwortet. Falls dieser Edgeserver ausfällt, erfolgt kein automatisches Failover für die Kommunikation.



Zertifikatanforderungen werden in der Regel durch die Planung von Zertifikaten für Ihren gewählten Edgeserver- oder Pool-Edgeserver-Plan erfüllt.

## In diesem Abschnitt

  - [Zertifikatzusammenfassung – SIP, XMPP-Partnerverbund und öffentliche Chatdienste](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Portzusammenfassung – SIP, XMPP-Partnerverbund und Chat in öffentlichen Netzen](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS-Zusammenfassung - SIP-, XMPP-Partnerverbund und öffentliche Chatdienste](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

## Siehe auch

#### Aufgaben

[Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md)  

#### Konzepte

[Szenarien für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
[Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[Ermitteln von DNS-Anforderungen für Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  

#### Weitere Ressourcen

[Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

