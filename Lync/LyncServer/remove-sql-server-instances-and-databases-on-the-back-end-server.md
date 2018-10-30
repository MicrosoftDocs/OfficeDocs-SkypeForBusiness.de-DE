---
title: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
TOCTitle: Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49890697
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen von SQL Server-Instanzen und -Datenbanken auf dem Back-End-Server

 

_**Letztes Änderungsdatum des Themas:** 2012-10-19_

Sie entfernen die Microsoft SQL Server-Datenbanken und -Instanzen nach dem Entfernen der Server mit Lync Server 2010, die von ihnen abhängig sind, oder nach dem Neukonfigurieren der Server mit Lync Server 2010, sodass eine andere Datenbank verwendet wird. Sie müssen das Verfahren in diesem Thema ausführen, wenn Sie den aktuellen SQL Server zurückziehen oder den aktuellen Server mit Lync Server 2010 so neu konfigurieren, dass die Datenbanken als veraltet oder nicht mehr verfügbar zurückgegeben werden.

Zum Entfernen der Datenbanken oder der Instanz für den Archivierungsserver oder Monitoring-Server müssen Sie zunächst die Serverrolle entfernen. Entsprechend müssen Sie zum Entfernen der Instanzen oder Datenbanken für den Front-End-Pool zunächst den abhängigen Server entfernen oder neu konfigurieren. Bei diesen Verfahren wird nicht zwischen oder verbundenen Datenbanken oder getrennten Instanzen für Server unterschieden. Die Kollokation von Datenbanken wirkt sich nicht auf die Verfahren aus.

## In diesem Abschnitt

  - [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [Entfernen der SQL Server-Datenbank für einen Monitoring Server](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [Entfernen der SQL Server-Datenbank für einen Archivierungsserver](remove-the-sql-server-database-for-an-archiving-server.md)

