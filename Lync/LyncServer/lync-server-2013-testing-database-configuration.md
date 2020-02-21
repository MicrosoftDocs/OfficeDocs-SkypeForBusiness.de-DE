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
ms.openlocfilehash: 69dea9e2b75125740729f658e1c370838bb5d8bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="2bc5b-102">Testen der Datenbankkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2bc5b-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bc5b-103">_**Letztes Änderungsstand des Themas:** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="2bc5b-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bc5b-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="2bc5b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2bc5b-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="2bc5b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bc5b-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="2bc5b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2bc5b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2bc5b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bc5b-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2bc5b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2bc5b-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein und über Administrator Rechte für den SQL Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="2bc5b-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsDatabase</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="2bc5b-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="2bc5b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2bc5b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2bc5b-112">Description</span></span>

<span data-ttu-id="2bc5b-113">Das Cmdlet **Test-CsDatabase** überprüft die Konnektivität mit einer oder mehreren lync Server 2013 Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="2bc5b-114">Bei der Ausführung liest das Cmdlet **Test-CsDatabase** die lync Server Topologie, versucht, eine Verbindung mit relevanten Datenbankenherzustellen, und meldet dann den Erfolg oder das Fehlschlagen der einzelnen Versuche zurück.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="2bc5b-115">Wenn eine Verbindung hergestellt werden kann, meldet das Cmdlet auch Informationen wie Datenbankname, SQL Server-Version und den Ort der installierten Spiegeldatenbanken.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2bc5b-116">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="2bc5b-116">Running the test</span></span>

<span data-ttu-id="2bc5b-117">Der Befehl im ersten Beispiel dient zum Überprüfen der Konfiguration der zentralen Verwaltungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="2bc5b-118">In Beispiel 2 werden alle auf dem Computer ATL-SQL-001.litwareinc.com installierten lync Server Datenbanken überprüft.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="2bc5b-p103">Im dritten Beispiel wird nur die auf dem Computer "atl-sql-001.litwareinc.com" installierte Archivierungsdatenbank überprüft. Beachten Sie, dass der Parameter "SqlInstanceName" verwendet wird, um die SQL Server-Instanz ("Archinst") anzugeben, in der sich die Archivierungsdatenbank befindet.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="2bc5b-121">Mit dem Befehl in Beispiel 4 werden die auf dem lokalen Computer installierten Datenbanken überprüft.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2bc5b-122">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="2bc5b-122">Determining success or failure</span></span>

<span data-ttu-id="2bc5b-123">Wenn die Datenbankverbindung ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Succeed-Eigenschaft mit **true**gekennzeichnet ist:</span><span class="sxs-lookup"><span data-stu-id="2bc5b-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="2bc5b-124">Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2bc5b-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="2bc5b-125">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="2bc5b-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="2bc5b-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="2bc5b-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="2bc5b-128">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="2bc5b-128">DatabaseName : xds</span></span>

<span data-ttu-id="2bc5b-129">DataSource</span><span class="sxs-lookup"><span data-stu-id="2bc5b-129">DataSource :</span></span>

<span data-ttu-id="2bc5b-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-130">SQLServerVersion :</span></span>

<span data-ttu-id="2bc5b-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="2bc5b-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="2bc5b-132">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="2bc5b-132">InstalledVersion :</span></span>

<span data-ttu-id="2bc5b-133">Erfolgreich: true</span><span class="sxs-lookup"><span data-stu-id="2bc5b-133">Succeed : True</span></span>

<span data-ttu-id="2bc5b-134">Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2bc5b-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="2bc5b-135">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="2bc5b-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="2bc5b-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="2bc5b-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="2bc5b-138">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="2bc5b-138">DatabaseName : lis</span></span>

<span data-ttu-id="2bc5b-139">DataSource</span><span class="sxs-lookup"><span data-stu-id="2bc5b-139">DataSource :</span></span>

<span data-ttu-id="2bc5b-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-140">SQLServerVersion :</span></span>

<span data-ttu-id="2bc5b-141">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="2bc5b-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="2bc5b-142">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="2bc5b-142">InstalledVersion :</span></span>

