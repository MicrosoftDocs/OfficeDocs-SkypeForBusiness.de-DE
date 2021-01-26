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
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Zusammenfassung: Informationen zum Verwalten von Chatrooms für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815105"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Chatrooms auf dem Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie Chatrooms für den Server für beständigen Chat in Skype for Business Server 2015 verwalten.
  
Das Erstellen und Verwalten von Chatrooms ist mit der richtigen Verwendung von Kategorien viel einfacher. Eine Kategorie definiert, wer Chatrooms erstellen oder beitreten kann. Bevor Sie versuchen, Chatrooms zu verwalten, müssen Sie unbedingt die Kategorien für beständigen Chat, Chatrooms und [Benutzerrollen in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) lesen und kategorien in "Server für beständigen [Chat" in Skype for Business Server 2015](categories.md)verwalten.
  
> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 

Sie können Chatrooms konfigurieren und verwalten, indem Sie die befehlszeilenschnittstelle Windows PowerShell oder den Skype for Business-Client verwenden, wenn Sie Mitglied des Chatrooms sind. In diesem Thema wird das Verwalten von Chatrooms mithilfe Windows PowerShell Befehlszeilenschnittstelle beschrieben. Wenn Sie Chatrooms mithilfe des Skype for Business-Clients verwalten möchten, lesen Sie die Clienthilfe. 
  
Chatrooms können einen von zwei Typen haben: "Normal" und "Auditorium". In einem normalen Chatroom können alle Mitglieder Nachrichten posten und lesen. Ein Auditorium ist eine Art Chatroom, in dem nur Moderatoren Posten posten können, aber jeder kann lesen.
  
Wer auf Chatrooms zugreifen und diese verwalten kann, hängt von den Benutzerrollen wie folgt ab:
  
- Benutzer müssen Mitglieder eines Chatrooms sein, um Nachrichten posten und lesen zu können.
    
- Presenters are allowed to post to Auditorium rooms.
    
- Administratoren können frühere Inhalte (z. B. Inhalte, die vor einem bestimmten Datum veröffentlicht wurden) aus einem beliebigen Chatroom löschen, damit die Datenbank nicht zu groß wird. Administratoren können auch Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom als ungeeignet betrachtet werden.
    
- Endbenutzer, einschließlich Nachrichtenautoren, können keine Inhalte aus chatrooms löschen.
    
- Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen, einschließlich der Deaktivierung von Chatrooms. Manager können jedoch keinen Raum löschen oder die Kategorie eines Raumes ändern. 
    
- Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.
    
Sie können Chatrooms mithilfe der folgenden cmdlets Windows PowerShell verwalten:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Erstellen eines neuen Chatrooms  <br/> |
|Set-CsPersistentChatRoom  <br/> |Konfigurieren von Einstellungen für einen vorhandenen Raum; Zuweisen von Benutzern und Benutzergruppen zum Raum  <br/> |
|Get-CsPersistentChatRoom  <br/> |Abrufen von Informationen zu Räumen  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Löschen eines Bzw. von Nachrichten aus einem Raum  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Entfernen eines Raumes  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Entfernen von Nachrichten aus einem Raum  <br/> |
   
Verwenden Sie das **Cmdlet New-CsPersistentChatRoom** zum Erstellen von Chatrooms und das Cmdlet **"Set-CsPersistentChatRoom",** um einen vorhandenen Chatroom zu konfigurieren, einschließlich des Hinzufügens von Benutzern zum Chatroom. Sie können die folgenden Parameter für Chatrooms konfigurieren:
  
- Deaktiviert. Hiermit können Sie einen Chatroom deaktivieren oder aktivieren. 
    
