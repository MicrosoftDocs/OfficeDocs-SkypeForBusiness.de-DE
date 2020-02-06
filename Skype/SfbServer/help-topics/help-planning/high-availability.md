---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server 2015 basiert auf Serverredundanz über Pooling. Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.
ms.openlocfilehash: 1d82174e8dc1314deaf81708c70054a4d602085b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821437"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="13783-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="13783-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="13783-105">Das wichtigste Hochverfügbarkeits-Schema für die meisten Serverfunktionen in Skype for Business Server 2015 basiert auf Serverredundanz über Pooling.</span><span class="sxs-lookup"><span data-stu-id="13783-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="13783-106">Wenn ein Server ausfällt, auf dem eine bestimmte Serverrolle ausgeführt wird, übernehmen die anderen Server im Pool, auf denen die gleiche Rolle ausgeführt wird, die Last dieses Servers.</span><span class="sxs-lookup"><span data-stu-id="13783-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="13783-107">Für Skype for Business Server 2015 sind mindestens zwei Front-End-Server erforderlich, um eine höhere Verfügbarkeit zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="13783-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="13783-108">Das Planungs Tool verwendet die folgenden Kriterien, um festzustellen, ob zusätzliche Server hinzugefügt werden, um eine höhere Verfügbarkeit zu unterstützen:</span><span class="sxs-lookup"><span data-stu-id="13783-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="13783-109">Wenn die Bereitstellung zwei oder mehr Front-End-Server enthält, fügt das Planungs Tool keinen zusätzlichen Server hinzu.</span><span class="sxs-lookup"><span data-stu-id="13783-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="13783-110">Wenn die Bereitstellung Edge-Server enthält, wird ein zusätzlicher Server hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="13783-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="13783-111">Wenn die Bereitstellung beständigen Chat enthält, wird vom Planungstool ein zusätzlicher Server hinzugefügt, aber nicht die Poolnummer erhöht.</span><span class="sxs-lookup"><span data-stu-id="13783-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="13783-112">Wenn die Bereitstellung beispielsweise bereits vier Server enthält, schlägt das Planungs Tool vor, einen zusätzlichen Server hinzuzufügen (für insgesamt fünf Server), jedoch wird ein einzelner Pool verwaltet.</span><span class="sxs-lookup"><span data-stu-id="13783-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="13783-113">Das Planungs Tool fügt auch eine Spiegel-SQL-Datenbank für alle Datenbanken hinzu.</span><span class="sxs-lookup"><span data-stu-id="13783-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="13783-114">Wenn beispielsweise eine SQL Server-Front-End-Datenbank vorhanden ist, wird das Planungs Tool die andere Datenbank als Spiegeldatenbank für diese hinzufügen und als "Front-End-Spiegelungs-SQL-Datenbank benennen.</span><span class="sxs-lookup"><span data-stu-id="13783-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="13783-115">Weitere Informationen zum Vorbereiten Ihrer Umgebung für eine höhere Verfügbarkeit finden Sie unter [Planen von höchst Verfügbarkeit und Disaster Recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="13783-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

