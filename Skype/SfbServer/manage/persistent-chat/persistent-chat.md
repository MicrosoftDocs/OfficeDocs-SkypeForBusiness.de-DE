---
title: Verwalten des Servers für beständigen Chat in Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Persistent Chat Server in Skype für Business Server 2015.'
ms.openlocfilehash: 294c6bcecbbfb57bb8d2a6a785cdf20775119510
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Informationen Sie zum Verwalten von Persistent Chat Server in Skype für Business Server 2015.
  
Wenn Sie für Ihre Organisation Persistent Chat Server eingerichtet haben, geben Sie die Erstkonfiguration während der Bereitstellung. Möglicherweise gibt es jedoch vorkommen, dass Sie zum Implementieren von Persistent Chat Server Support ändern möchten. Beispielsweise müssen Sie die Unterstützung von Persistent Chat Server und Steuerelemente für ein bestimmtes Team oder eine Gruppe in der Organisation unterschiedlich einrichten. Dieser Abschnitt enthält Informationen und Vorgehensweisen zum Anpassen Ihrer Bereitstellung Persistent Chat Server. Ausführliche Informationen zu den Features und Funktionen, die Sie für Persistent Chat Server konfigurieren können, finden Sie unter [Planen von Persistent Chat Server in Skype für Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Weitere Informationen zum Bereitstellen von Persistent Chat Server finden Sie unter [Bereitstellen von Persistent Chat Server in Skype für Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
  
Sie können mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell-Cmdlets Persistent Chat Server verwalten. 
  
So verwenden Sie die Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Im Menü **Start** wählen Sie die Skype für Business Server-Systemsteuerung oder öffnen Sie ein Browserfenster, und geben Sie die Admin-URL.
    
3. Klicken Sie in der linken Navigationsleiste auf **Beständiger Chat**.
    
In der folgenden Tabelle werden die Windows PowerShell-Cmdlets zur einfacheren Verwaltung von Persistent Chat Server zusammengefasst. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|"New-cspersistentchatcategory"  <br/> |Erstellt eine neue Kategorie  <br/> |
|"Set-cspersistentchatcategory"  <br/> |Konfiguriert Einstellungen für eine vorhandene Kategorie  <br/> |
|"Get-cspersistentchatcategory"  <br/> |Ruft Informationen über Kategorien ab  <br/> |
|"Remove-cspersistentchatcategory"  <br/> |Entfernt eine Kategorie  <br/> |
|"New-cspersistentchatroom"  <br/> |Erstellt einen neuen Chatroom  <br/> |
|"Set-cspersistentchatroom"  <br/> |Konfiguriert Einstellungen für einen bestehenden Chatroom; weist dem Chatroom Benutzer und Benutzergruppen zu  <br/> |
|"Get-cspersistentchatroom"  <br/> |Ruft Informationen zu Chatrooms  <br/> |
|"Clear-cspersistentchatroom"  <br/> |Löscht einen Chatroom oder Nachrichten in einem Chatroom  <br/> |
|"Remove-cspersistentchatroom"  <br/> |Entfernt einen Chatroom  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Entfernt Nachrichten aus einem Chatroom  <br/> |
|"New-cspersistentchataddin"  <br/> |Erstellt ein neues Add-In  <br/> |
|"Set-cspersistentchataddin"  <br/> |Konfiguriert Einstellungen für ein vorhandenes Add-In  <br/> |
|"Get-cspersistentchataddin"  <br/> |Ruft Informationen über Add-Ins ab  <br/> |
|"Remove-cspersistentchataddin"  <br/> |Entfernt ein Add-In  <br/> |
|"Set-cspersistentchatcomplianceconfiguration"  <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Kompatibilitäten  <br/> |
|Export-CsPersistentChatData  <br/> |Exportiert Daten aus einer Datenbank für beständigen Chat  <br/> |
|Import-CsPersistentChatData  <br/> |Importiert Daten, die von einer früheren Version von Lync Server exportiert wurden  <br/> |
   

