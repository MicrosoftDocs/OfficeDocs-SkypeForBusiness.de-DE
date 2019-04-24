---
title: Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Zusammenfassung: Erfahren Sie mehr über die Aufzeichnung von kommunikationsdatensätzen (KDS) in Skype für Business Server.'
ms.openlocfilehash: 563aeb37a0d6ae8cc10f73fe8d5d6808b9a051a9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199750"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Lernen Sie die Aufzeichnung von kommunikationsdatensätzen (KDS) in Skype für Business Server aus.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Bei der Installation von Skype für Business Server Single-Wert ist die globale Auflistung von KDS-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen. Wenn diese Einstellungen auf Standortebene verwendet werden, haben sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise Einstellungen auf Standortebene für den Standort „Redmond“ erstellen, werden diese Einstellung (anstelle der globalen Einstellungen) für die KDS-Verwaltung in Redmond verwendet.
  
Sie können KDS-Konfigurationseinstellungen mithilfe von entweder Skype für Business Server-Systemsteuerung oder [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) -Cmdlet erstellen. Skype für Business Server-Systemsteuerung oder [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) -Cmdlet können Sie die vorhandene Einstellungen ändern. Wenn Sie zum Erstellen oder Ändern der Einstellungen für die Business Server-Systemsteuerung Skype verwenden, werden die folgenden Optionen zur Verfügung:
  
|**Benutzeroberflächeneinstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutiger Bezeichner für die KDS-Konfigurationseinstellungen, die erstellt werden. Diese Einstellungen können nur auf der Standortebene erstellt werden.  <br/> |
|Überwachung von KDS-Aufzeichnungen aktivieren  <br/> |EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist.  <br/> |
|Bereinigung von KDS-Aufzeichnungen aktivieren  <br/> |EnablePurging  <br/> |Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.  <br/> |
|Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen)  <br/> |KeepCallDetailForDays  <br/> |Gibt die Anzahl von Tagen an, die KDS-Datensätze in der KDS-Datenbank gespeichert werden. Datensätze, die älter sind als angegeben, werden automatisch gelöscht. (Beachten Sie, dass der Löschvorgang nur stattfindet, wenn die Bereinigung aktiviert wurde.)  <br/> |
|Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen)  <br/> |KeepErrorReportForDays  <br/> |Gibt die Anzahl von Tagen an, die KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter sind als angegeben, werden automatisch gelöscht. Fehlerberichte zu Kommunikationsdatensätzen sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.  <br/> |
   
> [!NOTE]
> Die Cmdlets New-CsCdrConfiguration und Set-CsCdrConfiguration gehören zusätzliche Optionen für die Business Server-Systemsteuerung in Skype nicht verfügbar. Finden Sie das [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) und das [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) die Themen der Onlinehilfe für Weitere Informationen.
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Erstellen Sie KDS-Konfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung

1. Klicken Sie in Skype Business Server-Systemsteuerung auf **Überwachung und Archivierung**.
    
2. Klicken Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** auf **neu**.
    
3. Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, in dem die neuen Konfigurationseinstellungen erstellt werden sollen. Falls das Dialogfeld leer ist, bedeutet dies, dass allen Ihren Standorten bereits eine Auflistung von KDS-Konfigurationseinstellungen zugewiesen wurde. Für jeden Standort ist nur eine einzige derartige Auflistung zulässig. In diesem Fall können Sie entweder die Einstellungen löschen und anschließend neu erstellen oder aber einfach die vorhandenen Einstellungen ändern.
    
4. Wählen Sie im Dialogfeld **Neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS)** die gewünschten Optionen aus und klicken Sie dann auf **Commit ausführen**.
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So ändern Sie vorhandene KDS-Konfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung

1. Klicken Sie in Skype Business Server-Systemsteuerung auf **Überwachung und Archivierung**.
    
2. Doppelklicken Sie auf die zu ändernde Auflistung von Einstellungen oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten** und klicken Sie anschließend auf **Details einblenden**. Beachten Sie, dass Sie jeweils immer nur eine Auflistung ändern können. Um die gleiche Änderung an mehreren Websitesammlungen vornehmen möchten, verwenden Sie die Skype stattdessen für Business Server-Verwaltungsshell.
    
3. Wählen Sie im Dialogfeld **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die gewünschten Optionen aus und klicken Sie dann auf **Commit ausführen**.
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen KDS-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können KDS-Konfiguration erstellen, die Einstellungen mithilfe von Windows PowerShell und das **New-CsCdrConfiguration** -Cmdlet auch erstellt werden können. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen

 Mit dem folgenden Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen für den Standort „Redmond“ erstellt:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>So erstellen Sie eine Auflistung von KDS-Konfigurationseinstellungen, mit denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wird

 Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet. Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von KDS-Konfigurationseinstellungen erstellen möchten, die standardmäßig das Deaktivieren der Aufzeichnung von Kommunikationsdatensätzen erlauben, verwenden Sie den folgenden Befehl:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an

 Durch die Angabe mehrerer Parameter können Sie mehrere Eigenschaftswerte ändern. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Kommunikationsdatensätze 30 Tage und Fehlerberichte 90 Tage lang aufbewahrt werden:
    
  ```
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Weitere Informationen finden Sie im Hilfethema für das [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) -Cmdlet.
  

