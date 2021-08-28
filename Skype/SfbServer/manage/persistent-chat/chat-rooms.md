---
title: Verwalten von Chatrooms auf dem Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Zusammenfassung: Erfahren Sie, wie Sie Chatrooms für den Server für beständigen Chat in Skype for Business Server 2015 verwalten.'
ms.openlocfilehash: 928fef65d63165721957ca0622b959860d82704e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58630569"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Chatrooms auf dem Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Chatrooms für den Server für beständigen Chat in Skype for Business Server 2015 verwalten.
  
Das Erstellen und Verwalten von Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Eine Kategorie definiert, wer chatrooms erstellen oder daran teilnehmen kann. Bevor Sie versuchen, Chatrooms zu verwalten, müssen Sie [die Kategorien für beständigen Chat, Chatrooms und Benutzerrollen in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) lesen und [Kategorien im Server für beständigen Chat in Skype for Business Server 2015 verwalten.](categories.md)
  
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Erste Schritte mit Ihrem Microsoft Teams Upgrade.](/microsoftteams/upgrade-start-here) Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität zum Teams benötigen, oder Skype for Business Server 2015 weiterhin verwenden. 

Sie können Chatrooms mithilfe der Windows PowerShell Befehlszeilenschnittstelle oder mit dem Skype for Business-Client konfigurieren und verwalten, wenn Sie Mitglied des Chatrooms sind. In diesem Thema wird beschrieben, wie Sie Chatrooms mithilfe der Windows PowerShell Befehlszeilenschnittstelle verwalten. Wenn Sie Chatrooms mithilfe des Skype for Business-Clients verwalten möchten, lesen Sie die Clienthilfe. 
  
Chatrooms können eine von zwei Typen sein: Normal und Auditorium. Ein normaler Chatroom ermöglicht es allen Mitgliedern, Nachrichten zu posten und zu lesen. Ein Auditorium ist eine Art von Chatroom, in dem nur Referenten beiträgen können, aber jeder kann lesen.
  
Wer auf Chatrooms zugreifen und diese verwalten können, hängt von benutzerrollen wie folgt ab:
  
- Benutzer müssen Mitglieder eines Chatrooms sein, um Nachrichten posten und lesen zu können.
    
- Referenten dürfen Beiträge in Auditorium-Räumen veröffentlichen.
    
- Administratoren können frühere Inhalte (z. B. Inhalte, die vor einem bestimmten Datum veröffentlicht wurden) aus jedem Chatroom löschen, damit die Datenbank nicht zu groß wird. Administratoren können auch Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom als unangemessen gelten.
    
- Endbenutzer, einschließlich Nachrichtenautoren, können keine Inhalte aus einem Chatroom löschen.
    
- Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen, einschließlich des Deaktivierens von Chatrooms. Manager können jedoch keinen Raum löschen oder die Kategorie eines Raums ändern. 
    
- Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.
    
Sie können Chatrooms mithilfe der folgenden cmdlets Windows PowerShell konfigurieren und verwalten:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Erstellen eines neuen Chatrooms  <br/> |
|Set-CsPersistentChatRoom  <br/> |Konfigurieren von Einstellungen für einen vorhandenen Raum; Zuweisen von Benutzern und Benutzergruppen zum Raum  <br/> |
|Get-CsPersistentChatRoom  <br/> |Abrufen von Informationen zu Chatrooms  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Löschen eines Chatrooms oder von Nachrichten aus einem Raum  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Entfernen eines Raums  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Entfernen von Nachrichten aus einem Raum  <br/> |
   
Sie verwenden das Cmdlet **"New-CsPersistentChatRoom",** um Chatrooms zu erstellen, und das Cmdlet **"Set-CsPersistentChatRoom",** um einen vorhandenen Chatroom zu konfigurieren, einschließlich des Hinzufügens von Benutzern zum Chatroom. Sie können die folgenden Parameter für Chatrooms konfigurieren:
  
- Deaktiviert. Ermöglicht das Deaktivieren oder Aktivieren eines Chatrooms. 
    
