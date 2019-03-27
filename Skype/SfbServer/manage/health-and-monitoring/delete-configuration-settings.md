---
title: Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in Skype für Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Zusammenfassung: Erfahren Sie, wie KDS-Konfigurationseinstellungen in Skype für Business Server zu entfernen.'
ms.openlocfilehash: 470aade77fce211ba771c628b913efa4376a4a6f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873077"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in Skype für Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie KDS-Konfigurationseinstellungen in Skype für Business Server entfernen.
  
Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.
  
Bei der Installation von Skype für Business Server, einer einzelnen wird die globale Auflistung von KDS-Konfigurationseinstellungen für Sie erstellt. Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie die Einstellungen auf Standortebene entfernen, werden die KDS-Daten (Kommunikationsdatensätze) an diesem Standort mithilfe von globalen Einstellungen verwaltet.
  
Beachten Sie, dass Sie auch "die globalen Einstellungen löschen können". Allerdings werden die globalen Einstellungen dabei nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist in der Auflistung von KDS-Konfigurationseinstellungen standardmäßig die Löschung aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. In diesem Fall bedeutet das, dass die Bereinigung wieder aktiviert ist.
  
Sie können KDS-Konfigurationseinstellungen mithilfe der Skype für Business Server-Systemsteuerung oder [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) -Cmdlet entfernen.
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a>So entfernen Sie KDS-Konfigurationseinstellungen mit Skype Business Server-Systemsteuerung

1. Skype für Business Server-Systemsteuerung klicken Sie auf **Überwachung und Archivierung**. 
    
2. Wählen Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** die Auflistung (oder Auflistungen) der zu entfernenden KDS-Einstellungen aus. Zum Auswählen mehrerer Auflistungen klicken Sie auf die erste Auflistung, halten Sie die Strg-Taste gedrückt und klicken Sie dann auf weitere Auflistungen.
    
3. Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.
    
4. Die Skype für Dialogfeld Business Server-Systemsteuerung klicken Sie auf **OK**.
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen KDS-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können Konfigurationseinstellungen mithilfe von Windows PowerShell und das Cmdlet **Remove-CsCdrConfiguration** Aufzeichnung von kommunikationsdatensätzen löschen. Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype für Business Server identisch.
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von KDS-Konfigurationseinstellungen

 Mit diesem Befehl werden die KDS-Konfigurationseinstellungen entfernt, die auf den Standort „Redmond“ angewendet wurden:
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle KDS-Konfigurationseinstellungen, die auf Standortebene angewendet wurden

 Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>So entfernen Sie alle KDS-Konfigurationseinstellungen, die die Aufzeichnung von Kommunikationsdatensätzen deaktivieren

 Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, bei denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wurde:
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

Weitere Informationen finden Sie im Hilfethema zum [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) -Cmdlet.
  
## <a name="see-also"></a>Siehe auch

[Manuelles Löschen der KDS- und Quality of Experience-Datenbanken in Skype für Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

