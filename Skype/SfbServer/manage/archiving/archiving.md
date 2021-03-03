---
title: Verwalten der Archivierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Archivierung für Skype for Business Server verwalten.'
ms.openlocfilehash: 3c84fe35e59d14f957391ecb9bdc503e1bff6b87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817735"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Verwalten der Archivierung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Archivierung für Skype for Business Server verwalten.
  
Wenn Sie die Archivierung für Ihre Organisation bereitstellen, geben Sie die Erstkonfiguration während der Bereitstellung an. Es kann jedoch auch sein, dass Sie die Implementierung der Archivierungsunterstützung für die täglichen Verwaltung oder die Erfüllung neuer Anforderungen für Ihre Organisation ändern möchten. Möglicherweise müssen Sie die Archivierungsunterstützung für einen bestimmten Standort, einen bestimmten Pool oder bestimmte Benutzer in Ihrer Organisation unterschiedlich einrichten. Für Benutzer, die in Skype for Business Server zu Hause sind, erstellen und anpassen Sie archivierungskonfigurationsoptionen und Benutzerrichtlinien. 
  
Bevor Sie dieses Thema lesen, sollten Sie mit den Informationen in [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und Deploy archiving for Skype for Business Server vertraut [sein.](../../deploy/deploy-archiving/deploy-archiving.md)
  
> [!NOTE]
> Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung aktivieren, steuern Die Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange gespeichert sind und deren Postfächer im In-Place sind. Weitere Informationen finden Sie unter [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Archivierungskonfigurationsoptionen

Archivierungskonfigurationsoptionen geben an, ob:
  
- Aktivieren oder Deaktivieren der Archivierung
    
- IM-Sitzungen archivieren
    
- Archivieren von Webkonferenzsitzungen
    
- Blockieren von Aktivitäten, wenn die Archivierung nicht verfügbar ist
    
- Verwenden der Exchange-Integration
    
- Einrichten des Löschens und Exportierens von Daten
    
Diese Optionen können auf globaler, Standort- oder Poolebene festgelegt werden. Weitere Informationen finden Sie unter ["Verwalten von Archivierungsoptionen in Skype for Business Server".](options.md)
  
## <a name="archiving-policies"></a>Archivierungsrichtlinien

Archivierungsrichtlinien bestimmen, ob Folgendes archiviert werden soll:
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Diese Richtlinien können auf globaler, Standort- oder Benutzerebene festgelegt werden. Weitere Informationen finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Verwalten der Archivierung mithilfe der Systemsteuerung oder Windows PowerShell

Sie können die Archivierung mithilfe der Systemsteuerung oder mithilfe von Windows PowerShell. In der folgenden Tabelle sind die verfügbaren Cmdlets zusammengefasst, mit deren Hilfe Sie die Archivierung verwalten können. Einzelheiten zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server Management Shell](../management-shell.md). 


|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exportiert Datensätze, die in der Skype for Business Server-Archivierungsdatenbank gespeichert wurden.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den Archivierungskonfigurationseinstellungen in Ihrer Organisation zurück.  <br/> |
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu den Archivierungsrichtlinien Ihrer Organisation für die interne und externe Kommunikation zurück.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Weist Benutzern oder Benutzergruppen Archivierungsrichtlinien für Chatsitzungen zu. Diese Richtlinien bieten Ihnen die Möglichkeit, alle Nachrichtensitzungen zu archivieren, die zwischen internen Benutzern stattfinden, und/oder alle Im-Im-Sitzungen zu archivieren, die zwischen internen Benutzern und externen Partnern stattfinden.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Dient zum manuellen Löschen von Einträgen aus der Archivierungsdatenbank.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz von Chateinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatnachrichtensitzungen und zum Blockieren von Chatnachrichten verwendet werden können, die nicht archiviert werden können.  <br/> |
|New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Diese Richtlinien bieten Ihnen die Möglichkeit, alle Nachrichtensitzungen zu archivieren, die zwischen internen Benutzern stattfinden, und/oder alle Im-Im-Sitzungen zu archivieren, die zwischen internen Benutzern und externen Partnern stattfinden.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatsitzungen und zum optionalen Blockieren von Chatnachrichten verwendet werden, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Archivierungsrichtlinie für Chatnachrichten, die bestimmt, ob Skype for Business Server automatisch alle Chatnachrichtensitzungen zwischen internen Benutzern und/oder alle Chatnachrichtensitzungen zwischen internen Benutzern und Verbundpartnern speichern wird.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine vorhandene Auflistung von Archivierungsoptionen für Chatnachrichten.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Archivierungsrichtlinie für Chatnachrichten. Mit einer Archivierungsrichtlinie können Sie alle #A0 und -Konferenzen archivieren, die zwischen internen Benutzern stattfinden. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
|Set-CsArchivingServer  <br/> |Ermöglicht die Angabe eines neuen Datenbankspeicherorts für einen oder mehrere Archivierungsserver.  <br/> |
   

