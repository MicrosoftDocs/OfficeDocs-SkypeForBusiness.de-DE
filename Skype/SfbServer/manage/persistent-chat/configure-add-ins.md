---
title: Konfigurieren von Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Zusammenfassung: Informationen zum Konfigurieren von Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815076"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Konfigurieren von Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015 konfigurieren.
  
Add-Ins werden verwendet, um die Raumerfahrung durch Zuordnen von URLs zu Chatrooms zu erweitern. Diese URLs werden im Erweiterbarkeitsbereich der Clientbesprechung angezeigt. Ein typisches Add-in kann eine URL enthalten, die auf eine Silverlight-Anwendung verweist, die abfängt, wenn ein Aktienticker in einem Chatroom veröffentlicht wird, und zeigt den Aktienverlauf im Erweiterbarkeitsbereich an. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-In, um einen freigegebenen Kontext wie "Kopf-an-Kopf" oder "Thema des Tages" einzubetten.
  
 Bevor Benutzer ein Add-In im Client sehen können, müssen Sie das Add-in der Liste der registrierten Add-Ins hinzufügen, und Chatroommanager oder Ersteller müssen dem Add-in Chatrooms zuordnen.
  
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Konfigurieren von Add-Ins für Chatrooms mithilfe der Systemsteuerung

So konfigurieren Sie Add-Ins für Chatrooms mithilfe der Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.
    
    Wählen Sie für mehrere Bereitstellungen des Pools für beständigen Chat in der Dropdownliste den entsprechenden Pool aus.
    
4. Klicken Sie auf der Seite **Add-In** auf **Neu**.
    
5. Wählen **Sie in "Dienst** auswählen" den Dienst aus, der dem Serverpool für beständigen Chat entspricht, in dem Sie das Add-in erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen Pool verschoben oder von unterschiedlichen Pools gemeinsam genutzt werden.
    
6. Führen Sie unter **Neues Add-In** Folgendes aus:
    
   - Geben Sie unter **Name** einen Namen für das neue Add-In an.
    
   - Geben Sie unter **URL** die URL an, die dem Add-In zugeordnet werden soll. URLs sind auf die Http- und https-Protokolle beschränkt.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Konfigurieren von Add-Ins mithilfe von Windows PowerShell

Sie können Add-Ins für Chatrooms mithilfe der folgenden Windows PowerShell konfigurieren. Einzelheiten zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Erstellen eines neuen Add-Ins  <br/> |
|Set-CsPersistentChatAddin  <br/> |Konfigurieren von Einstellungen für ein vorhandenes Add-In  <br/> |
|Get-CsPersistentChatAddin  <br/> |Abrufen von Informationen zu Add-Ins  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Entfernen eines Add-Ins  <br/> |
   
### <a name="create-a-new-add-in"></a>Erstellen eines neuen Add-Ins

Sie können ein neues Add-In mit dem **Cmdlet "New-CsPersistentChatAddin"** erstellen.
  
Der folgende Befehl erstellt z. B. ein neues Add-In (mit dem Namen "ITPersistentChatAddin") für atl-cs-001.contoso.com. Der Parameter "URL" und der Parameterwert geben den Speicherort der Webseite des http://atl-cs-001.contoso.com/itchat Add-Ins an:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Konfigurieren von Einstellungen für ein vorhandenes Add-In

Sie können Einstellungen für ein vorhandenes Add-In mithilfe des **Cmdlets "Set-CsPersistentChatAddIn"** konfigurieren. Der folgende Befehl ändert beispielsweise die URL, die dem Add-In "ITPersistentChatAddin" für beständigen Chat zugewiesen ist. In diesem Fall wird die URL in http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Abrufen von Informationen zu Add-Ins

Mit dem Cmdlet **"Get-CsPersistentChatAddin"** können Sie Informationen zu Add-Ins erhalten. Der folgende Befehl gibt beispielsweise Informationen zu allen Add-Ins für beständigen Chat zurück, die für die Verwendung in der Organisation konfiguriert sind:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Entfernen eines Add-Ins

Sie können ein Add-In mithilfe des **Cmdlets "Remove-CsPersistentChatAddIn"** entfernen. Der folgende Befehl entfernt z. B. das Add-In "ITChatAddin" für beständigen Chat, das in der Pooladresse atl-cs-001.contoso.com:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


