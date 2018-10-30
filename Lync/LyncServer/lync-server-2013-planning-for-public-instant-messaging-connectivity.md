---
title: Planen von Verbindungen mit öffentlichen Instant Messaging-Diensten
TOCTitle: Planen von Verbindungen mit öffentlichen Instant Messaging-Diensten
ms:assetid: e75e8884-05c7-414a-8014-bc9aa8126fb7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205349(v=OCS.15)
ms:contentKeyID: 49295739
ms.date: 03/09/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen von Verbindungen mit öffentlichen Instant Messaging-Diensten

 

_**Letztes Änderungsdatum des Themas:** 2017-03-09_

Die Verbindung mit öffentlichen Instant Messaging-Diensten stellt eine Partnerverbundklasse dar und wird konfiguriert, damit Ihre internen und externen Lync Server 2013-Benutzer die folgenden Kontakte hinzufügen können:

  - Messenger-Kontakte

  - Yahoo\! Kontakte

  - America Online (AOL)-Kontakte


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Instant Messaging-Diensten (PIC USL) nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Für AOL und Yahoo! wurde das Einstellungsdatum Juni 2014 angekündigt. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung nicht verlängert wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync-Standard-Clientzugriffslizenz (CAL). Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



Für diese Partnerverbundklasse sind die folgenden Planungsüberlegungen erforderlich:

  - Benutzer von Windows Live Messenger können die Peer-zu-Peer-Kommunikation per Audio/Video mit Benutzern von Lync Server 2013 sowie Chatdienste nutzen. Ihre Edgeserver müssen bestimmte Port- und Protokollanforderungen erfüllen. Ausführliche Informationen finden Sie unter [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - Für den Yahoo-Chatdienst gelten außer den üblichen Anforderungen für die Planung und Bereitstellung eines typischen Edgeservers mit Partnerverbundunterstützung keine speziellen Anforderungen.

  - Für America Online muss das Edgeserverzertifikat, das dem Zugriffs-Edgedienst zugewiesen ist, die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für den Client unterstützen.

## In diesem Abschnitt

  - [Zertifikatzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten](lync-server-2013-certificate-summary-public-instant-messaging-connectivity.md)

  - [Portzusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten](lync-server-2013-port-summary-public-instant-messaging-connectivity.md)

  - [DNS-Zusammenfassung für Verbindungen mit öffentlichen Instant Messaging-Diensten](https://technet.microsoft.com/de-de/library/jj618375\(v=ocs.15\))

