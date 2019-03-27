---
title: Verwalten der Archivierung in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Zusammenfassung: Informationen Sie zum Verwalten der Archivierung für Skype für Business Server.'
ms.openlocfilehash: 19d8d7eb6a2cd92bb4132d5dfe7703995b1056b9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875236"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Verwalten der Archivierung in Skype für Business Server

**Zusammenfassung:** Informationen Sie zum Verwalten der Archivierung für Skype für Business Server.
  
Die ursprüngliche Konfiguration wird beim Bereitstellen der Archivierung in Ihrer Organisation vorgenommen. Zu einem späteren Zeitpunkt kann es jedoch wünschenswert oder notwendig sein, die Implementierung der Archivierungsunterstützung an alltägliche Verwaltungsvorgänge oder neue Herausforderungen anzupassen. Beispielsweise kann es sein, dass Sie die Archivierungsunterstützung für einen bestimmten Standort, einen bestimmten Pool oder bestimmte Benutzer in Ihrer Organisation verändern müssen. Für Benutzer in Skype für Business Server verwaltet werden, Sie zu diesem Zweck erstellen und Anpassen von Archivierungsoptionen für Konfiguration und Benutzerrichtlinien. 
  
Bevor Sie dieses Thema lesen, sollten Sie darauf achten Sie, dass Sie mit den Informationen im [für die Archivierung in Skype für Business Server planen](../../plan-your-deployment/archiving/archiving.md) und [Bereitstellen Archivierung für Skype für Business Server](../../deploy/deploy-archiving/deploy-archiving.md)vertraut sind.
  
> [!NOTE]
> Wenn Sie für Ihre Bereitstellung die Microsoft Exchange-Integration aktiviert haben, wird mithilfe von Exchange-Richtlinien gesteuert, ob die Archivierung für die Benutzer aktiviert ist, die Exchange zugeordnet sind und deren Postfächer im Compliance-Archiv platziert sind. Weitere Informationen hierzu finden Sie unter [Planen für die Archivierung in Skype für Business Server](../../plan-your-deployment/archiving/archiving.md) und [Integration mit Exchange-Speicher für Skype für Business Server konfigurieren](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Optionen für die Archivierungskonfiguration

Mit den Optionen für die Archivierungskonfiguration können Sie Folgendes festlegen:
  
- Archivierung aktivieren oder deaktivieren
    
- Chatsitzungen archivieren
    
- Webkonferenzsitzungen archivieren
    
- Aktivitäten blockieren, wenn keine Archivierung verfügbar ist
    
- Exchange-Integration verwenden
    
- Löschen und Exportieren von Daten einrichten
    
Diese Optionen können auf globaler, Standort- oder Poolebene festgelegt werden. Weitere Informationen finden Sie unter [Archivierungsoptionen in Skype für Business Server verwalten](options.md).
  
## <a name="archiving-policies"></a>Archivierungsrichtlinien

Archivierungsrichtlinien bestimmen, ob die folgenden archiviert:
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Diese Richtlinien können auf globaler, Standort- oder Poolebene festgelegt werden. Weitere Informationen finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype für Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Archivierungsverwaltung mithilfe der Systemsteuerung oder von Windows-PowerShell

Sie können die Archivierung mit der Systemsteuerung oder Windows-PowerShell verwalten. In der folgenden Tabelle finden Sie einen Überblick über die zur Archivierungsverwaltung verfügbaren Cmdlets. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter finden Sie unter [Skype für Business Server-Verwaltungsshell](../management-shell.md). 


|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exportiert die Datensätze, die in der Skype für Business Server-Archivierungsdatenbank gespeichert wurden.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konfigurationseinstellungen zurück.  <br/> |
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Archivierungsrichtlinien für interne und externe Kommunikationen zurück.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Instant messaging (IM) Sitzung Archivierungsrichtlinien für Benutzer oder Gruppen von Benutzern zugewiesen. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Dient zum manuellen Löschen von Einträgen aus der Archivierungsdatenbank.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz mit Chatnachrichteneinstellungen. Diese Einstellungen dienen zum Aktivieren bzw. Deaktivieren der automatischen Speicherung von Chatsitzungen. Sie ermöglichen ferner das Blockieren von Chatnachrichten, die nicht archiviert werden können.  <br/> |
|New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen. Archivierungseinstellungen dienen zum Aktivieren und Deaktivieren des automatischen Speicherns von Chatsitzungen sowie zum optionalen Sperren aller Chatnachrichten, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Sofortnachrichten (Instant messaging) Archivierungsrichtlinie, der bestimmt, ob Skype für Business Server automatisch alle Sofortnachrichtensitzungen gespeichert, die zwischen internen Benutzern und/oder alle Sofortnachrichtensitzungen zwischen internen Benutzern und Verbundpartner stattfinden.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine bestehende Auflistung von Archivierungseinstellungen für Chatnachrichten.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Sofortnachrichten (Instant messaging) Archivierungsrichtlinie. Eine Archivierungsrichtlinie bietet die Möglichkeit, alle IM-Sitzungen und Konferenzen, die stattfinden zwischen internen Benutzern archivieren. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartner stattfinden.  <br/> |
|Set-CsArchivingServer  <br/> |Ermöglicht Ihnen die Angabe eines neuen Datenbankpfads für einen oder mehrere Archivierungsserver.  <br/> |
   

