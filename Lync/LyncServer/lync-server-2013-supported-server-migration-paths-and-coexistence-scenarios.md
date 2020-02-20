---
title: 'Lync Server 2013: unterstützte Server Migrationspfade und Szenarien für die Koexistenz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server migration paths and coexistence scenarios
ms:assetid: 2a6a730f-7f80-45f9-9540-3edfdaa265fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425764(v=OCS.15)
ms:contentKeyID: 48183686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ace33bad5d00dae398557acb66af6bdf880909b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Unterstützte Server Migrationspfade und Szenarien für die Koexistenz in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-16_

Lync Server 2013 unterstützt die Migration aus einem der folgenden:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

Die Migration einer Umgebung, in der beide dieser vorherigen Versionen ausgeführt werden, wird nicht unterstützt. Migration aus früheren Versionen, wie Microsoft Office Communications Server 2007 oder Live Communications Server 2005, wird nicht unterstützt. Wenn Ihre frühere Bereitstellung Gruppen Chat umfasste, müssen Sie Sie separat migrieren.

<div>

## <a name="migration-methods"></a>Migrationsmethoden

Die Migration aller lync Server Topologien und Server Rollen wird unterstützt. Sie können von einer Topologie zu einer anderen Topologie migrieren, beispielsweise von Standard Edition-Server zu Enterprise Edition-Server.

Lync Server 2013 unterstützt nur die folgende Migrationsmethode:

  - <span></span>  
    **Side-by-Side-Migration.** Bei der parallelen Migration werden lync Server 2013 neben einer vorhandenen Microsoft lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung bereitgestellt, und anschließend werden die Vorgänge auf die neuen Server übertragen und Benutzer zu lync Server 2013. Diese Methode erfordert zusätzliche Serverplattformen, einschließlich Hardware und Software, während der Migration, und Systemnamen und Poolnamen unterscheiden sich in der neuen Konfiguration. Wenn es erforderlich ist, ein Rollback auf die vorherige Version durchführen zu können, können Sie die Vorgänge wieder auf die vorherigen Server verschieben.

Die Migration in Active Directory-Domänendienste Gesamtstrukturen wird nicht unterstützt.

Die empfohlene Migration erfolgt phasenweise. Ausführliche Informationen zur Migration von einer vorherigen Version, einschließlich der geeigneten Phasen für die Komponentenbereitstellung, finden Sie in den folgenden Themen der Migration-Dokumentation:

  - [Migration von Lync Server 2010 zu Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migration von Office Communications Server 2007 R2 zu lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Koexistenzszenarien

Lync Server 2013 können mit Komponenten einer lync Server 2010-Bereitstellung oder einer Office Communications Server 2007 R2-Bereitstellung koexistieren. Die gleichzeitige Bereitstellung von lync Server 2013 mit lync Server 2010 und Office Communications Server 2007 R2 (gleichzeitige Bereitstellung aller drei Versionen) wird nicht unterstützt.

Während einer phasenweisen Migration, bei der eine frühere lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung vorübergehend mit der neuen lync Server 2013-Bereitstellung koexistiert, ist die Unterstützung für das Routing in gemischten Versionen begrenzt. Ausführliche Informationen finden Sie in der Migrationsdokumentation.

Sie müssen separate und unterschiedliche Computer mit Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für Ihre lync Server 2013-Datenbankinstanzen verwenden. Sie können nicht dieselbe Instanz von SQL Server für eine lync Server 2013 Front-End-Pool verwenden, die Sie für eine lync Server 2010 oder Office Communications Server 2007 R2 Front-End-Pool verwenden. Wenn Sie lync Server 2013 im Topologie-Generator für eine Bereitstellung definieren und konfigurieren, die bereits lync Server 2010 oder Office Communications Server 2007 R2 bereitgestellt wurde, können Sie mit dem Topologie-Generator keine Instanz einer lync Server 2013 definieren, die bereits in verwendet wird. die Topologie.

Im Topologie-Generator wird die folgende Meldung angezeigt, um Sie über dieses Problem zu informieren: \["der SQL Server\] -FQDN des Servers enthält bereits eine SQL-Instanz-Host Rolle" Benutzerspeicher ".

<div>


> [!NOTE]  
> Wenn Sie Serverrollen bereitstellen möchten, die für Ihre lync Server 2013-Bereitstellung neu sind, sollten Sie zuerst die vorhandene Bereitstellung wie in der Migrationsdokumentation und in der Bereitstellungsdokumentation beschrieben aktualisieren und dann die neuen Serverrollen wie in beschrieben bereitstellen. die Planungsdokumentation und die Bereitstellungsdokumentation. Wenn Sie eine frühere Version des Gruppenchats migrieren, migrieren Sie Sie zuletzt, nachdem Sie den Prozess für die Migration aller anderen Komponenten von lync Server 2010 oder Office Communications Server 2007 R2 abgeschlossen haben.



</div>

Informationen zu spezifischen Anforderungen an die Koexistenz und andere Details zur Koexistenz und Migration von lync Server 2010-oder Office Communications Server 2007 R2-und lync Server 2013-Komponenten finden Sie unter [Migration from lync Server 2010 to lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) und [Migration from Office Communications Server 2007 R2 to lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in der Migrationsdokumentation. Ausführliche Informationen zur Unterstützung gemischter Versionen für Clients finden Sie unter [Supported Clients from previous Deployments in lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

