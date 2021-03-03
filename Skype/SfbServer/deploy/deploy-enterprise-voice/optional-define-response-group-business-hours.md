---
title: (Optional) Definieren von Geschäftszeiten für Reaktionsgruppe in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Erstellen oder ändern Sie die Geschäftszeiten für Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: dcd2f7174a75eb68ef8d35759a1e454ede976bde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830995"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>(Optional) Definieren von Geschäftszeiten für Reaktionsgruppe in Skype for Business 
 
Erstellen oder ändern Sie die Geschäftszeiten für Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
  
## <a name="defining-business-hours"></a>Definieren von Geschäftszeiten

Mit der Einstellung der Geschäftszeiten wird definiert, wann der Workflow zur Anrufbeantwortung zur Verfügung steht, und es werden die Aktionen angegeben, die für Anrufe außerhalb der Geschäftszeiten ausgeführt werden sollen. Reaktionsgruppenadministratoren können mit dem **New-CsRgsHoursOfBusiness**-Cmdlet vordefinierte Zeitpläne erstellen, die Sie für eine beliebige Anzahl von Reaktionsgruppen verwenden können.
  
> [!TIP]
> Beim Erstellen oder Ändern eines Workflows können Sie einen benutzerdefinierten Zeitplan angeben, der nur für diesen Workflow gilt. Weitere Informationen finden Sie unter [Entwerfen und Erstellen von Reaktionsgruppe Workflows in Skype for Business](designing-and-creating-response-group-workflows.md). 
  
> [!NOTE]
> Wenn ein Workflow als verwalteter Workflow definiert wird, kann jeder Benutzer, dem die Rolle CsResponseGroupManager zugewiesen ist, benutzerdefinierte Geschäftszeiten für die von ihnen verwalteten Workflows festlegen und ändern. 
  
> [!IMPORTANT]
> Verwenden Sie das 24-Stunden-Format für die Parameter in den folgenden Cmdlets (z. B. 20:00=20 Uhr). 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>So erstellen Sie eine vordefinierte Geschäftszeitenauflistung

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppe unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
3. Führen Sie für jeden einzelnen Stundenbereich, den Sie definieren möchten, folgenden Befehl aus:
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    Führen Sie zum Erstellen der Geschäftszeitenauflistung, welche die definierten Bereiche verwendet, folgenden Befehl aus:
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    Im folgenden Beispiel werden für Werktage die Geschäftszeiten von 9:00 Uhr bis 17:00 Uhr, für Samstage von 8:00 Uhr bis 10:00 Uhr und von 14:00 Uhr bis 18:00 Uhr und für Sonntage keine Geschäftszeiten festgelegt:
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>Siehe auch

[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
