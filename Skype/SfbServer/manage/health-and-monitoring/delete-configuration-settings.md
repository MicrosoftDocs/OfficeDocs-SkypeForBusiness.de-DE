---
title: Löschen einer vorhandenen Sammlung von CDR-Konfigurationseinstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie CDR-Konfigurationseinstellungen in Skype for Business Server entfernen.'
ms.openlocfilehash: d9e990018d97f8e631f3a95718a76aa83d7d619e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818025"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Sammlung von CDR-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie CDR-Konfigurationseinstellungen in Skype for Business Server entfernen.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Wenn Sie Skype for Business Server installieren, wird eine einzige globale Sammlung von CDR-Konfigurationseinstellungen für Sie erstellt. Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie die Einstellungen auf Standortebene entfernen, werden die KDS-Daten (Kommunikationsdatensätze) an diesem Standort mithilfe von globalen Einstellungen verwaltet.
  
Beachten Sie, dass Sie auch die globalen Einstellungen "Löschen" können. Allerdings werden die globalen Einstellungen dabei nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist in der Auflistung von KDS-Konfigurationseinstellungen standardmäßig die Löschung aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. In diesem Fall bedeutet das, dass die Bereinigung wieder aktiviert ist.
  
Sie können die CDR-Konfigurationseinstellungen mithilfe des Skype for Business Server Control Panels oder des Cmdlets [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) entfernen.
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie CDR-Konfigurationseinstellungen mit der Skype for Business Server-Systemsteuerung

1. Klicken Sie in der Skype for Business Server-Systemsteuerung auf **Überwachung und Archivierung**. 
    
2. Wählen Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** die Auflistung (oder Auflistungen) der zu entfernenden KDS-Einstellungen aus. Zum Auswählen mehrerer Auflistungen klicken Sie auf die erste Auflistung, halten Sie die Strg-Taste gedrückt und klicken Sie dann auf weitere Auflistungen.
    
3. Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.
    
4. Klicken Sie im Dialogfeld Skype for Business Server Control Panel auf **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von CDR-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen für die Anrufdetailaufzeichnung mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsCdrConfiguration** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von KDS-Konfigurationseinstellungen

 Mit diesem Befehl werden die KDS-Konfigurationseinstellungen entfernt, die auf den Standort „Redmond“ angewendet wurden:
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle KDS-Konfigurationseinstellungen, die auf Standortebene angewendet wurden

 Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .
  
## <a name="see-also"></a>Siehe auch

[Manuelles Bereinigen der Datenbanken für die Anrufdetailaufzeichnung und-Qualität in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

