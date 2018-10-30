---
title: Bereitstellen des Monitoring Servers
TOCTitle: Bereitstellen des Monitoring Servers
ms:assetid: 117f4a3e-0670-4388-a553-b9854921145f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398199(v=OCS.15)
ms:contentKeyID: 49293217
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellen des Monitoring Servers

 

_**Letztes Änderungsdatum des Themas:** 2013-12-17_

An der Microsoft Lync Server 2013-Überwachungsstruktur wurden wesentliche Änderungen vorgenommen, beginnend damit, dass die Überwachungsserverrolle veraltet ist. Anstatt separater Überwachungsserverrollen (für die Organisationen in der Regel dedizierte Computer einrichten mussten, die als Überwachungsserver dienten) werden Überwachungsdienste jetzt auf jedem Front-End-Server gemeinsam ausgeführt. Unter anderem sorgt diese Änderung für folgende Vorteile:

  - Geringere Anzahl von erforderlichen Serverrollen beim Implementieren von Lync Server 2013. In diesem Fall kann das Verringern der Überwachungsserverrolle auch Kosten sparen, da keine dedizierten Server für die Überwachung mehr erforderlich sind.

  - Weniger Komplexität beim Setup und der Verwaltung von Lync Server. Da die Überwachungsdienste auf jedem Front-End-Server automatisch gemeinsam ausgeführt werden, müssen Sie die Überwachungsserverrolle nicht mehr installieren, konfigurieren und verwalten.


> [!NOTE]
> Die Archivierungsserverrolle ist in Lync Server 2013 ebenfalls veraltet. Genau wie die Überwachungsdienste werden auch die Lync Server 2013-Archivierungsdienste jetzt auf jedem Front-End-Server gemeinsam ausgeführt. Dies sollte beachtet werden, da Überwachung und Archivierung oft auf derselben SQL Server-Datenbankinstanz ausgeführt werden.



Erwartungsgemäß haben diese Änderungen erhebliche Auswirkungen darauf, wie Überwachungsdienste installiert und verwaltet werden. Da die Überwachungsserverrolle nicht mehr vorhanden ist, wurde der Überwachungsserverknoten aus dem Lync Server-Topologie-Generator entfernt. Dies wiederum bedeutet, dass sie den Assistenten für neue Überwachungsserver des Topologie-Generators nicht mehr verwenden, um Ihrer Topologie einen neuen Überwachungsserver hinzuzufügen. (Dieser Assistent ist nicht mehr vorhanden.) Stattdessen implementieren Sie in der Regel Überwachungsdienste innerhalb Ihrer Topologie, indem Sie folgende zwei Schritte ausführen:

1.  Aktivieren der Überwachung zur selben Zeit, wie Sie einen neuen Lync Server-Pool einrichten. (In Lync Server 2013 ist die Überwachung auf Pool-für-Pool-Basis aktiviert oder deaktiviert.) Sie können die Überwachung für einen Pool aktivieren, ohne tatsächlich Überwachungsdaten zu sammeln. Dieser Prozess wird in den Abschnitten "Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen)" und "QoE (Quality of Experience)-Einstellungen" in dieser Dokumentation erklärt.

2.  Zuordnen eines Überwachungsspeichers (d. h. einer Überwachungsdatenbank) an den neuen Pool. Ein einzelner Überwachungsspeicher kann mehreren Pools zugeordnet werden. Anhängig von der Anzahl von Benutzern, die in Ihren Registrierungsstellenpools verwaltet werden, bedeutet dies, dass Sie keine separate Überwachungsdatenbank für jeden Pool einrichten müssen. Stattdessen können einzelne Überwachungsspeicher von mehreren Pools verwendet werden.

Oft ist es zwar einfacher, die Überwachung gleichzeitig mit der Erstellung eines neuen Pool zu aktivieren, es ist jedoch auch möglich, bei deaktivierter Überwachung einen neuen Pool zu erstellen. In diesem Fall können Sie später den Topologie-Generator verwenden, um den Dienst zu aktivieren. Mithilfe des Topologie-Generators kann die Überwachung für einen Pool aktiviert bzw deaktiviert, oder ein Pool kann einem anderen Überwachungsspeicher zugeordnet werden. Beachten Sie, dass weiterhin mindestens ein Überwachungsspeicher erstellt werden muss, auch wenn keine Überwachungsserverrolle mehr vorhanden ist: Back-End-Datenbanken, die zum Speichern der vom Überwachungsdienst gesammelten Daten dienen. Diese Back-End-Datenbanken können mithilfe von Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 erstellt werden.


> [!NOTE]
> Wenn die Überwachung für einen Pool aktiviert wurde können Sie den Sammlungsprozess von Überwachungsdaten deaktivieren, ohne Ihre Topologie zu ändern, da Lync Server-Verwaltungsshell eine Möglichkeit bietet, die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten zu deaktivieren (und später erneut zu aktivieren). Weitere Informationen finden Sie in diesem Dokument im Abschnitt "Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE (Quality of Experience)-Einstellungen".



Eine weitere bedeutende Verbesserung der Überwachung in Lync Server 2013 besteht darin, dass Lync Server-Überwachungsberichte jetzt IPv6 unterstützen. In Berichten, die das Feld "IP-Adresse" verwenden, werden entweder IPv4- oder IPv6-Adressen angezeigt. Dies hängt von Folgendem ab: 1) von der verwendeten SQL-Abfrage und 2) ob die IPv6-Adresse in der Überwachungsdatenbank gespeichert ist.


> [!NOTE]
> Vergewissern Sie sich, dass der Starttyp des SQL Server-Agent-Diensts „Automatisch“ ist und der SQL Server-Agent-Dienst für die SQL-Instanz mit den Überwachungsdatenbanken ausgeführt wird, damit die SQL Server-Wartungsaufträge für die Standardüberwachung plangemäß unter der Kontrolle des SQL Server-Agent-Diensts ausgeführt werden können.



Diese Dokumentation führt Sie durch Schritte zum Installieren und Konfigurieren der Überwachung und Überwachungsberichte für Lync Server 2013. Die Dokumentation enthält Schritt-für-Schritt-Anleitungen für Folgendes:

  - Aktivieren der Überwachung in Ihrer Topologie und Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool.

  - Installieren von SQL Server Reporting Services und der Lync Server-Überwachungsberichte. Überwachungsberichte sind vorkonfigurierte Berichte, die verschiedene Einsichten in die in einer Überwachungsdatenbank gespeicherten Informationen bieten.

  - Konfigurieren der Aufzeichnung von Kommunikationsdatensätzen (KDS) und der Sammlung von QoE (Quality of Experience)-Daten. Die KDS-Funktion bietet eine Möglichkeit, die Nutzung von Lync Server-Funktionen wie Voice-over-IP-Anrufe (VoIP), Chats, Dateiübertragungen, Audio-/Videokonferenzen (A/V) und Anwendungsfreigabesitzungen nachzuverfolgen. QoE-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter).

  - Manuelles Löschen von KDS und QoE-Datensätzen aus der Überwachungsdatenbank.

