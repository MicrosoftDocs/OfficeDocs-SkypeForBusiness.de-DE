---
title: Zurücksetzen der Anrufsteuerung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307098"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="e68af-103">Zurücksetzen der Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="e68af-103">Reset call admission control</span></span>

<span data-ttu-id="e68af-104">Wenn ein Legacy-Front-End-Pool eine Anrufannahme Steuerung (CAC) hostet, müssen Sie das CAC-Hosting in einen Skype for Business Server 2019-Pool verschieben, bevor Sie den Legacy-Front-End-Pool entfernen können.</span><span class="sxs-lookup"><span data-stu-id="e68af-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="e68af-105">So setzen Sie CAC zurück</span><span class="sxs-lookup"><span data-stu-id="e68af-105">To reset CAC</span></span>

1. <span data-ttu-id="e68af-106">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="e68af-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="e68af-107">Klicken Sie mit der rechten Maustaste auf den Websiteknoten, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="e68af-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e68af-108">Vergewissern Sie sich, dass unter Einstellungen für die **Anrufsteuerung**die Option **Anrufsteuerung aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e68af-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="e68af-109">Wählen Sie unter **Front-End-Pool zum Ausführen der Anrufannahme Steuerung (CAC)** den Skype for Business Server 2019-Pool aus, der CAC hosten soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e68af-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e68af-110">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="e68af-110">Publish the topology.</span></span>
    

