---
title: Erstellen von QoE-Konfigurationseinstellungen in Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 'Zusammenfassung: Informationen Sie zu Quality of Experience (QoE)-Einstellungen in Skype für Business Server 2015.'
ms.openlocfilehash: a6ba2906b54ac5d963b0c8394c1fcf254cffd12d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="ea4d3-103">Erstellen von QoE-Konfigurationseinstellungen in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ea4d3-103">Create Quality of Experience configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ea4d3-104">**Zusammenfassung:** Informationen Sie zu Quality of Experience (QoE)-Einstellungen in Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-104">**Summary:** Learn about Quality of Experience (QoE) settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ea4d3-p101">QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="ea4d3-107">Bei der Installation von Skype für Business Server 2015, ein einzelnes wird die globale Auflistung von QoE-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-107">When you install Skype for Business Server 2015, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="ea4d3-108">Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="ea4d3-109">Wenn diese standortspezifischen Einstellungen verwendet werden, haben sie Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="ea4d3-110">Beispiel: Wenn Sie für den Standort Redmond standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>
  
<span data-ttu-id="ea4d3-111">QoE-Konfigurationseinstellungen können unter Verwendung von entweder Skype für Business Server-Systemsteuerung oder das [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) -Cmdlet erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-111">QoE configuration settings can be created by using either Skype for Business Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="ea4d3-112">Wenn Sie Skype Business Server-Systemsteuerung verwenden, erstellen Sie neue Einstellungen werden die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="ea4d3-112">If you are using Skype for Business Server Control Panel to create new settings the following options will be available to you:</span></span>
  
|<span data-ttu-id="ea4d3-113">**UI-Einstellung**</span><span class="sxs-lookup"><span data-stu-id="ea4d3-113">**UI setting**</span></span>|<span data-ttu-id="ea4d3-114">**PowerShell-parameter**</span><span class="sxs-lookup"><span data-stu-id="ea4d3-114">**PowerShell parameter**</span></span>|<span data-ttu-id="ea4d3-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ea4d3-115">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea4d3-116">Name</span><span class="sxs-lookup"><span data-stu-id="ea4d3-116">Name</span></span>  <br/> |<span data-ttu-id="ea4d3-117">Identität</span><span class="sxs-lookup"><span data-stu-id="ea4d3-117">Identity</span></span>  <br/> |<span data-ttu-id="ea4d3-p104">Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span>  <br/> |
|<span data-ttu-id="ea4d3-120">Überwachung der QoE-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="ea4d3-120">Enable monitoring of QoE data</span></span>  <br/> |<span data-ttu-id="ea4d3-121">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="ea4d3-121">EnableQoE</span></span>  <br/> |<span data-ttu-id="ea4d3-122">Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-122">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span>  <br/> |
|<span data-ttu-id="ea4d3-123">Löschvorgang für QoE-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="ea4d3-123">Enable purging of QoE data</span></span>  <br/> |<span data-ttu-id="ea4d3-124">"Enablepurging"</span><span class="sxs-lookup"><span data-stu-id="ea4d3-124">EnablePurging</span></span>  <br/> |<span data-ttu-id="ea4d3-125">Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft **QoE-Daten für maximal (Tage) aufbewahren** festgelegten Zeitraums gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-125">Specifies whether records will be purged after the duration defined in the **Keep QoE data for a maximum duration (days)** property has elapsed.</span></span> <br/> |
|<span data-ttu-id="ea4d3-126">QoE-Daten für maximal (Tage) aufbewahren</span><span class="sxs-lookup"><span data-stu-id="ea4d3-126">Keep QoE data for maximum duration (days)</span></span>  <br/> |<span data-ttu-id="ea4d3-127">"Keepqoedatafordays"</span><span class="sxs-lookup"><span data-stu-id="ea4d3-127">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="ea4d3-p105">Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank gelöscht werden. Bei deaktiviertem Löschvorgang wird dieser Wert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="ea4d3-130">Das Cmdlet New-CsQoEConfiguration enthält zusätzliche Optionen für die Business Server-Systemsteuerung in Skype nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-130">The New-CsQoEConfiguration cmdlet includes additional options not available in Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ea4d3-131">Weitere Informationen finden Sie im Hilfethema [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ea4d3-131">For more information, see the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) help topic.</span></span>
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ea4d3-132">Erstellen Sie QoE-Konfigurationseinstellungen mithilfe von Skype Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ea4d3-132">To create QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ea4d3-133">Melden Sie sich an dem Computer als Mitglied der Gruppe RTCUniversalServerAdmins oder als Mitglied der Rolle CsVoiceAdministrator, CsServerAdministrator oder csadministrator an.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-133">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="ea4d3-134">Weitere Informationen hierzu finden Sie unter **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-134">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="ea4d3-135">Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL, um die Skype Business Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-135">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ea4d3-136">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="ea4d3-137">Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-137">On the **Quality of Experience Data** page, click **New**.</span></span>
    
5. <span data-ttu-id="ea4d3-138">Klicken Sie unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>
    
6. <span data-ttu-id="ea4d3-139">Tun Sie unter **Neue QoE-Einstellung** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ea4d3-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
   - <span data-ttu-id="ea4d3-140">Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
   - <span data-ttu-id="ea4d3-141">Wählen Sie **Löschvorgang für QoE-Daten aktivieren** aus, um den Löschvorgang einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
   - <span data-ttu-id="ea4d3-142">Wählen Sie unter **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>
    
7. <span data-ttu-id="ea4d3-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-143">Click **Commit**.</span></span>
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ea4d3-144">Erstellen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ea4d3-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ea4d3-145">Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und das New-CsQoEConfiguration-Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="ea4d3-146">Sie können dieses Cmdlet entweder von der Skype für Business Server-Verwaltungsshell oder aus einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-146">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ea4d3-147">Weitere Informationen zur Verwendung von remote Windows PowerShell zum Skype für Business Server herstellen finden Sie im Blog-Artikel ["Quick Start: Verwalten von Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="ea4d3-147">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="ea4d3-148">Der Vorgang ist in Skype für Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-148">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="ea4d3-149">So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="ea4d3-149">To create a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="ea4d3-150">Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort „Redmond“ gelten sollen:</span><span class="sxs-lookup"><span data-stu-id="ea4d3-150">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="ea4d3-151">So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen mit deaktivierter QoE-Überwachung</span><span class="sxs-lookup"><span data-stu-id="ea4d3-151">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="ea4d3-p109">Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Beispiel: Zum Erstellen von QoE-Konfigurationseinstellungen, die es standardmäßig erlauben, die QoE-Aufzeichnung zu deaktivieren, verwenden Sie einen Befehl der folgenden Art:</span><span class="sxs-lookup"><span data-stu-id="ea4d3-p109">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="ea4d3-155">So geben Sie beim Erstellen einer neuen Auflistung von QoE-Konfigurationseinstellungen mehrere Eigenschaftswerte an:</span><span class="sxs-lookup"><span data-stu-id="ea4d3-155">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

 <span data-ttu-id="ea4d3-p110">Sie können mehrere Eigenschaftswerte angeben, indem Sie mehrere Parameter in den Befehl einfügen. So konfiguriert zum Beispiel dieser Befehl die neuen Einstellungen so, dass QoE-Daten 30 Tage aufbewahrt und alte Daten um 03:00 Uhr bereinigt werden:</span><span class="sxs-lookup"><span data-stu-id="ea4d3-p110">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

<span data-ttu-id="ea4d3-158">Weitere Informationen finden Sie im Hilfethema für das [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) -Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="ea4d3-158">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  

