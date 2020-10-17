---
title: 'Lync Server 2013: (optional) definieren von Feiertagssätzen für Reaktionsgruppen'
description: 'Lync Server 2013: (optional) definieren von Feiertagssätzen für Reaktionsgruppen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ba735cc62efb9d5553c8bd6aad1aa9484f70f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565761"
---
# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="035bc-103">Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="035bc-103">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="035bc-104">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="035bc-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="035bc-p101">Feiertage sind als Tage definiert, an denen die Reaktionsgruppe geschlossen ist. Geben Sie die Aktion an, die an solchen Tagen ausgeführt werden soll. Ein Feiertagssatz ist eine Sammlung der Feiertage, die eine Reaktionsgruppe betreffen.</span><span class="sxs-lookup"><span data-stu-id="035bc-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="035bc-107">Wenn ein Workflow als verwalteter Workflow definiert ist, können alle Benutzer mit der CsResponseGroupManager-Rolle die Feiertage der von ihnen verwalteten Workflows festlegen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="035bc-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="035bc-108">So erstellen Sie einen Feiertagssatz</span><span class="sxs-lookup"><span data-stu-id="035bc-108">To create a holiday set</span></span>

1.  <span data-ttu-id="035bc-109">Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="035bc-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="035bc-110">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="035bc-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="035bc-111">Führen Sie für jeden zu definierenden Feiertag folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="035bc-111">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="035bc-112">Führen Sie zum Erstellen des Feiertagssatzes, der die definierten Feiertage enthalten soll, folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="035bc-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="035bc-113">Im folgenden Beispiel wird ein Feiertagssatz mit zwei Feiertagen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="035bc-113">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="035bc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="035bc-114">See Also</span></span>


[<span data-ttu-id="035bc-115">Erstellen oder Ändern eines Sammelanschluss-Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="035bc-115">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="035bc-116">Erstellen oder Ändern eines interaktiven Workflows in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="035bc-116">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="035bc-117">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="035bc-117">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="035bc-118">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="035bc-118">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

