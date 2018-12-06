---
title: Konfigurieren von Lync Server zur Verwendung mit System Center Operations Manager
TOCTitle: Konfigurieren von Lync Server zur Verwendung mit System Center Operations Manager
ms:assetid: b55a24ab-648b-4142-b3cd-3792860ba872
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205188(v=OCS.15)
ms:contentKeyID: 49295155
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Lync Server zur Verwendung mit System Center Operations Manager

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Für die Konfiguration Ihrer Microsoft Lync Server 2013-Infrastruktur, damit diese zusammen mit System Center Operations Manager ausgeführt werden kann, müssen Sie drei Dinge vornehmen:

  - Identifizieren und Konfigurieren Sie Ihren primären System Center Operations Manager-Verwaltungsserver. Das Konfigurieren des Verwaltungsservers beinhaltet das Installieren von System Center Operations Manager 2012 oder System Center Operations Manager 2007 R2 sowie das Einrichten einer Back-End-Datenbank mithilfe von SQL Server. Die tatsächliche erforderliche Version von SQL Server ist von der von Ihnen verwendeten System Center Operations Manager-Version abhängig. Details finden Sie unter [Konfigurieren des primären Verwaltungsservers](lync-server-2013-configuring-the-primary-management-server.md).

  - Identifizieren und Konfigurieren Sie die Computer mit Lync Server, die Sie überwachen möchten. Zum Überwachen eines Computers mit Lync Server mithilfe von System Center Operations Manager müssen Sie die Agentdateien von System Center Operations Manager installieren und jeden Server so konfigurieren, dass er als Proxy fungiert.

  - Identifizieren und Konfigurieren Sie die Computer, die als Lync Server-*Watcher-Knoten* fungieren sollen. Watcher-Knoten sind Computer, die periodisch synthetische Transaktionen für Lync Server ausführen. Hierbei handelt es sich um Windows PowerShell-Cmdlets, die sicherstellen, dass wichtige Lync Server-Komponenten (beispielsweise die Fähigkeit, sich am System anzumelden oder Sofortnachrichten auszutauschen) wie erwartet funktionieren.

Die Themen in diesem Abschnitt enthalten Anweisungen zum Ausführen aller dieser Aufgaben

## In diesem Abschnitt

  - [Konfigurieren des primären Verwaltungsservers](lync-server-2013-configuring-the-primary-management-server.md)

  - [Installieren der Lync Server 2013 Management Packs](lync-server-2013-installing-the-lync-server-2013-management-packs.md)

  - [Konfigurieren der zu überwachenden Lync Server-Computer](lync-server-2013-configuring-the-lync-server-computers-that-will-be-monitored.md)

  - [Installieren und Konfigurieren von Watcher-Knoten](lync-server-2013-installing-and-configuring-watcher-nodes.md)

