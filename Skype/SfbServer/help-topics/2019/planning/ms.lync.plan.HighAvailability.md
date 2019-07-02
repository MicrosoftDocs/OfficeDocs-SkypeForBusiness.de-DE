---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 36869cedb2443d13774e8646b72a51a039683f16
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418612"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="312bb-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="312bb-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="312bb-105">Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server basiert auf Serverredundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="312bb-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="312bb-106">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="312bb-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="312bb-107">Für Skype for Business Server sind mindestens zwei Front-End-Server erforderlich, um eine höhere Verfügbarkeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="312bb-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="312bb-108">Das Planungs Tool verwendet die folgenden Kriterien, um festzustellen, ob zusätzliche Server hinzugefügt werden, um eine höhere Verfügbarkeit zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="312bb-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="312bb-109">Wenn die Bereitstellung zwei oder mehr Front-End-Server enthält, fügt das Planungs Tool keinen zusätzlichen Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="312bb-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="312bb-110">Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="312bb-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="312bb-111">Wenn die Bereitstellung beständigen Chat enthält, wird vom Planungstool ein zusätzlicher Server hinzugefügt, aber nicht die Poolnummer erhöht.</span><span class="sxs-lookup"><span data-stu-id="312bb-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="312bb-112">Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungs Tool vor, einen zusätzlichen Server hinzuzufügen (für insgesamt fünf Server), jedoch wird ein einzelner Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="312bb-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="312bb-113">Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="312bb-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="312bb-114">In Teams steht dieselbe Funktionalität zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="312bb-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="312bb-115">Weitere Informationen finden Sie unter [Upgrade von Skype for Business zu Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="312bb-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="312bb-116">Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer, die diese Funktion benötigen, an Teams migrieren oder die Verwendung von Skype for Business Server 2015 fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="312bb-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="312bb-117">Das Planungs Tool fügt auch eine Spiegel-SQL-Datenbank für alle Datenbanken hinzu.</span><span class="sxs-lookup"><span data-stu-id="312bb-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="312bb-118">Wenn beispielsweise eine SQL Server-Front-End-Datenbank vorhanden ist, wird das Planungs Tool die andere Datenbank als Spiegeldatenbank für diese hinzufügen und als "Front-End-Spiegelungs-SQL-Datenbank benennen.</span><span class="sxs-lookup"><span data-stu-id="312bb-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="312bb-119">Weitere Informationen zum Vorbereiten Ihrer Umgebung für eine höhere Verfügbarkeit finden Sie unter [Planen von Höchstverfügbarkeit und Disaster Recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="312bb-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

