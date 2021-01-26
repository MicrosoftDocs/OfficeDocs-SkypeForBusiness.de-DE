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
description: 'Zusammenfassung: Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server erstellen.'
ms.openlocfilehash: edc498ed3847618b17970fb2270c21fd3f4ec025
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828205"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server erstellen.
  
Sie können Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe der Skype for Business Server-Verwaltungsshell erstellen.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Erstellen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie die Skype for Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen"** und dann auf **"Besprechungskonfiguration".**
    
4. Klicken Sie auf der Seite "Besprechungskonfiguration" auf **"Neu",** und gehen Sie dann wie folgt vor: 
    
    - Klicken Sie auf "Standortkonfiguration", um eine Richtlinie auf **Standortebene zu erstellen.** Geben Sie **im Suchfeld** "Standort auswählen" den Namen der Website ganz oder teilweise ein, für die Sie Einstellungen für den Besprechungsteil nehmen möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
    - Klicken Sie auf "Poolkonfiguration", um eine **Richtlinie auf Poolebene zu erstellen.** Geben Sie **im Suchfeld** "Dienst auswählen" den Namen des Pooldiensts, für den Sie Einstellungen für den Besprechungsteil nehmen möchten, ganz oder teilweise ein. Klicken Sie in der Ergebnisliste der Dienste auf den pool, den Sie verwenden möchten, und klicken Sie dann auf **OK**.
    
5. Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Lobby**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an die Lobby weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.
    
6. Legen Sie im Abschnitt **Als Referent benennen** fest, wer in der Besprechung als Referent agieren kann:
    
   - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
   - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
   - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.
    
7. Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zuweisen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.
    
8. Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.
    
9. Gehen Sie wie folgt vor, um die Besprechungs-Einladung anzupassen, die an die Teilnehmer gesendet wird. Beachten Sie, dass die maximale Länge für URLs und benutzerdefinierten Fußzeilentext 1 KB beträgt. Mit Ausnahme **der Hilfe-URL** werden diese nicht in die Besprechung einbezogen, wenn Sie keinen Wert für die Anpassungen angeben. Wenn Sie keine benutzerdefinierte Hilfe-URL angeben, wird die standardmäßige Hilfe-URL für Skype for Business in der Einladung angezeigt. 
    
   - Um das Logo anzupassen, das in der Besprechungs-Einladung angezeigt wird, geben Sie in der **Logo-URL** den Speicherort des Logos ein. Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188 x 30 Pixeln sein. 
    
   - Um den Hilfetext anzupassen, der in der Besprechungs-Einladung angezeigt wird, geben Sie in der **Hilfe-URL** den Speicherort des Hilfetexts ein.
    
   - Geben Sie zum Anpassen des rechtlichen Texts, der in der Besprechungs-Einladung angezeigt wird, unter **"Legal text URL"** den Speicherort des rechtlichen Texts ein.
    
   - Geben Sie zum Anpassen des Fußzeilentexts, der in der Besprechungs-Einladung angezeigt wird, in benutzerdefinierten **Fußzeilentext** Text ein.
    
10. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Erstellen von Besprechungskonfigurationseinstellungen mithilfe der Skype for Business Server-Verwaltungsshell

Verwenden Sie zum Erstellen von Besprechungskonfigurationseinstellungen das **Cmdlet "New-CsMeetingConfiguration".**
  
Mit dem folgenden Befehl wird ein neuer Satz von Besprechungskonfigurationseinstellungen für den Standort "Redmond" erstellt:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Da im vorherigen Befehl keine Parameter (mit Anderen als dem obligatorischen Parameter "Identity") angegeben wurden, verwenden die neuen Besprechungskonfigurationseinstellungen die Standardwerte für alle Eigenschaften.
  
Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Auflistung von Besprechungskonfigurationseinstellungen zu erstellen, mit der standardmäßig jeder als Moderator einer Besprechung zugestellt werden kann, verwenden Sie einen Befehl wie den folgenden:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Mehrere Eigenschaftswerte können festgelegt werden, indem mehrere Parameter angegeben werden. Der folgende Befehl lässt beispielsweise alle Benutzer zu einer Besprechung als Moderator zu und zwingt pstN-Benutzer, im Wartebereich zu warten, bis sie formell zur Besprechung zugelassen werden:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
  

