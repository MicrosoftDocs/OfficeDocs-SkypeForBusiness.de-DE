---
title: Verwalten des Servers für beständigen Chat in Skype for Business Server 2015
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
ms.assetid: c58ee4f4-563b-4d0c-be91-c62df886caa9
description: 'Zusammenfassung: Informationen zum Verwalten des Servers für beständigen Chat in Skype for Business Server 2015.'
ms.openlocfilehash: 9a97511f9b4c2adae7ead816e86876f05dd39790
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832885"
---
# <a name="manage-persistent-chat-server-in-skype-for-business-server-2015"></a>Verwalten des Servers für beständigen Chat in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie Sie den Server für beständigen Chat in Skype for Business Server 2015 verwalten.
  
Wenn Sie den Server für beständigen Chat für Ihre Organisation einrichten, geben Sie die Erstkonfiguration während der Bereitstellung an. Es kann jedoch auch sein, dass Sie die Implementierung der Unterstützung für den Server für beständigen Chat ändern möchten. Möglicherweise müssen Sie die Unterstützung für den Server für beständigen Chat und die Steuerelemente für ein bestimmtes Team oder eine bestimmte Gruppe in Ihrer Organisation unterschiedlich einrichten. Dieser Abschnitt enthält Informationen und Verfahren, mit deren Hilfe Sie Die Bereitstellung des Servers für beständigen Chat anpassen können. Details zu den Features und Funktionen, die Sie für den Server für beständigen Chat konfigurieren können, finden Sie unter [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Weitere Informationen zum Bereitstellen des Servers für beständigen Chat finden Sie unter [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 

> [!NOTE]
> Beständiger Chat ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die gleiche Funktionalität ist in Teams verfügbar. Weitere Informationen finden Sie unter ["Erste Schritte mit Ihrem Microsoft Teams-Upgrade".](/microsoftteams/upgrade-start-here) Wenn Sie beständigen Chat verwenden müssen, können Sie entweder Benutzer migrieren, die diese Funktionalität benötigen, zu Teams migrieren oder Skype for Business Server 2015 weiterhin verwenden. 
  
Sie können den Server für beständigen Chat mithilfe der Systemsteuerung oder mithilfe Windows PowerShell verwalten. 
  
So verwenden Sie die Systemsteuerung:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsPersistentChatAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.
    
2. Wählen Sie **im Startmenü** die Skype for Business Server-Systemsteuerung aus, oder öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein.
    
3. Klicken Sie in der linken Navigationsleiste auf **"Beständiger Chat".**
    
In der folgenden Tabelle sind die Windows PowerShell cmdlets zusammengefasst, die Ihnen bei der Verwaltung des Servers für beständigen Chat helfen. Einzelheiten zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Erstellt eine neue Kategorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Konfiguriert Einstellungen für eine vorhandene Kategorie  <br/> |
|Get-CsPersistentChatCategory  <br/> |Ruft Informationen zu Kategorien ab  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Entfernt eine Kategorie  <br/> |
|New-CsPersistentChatRoom  <br/> |Erstellt einen neuen Chatroom  <br/> |
|Set-CsPersistentChatRoom  <br/> |Konfiguriert Einstellungen für einen vorhandenen Raum. Zuweisen von Benutzern und Benutzergruppen zum Raum  <br/> |
|Get-CsPersistentChatRoom  <br/> |Ruft Informationen zu Räumen ab  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Entfernt einen Raum oder Nachrichten aus einem Raum  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Entfernt einen Raum  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Entfernt Nachrichten aus einem Raum  <br/> |
|New-CsPersistentChatAddin  <br/> |Erstellt ein neues Add-In  <br/> |
|Set-CsPersistentChatAddin  <br/> |Konfiguriert Einstellungen für ein vorhandenes Add-In  <br/> |
|Get-CsPersistentChatAddin  <br/> |Ruft Informationen zu Add-Ins ab  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Entfernt ein Add-In  <br/> |
|Set-CsPersistentChatComplianceConfiguration  <br/> |Ändert eine vorhandene Auflistung von Kompatibilitätskonfigurationseinstellungen  <br/> |
|Export-CsPersistentChatData  <br/> |Exportiert Daten aus einer Datenbank für beständigen Chat  <br/> |
|Import-CsPersistentChatData  <br/> |Importiert Daten, die aus einer früheren Version von Lync Server exportiert wurden  <br/> |
   

