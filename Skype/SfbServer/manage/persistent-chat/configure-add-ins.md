---
title: Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von Add-Ins für Chatrooms Persistent Chat Server in Skype für Business Server 2015.'
ms.openlocfilehash: 146f05b181998f995b6e15b0717034a55f518d7f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910256"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Konfigurieren von Add-Ins für beständige Chatrooms in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Konfigurieren von Add-Ins für Chatrooms Persistent Chat Server in Skype für Business Server 2015.
  
-Add-ins werden verwendet, um die Erfahrung in Raum durch Zuordnen von URLs zu Chatrooms zu erweitern. Diese URLs werden im Erweiterbarkeit Client Unterhaltung angezeigt. Ein typisches Add-in gehören eine URL, die auf einer Silverlight-Anwendung, die fängt ab, wenn ein Aktienticker in einem Chatroom gesendet wurde, und den vordefinierten Verlauf im Bereich Erweiterbarkeit zeigt zeigen. Weitere Beispiele umfassen Einbetten einer OneNote 2013 URL im Chatroom als ein Add-in einige freigegebenen Kontext, beispielsweise "Oben unter Sicherheitsgesichtspunkten" oder "Thema des Tages".
  
 Bevor Benutzer ein Add-In im Client sehen können, müssen sie es der Liste registrierter Add-Ins hinzufügen und Chatroom-Manager oder -Ersteller müssen es Räumen zuordnen.
  
> [!NOTE]
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Konfigurieren von Add-Ins für Chatrooms mithilfe der Systemsteuerung

So konfigurieren Sie Add-Ins für Chatrooms mithilfe der Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.
    
    Wählen Sie für Bereitstellungen mit mehreren Persistent Chat Server Pool den entsprechenden Pool aus der Dropdownliste aus.
    
4. Klicken Sie auf der Seite **Add-In** auf **Neu**.
    
5. Wählen Sie unter **Wählen Sie einen Dienst**Dienst entspricht dem Persistent Chat Server Pool, wenn Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen verschoben oder in mehreren Pools gemeinsam verwendet werden.
    
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

Sie können ein neues Add-in erstellen, mit dem Cmdlet **"New-cspersistentchataddin"** .
  
Dem folgenden Befehl wird beispielsweise ein neues Add-in (mit der Bezeichnung ITPersistentChatAddin) für den Pool Atl-Cs-001.contoso.com erstellt. Der URL-Parameter und der Wert des Parameters http://atl-cs-001.contoso.com/itchat Geben Sie den Speicherort der Webseite das Add-in:
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Konfiguriert Einstellungen für ein vorhandenes Add-In

Sie können für ein vorhandenes Add-in-Einstellungen konfigurieren, mit dem Cmdlet **"Set-cspersistentchataddin"** . Der folgende Befehl wird beispielsweise die URL für den beständigen Chat-add-in ITPersistentChatAddin geändert. In diesem Fall wird die URL in geänderthttp://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Ruft Informationen über Add-Ins ab

Mithilfe des Cmdlets **Get-CsPersistentChatAddin** können Sie Informationen über Add-Ins abrufen. Beispielsweise liefert der folgende Befehl Informationen über alle Add-Ins für beständigen Chat, die zur Verwendung in der Organisation konfiguriert wurden:
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Entfernt ein Add-In

Sie können ein Add-in mit dem Cmdlet **"Remove-cspersistentchataddin"** entfernen. Beispielsweise entfernt der folgende Befehl das Add-In für beständigen Chat namens „ITChatAddin“ aus dem Pool „atl-cs-001.contoso.com“:
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


