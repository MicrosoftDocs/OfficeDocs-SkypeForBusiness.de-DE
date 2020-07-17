---
title: Migrieren von Archivierungservern und Monitoring Servern
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Wenn Sie Archivierungsserver und Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben. Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor dem migrieren die Archivierung und Überwachung zu Ihrem Skype for Business Server 2019-Pilot Pool hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752667"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="b374e-104">Migrieren von Archivierungservern und Monitoring Servern</span><span class="sxs-lookup"><span data-stu-id="b374e-104">Migrating Archiving and Monitoring Servers</span></span>

<span data-ttu-id="b374e-105">Wenn Sie Archivierungsserver und Monitoring Server in ihrer Legacyumgebung bereitgestellt haben, können Sie diese Server in Ihrer Skype for Business Server 2019-Umgebung bereitstellen, nachdem Sie Ihre Front-End-Pools migriert haben.</span><span class="sxs-lookup"><span data-stu-id="b374e-105">If you deployed Archiving Server and Monitoring Server in your legacy environment, you can deploy these servers in your Skype for Business Server 2019 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="b374e-106">Wenn Archivierungs-und Überwachungsfunktionen für Ihre Organisation wichtig sind, sollten Sie jedoch vor dem migrieren die Archivierung und Überwachung zu Ihrem Skype for Business Server 2019-Pilot Pool hinzufügen, damit die Funktionalität während des Migrationsprozesses zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="b374e-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Skype for Business Server 2019 pilot pool before you migrate so that the functionality is available during the migration process.</span></span> 
  
<span data-ttu-id="b374e-107">Wenn Sie während des Migrationsvorgangs Archivierungs- und Überwachungsfunktionen benötigen, sollten Sie die folgenden Aspekte berücksichtigen:</span><span class="sxs-lookup"><span data-stu-id="b374e-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>
  
- <span data-ttu-id="b374e-108">Das Archivieren von Daten und Überwachungsdaten wird nicht in die Skype for Business Server 2019-Bereitstellung verschoben.</span><span class="sxs-lookup"><span data-stu-id="b374e-108">Archiving data and monitoring data are not moved to the Skype for Business Server 2019 deployment.</span></span> <span data-ttu-id="b374e-109">Die Daten, die Sie vor der Außerbetriebnahme der Vorgänger Umgebung sichern, sind die Historie der Aktivitäten in der Legacyumgebung.</span><span class="sxs-lookup"><span data-stu-id="b374e-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the legacy environment.</span></span>
    
- <span data-ttu-id="b374e-110">Die ältere Version von Archivierungsserver und Monitoring Server kann nur mit einem Legacy Front-End-Pool verknüpft werden.</span><span class="sxs-lookup"><span data-stu-id="b374e-110">The legacy version of Archiving Server and Monitoring Server can be associated only with a legacy Front End pool.</span></span> <span data-ttu-id="b374e-111">In Skype for Business Server 2019 sind Archivierung und Überwachung keine Server Rollen mehr, sondern Dienste, die in die Front-End-Pool Skype for Business Server 2019 integriert sind.</span><span class="sxs-lookup"><span data-stu-id="b374e-111">In Skype for Business Server 2019, Archiving and Monitoring are no longer server roles, but services integrated into the Skype for Business Server 2019 Front End pool.</span></span>
    
- <span data-ttu-id="b374e-112">Während der Zeit, in der Ihre Legacy-und Skype for Business Server 2019-Bereitstellungen nebeneinander bestehen, sammeln die Legacy Version von Archivierungsserver und Monitoring Server Daten für Benutzer, die in älteren Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b374e-112">During the time that your legacy and Skype for Business Server 2019 deployments coexist, the legacy version of Archiving Server and Monitoring Server gather data for users homed on legacy pools.</span></span> <span data-ttu-id="b374e-113">Archivierung und Überwachung in Skype for Business Server 2019 Sammeln von Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b374e-113">Archiving and Monitoring in Skype for Business Server 2019 gather data for users homed on Skype for Business Server 2019 pools.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b374e-114">Während der Migrationsphase, in der Sie weiterhin den Legacy-Edgeserver mit dem neuen Skype for Business Server 2019-Pilot Pool verwenden, sammelt die Vorgängerversion von Archivierungsserver weiterhin Daten für Benutzer, die in älteren Pools verwaltet werden, und archiviert in Skype for Business Server 2019 sammelt Daten für Benutzer, die in Skype for Business Server 2019-Pools verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b374e-114">During the phase of migration when you are still using your legacy Edge server with the new Skype for Business Server 2019 pilot pool, the legacy version of Archiving Server continues to gather data for users homed on legacy pools and Archiving in Skype for Business Server 2019 gathers data for users homed on Skype for Business Server 2019 pools.</span></span> 
  
- <span data-ttu-id="b374e-115">Wenn Sie eine Archivierungs-und Überwachungslösung eines Drittanbieters in Verbindung mit der Archivierung und Überwachung in Skype for Business Server 2019 verwenden, wenden Sie sich an Ihren Anbieter, wann und wie Sie die Drittanbieterlösung mit Skype for Business Server 2019 integrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b374e-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Skype for Business Server 2019, consult with your vendor about when and how you need to integrate the third-party solution with Skype for Business Server 2019.</span></span>
    