<span data-ttu-id="2bc5b-143">Erfolgreich: true</span><span class="sxs-lookup"><span data-stu-id="2bc5b-143">Succeed : True</span></span>

<span data-ttu-id="2bc5b-144">Wenn die Datenbank ordnungsgemäß konfiguriert ist, aber weiterhin verfügbar ist, wird das Feld erfolgreich als **false**angezeigt, und es werden zusätzliche Warnungen und Informationen bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="2bc5b-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="2bc5b-145">Sqlserverfqdn "nicht: ATL-SQL-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2bc5b-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="2bc5b-146">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="2bc5b-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="2bc5b-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="2bc5b-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="2bc5b-149">DatabaseName: XDS</span><span class="sxs-lookup"><span data-stu-id="2bc5b-149">DatabaseName : xds</span></span>

<span data-ttu-id="2bc5b-150">DataSource</span><span class="sxs-lookup"><span data-stu-id="2bc5b-150">DataSource :</span></span>

<span data-ttu-id="2bc5b-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-151">SQLServerVersion :</span></span>

<span data-ttu-id="2bc5b-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="2bc5b-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="2bc5b-153">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="2bc5b-153">InstalledVersion :</span></span>

<span data-ttu-id="2bc5b-154">Erfolgreich: false</span><span class="sxs-lookup"><span data-stu-id="2bc5b-154">Succeed : False</span></span>

<span data-ttu-id="2bc5b-155">Sqlserverfqdn "nicht: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2bc5b-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2bc5b-156">SqlInstanceName: RTC</span><span class="sxs-lookup"><span data-stu-id="2bc5b-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="2bc5b-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="2bc5b-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="2bc5b-159">DatabaseName: Lis</span><span class="sxs-lookup"><span data-stu-id="2bc5b-159">DatabaseName : lis</span></span>

<span data-ttu-id="2bc5b-160">DataSource</span><span class="sxs-lookup"><span data-stu-id="2bc5b-160">DataSource :</span></span>

<span data-ttu-id="2bc5b-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="2bc5b-161">SQLServerVersion :</span></span>

<span data-ttu-id="2bc5b-162">ExpectedVersion: 3.1.1</span><span class="sxs-lookup"><span data-stu-id="2bc5b-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="2bc5b-163">InstalledVersion</span><span class="sxs-lookup"><span data-stu-id="2bc5b-163">InstalledVersion :</span></span>

<span data-ttu-id="2bc5b-164">Erfolgreich: false</span><span class="sxs-lookup"><span data-stu-id="2bc5b-164">Succeed : False</span></span>

<span data-ttu-id="2bc5b-165">Warnung: bei Test-CsDatabase sind Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="2bc5b-166">Konsultieren Sie die Protokolldatei für einen</span><span class="sxs-lookup"><span data-stu-id="2bc5b-166">Consult the log file for a</span></span>

<span data-ttu-id="2bc5b-167">detaillierte Analyse und sicherstellen, dass alle Fehler (2) und Warnungen (0) adressiert werden</span><span class="sxs-lookup"><span data-stu-id="2bc5b-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="2bc5b-168">bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-168">before continuing.</span></span>

<span data-ttu-id="2bc5b-169">Warnung: detaillierte Ergebnisse finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="2bc5b-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="2bc5b-170">"C:\\Benutzer\\testen\\APPDATA\\local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="2bc5b-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="2bc5b-171">04d593cce8e6. html ".</span><span class="sxs-lookup"><span data-stu-id="2bc5b-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2bc5b-172">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="2bc5b-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="2bc5b-173">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsDatabase** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="2bc5b-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="2bc5b-174">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="2bc5b-175">Wenn die optionalen Parameter verwendet werden, müssen Sie ordnungsgemäß konfiguriert sein, oder der Test kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="2bc5b-176">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="2bc5b-177">Dieser Befehl schlägt fehl, wenn die Datenbank falsch konfiguriert oder noch nicht bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2bc5b-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2bc5b-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bc5b-178">See Also</span></span>


[<span data-ttu-id="2bc5b-179">Get-csdatabasemirrorstate "</span><span class="sxs-lookup"><span data-stu-id="2bc5b-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="2bc5b-180">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="2bc5b-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="2bc5b-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="2bc5b-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

