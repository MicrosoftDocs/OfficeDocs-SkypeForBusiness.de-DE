---
title: 'Lync Server 2013: Übersicht über die Bereitstellung'
TOCTitle: Übersicht über die Bereitstellung
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205305(v=OCS.15)
ms:contentKeyID: 49295598
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über die Bereitstellung für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-03-12_

Der Hauptunterschied zwischen Lync Server 2013  Enterprise Edition und Lync Server 2013  Standard Edition besteht darin, dass die Standard Edition die Features für die hohe Verfügbarkeit der Enterprise Edition nicht unterstützt. Für die hohe Verfügbarkeit müssen Sie mehrere Front-End-Server in einem Pool bereitstellen, und anschließend können Sie den Server mit SQL Server spiegeln. Bei der Enterprise Edition können Sie einen Vermittlungsserver gemeinsam ausführen oder ein eigenständigen Server definieren. Der Monitoring-Server und der Archivierungsserver können einen eigenständigen Server mit SQL Server verwenden. Es können aber auch Instanzen von SQL Server auf dem Datenbankserver für die Front-End-Server und Pools ausgeführt werden.

Server mit Lync Server 2013Standard Edition sind für kleinere Organisationen und für Zweigniederlassungen bestimmt, die sich in geografischer Entfernung zur Hauptbereitstellung einer Organisation befinden. Ein Paar aus zwei Standard Edition-Server-Servern, die für Failover im Notfall konfiguriert sind, kann bis zu 5.000 Benutzer unterstützen. Standard Edition-Server können nicht in einem Pool zusammengefasst werden, wie dies bei Front-End-Servern in der Enterprise Edition der Fall ist. Ferner handelt es sich bei der SQL Server-Datenbank, die für die Standard Edition genutzt wird, um einen gemeinsam ausgeführten Server mit SQL Server Express, der für die Arbeitslastung eines Standard Edition-Servers ausgelegt ist. Dies bedeutet nicht, dass alle Rollen auf einem Standard Edition-Server ausgeführt werden müssen. Sie können eigenständige Vermittlungsserver und Edgeserver einsetzen. Die SQL Server-Datenbank für den zentraler Verwaltungsspeicher und für Lync Server 2013 muss sich auf dem Standard Edition-Server befinden, der gemeinsam mit dem Server mit SQL Server ausgeführt wird. Der Monitoring-Server und der Archivierungsserver verwenden einen eigenständigen Server mit der SQL Server-Datenbank.

