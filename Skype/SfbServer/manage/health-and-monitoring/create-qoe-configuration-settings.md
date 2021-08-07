---
title: Erstellen von QoE-Konfigurationseinstellungen in Skype for Business Server
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Zusammenfassung: Erfahren Sie mehr über QoE-Einstellungen (Quality of Experience) in Skype for Business Server.'
ms.openlocfilehash: 2f9c233b46588bd70566606f538451063802f5f3d35c4ffef59a8d0f7e6d85f9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305437"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Erstellen von QoE-Konfigurationseinstellungen in Skype for Business Server
 
**Zusammenfassung:** Erfahren Sie mehr über QoE-Einstellungen (Quality of Experience) in Skype for Business Server.
  
QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.
  
Wenn Sie Skype for Business Server installieren, wird eine einzelne, globale Sammlung von QoE-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen. Beispiel: Wenn Sie für den Standort "Redmond" standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.
  
QoE-Konfigurationseinstellungen können entweder mit Skype for Business Server Systemsteuerung oder mit dem Cmdlet ["New-CsQoEConfiguration"](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) erstellt werden. Wenn Sie Skype for Business Server Systemsteuerung verwenden, um neue Einstellungen zu erstellen, stehen Ihnen die folgenden Optionen zur Verfügung:
  
|**UI-Einstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.  <br/> |
|Überwachung der QoE-Daten aktivieren  <br/> |EnableQoE  <br/> |Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden sollen.  <br/> |
|Bereinigungsfunktion für QoE-Daten aktivieren  <br/> |EnablePurging  <br/> |Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft **QoE-Daten für maximal (Tage) aufbewahren** festgelegten Zeitraums bereinigt werden sollen. <br/> |
|QoE-Daten für maximal (Tage) aufbewahren  <br/> |KeepQoEDataForDays  <br/> |Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank bereinigt werden. Bei deaktivierter Bereinigung wird dieser Wert ignoriert.  <br/> |
   
> [!NOTE]
> Das cmdlet New-CsQoEConfiguration enthält zusätzliche Optionen, die in Skype for Business Server Systemsteuerung nicht verfügbar sind. Weitere Informationen finden Sie im Hilfethema ["New-CsQoEConfiguration".](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie QoE-Konfigurationseinstellungen mithilfe Skype for Business Server Systemsteuerung

1. Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.
    
4. Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.
    
5. Klicken Sie in **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll, und klicken Sie dann auf **OK**.
    
6. Führen Sie in **Neue QoE-Einstellung** die folgenden Aktionen aus:
    
   - Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.
    
   - Wählen Sie **Bereinigungsfunktion für QoE-Daten aktivieren** aus, um die Bereinigung zu aktivieren.
    
   - Wählen Sie in **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.
    
7. Klicken Sie auf **Commit**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von QoE-Konfigurations-Einstellungen mithilfe Windows PowerShell Cmdlets

Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet New-CsQoEConfiguration erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell".](https://go.microsoft.com/fwlink/p/?linkId=255876) Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen

 Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort "Redmond" gelten sollen:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen mit deaktivierter QoE-Überwachung

 Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Beispiel: Zum Erstellen von QoE-Konfigurationseinstellungen, die es standardmäßig erlauben, die QoE-Aufzeichnung zu deaktivieren, verwenden Sie einen Befehl der folgenden Art:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>So geben Sie beim Erstellen einer neuen Auflistung von QoE-Konfigurationseinstellungen mehrere Eigenschaftswerte an:

 Sie können mehrere Eigenschaftswerte angeben, indem Sie mehrere Parameter in den Befehl einfügen. So konfiguriert zum Beispiel dieser Befehl die neuen Einstellungen so, dass QoE-Daten 30 Tage aufbewahrt und alte Daten um 03:00 Uhr bereinigt werden:
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet ["New-CsQoEConfiguration".](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)
