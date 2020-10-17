---
title: 'Lync Server 2013: Testen der Datenbankkonfiguration'
description: 'Lync Server 2013: Testen der Datenbankkonfiguration.'
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
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560681"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="ec03f-103">Testen der Datenbankkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec03f-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec03f-104">_**Letztes Änderungsstand des Themas:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="ec03f-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec03f-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="ec03f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ec03f-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="ec03f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec03f-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="ec03f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ec03f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ec03f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec03f-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ec03f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ec03f-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein und über Administrator Rechte für den SQL Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="ec03f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="ec03f-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsDatabase</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="ec03f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="ec03f-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="ec03f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ec03f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec03f-113">Description</span></span>

<span data-ttu-id="ec03f-114">Das Cmdlet **Test-CsDatabase** überprüft die Konnektivität mit einer oder mehreren lync Server 2013 Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ec03f-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="ec03f-115">Bei der Ausführung liest das Cmdlet **Test-CsDatabase** die lync Server Topologie, versucht, eine Verbindung mit relevanten Datenbankenherzustellen, und meldet dann den Erfolg oder das Fehlschlagen der einzelnen Versuche zurück.</span><span class="sxs-lookup"><span data-stu-id="ec03f-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="ec03f-116">Wenn eine Verbindung hergestellt werden kann, meldet das Cmdlet auch Informationen wie Datenbankname, SQL Server-Version und den Ort der installierten Spiegeldatenbanken.</span><span class="sxs-lookup"><span data-stu-id="ec03f-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ec03f-117">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="ec03f-117">Running the test</span></span>

<span data-ttu-id="ec03f-118">Der Befehl im ersten Beispiel dient zum Überprüfen der Konfiguration der zentralen Verwaltungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="ec03f-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="ec03f-119">In Beispiel 2 werden alle auf dem Computer ATL-SQL-001.litwareinc.com installierten lync Server Datenbanken überprüft.</span><span class="sxs-lookup"><span data-stu-id="ec03f-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="ec03f-p103">Im dritten Beispiel wird nur die auf dem Computer "atl-sql-001.litwareinc.com" installierte Archivierungsdatenbank überprüft. Beachten Sie, dass der Parameter "SqlInstanceName" verwendet wird, um die SQL Server-Instanz ("Archinst") anzugeben, in der sich die Archivierungsdatenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="ec03f-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="ec03f-122">Mit dem Befehl in Beispiel 4 werden die auf dem lokalen Computer installierten Datenbanken überprüft.</span><span class="sxs-lookup"><span data-stu-id="ec03f-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ec03f-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="ec03f-123">Determining success or failure</span></span>

<span data-ttu-id="ec03f-124">Wenn die Datenbankverbindung ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Succeed-Eigenschaft mit **true**gekennzeichnet ist:</span><span class="sxs-lookup"><span data-stu-id="ec03f-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="ec03f-125">Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec03f-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="ec03f-126">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="ec03f-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="ec03f-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="ec03f-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="ec03f-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="ec03f-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="ec03f-129">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="ec03f-129">DatabaseName : xds</span></span>

<span data-ttu-id="ec03f-130">DataSource</span><span class="sxs-lookup"><span data-stu-id="ec03f-130">DataSource :</span></span>

<span data-ttu-id="ec03f-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="ec03f-131">SQLServerVersion :</span></span>

<span data-ttu-id="ec03f-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="ec03f-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="ec03f-133">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="ec03f-133">InstalledVersion :</span></span>

<span data-ttu-id="ec03f-134">Erfolgreich: true</span><span class="sxs-lookup"><span data-stu-id="ec03f-134">Succeed : True</span></span>

<span data-ttu-id="ec03f-135">Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec03f-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="ec03f-136">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="ec03f-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="ec03f-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="ec03f-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="ec03f-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="ec03f-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="ec03f-139">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="ec03f-139">DatabaseName : lis</span></span>

