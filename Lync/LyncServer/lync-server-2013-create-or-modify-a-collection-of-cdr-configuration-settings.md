---
title: 'Lync Server 2013: Erstellen oder Ändern einer Sammlung von KDS-Konfigurationseinstellungen'
description: 'Lync Server 2013: Erstellen oder ändern Sie eine Sammlung von KDS-Konfigurationseinstellungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba911607db55a7b7206645495e70a27ed453784
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578331"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f5845-103">Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5845-103">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5845-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f5845-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f5845-105">Mit der Aufzeichnung von Kommunikationsdatensätzen (KDS) können Sie die Verwendung von Peer-zu-Peer-Sofortnachrichtensitzungen, VoIP-Telefon anrufen (Voice over Internet Protocol) und Konferenzanrufe nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="f5845-105">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="f5845-106">Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.</span><span class="sxs-lookup"><span data-stu-id="f5845-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="f5845-107">Bei der Installation von Microsoft lync Server 2013 wird eine einzelne, globale Sammlung von KDS-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5845-107">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="f5845-108">Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5845-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="f5845-109">Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="f5845-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="f5845-110">Wenn Sie beispielsweise standortspezifische Einstellungen für den Standort "Redmond" erstellen, werden diese Einstellungen (anstelle der globalen Einstellungen) zum Verwalten von KDS in Redmond verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5845-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="f5845-111">Sie können KDS-Konfigurationseinstellungen entweder mit lync Server-Systemsteuerung oder mit dem [New-CsCdrConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5845-111">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="f5845-112">Sie können lync Server-Systemsteuerung oder das Cmdlet " [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) " verwenden, um vorhandene Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f5845-112">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="f5845-113">Wenn Sie lync Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f5845-113">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5845-114">UI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="f5845-114">UI Setting</span></span></th>
<th><span data-ttu-id="f5845-115">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="f5845-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="f5845-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f5845-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5845-117">Name</span><span class="sxs-lookup"><span data-stu-id="f5845-117">Name</span></span></p></td>
<td><p><span data-ttu-id="f5845-118">Identität</span><span class="sxs-lookup"><span data-stu-id="f5845-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="f5845-119">Eindeutiger Bezeichner für die zu erstellenden KDS-Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="f5845-119">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="f5845-120">Diese Einstellungen können nur auf Standortebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f5845-120">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5845-121">Aktivieren der Überwachung von CDRs</span><span class="sxs-lookup"><span data-stu-id="f5845-121">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="f5845-122">"Enablecdr"</span><span class="sxs-lookup"><span data-stu-id="f5845-122">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="f5845-123">Gibt an, ob KDS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f5845-123">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5845-124">Aktivieren der Bereinigung von CDRs</span><span class="sxs-lookup"><span data-stu-id="f5845-124">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="f5845-125">"Enablepurging"</span><span class="sxs-lookup"><span data-stu-id="f5845-125">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="f5845-126">Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="f5845-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5845-127">CDRs für maximale Dauer (Tage) beibehalten</span><span class="sxs-lookup"><span data-stu-id="f5845-127">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="f5845-128">"Keepcalldetailfordays"</span><span class="sxs-lookup"><span data-stu-id="f5845-128">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="f5845-129">Gibt an, wie viele Tage KDS-Einträge in der KDS-Datenbank aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="f5845-129">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="f5845-130">Alle Datensätze, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f5845-130">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="f5845-131">(Beachten Sie, dass das Löschen nur erfolgen kann, wenn die Bereinigung aktiviert wurde.)</span><span class="sxs-lookup"><span data-stu-id="f5845-131">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5845-132">Fehlerberichtsdaten für maximale Dauer (Tage) aufbewahren</span><span class="sxs-lookup"><span data-stu-id="f5845-132">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="f5845-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="f5845-133">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="f5845-134">Gibt die Anzahl der Tage an, an denen KDS-Fehlerberichte aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="f5845-134">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="f5845-135">Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f5845-135">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="f5845-136">CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="f5845-136">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f5845-137">Die Cmdlets New-CsCdrConfiguration und Set-CsCdrConfiguration enthalten zusätzliche Optionen, die in lync Server-Systemsteuerung nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="f5845-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="f5845-138">Weitere Informationen finden Sie in den Hilfethemen zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> und in den <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Sets-CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="f5845-138">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f5845-139">So erstellen Sie KDS-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f5845-139">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f5845-140">Klicken Sie in lync Server-Systemsteuerung auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="f5845-140">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="f5845-141">Klicken Sie auf der Registerkarte **Anruf Detail Aufzeichnung** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="f5845-141">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="f5845-142">Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, an dem die neuen Konfigurationseinstellungen erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5845-142">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="f5845-143">Wenn das Dialogfeld leer ist, bedeutet dies, dass allen Websites bereits eine Sammlung von KDS-Konfigurationseinstellungen zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="f5845-143">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="f5845-144">Jede Website ist auf eine einzelne solche Sammlung limitiert.</span><span class="sxs-lookup"><span data-stu-id="f5845-144">Each site is limited to a single such collection.</span></span> <span data-ttu-id="f5845-145">In diesem Fall können Sie die Einstellungen entweder löschen und dann neu erstellen oder die vorhandenen Einstellungen einfach ändern.</span><span class="sxs-lookup"><span data-stu-id="f5845-145">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="f5845-146">Nehmen Sie im Dialogfeld neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen **(KDS)** die gewünschten Optionen vor, und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f5845-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="f5845-147">So ändern Sie vorhandene KDS-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="f5845-147">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f5845-148">Klicken Sie in lync Server-Systemsteuerung auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="f5845-148">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="f5845-149">Doppelklicken Sie auf die Auflistung der zu ändernden Einstellungen, oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f5845-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="f5845-150">Beachten Sie, dass Sie nur eine einzelne Auflistung gleichzeitig ändern können.</span><span class="sxs-lookup"><span data-stu-id="f5845-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="f5845-151">Um dieselben Änderungen an mehreren Auflistungen vorzunehmen, verwenden Sie stattdessen die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="f5845-151">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="f5845-152">Nehmen Sie im Dialogfeld Einstellung für die Aufzeichnung von Kommunikationsdatensätzen **(KDS)** die gewünschten Optionen vor, und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f5845-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f5845-153">Erstellen von KDS-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f5845-153">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f5845-154">Sie können KDS-Konfigurationseinstellungen auch mit Windows PowerShell und dem Cmdlet **New-CsCdrConfiguration** erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5845-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="f5845-155">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5845-155">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f5845-156">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f5845-156">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="f5845-157">So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="f5845-157">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="f5845-158">Mit diesem Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen erstellt, die auf den Standort "Redmond" angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="f5845-158">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="f5845-159">So erstellen Sie eine Sammlung von KDS-Konfigurationseinstellungen, die die Aufzeichnung von Anrufdetails deaktivieren</span><span class="sxs-lookup"><span data-stu-id="f5845-159">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="f5845-160">Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5845-160">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="f5845-161">Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein.</span><span class="sxs-lookup"><span data-stu-id="f5845-161">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="f5845-162">Um beispielsweise eine Auflistung von Konfigurationseinstellungen für das Anruf Detail zu erstellen, die standardmäßig die Aufzeichnung von Anruf Detail Aufzeichnungen zulassen, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="f5845-162">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="f5845-163">So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an</span><span class="sxs-lookup"><span data-stu-id="f5845-163">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="f5845-164">Sie können mehrere Eigenschaftswerte ändern, indem Sie mehrere Parameter einschließen.</span><span class="sxs-lookup"><span data-stu-id="f5845-164">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="f5845-165">Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Anruf Detail Datensätze für 30 Tage und Fehlerberichte für 90 Tage aufbewahrt werden:</span><span class="sxs-lookup"><span data-stu-id="f5845-165">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="f5845-166">Weitere Informationen finden Sie im Hilfethema zum [New-CsCdrConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="f5845-166">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

