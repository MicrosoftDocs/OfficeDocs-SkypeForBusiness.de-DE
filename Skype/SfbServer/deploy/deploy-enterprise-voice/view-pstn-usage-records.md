---
title: Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 65025c78-c263-472c-9ff9-e170588f10b5
description: 'Zusammenfassung: Informationen Sie zum Anzeigen von PSTN-verwendungsdatensätzen unter Verwendung der Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell.'
ms.openlocfilehash: 63e35879f9530d56ef770584de45a169c20ea057
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="view-pstn-usage-records-in-skype-for-business-2015"></a><span data-ttu-id="2861e-103">Anzeigen von PSTN-Verwendungsdatensätzen in Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="2861e-103">View PSTN usage records in Skype for Business 2015</span></span>
 
<span data-ttu-id="2861e-104">**Zusammenfassung:** Informationen Sie zum Anzeigen von PSTN-verwendungsdatensätzen unter Verwendung der Skype für Business Server-Systemsteuerung oder die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="2861e-104">**Summary:** Learn how to view PSTN usage records by using the Skype for Business Server Control Panel or the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="2861e-105">Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Nutzern oder Nutzergruppen in einer Organisation getätigt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="2861e-105">A Public Switched Telephone Network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="2861e-106">Weitere Informationen hierzu finden Sie unter [PSTN-Verwendungsdatensätzen](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="2861e-106">For details, see [PSTN Usage Records](http://technet.microsoft.com/library/b5f624aa-abe8-455b-a8e3-c228be230463.aspx) in the Planning documentation.</span></span>
  
### <a name="to-view-a-pstn-usage-record-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="2861e-107">So zeigen Sie eine PSTN-Datensatz mithilfe von Skype Business Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="2861e-107">To view a PSTN usage record by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="2861e-108">Öffnen von Skype Business Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="2861e-108">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="2861e-109">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.</span><span class="sxs-lookup"><span data-stu-id="2861e-109">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>
    
3. <span data-ttu-id="2861e-110">Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, den Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="2861e-110">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2861e-111">Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2861e-111">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span> 
  
### <a name="to-view-pstn-usage-information-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="2861e-112">So zeigen Sie PSTN-Verwendungsinformationen mithilfe von Skype für Business Server-Verwaltungsshell-Cmdlets an</span><span class="sxs-lookup"><span data-stu-id="2861e-112">To view PSTN usage information by using Skype for Business Server Management Shell cmdlets</span></span>

- <span data-ttu-id="2861e-113">Zum Anzeigen von Informationen über alle PSTN-Nutzungen Geben Sie den folgenden Befehl in der Skype für Business Server-Verwaltungsshell, und drücken Sie die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="2861e-113">To view information about all of your PSTN usages, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
  ```
  Get-CsPstnUsage
  ```

    <span data-ttu-id="2861e-114">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="2861e-114">This command returns information similar to the following:</span></span>
    
  ```
  Identity : Global
  Usage    : {Internal, Local, Long Distance}
  ```

## <a name="see-also"></a><span data-ttu-id="2861e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2861e-115">See also</span></span>

#### 

[<span data-ttu-id="2861e-116">Erstellen oder Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungseinträge in Skype für Business 2015</span><span class="sxs-lookup"><span data-stu-id="2861e-116">Create or modify a voice policy and configure PSTN usage records in Skype for Business 2015</span></span>](voice-policy-and-pstn-usage-records.md)

