---
title: 'Lync Server 2013: Erstellen oder Ändern einer Sammlung von CDR-Konfigurationseinstellungen'
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
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e8212-102">Erstellen oder Ändern einer Sammlung von CDR-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8212-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8212-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="e8212-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="e8212-p101">Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.</span><span class="sxs-lookup"><span data-stu-id="e8212-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="e8212-106">Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzige globale Sammlung von CDR-Konfigurationseinstellungen für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="e8212-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="e8212-107">Administratoren haben auch die Möglichkeit, benutzerdefinierte Einstellungen für die Standortebene zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8212-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="e8212-108">Wenn diese Einstellungen auf Standortebene verwendet werden, haben sie Vorrang vor den globalen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e8212-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="e8212-109">Wenn Sie beispielsweise Einstellungen auf Standortebene für den Standort „Redmond“ erstellen, werden diese Einstellung (anstelle der globalen Einstellungen) für die KDS-Verwaltung in Redmond verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8212-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="e8212-110">Sie können CdR-Konfigurationseinstellungen entweder mithilfe der lync Server-Systemsteuerung oder mit dem Cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) erstellen.</span><span class="sxs-lookup"><span data-stu-id="e8212-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="e8212-111">Sie können die lync Server-Systemsteuerung oder das Cmdlet " [Satz-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) " verwenden, um vorhandene Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e8212-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="e8212-112">Wenn Sie die lync Server-Systemsteuerung zum Erstellen oder Ändern von Einstellungen verwenden, stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="e8212-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e8212-113">Benutzeroberflächeneinstellung</span><span class="sxs-lookup"><span data-stu-id="e8212-113">UI Setting</span></span></th>
<th><span data-ttu-id="e8212-114">PowerShell-Parameter</span><span class="sxs-lookup"><span data-stu-id="e8212-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="e8212-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8212-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e8212-116">Name</span><span class="sxs-lookup"><span data-stu-id="e8212-116">Name</span></span></p></td>
<td><p><span data-ttu-id="e8212-117">Identität</span><span class="sxs-lookup"><span data-stu-id="e8212-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="e8212-p104">Eindeutiger Bezeichner für die KDS-Konfigurationseinstellungen, die erstellt werden. Diese Einstellungen können nur auf der Standortebene erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e8212-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8212-120">Überwachung von KDS-Aufzeichnungen aktivieren</span><span class="sxs-lookup"><span data-stu-id="e8212-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="e8212-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="e8212-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="e8212-122">Gibt an, ob KDS aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8212-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8212-123">Bereinigung von KDS-Aufzeichnungen aktivieren</span><span class="sxs-lookup"><span data-stu-id="e8212-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="e8212-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="e8212-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="e8212-125">Gibt an, ob Kommunikationsdatensätze (KDS) regelmäßig aus der KDS-Datenbank gelöscht werden oder nicht.</span><span class="sxs-lookup"><span data-stu-id="e8212-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e8212-126">Maximale Aufbewahrungsdauer für KDS-Aufzeichnungen (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="e8212-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="e8212-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="e8212-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="e8212-p105">Gibt die Anzahl von Tagen an, die KDS-Datensätze in der KDS-Datenbank gespeichert werden. Datensätze, die älter sind als angegeben, werden automatisch gelöscht. (Beachten Sie, dass der Löschvorgang nur stattfindet, wenn die Bereinigung aktiviert wurde.)</span><span class="sxs-lookup"><span data-stu-id="e8212-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e8212-131">Maximale Aufbewahrungsdauer von Fehlerberichtsdaten (in Tagen)</span><span class="sxs-lookup"><span data-stu-id="e8212-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="e8212-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="e8212-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="e8212-p106">Gibt die Anzahl von Tagen an, die KDS-Fehlerberichte aufbewahrt werden. Berichte, die älter sind als angegeben, werden automatisch gelöscht. Fehlerberichte zu Kommunikationsdatensätzen sind Diagnoseberichte, die von Clientanwendungen hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="e8212-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e8212-136">Die Cmdlets New-CsCdrConfiguration und CsCdrConfiguration umfassen zusätzliche Optionen, die in der lync Server-Systemsteuerung nicht zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="e8212-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="e8212-137">Weitere Informationen finden Sie in den Hilfethemen zu <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> und den <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Satz-CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="e8212-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e8212-138">So erstellen Sie CDR-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e8212-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e8212-139">Klicken Sie in der lync Server-Systemsteuerung auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="e8212-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e8212-140">Klicken Sie auf der Registerkarte **Anruf Detail Aufzeichnung** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="e8212-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="e8212-p108">Wählen Sie im Dialogfeld **Standort auswählen** den Standort aus, in dem die neuen Konfigurationseinstellungen erstellt werden sollen. Falls das Dialogfeld leer ist, bedeutet dies, dass allen Ihren Standorten bereits eine Auflistung von KDS-Konfigurationseinstellungen zugewiesen wurde. Für jeden Standort ist nur eine einzige derartige Auflistung zulässig. In diesem Fall können Sie entweder die Einstellungen löschen und anschließend neu erstellen oder aber einfach die vorhandenen Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="e8212-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="e8212-145">Wählen Sie im Dialogfeld **Neue Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS)** die gewünschten Optionen aus und klicken Sie dann auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e8212-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e8212-146">So ändern Sie vorhandene CdR-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="e8212-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e8212-147">Klicken Sie in der lync Server-Systemsteuerung auf **Überwachung und Archivierung**.</span><span class="sxs-lookup"><span data-stu-id="e8212-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="e8212-148">Doppelklicken Sie auf die zu ändernde Auflistung von Einstellungen oder wählen Sie die Auflistung aus, klicken Sie auf **Bearbeiten** und klicken Sie anschließend auf **Details einblenden**.</span><span class="sxs-lookup"><span data-stu-id="e8212-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="e8212-149">Beachten Sie, dass Sie jeweils immer nur eine Auflistung ändern können.</span><span class="sxs-lookup"><span data-stu-id="e8212-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="e8212-150">Wenn Sie die gleichen Änderungen an mehreren Auflistungen vornehmen möchten, verwenden Sie stattdessen die lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e8212-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="e8212-151">Wählen Sie im Dialogfeld **Einstellung für die Aufzeichnung von Kommunikationsdatensätzen (KDS) bearbeiten** die gewünschten Optionen aus und klicken Sie dann auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="e8212-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e8212-152">Erstellen von CDR-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e8212-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e8212-153">Sie können CdR-Konfigurationseinstellungen erstellen, die auch mithilfe von Windows PowerShell und dem Cmdlet **New-CsCdrConfiguration** erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="e8212-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="e8212-154">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="e8212-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e8212-155">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="e8212-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="e8212-156">So erstellen Sie eine neue Auflistung von KDS-Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e8212-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="e8212-157">Mit dem folgenden Befehl wird eine neue Auflistung von KDS-Konfigurationseinstellungen für den Standort „Redmond“ erstellt:</span><span class="sxs-lookup"><span data-stu-id="e8212-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="e8212-158">So erstellen Sie eine Auflistung von KDS-Konfigurationseinstellungen, mit denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wird</span><span class="sxs-lookup"><span data-stu-id="e8212-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="e8212-p111">Da im vorherigen Befehl keine weiteren Parameter (außer dem obligatorischen Identity-Parameter) angegeben wurden, werden in der neuen Auflistung von Konfigurationseinstellungen für alle Eigenschaften die Standardwerte verwendet. Um Einstellungen zu erstellen, die andere Eigenschaftswerte verwenden, geben Sie einfach den entsprechenden Parameter und Parameterwert ein. Wenn Sie beispielsweise eine Auflistung von KDS-Konfigurationseinstellungen erstellen möchten, die standardmäßig das Deaktivieren der Aufzeichnung von Kommunikationsdatensätzen erlauben, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="e8212-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="e8212-162">So geben Sie beim Erstellen einer neuen Auflistung von KDS-Konfigurationseinstellungen mehrere Eigenschaftswerte an</span><span class="sxs-lookup"><span data-stu-id="e8212-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="e8212-p112">Durch die Angabe mehrerer Parameter können Sie mehrere Eigenschaftswerte ändern. Beispielsweise werden mit dem folgenden Befehl die neuen Einstellungen so konfiguriert, dass Kommunikationsdatensätze 30 Tage und Fehlerberichte 90 Tage lang aufbewahrt werden:</span><span class="sxs-lookup"><span data-stu-id="e8212-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="e8212-165">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="e8212-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

