---
title: Verwalten Sie der Konferenz teilnehmen und lassen Sie Ansagen im Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Zusammenfassung: Informationen Sie zum Verwalten der Konferenz teilnehmen und Ansagen im Skype für Business Server belassen.'
ms.openlocfilehash: ace07fdc3325d97e443297265892e7bcc4bce562
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919521"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Verwalten Sie der Konferenz teilnehmen und lassen Sie Ansagen im Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Verwalten der Konferenz teilnehmen und Ansagen im Skype für Business Server belassen.
  
Wenn Einwahlbenutzer beitreten oder diese verlassen einer Konferenz, kann die Konferenzankündigungsanwendung Anwendung announce ihre Eingangskriterien oder durch einen Ton wiedergegeben oder ihre Namen sagen beenden. Sie können die Funktionsweise von Ansagen mithilfe von Skype für Business Server-Verwaltungsshell und das Cmdlet **Set-CsDialinConferencing** mit den folgenden Parametern ändern:
  
- EnableNameRecording – Legt fest, ob anonyme Teilnehmer vor dem Beitreten einer Konferenz dazu aufgefordert werden, ihren Namen aufzuzeichnen. Der Standardwert lautet „$true“. Dies bedeutet, dass anonyme Teilnehmer aufgefordert werden, ihren Namen zu sagen, wenn sie einer Konferenz beitreten möchten. (Authentifizierte Teilnehmer müssen ihren Namen nicht aufzeichnen, da stattdessen ihr Anzeigename verwendet wird.)
    
- EntryExitAnnouncementsEnabledByDefault – Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert lautet „$false“. Dies bedeutet, dass standardmäßig keine Ankündigung erfolgt, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
- EntryExitAnnouncementsType – Gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz, für die die Ankündigungsfunktion aktiviert ist, beitritt oder diese verlässt. Der Standardwert lautet „UseNames“. Dies bedeutet, dass eine Ankündigung ähnlich dieser erfolgt: „Jonas Baar ist der Konferenz beigetreten.“
    
Sie können diese Einstellungen auf globaler oder Standortebene konfigurieren. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Verhalten von Ankündigungen beim Beitreten oder Verlassen einer Konferenz

1. Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

Dieses Cmdlet Ruft Informationen dazu, ob Teilnehmer ihren Namen aufzeichnen, wenn die Teilnahme an einer Konferenz erforderlich sind und wie Skype für Business Server reagiert, wenn die Teilnehmer beitreten oder diese verlassen einer Konferenz einwählen.
    
4. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Im folgenden Beispiel sind die Einstellungen auf Standortebene für Redmond konfiguriert. Die Ankündigungsfunktion ist aktiviert, Teilnehmer müssen jedoch nicht ihren Namen sagen, wenn sie einer Konferenz beitreten. Wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, wird ein Ton abgespielt.
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Weitere Informationen zu Syntax und eine vollständige Liste der Parameter, einschließlich finden Sie unter [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

