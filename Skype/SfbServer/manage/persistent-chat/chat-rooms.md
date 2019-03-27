---
title: Verwalten von Chatrooms im Server für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Chatrooms in Skype Persistent Chat Server for Business Server 2015.'
ms.openlocfilehash: 8764b40651c9872393867ced205c405cfc2d4046
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881730"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten von Chatrooms im Server für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Verwalten von Chatrooms in Skype Persistent Chat Server for Business Server 2015.
  
Das Erstellen und Verwalten von Chatrooms wird durch die ordnungsgemäße Verwendung von Kategorien wesentlich vereinfacht. Eine Kategorie definiert, die erstellen oder die Chatrooms beitreten können. Bevor Sie versuchen, Chatrooms zu verwalten, müssen Sie unbedingt [Persistent Chatkategorien, Chatrooms, und Benutzerrollen in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) und [Verwalten von Kategorien in Persistent Chat Server in Skype für Business Server 2015](categories.md)vertraut zu machen.
  
> [!NOTE]
> Beständiger Chat wird steht in Skype für Business Server 2015 jedoch nicht mehr unterstützt in Skype Business Server 2019. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter [Weg von Skype für Unternehmen, die Microsoft-Teams](/microsoftteams/journey-skypeforbusiness-teams). Wenn Sie Persistent Chat verwenden müssen, sind Ihrer Auswahl an Benutzer, die diese Funktionalität Teams migrieren oder weiterhin Skype für Business Server 2015 verwenden. 

Sie können konfigurieren und Verwalten von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle oder mithilfe der Skype für Business-Client, wenn Sie ein Mitglied des Chatrooms sind. In diesem Thema wird beschrieben, wie Sie Chatrooms mit der Befehlszeilenschnittstelle von Windows PowerShell verwalten. Zum Verwalten von Chatrooms mithilfe der Skype für Business-Client, finden Sie die Client-Hilfe. 
  
Chatrooms kann eine der beiden folgenden Typen: Normal und Auditorium. In einem normalen Chatroom können alle Mitglieder Nachrichten posten und lesen. Ein Auditorium ist eine Art von Chatroom, in der nur Referenten Inhalte posten, aber alle Mitglieder diese Inhalte lesen können.
  
Es hängt von den jeweiligen Benutzerrollen ab, wer auf Chatrooms zugreifen und diese verwalten kann:
  
- Um Nachrichten posten und lesen zu können, müssen Benutzer Mitglied eines Chatrooms sein.
    
- Referenten können Posts in Auditorium-Chatrooms veröffentlichen.
    
- Administratoren können frühere Inhalte aus jedem Chatroom löschen (z. B. Inhalte, die vor einem bestimmen Datum veröffentlicht wurden), um zu verhindern, dass die Datenbanken zu groß werden. Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom ungeeignet sind.
    
- Endbenutzer, einschließlich Autoren von Nachrichten, können keine Inhalte aus Chatrooms entfernen.
    
- Chatroommanager können Änderungen an allen Chatroomeigenschaften vornehmen, z. B. können sie einen Chatroom deaktivieren. Manager können aber keine Chatrooms löschen oder die Kategorie eines Chatrooms ändern. 
    
- Nur Administratoren können Chatrooms löschen, nachdem diese erstellt wurden.
    
Mithilfe der folgenden Windows PowerShell-Cmdlets können Sie Chatrooms konfigurieren und managen:
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Erstellen eines neuen Chatrooms  <br/> |
|Set-CsPersistentChatRoom  <br/> |Zum Konfigurieren der Einstellungen für einen vorhandenen Chatroom sowie zum Zuweisen von Benutzern und Benutzergruppen zum Chatroom  <br/> |
|Get-CsPersistentChatRoom  <br/> |Abrufen von Informationen über Räume  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Löschen eines Chatrooms oder Löschen von Nachrichten in einem Chatroom  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Entfernen eines Chatrooms  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Entfernen von Nachrichten aus einem Chatroom  <br/> |
   
Mit dem Cmdlet **New-CsPersistentChatRoom** und dem Cmdlet **Set-CsPersistentChatRoom** können Sie einen vorhandenen Chatroom konfigurieren und beispielsweise Benutzer hinzufügen. Sie können die folgenden Parameter für Chatrooms konfigurieren:
  
