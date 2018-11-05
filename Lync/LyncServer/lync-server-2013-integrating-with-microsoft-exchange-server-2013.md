---
title: 'Lync Server 2013: Integrieren in Microsoft Exchange Server 2013'
TOCTitle: Integrieren von Lync Server 2013 und Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49890800
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Integrieren von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Zwischen Exchange und Lync Server besteht seit langem eine enge Integration und Kompatibilität. Diese Integration zeigt sich besonders deutlich in den entsprechenden Clientanwendungen. So können beispielsweise die Lync-Anwesenheitsinformationen in Berichten in Microsoft Outlook verwenden werden. Andererseits kann Lync den Outlook-Kalender verwenden, um die Anwesenheitsinformationen automatisch zu aktualisieren. (So kann Ihr Status von Lync beispielsweise in den Status ”Beschäftigt” geändert werden, wenn in Ihrem Kalender eine geplante Besprechung verzeichnet ist.) Obwohl es nicht erforderlich ist, Exchange auszuführen, um Lync Server verwenden zu können (oder umgekehrt), besteht kaum Zweifel daran, dass eine gemeinsame Verwendung dieser Produkte per Definition eine ideale Lösung darstellt.

Dies gilt insbesondere für die Versionen Microsoft Lync Server 2013 und Microsoft Exchange Server 2013. Neben Funktionen wie Unified Messaging, Sofortnachrichten und Anwesenheitsinformationen, die in Microsoft Exchange Server 2010 und Microsoft Lync Server 2010 verfügbar sind, umfassen die 2013er-Versionen der Serverprodukte zahlreiche neue Funktionalitäten. Dazu zählen beispielsweise folgende:

  - **Lync-Archivierungsintegration**. In Lync Server 2013 haben Administratoren weiterhin die Option, Aufzeichnungen von Chatsitzungen und Webkonferenzen in SQL Server zu archivieren (auf dieselbe Weise, in der diese Aufzeichnungen in Lync Server 2010 archiviert wurden). Alternativ können Administratoren diese Aufzeichnungen auch unter Exchange 2013 archivieren. Dabei werden die Aufzeichnungen in den Postfächern der einzelnen Benutzer gespeichert. Dies erfolgt auf dieselbe Weise wie die Archivierung von Kommunikation in Exchange. Das bedeutet, es wird ein einzelnes Repository für Ihre gesamte elektronische Kommunikation (von Exchange und Lync Server) verwendet. Dies stellt – soweit erforderlich – eine deutliche Vereinfachung beim Suchen und Abrufen dieser archivierten Kommunikation dar.

  - **Einheitlicher Kontaktspeicher**. In Lync Server 2010 mussten die Benutzer in Outlook und Lync separate Kontaktlisten pflegen. Um also sicherzustellen, dass Sie in beiden Produkten über dieselben Kontakte verfügen, mussten Sie doppelte Kontaktlisten verwalten – eine für Outlook und eine für Lync. In Lync Server 2013 können die Benutzerkontakte nun in Exchange 2013 und im einheitlichen Kontaktspeicher gespeichert werden. Durch die Nutzung eines zentralen Kontaktspeichers müssen die Benutzer die Kontakte jeweils nur einmal verwalten und haben aber in Lync 2013, Outlook 2013 und Outlook Web Access 2013 Zugriff auf dieselben Kontakte.

  - **Lync-Besprechungsplanung von OWA** . Mit der Integration von Lync Server 2013 und Exchange 2013 können Benutzer Lync-Besprechungen von Outlook Web Access 2013 planen.

  - **Fotos mit hoher Auflösung** . In Lync 2010 konnten nur kleine Fotos von Ihren Kontakten angezeigt werden. Der Grund hierfür war die Speicherung der Fotos in Active Directory. In Active Directory besteht eine Größenbeschränkung für die gespeicherten Fotos von 48 X 48 Pixel. In Lync Server 2013 können die Fotos nun in Microsoft Exchange gespeichert werden. Dadurch können Fotos mit hoher Auflösung mit einer Größe von bis zu 648 x 648 Pixel verwendet werden. Wie zu erwarten, wurde Lync 2013 dahingehend aktualisiert, dass eine Anzeige dieser hochaufgelösten Bilder möglich ist.

Beachten Sie, dass für diese neuen Funktionen die Verwendung von beiden Anwendungen, Lync Server 2013 und Exchange 2013, erforderlich ist. Darüber hinaus benötigen Benutzer, die das vollständige Leistungsspektrum dieser Funktionen nutzen möchten, Konten für Lync Server 2013 und Exchange 2013 und müssen die jeweils aktuelle Version der Clientsoftware (z. B. Lync 2013) ausführen. So ist beispielsweise der einheitliche Kontaktspeicher nicht verfügbar für Benutzer, die unter Lync Server 2010 verwaltet werden; es können auch keine Fotos mit hoher Auflösung unter Lync 2010 angezeigt werden.

In dieser Dokumentation finden Sie Informationen zur Integration von Lync Server 2013 und Exchange 2013, einschließlich einer schrittweisen Anleitung zur Aktivierung der neuen Funktionen wie der Archivierungsintegration und des einheitlichen Kontaktspeichers. Nicht behandelt wird in dieser Dokumentation die Erstkonfiguration dieser beiden Produkte. Detaillierte Informationen zur Bereitstellung von Lync Server 2013 finden Sie im Lync Server 2013-Tech-Center unter [http://go.microsoft.com/fwlink/?linkid=246127\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=246127%26clcid=0x407). Detaillierte Informationen zur Bereitstellung von Exchange 2013 finden Sie im Exchange 2013-Tech-Center unter [http://go.microsoft.com/fwlink/?linkid=268528\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=268528%26clcid=0x407).

## In diesem Abschnitt

[Voraussetzungen für die Integration von Microsoft Lync Server 2013 und Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Konfigurieren von Partneranwendungen in Microsoft Lync Server 2013 und Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Konfigurieren von Microsoft Lync Server 2013 für die Verwendung der Microsoft Exchange Server 2013-Archivierung](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Konfigurieren von Microsoft SharePoint Server 2013 zum Suchen nach archivierten Microsoft Lync Server 2013-Daten](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Konfigurieren von Microsoft Lync Server 2013 zur Verwendung des einheitlichen Kontaktspeichers](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Konfigurieren der Verwendung von hoch auflösenden Fotos in Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Konfigurieren von Microsoft Exchange Server 2013 Unified Messaging für Microsoft Lync Server 2013-Voicemail](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integrieren von Microsoft Lync Server 2013 und Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

