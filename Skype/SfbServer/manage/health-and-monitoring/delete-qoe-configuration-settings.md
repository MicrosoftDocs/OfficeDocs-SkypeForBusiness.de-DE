---
title: Löschen von Konfigurationseinstellungen für die Qualität der Benutzererfahrung in Skype for Business Server
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Zusammenfassung: Erfahren Sie, wie Sie QoE-Einstellungen (Quality of Experience) in Skype for Business Server löschen.'
ms.openlocfilehash: b48ddb9af715cd33b11d3c2f1c7ea90b3746aa4a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095279"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Löschen von Konfigurationseinstellungen für die Qualität der Benutzererfahrung in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie, wie Sie QoE-Einstellungen (Quality of Experience) in Skype for Business Server löschen.
  
QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne, globale Auflistung von QoE-Konfigurationseinstellungen für Sie erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie Einstellungen mit Standortbereich löschen, wird QoE an diesem Standort mithilfe der globalen Einstellungen verwaltet.
  
Beachten Sie, dass Sie die globalen Einstellungen auch "löschen" können. Diese globalen Einstellungen werden jedoch tatsächlich nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist das Löschen standardmäßig in einer Auflistung von QoE-Konfigurationseinstellungen aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. Das bedeutet in diesem Fall, dass die Löschung wieder aktiviert wurde.
  
Sie können die QoE-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung oder mithilfe des [Cmdlets Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) entfernen.
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So löschen Sie die QoE-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" am Computer an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.
    
4. Klicken Sie **auf der Seite** Daten zur Qualität der Erfahrung auf die richtlinie, die Sie möchten, klicken Sie auf **Bearbeiten,** und klicken Sie dann auf **Löschen**.
    
5. Klicken Sie auf **OK**.
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von QoE-Konfigurationseinstellungen mithilfe Windows PowerShell Cmdlets

Sie können die QoE-Konfigurationseinstellungen mit Windows PowerShell und dem **Cmdlet Remove-CsQoEConfiguration** löschen. Sie können dieses Cmdlet entweder über die Skype for Business Server Management Shell oder über eine Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von QoE-Konfigurationseinstellungen

 Mit diesem Befehl werden die auf den Standort "Redmond" angewendeten QoE-Konfigurationseinstellungen entfernt:
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Standortbereich angewendeten QoE-Konfigurationseinstellungen

 Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, die auf den Standortbereich angewendet wurden:
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>So entfernen Sie alle QoE-Konfigurationseinstellungen, bei denen die QoE-Überwachung deaktiviert ist

 Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, bei denen die QoE-Überwachung deaktiviert wurde:
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

Weitere Informationen finden Sie unter [Remove-CsQoEConfiguration](/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).
  
## <a name="see-also"></a>Siehe auch

[Manuelles Löschen der Aufzeichnung von Anrufdetails und Der Benutzerqualitätsdatenbanken in Skype for Business Server](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)