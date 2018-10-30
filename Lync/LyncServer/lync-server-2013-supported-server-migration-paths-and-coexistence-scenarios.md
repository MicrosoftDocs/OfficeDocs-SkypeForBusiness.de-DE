---
title: 'Lync Server 2013: Unterstützte Servermigrationspfade und Koexistenzszenarien'
TOCTitle: Unterstützte Servermigrationspfade und Koexistenzszenarien
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425764(v=OCS.15)
ms:contentKeyID: 49293507
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Unterstützte Servermigrationspfade und Koexistenzszenarien in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Lync Server 2013 unterstützt die Migration von einer der folgenden Versionen:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

Die Migration einer Umgebung, in der beide dieser vorherigen Versionen ausgeführt werden, wird nicht unterstützt. Die Migration von früheren Versionen, z. B. Microsoft Office Communications Server 2007 oder Live Communications Server 2005, wird nicht unterstützt. Wenn Ihre vorherige Bereitstellung den Gruppenchat beinhaltete, müssen Sie diesen separat migrieren.

## Migrationsmethoden

Die Migration aller Lync Server-Topologien und -Serverrollen wird unterstützt. Sie können von einer Topologie zu einer anderen Topologie migrieren, beispielsweise von Standard Edition-Server zu Enterprise Edition-Server.

Lync Server 2013 unterstützt nur die folgende Migrationsmethode:

  - **Parallele Migration.** Bei der parallelen Migration wird Lync Server 2013 neben einer vorhandenen Microsoft Lync Server 2010- oder Office Communications Server 2007 R2-Bereitstellung bereitgestellt. Anschließend übertragen Sie die Vorgänge auf die neuen Server und verschieben Benutzer in Lync Server 2013. Für diese Methode sind zusätzliche Serverplattformen, einschließlich Hardware und Software, während der Migration erforderlich, und die System- und Poolnamen lauten in der neuen Konfiguration anders. Wenn Sie die vorherige Version wiederherstellen müssen, können Sie die Vorgänge auf die vorherigen Server zurück übertragen.

Die Migration über Active Directory-Domänendienste-Gesamtstrukturen hinweg wird nicht unterstützt.

Die empfohlene Migration erfolgt phasenweise. Ausführliche Informationen zur Migration von einer vorherigen Version, einschließlich der geeigneten Phasen für die Komponentenbereitstellung, finden Sie in den folgenden Themen der Migration-Dokumentation:

  - [Migration von Lync Server 2010 zu Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

## Koexistenzszenarien

Lync Server 2013 kann zusammen mit Komponenten aus entweder einer Lync Server 2010-Bereitstellung oder einer Office Communications Server 2007 R2-Bereitstellung verwendet werden. Die gleichzeitige Bereitstellung von Lync Server 2013 mit sowohl Lync Server 2010 als auch Office Communications Server 2007 R2 (gleichzeitige Bereitstellung aller drei Versionen) wird nicht unterstützt.

Während einer phasenweisen Migration, bei der eine vorherige Lync Server 2013- oder Office Communications Server 2007 R2-Bereitstellung vorübergehend neben der neuen Lync Server 2010-Bereitstellung verwendet wird, ist die Unterstützung für das Routen zwischen verschiedenen Versionen begrenzt. Ausführliche Informationen finden Sie in der Migrationsdokumentation.

Sie müssen separate und verschiedene Computer, auf denen Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 aufgeführt wird, für Ihre Lync Server 2013-Datenbankinstanzen verwenden. Sie können für einen Lync Server 2013-Front-End-Pool nicht dieselbe SQL Server-Instanz verwenden, die Sie auch für einen Lync Server 2010- oder Office Communications Server 2007 R2-Front-End-Pool einsetzen. Wenn Sie Lync Server 2013 im Topologie-Generator für eine Bereitstellung definieren und konfigurieren, für die bereits Lync Server 2010 oder Office Communications Server 2007 R2 bereitgestellt ist, können Sie im Topologie-Generator keine Instanz von Lync Server 2013 definieren, die bereits in der Topologie verwendet wird.

In Topologie-Generator wird die folgende Meldung angezeigt, um Sie über dieses Problem zu informieren: "SQL-Server \[FQDN des Servers\] enthält bereits eine Hostingrolle "Benutzerspeicher" für SQL-Instanzen."


> [!NOTE]
> Wenn Sie Serverrollen bereitstellen möchten, die in Ihrer Lync Server 2013-Bereitstellung neu eingeführt wurden, empfiehlt es sich, zuerst für die vorhandene Bereitstellung gemäß der Migrationsdokumentation und der Bereitstellungsdokumentation ein Upgrade durchzuführen und anschließend die neuen Serverrollen den Beschreibungen in der Planungsdokumentation und in der Bereitstellungsdokumentation entsprechend bereitzustellen. Wenn Sie eine vorherige Gruppenchatversion migrieren, migrieren Sie diese zuletzt, nachdem Sie den Prozess zum Migrieren aller anderen Komponenten von Lync Server 2010 oder Office Communications Server 2007 R2 abgeschlossen haben.



Spezifische Koexistenzanforderungen und weitere Einzelheiten zur Koexistenz und Migration von Lync Server 2010 oder Office Communications Server 2007 R2- und Lync Server 2013-Komponenten finden Sie unter [Migration von Lync Server 2010 zu Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) und [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in der Migrationsdokumentation. Detaillierte Informationen zur Unterstützung von gemischten Versionen für Clients finden Sie unter [Unterstützte Clients aus vorherigen Bereitstellungen in Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

