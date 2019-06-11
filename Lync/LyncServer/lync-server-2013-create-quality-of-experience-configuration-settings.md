---
title: 'Lync Server 2013: Erstellen von Konfigurationseinstellungen für die Qualität der Benutzeroberfläche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="5dfcb-102">Erstellen von Konfigurationseinstellungen für die Qualität von Erfahrungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5dfcb-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5dfcb-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="5dfcb-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="5dfcb-p101">QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="5dfcb-106">Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzelne globale Sammlung von QoE-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="5dfcb-107">Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="5dfcb-108">Wenn diese standortspezifischen Einstellungen verwendet werden, haben sie Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="5dfcb-109">Beispiel: Wenn Sie für den Standort Redmond standortspezifische Einstellungen erstellen, wird QoE in Redmond gemäß diesen Einstellungen (anstelle der globalen) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="5dfcb-110">QoE-Konfigurationseinstellungen können entweder mit der lync Server-Systemsteuerung oder mit dem Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="5dfcb-111">Wenn Sie die lync Server-Systemsteuerung zum Erstellen neuer Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="5dfcb-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5dfcb-112">Benutzeroberflächeneinstellung</span><span class="sxs-lookup"><span data-stu-id="5dfcb-112">UI Setting</span></span></th>
<th><span data-ttu-id="5dfcb-113">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="5dfcb-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="5dfcb-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5dfcb-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5dfcb-115">Name</span><span class="sxs-lookup"><span data-stu-id="5dfcb-115">Name</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-116">Identität</span><span class="sxs-lookup"><span data-stu-id="5dfcb-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-p104">Eindeutiger Bezeichner für die zu erstellenden Einstellungen. QoE-Konfigurationseinstellungen können nur auf der Standortebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dfcb-119">Überwachung der QoE-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="5dfcb-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="5dfcb-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-121">Gibt an, ob QoE-Datensätze erfasst und in der Überwachungsdatenbank gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5dfcb-122">Löschvorgang für QoE-Daten aktivieren</span><span class="sxs-lookup"><span data-stu-id="5dfcb-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="5dfcb-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-124">Gibt an, ob Datensätze nach Ablauf des in der Eigenschaft <strong>QoE-Daten für maximal (Tage) aufbewahren</strong> festgelegten Zeitraums gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5dfcb-125">QoE-Daten für maximal (Tage) aufbewahren</span><span class="sxs-lookup"><span data-stu-id="5dfcb-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="5dfcb-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="5dfcb-p105">Zeitdauer in Tagen, die QoE-Daten gespeichert bleiben sollen, bevor sie aus der Datenbank gelöscht werden. Bei deaktiviertem Löschvorgang wird dieser Wert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5dfcb-129">Das Cmdlet New-CsQoEConfiguration enthält zusätzliche Optionen, die in der lync Server-Systemsteuerung nicht zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="5dfcb-130">Weitere Informationen finden Sie im Hilfethema zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="5dfcb-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="5dfcb-131">So erstellen Sie QoE-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="5dfcb-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="5dfcb-132">Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="5dfcb-133">Ausführliche Informationen finden Sie unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcb-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5dfcb-134">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5dfcb-135">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5dfcb-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5dfcb-136">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="5dfcb-137">Klicken Sie auf der Seite **QoE-Daten** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="5dfcb-138">Klicken Sie unter **Standort auswählen** auf den Standort, auf den die Richtlinie angewendet werden soll und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="5dfcb-139">Tun Sie unter **Neue QoE-Einstellung** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5dfcb-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="5dfcb-140">Wählen Sie **Überwachung der QoE-Daten aktivieren** aus, um die Überwachung einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="5dfcb-141">Wählen Sie **Löschvorgang für QoE-Daten aktivieren** aus, um den Löschvorgang einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="5dfcb-142">Wählen Sie unter **QoE-Daten für maximal (Tage) aufbewahren** aus, wie viele Tage QoE-Datensätze maximal aufbewahrt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="5dfcb-143">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="5dfcb-144">Erstellen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="5dfcb-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="5dfcb-145">Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet New-CsQoEConfiguration erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="5dfcb-146">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="5dfcb-147">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="5dfcb-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="5dfcb-148">So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="5dfcb-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="5dfcb-149">Dieser Befehl erstellt eine neue Auflistung von QoE-Konfigurationseinstellungen, die für den Standort „Redmond“ gelten sollen:</span><span class="sxs-lookup"><span data-stu-id="5dfcb-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="5dfcb-150">So erstellen Sie eine neue Auflistung von QoE-Konfigurationseinstellungen mit deaktivierter QoE-Überwachung</span><span class="sxs-lookup"><span data-stu-id="5dfcb-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="5dfcb-p110">Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet. Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein. Beispiel: Zum Erstellen von QoE-Konfigurationseinstellungen, die es standardmäßig erlauben, die QoE-Aufzeichnung zu deaktivieren, verwenden Sie einen Befehl der folgenden Art:</span><span class="sxs-lookup"><span data-stu-id="5dfcb-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="5dfcb-154">So geben Sie beim Erstellen einer neuen Auflistung von QoE-Konfigurationseinstellungen mehrere Eigenschaftswerte an:</span><span class="sxs-lookup"><span data-stu-id="5dfcb-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="5dfcb-p111">Sie können mehrere Eigenschaftswerte angeben, indem Sie mehrere Parameter in den Befehl einfügen. So konfiguriert zum Beispiel dieser Befehl die neuen Einstellungen so, dass QoE-Daten 30 Tage aufbewahrt und alte Daten um 03:00 Uhr bereinigt werden:</span><span class="sxs-lookup"><span data-stu-id="5dfcb-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="5dfcb-157">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5dfcb-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

