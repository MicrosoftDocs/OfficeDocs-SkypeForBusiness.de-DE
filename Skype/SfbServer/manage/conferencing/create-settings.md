---
title: Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server
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
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Zusammenfassung: Informationen zum Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server.'
ms.openlocfilehash: 862ffc56fd14c446a747a490daa0655e410e01d9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119514"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server erstellen.
  
Sie können Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell erstellen.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Erstellen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste **auf** Konferenzen und dann auf **Besprechungskonfiguration**.
    
4. Klicken Sie **auf der** Seite Besprechungskonfiguration auf **Neu,** und gehen Sie dann wie folgt vor:
    
    - Klicken Sie zum Erstellen einer Richtlinie auf Websiteebene auf **Websitekonfiguration**. Geben Sie **im Suchfeld** Website auswählen den Namen der Website, für die Sie Besprechungs beitreten möchten, ganz oder teilweise ein. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
    - Klicken Sie zum Erstellen einer Richtlinie auf Poolebene auf **Poolkonfiguration**. Geben Sie **im Suchfeld** Dienst auswählen den Namen des Pooldiensts, für den Sie Besprechungs beitreten möchten, ganz oder teilweise ein. Klicken Sie in der resultierenden Liste der Dienste auf den pool, den Sie möchten, und klicken Sie dann auf **OK**.
    
5. Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Lobby**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an die Lobby weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.
    
6. Legen Sie im Abschnitt **Als Referent benennen** fest, wer in der Besprechung als Referent agieren kann:
    
   - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
   - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
   - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.
    
7. Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zuweisen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.
    
8. Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.
    
9. Gehen Sie wie folgt vor, um die an Teilnehmer gesendete Besprechungs-Einladung anzupassen. Beachten Sie, dass die maximale Länge für URLs und benutzerdefinierten Fußzeilentext 1 KB beträgt. Mit Ausnahme **der Hilfe-URL** werden diese nicht in die Besprechung einbezogen, wenn Sie keinen Wert für die Anpassungen angeben. Wenn Sie keine benutzerdefinierte Hilfe-URL angeben, wird die Standard-Hilfe-URL für Skype for Business in der Einladung angezeigt. 
    
   - Geben Sie zum Anpassen des Logos, das in der Besprechungs-Einladung angezeigt wird, unter **Logo-URL** den Speicherort des Logos ein. Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188 x 30 Pixeln sein. 
    
   - Geben Sie zum Anpassen des Hilfetexts, der in der Besprechungs-Einladung angezeigt wird, unter **Hilfe-URL** den Speicherort des Hilfetexts ein.
    
   - Geben Sie zum Anpassen des rechtstexts, der in der Besprechungs-Einladung angezeigt wird, unter **Legal text URL** den Speicherort des Rechtstexts ein.
    
   - Um den Fußzeilentext anzupassen, der in der Besprechungs-Einladung angezeigt wird, geben Sie in Benutzerdefinierter **Fußzeilentext** Text ein.
    
10. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Erstellen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Erstellen von Besprechungskonfigurationseinstellungen **das Cmdlet New-CsMeetingConfiguration.**
  
Mit dem folgenden Befehl wird ein neuer Satz von Besprechungskonfigurationseinstellungen für den Standort "Redmond" erstellt:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Da im vorherigen Befehl keine Parameter (mitser dem obligatorischen Identity-Parameter) angegeben wurden, verwenden die neuen Besprechungskonfigurationseinstellungen die Standardwerte für alle eigenschaften.
  
Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Sammlung von Besprechungskonfigurationseinstellungen zu erstellen, die standardmäßig alle Benutzer einer Besprechung als Presenter zugeben, verwenden Sie einen Befehl wie den folgenden:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Mehrere Eigenschaftswerte können durch Einschleieren mehrerer Parameter festgelegt werden. Der folgende Befehl lässt beispielsweise alle Benutzer zu einer Besprechung als Moderator zu und zwingt außerdem PSTN-Benutzer, in der Lobby zu warten, bis sie formal zur Besprechung zugelassen sind:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
