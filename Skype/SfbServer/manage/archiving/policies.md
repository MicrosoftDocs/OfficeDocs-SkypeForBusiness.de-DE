---
title: Verwalten von Archivierungsrichtlinien in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Zusammenfassung: Informationen Sie zum Verwalten von Benutzerrichtlinien für die Archivierung für Skype für Business Server 2015.'
ms.openlocfilehash: 584849862e106098bc4bbad92ed4e0b87be410e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-archiving-policies-in-skype-for-business-server-2015"></a>Verwalten von Archivierungsrichtlinien in Skype for Business Server 2015

**Zusammenfassung:** Informationen Sie zum Verwalten von Benutzerrichtlinien für die Archivierung für Skype für Business Server 2015.
  
Zunächst eingerichtet werden Archivierungsrichtlinien, wenn Sie die Archivierung bereitstellen, jedoch können Sie ändern, hinzufügen und Löschen von Konfigurationen nach der Bereitstellung. Archivierungsrichtlinien bestimmen, ob das archivieren: 
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Archivierungsrichtlinien kann Set auf globaler, Standort- oder Benutzerebene sein.
  
> [!NOTE]
> Wenn Sie Microsoft Exchange-Integration für die Bereitstellung, Exchange-Richtlinien Steuerelement aktiviert, ob Archivierung aktiviert ist, für die Benutzer, die sich auf Exchange befinden und haben ihren Postfächern zu Compliance-Archiv platzieren. Weitere Informationen hierzu finden Sie unter [Planen für die Archivierung in Skype für Business Server 2015](../../plan-your-deployment/archiving/archiving.md) und [Integration mit Exchange-Speicher für Skype für Business Server 2015 konfigurieren](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a>Verwalten von Archivierungsrichtlinien über die Systemsteuerung

Sie können Archivierungsrichtlinien wie folgt mit der Systemsteuerung verwalten:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Archivierungsrichtlinie**.
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a>Verwalten von Archivierungsrichtlinien mit Windows PowerShell

Sie können die Archivierungsrichtlinien auch mithilfe der in der folgenden Tabelle aufgeführten Windows PowerShell-Cmdlets konfigurieren. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter finden Sie unter [Skype für Business Server 2015-Verwaltungsshell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu Archivierungsrichtlinien für Chatsitzungen zurück.  <br/> |
|GRANT-CsArchivingPolicy  <br/> |Instant messaging (IM) Sitzung Archivierungsrichtlinien für Benutzer oder Gruppen von Benutzern zugewiesen. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Mit New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Sofortnachrichten (Instant messaging) Archivierungsrichtlinie, der bestimmt, ob Skype für Business Server automatisch alle Sofortnachrichtensitzungen gespeichert, die zwischen internen Benutzern und/oder alle Sofortnachrichtensitzungen zwischen internen Benutzern und Verbundpartner stattfinden.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Sofortnachrichten (Instant messaging) Archivierungsrichtlinie. Eine Archivierungsrichtlinie bietet die Möglichkeit, alle IM-Sitzungen und Konferenzen, die stattfinden zwischen internen Benutzern archivieren. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartner stattfinden.  <br/> |
   

