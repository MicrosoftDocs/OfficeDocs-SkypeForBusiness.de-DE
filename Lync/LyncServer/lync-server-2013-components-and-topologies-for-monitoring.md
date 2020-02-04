---
title: 'Lync Server 2013: Komponenten und Topologien für die Überwachung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for monitoring
ms:assetid: c1bb36b0-1fb8-4d8e-9cc9-9bef740fe3c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412952(v=OCS.15)
ms:contentKeyID: 48185313
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76e857d0c80793f61b8e60686cc9455d27bb9f95
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-monitoring-in-lync-server-2013"></a>Komponenten und Topologien für die Überwachung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-05_

Da die Unified Data Collection-Agents automatisch auf jedem Front-End-Server installiert und aktiviert werden, müssen Sie keinen Server so konfigurieren, dass er als Monitoring Server fungiert. Jeder Front-End-Server fungiert bereits als Monitoring Server. Sie müssen jedoch eine Datenbank installieren und konfigurieren, damit Sie als Back-End-Datenspeicher für Ihre Überwachungsdaten fungieren kann. Microsoft lync Server 2013 kann eine der folgenden Datenbanken als Back-End-Speicher für die Überwachung verwenden:

  - Microsoft SQL Server 2008 R2 Enterprise Edition

  - Microsoft SQL Server 2008 R2 Standard Edition

  - Microsoft SQL Server 2012 Enterprise Edition

  - Microsoft SQL Server 2012 Standard Edition

Beachten Sie, dass Sie die 64-Bit-Editionen dieser Datenbanken verwenden müssen. 32-Bit-Versionen von SQL Server können nicht als Back-End-Speicher zum Überwachen verwendet werden. Ebenso unterstützt lync Server 2013 die Express-Editionen von SQL Server 2008 oder SQL Server 2012 nicht. Weitere Informationen zu den Datenbankanforderungen für lync Server 2013 finden Sie im Thema [Datenbanksoftware-Unterstützung in lync Server 2013](lync-server-2013-database-software-support.md) im lync Server 2013-Leitfaden zur Unterstützung.

Beachten Sie, dass SQL Server installiert und konfiguriert werden muss, bevor Sie die Überwachung bereitstellen und konfigurieren. Sie müssen jedoch nur SQL Server selbst bereitstellen. Sie müssen die Überwachungsdatenbanken nicht im Voraus einrichten. Stattdessen werden diese Datenbankenautomatisch für Sie erstellt, wenn Sie Ihre lync Server-Topologie veröffentlichen.

Überwachungsdaten können eine SQL Server-Instanz gemeinsam mit anderen Datentypen verwenden. In der Regel verwenden die Datenbank für die Aufzeichnung von Kommunikationsdatensätzen (LcsCdr) und die Quality of Experience-Datenbank (QoEMetrics) dieselbe SQL-Instanz. Häufig sind die beiden Überwachungsdatenbanken auch in derselben SQL-Instanz wie die Archivierungsdatenbank (LcsLog) vorhanden. Die einzige echte Anforderung für SQL Server-Instanzen besteht darin, dass jede Instanz von SQL Server auf Folgendes beschränkt ist:

  - Eine Instanz der lync Server 2013-Back-End-Datenbank. (Im Allgemeinen wird davon abgeraten, die Überwachungsdatenbank in derselben SQL-Instanz oder sogar auf demselben Computer wie die Back-End-Datenbank zu verwenden. Dies ist zwar technisch möglich, aber es besteht das Risiko, dass die Überwachungsdatenbank Speicherplatz belegt, der für die Back-End-Datenbank benötigt wird.)

  - Eine Instanz der Datenbank für die Aufzeichnung von Kommunikationsdatensätzen.

  - Eine Instanz der Quality of Experience-Datenbank.

  - Eine Instanz der Archivierungsdatenbank.

Anders ausgedrückt: Sie können nicht zwei Instanzen der LcsCdr-Datenbank in der gleichen Instanz von SQL Server haben. Wenn Sie mehrere Instanzen der LcsCdr-Datenbank benötigen, müssen Sie mehrere Instanzen von SQL Server konfigurieren.

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen der Überwachung in lync Server 2013](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