- Einladungen. Ermöglicht ihnen das Aktivieren oder Deaktivieren von Chatroom-Einladungen, die verwendet werden, um Benutzer zu benachrichtigen, wenn sie als Chatroommitglieder hinzugefügt wurden. Die Standardeinstellung für Einladungen in "inherit", die dazu führte, dass der Chatroom die Einladungseinstellung annimmt, die für die Kategorie konfiguriert ist, zu der er gehört. Wenn Sie die Einladungseinstellung auf Chatroomebene auf "false" konfigurieren, kann die Kategorieeinstellung überschrieben werden. 
    
- Privatsphäre. Hiermit können Sie angeben, ob ein Chatroom geöffnet, geschlossen oder geheim ist. Offene Räume können von jedem durchsucht und aufgerufen werden. Geschlossene Räume können von jedem durchsucht werden, aber nur von Mitgliedern aufgerufen werden. Geheime Räume können nur von Mitgliedern des Raums durchsucht und darauf zugegriffen werden. Standardmäßig ist jeder neue Raum anfänglich als "Geschlossen" konfiguriert.
    
- Typ. Hiermit können Sie angeben, ob ein Chatroom ein Normaler Chatroom ist, der von einem beliebigen Mitglied gepostete Nachrichten akzeptiert, oder ein Auditorium-Chatroom, der nur von einem Referenten gepostete Nachrichten akzeptiert.
    
- Addin. Hiermit können Sie ein zuvor konfiguriertes Add-In einem Chatroom zuordnen, sodass URL-Inhalte während der Teilnahme von Mitgliedern angezeigt werden können.
    
Zusätzlich zu den oben genannten Parametern können Sie mit dem Cmdlet **"Set-CsPersistentChatRoom"** dem Chatroom wie folgt Benutzer zuweisen:
  
- Mitglieder. Konfiguriert die Mitgliedschaft für den Chatroom. Sie können entweder die einzelnen oder mehrere Mitglieder mit einem einzigen Cmdlet hinzufügen oder entfernen, indem Sie die SIP-Adresse der Benutzer angeben. Damit Benutzer in Massen hinzugefügt werden können, können auch Active Directory-Organisationseinheiten oder Verteilergruppen angegeben werden.
    
- Manager. Hiermit können Sie dem Chatroom Manager zuweisen. Manager haben die Berechtigung, die Mitgliedschaft in einem Chatroom zusammen mit anderen Einstellungen zu definieren.
    
- Moderatoren. Mit dieser Option können Sie Referenten einem Auditorium-Chatroom zuweisen. 
    
  Ausführliche Informationen zur Syntax, einschließlich aller Parameter, finden Sie unter [Skype for Business Server 2015-Verwaltungsshell.](../management-shell.md)
  
## <a name="create-a-new-room"></a>Erstellen eines neuen Raums

Mit dem Cmdlet **"New-CsPersistentChatRoom"** können Sie einen neuen Raum erstellen. Der folgende Befehl erstellt beispielsweise einen neuen Chatroom mit dem Namen ITChatRoom im Pool atl-cs-001.contoso.com. In diesem Beispiel wird der Chatroom der IT-Kategorie hinzugefügt:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Hinweis:** PersistentChatPoolFqdn ist nicht erforderlich, wenn einer der folgenden Werte zutrifft: 
  
- Es gibt nur einen Serverpool für beständigen Chat.
    
- Sie stellen einen Pool-FQDN für die Kategorie bereit.
    
- Sie stellen einen Pool-FQDN bereit, um den Raum hinzuzufügen.
    
## <a name="configure-an-existing-room"></a>Konfigurieren eines vorhandenen Chatrooms

Sie können einen vorhandenen Raum mithilfe des Cmdlets **"Set-CsPersistentChatRoom"** konfigurieren. Mit dem folgenden Befehl wird beispielsweise "user1" als Mitglied und Referent und "User2" als Manager des "testCat Auditorium"-Raums zugewiesen:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Im nächsten Beispiel werden alle Benutzer aus der Oe "NorthAmericaUsers" in Active Directory zum Chatroom "NorthAmerica" hinzugefügt:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Im nächsten Beispiel werden alle Mitglieder aus der Verteilergruppe "Finance" zum selben Chatroom hinzugefügt:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Deaktivieren oder Aktivieren eines Raums

