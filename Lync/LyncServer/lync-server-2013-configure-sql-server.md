---
title: 'Lync Server 2013: Configure SQL Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server
ms:assetid: 84504918-cb4f-4b2f-be17-a70770b69025
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398669(v=OCS.15)
ms:contentKeyID: 48184699
ms.date: 01/22/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2bdac9841e908910697068460a6b7e42075e7e3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535112"
---
# <a name="configure-sql-server-in-lync-server-2013"></a><span data-ttu-id="38854-102">Konfigurieren von SQL Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38854-102">Configure SQL Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38854-103">_**Letztes Änderungsstand des Themas:** 2015-01-22_</span><span class="sxs-lookup"><span data-stu-id="38854-103">_**Topic Last Modified:** 2015-01-22_</span></span>

<span data-ttu-id="38854-104">Für jede Datenbank, die Sie bereitstellen, können Sie eine einzelne SQL Server Instanz für alle Datenbanken für Ihre lync Server 2013-Bereitstellung verwenden, die auf einem Daten Bank Server zusammengestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="38854-104">For each database that you deploy, you can use a single SQL Server instance for all databases for your Lync Server 2013 deployment that can be collocated on a database server.</span></span> <span data-ttu-id="38854-105">Ausführliche Informationen zur Daten Bank Zusammenstellung finden Sie unter [Supported Server Colocation in lync Server 2013](lync-server-2013-supported-server-collocation.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="38854-105">For details about database collocation, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="38854-106">Darüber hinaus muss jede SQL Server Instanz vor dem Ausführen der Schritte im Topologie-Generator, mit dem die Datenbanken eingerichtet wurden, oder manuelles Erstellen der Datenbanken mit Windows PowerShell-Cmdlets installiert und verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="38854-106">Additionally, each SQL Server instance must be installed and available prior to completing the steps in Topology Builder that set up the databases, or manually creating the databases with Windows PowerShell cmdlets.</span></span> <span data-ttu-id="38854-107">Ausführliche Informationen zur SQL Server-Unterstützung finden Sie unter [Hardware-Setup für lync Server 2013](lync-server-2013-hardware-setup.md).</span><span class="sxs-lookup"><span data-stu-id="38854-107">For details about SQL Server supportability, see [Hardware setup for Lync Server 2013](lync-server-2013-hardware-setup.md).</span></span>

<div>

## <a name="to-install-microsoft-sql-server-2012"></a><span data-ttu-id="38854-108">So installieren Sie Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="38854-108">To install Microsoft SQL Server 2012</span></span>

  - <span data-ttu-id="38854-109">Siehe Microsoft SQL Server 2012-Dokumentation unter: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx> .</span><span class="sxs-lookup"><span data-stu-id="38854-109">See the Microsoft SQL Server 2012 documentation at: <https://technet.microsoft.com/library/bb500395(v=sql.110).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