- Einladungen. Hiermit können Sie Chatroomeinladungen aktivieren oder deaktivieren, die verwendet werden, um Benutzer zu benachrichtigen, wenn sie als Chatroommitglieder hinzugefügt wurden. Die Standardeinstellung für Einladungen, die geerbt werden, wodurch der Chatroom die Einladungseinstellung übernimmt, die für die Kategorie konfiguriert ist, zu der er gehört. Wenn Sie die Einladungseinstellung auf Chatroomebene auf "false" festlegen, kann die Kategorieeinstellung außer Kraft gesetzt werden. 
    
- Datenschutz. Hiermit können Sie angeben, ob ein Chatroom "Offen", "Geschlossen" oder "Geheim" ist. Offene Räume können von allen Durchsuchten durchsucht und darauf zugegriffen werden. Geschlossene Räume können von jedem durchsucht werden, aber nur von Mitgliedern. Geheime Räume können nur von Mitgliedern des Raumes durchsucht und darauf zugegriffen werden. Standardmäßig ist jeder neue Raum zunächst als "Geschlossen" konfiguriert.
    
- Typ. Hiermit können Sie angeben, ob es sich bei einem Chatroom um einen normalen Chatroom handelt, der von einem beliebigen Mitglied gepostete Nachrichten akzeptiert, oder um einen Auditoriumraum, der nur von einem Presenter gepostete Nachrichten akzeptiert.
    
- Addin. Hiermit können Sie ein zuvor konfiguriertes Add-In einem Chatroom zuordnen, der es mitgliedern ermöglicht, den Inhalt der URL während der Teilnahme anzuzeigen.
    
Zusätzlich zu den oben genannten Parametern können Sie mit dem **Cmdlet "Set-CsPersistentChatRoom"** dem Chatroom wie folgt Benutzer zuweisen:
  
- Member. Konfiguriert die Mitgliedschaft für den Chatroom. Sie können entweder die einzelnen oder mehrere Mitglieder mithilfe eines einzelnen Cmdlets hinzufügen oder entfernen, indem Sie die SIP-Adresse der Benutzer angeben. Damit Benutzer massenverteilt hinzugefügt werden können, können auch Active Directory-Organisationseinheiten oder Verteilergruppen angegeben werden.
    
- Manager. Hiermit können Sie dem Chatroom Manager zuweisen. Manager verfügen über die Berechtigungen zum Definieren der Mitgliedschaft in einem Chatroom zusammen mit anderen Einstellungen.
    
- Moderatoren. Hiermit können Sie einem Auditoriumchatroom Moderatoren zuweisen. 
    
  Details zur Syntax, einschließlich aller Parameter, finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Erstellen eines neuen Raumes

Mit dem Cmdlet **"New-CsPersistentChatRoom"** können Sie einen neuen Raum erstellen. Mit dem folgenden Befehl wird beispielsweise ein neuer Chatroom mit dem Namen "ITChatRoom" im Pool atl-cs-001.contoso.com. In diesem Beispiel wird der Chatroom der Kategorie "IT" hinzugefügt:
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Hinweis:** PersistentChatPoolFqdn ist nicht erforderlich, wenn eine der folgenden Bedingungen erfüllt ist: 
  
- Es gibt nur einen Serverpool für beständigen Chat.
    
- Sie geben einen Pool-FQDN für die Kategorie an.
    
- Sie stellen einen Pool-FQDN zum Hinzufügen des Raum zur Verfügung.
    
## <a name="configure-an-existing-room"></a>Konfigurieren eines vorhandenen Raums

Sie können einen vorhandenen Raum mithilfe des **Cmdlets "Set-CsPersistentChatRoom"** konfigurieren. Der folgende Befehl weist beispielsweise "user1" als Mitglied und Sprechleiter und "user2" als Vorgesetzter des "testCat Auditorium"-Raum zu:
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Im nächsten Beispiel werden dem Chatroom "NorthAmerica" alle Benutzer aus der Ou "NorthAmericaUsers" in Active Directory hinzufügt:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Im nächsten Beispiel werden alle Mitglieder aus der Verteilergruppe "Finance" demselben Chatroom hinzufügt:
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Deaktivieren oder Aktivieren eines Raum

