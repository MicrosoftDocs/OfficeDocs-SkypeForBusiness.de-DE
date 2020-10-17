---
title: 'Lync Server 2013: von der gruppenanrufannahme verwendete Komponenten'
description: 'Lync Server 2013: von der gruppenanrufannahme verwendete Komponenten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 517f75dcbac8bfed0e749c061a9696b7667e10ed
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571831"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="b0238-103">Von der gruppenanrufannahme in lync Server 2013 verwendete Komponenten</span><span class="sxs-lookup"><span data-stu-id="b0238-103">Components used by Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0238-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="b0238-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="b0238-105">Die gruppenanrufannahme wird automatisch bereitgestellt, wenn Sie Enterprise-VoIP und die Anwendung zum Parken von Anrufen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b0238-105">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="b0238-106">Sie aktivieren die gruppenanrufannahme durch Konfigurieren der Orbit-Tabelle für das Parken von Anrufen mit getrennten Nummernbereichen, die als Nummern für die Anrufannahme Gruppe festgelegt sind, und dann durch Zuweisen von Benutzern zu Anrufannahme Gruppen und Aktivieren der Benutzer für die gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="b0238-106">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="b0238-107">Die folgenden lync Server Komponenten unterstützen die gruppenanrufannahme:</span><span class="sxs-lookup"><span data-stu-id="b0238-107">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="b0238-108">**Anwendungsdienst**     Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen, wie etwa der Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="b0238-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="b0238-109">Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="b0238-109">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="b0238-110">**Anwendung zum Parken von Anrufen**     Die Anwendung zum Parken von anrufen ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="b0238-110">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="b0238-111">Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="b0238-111">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="b0238-112">**Lync Server-Verwaltungsshell**     Sie verwenden lync Server-Verwaltungsshell zum Verwalten von Gruppenanruf-pickupgruppen.</span><span class="sxs-lookup"><span data-stu-id="b0238-112">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="b0238-113">**SEFAUtil Resource Kit-Tool**     Sie verwenden das sekundäre Erweiterungsfeature Activation Utility (SEFAUtil), um Benutzer einer Anrufannahme Gruppe zuzuweisen und die Anrufannahme für Benutzer zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b0238-113">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

