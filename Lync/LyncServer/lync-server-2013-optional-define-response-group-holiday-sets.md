---
title: 'Lync Server 2013: (optional) definieren von Reaktionsgruppen-Feiertagssätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ca58b3e2c17ea70e9af7a9eba48df8582b1485c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a>Optional Definieren von Feiertagssätzen für Reaktionsgruppen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Feiertage sind als Tage definiert, an denen die Reaktionsgruppe geschlossen ist. Geben Sie die Aktion an, die an solchen Tagen ausgeführt werden soll. Ein Feiertagssatz ist eine Sammlung der Feiertage, die eine Reaktionsgruppe betreffen.

<div>


> [!NOTE]  
> Wenn ein Workflow als verwalteter Workflow definiert ist, können alle Benutzer mit der CsResponseGroupManager-Rolle die Feiertage der von ihnen verwalteten Workflows festlegen und bearbeiten.



</div>

<div>

## <a name="to-create-a-holiday-set"></a>So erstellen Sie einen Feiertagssatz

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl für jeden Feiertag aus, den Sie definieren möchten:
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    Führen Sie den folgenden Befehl aus, um einen Feiertagssatz mit den von Ihnen definierten Feiertagen zu erstellen:
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    Das folgende Beispiel enthält einen Feiertagssatz mit zwei Feiertagen:
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern eines Sammel Ansuchen-Workflows in lync Server 2013](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[Erstellen oder Ändern eines interaktiven Workflows in Lync Server 2013](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[Neu – CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

