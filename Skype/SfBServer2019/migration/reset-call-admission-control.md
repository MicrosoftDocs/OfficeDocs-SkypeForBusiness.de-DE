---
title: Zurücksetzen der Anrufsteuerung
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
description: Wenn ein Legacy Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool versetzen, bevor Sie die Legacy Front-End-Pool entfernen können.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753297"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="eca88-103">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="eca88-103">Reset call admission control</span></span>

<span data-ttu-id="eca88-104">Wenn ein Legacy Front-End-Pool die Anrufsteuerung (Call Admission Control, CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool versetzen, bevor Sie die Legacy Front-End-Pool entfernen können.</span><span class="sxs-lookup"><span data-stu-id="eca88-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="eca88-105">So setzen Sie die Anrufsteuerung zurück</span><span class="sxs-lookup"><span data-stu-id="eca88-105">To reset CAC</span></span>

1. <span data-ttu-id="eca88-106">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="eca88-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="eca88-107">Klicken Sie mit der rechten Maustaste auf den Standortknoten, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eca88-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="eca88-108">Vergewissern Sie sich, dass in der **Einstellung für Anrufsteuerung** die Option **Anrufsteuerung aktivieren** ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="eca88-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="eca88-109">Wählen Sie unter **Front-End-Pool, um die Anrufsteuerung (Call Admission Control, CAC) auszuführen**, den Skype for Business Server 2019-Pool aus, der als Host für CAC dient, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eca88-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="eca88-110">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="eca88-110">Publish the topology.</span></span>
    

