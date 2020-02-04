---
title: 'Lync Server 2013: Testen der Datenbankkonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="8fb7d-102">Testen der Datenbankkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8fb7d-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fb7d-103">_**Letztes Änderungsdatum des Themas:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="8fb7d-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fb7d-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="8fb7d-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8fb7d-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="8fb7d-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fb7d-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="8fb7d-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8fb7d-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fb7d-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fb7d-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8fb7d-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8fb7d-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein und über Administrator Rechte für SQL Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="8fb7d-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsDatabase-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="8fb7d-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="8fb7d-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8fb7d-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8fb7d-112">Description</span></span>

<span data-ttu-id="8fb7d-113">Das Cmdlet **Test-CsDatabase** überprüft die Konnektivität mit einer oder mehreren lync Server 2013-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="8fb7d-114">Beim Ausführen liest das Cmdlet **Test-CsDatabase** die lync Server-Topologie, versucht, eine Verbindung mit relevanten Datenbankenherzustellen, und gibt dann den Erfolg oder Misserfolg jedes einzelnen Versuchs zurück.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="8fb7d-115">Wenn eine Verbindung hergestellt werden kann, meldet das Cmdlet auch Informationen wie den Datenbanknamen, die SQL Server-Versionsinformationen und den Speicherort aller installierten Spiegeldatenbanken zurück.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8fb7d-116">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="8fb7d-116">Running the test</span></span>

<span data-ttu-id="8fb7d-117">Der in Beispiel 1 gezeigte Befehl überprüft die Konfiguration der zentralen Verwaltungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="8fb7d-118">Beispiel 2 überprüft alle lync Server-Datenbanken, die auf dem Computer ATL-SQL-001.litwareinc.com installiert sind.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="8fb7d-119">In Beispiel 3 wird die Überprüfung nur für die auf dem Computer ATL-SQL-001.litwareinc.com installierte Archivierungsdatenbank durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="8fb7d-120">Beachten Sie, dass der SqlInstanceName-Parameter enthalten ist, um die SQL Server-Instanz (Archinst) anzugeben, in der sich die Archivierungsdatenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="8fb7d-121">Der in Beispiel 4 angezeigte Befehl überprüft die auf dem lokalen Computer installierten Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8fb7d-122">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="8fb7d-122">Determining success or failure</span></span>

<span data-ttu-id="8fb7d-123">Wenn die Datenbankverbindung ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Eigenschaft erfolgreich als **wahr**markiert ist:</span><span class="sxs-lookup"><span data-stu-id="8fb7d-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="8fb7d-124">SqlServerFqdn: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8fb7d-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="8fb7d-125">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="8fb7d-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="8fb7d-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="8fb7d-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="8fb7d-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="8fb7d-128">DatabaseName : xds</span></span>

<span data-ttu-id="8fb7d-129">DataSource</span><span class="sxs-lookup"><span data-stu-id="8fb7d-129">DataSource :</span></span>

<span data-ttu-id="8fb7d-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-130">SQLServerVersion :</span></span>

<span data-ttu-id="8fb7d-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="8fb7d-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="8fb7d-132">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="8fb7d-132">InstalledVersion :</span></span>

<span data-ttu-id="8fb7d-133">Erfolgreich: true</span><span class="sxs-lookup"><span data-stu-id="8fb7d-133">Succeed : True</span></span>

<span data-ttu-id="8fb7d-134">SqlServerFqdn: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8fb7d-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="8fb7d-135">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="8fb7d-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="8fb7d-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="8fb7d-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="8fb7d-138">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="8fb7d-138">DatabaseName : lis</span></span>

<span data-ttu-id="8fb7d-139">DataSource</span><span class="sxs-lookup"><span data-stu-id="8fb7d-139">DataSource :</span></span>

<span data-ttu-id="8fb7d-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-140">SQLServerVersion :</span></span>

<span data-ttu-id="8fb7d-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="8fb7d-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="8fb7d-142">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="8fb7d-142">InstalledVersion :</span></span>

<span data-ttu-id="8fb7d-143">Erfolgreich: true</span><span class="sxs-lookup"><span data-stu-id="8fb7d-143">Succeed : True</span></span>

<span data-ttu-id="8fb7d-144">Wenn die Datenbank richtig konfiguriert ist, aber weiterhin verfügbar ist, wird das Feld erfolgreich als **falsch**angezeigt, und es werden weitere Warnungen und Informationen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="8fb7d-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="8fb7d-145">SqlServerFqdn: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8fb7d-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="8fb7d-146">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="8fb7d-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="8fb7d-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="8fb7d-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="8fb7d-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="8fb7d-149">DatabaseName : xds</span></span>

<span data-ttu-id="8fb7d-150">DataSource</span><span class="sxs-lookup"><span data-stu-id="8fb7d-150">DataSource :</span></span>

<span data-ttu-id="8fb7d-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-151">SQLServerVersion :</span></span>

<span data-ttu-id="8fb7d-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="8fb7d-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="8fb7d-153">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="8fb7d-153">InstalledVersion :</span></span>

<span data-ttu-id="8fb7d-154">Erfolgreich: falsch</span><span class="sxs-lookup"><span data-stu-id="8fb7d-154">Succeed : False</span></span>

<span data-ttu-id="8fb7d-155">SqlServerFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8fb7d-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8fb7d-156">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="8fb7d-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="8fb7d-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="8fb7d-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="8fb7d-159">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="8fb7d-159">DatabaseName : lis</span></span>

<span data-ttu-id="8fb7d-160">DataSource</span><span class="sxs-lookup"><span data-stu-id="8fb7d-160">DataSource :</span></span>

<span data-ttu-id="8fb7d-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="8fb7d-161">SQLServerVersion :</span></span>

<span data-ttu-id="8fb7d-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="8fb7d-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="8fb7d-163">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="8fb7d-163">InstalledVersion :</span></span>

<span data-ttu-id="8fb7d-164">Erfolgreich: falsch</span><span class="sxs-lookup"><span data-stu-id="8fb7d-164">Succeed : False</span></span>

<span data-ttu-id="8fb7d-165">Warnung: bei Test-CsDatabase sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="8fb7d-166">Konsultieren Sie die Protokolldatei für eine</span><span class="sxs-lookup"><span data-stu-id="8fb7d-166">Consult the log file for a</span></span>

<span data-ttu-id="8fb7d-167">detaillierte Analyse und um sicherzustellen, dass alle Fehler (2) und Warnungen (0) behandelt werden</span><span class="sxs-lookup"><span data-stu-id="8fb7d-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="8fb7d-168">bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-168">before continuing.</span></span>

<span data-ttu-id="8fb7d-169">Warnung: detaillierte Ergebnisse finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="8fb7d-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="8fb7d-170">"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="8fb7d-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="8fb7d-171">04d593cce8e6. html ".</span><span class="sxs-lookup"><span data-stu-id="8fb7d-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8fb7d-172">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="8fb7d-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="8fb7d-173">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsDatabase** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="8fb7d-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="8fb7d-174">Es wurde ein falscher Parameterwert angegeben.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="8fb7d-175">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="8fb7d-176">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="8fb7d-177">Dieser Befehl schlägt fehl, wenn die Datenbank falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8fb7d-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8fb7d-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8fb7d-178">See Also</span></span>


[<span data-ttu-id="8fb7d-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="8fb7d-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="8fb7d-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="8fb7d-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="8fb7d-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="8fb7d-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

