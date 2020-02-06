---
title: Verwalten von Teilnahme-und Abwesenheits Ankündigungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server Konferenz Anmeldungen verwalten und Ankündigungen hinterlassen.'
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818546"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Verwalten von Teilnahme-und Abwesenheits Ankündigungen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie in Skype for Business Server Konferenzteilnahme verwalten und Ankündigungen hinterlassen.
  
Wenn Einwahlbenutzer an einer Konferenz teilnehmen oder Sie verlassen, kann die APP für Konferenz Ankündigungen deren ein-oder Ausstieg ankündigen, indem Sie einen Ton abspielen oder ihre Namen sagen. Sie können die Funktionsweise von Ankündigungen mithilfe der Skype for Business Server-Verwaltungsshell und des Cmdlets " **Satz-CsDialinConferencing** " mit den folgenden Parametern ändern:
  
- EnableNameRecording – Legt fest, ob anonyme Teilnehmer vor dem Beitreten einer Konferenz dazu aufgefordert werden, ihren Namen aufzuzeichnen. Der Standardwert lautet „$true“. Dies bedeutet, dass anonyme Teilnehmer aufgefordert werden, ihren Namen zu sagen, wenn sie einer Konferenz beitreten möchten. (Authentifizierte Teilnehmer müssen ihren Namen nicht aufzeichnen, da stattdessen ihr Anzeigename verwendet wird.)
    
- EntryExitAnnouncementsEnabledByDefault – Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert lautet „$false“. Dies bedeutet, dass standardmäßig keine Ankündigung erfolgt, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
- EntryExitAnnouncementsType – Gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz, für die die Ankündigungsfunktion aktiviert ist, beitritt oder diese verlässt. Der Standardwert lautet „UseNames“. Dies bedeutet, dass eine Ankündigung ähnlich dieser erfolgt: „Jonas Baar ist der Konferenz beigetreten.“
    
Sie können diese Einstellungen auf globaler oder Standortebene konfigurieren. Einstellungen auf Standortebene haben Vorrang vor globalen Einstellungen.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Verhalten von Ankündigungen beim Beitreten oder Verlassen einer Konferenz

1. Melden Sie sich beim Computer als Mitglied der Gruppe  RTCUniversalServerAdmins  oder als Benutzer mit der Rolle  Cs-ServerAdministrator  oder  CsAdministrator  an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Skype for Business 2015** und klicken Sie anschließend auf **Skype for Business Server-Verwaltungsshell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Mit diesem Cmdlet werden Informationen darüber abgerufen, ob Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen und wie Skype for Business Server antwortet, wenn Teilnehmer an einer Einwahlkonferenz teilnehmen oder diese hinterlassen.
    
4. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Im folgenden Beispiel sind die Einstellungen auf Standortebene für Redmond konfiguriert. Die Ankündigungsfunktion ist aktiviert, Teilnehmer müssen jedoch nicht ihren Namen sagen, wenn sie einer Konferenz beitreten. Wenn Teilnehmer einer Konferenz beitreten oder diese verlassen, wird ein Ton abgespielt.
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Weitere Informationen, einschließlich Syntax und einer vollständigen Liste der Parameter, finden Sie unter [CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