- Disabled: Zum Deaktivieren bzw. Können Sie einen Chatroom aktivieren oder deaktivieren. 
    
- Einladungen. Können Sie aktivieren oder Deaktivieren von chatroomeinladungen, die verwendet werden, um Benutzer zu benachrichtigen, wenn sie als Chatroom-Mitglieder hinzugefügt wurden. Die Standardeinstellung für Einladungen in erben, die verursacht den Chatroom treffen die Einstellung der Einladung auf die Kategorie, zu der es gehört konfiguriert ist. Konfigurieren von Einladungen ermöglicht Einstellung auf "false" auf der Ebene der Chatroom die Kategorie Einstellung außer Kraft gesetzt werden. 
    
- Datenschutz. Gibt an, ob ein Chatroom öffnen, schließen oder geheimen Schlüssel ist. Offene Chatrooms können durchsucht und von allen Benutzern zugegriffen werden. Geschlossene Räume können von jeder Person durchsucht werden, jedoch nur von Mitgliedern zugegriffen werden können. Geheimen Chatrooms können durchsucht und nur von Mitgliedern des Raums aufgerufen werden. Standardmäßig ist jeder neuen Raums anfänglich als geschlossen konfiguriert.
    
- Geben Sie ein. Gibt an, ob ein Chatroom einem normalen Raum, ist, der durch ein beliebiges Mitglied oder einem Auditorium, die nur von Referent übermittelten Nachrichten akzeptiert veröffentlichte Nachrichten akzeptiert.
    
- Addin: Ermöglicht Ihnen, ein zuvor konfiguriertes Add-In mit einem Chatroom zu verknüpfen. Auf diese Weise können Mitglieder während der Nutzung des Chatrooms URL-Inhalte anzeigen.
    
Zusätzlich zu den oben genannten Parametern kann mit dem Cmdlet **"Set-cspersistentchatroom"** Zuweisen von Benutzern für den Chatroom wie folgt:
  
- Elemente des Objekts. Die Mitgliedschaft für den Chatroom konfiguriert. Sie können hinzufügen oder Entfernen der betroffenen oder mehrere Mitglieder, die mit einem einzelnen Cmdlet durch die SIP-Adresse der Benutzer angeben. Damit Benutzer in einer Sammeloperation hinzugefügt werden können, können auch Active Directory-Organisationseinheiten oder Verteilergruppen angegeben werden.
    
- Manager. Hier können Sie den Chatroom Manager zuweisen. Manager müssen die Berechtigungen, um die Mitgliedschaft eines Chatrooms zusammen mit anderen Einstellungen zu definieren.
    
- Presenters: Ermöglicht Ihnen, einem Auditorium-Chatroom Referenten zuzuweisen. 
    
  Details zur Syntax und allen Parametern finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Einen neuen Chatroom erstellen

Mit dem Cmdlet **New-CsPersistentChatRoom** können Sie einen neuen Chatroom erstellen. Der folgende Befehl erstellt beispielsweise einen neuen Chatroom namens „ITChatRoom“ im Pool „atl-cs-001.contoso.com“. In diesem Beispiel wird der Chatroom der IT-Kategorie zugeordnet:
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Hinweis:** PersistentChatPoolFqdn ist nicht erforderlich, wenn eine der folgenden Bedingungen erfüllt ist: 
  
- Nur ein Persistent Chat Server-Pool ist vorhanden.
    
- Sie stellen für die Kategorie einen Pool-FQDN bereit.
    
- Sie stellen einen Pool-FQDN zum Hinzufügen des Chatrooms bereit.
    
## <a name="configure-an-existing-room"></a>Konfigurieren eines vorhandenen Chatrooms

Sie können eine vorhandene Raum konfigurieren, mit dem Cmdlet **"Set-cspersistentchatroom"** . Dem folgenden Befehl wird beispielsweise user1 als Member und Referent und user2 als Manager, der die TestCat Auditorium-Chatrooms:
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 Mit dem folgenden Befehl werden beispielsweise alle Benutzer in der Organisationseinheit „NorthAmericaUsers“ in Active Directory zum Chatroom „NorthAmerica“ hinzugefügt:
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

