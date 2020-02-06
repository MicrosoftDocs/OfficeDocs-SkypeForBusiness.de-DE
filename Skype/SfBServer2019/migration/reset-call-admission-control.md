---
title: Zurücksetzen der Anrufsteuerung
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
description: Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812803"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="b05f3-103">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="b05f3-103">Reset call admission control</span></span>

<span data-ttu-id="b05f3-104">Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.</span><span class="sxs-lookup"><span data-stu-id="b05f3-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="b05f3-105">So setzen Sie CAC zurück</span><span class="sxs-lookup"><span data-stu-id="b05f3-105">To reset CAC</span></span>

1. <span data-ttu-id="b05f3-106">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="b05f3-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="b05f3-107">Klicken Sie mit der rechten Maustaste auf den Websiteknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b05f3-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="b05f3-108">Vergewissern Sie sich, dass unter Einstellungen für die **Anrufsteuerung**die Option **Anrufsteuerung aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b05f3-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="b05f3-109">Wählen Sie unter **Front-End-Pool zum Ausführen der Anrufannahme Steuerung (CAC)** den Skype for Business Server 2019-Pool aus, der CAC hosten soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b05f3-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="b05f3-110">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="b05f3-110">Publish the topology.</span></span>
    

