---
title: 'Lync Server 2013: von der gruppenanrufannahme verwendete Komponenten'
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
ms.openlocfilehash: a05bf0b6a55eb3d8d3d322061947ac43f6295c63
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="0ff70-102">Von der gruppenanrufannahme in lync Server 2013 verwendete Komponenten</span><span class="sxs-lookup"><span data-stu-id="0ff70-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ff70-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="0ff70-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="0ff70-104">Die gruppenanrufannahme wird automatisch bereitgestellt, wenn Sie Enterprise-VoIP und die Anwendung zum Parken von Anrufen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0ff70-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="0ff70-105">Sie aktivieren die gruppenanrufannahme durch Konfigurieren der Orbit-Tabelle für das Parken von Anrufen mit getrennten Nummernbereichen, die als Nummern für die Anrufannahme Gruppe festgelegt sind, und dann durch Zuweisen von Benutzern zu Anrufannahme Gruppen und Aktivieren der Benutzer für die gruppenanrufannahme.</span><span class="sxs-lookup"><span data-stu-id="0ff70-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="0ff70-106">Die folgenden lync Server Komponenten unterstützen die gruppenanrufannahme:</span><span class="sxs-lookup"><span data-stu-id="0ff70-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="0ff70-107">**Anwendungsdienst**   Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen wie der Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="0ff70-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="0ff70-108">Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="0ff70-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="0ff70-109">**Anwendung zum Parken von Anrufen**   das Anwendung zum Parken von anrufen ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="0ff70-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="0ff70-110">Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="0ff70-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="0ff70-111">**Lync Server-Verwaltungsshell**   Sie lync Server-Verwaltungsshell zum Verwalten von Gruppenanruf-pickupgruppen verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ff70-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="0ff70-112">**SEFAUtil Resource Kit-Tool**   Sie verwenden das sekundäre Erweiterungsfeature Activation Utility (SEFAUtil), um Benutzer einer Anrufannahme Gruppe zuzuweisen und die Anrufannahme für Benutzer zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0ff70-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

