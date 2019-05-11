---
title: Konfigurieren Sie die Aufzeichnung von kommunikationsdatensätzen und Quality of Experience Settings in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren von KDS und QoE in Skype für Business Server.'
ms.openlocfilehash: babc2ebe7901c19048624194b38e4cfa143e8f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894654"
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server"></a>Konfigurieren Sie die Aufzeichnung von kommunikationsdatensätzen und Quality of Experience Settings in Skype für Business Server
 
**Zusammenfassung:** Informationen Sie zum Konfigurieren von KDS und QoE in Skype für Business Server.
  
Konfigurieren Sie KDS und QoE-Überwachung mithilfe von SQL Server Reporting Services-Berichte für Skype für Business Server.
  
## <a name="configure-cdr-and-qoe"></a>Konfigurieren von KDS und QoE

Nachdem Sie einen Front-End-Pool, richten Sie den Speicher für Überwachung, und klicken Sie dann installiert und konfiguriert SQL Server Reporting Services und Überwachungsberichte ein überwachungsspeichers zugeordnet haben können Sie Aufzeichnung von Kommunikationsdatensätzen (KDS) und Quality of Experience (QoE) verwalten. Überwachen mithilfe von Skype für Business Server-Verwaltungsshell. Skype für Business Server-Verwaltungsshell-Cmdlets können Sie aktivieren und deaktivieren KDS und QoE-Überwachung für einen bestimmten Standort oder für Ihre gesamte Skype für Business Server-Bereitstellung. können Sie mit einem so einfach wie dieser Befehl ausführen:
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

Wenn Sie Skype für Business Server installieren, installieren Sie auch eine vordefinierte Sammlung von globalen Konfigurationseinstellungen für KDS und QoE. In der folgenden Tabelle sind Standardwerte für einige gängige Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen aufgeführt:
  
|**Eigenschaft**|**Beschreibung**|**Standardwert**|
|:-----|:-----|:-----|
|EnableCDR  <br/> |Gibt an, ob KDS aktiviert ist. Bei „True“ werden alle KDS-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.  <br/> |True  <br/> |
|EnablePurging  <br/> |Gibt an, ob KDS-Datensätze regelmäßig aus der Datenbank gelöscht werden. Bei Festlegung auf „True“ werden Einträge nach dem Zeitraum gelöscht, der in den Eigenschaften „KeepCallDetailForDays“ (KDS-Datensätze) und „KeepErrorReportForDays“ (KDS-Fehler) angegeben ist. Bei Festlegung des Parameters auf „False“ werden KDS-Einträge nie gelöscht.  <br/> |True  <br/> |
|KeepCallDetailForDays  <br/> |Gibt die Anzahl von Tagen an, die KDS-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.  <br/> „KeepCallDetailForDays“ kann auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (ungefähr 7 Jahre) festgelegt werden.  <br/> |60 Tage  <br/> |
|KeepErrorReportForDays  <br/> |Gibt die Anzahl von Tagen, für die Fehlerberichte CDR gehalten werden; Berichte, die älter sind als die angegebene Anzahl von Tagen werden automatisch gelöscht werden. KDS Fehlerberichte sind Diagnoseberichte von Clientanwendungen wie Skype für Business Server hochgeladen.  <br/> Sie können diese Eigenschaft auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (etwa 7 Jahre) festlegen.  <br/> |60 Tage  <br/> |
   
Entsprechend werden in dieser Tabelle Standardwerte für ausgewählte QoE-Einstellungen aufgeführt:
  
|**Eigenschaft**|**Beschreibung**|**Standardwert**|
|:-----|:-----|:-----|
|EnableQoE  <br/> |Gibt an, ob die QoE-Überwachung aktiviert ist. Bei Festlegung auf „True“ werden alle QoE-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.  <br/> |True  <br/> |
|EnablePurging  <br/> |Gibt an, ob QoE-Datensätze regelmäßig aus der Datenbank gelöscht werden oder nicht. Wenn dieser Parameter auf „True“ festgelegt ist, werden die Einträge nach der über die Eigenschaft „KeepQoEDataForDays“ angegebenen Zeitdauer gelöscht. Bei Festlegung des Parameters auf „False“ werden QoE-Datensätze nie gelöscht.  <br/> |True  <br/> |
|KeepQoEDataForDays  <br/> |Gibt die Anzahl von Tagen an, die QoE-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.  <br/> „KeepCallDetailForDays“ kann auf einen beliebigen Ganzzahlwert zwischen einschließlich 1 und 2562 Tage gesetzt werden.  <br/> |60 Tage  <br/> |
   
Wenn Sie diese globalen Einstellungen ändern müssen, können Sie dazu die Cmdlets „Set-CsCdrConfiguration“ und „Set-CsQoEConfiguration“ verwenden. Beispielsweise wird mit diesem Befehl (ausgeführt von innerhalb der Skype für Business Server-Verwaltungsshell) KDS-Überwachung auf globaler Ebene deaktiviert; erfolgt durch Festlegen der EnableCDR-Eigenschaft auf "false" ($False):
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

Durch das Deaktivieren der Überwachung wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben, noch wird die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig geändert. Wenn Sie Skype für Business Server-Verwaltungsshell verwenden, um CDR oder QoE-Überwachung deaktivieren Sie wirklich brauchen ist vorübergehend Skype für Business Server aus sammeln und Überwachungsdaten Archivierung zu beenden. Wenn Sie in diesem Fall das Sammeln und Archivieren von KDS-Daten fortsetzen möchten, müssen Sie nur die Eigenschaft „EnableCDR“ wieder auf „True“ ($True) festlegen:
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

Entsprechend deaktiviert dieser Befehl den Löschvorgang für QoE-Datensätze auf globaler Ebene:
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

Neben den globalen Einstellungen können KDS- und QoE-Konfigurationseinstellungen auch auf Standortebene zugewiesen werden. Dadurch wird die Verwaltung bei der Überwachung flexibler gestaltet; ein Administrator kann beispielsweise die KDS-Überwachung für den Standort Redmond aktivieren, für den Standort Dublin jedoch deaktivieren. Verwenden Sie einen Befehl wie den folgenden, um neue KDS-Konfigurationseinstellungen auf Standortebene zu erstellen:
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

Beachten Sie, dass Einstellungen auf Standortebene Vorrang vor globalen Einstellungen haben. Angenommen, die KDS-Überwachung ist auf globaler Ebene aktiviert, auf Standortebene (für den Standort Redmond) jedoch deaktiviert. Das bedeutet, dass für Benutzer am Standort Redmond keine Kommunikationsdatensätze aufgezeichnet werden. Für Benutzer an anderen Standorten (die von den globalen Einstellungen statt den Einstellungen für den Standort Redmond verwaltet werden), werden jedoch Kommunikationsdatensätze archiviert.
  
Neue QoE-Konfigurationseinstellungen auf Standortebene können mit einem Befehl wie dem folgenden erstellt werden:
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

Weitere Informationen geben Sie die folgenden Befehle aus innerhalb der Skype für Business Server-Verwaltungsshell aus:
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```
