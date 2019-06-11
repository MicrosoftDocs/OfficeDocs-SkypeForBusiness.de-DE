---
title: Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using a stretched Persistent Chat Server pool for disaster recovery
ms:assetid: 74c5287e-d70d-490a-9adc-ab419917ddd9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205007(v=OCS.15)
ms:contentKeyID: 48184506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cced4904619fdbda87fecb29f35f11b40270c0ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-a-stretched-persistent-chat-server-pool-for-disaster-recovery-in-lync-server-2013"></a>Verwenden eines ausgedehnten Pools für den Server für beständigen Chat für die Notfallwiederherstellung in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Die Disaster Recovery-Lösung für den Server für beständigen Chat basiert auf einem ausgestreckten beständigen Chat Serverpool. Dies ähnelt der Stabilität von Metropolitan Site in lync Server 2010; Es gibt jedoch keine Voraussetzung für ein gedehntes virtuelles lokales Netzwerk (VLAN). Indem Sie den Serverpool für beständigen Chat Strecken, konfigurieren Sie im Wesentlichen einen Pool in der Topologie logisch, aber Sie platzieren die Server physisch in einem Pool in zwei unterschiedlichen Rechenzentren. Konfigurieren Sie die SQL Server-Spiegelung für die Datenbank auf die gleiche Weise, und stellen Sie die Datenbank und die Spiegelung im gleichen Rechenzentrum bereit. Sie müssen eine Sicherungsdatenbank im sekundären Rechenzentrum konfigurieren (mit einem optionalen Mirror, um eine höhere Verfügbarkeit während der Disaster Recovery zu gewährleisten). Hierbei handelt es sich um die Backup-Datenbank, die für ein Failover während der Disaster Recovery verwendet wird.

Ausführliche Informationen zum Konfigurieren der SQL Server-Spiegelung für eine höhere Verfügbarkeit finden Sie unter [SQL Server-Spiegelung in lync Server 2013](lync-server-2013-sql-server-mirroring.md). Details zum Failover der Datenbank für die Disaster Recovery finden Sie unter [Einrichten des SQL Server-Protokollversands in lync Server 2013 für die primäre Datenbank des](lync-server-2013-setting-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database.md) beständigen Chats und Einrichten des [SQL Server-Protokollversands zwischen der primären Spiegelung und dem Protokoll. Sekundäre Datenbank für den Versand in lync Server 2013](lync-server-2013-setting-up-sql-server-log-shipping-between-the-primary-mirror-and-the-log-shipping-secondary-database.md)

</div>

<span> </span>

</div>

</div>

</div>

