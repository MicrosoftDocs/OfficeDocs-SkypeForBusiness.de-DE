---
title: Konfigurieren der Aufzeichnung von Anrufdetails und Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie CDR und QoE in Skype for Business Server konfigurieren.'
ms.openlocfilehash: 93dc0dd5917e476d3c993562dfd06bc3a086f8dc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001115"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Konfigurieren der Aufzeichnung von Anrufdetails und Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie CDR und QoE in Skype for Business Server konfigurieren.
  
Konfigurieren Sie die CDR-und QoE-Überwachung mithilfe von SQL Server Reporting Services-Berichten für Skype for Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Konfigurieren von KDS und QoE

Nachdem Sie einen Überwachungsspeicher mit einem Front-End-Pool verknüpft haben, Einrichten des überwachungsspeichers und anschließendes Installieren und Konfigurieren von SQL Server Reporting Services-und Überwachungsberichten können Sie die Anruf Detail Aufzeichnung (CDR) und die Quality of Experience (QoE) verwalten. Überwachung mithilfe der Skype for Business Server-Verwaltungsshell. Mit den Cmdlets für die Skype for Business Server-Verwaltungsshell können Sie die CDR-und/oder QoE-Überwachung für eine bestimmte Website oder für die gesamte Skype for Business Server-Bereitstellung aktivieren und deaktivieren. Dies kann mit einem einfachen Befehl erfolgen:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Wenn Sie Skype for Business Server installieren, werden Sie auch eine vordefinierte Sammlung globaler Konfigurationseinstellungen für CDR und QoE installieren. In der folgenden Tabelle sind Standardwerte für einige gängige Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen aufgeführt:
  
|**Eigenschaft**|**Beschreibung**|**Standardwert**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist. Bei „True“ werden alle KDS-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.  <br/> |Wahr  <br/> |
|EnablePurging  <br/> |Gibt an, ob KDS-Datensätze regelmäßig aus der Datenbank gelöscht werden. Bei Festlegung auf „True“ werden Einträge nach dem Zeitraum gelöscht, der in den Eigenschaften „KeepCallDetailForDays“ (KDS-Datensätze) und „KeepErrorReportForDays“ (KDS-Fehler) angegeben ist. Bei Festlegung des Parameters auf „False“ werden KDS-Einträge nie gelöscht.  <br/> |Wahr  <br/> |
|KeepCallDetailForDays  <br/> |Gibt die Anzahl von Tagen an, die KDS-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.  <br/> „KeepCallDetailForDays“ kann auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (ungefähr 7 Jahre) festgelegt werden.  <br/> |60 Tage  <br/> |
|KeepErrorReportForDays  <br/> |Gibt an, wie viele Tage CdR-Fehlerberichte aufbewahrt werden. Alle Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht. CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen wie Skype for Business Server hochgeladen werden.  <br/> Sie können diese Eigenschaft auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (etwa 7 Jahre) festlegen.  <br/> |60 Tage  <br/> |
   
Entsprechend werden in dieser Tabelle Standardwerte für ausgewählte QoE-Einstellungen aufgeführt:
  
|**Eigenschaft**|**Beschreibung**|**Standardwert**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Gibt an, ob die QoE-Überwachung aktiviert ist. Bei Festlegung auf „True“ werden alle QoE-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.  <br/> |Wahr  <br/> |
|EnablePurging  <br/> |Gibt an, ob QoE-Datensätze regelmäßig aus der Datenbank gelöscht werden oder nicht. Wenn dieser Parameter auf „True“ festgelegt ist, werden die Einträge nach der über die Eigenschaft „KeepQoEDataForDays“ angegebenen Zeitdauer gelöscht. Bei Festlegung des Parameters auf „False“ werden QoE-Datensätze nie gelöscht.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Gibt die Anzahl von Tagen an, die QoE-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.  <br/> „KeepCallDetailForDays“ kann auf einen beliebigen Ganzzahlwert zwischen einschließlich 1 und 2562 Tage gesetzt werden.  <br/> |60 Tage  <br/> |
   
Wenn Sie diese globalen Einstellungen ändern müssen, können Sie dazu die Cmdlets „Set-CsCdrConfiguration“ und „Set-CsQoEConfiguration“ verwenden. Mit diesem Befehl (der in der Skype for Business Server-Verwaltungsshell ausgeführt wird) wird beispielsweise die CDR-Überwachung im globalen Bereich deaktiviert. Dies erfolgt durch Festlegen der EnableCDR-Eigenschaft auf "false" ($false):
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Durch das Deaktivieren der Überwachung wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben, noch wird die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig geändert. Wenn Sie die Skype for Business Server-Verwaltungsshell verwenden, um die CDR-oder QoE-Überwachung zu deaktivieren, ist das alles, was Sie wirklich tun, dazu führen, dass Skype for Business Server vorübergehend die Erfassung und Archivierung von Überwachungsdaten verhindert. Wenn Sie in diesem Fall das Sammeln und Archivieren von KDS-Daten fortsetzen möchten, müssen Sie nur die Eigenschaft „EnableCDR“ wieder auf „True“ ($True) festlegen:
  
```powershell
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Entsprechend deaktiviert dieser Befehl den Löschvorgang für QoE-Datensätze auf globaler Ebene:
  
```powershell
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Neben den globalen Einstellungen können KDS- und QoE-Konfigurationseinstellungen auch auf Standortebene zugewiesen werden. Dadurch wird die Verwaltung bei der Überwachung flexibler gestaltet; ein Administrator kann beispielsweise die KDS-Überwachung für den Standort Redmond aktivieren, für den Standort Dublin jedoch deaktivieren. Verwenden Sie einen Befehl wie den folgenden, um neue KDS-Konfigurationseinstellungen auf Standortebene zu erstellen:
  
```powershell
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Beachten Sie, dass Einstellungen auf Standortebene Vorrang vor globalen Einstellungen haben. Angenommen, die KDS-Überwachung ist auf globaler Ebene aktiviert, auf Standortebene (für den Standort Redmond) jedoch deaktiviert. Das bedeutet, dass für Benutzer am Standort Redmond keine Kommunikationsdatensätze aufgezeichnet werden. Für Benutzer an anderen Standorten (die von den globalen Einstellungen statt den Einstellungen für den Standort Redmond verwaltet werden), werden jedoch Kommunikationsdatensätze archiviert.
  
Neue QoE-Konfigurationseinstellungen auf Standortebene können mit einem Befehl wie dem folgenden erstellt werden:
  
```powershell
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Wenn Sie weitere Informationen wünschen, geben Sie in der Skype for Business Server-Verwaltungsshell die folgenden Befehle ein:
  
```powershell
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
