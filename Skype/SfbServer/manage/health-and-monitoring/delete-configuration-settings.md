---
title: Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Zusammenfassung: Erfahren Sie, wie Sie KDS-Konfigurationseinstellungen in Skype for Business Server entfernen.'
---

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie KDS-Konfigurationseinstellungen in Skype for Business Server entfernen.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-zu-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne, globale Sammlung von KDS-Konfigurationseinstellungen für Sie erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie die Einstellungen auf Standortebene entfernen, werden die KDS-Daten (Kommunikationsdatensätze) an diesem Standort mithilfe von globalen Einstellungen verwaltet.
  
Beachten Sie, dass Sie auch die globalen Einstellungen "löschen" können. Diese globalen Einstellungen werden jedoch tatsächlich nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist in der Auflistung von KDS-Konfigurationseinstellungen standardmäßig die Löschung aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. Das bedeutet in diesem Fall, dass die Löschung wieder aktiviert wurde.
  
Sie können KDS-Konfigurationseinstellungen mithilfe der Skype for Business Server Systemsteuerung oder des Cmdlets ["Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)" entfernen.
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie KDS-Konfigurationseinstellungen mit Skype for Business Server Systemsteuerung

1. Klicken Sie in Skype for Business Server Systemsteuerung auf **"Überwachung und Archivierung**". 
    
2. Wählen Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** die Auflistung (oder Auflistungen) der zu entfernenden KDS-Einstellungen aus. Zum Auswählen mehrerer Auflistungen klicken Sie auf die erste Auflistung, halten Sie die STRG-TASTE gedrückt und klicken dann auf weitere Auflistungen.
    
3. Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.
    
4. Klicken Sie im Dialogfeld Skype for Business Server Systemsteuerung auf **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von KDS-Konfigurationseinstellungen mithilfe Windows PowerShell Cmdlets

Sie können die Konfigurationseinstellungen für die Aufzeichnung von Kommunikationsdatensätzen mithilfe von Windows PowerShell und dem Cmdlet **"Remove-CsCdrConfiguration**" löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync-Remote-PowerShell-Verwaltung](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von KDS-Konfigurationseinstellungen

 Mit diesem Befehl werden die KDS-Konfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden:
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle KDS-Konfigurationseinstellungen, die auf den Standortbereich angewendet wurden

 Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Remove-CsCdrConfiguration](/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) ".
  
## <a name="see-also"></a>Siehe auch

[Manuelles Löschen der Datenbanken "Aufzeichnung von Kommunikationsdatensätzen" und "Quality of Experience" in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)