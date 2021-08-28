---
title: Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 'Zusammenfassung: Erfahren Sie mehr über die Aufzeichnung von Kommunikationsdatensätzen (KDS) in Skype for Business Server.'
ms.openlocfilehash: e9b30eee578fd83dd0d94fbd78a490bf1b0e65de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626607"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Aufzeichnung von Kommunikationsdatensätzen (KDS) in Skype for Business Server.
  
Mit der Aufzeichnung von Kommunikationsdatensätzen (KDS) können Sie die Verwendung von Peer-to-Peer-Chatsitzungen, VoIP-Telefonanrufen (Voice over Internet Protocol) und Konferenzanrufen nachverfolgen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne globale Sammlung von KDS-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise Standorteinstellungen für den Standort Redmond erstellen, werden diese Einstellungen (statt der globalen Einstellungen) zum Verwalten von KDS in Redmond verwendet.
  
Sie können KDS-Konfigurationseinstellungen entweder mit Skype for Business Server Systemsteuerung oder mit dem Cmdlet ["New-CsCdrConfiguration"](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) erstellen. Sie können Skype for Business Server Systemsteuerung oder das Cmdlet ["Set-CsCdrConfiguration"](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) verwenden, um vorhandene Einstellungen zu ändern. Wenn Sie Skype for Business Server Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:
  
|**UI-Einstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutiger Bezeichner für die KDS-Konfigurationseinstellungen, die erstellt werden. Diese Einstellungen können nur auf Websiteebene erstellt werden.  <br/> |
|Aktivieren der Überwachung von KDS  <br/> |EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist.  <br/> |
|Aktivieren des Löschens von KDS  <br/> |EnablePurging  <br/> |Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.  <br/> |
|Aufbewahren von KDS für die maximale Dauer (Tage)  <br/> |KeepCallDetailForDays  <br/> |Gibt die Anzahl der Tage an, die KDS-Datensätze in der KDS-Datenbank aufbewahrt werden. Datensätze, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. (Beachten Sie, dass die Bereinigung nur erfolgt, wenn die Bereinigung aktiviert wurde.)  <br/> |
|Beibehalten von Fehlerberichtsdaten für die maximale Dauer (Tage)  <br/> |KeepErrorReportForDays  <br/> |Gibt die Anzahl der Tage an, die KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. KDS-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.  <br/> |
   
> [!NOTE]
> Die Cmdlets New-CsCdrConfiguration und Set-CsCdrConfiguration enthalten zusätzliche Optionen, die in Skype for Business Server Systemsteuerung nicht verfügbar sind. Weitere Informationen finden Sie in den Hilfethemen ["New-CsCdrConfiguration"](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) und ["Set-CsCdrConfiguration".](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie KDS-Konfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Klicken Sie in Skype for Business Server Systemsteuerung auf **"Überwachung und Archivierung".**
    
2. Klicken Sie auf der Registerkarte "Aufzeichnung von **Kommunikationsdatensätzen"** auf **"Neu".**
    
3. Wählen Sie im Dialogfeld **"Standort auswählen"** den Standort aus, an dem die neuen Konfigurationseinstellungen erstellt werden sollen. Wenn das Dialogfeld leer ist, bedeutet dies, dass allen Ihren Standorten bereits eine Sammlung von KDS-Konfigurationseinstellungen zugewiesen wurde. Jede Website ist auf eine einzelne solche Sammlung beschränkt. In diesem Fall können Sie die Einstellungen entweder löschen und dann erneut erstellen oder einfach die vorhandenen Einstellungen ändern.
    
4. Treffen Sie im Dialogfeld "Neue Aufzeichnung von **Kommunikationsdatensätzen "KDS"** die gewünschte Auswahl, und klicken Sie dann auf **"Commit ausführen".**
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So ändern Sie vorhandene KDS-Konfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Klicken Sie in Skype for Business Server Systemsteuerung auf **"Überwachung und Archivierung".**
    
2. Doppelklicken Sie auf die Zu ändernde Einstellungssammlung, oder wählen Sie die Auflistung aus, klicken Sie auf **"Bearbeiten"** und dann auf **"Details anzeigen".** Beachten Sie, dass Sie jeweils nur eine einzelne Auflistung ändern können. Wenn Sie dieselben Änderungen an mehreren Auflistungen vornehmen möchten, verwenden Sie stattdessen die Skype for Business Server Verwaltungsshell.
    
3. Treffen Sie im Dialogfeld "Aufzeichnung von **Kommunikationsdatensätzen bearbeiten"** die gewünschte Auswahl, und klicken Sie dann auf **"Commit ausführen".**
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von KDS-Konfigurationseinstellungen mithilfe Windows PowerShell Cmdlets

Sie können KDS-Konfigurationseinstellungen auch mit Windows PowerShell und dem Cmdlet **"New-CsCdrConfiguration"** erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen

 Mit diesem Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen erstellt, die auf den Standort Redmond angewendet werden:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>So erstellen Sie eine Sammlung von KDS-Konfigurationseinstellungen, die die Aufzeichnung von Kommunikationsdatensätzen deaktivieren

 Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Wenn Sie z. B. eine Auflistung von Konfigurationseinstellungen für Das Kommunikationsdetail erstellen möchten, die standardmäßig die Deaktivierung der Aufzeichnung von Kommunikationsdatensätzen zulassen, verwenden Sie einen Befehl wie den folgenden:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an

 Sie können mehrere Eigenschaftswerte ändern, indem Sie mehrere Parameter einschließen. Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Anrufdetaildatensätze für 30 Tage und Fehlerberichte 90 Tage lang beibehalten werden:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "New-CsCdrConfiguration".](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
