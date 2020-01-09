---
title: Erstellen von Konfigurationseinstellungen für die Qualität von Erfahrungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Zusammenfassung: Informationen zu den QoE-Einstellungen (Quality of Experience) in Skype for Business Server.'
ms.openlocfilehash: 254e6f1032026f715c30017f984bc2906f46e0df
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992792"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Erstellen von Konfigurationseinstellungen für die Qualität von Erfahrungen in Skype for Business Server
 
**Zusammenfassung:** Informieren Sie sich über die Einstellungen für Quality of Experience (QoE) in Skype for Business Server.
  
QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.
  
Wenn Sie Skype for Business Server installieren, wird eine einzige globale Sammlung von QoE-Konfigurationseinstellungen für Sie erstellt. Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen. Wenn diese standortspezifischen Einstellungen verwendet werden, haben sie Vorrang vor den globalen Einstellungen. Beispiel: Wenn Sie für den Standort Redmond standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.
  
QoE-Konfigurationseinstellungen können entweder über die Skype for Business Server-Systemsteuerung oder über das Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) erstellt werden. Wenn Sie die Skype for Business Server-Systemsteuerung zum Erstellen neuer Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:
  
|**Benutzeroberflächeneinstellung**|**PowerShell-Parameter**|**Beschreibung**|
|:-----|:-----|:-----|
|Name  <br/> |Identität  <br/> |Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.  <br/> |
|Überwachung der QoE-Daten aktivieren  <br/> |EnableQoE  <br/> |Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden.  <br/> |
|Löschvorgang für QoE-Daten aktivieren  <br/> |EnablePurging  <br/> |Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft **QoE-Daten für maximal (Tage) aufbewahren** festgelegten Zeitraums gelöscht werden sollen. <br/> |
|QoE-Daten für maximal (Tage) aufbewahren  <br/> |KeepQoEDataForDays  <br/> |Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank gelöscht werden. Bei deaktiviertem Löschvorgang wird dieser Wert ignoriert.  <br/> |
   
> [!NOTE]
> Das Cmdlet New-CsQoEConfiguration enthält zusätzliche Optionen, die in der Skype for Business Server-Systemsteuerung nicht zur Verfügung stehen. Weitere Informationen finden Sie im Hilfethema zu [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>So erstellen Sie QoE-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung

1. Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.
    
2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.  
    
3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.
    
4. Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.
    
5. Klicken Sie unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll und klicken Sie dann auf **OK**.
    
6. Tun Sie unter **Neue QoE-Einstellung** Folgendes:
    
   - Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.
    
   - Wählen Sie **Löschvorgang für QoE-Daten aktivieren** aus, um den Löschvorgang einzuschalten.
    
   - Wählen Sie unter **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.
    
7. Klicken Sie auf **Commit ausführen**.
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Erstellen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet New-CsQoEConfiguration erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen

 Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort „Redmond“ gelten sollen:
    
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

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .
  

