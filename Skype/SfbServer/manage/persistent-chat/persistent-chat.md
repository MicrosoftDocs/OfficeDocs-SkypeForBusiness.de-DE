---
title: Verwalten des Servers für beständigen Chat in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 verwalten.'
ms.openlocfilehash: 97cce8adedbb4dea932084497006e3c17bfdd7d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817321"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 verwalten.
  
Wenn Sie den Server für beständigen Chat für Ihre Organisation einrichten, geben Sie die anfängliche Konfiguration während der Bereitstellung an. Es kann jedoch vorkommen, dass Sie ändern möchten, wie Sie die Unterstützung für beständigen Chat Server implementieren. So können Sie beispielsweise für ein bestimmtes Team oder eine bestimmte Gruppe in Ihrer Organisation die Unterstützung für beständigen Chat Server und die Steuerelemente anders einrichten. Dieser Abschnitt enthält Informationen und Verfahren, die Ihnen bei der Anpassung ihrer beständigen Chat Server Bereitstellung helfen. Details zu den Features und Funktionen, die Sie für den Server für beständigen Chat konfigurieren können, finden Sie unter [Planen des beständigen Chat Servers in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Ausführliche Informationen zum Bereitstellen von beständigen Chatservern finden Sie unter [Bereitstellen eines beständigen Chat Servers in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Der beständige Chat ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. In Teams steht dieselbe Funktionalität zur Verfügung. Weitere Informationen finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](/microsoftteams/upgrade-start-here). Wenn Sie den beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktion für Teams benötigen, oder die Verwendung von Skype for Business Server 2015 fortsetzen. 
  
Sie können den Server für beständigen Chat über die Systemsteuerung oder mithilfe von Windows PowerShell-Cmdlets verwalten. 
  
So verwenden Sie die Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, das über die Rolle „CsPersistentChatAdministrator“ oder „CsAdministrator-Rolle“ verfügt, bei einem Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie im **Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **beständigen Chat**.
    
In der folgenden Tabelle sind die Windows PowerShell-Cmdlets zusammengefasst, die Ihnen bei der Verwaltung des beständigen Chat Servers helfen. Ausführliche Informationen zur Syntax einschließlich aller Parameter finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Erstellt eine neue Kategorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Konfiguriert Einstellungen für eine vorhandene Kategorie  <br/> |
|Get-CsPersistentChatCategory  <br/> |Ruft Informationen über Kategorien ab  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Entfernt eine Kategorie  <br/> |
|New-CsPersistentChatRoom  <br/> |Erstellt einen neuen Chatroom  <br/> |
|Set-CsPersistentChatRoom  <br/> |Konfiguriert Einstellungen für einen bestehenden Chatroom; weist dem Chatroom Benutzer und Benutzergruppen zu  <br/> |
|Get-CsPersistentChatRoom  <br/> |Ruft Informationen zu Räumen ab  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Löscht einen Chatroom oder Nachrichten in einem Chatroom  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Entfernt einen Chatroom  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Entfernt Nachrichten aus einem Chatroom  <br/> |
|New-CsPersistentChatAddin  <br/> |Erstellt ein neues Add-In  <br/> |
|Set-CsPersistentChatAddin  <br/> |Konfiguriert Einstellungen für ein vorhandenes Add-In  <br/> |
|Get-CsPersistentChatAddin  <br/> |Ruft Informationen über Add-Ins ab  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Entfernt ein Add-In  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Ändert eine vorhandene Auflistung von Konfigurationseinstellungen für Kompatibilitäten  <br/> |
|Export-CsPersistentChatData  <br/> |Exportiert Daten aus einer Datenbank für beständigen Chat  <br/> |
|Import-CsPersistentChatData  <br/> |Importiert Daten, die von einer früheren Version von Lync Server exportiert wurden  <br/> |
   

