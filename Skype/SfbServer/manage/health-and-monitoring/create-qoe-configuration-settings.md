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
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="0e604-103">Erstellen von Konfigurationseinstellungen für die Qualität von Erfahrungen in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0e604-103">Create Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="0e604-104">**Zusammenfassung:** Informieren Sie sich über die Einstellungen für Quality of Experience (QoE) in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0e604-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="0e604-p101">QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e604-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="0e604-107">Wenn Sie Skype for Business Server installieren, wird eine einzige globale Sammlung von QoE-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="0e604-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="0e604-108">Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e604-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="0e604-109">Wenn diese standortspezifischen Einstellungen verwendet werden, haben sie Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0e604-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="0e604-110">Beispiel: Wenn Sie für den Standort Redmond standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0e604-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="0e604-111">QoE-Konfigurationseinstellungen können entweder über die Skype for Business Server-Systemsteuerung oder über das Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e604-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="0e604-112">Wenn Sie die Skype for Business Server-Systemsteuerung zum Erstellen neuer Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="0e604-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="0e604-113">**Benutzeroberflächeneinstellung**</span><span class="sxs-lookup"><span data-stu-id="0e604-113">**UI setting**</span></span>|<span data-ttu-id="0e604-114">**PowerShell-Parameter**</span><span class="sxs-lookup"><span data-stu-id="0e604-114">**PowerShell parameter**</span></span>|<span data-ttu-id="0e604-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0e604-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e604-116">Name</span><span class="sxs-lookup"><span data-stu-id="0e604-116">Name</span></span>  <br/> |<span data-ttu-id="0e604-117">Identität</span><span class="sxs-lookup"><span data-stu-id="0e604-117">Identity</span></span>  <br/> |<span data-ttu-id="0e604-p104">Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="0e604-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="0e604-120">Überwachung der QoE-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="0e604-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="0e604-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="0e604-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="0e604-122">Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0e604-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="0e604-123">Löschvorgang für QoE-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="0e604-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="0e604-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="0e604-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="0e604-125">Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft **QoE-Daten für maximal (Tage) aufbewahren** festgelegten Zeitraums gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0e604-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="0e604-126">QoE-Daten für maximal (Tage) aufbewahren</span><span class="sxs-lookup"><span data-stu-id="0e604-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="0e604-127">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="0e604-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="0e604-p105">Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank gelöscht werden. Bei deaktiviertem Löschvorgang wird dieser Wert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="0e604-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="0e604-130">Das Cmdlet New-CsQoEConfiguration enthält zusätzliche Optionen, die in der Skype for Business Server-Systemsteuerung nicht zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="0e604-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="0e604-131">Weitere Informationen finden Sie im Hilfethema zu [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0e604-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0e604-132">So erstellen Sie QoE-Konfigurationseinstellungen mithilfe der Skype for Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0e604-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="0e604-p107">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="0e604-p107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="0e604-135">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="0e604-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="0e604-136">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="0e604-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="0e604-137">Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="0e604-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="0e604-138">Klicken Sie unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e604-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="0e604-139">Tun Sie unter **Neue QoE-Einstellung** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0e604-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="0e604-140">Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="0e604-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="0e604-141">Wählen Sie **Löschvorgang für QoE-Daten aktivieren** aus, um den Löschvorgang einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="0e604-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="0e604-142">Wählen Sie unter **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0e604-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="0e604-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="0e604-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0e604-144">Erstellen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0e604-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0e604-145">Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet New-CsQoEConfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="0e604-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="0e604-146">Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e604-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0e604-147">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="0e604-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="0e604-148">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="0e604-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="0e604-149">So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="0e604-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="0e604-150">Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort „Redmond“ gelten sollen:</span><span class="sxs-lookup"><span data-stu-id="0e604-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="0e604-151">So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen mit deaktivierter QoE-Überwachung</span><span class="sxs-lookup"><span data-stu-id="0e604-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="0e604-p109">Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Beispiel: Zum Erstellen von QoE-Konfigurationseinstellungen, die es standardmäßig erlauben, die QoE-Aufzeichnung zu deaktivieren, verwenden Sie einen Befehl der folgenden Art:</span><span class="sxs-lookup"><span data-stu-id="0e604-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="0e604-155">So geben Sie beim Erstellen einer neuen Auflistung von QoE-Konfigurationseinstellungen mehrere Eigenschaftswerte an:</span><span class="sxs-lookup"><span data-stu-id="0e604-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="0e604-p110">Sie können mehrere Eigenschaftswerte angeben, indem Sie mehrere Parameter in den Befehl einfügen. So konfiguriert zum Beispiel dieser Befehl die neuen Einstellungen so, dass QoE-Daten 30 Tage aufbewahrt und alte Daten um 03:00 Uhr bereinigt werden:</span><span class="sxs-lookup"><span data-stu-id="0e604-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="0e604-158">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="0e604-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

