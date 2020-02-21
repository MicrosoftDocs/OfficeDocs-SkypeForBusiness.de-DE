---
title: Konfigurieren der Aufzeichnung von Gesprächs Details und der Einstellungen für die Qualität der Benutzerfreundlichkeit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f2c57f56f1f82b94b20feb7aa801ca26f0ae022
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="67410-102">Konfigurieren der Einstellungen für die Aufzeichnung von Gesprächsdaten und der erfahrungsqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67410-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67410-103">_**Letztes Änderungsstand des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="67410-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="67410-104">Nachdem Sie einem Überwachungsspeicher eine Front-End-Pool zugeordnet haben, den Überwachungsspeicher eingerichtet und dann SQL Server Reporting Services-und Monitoring-Berichte installiert und konfiguriert haben, können Sie die Aufzeichnung von Kommunikationsdatensätzen (KDS) und die Quality of Experience (QoE) verwalten. Überwachung mithilfe lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="67410-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="67410-105">Mit lync Server-Verwaltungsshell-Cmdlets können Sie die KDS-und/oder QoE-Überwachung für eine bestimmte Website oder für die gesamte lync Server-Bereitstellung aktivieren und deaktivieren. Dies kann mit einem einfachen Befehl erfolgen:</span><span class="sxs-lookup"><span data-stu-id="67410-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="67410-106">Wenn Sie Microsoft lync Server 2013 installieren, installieren Sie auch eine vordefinierte Sammlung globaler Konfigurationseinstellungen für KDS und QoE.</span><span class="sxs-lookup"><span data-stu-id="67410-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="67410-107">In der folgenden Tabelle sind Standardwerte für einige gängige Einstellungen für die Aufzeichnung von Kommunikationsdatensätzen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="67410-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67410-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="67410-108">Property</span></span></th>
<th><span data-ttu-id="67410-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67410-109">Description</span></span></th>
<th><span data-ttu-id="67410-110">Standardwert</span><span class="sxs-lookup"><span data-stu-id="67410-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67410-111">"Enablecdr"</span><span class="sxs-lookup"><span data-stu-id="67410-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="67410-p103">Gibt an, ob KDS aktiviert ist. Bei "True" werden alle KDS-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="67410-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="67410-114">Wahr</span><span class="sxs-lookup"><span data-stu-id="67410-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67410-115">"Enablepurging"</span><span class="sxs-lookup"><span data-stu-id="67410-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="67410-p104">Gibt an, ob KDS-Datensätze regelmäßig aus der Datenbank gelöscht werden. Bei Festlegung auf "True" werden Einträge nach dem Zeitraum gelöscht, der in den Eigenschaften "KeepCallDetailForDays" (KDS-Datensätze) und "KeepErrorReportForDays" (KDS-Fehler) angegeben ist. Bei Festlegung des Parameters auf "False" werden KDS-Einträge nie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="67410-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="67410-119">Wahr</span><span class="sxs-lookup"><span data-stu-id="67410-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67410-120">"Keepcalldetailfordays"</span><span class="sxs-lookup"><span data-stu-id="67410-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="67410-p105">Gibt die Anzahl von Tagen an, die KDS-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="67410-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="67410-123">"KeepCallDetailForDays" kann auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (ungefähr 7 Jahre) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="67410-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="67410-124">60 Tage</span><span class="sxs-lookup"><span data-stu-id="67410-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67410-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="67410-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="67410-126">Gibt die Anzahl der Tage an, an denen KDS-Fehlerberichte aufbewahrt werden; Berichte, die älter als die angegebene Anzahl von Tagen sind, werden automatisch gelöscht.</span><span class="sxs-lookup"><span data-stu-id="67410-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="67410-127">CdR-Fehlerberichte sind Diagnoseberichte, die von Clientanwendungen wie Microsoft lync 2013 hochgeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="67410-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="67410-128">Sie können diese Eigenschaft auf einen beliebigen ganzzahligen Wert zwischen 1 und 2562 Tage (etwa 7 Jahre) festlegen.</span><span class="sxs-lookup"><span data-stu-id="67410-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="67410-129">60 Tage</span><span class="sxs-lookup"><span data-stu-id="67410-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67410-130">Entsprechend werden in dieser Tabelle Standardwerte für ausgewählte QoE-Einstellungen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="67410-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="67410-131">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="67410-131">Property</span></span></th>
<th><span data-ttu-id="67410-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67410-132">Description</span></span></th>
<th><span data-ttu-id="67410-133">Standardwert</span><span class="sxs-lookup"><span data-stu-id="67410-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67410-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="67410-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="67410-p107">Gibt an, ob die QoE-Überwachung aktiviert ist. Bei Festlegung auf "True" werden alle QoE-Datensätze gesammelt und in die Überwachungsdatenbank geschrieben.</span><span class="sxs-lookup"><span data-stu-id="67410-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="67410-137">Wahr</span><span class="sxs-lookup"><span data-stu-id="67410-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67410-138">"Enablepurging"</span><span class="sxs-lookup"><span data-stu-id="67410-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="67410-p108">Gibt an, ob QoE-Datensätze regelmäßig aus der Datenbank gelöscht werden oder nicht. Wenn dieser Parameter auf "True" festgelegt ist, werden die Einträge nach der über die Eigenschaft "KeepQoEDataForDays"    angegebenen Zeitdauer gelöscht. Bei Festlegung des Parameters auf "False" werden QoE-Datensätze nie gelöscht.</span><span class="sxs-lookup"><span data-stu-id="67410-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="67410-142">Wahr</span><span class="sxs-lookup"><span data-stu-id="67410-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67410-143">"Keepqoedatafordays"</span><span class="sxs-lookup"><span data-stu-id="67410-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="67410-p109">Gibt die Anzahl von Tagen an, die QoE-Datensätze in der Datenbank gespeichert werden. Einträge, die älter sind als angegeben, werden automatisch gelöscht. Dies erfolgt jedoch nur, wenn der Löschvorgang aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="67410-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="67410-146">"KeepCallDetailForDays" kann auf einen beliebigen Ganzzahlwert zwischen einschließlich 1 und 2562 Tage gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="67410-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="67410-147">60 Tage</span><span class="sxs-lookup"><span data-stu-id="67410-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="67410-p110">Wenn Sie diese globalen Einstellungen ändern müssen, können Sie dazu die Cmdlets "Set-CsCdrConfiguration" und "Set-CsQoEConfiguration" verwenden. Beispielsweise deaktiviert dieser Befehl (ausgeführt in der Lync Server-Verwaltungsshell) die KDS-Überwachung auf globaler Ebene; dazu wird die Eigenschaft "EnableCDR" auf "False" ($False) festgelegt:</span><span class="sxs-lookup"><span data-stu-id="67410-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="67410-150">Durch das Deaktivieren der Überwachung wird weder die Zuordnung des Überwachungsspeichers zum Front-End-Pool aufgehoben, noch wird die Back-End-Überwachungsdatenbank deinstalliert oder anderweitig geändert.</span><span class="sxs-lookup"><span data-stu-id="67410-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="67410-151">Wenn Sie lync Server-Verwaltungsshell verwenden, um die KDS-oder QoE-Überwachung zu deaktivieren, müssen Sie tatsächlich vorübergehend lync Server aus dem sammeln und Archivieren von Überwachungsdaten beenden.</span><span class="sxs-lookup"><span data-stu-id="67410-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="67410-152">Wenn Sie in diesem Fall das Sammeln und Archivieren von KDS-Daten fortsetzen möchten, müssen Sie nur die Eigenschaft "EnableCDR" wieder auf "True" ($True) festlegen:</span><span class="sxs-lookup"><span data-stu-id="67410-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="67410-153">Entsprechend deaktiviert dieser Befehl den Löschvorgang für QoE-Datensätze auf globaler Ebene:</span><span class="sxs-lookup"><span data-stu-id="67410-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="67410-p112">Neben den globalen Einstellungen können KDS- und QoE-Konfigurationeneinstellungen auch auf Standortebene zugewiesen werden. Dadurch wird die Verwaltung bei der Überwachung flexibler gestaltet; ein Administrator kann beispielsweise die KDS-Überwachung für den Standort Redmond aktivieren, für den Standort Dublin jedoch deaktivieren. Verwenden Sie einen Befehl wie den folgenden, um neue KDS-Konfigurationseinstellungen auf Standortebene zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="67410-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="67410-p113">Beachten Sie, dass Einstellungen auf Standortebene Vorrang vor globalen Einstellungen haben. Angenommen, die KDS-Überwachung ist auf globaler Ebene aktiviert, auf Standortebene (für den Standort Redmond) jedoch deaktiviert. Das bedeutet, dass für Benutzer am Standort Redmond keine Kommunikationsdatensätze aufgezeichnet werden. Für Benutzer an anderen Standorten (die von den globalen Einstellungen statt den Einstellungen für den Standort Redmond verwaltet werden), werden jedoch Kommunikationsdatensätze archiviert.</span><span class="sxs-lookup"><span data-stu-id="67410-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="67410-161">Neue QoE-Konfigurationseinstellungen auf Standortebene können mit einem Befehl wie dem folgenden erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="67410-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="67410-162">Weitere Informationen erhalten Sie, indem Sie die folgenden Befehle in der lync Server-Verwaltungsshell eingeben:</span><span class="sxs-lookup"><span data-stu-id="67410-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

