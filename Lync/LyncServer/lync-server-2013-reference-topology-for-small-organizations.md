---
title: 'Lync Server 2013: Referenztopologie für kleine Unternehmen'
TOCTitle: Referenztopologie für kleine Unternehmen
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398095(v=OCS.15)
ms:contentKeyID: 49293028
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Referenztopologie für Lync Server 2013 in kleinen Unternehmen

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Referenztopologie für kleine Organisationen zeigt, wie Sie eine zuverlässige Lösung mit hoher Verfügbarkeit durch Bereitstellung von lediglich drei Servern mit Lync Server bereitstellen können.

**Referenztopologie für kleine Unternehmen**

![Referenztopologie mit drei Servern (Diagramm)](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Referenztopologie mit drei Servern (Diagramm)")

  - **Paar bereitgestellter Standard Edition-Server**     Diese Organisation hat 4.000 Benutzer an ihrem Hauptstandort. Die Organisation hat zwei Standard Edition-Server bereitgestellt und diese als Paar zusammengefasst, um eine hohe Verfügbarkeit sowie Notfallwiederherstellung zu ermöglichen. Jeder Server hostet 2.000 Benutzer, die Informationen zu allen Benutzern werden aber zwischen den beiden Server synchronisiert. Fällt ein Server aus, kann ein Administrator ein Failover für diese Benutzer ausführen, sodass sie mit minimaler Unterbrechung von dem anderen Server gehostet werden. Weitere Informationen zu den Features für hohe Verfügbarkeit und Notfallwiederherstellung in Lync Server 2013 finden Sie unter [Planen der hohen Verfügbarkeit und der Notfallwiederherstellung in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

  - **Empfehlung zur Bereitstellung eines Edgeservers.**    Wenngleich die Bereitstellung eines Edgeservers für das interne Instant Messaging, für Anwesenheitsinformationen und Konferenzen nicht erforderlich ist, wird sie selbst für kleine Bereitstellung empfohlen. Sie können Ihre Investition in Lync Server maximieren, indem Sie einen Edgeserver zur Bereitstellung von Diensten für Benutzer implementieren, die sich aktuell außerhalb der Organisationsfirewall befinden. Es bieten sich folgende Vorteile:
    
      - Die organisationseigenen Benutzer können die Lync Server-Funktionalität nutzen, wenn sie von zu Hause oder unterwegs arbeiten.
    
      - Ihre Benutzer können externe Benutzer zur Teilnahme an Besprechungen einladen.
    
      - Wenn Sie mit einer Partner-, Lieferanten- oder Kundenorganisation zusammenarbeiten, die ebenfalls Lync Server einsetzt, können Sie eine *Partnerverbundbeziehung* mit dieser Organisation einrichten. Benutzer dieser Partnerorganisation werden anschließend in Ihrer Lync Server-Bereitstellung erkannt, wodurch die Zusammenarbeit verbessert wird.
    
      - Ihre Benutzer können Chatnachrichten mit Benutzern von öffentlichen Instant Messaging-Diensten austauschen, darunter: Windows Live, AOL, Yahoo\! und Google Talk. Für Verbindungen mit diesen öffentlichen Instant Messaging-Diensten ist möglicherweise eine separate Lizenz erforderlich.
        

        > [!IMPORTANT]
        > <UL>
        > <LI>
        > <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
        > <LI>
        > <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
        > <LI>
        > <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



  - **Ausfallsicherheit für Zweigstellen.**    Die Organisation führt ein Pilotprogramm zur Enterprise-VoIP-Funktion von Lync Server durch. Einige Benutzer verwenden Lync Server als alleinige VoIP-Lösung. Einige dieser VoIP-Pilotbenutzer befinden sich am Zweigstellenstandort. Der Zweigstellenstandort ist nicht über eine zuverlässige WAN (Wide Area Network)-Leitung mit dem zentralen Standort verbunden, daher wurde am Zweigstellenstandort eine Survivable Branch-Anwendung bereitgestellt. Dank der Survivable Branch Appliance können die Benutzer am Zweigstellenstandort bei Ausfall der WAN-Verbindung weiterhin Anrufe tätigen und entgegennehmen (sowohl innerhalb der Organisation als auch über das Festnetz), die Voicemailfunktion nutzen und per Instant Messaging kommunizieren. Benutzer können darüber hinaus auch dann authentifiziert werden, wenn die WAN-Verbindung nicht verfügbar ist.

  - **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (UM)-Server, auf dem nicht Lync Server, sondern Microsoft Exchange Server ausgeführt wird.
    
    Ausführliche Informationen zu Exchange UM finden Sie unter [Planen der Integration von Exchange Unified Messaging in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [Integration in gehostete Exchange Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.

  - **Office Web Apps Server** Es wird empfohlen, eine Office Web Apps Server- oder Office Web Apps Server-Farm in allenOrganisationen bereitzustellen, die Webkonferenzen verwenden. Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

