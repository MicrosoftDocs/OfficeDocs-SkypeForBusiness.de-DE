---
title: Verwalten von Archivierungsoptionen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Zusammenfassung: Erfahren Sie, wie Sie Archivierungsoptionen für Skype for Business Server konfigurieren.'
---

# <a name="manage-archiving-options-in-skype-for-business-server"></a>Verwalten von Archivierungsoptionen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Archivierungsoptionen für Skype for Business Server konfigurieren.
  
Sie konfigurieren die Archivierung zunächst bei der Bereitstellung, aber Sie können Konfigurationen nach der Bereitstellung ändern, hinzufügen und löschen. Archivierungsoptionen bestimmen Folgendes: 
  
- Aktivieren oder Deaktivieren der Archivierung
    
- IM-Sitzungen archivieren
    
- Archivieren von Webkonferenzsitzungen
    
- Blockieren von Aktivitäten, wenn die Archivierung nicht verfügbar ist
    
- Verwenden Exchange Integration
    
- Einrichten des Löschens und Exportierens von Daten
    
Sie können Konfigurationsoptionen auf den folgenden Ebenen angeben:
  
- Konfiguration auf globaler Ebene, die standardmäßig erstellt wird, wenn Sie Skype for Business Server
    
- Optionale Konfigurationen auf Standortebene, die angeben, wie die Archivierung für einen bestimmten Standort implementiert wird
    
- Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird
    
Sie können eine Standort- oder Poolkonfiguration löschen, die globale Konfiguration jedoch nicht. Wenn Sie die globale Konfiguration löschen, werden automatisch die Standardwerte wieder hergestellt. Ausführliche Informationen zur Implementierung von Archivierungskonfigurationen und zur Hierarchie der Archivierungskonfigurationen finden Sie unter [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Konfigurieren von Archivierungsoptionen mithilfe der Systemsteuerung

Sie können Archivierungsoptionen mithilfe der Systemsteuerung wie folgt konfigurieren:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **"Archivierungskonfiguration**".
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Konfigurieren von Archivierungsoptionen mithilfe von Windows PowerShell

Sie können Archivierungsoptionen auch mithilfe der in der folgenden Tabelle aufgeführten cmdlets Windows PowerShell konfigurieren. Ausführliche Informationen zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server Verwaltungsshell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den Archivierungskonfigurationseinstellungen in Ihrer Organisation zurück.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz von Chateinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatsitzungen und zum Blockieren von Chatnachrichten verwendet werden können, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatsitzungen verwendet werden, und um optional alle Chatnachrichten zu blockieren, die nicht archiviert werden können.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine vorhandene Sammlung von Archivierungsoptionen für Chatnachrichten.  <br/> |
