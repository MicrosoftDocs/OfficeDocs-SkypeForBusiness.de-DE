---
title: Einrichten von Systemplattformen für die Archivierung
TOCTitle: Einrichten von Systemplattformen für die Archivierung
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204768(v=OCS.15)
ms:contentKeyID: 49293538
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Einrichten von Systemplattformen für die Archivierung

 

_**Letztes Änderungsdatum des Themas:** 2012-10-09_

Bevor Sie mit der Archivierungsbereitstellung beginnen, müssen Sie das erforderliche Betriebssystem und andere erforderliche Software auf Hardware installieren, die den Systemanforderungen entspricht:

  - **Lync Server 2013-Plattform**   Lync Server 2013-Bereitstellungen verfügen nicht über Archivierungsserver. Stattdessen werden auf Front-End-Servern und Standard Edition-Servern UDC-Agents (Unified Data Collection) ausgeführt, um die zu archivierenden Daten zu erfassen. Es ist also keine separate Systemplattform zum Hosten der Archivierung erforderlich.

  - **Datenspeicherplattform**   In Lync Server 2013 können Daten mit einer der folgenden Methoden gespeichert werden:
    
      - **Microsoft Exchange-Integration**   Wenn Sie die Lync Server 2013-Archivierungsdaten mithilfe der Exchange 2013-Bereitstellung speichern möchten, anstelle oder zusätzlich zur Einrichtung einer separaten Datenbank zum Speichern von Archivierungsdaten, muss in Ihrer Exchange-Bereitstellung Exchange 2013 ausgeführt werden. Detaillierte Informationen zum Einrichten von Systemplattformen für Exchange 2013 finden Sie in der Exchange-Produktdokumentation.
    
      - **SQL Server**   Wenn Sie eine separate SQL Server-Datenbank zum Speichern von Archivierungsdaten verwenden möchten, anstelle oder zusätzlich zur Verwendung der Microsoft Exchange-Integration, müssen Sie die Systemplattform für die Datenbank vor der Archivierungsbereitstellung einrichten. Die spezifischen Systemplattformanforderungen hängen davon ab, ob Sie Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für die Archivierungsdatenbank verwenden. Ausführliche Informationen zum Einrichten von Systemplattformen für diese Datenbanken finden Sie in der Produktdokumentation zu Microsoft SQL Server 2008 R2 und Microsoft SQL Server 2012.

  - **Dateiserverplattform**   In Lync Server 2013 werden Lync Server-Archivierungsdateien an demselben Speicherort gespeichert, den Sie beim Einrichten der Front-End-Server oder Standard Edition-Server für die Dateispeicherung angeben. Sie können keinen separaten Speicherort für die Speicherung von Archivierungsdateien angeben, sodass keine separate Systemplattform zur Speicherung von Archivierungsdateien erforderlich ist. Wenn Sie die Microsoft Exchange-Integration verwenden, werden die Exchange 2013-Dateien für die archivierten Lync-Kommunikationen für Benutzer, die auf Exchange-Servern verwaltet werden, auf Exchange 2013-Servern gespeichert.

