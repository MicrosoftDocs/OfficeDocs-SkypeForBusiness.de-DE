---
title: Optional Definieren von Feiertagssätzen für Reaktionsgruppen in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Sie können in Skype for Business Server Enterprise-VoIP Gruppen-Feiertagssätze erstellen oder ändern.
ms.openlocfilehash: 5d38814a8e4e9e50634b6d63b1db4c8230c496ea
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767318"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="b9d07-103">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b9d07-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="b9d07-104">Sie können in Skype for Business Server Enterprise-VoIP Gruppen-Feiertagssätze erstellen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="b9d07-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b9d07-p101">Feiertage sind als Tage definiert, an denen die Reaktionsgruppe geschlossen ist. Geben Sie die Aktion an, die an solchen Tagen ausgeführt werden soll. Ein Feiertagssatz ist eine Sammlung der Feiertage, die eine Reaktionsgruppe betreffen.</span><span class="sxs-lookup"><span data-stu-id="b9d07-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9d07-107">Wenn ein Workflow als verwalteter Workflow definiert ist, können alle Benutzer mit der CsResponseGroupManager-Rolle die Feiertage der von ihnen verwalteten Workflows festlegen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="b9d07-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="b9d07-108">So erstellen Sie einen Feiertagssatz</span><span class="sxs-lookup"><span data-stu-id="b9d07-108">To create a holiday set</span></span>

1. <span data-ttu-id="b9d07-109">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b9d07-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="b9d07-110">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b9d07-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b9d07-111">Führen Sie den folgenden Befehl für jeden Feiertag aus, den Sie definieren möchten:</span><span class="sxs-lookup"><span data-stu-id="b9d07-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="b9d07-112">Führen Sie den folgenden Befehl aus, um einen Feiertagssatz mit den von Ihnen definierten Feiertagen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="b9d07-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="b9d07-113">Das folgende Beispiel enthält einen Feiertagssatz mit zwei Feiertagen:</span><span class="sxs-lookup"><span data-stu-id="b9d07-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="b9d07-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9d07-114">See also</span></span>

[<span data-ttu-id="b9d07-115">Entwerfen und Erstellen von Workflows für die Reaktionsgruppe in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b9d07-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="b9d07-116">Neu – CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="b9d07-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="b9d07-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="b9d07-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
