---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
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
description: Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool festlegen. In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Pool Skype for Business Server 2019 in der Dropdownliste angezeigt. Die Auswahl des Pools der Vorversion wird nicht unterstützt.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753945"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="2af55-105">Konfigurieren von vertrauenswürdigen Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="2af55-105">Configure trusted application servers</span></span>

<span data-ttu-id="2af55-106">Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool festlegen.</span><span class="sxs-lookup"><span data-stu-id="2af55-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="2af55-107">In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Pool Skype for Business Server 2019 in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2af55-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="2af55-108">Die Auswahl des Pools der Vorversion wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2af55-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2af55-109">Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die Version von UCMA aktualisieren, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="2af55-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="2af55-110">Wenn Sie einen neuen vertrauenswürdigen Anwendungs Pool für Skype for Business Server 2019 erstellen, sollten Sie UCMA auf die Version aktualisieren, die in Skype for Business Server 2019 enthalten ist, oder die neueste Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2af55-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="2af55-111">Auswählen Skype for Business Server 2019 als nächsten Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers</span><span class="sxs-lookup"><span data-stu-id="2af55-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="2af55-112">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="2af55-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="2af55-113">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.</span><span class="sxs-lookup"><span data-stu-id="2af55-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="2af55-114">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um einen Einzelserver oder mehrere Server handelt.</span><span class="sxs-lookup"><span data-stu-id="2af55-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="2af55-115">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2af55-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="2af55-116">Wählen Sie auf der Seite **nächsten Hop auswählen** in der Liste die Skype for Business Server 2019 Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="2af55-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="2af55-117">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2af55-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="2af55-118">Wählen Sie den obersten Knoten **Skype for Business Server**aus, und wählen Sie im Menü **Aktion** die Option **veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="2af55-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="2af55-119">Stellen Sie sicher, dass der **Vertrauenswürdige Anwendungs Pool** erfolgreich erstellt wurde und dem korrekten Front-End-Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2af55-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

