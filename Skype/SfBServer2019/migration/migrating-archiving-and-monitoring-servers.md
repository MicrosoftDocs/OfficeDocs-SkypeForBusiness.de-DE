---
title: Migrieren von Archivierungsservern und Monitoring Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie in der vorgängerumgebung Archivierungsserver und Monitoring Server bereitgestellt haben, können Sie diese Server nach dem Migrieren der Front-End-Pools in Ihrer Skype für Business Server 2019 Umgebung bereitstellen. Wenn die Archivierung und Überwachung von Funktionen für Ihre Organisation unternehmenskritisch sind, jedoch sollten Sie hinzufügen, Archivierung und Überwachung auf Ihre Skype für Business Server 2019 pilot Pool vor der Migration, damit die Funktionalität während des Migrationsprozesses verfügbar ist.
ms.openlocfilehash: 24dc3e3007fd9a58c23f9c15a31cccc766d45e83
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231644"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="f6065-104">Migrieren von Archivierungsservern und Monitoring Servern</span><span class="sxs-lookup"><span data-stu-id="f6065-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="f6065-105">Wenn Sie in der vorgängerumgebung Archivierungsserver und Monitoring Server bereitgestellt haben, können Sie diese Server nach dem Migrieren der Front-End-Pools in Ihrer Skype für Business Server 2019 Umgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f6065-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="f6065-106">Wenn die Archivierung und Überwachung von Funktionen für Ihre Organisation unternehmenskritisch sind, jedoch sollten Sie hinzufügen, Archivierung und Überwachung auf Ihre Skype für Business Server 2019 pilot Pool vor der Migration, damit die Funktionalität während des Migrationsprozesses verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f6065-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="f6065-107">Wenn Sie während des Migrationsvorgangs Archivierungs-und möchten, beachten Sie folgende Aspekte beachten:</span><span class="sxs-lookup"><span data-stu-id="f6065-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="f6065-108">Archivieren von Daten und Überwachung von Daten werden nicht in der Skype für Business Server 2019 Bereitstellung verschoben.</span><span class="sxs-lookup"><span data-stu-id="f6065-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="f6065-109">Die Daten, die Sie vor der Außerbetriebnahme der Vorversionen Umgebung sichern werden aufgezeichnete Aktivität in der Vorversion-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="f6065-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="f6065-110">Die ältere Version des Archivierungsservers und Monitoring Server kann nur einen legacy-Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f6065-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="f6065-111">In Skype für Business Server 2019 sind Archivierung und Überwachung nicht mehr Serverrollen, aber Services integriert die Skype für Business Server 2019 Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="f6065-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="f6065-112">Während der Zeit, die Ihre Legacy und Skype für Business Server 2019 Bereitstellungen möglich ist, die ältere Version des Archivierungsservers und Monitoring Server Erfassen von Daten für Benutzer in alten Pools verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f6065-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="f6065-113">Archivierung und Überwachung in Skype für Business Server 2019 sammeln, dass Daten für Benutzer in Skype für Business Server 2019 Pools verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f6065-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f6065-114">Während der Phase der Migration, wenn Sie sind weiterhin mit dem von der legacy-Edge-Server mit der neuen Skype für Business Server 2019 pilot Pool, die ältere Version des Archivierungsservers zum Erfassen von Daten für Benutzer weiterhin in alten Pools verwaltet und Archivierung in Skype für Unternehmen Server 2019 sammelt Daten für Benutzer in Skype für Business Server 2019 Pools verwaltet.</span><span class="sxs-lookup"><span data-stu-id="f6065-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="f6065-115">Wenn Sie einen Drittanbieter-Archivierung und Überwachung der Lösung in Verbindung mit der Archivierung und Überwachung in Skype für Business Server 2019 verwenden, wenden Sie sich an Ihren Händler wann und wie Sie die Drittanbieter-Lösung mit Skype für Business Server 2019 integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="f6065-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

