---
title: Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Erlebnisqualität in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Zusammenfassung: Informationen zum Konfigurieren von CDR und QoE in Skype for Business Server.'
ms.openlocfilehash: dd8611723e3d83f8a4553ba2148ee5ae29791e88
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802285"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Konfigurieren der Aufzeichnung von Anrufdetails und der Einstellungen für die Erlebnisqualität in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie CDR und QoE in Skype for Business Server konfigurieren.
  
Konfigurieren Sie die CdR- und QoE-Überwachung mithilfe SQL Server Reporting Services-Berichte für Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Konfigurieren von CDR und QoE

Nachdem Sie einen Überwachungsspeicher einem Front-End-Pool zugeordnet haben, den Überwachungsspeicher eingerichtet und dann SQL Server Reporting Services und Überwachungsberichte installiert und konfiguriert haben, können Sie die Überwachung der Aufzeichnung von Anrufdetails (Call Detail Recording, CDR) und QoE (Quality of Experience) mithilfe der Skype for Business Server-Verwaltungsshell verwalten. Mit Cmdlets der Skype for Business #A0 können Sie die CdR- und/oder #A1 für einen bestimmten Standort oder für Ihre gesamte Skype for Business #A2 aktivieren und deaktivieren. dies kann mit einem befehl so einfach wie dem folgenden durchgeführt werden:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Wenn Sie Skype for Business Server installieren, installieren Sie auch eine vordefinierte Auflistung von globalen Konfigurationseinstellungen für CDR und QoE. In der folgenden Tabelle sind Standardwerte für einige gängige Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen aufgeführt:
  
|**Eigenschaft**|**Beschreibung**|**Standardwert**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist. Bei "True" werden alle KDS-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.  <br/> |Richtig  <br/> |
|EnablePurging  <br/> |Gibt an, ob KDS-Datensätze regelmäßig aus der Datenbank gelöscht werden. Bei Festlegung auf "True" werden Einträge nach dem Zeitraum gelöscht, der in den Eigenschaften "KeepCallDetailForDays" (KDS-Datensätze) und "KeepErrorReportForDays" (KDS-Fehler) angegeben ist. Bei Festlegung des Parameters auf "False" werden KDS-Einträge nie gelöscht.  <br/> |Richtig  <br/> |
|KeepCallDetailForDays  <br/> |Gibt die Anzahl von Tagen an, die KDS-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.  <br/> "KeepCallDetailForDays" kann auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (ungefähr 7 Jahre) festgelegt werden.  <br/> |60 Tage  <br/> |
|KeepErrorReportForDays  <br/> |Gibt an, wie viele Tage #A0 aufbewahrt werden; Alle Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. Fehlerberichte zu DenKDS sind Diagnoseberichte, die von Clientanwendungen wie Skype for Business Server hochgeladen werden.  <br/> Sie können diese Eigenschaft auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (etwa 7 Jahre) festlegen.  <br/> |60 Tage  <br/> |
   
Entsprechend werden in dieser Tabelle Standardwerte für ausgewählte QoE-Einstellungen aufgeführt:
  
|**Eigenschaft**|**Beschreibung**|**Standardwert**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Gibt an, ob die QoE-Überwachung aktiviert ist. Bei Festlegung auf "True" werden alle QoE-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.  <br/> |Richtig  <br/> |
|EnablePurging  <br/> |Gibt an, ob QoE-Datensätze regelmäßig aus der Datenbank gelöscht werden oder nicht. Wenn dieser Parameter auf "True" festgelegt ist, werden die Einträge nach der über die Eigenschaft "KeepQoEDataForDays"    angegebenen Zeitdauer gelöscht. Bei Festlegung des Parameters auf "False" werden QoE-Datensätze nie gelöscht.  <br/> |Richtig  <br/> |
|KeepQoEDataForDays  <br/> |Gibt die Anzahl von Tagen an, die QoE-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.  <br/> "KeepCallDetailForDays" kann auf einen beliebigen Ganzzahlwert zwischen einschließlich 1 und 2562 Tage gesetzt werden.  <br/> |60 Tage  <br/> |
   
Wenn Sie diese globalen Einstellungen ändern müssen, können Sie dazu die Cmdlets "Set-CsCdrConfiguration" und "Set-CsQoEConfiguration" verwenden. Beispielsweise deaktiviert dieser Befehl (ausgeführt in der Skype for Business Server-Verwaltungsshell) die #A0 auf globaler Ebene. dazu wird die Eigenschaft "EnableCDR" auf "False" ($False) gesetzt:
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Durch das Deaktivieren der Überwachung wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben, noch wird die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig geändert. Wenn Sie die Skype for Business Server-Verwaltungsshell verwenden, um die CdR- oder die QoE-Überwachung zu deaktivieren, müssen Sie nur vorübergehend verhindern, dass Skype for Business Server Überwachungsdaten sammelt und archiviert. Wenn Sie in diesem Fall das Sammeln und Archivieren von KDS-Daten fortsetzen möchten, müssen Sie nur die Eigenschaft "EnableCDR" wieder auf "True" ($True) festlegen:
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Entsprechend deaktiviert dieser Befehl den Löschvorgang für QoE-Datensätze auf globaler Ebene:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Neben den globalen Einstellungen können KDS- und QoE-Konfigurationeneinstellungen auch auf Standortebene zugewiesen werden. Dadurch wird die Verwaltung bei der Überwachung flexibler gestaltet; ein Administrator kann beispielsweise die KDS-Überwachung für den Standort Redmond aktivieren, für den Standort Dublin jedoch deaktivieren. Verwenden Sie einen Befehl wie den folgenden, um neue KDS-Konfigurationseinstellungen auf Standortebene zu erstellen:
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Beachten Sie, dass Einstellungen auf Standortebene Vorrang vor globalen Einstellungen haben. Angenommen, die KDS-Überwachung ist auf globaler Ebene aktiviert, auf Standortebene (für den Standort Redmond) jedoch deaktiviert. Das bedeutet, dass für Benutzer am Standort Redmond keine Kommunikationsdatensätze aufgezeichnet werden. Für Benutzer an anderen Standorten (die von den globalen Einstellungen statt den Einstellungen für den Standort Redmond verwaltet werden), werden jedoch Kommunikationsdatensätze archiviert.
  
Neue QoE-Konfigurationseinstellungen auf Standortebene können mit einem Befehl wie dem folgenden erstellt werden:
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Geben Sie die folgenden Befehle in der Skype for Business Server-Verwaltungsshell ein, um weitere Informationen zu erhalten:
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
