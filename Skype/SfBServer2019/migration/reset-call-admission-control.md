---
title: Zurücksetzen der Anrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn eine Deaktivierung von Front-End-Pools die anrufsteuerung (CAC) gehostet wird, müssen Sie verschieben, CAC hosting an einen Skype für Business Server 2019 Pool, bevor Sie den legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: 3b94322b86feb2c647f88102617ab1dcc9d5f8bc
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231390"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="8936a-103">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="8936a-103">Reset call admission control</span></span>

<span data-ttu-id="8936a-104">Wenn eine Deaktivierung von Front-End-Pools die anrufsteuerung (CAC) gehostet wird, müssen Sie verschieben, CAC hosting an einen Skype für Business Server 2019 Pool, bevor Sie den legacy-Front-End-Pool entfernen können.</span><span class="sxs-lookup"><span data-stu-id="8936a-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="8936a-105">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="8936a-105">To reset CAC</span></span>

1. <span data-ttu-id="8936a-106">Topologie-Generator zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8936a-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="8936a-107">Maustaste auf den Standortknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8936a-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="8936a-108">Klicken Sie unter **Call Admission Control Einstellung**sicherstellen Sie, dass **Die Anrufsteuerung aktivieren** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="8936a-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="8936a-109">Wählen Sie unter **Front-End-Pool, führen Sie die anrufsteuerung (CAC)** die Skype für Business Server 2019 Pool CAC gehostet ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8936a-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="8936a-110">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="8936a-110">Publish the topology.</span></span>
    

