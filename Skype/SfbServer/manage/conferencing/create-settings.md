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
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Zusammenfassung: Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server erstellen.'
ms.openlocfilehash: ad1f4fabf172fa5ff693a91e7994916487c322e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595567"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Besprechungskonfigurationseinstellungen in Skype for Business Server erstellen.
  
Sie können Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung oder mithilfe Skype for Business Server Verwaltungsshell erstellen.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Erstellen von Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen Sie Skype for Business Server Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Konferenzen",** und klicken Sie dann auf **"Besprechungskonfiguration".**
    
4. Klicken Sie auf der Seite **"Besprechungskonfiguration"** auf **"Neu"** und führen Sie dann eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **"Standortkonfiguration",** um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Feld **"Websitesuche auswählen"** den Namen der Website, für die Sie Einstellungen für den Besprechungsbeitritt definieren möchten, ganz oder teilweise ein. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort, und klicken Sie auf **OK**.
    
    - Klicken Sie auf **"Poolkonfiguration",** um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **"Dienst auswählen"** den Namen des Pooldiensts, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten, ganz oder teilweise ein. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool, und klicken Sie dann auf **OK.**
    
5. Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Lobby**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an die Lobby weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.
    
6. Legen Sie im Abschnitt **Als Referent benennen** fest, wer in der Besprechung als Referent agieren kann:
    
   - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
   - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
   - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.
    
7. Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zuweisen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.
    
8. Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.
    
9. Gehen Sie folgendermaßen vor, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird. Beachten Sie, dass die maximale Länge für URLs und benutzerdefinierten Fußzeilentext 1 KB beträgt. Mit Ausnahme der **Hilfe-URL** werden sie nicht in die Besprechung einbezogen, wenn Sie keinen Wert für die Anpassungen angeben. Wenn Sie keine benutzerdefinierte Hilfe-URL einschließen, wird die Standardmäßige Hilfe-URL für Skype for Business in der Einladung angezeigt. 
    
   - Um das Logo anzupassen, das in der Besprechungseinladung angezeigt wird, geben Sie in der **Logo-URL** den Speicherort des Logos ein. Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188 x 30 Pixeln sein. 
    
   - Um den Hilfetext anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie in der **Hilfe-URL** den Speicherort des Hilfetexts ein.
    
   - Um den rechtlichen Text anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie in der URL des **Rechtstexts** den Speicherort des Rechtstexts ein.
    
   - Um den Fußzeilentext anzupassen, der in der Besprechungseinladung angezeigt wird, geben Sie in **benutzerdefiniertem Fußzeilentext** Text ein.
    
10. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Erstellen von Besprechungskonfigurationseinstellungen mithilfe Skype for Business Server Verwaltungsshell

Verwenden Sie zum Erstellen von Besprechungskonfigurationseinstellungen das Cmdlet **"New-CsMeetingConfiguration".**
  
Der folgende Befehl erstellt einen neuen Satz von Besprechungskonfigurationseinstellungen für den Standort Redmond:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Da im vorherigen Befehl keine parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, verwenden die neuen Besprechungskonfigurationseinstellungen die Standardwerte für alle eigenschaften.
  
Zum Erstellen von Einstellungen, die verschiedene Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und den Parameterwert an. Um beispielsweise eine Sammlung von Besprechungskonfigurationseinstellungen zu erstellen, die standardmäßig alle Personen zu einer Besprechung als Referenten zulassen, verwenden Sie einen Befehl wie den folgenden:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Mehrere Eigenschaftswerte können festgelegt werden, indem mehrere Parameter eingeschlossen werden. Der folgende Befehl lässt beispielsweise jeden zu einer Besprechung als Referent zu und erzwingt außerdem, dass PSTN-Benutzer im Wartebereich warten, bis sie formell zur Besprechung zugelassen werden:
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Weitere Informationen, einschließlich einer vollständigen Liste von Parametern, finden Sie unter [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