Wenn das Thema eines Chatrooms für beständigen Chat nicht mehr relevant ist, können Sie den Chatroom für Benutzer deaktivieren. Wird ein Chatroom deaktiviert, dann werden alle Mitglieder vom Chatroom getrennt. Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten, und er wird auch nicht bei der Suche nach Chatrooms gefunden.
  
Wenn der Verlauf des Chatrooms beibehalten wird, wird der Inhalt beibehalten, wenn der Chatroom deaktiviert ist. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden. Informationen zum Konfigurieren des Chatroomverlaufs finden Sie unter "Verwalten von Kategorien [im Server für beständigen Chat in Skype for Business Server 2015".](categories.md) 
  
Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten. Als Administrator können Sie einen deaktivierten Raum aktivieren, und Sie müssen die Einstellungen nicht manuell neu erstellen.
  
Sie können einen Raum deaktivieren, indem Sie das **Cmdlet "Set-CsPersistentChatRoom"** verwenden und den Parameter "Disabled" auf "True" festlegen:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Um einen Chatroom zu aktivieren, legen Sie den Parameter "Disabled" auf "False" (False) festgelegt:
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Informationen zu Räumen erhalten

Um Informationen zu den Chatrooms zu erhalten, die für die Verwendung in Ihrer Organisation konfiguriert sind, können Sie das **Cmdlet "Get-CsPersistentChatRoom"** verwenden.
  
Der folgende Befehl gibt Informationen zu allen Chatrooms zurück, die für die Verwendung in der Organisation konfiguriert sind:
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Entfernen aller Inhalte aus einem Raum

Mit dem Cmdlet **"Clear-CsPersistentChatRoom"** können Sie Inhalte aus einem Raum entfernen. Mit dem folgenden Befehl werden beispielsweise alle Inhalte aus dem Chatroom für beständigen Chat "ITChatRoom" entfernt, der dem Chatroom am oder vor dem 1. März 2015 hinzugefügt wurde:
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Entfernen einer Nachricht aus einem Raum

Mithilfe des Cmdlets **"Remove-CsPersistentChatMessage"** können Sie eine oder mehrere Nachrichten in der Datenbank für den beständigen Chat entfernen und optional durch eine Standardnachricht oder durch eine vom Administrator bereitgestellte Nachricht ersetzen. Der folgende Befehl entfernt beispielsweise alle Nachrichten aus dem ITChatRoom-Chatroom, die vom Benutzer gepostet kenmyer@contoso.com:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

Im nächsten Beispiel werden alle entfernten Nachrichten durch den Hinweis ersetzt, dass die Nachricht nicht mehr verfügbar ist:
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Entfernen eines Raumes

Sie können einen Raum mit dem **Cmdlet "Remove-CsPersistentChatRoom"** entfernen.
  
Der folgende Befehl entfernt beispielsweise den Chatroom "RedmondChatRoom":
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Verschieben eines Raumes von einer Kategorie in eine andere

Wenn ein Chatroommanager über Creator-Berechtigungen in einer anderen Kategorie verfügt, kann er den Chatroom von einer Kategorie in eine andere verschieben.  Der Room wird hierbei weder gelöscht noch neu erstellt. Es wird lediglich die Zuordnung in der Datenbank geändert.
  
Das Ändern einer Chatroomkategorie sollte nur selten und mit Vorsicht durchgeführt werden. Eine Kategorie bestimmt die zulässige Mitgliedschaft für den Chatroom. Wenn also ein Chatroom in eine andere Kategorie verschoben wird, werden alle Systemzugriffssteuerungslisten (SACLs) gelöscht, die von der neuen Kategorie nicht mehr unterstützt werden. Wenn beispielsweise ein Benutzer Mitglied des Raumes war und kein zulässiges Mitglied mehr in der neuen Kategorie ist, wird die Raummitgliedschaft geändert, und der Benutzer wird aus dem Raum entfernt.
  

