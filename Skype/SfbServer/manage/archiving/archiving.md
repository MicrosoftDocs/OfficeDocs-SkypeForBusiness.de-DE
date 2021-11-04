---
title: Verwalten der Archivierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Archivierung für Skype for Business Server verwalten.'
ms.openlocfilehash: 4ab66b0abae48884935a3041c2fabed9124a9271
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768013"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Verwalten der Archivierung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Archivierung für Skype for Business Server verwalten.
  
Wenn Sie die Archivierung für Ihre Organisation bereitstellen, geben Sie die anfängliche Konfiguration während der Bereitstellung an. Es kann jedoch vorkommen, dass Sie die Implementierung der Archivierungsunterstützung für die tägliche Verwaltung ändern oder neue Anforderungen für Ihre Organisation erfüllen möchten. Beispielsweise müssen Sie die Archivierungsunterstützung für einen bestimmten Standort, einen bestimmten Pool oder bestimmte Benutzer in Ihrer Organisation möglicherweise anders einrichten. Für Benutzer, die auf Skype for Business Server verwaltet werden, erstellen und passen Sie Archivierungskonfigurationsoptionen und Benutzerrichtlinien an. 
  
Bevor Sie dieses Thema lesen, sollten Sie mit den Informationen in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Deploy archiving for [Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md)vertraut sein.
  
> [!NOTE]
> Wenn Sie die Integration von Microsoft Exchange für Ihre Bereitstellung aktivieren, steuern Exchange Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange verwaltet werden und deren Postfächer In-Place Haltebereich haben. Ausführliche Informationen finden Sie unter [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for [Skype for Business Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md) 
  
## <a name="archiving-configuration-options"></a>Archivierungskonfigurationsoptionen

Archivierungskonfigurationsoptionen geben an, ob:
  
- Aktivieren oder Deaktivieren der Archivierung
    
- IM-Sitzungen archivieren
    
- Archivieren von Webkonferenzsitzungen
    
- Blockieren von Aktivitäten, wenn die Archivierung nicht verfügbar ist
    
- Verwenden Exchange Integration
    
- Einrichten des Löschens und Exportierens von Daten
    
Diese Optionen können auf globaler, Standort- oder Poolebene festgelegt werden. Weitere Informationen finden Sie unter [Verwalten von Archivierungsoptionen in Skype for Business Server.](options.md)
  
## <a name="archiving-policies"></a>Archivierungsrichtlinien

Archivierungsrichtlinien bestimmen, ob Folgendes archiviert werden soll:
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Diese Richtlinien können auf globaler, Standort- oder Benutzerebene festgelegt werden. Weitere Informationen finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype for Business Server.](policies.md)
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Verwalten der Archivierung mithilfe der Systemsteuerung oder mit Windows PowerShell

Sie können die Archivierung mithilfe der Systemsteuerung oder mit Windows PowerShell verwalten. In der folgenden Tabelle sind die cmdlets zusammengefasst, die Ihnen bei der Verwaltung der Archivierung zur Verfügung stehen. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server Verwaltungsshell.](../management-shell.md) 


|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exportiert Datensätze, die in der Skype for Business Server Archivierungsdatenbank gespeichert wurden.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den Archivierungskonfigurationseinstellungen in Ihrer Organisation zurück.  <br/> |
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu den Archivierungsrichtlinien Ihrer Organisation für die interne und externe Kommunikation zurück.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Weist Benutzern oder Benutzergruppen Archivierungsrichtlinien für Chatsitzungen zu. Mit diesen Richtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern stattfinden, und/oder alle Chatsitzungen archivieren, die zwischen internen Benutzern und externen Partnern stattfinden.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Dient zum manuellen Löschen von Einträgen aus der Archivierungsdatenbank.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz von Chateinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatsitzungen und zum Blockieren von Chatnachrichten verwendet werden können, die nicht archiviert werden können.  <br/> |
|New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Mit diesen Richtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern stattfinden, und/oder alle Chatsitzungen archivieren, die zwischen internen Benutzern und externen Partnern stattfinden.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatsitzungen verwendet werden, und um optional alle Chatnachrichten zu blockieren, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Archivierungsrichtlinie für Chatnachrichten, die bestimmt, ob Skype for Business Server automatisch alle Chatsitzungen speichert, die zwischen internen Benutzern und/oder allen Chatsitzungen zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine vorhandene Sammlung von Archivierungsoptionen für Chatnachrichten.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Archivierungsrichtlinie für Chatnachrichten. Mit einer Archivierungsrichtlinie können Sie alle Chatsitzungen und Konferenzen archivieren, die zwischen internen Benutzern stattfinden. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
|Set-CsArchivingServer  <br/> |Ermöglicht die Angabe eines neuen Datenbankspeicherorts für einen oder mehrere Archivierungsserver.  <br/> |
   

