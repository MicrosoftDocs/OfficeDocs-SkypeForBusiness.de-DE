---
title: 'Lync Server 2013: Übersicht über die Archivierung'
TOCTitle: Übersicht über die Archivierung
ms:assetid: 1e3c2ef1-f561-4f57-8b6a-7d78addc1ed1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204729(v=OCS.15)
ms:contentKeyID: 49293370
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Archivierung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-09-30_

Die Archivierung in Lync Server 2013 bietet die Möglichkeit, über Lync Server 2013 gesendete Kommunikation zu archivieren.

Sie können die Archivierung im Rahmen der ursprünglichen Lync Server 2013-Bereitstellung implementieren oder zu einer vorhandenen Bereitstellung hinzufügen. Verwenden Sie zur Nutzung der Lync Server 2013-Archivierungsdatenbanken ( SQL Server-Datenbanken) zum Speichern von Archivierungsdaten den Topologie-Generator, um die Datenbanken zu Ihrer Topologie hinzuzufügen, und veröffentlichen Sie dann die Topologie erneut. Wenn alle Benutzer unter Exchange 2013 verwaltet werden und für ihre Postfächer das Compliance-Archiv festgelegt ist, müssen Sie die Topologie nicht aktualisieren, sondern nur die Microsoft Exchange-Integration aktivieren, um archivierte Daten in Exchange 2013 zu speichern.

Bei der Implementierung der Archivierung konfigurieren Sie sie zur Angabe der archivierten Objekte. Standardmäßig wird nichts archiviert. Sie konfigurieren und verwalten die Archivierung mithilfe der Systemsteuerung für Lync Server 2013. Sie können die Archivierung für interne Kommunikation, externe Kommunikation oder beides implementieren. Sie können Archivierungseinstellungen für die gesamte Organisation und optional für bestimmte Standorte, Pools und Benutzer bzw. Benutzergruppen konfigurieren. Ausführliche Informationen zum Ermitteln der geeigneten Optionen für Ihre Organisation finden Sie in der Planungsdokumentation unter [Definieren der Anforderungen Ihrer Organisation für die Archivierung in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md). Ausführliche Informationen zur Implementierung von Archivierungsrichtlinien und -konfigurationen sowie Details dazu, welche Informationen archiviert bzw. nicht archiviert werden können, finden Sie unter [Funktionsweise der Archivierung in Lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungs-, Bereitstellungs- oder Betriebsdokumentation.

