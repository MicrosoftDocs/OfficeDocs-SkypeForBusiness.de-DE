---
title: Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Add-Ins für Chatrooms für beständigen Chat-Server in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: c7243184f273704335dda3c8709de17e767f6b51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992110"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Add-Ins für Chatrooms für beständigen Chat-Server in Skype for Business Server 2015 konfigurieren.
  
Add-Ins werden verwendet, um die in-Room-Erfahrung zu erweitern, indem Sie URLs mit Chatrooms verknüpfen. Diese URLs werden im Bereich für die Erweiterbarkeit von Client Unterhaltungen angezeigt. Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung zeigt, die abfängt, wenn ein Börsenticker in einem Chatroom bereitgestellt wird, und den Aktienverlauf im Bereich "Erweiterbarkeit" anzeigt. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-in, um einen freigegebenen Kontext einzubeziehen, beispielsweise "Top of mindi" oder "Tagesthema".
  
 Bevor Benutzer ein Add-In im Client sehen können, müssen sie es der Liste registrierter Add-Ins hinzufügen und Chatroom-Manager oder -Ersteller müssen es Räumen zuordnen.
  
> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Konfigurieren von Add-Ins für Chatrooms mithilfe der Systemsteuerung

So konfigurieren Sie Add-Ins für Chatrooms mithilfe der Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.
    
    Wählen Sie für die Bereitstellung mehrerer beständiger Chat Server Pools den entsprechenden Pool in der Dropdownliste aus.
    
4. Klicken Sie auf der Seite **Add-In** auf **Neu**.
    
5. Wählen Sie in **Dienst auswählen**den Dienst aus, der dem Server Pool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.
    
6. Gehen Sie unter **Neues Add-In** wie folgt vor:
    
   - Geben Sie im Feld **Name** einen Namen für das neue Add-In ein.
    
   - Geben Sie unter **URL** die URL ein, die mit dem Add-In verknüpft werden soll. URLs müssen das HTTP- oder HTTPS-Protokoll verwenden.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Konfigurieren von Add-Ins mithilfe von Windows PowerShell

Sie können Add-Ins für Chatrooms mithilfe der Windows PowerShell-Cmdlets konfigurieren. Ausführliche Informationen zur Syntax einschließlich aller verfügbaren Parameter finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Erstellt ein neues Add-In  <br/> |
|Set-CsPersistentChatAddin  <br/> |Konfiguriert Einstellungen für ein vorhandenes Add-In  <br/> |
|Get-CsPersistentChatAddin  <br/> |Ruft Informationen über Add-Ins ab  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Entfernt ein Add-In  <br/> |
   
### <a name="create-a-new-add-in"></a>Erstellt ein neues Add-In

Sie können ein neues Add-in mit dem Cmdlet **New-CsPersistentChatAddin** erstellen.
  
Mit dem folgenden Befehl wird beispielsweise ein neues Add-in (mit dem Namen ITPersistentChatAddin) für den Pool ATL-CS-001.contoso.com erstellt. Der URL-Parameter und der Parameter http://atl-cs-001.contoso.com/itchat Wert geben den Speicherort der Webseite des Add-Ins an:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Konfiguriert Einstellungen für ein vorhandenes Add-In

Sie können die Einstellungen für ein vorhandenes Add-in mithilfe des Cmdlets " **Satz-CsPersistentChatAddIn** " konfigurieren. Mit dem folgenden Befehl wird beispielsweise die URL geändert, die dem Add-in ITPersistentChatAddin für beständigen Chat zugewiesen ist. In diesem Fall wird die URL inhttp://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Ruft Informationen über Add-Ins ab

Mithilfe des Cmdlets **Get-CsPersistentChatAddin** können Sie Informationen über Add-Ins abrufen. Beispielsweise liefert der folgende Befehl Informationen über alle Add-Ins für beständigen Chat, die zur Verwendung in der Organisation konfiguriert wurden:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Entfernt ein Add-In

Mithilfe des Cmdlets **Remove-CsPersistentChatAddIn** können Sie ein Add-in entfernen. Beispielsweise entfernt der folgende Befehl das Add-In für beständigen Chat namens „ITChatAddin“ aus dem Pool „atl-cs-001.contoso.com“:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


