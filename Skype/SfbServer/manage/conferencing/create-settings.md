---
title: Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Zusammenfassung: Informationen zum Erstellen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: 2d3bde2c856c85e0795f2e1d43fbb5cf705c7024
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server-2015"></a>Erstellen von Besprechungskonfigurationseinstellungen in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen zum Erstellen von besprechungskonfigurationseinstellungen in Skype für Business Server 2015.
  
Sie können erstellen besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung oder mithilfe von Skype für Business Server-Verwaltungsshell.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Erstellen von besprechungskonfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung

1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2.  Öffnen von Skype Business Server-Systemsteuerung.
    
3. Klicken Sie in der linken Navigationsleiste auf **Konferenzen** und anschließend auf **Besprechungskonfiguration**.
    
4. Klicken Sie auf der Seite **Besprechungskonfiguration** auf **Neu** und führen Sie eine der folgenden Aktionen aus:
    
    - Klicken Sie auf **Standortkonfiguration**, um eine Richtlinie auf Standortebene zu erstellen. Geben Sie im Suchfeld **Standort auswählen** einen Teil oder den gesamten Namen des Standorts ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Standorte auf den gewünschten Standort und klicken Sie auf **OK**.
    
    - Klicken Sie auf **Poolkonfiguration**, um eine Richtlinie auf Poolebene zu erstellen. Geben Sie im Suchfeld **Dienst auswählen** einen Teil oder den gesamten Namen des Pooldienstes ein, für den Sie Einstellungen für den Besprechungsbeitritt definieren möchten. Klicken Sie in der resultierenden Liste der Dienste auf den gewünschten Pool und klicken Sie auf **OK**.
    
5. Deaktivieren Sie das Kontrollkästchen **PSTN-Anrufer umgehen Wartebereich**, um Teilnehmer, die sich über das Festnetz einwählen, zunächst an den Wartebereich weiterzuleiten. In der Standardeinstellung gelangen Anrufer, die sich über das Festnetz einwählen, direkt zur Besprechung.
    
6. Legen Sie im Abschnitt **Als Referenten festlegen** fest, wer in der Besprechung als Referent agieren kann:
    
   - Klicken Sie auf **Keiner**, um nur dem Organisator die Rolle des Referenten zuzuweisen.
    
   - Klicken Sie auf **Unternehmen**, um nur denjenigen Teilnehmern die Funktion des Referenten zu ermöglichen, die Mitglieder Ihrer Organisation sind. Dies ist die Standardeinstellung.
    
   - Klicken Sie auf **Jeder**, um allen Teilnehmern das Agieren als Referent zu ermöglichen.
    
7. Wenn der Organisator bei der Planung einer Besprechung einen Konferenztyp auswählen soll, deaktivieren Sie das Kontrollkästchen **Konferenztyp standardmäßig zugewiesen**. In der Standardeinstellung wird der Konferenztyp automatisch zugewiesen.
    
8. Wenn Sie verhindern möchten, dass anonyme (nicht authentifizierte) Benutzer automatisch zugelassen werden, deaktivieren Sie das Kontrollkästchen **Anonyme Benutzer standardmäßig zulassen**. In der Standardeinstellung werden anonyme Benutzer automatisch für Besprechungen zugelassen.
    
9. Führen Sie die folgenden Schritte aus, um die Besprechungseinladung anzupassen, die an die Teilnehmer gesendet wird. Beachten Sie, dass für URLs und den benutzerdefinierten Fußzeilentext eine maximale Größe von 1 KB gilt. Wenn Sie, mit Ausnahme von **Hilfe-URL**, keinen Wert für die Anpassungen angeben, werden sie nicht in die Besprechung aufgenommen. Wenn Sie eine benutzerdefinierte Hilfe-URL nicht verwenden, wird die Standard-URL für die Hilfe für Skype für Unternehmen einladen angezeigt. 
    
   - Zum Anpassen des Logos, das in der Besprechungseinladung angezeigt wird, geben Sie in **Logo-URL** den Speicherort des Logos ein. Das Logo muss ein GIF- oder JPG-Bild mit einer Größe von 188 x 30 Pixel sein. 
    
   - Zum Anpassen des Hilfetexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Hilfe-URL** den Speicherort des Hilfetexts ein.
    
   - Zum Anpassen der rechtlichen Hinweise, die in der Besprechungseinladung angezeigt werden, geben Sie in **URL zu rechtlichen Hinweisen** den Speicherort der rechtlichen Hinweise ein.
    
   - Zum Anpassen des Fußzeilentexts, der in der Besprechungseinladung angezeigt wird, geben Sie in **Benutzerdefinierter Fußzeilentext** Text ein.
    
10. Klicken Sie auf **Commit ausführen**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Erstellen von besprechungskonfigurationseinstellungen mithilfe von Skype für Business Server-Verwaltungsshell

Verwenden Sie das **New-CsMeetingConfiguration**-Cmdlet, um Besprechungskonfigurationseinstellungen zu erstellen.
  
Mit dem folgenden Befehl wird ein neuer Satz von Besprechungskonfigurationseinstellungen für den Standort „Redmond“ erstellt:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in den neuen Besprechungskonfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet.
  
Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von Besprechungskonfigurationseinstellungen erstellen möchten, die standardmäßig jeden als Referent zu einer Besprechung zulassen, verwenden Sie den folgenden Befehl:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Mehrere Eigenschaftswerte können eingestellt werden, indem Sie mehrere Parameter angeben. Beispielsweise wird mit dem folgenden Befehl jeder als Referent zu einer Besprechung zugelassen und außerdem werden PSTN-Benutzer gezwungen, im Wartebereich zu warten, bis sie formell zur Besprechung zugelassen werden:
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Weitere Informationen sowie eine vollständige Liste der Parameter finden Sie unter [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
  

