---
title: Konfigurieren von vertrauenswürdigen Anwendungsservern
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn Sie einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie in einer gemischten Umgebung mit den nächsten hoppool einen Skype für Business Server 2019 Pool werden festlegen. In einer gemischten Umgebung werden sowohl Pool der Vorgängerversion der Skype für Business Server 2019 Pool in der Dropdownliste aus. Auswählen der Pool den Vorgängerversion wird nicht unterstützt.
ms.openlocfilehash: d1c79e044145a4739cf1b7bfb3992320be1e4ab3
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027746"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="b8d93-105">Konfigurieren von vertrauenswürdigen Anwendungsservern</span><span class="sxs-lookup"><span data-stu-id="b8d93-105">Configure trusted application servers</span></span>

<span data-ttu-id="b8d93-106">Wenn Sie einen neuen vertrauenswürdigen Anwendungsserver erstellen, müssen Sie in einer gemischten Umgebung mit den nächsten hoppool einen Skype für Business Server 2019 Pool werden festlegen.</span><span class="sxs-lookup"><span data-stu-id="b8d93-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b8d93-107">In einer gemischten Umgebung werden sowohl Pool der Vorgängerversion der Skype für Business Server 2019 Pool in der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="b8d93-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="b8d93-108">Auswählen der Pool den Vorgängerversion wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b8d93-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b8d93-109">Wenn Sie einen vertrauenswürdigen Anwendungsserver migrieren, sollten Sie auch die Version von UCMA aktualisieren, den, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8d93-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="b8d93-110">Wenn Sie einen neuen vertrauenswürdigen Anwendungspool für Skype für Business Server 2019 erstellen, sollten Sie UCMA aktualisieren, um die Version, die in Skype für Business Server 2019 enthalten ist oder die neueste Version verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b8d93-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="b8d93-111">Wählen Sie Skype für Business Server 2019 als nächsten Hop beim Erstellen eines vertrauenswürdigen Anwendungsservers</span><span class="sxs-lookup"><span data-stu-id="b8d93-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="b8d93-112">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b8d93-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="b8d93-113">Klicken Sie im linken Bereich Maustaste auf **Vertrauenswürdige Anwendungsserver** , und klicken Sie auf **Neuer Pool für vertrauenswürdige Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="b8d93-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="b8d93-114">Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools, und wählen Sie aus, ob es Einzelserver oder mehreren Servern ist.</span><span class="sxs-lookup"><span data-stu-id="b8d93-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="b8d93-115">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b8d93-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="b8d93-116">Wählen Sie auf der Seite **Wählen Sie den nächsten Hop** aus der Liste der Skype für Business Server 2019 Front-End-Pool ein.</span><span class="sxs-lookup"><span data-stu-id="b8d93-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="b8d93-117">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b8d93-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="b8d93-118">Wählen Sie den obersten Knoten **Skype für Business Server**aus, und wählen Sie im Menü **Aktion** **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="b8d93-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="b8d93-119">Stellen Sie sicher, dass der **Vertrauenswürdige Anwendungspool** erfolgreich erstellt wurde und dem richtigen Front-End-Pool zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b8d93-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

