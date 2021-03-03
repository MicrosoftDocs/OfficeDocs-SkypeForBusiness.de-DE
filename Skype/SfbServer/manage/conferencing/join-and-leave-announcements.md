---
title: Verwalten von Ankündigungen zum Beitreten und Verlassen einer Konferenz in Skype for Business Server
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ankündigungen zum Beitreten und Verlassen von Konferenzkonferenzen in Skype for Business Server verwalten.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828105"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Verwalten von Ankündigungen zum Beitreten und Verlassen einer Konferenz in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ankündigungen zum Beitreten und Verlassen von Konferenzkonferenzen in Skype for Business Server verwalten.
  
Wenn Einwahlbenutzer einer Konferenz beitreten oder diese verlassen, kann die Konferenzankündigungsanwendung ihren Ein- oder Ausstieg ankündigen, indem sie einen Ton angibt oder ihren Namen sagt. Sie können die Funktionsweise von Ansagen ändern, indem Sie die Skype for Business Server-Verwaltungsshell und das **Cmdlet "Set-CsDialinConferencing"** mit den folgenden Parametern verwenden:
  
- EnableNameRecording – Bestimmt, ob anonyme Teilnehmer aufgefordert werden, ihren Namen vor dem Betreten der Konferenz zu notieren. Der Standardwert ist "$true", was bedeutet, dass anonyme Teilnehmer beim Beitreten zu einer Konferenz aufgefordert werden, ihren Namen zu benennen. (Authentifizierte Teilnehmer zeichnen ihren Namen nicht auf, da stattdessen der Anzeigename verwendet wird.)
    
- EntryExitAnnouncementsEnabledByDefault – Gibt an, ob Ansagen standardmäßig aktiviert oder deaktiviert sind. Der Standardwert ist "$false", was bedeutet, dass standardmäßig keine Ankündigungen angezeigt werden, wenn Teilnehmer einer Konferenz beitreten oder diese verlassen. Der Besprechungsorganisator kann diese Einstellung beim Planen einer Besprechung außer Kraft setzen.
    
- EntryExitAnnouncementsType – Gibt die Aktion an, die jedes Mal, wenn ein Teilnehmer einer Konferenz beitritt oder diese verlässt, für die Ankündigungen aktiviert sind, ausgelöst wird. Der Standardwert ist "UseNames", was bedeutet, dass es eine Ansage wie die folgende gibt: "Ken Myer ist der Konferenz beigetreten", wenn Ankündigungen aktiviert sind.
    
Sie können diese Einstellungen auf globaler ebene oder auf Standortbereich konfigurieren. Auf Standortbereich konfigurierte Einstellungen haben Vorrang vor globalen Einstellungen.
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>So ändern Sie das Ankündigungsverhalten für den Konferenz beitreten und verlassen

1. Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle Cs-ServerAdministrator oder CsAdministrator an.
    
2. Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **"Start",**"Alle **Programme",** **"Skype for Business 2015"** und dann auf **"Skype for Business Server-Verwaltungsshell".**
    
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

Im folgenden Beispiel werden einstellungen auf Standortbereich für Redmond konfiguriert. Ankündigungen sind aktiviert, aber teilnehmer werden nicht aufgefordert, ihren Namen zu sagen, wenn sie an einer Konferenz teilnehmen. Wenn Teilnehmer eine Konferenz betreten oder verlassen, wird ein Ton abgespielt:
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

Weitere Informationen, einschließlich Syntax und einer vollständigen Liste von Parametern, finden Sie unter [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).
  

