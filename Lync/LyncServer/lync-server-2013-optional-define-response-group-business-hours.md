---
title: 'Lync Server 2013: (optional) definieren von Geschäftszeiten für Reaktionsgruppen'
description: 'Lync Server 2013: (optional) definieren von Geschäftszeiten für Reaktionsgruppen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group business hours
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205291(v=OCS.15)
ms:contentKeyID: 48185504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5780ee362ff11fc4b6fe2ccf8f119f35d0bee36
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565771"
---
# <a name="optional-define-response-group-business-hours-in-lync-server-2013"></a>Optional Definieren von Geschäftszeiten für Reaktionsgruppen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

<div>

## <a name="defining-business-hours"></a>Definieren von Geschäftszeiten

Mit der Einstellung der Geschäftszeiten wird definiert, wann der Workflow zur Anrufbeantwortung zur Verfügung steht, und es werden die Aktionen angegeben, die für Anrufe außerhalb der Geschäftszeiten ausgeführt werden sollen. Reaktionsgruppenadministratoren können mit dem **New-CsRgsHoursOfBusiness**-Cmdlet vordefinierte Zeitpläne erstellen, die Sie für eine beliebige Anzahl von Reaktionsgruppen verwenden können.

<div>


> [!TIP]  
> Beim Erstellen oder Ändern eines Workflows können Sie einen benutzerdefinierten Zeitplan angeben, der nur für diesen Workflow gilt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">Create or Modify a Hunt Group Workflow in lync Server 2013</A> oder <A href="lync-server-2013-create-or-modify-an-interactive-workflow.md">erstellen oder Ändern eines interaktiven Workflows in lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Wenn ein Workflow als verwalteter Workflow definiert wird, kann jeder Benutzer, dem die Rolle CsResponseGroupManager zugewiesen ist, benutzerdefinierte Geschäftszeiten für die von ihnen verwalteten Workflows festlegen und ändern.



</div>

<div>


> [!IMPORTANT]  
> Verwenden Sie das 24-Stunden-Format für die Parameter in den folgenden Cmdlets (z. B. 20:00=20 Uhr).



</div>

<div>

## <a name="to-create-a-predefined-business-hours-collection"></a>So erstellen Sie eine vordefinierte Geschäftszeitenauflistung

1.  Melden Sie sich als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie für jeden einzelnen Stundenbereich, den Sie definieren möchten, folgenden Befehl aus:
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    Führen Sie zum Erstellen der Geschäftszeitenauflistung, welche die definierten Bereiche verwendet, folgenden Befehl aus:
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    Im folgenden Beispiel werden für Werktage die Geschäftszeiten von 9:00 Uhr bis 17:00 Uhr, für Samstage von 8:00 Uhr bis 10:00 Uhr und von 14:00 Uhr bis 18:00 Uhr und für Sonntage keine Geschäftszeiten festgelegt:
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern eines Sammelanschluss-Workflows in lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Erstellen oder Ändern eines interaktiven Workflows in lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoursOfBusiness)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