Wenn das Thema eines Chatrooms für beständigen Chat nicht mehr relevant ist, können Sie den Chatroom für Benutzer nicht verfügbar machen, indem Sie ihn deaktivieren. Wird ein Chatroom deaktiviert, dann werden alle Mitglieder vom Chatroom getrennt. Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten, und er wird auch nicht bei der Suche nach Chatrooms gefunden.
  
Wenn der Verlauf des Chatrooms beibehalten wird, wird der Inhalt beibehalten, wenn der Chatroom deaktiviert ist. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden. Informationen zum Konfigurieren des Chatroomverlaufs finden Sie unter [Verwalten von Kategorien auf dem Server für beständigen Chat in Skype for Business Server 2015.](categories.md) 
  
Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten. Als Administrator können Sie einen deaktivierten Raum aktivieren und müssen die Einstellungen nicht manuell neu erstellen.
  
Sie können einen Raum deaktivieren, indem Sie das Cmdlet **"Set-CsPersistentChatRoom"** verwenden und den Parameter "Disabled" auf "True" festlegen:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Um einen Chatroom zu aktivieren, legen Sie den Parameter "Disabled" auf "False" fest:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Abrufen von Informationen zu Chatrooms

Um Informationen zu den für die Verwendung in Ihrer Organisation konfigurierten Chatrooms zu erhalten, können Sie das Cmdlet **"Get-CsPersistentChatRoom"** verwenden.
  
Der folgende Befehl gibt Informationen zu allen Chatrooms zurück, die für die Verwendung in der Organisation konfiguriert sind:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Entfernen aller Inhalte aus einem Raum

Mit dem Cmdlet **"Clear-CsPersistentChatRoom"** können Sie Inhalte aus einem Raum entfernen. Mit dem folgenden Befehl wird beispielsweise der gesamte Inhalt aus dem ITChatRoom für beständigen Chat entfernt, der dem Chatroom am oder vor dem 1. März 2015 hinzugefügt wurde:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Entfernen einer Nachricht aus einem Raum

Mit dem Cmdlet **"Remove-CsPersistentChatMessage"** können Sie eine oder mehrere Nachrichten in der Datenbank für beständigen Chat entfernen und optional durch eine Standardnachricht oder eine vom Administrator bereitgestellte Nachricht ersetzen. Mit dem folgenden Befehl werden beispielsweise alle Nachrichten aus dem CHATroom "ITChatRoom" entfernt, die vom Benutzer kenmyer@contoso.com gepostet wurden:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

Im nächsten Beispiel werden alle entfernten Nachrichten durch den Hinweis ersetzt, dass die Nachricht nicht mehr verfügbar ist:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Entfernen eines Raums

Sie können einen Raum mithilfe des **Cmdlets "Remove-CsPersistentChatRoom"** entfernen.
  
Mit dem folgenden Befehl wird beispielsweise der Chatroom "RedmondChatRoom" entfernt:
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Verschieben eines Raums von einer Kategorie in eine andere

Wenn ein Chatroom-Manager **über Creator-Berechtigungen** in einer anderen Kategorie verfügt, kann er den Chatroom von einer Kategorie in eine andere verschieben. Der Room wird hierbei weder gelöscht noch neu erstellt. Es wird lediglich die Zuordnung in der Datenbank geändert.
  
Das Ändern einer Chatroomkategorie sollte nur selten und mit Vorsicht erfolgen. Eine Kategorie bestimmt die zulässige Mitgliedschaft für den Chatroom. Wenn ein Chatroom in eine andere Kategorie verschoben wird, werden daher alle Systemzugriffssteuerungslisten (SACLs) gelöscht, die von der neuen Kategorie nicht mehr unterstützt werden. Wenn beispielsweise ein Benutzer Mitglied des Raums war und kein zulässiges Mitglied in der neuen Kategorie mehr ist, wird die Raummitgliedschaft geändert, und der Benutzer wird aus dem Raum entfernt.
  

