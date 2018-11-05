---
title: 'Lync Server 2013: Konfigurieren von SQL Server für Lync Server'
TOCTitle: Konfigurieren von SQL Server für Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425848(v=OCS.15)
ms:contentKeyID: 49293673
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von SQL Server für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-08-12_

In den Themen in diesem Abschnitt wird erläutert, wie Sie SQL Server für die Verwendung in einer Unternehmensbereitstellung von Lync Server bereitstellen und konfigurieren können. Für Standard Edition-Server wird eine verbundene SQL Server Express-Version von SQL Server verwendet, die für die Arbeitsauslastungen eines Standard Edition-Servers richtig dimensioniert ist.

Der zentralen Verwaltungsspeicher von Lync Server 2013 enthält Benutzerdaten für alle Enterprise Edition-Server in einem Pool und ist für die Platzierung auf einem SQL Server -basierten Back-End-Server vorgesehen. Als zentrales Repository kann der zentralen Verwaltungsspeicher nicht auf einem Computer installiert werden, auf dem bereits eine andere Lync Server 2013-Rolle installiert ist. Der zentralen Verwaltungsspeicher kann sich nicht auf einem Enterprise Edition-Server im Pool befinden. Der zentralen Verwaltungsspeicher wird automatisch erstellt, wenn Sie die Topologie zum ersten Mal veröffentlichen und die Option zum Erstellen der Datenbanken auswählen. Auf dem Computer, der als Back-End-Server zugewiesen ist, muss bereits die SQL Server-Datenbanksoftware ausgeführt werden, damit die Installation erfolgreich ist.

## In diesem Abschnitt

  - [Platzierung von SQL Server-Daten und Protokolldatei für Lync Server 2013](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [Konfigurieren von SQL Server in Lync Server 2013](lync-server-2013-configure-sql-server.md)

  - [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [Installieren von Datenbanken mithilfe der Lync Server-Verwaltungsshell in Lync Server 2013](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [Grundlegendes zu den Firewallanforderungen für SQL Server mit Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [Konfigurieren von SQL Server-Clustering](lync-server-2013-configure-sql-server-clustering.md)

