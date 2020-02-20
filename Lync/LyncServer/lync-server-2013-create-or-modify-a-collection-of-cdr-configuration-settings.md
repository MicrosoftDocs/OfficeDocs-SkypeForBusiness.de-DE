---
title: 'Lync Server 2013: Erstellen oder Ändern einer Sammlung von KDS-Konfigurationseinstellungen'
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
ms.openlocfilehash: 6ddb442a2b919650706329b4acaf21311b096b4a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="466e8-102">Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="466e8-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="466e8-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="466e8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="466e8-104">Mit der Aufzeichnung von Kommunikationsdatensätzen (KDS) können Sie die Verwendung von Peer-zu-Peer-Sofortnachrichtensitzungen, VoIP-Telefon anrufen (Voice over Internet Protocol) und Konferenzanrufe nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="466e8-104">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="466e8-105">Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.</span><span class="sxs-lookup"><span data-stu-id="466e8-105">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="466e8-106">Bei der Installation von Microsoft lync Server 2013 wird eine einzelne, globale Sammlung von KDS-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="466e8-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="466e8-107">Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen auf Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="466e8-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="466e8-108">Wenn diese standortspezifischen Einstellungen verwendet werden, haben Sie Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="466e8-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="466e8-109">Wenn Sie beispielsweise standortspezifische Einstellungen für den Standort "Redmond" erstellen, werden diese Einstellungen (anstelle der globalen Einstellungen) zum Verwalten von KDS in Redmond verwendet.</span><span class="sxs-lookup"><span data-stu-id="466e8-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="466e8-110">Sie können KDS-Konfigurationseinstellungen entweder mit lync Server-Systemsteuerung oder mit dem [New-CsCdrConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet erstellen.</span><span class="sxs-lookup"><span data-stu-id="466e8-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="466e8-111">Sie können lync Server-Systemsteuerung oder das Cmdlet " [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) " verwenden, um vorhandene Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="466e8-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="466e8-112">Wenn Sie lync Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="466e8-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="466e8-113">UI-Einstellung</span><span class="sxs-lookup"><span data-stu-id="466e8-113">UI Setting</span></span></th>
<th><span data-ttu-id="466e8-114">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="466e8-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="466e8-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="466e8-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="466e8-116">Name</span><span class="sxs-lookup"><span data-stu-id="466e8-116">Name</span></span></p></td>
<td><p><span data-ttu-id="466e8-117">Identität</span><span class="sxs-lookup"><span data-stu-id="466e8-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="466e8-118">Eindeutiger Bezeichner für die zu erstellenden KDS-Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="466e8-118">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="466e8-119">Diese Einstellungen können nur auf Standortebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="466e8-119">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466e8-120">Aktivieren der Überwachung von CDRs</span><span class="sxs-lookup"><span data-stu-id="466e8-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="466e8-121">"Enablecdr"</span><span class="sxs-lookup"><span data-stu-id="466e8-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="466e8-122">Gibt an, ob KDS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="466e8-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466e8-123">Aktivieren der Bereinigung von CDRs</span><span class="sxs-lookup"><span data-stu-id="466e8-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="466e8-124">"Enablepurging"</span><span class="sxs-lookup"><span data-stu-id="466e8-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="466e8-125">Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="466e8-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="466e8-126">CDRs für maximale Dauer (Tage) beibehalten</span><span class="sxs-lookup"><span data-stu-id="466e8-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="466e8-127">"Keepcalldetailfordays"</span><span class="sxs-lookup"><span data-stu-id="466e8-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="466e8-128">Gibt an, wie viele Tage KDS-Einträge in der KDS-Datenbank aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="466e8-128">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="466e8-129">Alle Datensätze, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="466e8-129">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="466e8-130">(Beachten Sie, dass das Löschen nur erfolgen kann, wenn die Bereinigung aktiviert wurde.)</span><span class="sxs-lookup"><span data-stu-id="466e8-130">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="466e8-131">Fehlerberichtsdaten für maximale Dauer (Tage) aufbewahren</span><span class="sxs-lookup"><span data-stu-id="466e8-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="466e8-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="466e8-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="466e8-133">Gibt die Anzahl der Tage an, an denen KDS-Fehlerberichte aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="466e8-133">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="466e8-134">Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="466e8-134">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="466e8-135">CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="466e8-135">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="466e8-136">Die Cmdlets New-CsCdrConfiguration und Sets-CsCdrConfiguration enthalten zusätzliche Optionen, die in lync Server-Systemsteuerung nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="466e8-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="466e8-137">Weitere Informationen finden Sie in den Hilfethemen zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> und in den <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Sets-CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="466e8-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="466e8-138">So erstellen Sie KDS-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="466e8-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="466e8-139">Klicken Sie in lync Server-Systemsteuerung auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="466e8-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="466e8-140">Klicken Sie auf der Registerkarte **Anruf Detail Aufzeichnung** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="466e8-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="466e8-141">Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, an dem die neuen Konfigurationseinstellungen erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="466e8-141">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="466e8-142">Wenn das Dialogfeld leer ist, bedeutet dies, dass allen Websites bereits eine Sammlung von KDS-Konfigurationseinstellungen zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="466e8-142">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="466e8-143">Jede Website ist auf eine einzelne solche Sammlung limitiert.</span><span class="sxs-lookup"><span data-stu-id="466e8-143">Each site is limited to a single such collection.</span></span> <span data-ttu-id="466e8-144">In diesem Fall können Sie die Einstellungen entweder löschen und dann neu erstellen oder die vorhandenen Einstellungen einfach ändern.</span><span class="sxs-lookup"><span data-stu-id="466e8-144">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="466e8-145">Nehmen Sie im Dialogfeld neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen **(KDS)** die gewünschten Optionen vor, und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="466e8-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="466e8-146">So ändern Sie vorhandene KDS-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="466e8-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="466e8-147">Klicken Sie in lync Server-Systemsteuerung auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="466e8-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="466e8-148">Doppelklicken Sie auf die Auflistung der zu ändernden Einstellungen, oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="466e8-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="466e8-149">Beachten Sie, dass Sie nur eine einzelne Auflistung gleichzeitig ändern können.</span><span class="sxs-lookup"><span data-stu-id="466e8-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="466e8-150">Um dieselben Änderungen an mehreren Auflistungen vorzunehmen, verwenden Sie stattdessen die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="466e8-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="466e8-151">Nehmen Sie im Dialogfeld Einstellung für die Aufzeichnung von Kommunikationsdatensätzen **(KDS)** die gewünschten Optionen vor, und klicken Sie dann auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="466e8-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="466e8-152">Erstellen von KDS-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="466e8-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="466e8-153">Sie können KDS-Konfigurationseinstellungen auch mit Windows PowerShell und dem Cmdlet **New-CsCdrConfiguration** erstellen.</span><span class="sxs-lookup"><span data-stu-id="466e8-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="466e8-154">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="466e8-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="466e8-155">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="466e8-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="466e8-156">So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="466e8-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="466e8-157">Mit diesem Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen erstellt, die auf den Standort "Redmond" angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="466e8-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="466e8-158">So erstellen Sie eine Sammlung von KDS-Konfigurationseinstellungen, die die Aufzeichnung von Anrufdetails deaktivieren</span><span class="sxs-lookup"><span data-stu-id="466e8-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="466e8-159">Da in dem oben aufgeführten Befehl keine Parameter (außer dem obligatorischen Identity-Parameter) angegeben sind, werden in den neuen Konfigurationseinstellungen bei allen Eigenschaften die Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="466e8-159">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="466e8-160">Wenn Sie Einstellungen erstellen möchten, deren Eigenschaften andere Werte haben, fügen Sie in den Befehl einfach den entsprechenden Parameter mit dem gewünschten Wert ein.</span><span class="sxs-lookup"><span data-stu-id="466e8-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="466e8-161">Um beispielsweise eine Auflistung von Konfigurationseinstellungen für das Anruf Detail zu erstellen, die standardmäßig die Aufzeichnung von Anruf Detail Aufzeichnungen zulassen, verwenden Sie einen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="466e8-161">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="466e8-162">So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an</span><span class="sxs-lookup"><span data-stu-id="466e8-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="466e8-163">Sie können mehrere Eigenschaftswerte ändern, indem Sie mehrere Parameter einschließen.</span><span class="sxs-lookup"><span data-stu-id="466e8-163">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="466e8-164">Mit diesem Befehl werden beispielsweise die neuen Einstellungen so konfiguriert, dass Anruf Detail Datensätze für 30 Tage und Fehlerberichte für 90 Tage aufbewahrt werden:</span><span class="sxs-lookup"><span data-stu-id="466e8-164">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="466e8-165">Weitere Informationen finden Sie im Hilfethema zum [New-CsCdrConfiguration-](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="466e8-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

