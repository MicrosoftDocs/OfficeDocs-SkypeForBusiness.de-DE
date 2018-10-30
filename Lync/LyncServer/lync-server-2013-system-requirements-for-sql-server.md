---
title: 'Lync Server 2013: Systemanforderungen für SQL Server'
TOCTitle: Systemanforderungen für SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205112(v=OCS.15)
ms:contentKeyID: 49294884
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Systemanforderungen für SQL Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-25_

Installieren Sie vor der Bereitstellung des Enterprise Edition-Servers Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 auf einem dedizierten Computer, der die geltenden Hardwareanforderungen erfüllt. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Unterstützte Datenbanksoftware in Lync Server 2013](lync-server-2013-database-software-support.md) in der Unterstützungsdokumentation. Informationen zu den erforderlichen Berechtigungen für die Bereitstellung finden Sie unter [Bereitstellungsberechtigungen für SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).

Bevor Sie einen Front-End-Pool erstellen, müssen Sie außerdem die Windows-Firewall so konfigurieren, dass Lync Server 2013 berechtigt ist, über bestimmte Ports auf SQL Server zuzugreifen. Verwenden Sie zur Definition der Serverports den SQL Server-Konfigurations-Manager, und öffnen Sie mithilfe der Einstellungen für die erweiterte Sicherheit Ports in der Windows-Firewall.

