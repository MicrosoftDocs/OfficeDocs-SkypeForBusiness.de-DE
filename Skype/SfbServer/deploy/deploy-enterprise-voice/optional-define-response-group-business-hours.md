---
title: (Optional) Reaktionsgruppe Definieren von Geschäftszeiten in Skype für Unternehmen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Erstellen oder Ändern von Reaktionsgruppen Geschäftszeiten in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: ba10f513495d21c7f94397350c1227cb77fe588b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884677"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="ca145-103">(Optional) Reaktionsgruppe Definieren von Geschäftszeiten in Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ca145-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="ca145-104">Erstellen oder Ändern von Reaktionsgruppen Geschäftszeiten in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="ca145-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="ca145-105">Definieren von Geschäftszeiten</span><span class="sxs-lookup"><span data-stu-id="ca145-105">Defining Business Hours</span></span>

<span data-ttu-id="ca145-106">Mit der Einstellung der Geschäftszeiten wird definiert, wann der Workflow zur Anrufbeantwortung zur Verfügung steht und es werden die Aktionen angegeben, die für Anrufe außerhalb der Geschäftszeiten ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ca145-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="ca145-107">Reaktionsgruppenadministratoren können mit dem **New-CsRgsHoursOfBusiness**-Cmdlet vordefinierte Zeitpläne erstellen, die Sie für eine beliebige Anzahl von Reaktionsgruppen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ca145-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="ca145-108">Beim Erstellen oder Ändern eines Workflows können Sie einen benutzerdefinierten Zeitplan angeben, der nur für diesen Workflow gilt.</span><span class="sxs-lookup"><span data-stu-id="ca145-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="ca145-109">Weitere Informationen hierzu finden Sie unter [Entwerfen und Erstellen von Antwort Gruppe Workflows in Skype für Unternehmen](designing-and-creating-response-group-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="ca145-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ca145-110">Wenn ein Workflow als verwalteter Workflow definiert wird, kann jeder Benutzer, dem die Rolle CsResponseGroupManager zugewiesen ist, benutzerdefinierte Geschäftszeiten für die von ihnen verwalteten Workflows festlegen und ändern.</span><span class="sxs-lookup"><span data-stu-id="ca145-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ca145-111">Verwenden Sie das 24-Stunden-Format für die Parameter in den folgenden Cmdlets (z. B. 20:00=8:00 Uhr abends).</span><span class="sxs-lookup"><span data-stu-id="ca145-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="ca145-112">So erstellen Sie eine vordefinierte Geschäftszeitenauflistung</span><span class="sxs-lookup"><span data-stu-id="ca145-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="ca145-113">Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ca145-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="ca145-114">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="ca145-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ca145-115">Führen Sie für jeden einzelnen Stundenbereich, den Sie definieren möchten, folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ca145-115">For each unique range of hours you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="ca145-116">Führen Sie zum Erstellen der Geschäftszeitenauflistung, welche die definierten Bereiche verwendet, folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ca145-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="ca145-p103">Im folgenden Beispiel werden für Werktage die Geschäftszeiten von 9:00 Uhr bis 17:00 Uhr, für Samstage von 8:00 Uhr bis 10:00 Uhr und von 14:00 Uhr bis 18:00 Uhr und für Sonntage keine Geschäftszeiten festgelegt:</span><span class="sxs-lookup"><span data-stu-id="ca145-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="ca145-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca145-124">See also</span></span>

[<span data-ttu-id="ca145-125">Mit New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="ca145-125">New-CsRgsTimeRange</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="ca145-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="ca145-126">New-CsRgsHoursOfBusiness</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
