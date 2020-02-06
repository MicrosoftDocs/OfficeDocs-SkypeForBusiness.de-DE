---
title: Migrieren von Archivierungs-und Überwachungs Servern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn Sie den Archivierungsserver und den Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration dem Skype for Business Server 2019-Pilot Pool Archivierungs-und Überwachungsfunktionen hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.
ms.openlocfilehash: 5088f4b4f72ddc083cf2868df893946561eb2469
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813453"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="3a0c8-104">Migrieren von Archivierungs-und Überwachungs Servern</span><span class="sxs-lookup"><span data-stu-id="3a0c8-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="3a0c8-105">Wenn Sie den Archivierungsserver und den Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="3a0c8-106">Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor der Migration dem Skype for Business Server 2019-Pilot Pool Archivierungs-und Überwachungsfunktionen hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="3a0c8-107">Wenn Sie während des Migrationsprozesses Archivierungs-und Überwachungsfunktionen wünschen, sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="3a0c8-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="3a0c8-108">Archivierungsdaten und Überwachungsdaten werden nicht in die Skype for Business Server 2019-Bereitstellung verschoben.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="3a0c8-109">Die Daten, die Sie vor der Außerbetriebnahme der Legacyumgebung sichern, sind Ihr Aktivitätsverlauf in der Legacyumgebung.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="3a0c8-110">Die Legacy Version des Archivierungsservers und des Überwachungsservers kann nur einem Legacy-Front-End-Pool zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="3a0c8-111">In Skype for Business Server 2019 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in den Front-End-Pool von Skype for Business Server 2019 integriert sind.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="3a0c8-112">In der Zeit, in der Ihre Legacy-und Skype for Business Server 2019-Bereitstellungen koexistieren, sammeln die Legacy Version des Archivierungsservers und des Überwachungsservers Daten für Benutzer, die in Legacy Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="3a0c8-113">Archivierung und Überwachung in Skype for Business Server 2019 sammeln Sie Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3a0c8-114">Während der Migrationsphase, wenn Sie Ihren Legacy-Edgeserver weiterhin mit dem neuen Skype for Business Server 2019-Pilot Pool verwenden, sammelt die Legacy Version des Archivierungsservers weiterhin Daten für Benutzer, die sich in Legacy Pools befinden und in Skype for Business archiviert werden. Server 2019 sammelt Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="3a0c8-115">Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit Archivierung und Überwachung in Skype for Business Server 2019 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung in Skype for Business Server 2019 integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="3a0c8-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

