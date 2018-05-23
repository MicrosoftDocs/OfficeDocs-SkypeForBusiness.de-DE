---
title: (Optional) Definieren von Feiertagssätzen für Reaktionsgruppen in Skype for Business 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Erstellen oder Ändern von Reaktionsgruppe feiertagssätzen in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 267e57e47b45d30889ba5deb992b4ecf951ab593
ms.sourcegitcommit: 926416cb538abeb2d601298346de97d697ea1a65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>(Optional) Definieren von Feiertagssätzen für Reaktionsgruppen in Skype for Business 2015
 
Erstellen oder Ändern von Reaktionsgruppe feiertagssätzen in Skype für Business Server Enterprise-VoIP.
  
Feiertage sind als Tage definiert, an denen die Reaktionsgruppe geschlossen ist. Geben Sie die Aktion an, die an solchen Tagen ausgeführt werden soll. Ein Feiertagssatz ist eine Sammlung der Feiertage, die eine Reaktionsgruppe betreffen.
  
> [!NOTE]
> Wenn ein Workflow als verwalteter Workflow definiert ist, können alle Benutzer mit der CsResponseGroupManager-Rolle die Feiertage der von ihnen verwalteten Workflows festlegen und bearbeiten. 
  
### <a name="to-create-a-holiday-set"></a>So erstellen Sie einen Feiertagssatz

1. Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied einer der vordefinierten Administratorrollen an, die Reaktionsgruppen unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl für jeden Feiertag aus, den Sie definieren möchten:
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Führen Sie den folgenden Befehl aus, um einen Feiertagssatz mit den von Ihnen definierten Feiertagen zu erstellen:
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    Das folgende Beispiel enthält einen Feiertagssatz mit zwei Feiertagen:
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/2/2013 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2013 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Siehe auch

[Entwerfen und Erstellen von Antwort Gruppe Workflows in Skype für Business 2015](designing-and-creating-response-group-workflows.md)

[Mit New-CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[Mit New-CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