Mit dem folgenden Befehl werden alle Mitglieder der Finanzdistributionsgruppe zum selben Chatroom hinzugefügt:
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Deaktivieren oder Aktivieren eines Chatrooms

Wenn das Thema eines beständigen Chatrooms nicht mehr relevant ist, können Sie den Chatroom Benutzern zur Verfügung durch deaktivieren. Wenn ein Chatroom deaktiviert wird, werden alle Mitglieder vom Chatroom getrennt. Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten und er wird auch nicht bei der Suche nach Chatrooms gefunden.
  
Wenn Sie den Chatroom Verlauf weiterhin auftritt, wird der Inhalt beibehalten, wenn Chatrooms deaktiviert ist. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden. Informationen zum Konfigurieren von chatroomverlauf finden Sie unter [Verwalten von Kategorien in Persistent Chat Server in Skype für Business Server 2015](categories.md). 
  
Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten. Sie als Administrator können einen deaktivierten Chatroom wieder aktivieren und brauchen die Einstellungen dabei nicht manuell wiederherzustellen.
  
Sie können einen Chatroom deaktivieren, indem Sie mithilfe des Cmdlets **"Set-cspersistentchatroom"** und den Parameter deaktiviert auf True festlegen:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Zum Aktivieren eines Chatrooms legen Sie den Parameter „Disabled“ auf „False“ fest:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Abrufen von Informationen über Räume

Mithilfe des Cmdlets **Get-CsPersistentChatRoom** können Sie Informationen für die in Ihrer Organisation konfigurierten und verwendeten Chatrooms abrufen.
  
Der folgende Befehl gibt Informationen zu allen Chatrooms zurück, die für die Verwendung in Ihrer Organisation konfiguriert sind:
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Entfernen aller Inhalte aus einem Chatroom

Mit dem Cmdlet **Clear-CsPersistentChatRoom** können Sie Inhalte aus einem Chatroom entfernen. Der folgende Befehl entfernt beispielsweise alle Inhalte aus dem Chatroom für beständigen Chat „ITChatRoom“, die dem Chatroom am oder vor dem 1. März 2015 hinzugefügt wurden:
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Entfernen einer Nachricht aus einem Chatroom

Mit dem Cmdlet **Remove-CsPersistentChatMessage** können Sie eine oder mehrere Nachrichten aus der Datenbank des beständigen Chats entfernen und optional durch eine Standardnachricht oder eine durch den Administrator bereitgestellte Nachricht ersetzen. Der folgende Befehl entfernt beispielsweise alle Nachrichten aus dem Chatroom „ITChatRoom“, die vom Benutzer „kenmyer@contoso.com“ gepostet wurden:
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

Mit diesem Beispiel werden alle entfernten Nachrichten durch den Hinweis ersetzt, dass die Nachricht nicht mehr verfügbar ist:
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Entfernen eines Chatrooms

Mit dem Cmdlet **Remove-CsPersistentChatRoom** können Sie einen Chatroom entfernen.
  
Mit dem folgenden Befehl wird beispielsweise der Chatroom „RedmondChatRoom“ entfernt:
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Verschieben eines Chatrooms von einer Kategorie in eine andere

Wenn ein Chatroommanager **Ersteller**-Berechtigungen in einer anderen Kategorie hat, kann er den Chatroom von einer Kategorie in eine andere verschieben. Der Chatroom wird dabei nicht gelöscht und neu erstellt, sondern die Verknüpfung mit der Datenbank wird geändert.
  
Chatroomkategorien sollten eher selten und nur mit Vorsicht geändert werden. Eine Kategorie legt die erlaubte Mitgliedschaft für einen Chatroom fest. Wenn also der Chatroom in eine andere Kategorie verschoben wird, werden alle Systemzugriffssteuerungslisten (SACLs) gelöscht, die von der neuen Kategorie nicht unterstützt werden. Wenn beispielsweise ein Benutzer Mitglied eines Chatrooms war und nun kein zugelassenes Mitglied der neuen Kategorie mehr ist, wird die Mitgliedschaft für den Chatroom geändert und der Benutzer aus diesem entfernt.
  

