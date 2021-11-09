---
title: Konfigurieren von Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Zusammenfassung: Erfahren Sie, wie Sie Add-Ins für Chatrooms für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.'
ms.openlocfilehash: c23a0dd11d51bbfa1c49d8a910decda5be0ac48f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854299"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Konfigurieren von Add-Ins für Chatrooms für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Add-Ins für Chatrooms für den Server für beständigen Chat in Skype for Business Server 2015 konfigurieren.
  
Add-Ins werden verwendet, um die In-Room-Erfahrung durch Zuordnen von URLs zu Chatrooms zu erweitern. Diese URLs werden im Erweiterungsbereich der Clientunterhaltung angezeigt. Ein typisches Add-In kann eine URL enthalten, die auf eine Silverlight-Anwendung zeigt, die abfängt, wenn ein Stock-Ticker in einem Chatroom veröffentlicht wird, und den Aktienverlauf im Erweiterbarkeitsbereich anzeigt. Weitere Beispiele sind das Einbetten einer OneNote 2013-URL in den Chatroom als Add-In, um einen freigegebenen Kontext einzuschließen, z. B. "Top of mind" oder "Topic of the day".
  
 Bevor Benutzer ein Add-In im Client sehen können, müssen Sie das Add-In der Liste der registrierten Add-Ins hinzufügen, und Chatroommanager oder Ersteller müssen dem Add-In Chatrooms zuordnen.
  
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Konfigurieren von Add-Ins für Chatrooms mithilfe der Systemsteuerung

So konfigurieren Sie Add-Ins für Chatrooms mithilfe der Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat** und dann auf **Add-In**.
    
    Wählen Sie für mehrere Bereitstellungen des Servers für beständigen Chat in der Dropdownliste den entsprechenden Pool aus.
    
4. Klicken Sie auf der Seite **Add-In** auf **Neu**.
    
5. Wählen Sie in **"Dienst auswählen"** den Dienst aus, der dem Serverpool für beständigen Chat entspricht, in dem Sie das Add-In erstellen müssen. Add-Ins können nicht von einem Pool in einen anderen Pool verschoben oder von unterschiedlichen Pools gemeinsam genutzt werden.
    
6. Führen Sie unter **Neues Add-In** Folgendes aus:
    
   - Geben Sie unter **Name** einen Namen für das neue Add-In an.
    
   - Geben Sie unter **URL** die URL an, die dem Add-In zugeordnet werden soll. URLs sind auf die HTTP- und HTTPS-Protokolle beschränkt.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Konfigurieren von Add-Ins mithilfe von Windows PowerShell

Sie können Add-Ins für Chatrooms mithilfe der folgenden cmdlets Windows PowerShell konfigurieren. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server 2015-Verwaltungsshell.](../management-shell.md)
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Erstellen eines neuen Add-Ins  <br/> |
|Set-CsPersistentChatAddin  <br/> |Konfigurieren von Einstellungen für ein vorhandenes Add-In  <br/> |
|Get-CsPersistentChatAddin  <br/> |Abrufen von Informationen zu Add-Ins  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Entfernen eines Add-Ins  <br/> |
   
### <a name="create-a-new-add-in"></a>Erstellen eines neuen Add-Ins

Mit dem Cmdlet **"New-CsPersistentChatAddin"** können Sie ein neues Add-In erstellen.
  
Beispielsweise erstellt der folgende Befehl ein neues Add-In (mit dem Namen ITPersistentChatAddin) für den `atl-cs-001.contoso.com` Pool. Der URL-Parameter und der Parameterwert `http://atl-cs-001.contoso.com/itchat` geben den Speicherort der Webseite des Add-Ins an:
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Konfigurieren von Einstellungen für ein vorhandenes Add-In

Sie können Einstellungen für ein vorhandenes Add-In mithilfe des **Cmdlets "Set-CsPersistentChatAddIn"** konfigurieren. Beispielsweise ändert der folgende Befehl die URL, die dem Add-In für beständigen Chat ITPersistentChatAddin zugewiesen ist. In diesem Fall wird die URL wie folgt `http://atl-cs-001.contoso.com/itchat2` geändert:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Abrufen von Informationen zu Add-Ins

Mit dem Cmdlet **"Get-CsPersistentChatAddin"** können Sie Informationen zu Add-Ins abrufen. Der folgende Befehl gibt beispielsweise Informationen zu allen Add-Ins für beständigen Chat zurück, die für die Verwendung in der Organisation konfiguriert sind:
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Entfernen eines Add-Ins

Sie können ein Add-In mithilfe des **Cmdlets "Remove-CsPersistentChatAddIn"** entfernen. Mit dem folgenden Befehl wird z. B. das Add-In "ITChatAddin" des Add-Ins für beständigen Chat entfernt, das im Pool gefunden `atl-cs-001.contoso.com` wurde:
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


