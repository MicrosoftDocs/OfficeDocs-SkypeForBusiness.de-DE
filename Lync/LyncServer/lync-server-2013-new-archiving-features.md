---
title: 'Lync Server 2013: Neue Funktionen für die Archivierung'
TOCTitle: Neue Funktionen für die Archivierung
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205225(v=OCS.15)
ms:contentKeyID: 49295283
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Funktionen für die Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Bei der Archivierung in Lync Server 2013 können die folgenden Arten von Inhalten archiviert werden:

  - Peer-zu-Peer-Chatnachrichten

  - Konferenzen (Besprechungen), bei denen es sich um Chatnachrichten mit mehreren Teilnehmern handelt

  - Konferenzinhalte, einschließlich hochgeladener Inhalte (z. B. Handzettel) sowie ereignisbezogener Inhalte (z. B. Beitritt zu/Verlassen einer Konferenz, Hochladen/Freigeben von Inhalten oder Änderungen in der Sichtbarkeit)

Darüber hinaus bietet die Archivierung in Lync Server 2013 die folgenden neuen Features, mit denen die Bereitstellungs- und Betriebseffizienz verbessert wird:

  - **Kollokation der Archivierung auf Front-End-Servern.**    Lync Server 2013 weist keine separate Archivierungsserverrolle auf. Die Archivierung ist ein optionales Feature, das auf allen Front-End-Servern in einer Enterprise Edition-Bereitstellung, und auf Standard Edition-Servern, die für einen Pool oder einen Standort implementiert und konfiguriert werden können, verfügbar ist.

  - **Microsoft Exchange-Integration.**   Beim Bereitstellen der Archivierung können Sie die bestehende Exchange 2013-Speicherung in die Datenspeicherung für die Archivierung für alle Benutzer integrieren, die in Exchange 2013 verwaltet werden und deren Postfächer auf "Compliance-Archiv" festgelegt sind, damit Sie keine separaten SQL Server-Datenbanken zum Archivieren von Lync-Daten bereitstellen müssen. Wenn Sie nicht über eine Exchange 2013-Bereitstellung verfügen, wenn Sie diese Integration nicht wünschen, oder wenn Sie über Lync 2013-Benutzer verfügen, die nicht in Exchange 2013 mit Postfächern verwaltet werden, für die "Compliance-Archiv" festgelegt ist, können Sie separate Archivierungsdatenbanken bereitstellen, indem Sie mithilfe von SQL Server archivierte Daten aus Lync-Kommunikationen speichern. Sie können sowohl die Microsoft Exchange-Integration als auch Lync Server 2013-Archivierungsdatenbanken verwenden, wenn Sie die Microsoft Exchange-Integration nur für einige Benutzer in Ihrer Bereitstellung nutzen möchten. Ausführliche Informationen zur Compliance-Archiv-Option finden Sie im Abschnitt "Compliance-Archiv" unter [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).

  - **SQL-Speicherspiegelung.**   Wenn Sie die Archivierung bereitstellen, können Sie die SQL Server-Datenbankspiegelung für Ihre Archivierungsdatenbank aktivieren.

  - **Archivierung von Whiteboards und Abstimmungen.**   Zu den archivierten Konferenzinhalten zählen nun auch Whiteboards und Abstimmungen, die während der Besprechung gemeinsam genutzt werden.

Die folgenden Arten von Inhalt können nicht archiviert werden:

  - Peer-to-Peer-Dateiübertragungen

  - Audio-/Videoinhalte für Peer-zu-Peer-Chatnachrichten und -konferenzen

  - Anwendungsfreigabe für Peer-zu-Peer-Chatnachrichten und Konferenzen

## Siehe auch

#### Weitere Ressourcen

[Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md)

