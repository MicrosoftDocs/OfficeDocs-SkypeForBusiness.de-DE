---
title: Verwalten von Ankündigungen für den Konferenzbeitritt und -verlassen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ankündigungen für den Konferenzbeitritt und -verlassen in Skype for Business Server verwalten.'
ms.openlocfilehash: f2219fc8d55485a4c34a8730fbec6b556d57b728
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625207"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Verwalten von Ankündigungen für den Konferenzbeitritt und -verlassen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ankündigungen für den Konferenzbeitritt und -abtritt in Skype for Business Server verwalten.
  
Wenn Einwahlbenutzer an einer Konferenz teilnehmen oder diese verlassen, können die Konferenzankündigungsanwendung ihren Eingang oder ihr Verlassen durch Abspielen eines Tons oder Durchsagen ihrer Namen ankündigen. Sie können die Funktionsweise von Ankündigungen ändern, indem Sie Skype for Business Server Verwaltungsshell und das Cmdlet **"Set-CsDialinConferencing"** mit den folgenden Parametern verwenden:
  
- EnableNameRecording – Bestimmt, ob anonyme Teilnehmer aufgefordert werden, ihren Namen vor der Teilnahme an der Konferenz zu notieren. Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer aufgefordert werden, ihren Namen anzugeben, wenn sie an einer Konferenz teilnehmen. (Authentifizierte Teilnehmer notieren ihren Namen nicht, da stattdessen ihr Anzeigename verwendet wird.)
    
- EntryExitAnnouncementsEnabledByDefault – Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert ist "$false", was bedeutet, dass standardmäßig keine Ankündigungen angezeigt werden, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
- EntryExitAnnouncementsType – Gibt die Aktion an, die ausgeführt wird, wenn ein Teilnehmer einer Konferenz beitritt oder diese verlässt, für die Ankündigungen aktiviert sind. Der Standardwert ist "UseNames", was bedeutet, dass es eine Ankündigung ähnlich der folgenden gibt: "Ken Myer ist der Konferenz beigetreten", wenn Ankündigungen aktiviert sind.
    
Sie können diese Einstellungen auf globaler Oder Standortebene konfigurieren. Einstellungen, die auf Standortebene konfiguriert sind, haben Vorrang vor den auf globaler Ebene konfigurierten Einstellungen.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Verhalten bei Der Konferenzbeitritt und -abmeldung

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server Verwaltungsshell: Klicken Sie auf **"Start",** auf **"Alle Programme",** auf **Skype for Business 2015** und dann auf **Skype for Business Server Verwaltungsshell.**
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Dieses Cmdlet ruft Informationen dazu ab, ob Teilnehmer ihren Namen aufzeichnen müssen, wenn sie einer Konferenz beitreten, und wie Skype for Business Server reagiert, wenn Teilnehmer einer Einwahlkonferenz beitreten oder diese verlassen.
    
4. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Im folgenden Beispiel werden die Einstellungen auf Standortebene für Redmond konfiguriert. Ankündigungen sind aktiviert, die Teilnehmer werden jedoch nicht aufgefordert, ihren Namen zu sagen, wenn sie an einer Konferenz teilnehmen. Wenn Teilnehmer eine Konferenz betreten oder verlassen, wird ein Ton wiedergegeben:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Weitere Informationen, einschließlich Syntax und einer vollständigen Liste von Parametern, finden Sie unter ["Set-CsDialInConferencingConfiguration".](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)