<span data-ttu-id="ec03f-140">DataSource</span><span class="sxs-lookup"><span data-stu-id="ec03f-140">DataSource :</span></span>

<span data-ttu-id="ec03f-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="ec03f-141">SQLServerVersion :</span></span>

<span data-ttu-id="ec03f-142">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="ec03f-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="ec03f-143">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="ec03f-143">InstalledVersion :</span></span>

<span data-ttu-id="ec03f-144">Erfolgreich: true</span><span class="sxs-lookup"><span data-stu-id="ec03f-144">Succeed : True</span></span>

<span data-ttu-id="ec03f-145">Wenn die Datenbank ordnungsgemäß konfiguriert ist, aber weiterhin verfügbar ist, wird das Feld erfolgreich als **false**angezeigt, und es werden zusätzliche Warnungen und Informationen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="ec03f-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="ec03f-146">Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec03f-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="ec03f-147">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="ec03f-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="ec03f-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="ec03f-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="ec03f-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="ec03f-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="ec03f-150">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="ec03f-150">DatabaseName : xds</span></span>

<span data-ttu-id="ec03f-151">DataSource</span><span class="sxs-lookup"><span data-stu-id="ec03f-151">DataSource :</span></span>

<span data-ttu-id="ec03f-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="ec03f-152">SQLServerVersion :</span></span>

<span data-ttu-id="ec03f-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="ec03f-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="ec03f-154">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="ec03f-154">InstalledVersion :</span></span>

<span data-ttu-id="ec03f-155">Erfolgreich: false</span><span class="sxs-lookup"><span data-stu-id="ec03f-155">Succeed : False</span></span>

<span data-ttu-id="ec03f-156">Sqlserverfqdn "nicht: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ec03f-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ec03f-157">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="ec03f-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="ec03f-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="ec03f-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="ec03f-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="ec03f-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="ec03f-160">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="ec03f-160">DatabaseName : lis</span></span>

<span data-ttu-id="ec03f-161">DataSource</span><span class="sxs-lookup"><span data-stu-id="ec03f-161">DataSource :</span></span>

<span data-ttu-id="ec03f-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="ec03f-162">SQLServerVersion :</span></span>

<span data-ttu-id="ec03f-163">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="ec03f-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="ec03f-164">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="ec03f-164">InstalledVersion :</span></span>

<span data-ttu-id="ec03f-165">Erfolgreich: false</span><span class="sxs-lookup"><span data-stu-id="ec03f-165">Succeed : False</span></span>

<span data-ttu-id="ec03f-166">Warnung: Test-CsDatabase Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ec03f-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="ec03f-167">Konsultieren Sie die Protokolldatei für einen</span><span class="sxs-lookup"><span data-stu-id="ec03f-167">Consult the log file for a</span></span>

<span data-ttu-id="ec03f-168">detaillierte Analyse und sicherstellen, dass alle Fehler (2) und Warnungen (0) adressiert werden</span><span class="sxs-lookup"><span data-stu-id="ec03f-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="ec03f-169">bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ec03f-169">before continuing.</span></span>

<span data-ttu-id="ec03f-170">Warnung: detaillierte Ergebnisse finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="ec03f-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="ec03f-171">"C: \\ Benutzer \\ Testen \\ AppData \\ local \\ Temp \\ 2 \\ Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="ec03f-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="ec03f-172">04d593cce8e6.html ".</span><span class="sxs-lookup"><span data-stu-id="ec03f-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ec03f-173">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="ec03f-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="ec03f-174">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsDatabase** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="ec03f-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="ec03f-175">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="ec03f-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ec03f-176">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="ec03f-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ec03f-177">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="ec03f-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ec03f-178">Dieser Befehl schlägt fehl, wenn die Datenbank falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="ec03f-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ec03f-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec03f-179">See Also</span></span>


[<span data-ttu-id="ec03f-180">Get-csdatabasemirrorstate "</span><span class="sxs-lookup"><span data-stu-id="ec03f-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="ec03f-181">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="ec03f-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="ec03f-182">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="ec03f-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

