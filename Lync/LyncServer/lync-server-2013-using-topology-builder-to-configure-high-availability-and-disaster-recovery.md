---
title: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75117cd8a88b5ff5f333457033b5af49c5464f53
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42116728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Konfigurieren der hohen Verfügbarkeit und der Notfallwiederherstellung mithilfe des Topologie-Generators in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Führen Sie die folgenden Schritte im Topologie-Generator aus, um die hohe Verfügbarkeit und Notfallwiederherstellung für den Server für beständigen Chat zu konfigurieren.

1.  Fügen Sie die Spiegeldatenbanken und die sekundäre Datenbank des Protokollversands SQL Server speichern hinzu.

2.  Bearbeiten Sie die Eigenschaften des Server Diensts für beständigen Chat wie folgt:
    
    1.  Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    2.  Fügen Sie den primären Spiegel SQL Server Speicher hinzu.
    
    3.  Aktivieren Sie die SQL Server Protokollversanddatenbank.
    
    4.  Fügen Sie den sekundären SQL Server Speicher des SQL Server Protokollversands hinzu.
    
    5.  Fügen Sie die SQL Server Speicher Spiegel für die sekundäre Datenbank hinzu.
    
    6.  Veröffentlichen Sie die Topologie.

</div>

<span> </span>

</div>

</div>

</div>

