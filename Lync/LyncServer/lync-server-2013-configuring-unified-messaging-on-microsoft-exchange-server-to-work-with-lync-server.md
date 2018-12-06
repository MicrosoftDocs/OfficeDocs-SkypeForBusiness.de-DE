---
title: 'Lync Server 2013: Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013'
TOCTitle: Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013
ms:assetid: 058da9c4-23af-4ddb-9f63-70133a8aafc6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398106(v=OCS.15)
ms:contentKeyID: 49293047
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Unified Messaging auf Microsoft Exchange Server für die Zusammenarbeit mit Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_


> [!IMPORTANT]
> Wenn Sie Exchange Unified Messaging (UM) zur Bereitstellung von Anrufbeantwortung, Outlook Voice Access oder automatischen Telefonzentralendiensten für Enterprise-VoIP-Benutzer verwenden möchten, lesen Sie die Informationen in der Planungsdokumentation unter <A href="lync-server-2013-planning-for-exchange-unified-messaging-integration.md">Planen der Integration von Exchange Unified Messaging in Lync Server 2013</A>, und folgen Sie den Anweisungen in diesem Abschnitt.



Führen Sie zum Konfigurieren von Exchange Unified Messaging (UM) zur Verwendung mit Enterprise-VoIP die folgenden Aufgaben aus:

  - Konfigurieren der Zertifikate auf dem Server mit Exchange Unified Messaging (UM)-Diensten
    

    > [!NOTE]
    > Fügen Sie alle Clientzugriffs- und Postfachserver zu allen UM-SIP-URI-Wählplänen hinzu. Andernfalls funktioniert das Routen ausgehender Anrufe nicht wie erwartet.



  - Erstellen von mindestens einem UM-SIP-URI-Wählplan gemeinsam mit den Telefonnummern für den Teilnehmerzugriff (nach Bedarf) und anschließendes Erstellen von entsprechenden Lync Server-Wählplänen.

  - Verwenden des Skripts **exchucutil.ps1** für folgende Aufgaben:
    
      - Erstellen von UM-IP-Gateways
    
      - Erstellen von UM-Sammelanschlüssen
    
      - Gewähren von Lync Server 2013-Berechtigungen zum Lesen von UM-Objekten in Active Directory-Domänendienste

  - Erstellen eines UM-Telefonzentralenobjekts

  - Erstellen eines Objekts für den Teilnehmerzugriff

  - Erstellen eines SIP-URIs für jeden Benutzer und Zuordnen von Benutzern zu einem UM-SIP-URI-Wählplan

## Anforderungen und Empfehlungen

In diesem Abschnitt wird vorausgesetzt, dass Sie die folgenden Exchange 2013-Rollen bereitgestellt haben: Clientzugriff und Postfach. Unter Microsoft Exchange Server 2013 wird Exchange UM als Dienst auf diesen Servern ausgeführt.

Ausführliche Informationen zum Bereitstellen von Exchange 2013 finden Sie in der Exchange 2013 TechNet-Bibliothek unter [http://go.microsoft.com/fwlink/p/?LinkId=266637](http://go.microsoft.com/fwlink/p/?linkid=266637)

Beachten Sie auch Folgendes:

  - Wird Exchange UM in mehreren Gesamtstrukturen installiert, müssen die Schritte für die Exchange Server-Integration für jede UM-Gesamtstruktur ausgeführt werden. Außerdem muss jede UM-Gesamtstruktur so konfiguriert sein, dass sie der Gesamtstruktur vertraut, in der Lync Server 2013 bereitgestellt wurde. Die Gesamtstruktur, in der Lync Server 2013 bereitgestellt wurde, muss wiederum so konfiguriert sein, dass sie den einzelnen UM-Gesamtstrukturen vertraut.

  - Die Integrationsschritte werden sowohl für die Exchange Server-Rollen, unter denen Unified Messaging-Dienste ausgeführt werden, als auch auf dem Server mit Lync Server 2013 ausgeführt. Es empfiehlt sich, die Exchange Server Unified Messaging-Integrationsschritte vor den Integrationsschritten für Lync Server 2013 auszuführen.
    

    > [!NOTE]
    > Informationen dazu, welche Integrationsschritte auf welchen Servern und von welchen Administratorrollen durchgeführt werden müssen, finden Sie unter <A href="lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md">Bereitstellungsprozess für die Integration von lokalen Unified Messaging-Diensten und Lync Server 2013</A>.



Auf jedem Server mit Exchange UM müssen die folgenden Tools verfügbar sein:

  - Exchange-Verwaltungsshell

  - Das Skript **exchucutil.ps1**, mit dem die folgenden Aufgaben ausgeführt werden:
    
      - Erstellen eines UM-IP-Gateways für jeden Lync Server 2013.
    
      - Erstellen eines Sammelanschlusses für jedes Gateway. Die Pilot-ID jedes Sammelanschlusses gibt die UM-SIP-URI-Wähleinstellungen an, die von dem Front-End-Pool oder Standard Edition-Server verwendet werden, der diesem Gateway zugeordnet ist.
    
      - Gewähren von Lync Server 2013-Berechtigungen zum Lesen von Exchange UM-Objekten in Active Directory-Domänendienste.

## In diesem Abschnitt

  - [Konfigurieren von Zertifikaten auf dem Server, auf dem Microsoft Exchange Server Unified Messaging ausgeführt wird](lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md)

  - [Konfigurieren von Unified Messaging auf Microsoft Exchange](lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md)

