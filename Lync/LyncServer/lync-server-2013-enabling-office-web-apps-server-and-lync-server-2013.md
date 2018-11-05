---
title: 'Lync Server 2013: Aktivieren von Office Web Apps Server und Lync Server 2013'
TOCTitle: Aktivieren von Office Web Apps Server und Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204792(v=OCS.15)
ms:contentKeyID: 49293620
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Lync Server 2013 wird Office Web Apps-Server zum Behandeln von PowerPoint-Präsentationen eingesetzt. Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Übersicht über Webkonferenzen in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).

Um diese neuen Funktionen nutzen zu können, müssen Administratoren Office Web Apps-Server installieren und Lync Server 2013 für die Kommunikation mit Office Web Apps-Server konfigurieren. Diese Dokumentation enthält Informationen darüber, wie Lync Server 2013 für die Zusammenarbeit mit Office Web Apps-Server konfiguriert werden kann. Die Dokumentation stellt jedoch keine Informationen zur Installation von Office Web Apps-Server bereit. Diese Informationen finden Sie auf der Microsoft-Website zur Bereitstellung von Office Web Apps unter [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x407). Dort finden Sie ausführliche Informationen zu den Voraussetzungen für Office Web Apps-Server. Beachten Sie, dass Office Web Apps-Server auf einem eigenständigen Computer installiert werden sollte, auf dem weder Lync Server, noch Microsoft SQL Server und auch keine andere Serveranwendung ausgeführt werden sollte; auf dem Computer darf keine Version von Microsoft Office installiert sein. Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Gruppe von Software installiert sein (einschließlich .NET Framework 4.5 und Windows PowerShell 3.0). Diese Anforderungen, einschließlich Konfiguration von Zertifikaten und Internetinformationsdienste (Internet Information Services, IIS), werden ausführlich auf der Microsoft-Website für die Bereitstellung von Office Web Apps unter [http://go.microsoft.com/fwlink/?linkid=257525\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=257525%26clcid=0x407) beschrieben.

Dieses Dokument befasst sich mit den folgenden Themenbereichen:

  - [Konfigurieren von Lync Server 2013 für die Verwendung mit Office Web Apps Server](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [Veröffentlichen von Office Web Apps Server in Lync Server 2013 mithilfe eines Reverseproxyservers](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [Überprüfen der Konfiguration von Office Web Apps Server in Lync Server 2013](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [Konfigurieren von Clients von Lync Server 2013 für die Verwendung mit Office Web Apps Server](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

