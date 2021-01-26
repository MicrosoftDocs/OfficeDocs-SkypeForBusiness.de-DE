---
title: Angeben der Aufbewahrung von CdR-Daten in Skype for Business Server
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
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Zusammenfassung: Erfahren Sie, wie Sie Aufzeichnungsdaten (CdR) für Skype for Business Server verwalten.'
ms.openlocfilehash: 01b4765a9fa98a898255c1374115e17c4966e797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814215"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>Angeben der Aufbewahrung von CdR-Daten in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie Aufzeichnungsdaten (CdR) für Skype for Business Server verwalten.
  
In der Standardeinstellung werden Daten zur Aufzeichnung von Kommunikationsdatensätzen (KDS) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie KDS deaktivieren, werden auch Daten gelöscht, die bei aktivierter KDS-Datenerfassung aufgezeichnet wurden.
  
> [!NOTE]
> Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten (Quality of Experience) so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Monitoring Server-Berichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen. 
  
Verwenden Sie die folgenden Verfahren, um Bereinigungseinstellungen für KDS-Daten zu konfigurieren. 
  
### <a name="to-specify-retention-of-cdr-data"></a>So geben Sie die Beibehaltungsdauer für KDS-Daten an

1. Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.
    
4. Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details einblenden**.
    
5. Wählen Sie **Bereinigung von KDS-Aufzeichnungen aktivieren** aus, um die Bereinigung zu aktivieren.
    
6. Wählen Sie unter **Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen):** die maximale Anzahl von Tagen aus, für die KDS-Aufzeichnungen gespeichert werden sollen.
    
7. Wählen Sie unter **Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen):** die maximale Anzahl von Tagen, für die Fehlerberichte gespeichert werden sollen.
    
8. Klicken Sie auf **Commit ausführen**.
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Angeben der Aufbewahrung von CdR mithilfe Windows PowerShell Cmdlets

Sie können Aufbewahrungseinstellungen für die Aufbewahrung von Daten im Windows PowerShell mit dem cmdlet Set-CsCdrConfiguration erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>So geben Sie die die Beibehaltungsdauer für KDS-Daten für einen bestimmten Standort an

- Mit diesem Befehl werden KDS-Daten für den Standort "Redmond" bereinigt, und außerdem wird für den Standort konfiguriert, dass sowohl KDS-Daten als auch Fehlerberichtdaten 20 Tage lang aufbewahrt werden.
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>So geben Sie die die Beibehaltungsdauer für KDS-Daten für mehrere Standorte an

- Mit diesem Befehl wird die Beibehaltung von KDS-Daten für alle in einer Organisation verwendeten KDS-Konfigurationseinstellungen konfiguriert.
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsCdrConfiguration".](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)
  
## <a name="see-also"></a>Weitere Informationen

[Aufzeichnung von Anrufdetail (Call Detail Recording, CDR) in Skype for Business Server](call-detail-recording-cdr.md)
