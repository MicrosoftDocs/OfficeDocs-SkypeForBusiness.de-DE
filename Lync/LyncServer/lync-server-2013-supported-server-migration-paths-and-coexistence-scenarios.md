---
title: 'Lync Server 2013: Unterstützte Servermigrationspfade und Koexistenzszenarien'
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
ms.openlocfilehash: 1b16b0c92954c004aa04b9cc665786badb9bf632
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-migration-paths-and-coexistence-scenarios-in-lync-server-2013"></a>Unterstützte Servermigrationspfade und Koexistenzszenarien in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-16_

Lync Server 2013 unterstützt die Migration von einer der folgenden:

  - Microsoft Lync Server 2010

  - Microsoft Office Communications Server 2007 R2

Die Migration aus einer Umgebung, auf der diese beiden vorherigen Versionen ausgeführt werden, wird nicht unterstützt. Die Migration aus früheren Versionen, wie etwa Microsoft Office Communications Server 2007 oder Live Communications Server 2005, wird nicht unterstützt. Wenn Ihre vorherige Bereitstellung Gruppen-Chats enthielt, müssen Sie Sie separat migrieren.

<div>

## <a name="migration-methods"></a>Migrationsmethoden

Die Migration aller lync Server-Topologien und Serverrollen wird unterstützt. Sie können von einer Topologie zu einer anderen Topologie migrieren, einschließlich vom Standard Edition-Server zu Enterprise Edition-Server.

Lync Server 2013 unterstützt nur die folgende Migrationsmethode:

  - <span></span>  
    **Parallele Migration.** Bei der parallelen Migration wird lync Server 2013 zusammen mit einer vorhandenen Microsoft lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung bereitgestellt, und Sie können dann Vorgänge auf die neuen Server übertragen und Benutzer zu lync Server 2013 verschieben. Diese Methode erfordert zusätzliche Serverplattformen, einschließlich Hardware und Software, während der Migration, und Systemnamen und Poolnamen unterscheiden sich in der neuen Konfiguration. Wenn ein Rollback zur vorherigen Version erforderlich ist, können Sie die Vorgänge zurück auf die vorherigen Server verschieben.

Die Migration in den Active Directory-Domänendienst Gesamtstrukturen wird nicht unterstützt.

Der empfohlene Migrationspfad ist ein Phasenbasierter Ansatz. Details zur Migration von einer früheren Version, einschließlich der entsprechenden Phasen der Komponentenbereitstellung, finden Sie in den folgenden Themen in der Migrationsdokumentation:

  - [Migration von Lync Server 2010 zu Lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md)

  - [Migration von Office Communications Server 2007 R2 zu Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md)

  - [Migration von Lync Server 2010-Gruppenchat oder Office Communications Server 2007 R2-Gruppenchat zu Lync Server 2013 Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md)

</div>

<span id="BKMK_PhasedMigration"></span>

<div>

## <a name="coexistence-scenarios"></a>Koexistenz-Szenarien

Lync Server 2013 kann mit Komponenten einer lync Server 2010-Bereitstellung oder einer Office Communications Server 2007 R2-Bereitstellung koexistieren. Die gleichzeitige Bereitstellung von lync Server 2013 mit lync Server 2010 und Office Communications Server 2007 R2 (gleichzeitige Bereitstellung aller drei Versionen) wird nicht unterstützt.

Während einer phasenweisen Migration, bei der eine vorherige lync Server 2010-oder Office Communications Server 2007 R2-Bereitstellung temporär mit der neuen lync Server 2013-Bereitstellung koexistiert, ist die Unterstützung für das Routing für gemischte Versionen begrenzt. Ausführliche Informationen finden Sie in der Migrationsdokumentation.

Sie müssen getrennte und unterschiedliche Computer mit Microsoft SQL Server 2008 R2 oder Microsoft SQL Server 2012 für Ihre lync Server 2013-Datenbankinstanzen verwenden. Sie können nicht dieselbe Instanz von SQL Server für einen lync Server 2013-Front-End-Pool verwenden, den Sie für einen lync Server 2010-oder Office Communications Server 2007 R2-Front-End-Pool verwenden. Wenn Sie lync Server 2013 im Topologie-Generator für eine Bereitstellung definieren und konfigurieren, die bereits lync Server 2010 oder Office Communications Server 2007 R2 bereitgestellt hat, können Sie mit dem Topology Builder keine Instanz eines lync Server 2013 definieren, die bereits in Verwendung ist die Topologie.

Der Topologie-Generator zeigt die folgende Meldung an, um Sie über dieses Problem zu informieren: \["der SQL Server\] -FQDN des Servers enthält bereits eine SQL-Instanz-Hostfunktion ' Benutzerspeicher '."

<div>


> [!NOTE]  
> Wenn Sie Serverrollen bereitstellen möchten, die für Ihre lync Server 2013-Bereitstellung neu sind, sollten Sie zunächst die vorhandene Bereitstellung wie in der Migrationsdokumentation und der Bereitstellungsdokumentation beschrieben aktualisieren und dann die neuen Serverrollen wie in beschrieben bereitstellen. die Dokumentation zur Planungsdokumentation und zur Bereitstellung. Wenn Sie eine frühere Version des Gruppen-Chats migrieren, migrieren Sie Sie zuletzt nach Abschluss des Prozesses für die Migration aller anderen Komponenten von lync Server 2010 oder Office Communications Server 2007 R2.



</div>

Spezifische Anforderungen an die Koexistenz und weitere Details zur Koexistenz und Migration von lync Server 2010 oder Office Communications Server 2007 R2 und lync Server 2013-Komponenten finden Sie unter [Migration von lync Server 2010 zu lync Server 2013](migration-from-lync-server-2010-to-lync-server-2013.md) und [Migration von Office Communications Server 2007 R2 zu lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md) in der Migrationsdokumentation. Details zur Unterstützung von gemischten Versionen für Clients finden Sie unter [Unterstützte Clients aus vorherigen Bereitstellungen in lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

