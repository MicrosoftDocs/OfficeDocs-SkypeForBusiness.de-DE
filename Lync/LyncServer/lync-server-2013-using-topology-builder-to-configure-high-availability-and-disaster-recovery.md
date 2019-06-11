---
title: Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Topology Builder to configure high availability and disaster recovery
ms:assetid: abc1a25d-1f5e-46ef-91d2-0144fc847206
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205172(v=OCS.15)
ms:contentKeyID: 48185113
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b167ea64f42510febe0f405d15e2eafab7efc2bd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-topology-builder-to-configure-high-availability-and-disaster-recovery-in-lync-server-2013"></a>Konfigurieren von hoher Verfügbarkeit und Notfallwiederherstellung mithilfe des Topologie-Generators in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Führen Sie die folgenden Schritte im Topologie-Generator aus, um die Hochverfügbarkeits-und Disaster Recovery für beständigen Chat Server zu konfigurieren.

1.  Hinzufügen der Spiegeldatenbanken und der sekundären Datenbank des Protokollversands SQL Server Stores.

2.  Bearbeiten Sie die Diensteigenschaften des beständigen Chat-Servers wie folgt:
    
    1.  Aktivieren Sie die Spiegelung für die primäre Datenbank.
    
    2.  Fügen Sie den primären Spiegelungs-SQL Server-Speicher hinzu.
    
    3.  Aktivieren Sie die SQL Server-Protokollversanddatenbank.
    
    4.  Fügen Sie den SQL Server-Protokollversand-sekundären SQL Server-Speicher hinzu.
    
    5.  Fügen Sie die SQL Server Store-Spiegelung für die sekundäre Datenbank hinzu.
    
    6.  Veröffentlichen Sie die Topologie.

</div>

<span> </span>

</div>

</div>

</div>

