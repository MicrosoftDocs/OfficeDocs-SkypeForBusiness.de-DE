---
title: Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für die Zusammenstellung von CdR in Skype for Business Server
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
description: 'Zusammenfassung: Erfahren Sie mehr über die Aufzeichnung von Anrufdetails (CdR) in Skype for Business Server.'
ms.openlocfilehash: 77529204483924664a462913e8d33eaa54e55453
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817015"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Erstellen oder Ändern einer Auflistung von Konfigurationseinstellungen für die Zusammenstellung von CdR in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über die Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) in Skype for Business Server.
  
Mit der Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) können Sie die Verwendung von Peer-zu-Peer-Sofortnachrichtensitzungen, VoIP-Telefonanrufen (Voice over Internet Protocol) und Konferenzanrufen nachverfolgen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne, globale Auflistung von Konfigurationseinstellungen für die Zusammenstellung von CdR für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen. Wenn Sie beispielsweise Standorteinstellungen für den Standort "Redmond" erstellen, werden diese Einstellungen (und nicht die globalen Einstellungen) zum Verwalten von CdR in Redmond verwendet.
  
Sie können KDS-Konfigurationseinstellungen entweder mithilfe der Skype for Business Server-Systemsteuerung oder des [Cmdlets "New-CsCdrConfiguration"](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) erstellen. Sie können die Skype for Business Server-Systemsteuerung oder das [Cmdlet "Set-CsCdrConfiguration"](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) verwenden, um vorhandene Einstellungen zu ändern. Wenn Sie die Skype for Business Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:
  
|**Benutzeroberflächeneinstellung**|**Parameter "PowerShell"**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutige ID für die zu erstellende CDR-Konfigurationseinstellungen. Diese Einstellungen können nur auf Standortbereich erstellt werden.  <br/> |
|Aktivieren der Überwachung von CdRs  <br/> |EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist.  <br/> |
|Bereinigung von CdRs aktivieren  <br/> |EnablePurging  <br/> |Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.  <br/> |
|Maximale Dauer (Tage) für CdRs  <br/> |KeepCallDetailForDays  <br/> |Gibt die Anzahl der Tage an, die die Aufzeichnungen von Aufzeichnungen für die Aufzeichnung von Aufzeichnungen in der Aufzeichnungsdatenbank aufbewahrt werden. Alle Datensätze, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. (Beachten Sie, dass das Löschen nur erfolgt, wenn die Bereinigung aktiviert wurde.)  <br/> |
|Fehlerberichtsdaten für maximale Dauer (Tage) speichern  <br/> |KeepErrorReportForDays  <br/> |Gibt die Anzahl der Tage an, für die Fehlerberichte über die Medienprotokolle aufbewahrt werden. Alle Berichte, die älter sind als die angegebene Anzahl von Tagen, werden automatisch gelöscht. Fehlerberichte zu DenKDS sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.  <br/> |
   
> [!NOTE]
> Die New-CsCdrConfiguration und Set-CsCdrConfiguration enthalten zusätzliche Optionen, die in der Skype for Business Server-Systemsteuerung nicht verfügbar sind. Weitere Informationen finden Sie in den Hilfethemen ["New-CsCdrConfiguration"](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) und ["Set-CsCdrConfiguration".](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie Konfigurationseinstellungen für die Anrufsteuerung von Skype for Business Server mithilfe der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Skype for Business Server-Systemsteuerung **auf "Überwachung und Archivierung".**
    
2. Klicken Sie **auf der Registerkarte "Aufzeichnung von** Anrufdetails" auf **"Neu".**
    
3. Wählen Sie **im Dialogfeld Standort auswählen** den Standort aus, an dem die neuen Konfigurationseinstellungen erstellt werden sollen. Wenn das Dialogfeld leer ist, bedeutet dies, dass allen Standorten bereits eine Auflistung von Konfigurationseinstellungen für die Zusammenstellung von CdR zugewiesen wurde. Jede Website ist auf eine einzelne solche Sammlung beschränkt. In diesem Fall können Sie die Einstellungen entweder löschen und dann neu erstellen oder einfach die vorhandenen Einstellungen ändern.
    
4. Treffen Sie im Dialogfeld Einstellung für die Neue Aufzeichnung von Anrufdetails **(New Call Detail Recording, CDR)** die gewünschte Auswahl, und klicken Sie dann auf **Commit.**
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So ändern Sie vorhandene Konfigurationseinstellungen für den Netzwerkdatenschutz mithilfe der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Skype for Business Server-Systemsteuerung **auf "Überwachung und Archivierung".**
    
2. Doppelklicken Sie auf die Auflistung der zu ändernde Einstellungen, oder wählen Sie die Auflistung aus, klicken Sie auf "Bearbeiten" **und** dann auf **"Details anzeigen".** Beachten Sie, dass Sie immer nur eine einzelne Auflistung ändern können. Um dieselben Änderungen an mehreren Auflistungen vorzunehmen, verwenden Sie stattdessen die Skype for Business Server-Verwaltungsshell.
    
3. Treffen Sie im Dialogfeld Einstellung für die Aufzeichnung von Anrufdetails **(Edit Call Detail Recording, CDR)** die gewünschte Auswahl, und klicken Sie dann auf **Commit.**
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von Konfigurationseinstellungen für die Erstellung von CdR mithilfe Windows PowerShell Cmdlets

Sie können KDS-Konfigurationseinstellungen auch mithilfe von Windows PowerShell **New-CsCdrConfiguration-Cmdlet** erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>So erstellen Sie eine neue Auflistung von Konfigurationseinstellungen für die CdR

 Mit diesem Befehl wird eine neue Auflistung von Konfigurationseinstellungen für den Netzwerkdatenfall erstellt, die auf den Standort "Redmond" angewendet werden:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>So erstellen Sie eine Auflistung von Konfigurationseinstellungen für die Aufzeichnung von Aufzeichnungen von Anrufdetails, die die Aufzeichnung von Anrufdetails deaktivieren

 Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Verwenden Sie beispielsweise einen Befehl wie den folgenden, um eine Auflistung von Konfigurationseinstellungen für die Anrufdetailkonfiguration zu erstellen, die standardmäßig das Deaktivieren der Aufzeichnung von Anrufdetails zulassen:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>So geben Sie mehrere Eigenschaftswerte beim Erstellen einer neuen Auflistung von Konfigurationseinstellungen für die Zusammenstellung von CdR an

 Sie können mehrere Eigenschaftswerte ändern, indem Sie mehrere Parameter hinzufügen. Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Die Anrufdetaildatensätze 30 Tage lang und Fehlerberichte 90 Tage lang erhalten bleiben:
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "New-CsCdrConfiguration".](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)
  

