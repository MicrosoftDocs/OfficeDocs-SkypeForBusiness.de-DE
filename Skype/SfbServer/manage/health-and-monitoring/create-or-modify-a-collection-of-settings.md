---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für cdR in Skype for Business Server
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Zusammenfassung: Informationen zur Aufzeichnung von Anrufdetails (CdR) in Skype for Business Server.'
ms.openlocfilehash: da4383ef31b2d3ee781c445f2c935b79ea89bed8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095369"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für cdR in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Aufzeichnung von Anrufdetails (CdR) in Skype for Business Server.
  
Mit der Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) können Sie die Verwendung von Peer-zu-Peer-Chatsitzungen, VoIP-Telefonanrufen (Voice over Internet Protocol) und Konferenzanrufen nachverfolgen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne, globale Auflistung von Konfigurationseinstellungen für cdR für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise Standorteinstellungen für den Standort "Redmond" erstellen, werden diese Einstellungen (anstelle der globalen Einstellungen) zum Verwalten von CDR in Redmond verwendet.
  
Sie können Konfigurationseinstellungen für KDS entweder mit der Skype for Business Server-Systemsteuerung oder dem [Cmdlet New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) erstellen. Sie können die Skype for Business Server-Systemsteuerung oder das [Cmdlet Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) verwenden, um vorhandene Einstellungen zu ändern. Wenn Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:
  
|**Benutzeroberflächeneinstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutiger Bezeichner für die zu erstellende CdR-Konfigurationseinstellungen. Diese Einstellungen können nur auf Standortbereich erstellt werden.  <br/> |
|Aktivieren der Überwachung von CDRs  <br/> |EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist.  <br/> |
|Aktivieren der Bereinigung von CDRs  <br/> |EnablePurging  <br/> |Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.  <br/> |
|CdRs für maximale Dauer (Tage) behalten  <br/> |KeepCallDetailForDays  <br/> |Gibt die Anzahl der Tage an, die CDR-Einträge in der CDR-Datenbank aufbewahrt werden. Alle Datensätze, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. (Beachten Sie, dass die Bereinigung nur erfolgt, wenn die Bereinigung aktiviert wurde.)  <br/> |
|Bewahren Sie Fehlerberichtsdaten für maximale Dauer (Tage) auf.  <br/> |KeepErrorReportForDays  <br/> |Gibt die Anzahl der Tage an, die CdR-Fehlerberichte aufbewahrt werden. Alle Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.  <br/> |
   
> [!NOTE]
> Die New-CsCdrConfiguration und Set-CsCdrConfiguration enthalten zusätzliche Optionen, die in der Skype for Business Server-Systemsteuerung nicht verfügbar sind. Weitere Informationen finden Sie in den [Hilfethemen New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) und [Set-CsCdrConfiguration.](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie Konfigurationseinstellungen für cdR mithilfe der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Skype for Business Server-Systemsteuerung **auf Überwachung und Archivierung.**
    
2. Klicken Sie **auf der** Registerkarte Aufzeichnung von Anrufdetails auf **Neu**.
    
3. Wählen Sie **im Dialogfeld Website** auswählen die Website aus, auf der die neuen Konfigurationseinstellungen erstellt werden sollen. Wenn das Dialogfeld leer ist, bedeutet dies, dass allen Websites bereits eine Auflistung von Konfigurationseinstellungen für cdR zugewiesen wurde. Jede Website ist auf eine einzelne solche Sammlung beschränkt. In diesem Fall können Sie die Einstellungen entweder löschen und dann neu erstellen oder einfach die vorhandenen Einstellungen ändern.
    
4. Wählen Sie im Dialogfeld Neue Aufzeichnung von **Anrufdetails (New Call Detail Recording, CDR)** die gewünschte Auswahl aus, und klicken Sie dann auf **Commit**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So ändern Sie vorhandene Konfigurationseinstellungen für cdR mithilfe der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Skype for Business Server-Systemsteuerung **auf Überwachung und Archivierung.**
    
2. Doppelklicken Sie auf die Zu ändernde Auflistung von Einstellungen, oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten,** und klicken Sie dann auf **Details anzeigen**. Beachten Sie, dass Sie immer nur eine einzelne Auflistung ändern können. Verwenden Sie stattdessen die Skype for Business Server-Verwaltungsshell, um die gleichen Änderungen an mehreren Sammlungen vorzunehmen.
    
3. Treffen Sie im Dialogfeld Aufzeichnung von **Anrufdetails bearbeiten (CDR)** die gewünschte Auswahl, und klicken Sie dann auf **Commit**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von Konfigurationseinstellungen für cdR mithilfe Windows PowerShell Cmdlets

Sie können KDS-Konfigurationseinstellungen auch mithilfe von Windows PowerShell und dem **Cmdlet New-CsCdrConfiguration** erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server Management Shell oder über eine Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>So erstellen Sie eine neue Auflistung von Konfigurationseinstellungen für cdR

 Mit diesem Befehl wird eine neue Auflistung von Konfigurationseinstellungen für cdR erstellt, die auf den Standort "Redmond" angewendet werden:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>So erstellen Sie eine Auflistung von Konfigurationseinstellungen für das CdR, die die Aufzeichnung von Anrufdetails deaktivieren

 Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Um beispielsweise eine Auflistung von Konfigurationseinstellungen für das Anrufdetail zu erstellen, die standardmäßig das Deaktivieren der Aufzeichnung von Anrufdetails zulassen, verwenden Sie einen Befehl wie den folgenden:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von Konfigurationseinstellungen für cdR mehrere Eigenschaftswerte an

 Sie können mehrere Eigenschaftswerte ändern, indem Sie mehrere Parameter hinzufügen. Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Die Anrufdetailse für 30 Tage und Fehlerberichte für 90 Tage erhalten bleiben:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Weitere Informationen finden Sie im Hilfethema für das [Cmdlet New-CsCdrConfiguration.](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
