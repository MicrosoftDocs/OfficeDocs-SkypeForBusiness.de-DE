---
title: Zurücksetzen der Anrufsteuerung
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn eine Deaktivierung von Front-End-Pools die anrufsteuerung (CAC) gehostet wird, müssen Sie verschieben, CAC hosting an einen Skype für Business Server 2019 Pool, bevor Sie den legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027319"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="5da4c-103">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="5da4c-103">Reset call admission control</span></span>

<span data-ttu-id="5da4c-104">Wenn eine Deaktivierung von Front-End-Pools die anrufsteuerung (CAC) gehostet wird, müssen Sie verschieben, CAC hosting an einen Skype für Business Server 2019 Pool, bevor Sie den legacy-Front-End-Pool entfernen können.</span><span class="sxs-lookup"><span data-stu-id="5da4c-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="5da4c-105">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="5da4c-105">To reset CAC</span></span>

1. <span data-ttu-id="5da4c-106">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5da4c-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="5da4c-107">Maustaste auf den Standortknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="5da4c-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="5da4c-108">Klicken Sie unter **Call Admission Control Einstellung**sicherstellen Sie, dass **Die Anrufsteuerung aktivieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="5da4c-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="5da4c-109">Wählen Sie unter **Front-End-Pool, führen Sie die anrufsteuerung (CAC)** die Skype für Business Server 2019 Pool CAC gehostet ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5da4c-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="5da4c-110">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="5da4c-110">Publish the topology.</span></span>
    

