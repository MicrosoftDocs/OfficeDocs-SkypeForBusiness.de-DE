---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool einrichten. In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Skype for Business Server 2019-Pool in der Dropdownliste angezeigt. Das Auswählen des Legacy Pools wird nicht unterstützt.
ms.openlocfilehash: b0dfb9ba1e4744ba3e0ea0c376f67a224e70376a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289599"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="556e1-105">Konfigurieren von vertrauenswürdigen Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="556e1-105">Configure trusted application servers</span></span>

<span data-ttu-id="556e1-106">Wenn Sie in einer gemischten Umgebung einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie den Pool für den nächsten Hop als Skype for Business Server 2019-Pool einrichten.</span><span class="sxs-lookup"><span data-stu-id="556e1-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="556e1-107">In einer gemischten Umgebung werden sowohl der Legacy Pool als auch der Skype for Business Server 2019-Pool in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="556e1-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="556e1-108">Das Auswählen des Legacy Pools wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="556e1-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="556e1-109">Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die von Ihnen verwendete Version von UCMA aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="556e1-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="556e1-110">Wenn Sie einen neuen vertrauenswürdigen Anwendungs Pool für Skype for Business Server 2019 erstellen, sollten Sie UCMA auf die Version aktualisieren, die im Lieferumfang von Skype for Business Server 2019 oder in der neuesten Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="556e1-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="556e1-111">Auswählen von Skype for Business Server 2019 als nächster Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers</span><span class="sxs-lookup"><span data-stu-id="556e1-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="556e1-112">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="556e1-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="556e1-113">Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **neuer vertrauenswürdiger Anwendungs Pool**.</span><span class="sxs-lookup"><span data-stu-id="556e1-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="556e1-114">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, und wählen Sie aus, ob es sich um einen Einzelserver oder um mehrere Server handelt.</span><span class="sxs-lookup"><span data-stu-id="556e1-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="556e1-115">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="556e1-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="556e1-116">Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den Skype for Business Server 2019-Front-End-Pool aus.</span><span class="sxs-lookup"><span data-stu-id="556e1-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="556e1-117">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="556e1-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="556e1-118">Wählen Sie den obersten Knoten **für Skype for Business Server**aus, und wählen Sie im Menü **Aktion** die Option **veröffentlichen**aus.</span><span class="sxs-lookup"><span data-stu-id="556e1-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="556e1-119">Überprüfen Sie, ob der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="556e1-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

