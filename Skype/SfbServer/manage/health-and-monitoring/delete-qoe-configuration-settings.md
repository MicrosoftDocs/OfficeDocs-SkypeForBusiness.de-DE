---
title: Löschen der Konfigurationseinstellungen für die Qualität von Erfahrungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie in Skype for Business Server die QoE-Einstellungen (Quality of Experience) löschen.'
ms.openlocfilehash: 134ebe39f41ca051db4ff79eafb094dcc929b5e8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992422"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Löschen der Konfigurationseinstellungen für die Qualität von Erfahrungen in Skype for Business Server
 
**Zusammenfassung:** Informationen zum Löschen von QoE-Einstellungen (Quality of Experience) in Skype for Business Server.
  
QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.
  
Wenn Sie Skype for Business Server installieren, wird eine einzige globale Sammlung von QoE-Konfigurationseinstellungen für Sie erstellt. Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können. Prinzipiell gilt, dass auf Standortebene konfigurierte Einstellungen Vorrang vor auf globaler Ebene konfigurierten Einstellungen haben. Wenn Sie Einstellungen auf Standortebene löschen, wird QoE an diesem Standort unter Verwendung der globalen Einstellungen gesteuert.
  
Beachten Sie, dass Sie auch die globalen Einstellungen "Löschen" können. Allerdings werden die globalen Einstellungen dabei nicht entfernt. Vielmehr werden alle Eigenschaften in dieser Auflistung auf ihre Standardwerte zurückgesetzt. Ein Beispiel: Angenommen, in einer Auflistung von QoE-Konfigurationseinstellungen ist standardmäßig die Bereinigung aktiviert. Sie ändern nun die globale Auflistung dahin gehend, dass Bereinigung deaktiviert ist. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. In diesem Fall bedeutet das, dass die Bereinigung wieder aktiviert ist.
  
Sie können QoE-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe des Cmdlets [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) entfernen.
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So löschen Sie QoE-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.
    
4. Klicken Sie auf der Seite **QoE-Daten** auf die gewünschte Richtlinie, dann auf **Bearbeiten** und anschließend auf **Löschen**.
    
5. Klicken Sie anschließend auf **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsQoEConfiguration** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von QoE-Konfigurationseinstellungen

 Mit diesem Befehl werden die QoE-Konfigurationseinstellungen entfernt, die auf den Standort Redmond angewendet wurden:
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle QoE-Konfigurationseinstellungen, die auf Standortebene angewendet wurden

 Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>So entfernen Sie alle QoE-Konfigurationseinstellungen, in denen QoE-Überwachung deaktiviert ist

 Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, in denen die QoE-Überwachung deaktiviert wurde:
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Ausführliche Informationen finden Sie unter [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Siehe auch

[Manuelles Bereinigen der Datenbanken für die Anrufdetailaufzeichnung und-Qualität in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

