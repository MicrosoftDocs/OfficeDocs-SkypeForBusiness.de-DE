---
title: Verwalten von Archivierungsoptionen in Skype for Business Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Zusammenfassung: Erfahren Sie, wie Sie Archivierungsoptionen für Skype for Business Server konfigurieren.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817535"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a>Verwalten von Archivierungsoptionen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Archivierungsoptionen für Skype for Business Server konfigurieren.
  
Sie konfigurieren die Archivierung zunächst bei der Bereitstellung, können konfigurationen jedoch nach der Bereitstellung ändern, hinzufügen und löschen. Archivierungsoptionen bestimmen, ob: 
  
- Aktivieren oder Deaktivieren der Archivierung
    
- IM-Sitzungen archivieren
    
- Archivieren von Webkonferenzsitzungen
    
- Blockieren von Aktivitäten, wenn die Archivierung nicht verfügbar ist
    
- Verwenden der Exchange-Integration
    
- Einrichten des Löschens und Exportierens von Daten
    
Sie können Konfigurationsoptionen auf den folgenden Ebenen angeben:
  
- Konfiguration auf globaler Ebene, die standardmäßig bei der Bereitstellung von Skype for Business Server erstellt wird
    
- Optionale Konfigurationen auf Standortebene, die angeben, wie die Archivierung für einen bestimmten Standort implementiert wird
    
- Optionale Konfigurationen auf Poolebene, die angeben, wie die Archivierung für einen bestimmten Pool implementiert wird
    
Sie können eine Standort- oder Poolkonfiguration löschen, die globale Konfiguration jedoch nicht. Wenn Sie die globale Konfiguration löschen, werden automatisch die Standardwerte wieder hergestellt. Weitere Informationen zur Implementierung von Archivierungskonfigurationen und zur Hierarchie der Archivierungskonfigurationen finden Sie unter "Planen der Archivierung [in Skype for Business Server".](../../plan-your-deployment/archiving/archiving.md)
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>Konfigurieren von Archivierungsoptionen mithilfe der Systemsteuerung

Sie können Die Archivierungsoptionen mithilfe der Systemsteuerung wie folgt konfigurieren:
  
1. Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an. 
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen. 
    
3. Klicken Sie in der linken Navigationsleiste auf **"Archivierungskonfiguration".**
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>Konfigurieren von Archivierungsoptionen mithilfe von Windows PowerShell

Sie können Archivierungsoptionen auch mithilfe der Windows PowerShell in der folgenden Tabelle aufgeführten Cmdlets konfigurieren. Einzelheiten zur Syntax, einschließlich aller verfügbaren Parameter, finden Sie unter [Skype for Business Server Management Shell](../management-shell.md).
  

|**Cmdlet**|**Beschreibung**|
|:-----|:-----|
|Get-CsArchivingConfiguration  <br/> |Gibt Informationen zu den Archivierungskonfigurationseinstellungen in Ihrer Organisation zurück.  <br/> |
|New-CsArchivingConfiguration  <br/> |Erstellt einen neuen Satz von Chateinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatnachrichtensitzungen und zum Blockieren von Chatnachrichten verwendet werden können, die nicht archiviert werden können.  <br/> |
|Remove-CsArchivingConfiguration  <br/> |Entfernt die angegebene Auflistung von Archivierungseinstellungen, die zum Aktivieren oder Deaktivieren des automatischen Speicherns von Chatsitzungen und zum optionalen Blockieren von Chatnachrichten verwendet werden, die nicht archiviert werden können.  <br/> |
|Set-CsArchivingConfiguration  <br/> |Ändert eine vorhandene Auflistung von Archivierungsoptionen für Chatnachrichten.  <br/> |
