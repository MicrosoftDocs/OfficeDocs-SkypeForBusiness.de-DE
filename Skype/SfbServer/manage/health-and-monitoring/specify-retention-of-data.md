---
title: Angeben der Beibehaltungsdauer für KDS-Daten in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Zusammenfassung: Erfahren Sie, wie die Aufzeichnung von kommunikationsdatensätzen (KDS) für Skype für Business Server 2015 verwalten.'
ms.openlocfilehash: cb15468f1980f0103c2333676a92ae1ca1280f1b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server-2015"></a>Angeben der Beibehaltungsdauer für KDS-Daten in Skype for Business Server 2015
 
**Zusammenfassung:** Erfahren Sie, wie die Aufzeichnung von kommunikationsdatensätzen (KDS) für Skype für Business Server 2015 verwalten.
  
In der Standardeinstellung werden Daten zur Aufzeichnung von Kommunikationsdatensätzen (KDS) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie KDS deaktivieren, werden auch Daten gelöscht, die bei aktivierter KDS-Datenerfassung aufgezeichnet wurden.
  
> [!NOTE]
> Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten (Quality of Experience) so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Monitoring Server-Berichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen. 
  
Verwenden Sie die folgenden Verfahren, um Bereinigungseinstellungen für KDS-Daten zu konfigurieren. 
  
### <a name="to-specify-retention-of-cdr-data"></a>So geben Sie die Beibehaltungsdauer für KDS-Daten an

1. Von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins (oder gleichwertige Benutzerrechte verfügt), oder der CsServerAdministrator oder CsAdministrator-Rolle, melden Sie sich an einem beliebigen Computer, die im Netzwerk ist in der Bereitstellung von Skype für Business Server zugeordnet ist 2015.
    
2. Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.
    
4. Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.
    
5. Wählen Sie **Bereinigung von KDS-Aufzeichnungen aktivieren** aus, um die Bereinigung zu aktivieren.
    
6. Wählen Sie unter **Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen):** die maximale Anzahl von Tagen aus, für die KDS-Aufzeichnungen gespeichert werden sollen.
    
7. Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.
    
8. Klicken Sie auf **Commit**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Angeben der Beibehaltungsdauer für KDS mithilfe von Windows PowerShell-cmdlets

Sie können KDS beibehaltungseinstellungen mithilfe von Windows PowerShell und das Set-CsCdrConfiguration-Cmdlet erstellen. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>So geben Sie die Beibehaltungsdauer für KDS-Daten für einen bestimmten Standort an

- Mit diesem Befehl werden KDS-Daten für den Standort „Redmond“ bereinigt und außerdem wird für den Standort konfiguriert, dass sowohl KDS-Daten als auch Fehlerberichtdaten 20 Tage lang aufbewahrt werden.
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>So geben Sie die Beibehaltungsdauer für KDS-Daten für mehrere Standorte an

- Mit diesem Befehl wird die Beibehaltung von KDS-Daten für alle in einer Organisation verwendeten KDS-Konfigurationseinstellungen konfiguriert.
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Weitere Informationen finden Sie im Hilfethema zum [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) -Cmdlet.
  
## <a name="see-also"></a>Siehe auch

#### 

[Aufzeichnung von kommunikationsdatensätzen (KDS) in Skype für Business Server 2015](call-detail-recording-cdr.md)

