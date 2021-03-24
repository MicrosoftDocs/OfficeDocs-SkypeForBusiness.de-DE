---
title: (Optional) Definieren von Feiertagssätzen für Reaktionsgruppe in Skype for Business
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
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Erstellen oder Ändern von Feiertagssätzen für Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 3a8173964cf32c148146ffc4c501861b35bf6077
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103681"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a>(Optional) Definieren von Feiertagssätzen für Reaktionsgruppe in Skype for Business
 
Erstellen oder Ändern von Feiertagssätzen für Reaktionsgruppe in Skype for Business Server Enterprise-VoIP.
  
Feiertage sind als Tage definiert, an denen die Reaktionsgruppe geschlossen ist. Geben Sie die Aktion an, die an solchen Tagen ausgeführt werden soll. Ein Feiertagssatz ist eine Sammlung der Feiertage, die eine Reaktionsgruppe betreffen.
  
> [!NOTE]
> Wenn ein Workflow als verwalteter Workflow definiert ist, können alle Benutzer mit der CsResponseGroupManager-Rolle die Feiertage der von ihnen verwalteten Workflows festlegen und bearbeiten. 
  
### <a name="to-create-a-holiday-set"></a>So erstellen Sie einen Feiertagssatz

1. Melden Sie sich als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied einer der vordefinierten Administrativen Rollen an, die die Reaktionsgruppe unterstützen.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie für jeden zu definierenden Feiertag folgenden Befehl aus:
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    Führen Sie zum Erstellen des Feiertagssatzes, der die definierten Feiertage enthalten soll, folgenden Befehl aus:
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    Im folgenden Beispiel wird ein Feiertagssatz mit zwei Feiertagen gezeigt:
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>Siehe auch

[Entwerfen und Erstellen von Reaktionsgruppeworkflows in Skype for Business](designing-and-creating-response-group-workflows.md)

[New-CsRgsHoliday](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-CsRgsHolidaySet](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)