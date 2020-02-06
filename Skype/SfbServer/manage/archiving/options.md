---
title: Verwalten von Archivierungsoptionen in Skype for Business Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Archivierungsoptionen für Skype for Business Server konfigurieren.'
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818897"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Verwalten von Archivierungsoptionen in Skype for Business Server

**Zusammenfassung:** Hier erfahren Sie, wie Sie Archivierungsoptionen für Skype for Business Server konfigurieren.
  
Zunächst konfigurieren Sie die Archivierung bei der Bereitstellung, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Archivierungsoptionen legen fest, ob: 
  
- Archivierung aktivieren oder deaktivieren
    
- Chatsitzungen archivieren
    
- Webkonferenzsitzungen archivieren
    
- Aktivitäten blockieren, wenn keine Archivierung verfügbar ist
    
- Exchange-Integration verwenden
    
- Löschen und Exportieren von Daten einrichten
    
Sie können Konfigurationsoptionen auf den folgenden Ebenen festlegen:
  
- Konfiguration auf globaler Ebene, die standardmäßig bei der Bereitstellung von Skype for Business Server erstellt wird
    
- Optionale Konfigurationen auf Standortebene, um anzugeben, wie die Archivierung für einen bestimmten Standort implementiert wird
    
- Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird
    
Standort- oder Poolkonfigurationen können gelöscht werden, nicht aber die globale Konfiguration. Wenn Sie die globale Konfiguration löschen, wird sie automatisch auf die Standardwerte zurückgesetzt. Einzelheiten zur Implementierung von Archivierungs Konfigurationen und zur Hierarchie der Archivierungs Konfigurationen finden Sie unter [Planen der Archivierung in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Konfigurieren von Archivierungsoptionen mit der Systemsteuerung

Sie können die Archivierungsoptionen wie folgt mit der Systemsteuerung konfigurieren:
  
1. Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsArchivingAdministrator“ oder „CsAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **Archivierungskonfiguration**.
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Konfigurieren von Archivierungsoptionen mit Windows PowerShell

Sie können die Archivierungsoptionen auch mithilfe der in der folgenden Tabelle aufgeführten Windows PowerShell-Cmdlets konfigurieren. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server-Verwaltungsshell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den in Ihrer Organisation verwendeten Konfigurationseinstellungen zurück.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz mit Chatnachrichteneinstellungen. Diese Einstellungen dienen zum Aktivieren bzw. Deaktivieren der automatischen Speicherung von Chatsitzungen. Sie ermöglichen ferner das Blockieren von Chatnachrichten, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen. Archivierungseinstellungen dienen zum Aktivieren und Deaktivieren des automatischen Speicherns von Chatsitzungen sowie zum optionalen Sperren aller Chatnachrichten, die nicht archiviert werden können.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine bestehende Auflistung von Optionen zur Archivierungskonfiguration für Chatnachrichten.  <br/> |
