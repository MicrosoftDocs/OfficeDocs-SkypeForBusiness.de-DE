---
title: 'Lync Server 2013: Komponenten und Topologien für die Überwachung'
TOCTitle: Komponenten und Topologien für die Überwachung
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412952(v=OCS.15)
ms:contentKeyID: 49890927
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für die Überwachung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Die einheitlichen Datensammlungs-Agents werden automatisch auf jedem Front-End-Server installiert und aktiviert. Deshalb müssen Sie keinen Server als Monitoring Server konfigurieren. Jeder Front-End-Server agiert bereits als Monitoring Server. Sie müssen jedoch eine Datenbank installieren und konfigurieren, die als Back-End-Datenspeicher für Ihre Überwachungsdaten dient. Microsoft Lync Server 2013 kann die folgenden Datenbanken als Back-End-Speicher für die Überwachung verwenden:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Beachten Sie, dass Sie die 64-Bit-Versionen dieser Datenbanken verwenden müssen; 32-Bit-Versionen von SQL Server können nicht als Back-End-Speicher für die Überwachung verwendet werden. Entsprechend unterstützt Lync Server 2013 die Express Edition von SQL Server 2008 oder SQL Server 2012. Weitere Informationen zu den Datenbankanforderungen für Lync Server 2013 finden Sie unter [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md) in der Lync Server 2013-Unterstützungsdokumentation.

Denken Sie daran, dass SQL Server installiert und konfiguriert werden muss, bevor Sie den Monitoring Server bereitstellen und konfigurieren. Sie müssen jedoch nur SQL Server selbst bereitstellen. Die Überwachungsdatenbanken müssen Sie nicht vorab einrichten. Diese Datenbanken werden automatisch für Sie erstellt, wenn Sie Ihre Lync Server-Topologie veröffentlichen.

Überwachungsdaten können eine SQL Server-Instanz gemeinsam mit anderen Datentypen verwenden. In der Regel verwenden die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen ( LcsCdr ) und die Quality of Experience-Datenbank ( QoEMetrics ) dieselbe SQL-Instanz. Häufig sind die beiden Überwachungsdatenbanken auch in derselben SQL-Instanz wie die Archivierungsdatenbank ( LcsLog ) vorhanden. Die einzige echte Anforderung für SQL Server-Instanzen besteht darin, dass jede Instanz von SQL Server auf Folgendes beschränkt ist:

  - Eine Instanz der Lync Server 2013-Back-End-Datenbank. (Im Allgemeinen wird davon abgeraten, die Überwachungsdatenbank in derselben SQL-Instanz, oder sogar auf demselben Computer, wie die Back-End-Datenbank zu verwenden. Dies ist zwar technisch möglich, aber es besteht das Risiko, dass die Überwachungsdatenbank Speicherplatz belegt, der für die Back-End-Datenbank benötigt wird.)

  - Eine Instanz der Datenbank für die Aufzeichnung von Kommunikationsdatensätzen.

  - Eine Instanz der Quality of Experience-Datenbank.

  - Eine Instanz der Archivierungsdatenbank.

Das heißt, zwei Instanzen der LcsCdr -Datenbank sind in derselben SQL Server-Instanz nicht zulässig. Falls Sie mehrere Instanzen der LcsCdr -Datenbank benötigen, müssen Sie mehrere SQL Server-Instanzen konfigurieren.

## Siehe auch

#### Weitere Ressourcen

[Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md)

