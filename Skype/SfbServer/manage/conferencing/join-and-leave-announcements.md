---
title: Verwalten von Ankündigungen zum Beitreten und Verlassen von Konferenzkonferenzen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ankündigungen zum Beitreten und Hinterlassen von Konferenzansagen in Skype for Business Server verwalten.'
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119454"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Verwalten von Ankündigungen zum Beitreten und Verlassen von Konferenzkonferenzen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ankündigungen zum Beitreten und Hinterlassen von Konferenzansagen in Skype for Business Server verwalten.
  
Wenn Einwahlbenutzer an einer Konferenz teilnehmen oder diese verlassen, kann die Konferenzansageanwendung ihren Ein- oder Ausstieg durch Abspielen eines Tons oder Durchsagen ihrer Namen ankündigen. Sie können die Funktionsweise von Ankündigungen mithilfe der Skype for Business Server-Verwaltungsshell und des **Cmdlets Set-CsDialinConferencing** mit den folgenden Parametern ändern:
  
- EnableNameRecording – Bestimmt, ob anonyme Teilnehmer aufgefordert werden, ihren Namen vor der Teilnahme an der Konferenz zu notieren. Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer aufgefordert werden, ihren Namen beim Beitritt zu einer Konferenz zu nennen. (Authentifizierte Teilnehmer zeichnen ihren Namen nicht auf, da stattdessen der Anzeigename verwendet wird.)
    
- EntryExitAnnouncementsEnabledByDefault – Gibt an, ob Ankündigungen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert ist "$false", was bedeutet, dass standardmäßig keine Ankündigungen angezeigt werden, wenn Teilnehmer an einer Konferenz teilnehmen oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
- EntryExitAnnouncementsType – Gibt die Aktion an, die bei jedem Beitritt oder Verlässt einer Konferenz, für die Ankündigungen aktiviert sind, ergriffen wird. Der Standardwert ist "UseNames", was bedeutet, dass es eine Ansage wie die folgende gibt: "Ken Myer ist der Konferenz beigetreten", wenn Ankündigungen aktiviert sind.
    
Sie können diese Einstellungen auf globaler Ebene oder auf Standortbereich konfigurieren. Auf Standortbereich konfigurierte Einstellungen haben Vorrang vor auf globaler Ebene konfigurierten Einstellungen.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Ankündigungsverhalten für die Konferenzankündigung und -verlassen

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start,** klicken Sie auf **Alle Programme,** **klicken Sie auf Skype for Business 2015,** und klicken Sie dann auf **Skype for Business Server Management Shell**.
    
3. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

Dieses Cmdlet ruft Informationen dazu ab, ob Teilnehmer ihren Namen bei der Teilnahme an einer Konferenz aufzeichnen müssen und wie Skype for Business Server reagiert, wenn Teilnehmer an einer Einwahlkonferenz teilnehmen oder diese verlassen.
    
4. Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

Im folgenden Beispiel werden Einstellungen auf Standortbereich für Redmond konfiguriert. Ankündigungen sind aktiviert, die Teilnehmer werden jedoch nicht aufgefordert, ihren Namen zu nennen, wenn sie an einer Konferenz teilnehmen. Wenn Teilnehmer eine Konferenz betreten oder verlassen, wird ein Ton gespielt:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Weitere Informationen, einschließlich Syntax und einer vollständigen Liste von Parametern, finden Sie unter [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
