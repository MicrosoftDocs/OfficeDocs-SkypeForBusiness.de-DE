---
title: Verwalten der Archivierung in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 63fd56cf-6d40-4db5-96fc-32d813930bcf
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Archivierung für Skype for Business Server verwalten.'
ms.openlocfilehash: 46b0937a00f289ad5383d3bb1a4acf890bf48390
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818997"
---
# <a name="manage-archiving-in-skype-for-business-server"></a>Verwalten der Archivierung in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie die Archivierung für Skype for Business Server verwalten.
  
Die ursprüngliche Konfiguration wird beim Bereitstellen der Archivierung in Ihrer Organisation vorgenommen. Zu einem späteren Zeitpunkt kann es jedoch wünschenswert oder notwendig sein, die Implementierung der Archivierungsunterstützung an alltägliche Verwaltungsvorgänge oder neue Herausforderungen anzupassen. Beispielsweise kann es sein, dass Sie die Archivierungsunterstützung für einen bestimmten Standort, einen bestimmten Pool oder bestimmte Benutzer in Ihrer Organisation verändern müssen. Für Benutzer, die sich in Skype for Business Server befinden, erstellen und Anpassen von Archivierungs Konfigurationsoptionen und Benutzerrichtlinien. 
  
Bevor Sie dieses Thema lesen, stellen Sie sicher, dass Sie mit den Informationen in [Plan für die Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) vertraut sind und die [Archivierung für Skype for Business Server bereitstellen](../../deploy/deploy-archiving/deploy-archiving.md).
  
> [!NOTE]
> Wenn Sie für Ihre Bereitstellung die Microsoft Exchange-Integration aktiviert haben, wird mithilfe von Exchange-Richtlinien gesteuert, ob die Archivierung für die Benutzer aktiviert ist, die Exchange zugeordnet sind und deren Postfächer im Compliance-Archiv platziert sind. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) und [Konfigurieren der Integration in Exchange Storage für Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md). 
  
## <a name="archiving-configuration-options"></a>Optionen für die Archivierungskonfiguration

Mit den Optionen für die Archivierungskonfiguration können Sie Folgendes festlegen:
  
- Archivierung aktivieren oder deaktivieren
    
- Chatsitzungen archivieren
    
- Webkonferenzsitzungen archivieren
    
- Aktivitäten blockieren, wenn keine Archivierung verfügbar ist
    
- Exchange-Integration verwenden
    
- Löschen und Exportieren von Daten einrichten
    
Diese Optionen können auf globaler, Standort- oder Poolebene festgelegt werden. Weitere Informationen finden Sie unter [Verwalten von Archivierungsoptionen in Skype for Business Server](options.md).
  
## <a name="archiving-policies"></a>Archivierungsrichtlinien

Archivierungsrichtlinien legen fest, ob Folgendes archiviert werden soll:
  
- Interne Kommunikation
    
- Externe Kommunikation
    
Diese Richtlinien können auf globaler, Standort- oder Poolebene festgelegt werden. Weitere Informationen finden Sie unter [Verwalten von Archivierungsrichtlinien in Skype for Business Server](policies.md).
  
## <a name="manage-archiving-by-using-the-control-panel-or-by-using-windows-powershell"></a>Archivierungsverwaltung mithilfe der Systemsteuerung oder von Windows-PowerShell

Sie können die Archivierung mit der Systemsteuerung oder Windows-PowerShell verwalten. In der folgenden Tabelle finden Sie einen Überblick über die zur Archivierungsverwaltung verfügbaren Cmdlets. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server-Verwaltungsshell](../management-shell.md). 


|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Export-CsArchivingData  <br/> |Exportiert Datensätze, die in der Skype for Business Server-Archivierungsdatenbank gespeichert wurden.  <br/> |
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konfigurationseinstellungen zurück.  <br/> |
|Get-CsArchivingPolicy  <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Archivierungsrichtlinien für interne und externe Kommunikationen zurück.  <br/> |
|Grant-CsArchivingPolicy  <br/> |Weist Benutzern oder Gruppen von Benutzern Chat-Archivierungsrichtlinien für Sofortnachrichten (im) zu. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Invoke-CsArchivingDatabasePurge  <br/> |Dient zum manuellen Löschen von Einträgen aus der Archivierungsdatenbank.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz mit Chatnachrichteneinstellungen. Diese Einstellungen dienen zum Aktivieren bzw. Deaktivieren der automatischen Speicherung von Chatsitzungen. Sie ermöglichen ferner das Blockieren von Chatnachrichten, die nicht archiviert werden können.  <br/> |
|New-CsArchivingPolicy  <br/> |Erstellt neue Archivierungsrichtlinien für Chatsitzungen. Mithilfe dieser Archivierungsrichtlinien können Sie alle Chatsitzungen archivieren, die zwischen internen Benutzern und/oder zwischen internen und externen Benutzern stattfinden.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen. Archivierungseinstellungen dienen zum Aktivieren und Deaktivieren des automatischen Speicherns von Chatsitzungen sowie zum optionalen Sperren aller Chatnachrichten, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingPolicy  <br/> |Entfernt die angegebene Sofortnachrichten-Archivierungsrichtlinie, die bestimmt, ob Skype for Business Server automatisch alle Chatsitzungen speichert, die zwischen internen Benutzern und/oder allen Chatsitzungen zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine bestehende Auflistung von Archivierungseinstellungen für Chatnachrichten.  <br/> |
|Set-CsArchivingPolicy  <br/> |Ändert eine vorhandene Instant Messaging-Archivierungsrichtlinie (im). Eine Archivierungsrichtlinie bietet Ihnen die Möglichkeit, alle Chatsitzungen und Konferenzen zu archivieren, die zwischen internen Benutzern stattfinden. Sie können auch Sitzungen archivieren, die zwischen internen Benutzern und Verbundpartnern stattfinden.  <br/> |
|Set-CsArchivingServer  <br/> |Ermöglicht Ihnen die Angabe eines neuen Datenbankpfads für einen oder mehrere Archivierungsserver.  <br/> |
   

