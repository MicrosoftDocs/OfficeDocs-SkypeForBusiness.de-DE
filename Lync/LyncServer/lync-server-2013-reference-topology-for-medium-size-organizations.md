---
title: 'Lync Server 2013: Referenztopologie für mittelständische Organisationen'
TOCTitle: Referenztopologie für mittelständische Organisationen
ms:assetid: 446b0914-2198-445e-ab6e-94802acebd5c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425939(v=OCS.15)
ms:contentKeyID: 49293846
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Referenztopologie für Lync Server 2013 für mittelständische Organisationen

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Referenztopologie mit hoher Verfügbarkeit und einem einzelnen Rechenzentrum ist auf kleine bis mittelständische Organisationen mit einem zentralen Standort zugeschnitten. Die im folgenden Diagramm gezeigte exakte Topologie ist auf 20.000 Benutzer ausgelegt.

**Referenztopologie für mittelständische Organisationen**

![Referenztopologie für ein einziges Rechenzentrum (Diagramm)](images/Gg425939.12b574fd-0b14-4563-a88c-3c8b0809bb90(OCS.15).jpg "Referenztopologie für ein einziges Rechenzentrum (Diagramm)")

  - **Möglichkeit zur Unterstützung weiterer Benutzer durch das Hinzufügen zusätzlicher Front-End-Server.**    Die im Diagramm gezeigte Topologie umfasst drei Front-End-Server und kann daher bis zu 20.000 Benutzer unterstützen. Wenn Sie über einen einzelnen zentralen Standort und mehr Benutzer verfügen, können Sie dem Pool einfach weitere Front-End-Server hinzufügen. Die maximale Anzahl von Benutzern pro Pool beträgt 80.000, mit zwölf Front-End-Servern.
    
    Die Topologie mit einem einzelnen Standort kann jedoch noch mehr Benutzer unterstützen, wenn dem Standort ein weiterer Front-End-Pool hinzugefügt wird.

  - **Notfallwiederherstellung kann hinzugefügt werden.**    Für diese Organisation ist die hohe Verfügbarkeit ihrer Lync Server-Dienste eine erforderliche Funktion, die Notfallwiederherstellung jedoch nicht. Der bereitgestellte Pool von Front-End-Server bietet hohe Verfügbarkeit.
    
    Wenn die Fähigkeit zur Notfallwiederherstellung hinzugefügt werden soll, könnte die Organisation ein weiteres Rechenzentrum einrichten und dort einen weiteren Front-End-Pool hinzufügen, der dann mit dem Front-End-Pool im aktuellen Rechenzentrum kombiniert wird. Dadurch könnten die Administratoren bei einem Notfall, der den primären Pool betrifft, einen Failover der Benutzer auf den Sicherungspool durchführen.

  - **Back-End-Server werden gespiegelt.**   Für höhere Verfügbarkeit für grundlegende Benutzerfunktionen hat die Organisation ein gespiegeltes Paar von Back-End-Server für jeden Front-End-Pool bereitgestellt. Dabei handelt es sich um eine neue optionale Topologieoption für Lync Server 2013. Sie können stattdessen auch eine einzelne Back-End-Server bereitstellen.

  - **Optionen für die Monitoring Server-Datenbank.**    Diese Organisation hat Monitoring bereitgestellt, um die Qualität von Enterprise-VoIP-Anrufen und A/V-Konferenzen sicherzustellen. Monitoring wird auf jedem Front-End-Server bereitgestellt, und die Monitoring-Datenbank wird mit den Back-End-Servern verbunden. Außerdem werden Topologien unterstützt, in denen sich die Monitoring-Datenbank auf einem separaten Server befindet.

  - **Hohe Verfügbarkeit von Edgeservern.**    Für diese Beispielorganisation mit 20.000 Benutzern reicht ein Edgeserver zur Sicherstellung der Leistung aus. Es wird jedoch ein Pool mit zwei Edgeservern bereitgestellt, um hohe Verfügbarkeit sicherzustellen.

  - **Optionen für Bereitstellungen an Zweigstellenstandorten.**    Die Organisation in dieser Topologie hat Enterprise-VoIP als ihre VoIP-Lösung bereitgestellt. Zweigstellenstandort 1 ist nicht über eine ausfallsichere WAN-Verbindung mit dem zentralen Standort verbunden, deshalb wurde eine Survivable Branch-Anwendung bereitgestellt, die bei einem Ausfall der WAN-Verbindung mit dem zentralen Standort für die Aufrechterhaltung zahlreicher Lync Server-Funktionen sorgt. Zweigstellenstandort 2 verfügt über eine ausfallsichere WAN-Verbindung, daher wird nur ein PSTN-Gateway benötigt. Das bereitgestellte PSTN-Gateway unterstützt die Medienumgehung, deshalb wird an Zweigstellenstandort 2 kein Vermittlungsserver benötigt. Ausführliche Informationen dazu, welche Komponenten an einem Zweigstellenstandort bereitgestellt werden sollten, finden Sie unter [Planen von VoIP-Ausfallsicherheit für Zweigstellen in Lync Server 2013](lync-server-2013-planning-for-branch-site-voice-resiliency.md) in der Planungsdokumentation.

  - **DNS-Lastenausgleich.**    Der Front-End-Pool und der Edgeserver-Pool wurden zum DNS-Lastenausgleich für SIP-Datenverkehr konfiguriert. Auf diese Weise sind keine Hardwaregeräte zum Lastenausgleich für die Edgeserver erforderlich, und Setup und Wartung der Hardwaregeräte zum Lastenausgleich für die weiteren Pools werden erheblich vereinfacht, da die Hardwaregeräte zum Lastenausgleich nur für HTTP-Datenverkehr benötigt werden. Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

  - **Exchange UM-Bereitstellung.** Diese Referenztopologie umfasst einen Exchange Unified Messaging (UM)-Server, auf dem nicht Lync Server, sondern Microsoft Exchange Server ausgeführt wird.
    
    Ausführliche Informationen zu Exchange UM finden Sie unter [Planen der Integration von Exchange Unified Messaging in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) und [Integration in gehostete Exchange Unified Messaging-Dienste in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in der Planungsdokumentation.

  - **Office Web Apps Server.** Es wird empfohlen, in jeder Organisation, in der der Webkonferenzdienst verwendet wird, einen Office Web Apps Server oder eine Office Web Apps-Serverfarm bereitzustellen. Der Office Web Apps Server ermöglicht die Präsentation von PowerPoint-Folien in Webkonferenzen. Weitere Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

  - **Empfohlene Verwendung von Edgeservern.**    Wenngleich die Bereitstellung eines Edgeservers nicht erforderlich ist, wird dies für Bereitstellungen jeder Größe empfohlen. Sie können Ihre Investition in Lync Server maximieren, indem Sie einen Edgeserver zur Bereitstellung von Diensten für Benutzer implementieren, die sich aktuell außerhalb der Organisationsfirewall befinden. Es bieten sich folgende Vorteile:
    
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



  - **Directors können hinzugefügt werden.**    Wenn diese Organisation die Sicherheit gegenüber Denial-of-Service-Angriffen erhöhen möchte, kann auch ein Director-Pool bereitgestellt werden. Eine Director ist eine separate, optionale Serverrolle in Lync Server, die keine Benutzerkonten verwaltet und keine Anwesenheits- oder Konferenzdienste zur Verfügung stellt. Sie dient als interner Server für den nächsten Hop, an den ein Edgeserver eingehenden SIP-Verkehr für interne Server weiterleitet. Die Director authentifiziert eingehende Anfragen vor und leitet sie an den Home-Pool oder Server des Benutzers weiter. Die Vorauthentifizierung am Director ermöglicht das Verwerfen von Anfragen von Benutzerkonten, die der Bereitstellung nicht bekannt sind. Eine Director trägt zum Schutz von Front-End-Servern vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen bei. Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr bei der Director.

  - **System Center Operations Manager wird empfohlen.** Es wird empfohlen, den Zustand Ihrer Lync Server-Bereitstellung zu überwachen, um die Verfügbarkeit von Diensten für Endbenutzer sicherzustellen. Sie können Lync mit dem System Center Operations Manager Management Pack für Lync überwachen, das als kostenloser Download bei Microsoft zur Verfügung steht. Mit dem Lync Management Pack können Sie unter anderem bei auftretenden Problemen proaktiv Echtzeitwarnungen empfangen, synthetische Transaktionen zum Testen der Lync-End-to-End-Funktionalität ausführen und Berichte über die Dienstverfügbarkeit erhalten. Dadurch können Sie proaktiv auf Probleme mit Ihrer Bereitstellung reagieren, bevor Endbenutzer davon betroffen sind.

