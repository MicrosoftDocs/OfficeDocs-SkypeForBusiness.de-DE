---
title: 'Lync Server 2013: Testen der LIS-Server Konfiguration'
description: 'Lync Server 2013: Testen der LIS-Server Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing LIS server configuration
ms:assetid: 6b06e7ab-522f-41a2-878b-e89cd4e3c6da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690129(v=OCS.15)
ms:contentKeyID: 63969614
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba4d16d2ce48e3e5bb89e863f02902d05ce77bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560611"
---
# <a name="testing-lis-server-configuration-in-lync-server-2013"></a><span data-ttu-id="67040-103">Testen der LIS-Serverkonfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67040-103">Testing LIS server configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67040-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="67040-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="67040-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="67040-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="67040-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="67040-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="67040-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="67040-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="67040-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="67040-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="67040-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="67040-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="67040-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="67040-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="67040-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsLisConfiguration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="67040-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLisConfiguration cmdlet.</span></span> <span data-ttu-id="67040-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="67040-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="67040-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67040-113">Description</span></span>

<span data-ttu-id="67040-114">Das Test-CsLisConfiguration-Cmdlet überprüft, ob Sie den LIS-Webdienst kontaktieren können.</span><span class="sxs-lookup"><span data-stu-id="67040-114">The Test-CsLisConfiguration cmdlet verifies your ability to contact the LIS web service.</span></span> <span data-ttu-id="67040-115">Wenn der Webdienst kontaktiert werden kann, wird der Test als Erfolg betrachtet, unabhängig davon, ob bestimmte Speicherorte gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="67040-115">If the web service can be contacted, then the test will be considered a success, regardless of whether any specific locations can be found.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="67040-116">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="67040-116">Running the test</span></span>

<span data-ttu-id="67040-117">Das Test-CsLisConfguration-Cmdlet kann entweder mit einem vorkonfigurierten Test Konto ausgeführt werden (siehe Einrichten von Testkonten für das Ausführen von lync Server Tests) oder nach dem Konto eines beliebigen Benutzers, der für lync Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="67040-117">The Test-CsLisConfguration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="67040-118">Um diese Prüfung mit einem Test Konto auszuführen, müssen Sie lediglich den FQDN des lync Server Pools angeben, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="67040-118">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="67040-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="67040-119">For example:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="67040-120">Um diese Prüfung mit einem tatsächlichen Benutzerkonto auszuführen, müssen Sie zuerst ein Windows PowerShell Credentials-Objekt erstellen, das den Kontonamen und das Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="67040-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="67040-121">Anschließend müssen Sie das Credentials-Objekt und die dem Konto zugewiesene SIP-Adresse angeben, wenn Sie Test-CsLisConfiguration aufrufen:</span><span class="sxs-lookup"><span data-stu-id="67040-121">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLisConfiguration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="67040-122">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="67040-122">For more information, see the Help documentation for the [Test-CsLisConfiguration](https://docs.microsoft.com/powershell/module/skype/Test-CsLisConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="67040-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="67040-123">Determining success or failure</span></span>

<span data-ttu-id="67040-124">Wenn der LIS ordnungsgemäß konfiguriert ist, erhalten Sie eine ähnliche Ausgabe, wobei die Result-Eigenschaft als **Success** markiert ist:</span><span class="sxs-lookup"><span data-stu-id="67040-124">If the LIS is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="67040-125">TargetUri https://atl-cs-001.litwareinc.com:443/locationinformation/</span><span class="sxs-lookup"><span data-stu-id="67040-125">TargetUri : https://atl-cs-001.litwareinc.com:443/locationinformation/</span></span>

<span data-ttu-id="67040-126">liservice. svc</span><span class="sxs-lookup"><span data-stu-id="67040-126">liservice.svc</span></span>

<span data-ttu-id="67040-127">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67040-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67040-128">Ergebnis: Success</span><span class="sxs-lookup"><span data-stu-id="67040-128">Result : Success</span></span>

<span data-ttu-id="67040-129">Wartezeit: 00:00:06.1616913</span><span class="sxs-lookup"><span data-stu-id="67040-129">Latency : 00:00:06.1616913</span></span>

<span data-ttu-id="67040-130">Fehler</span><span class="sxs-lookup"><span data-stu-id="67040-130">Error :</span></span>

<span data-ttu-id="67040-131">Diagnose</span><span class="sxs-lookup"><span data-stu-id="67040-131">Diagnosis :</span></span>

<span data-ttu-id="67040-132">Wenn sich der angegebene Benutzer nicht anmelden oder abmelden kann, wird das Ergebnis als Fehler angezeigt, und in den Eigenschaften Error und Diagnostic werden zusätzliche Informationen aufgezeichnet:</span><span class="sxs-lookup"><span data-stu-id="67040-132">If the specified user can't log on or log off, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="67040-133">TargetUri</span><span class="sxs-lookup"><span data-stu-id="67040-133">TargetUri :</span></span>

<span data-ttu-id="67040-134">TargetFqdn: ATL-CS-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="67040-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="67040-135">Ergebnis: Fehler</span><span class="sxs-lookup"><span data-stu-id="67040-135">Result : Failure</span></span>

<span data-ttu-id="67040-136">Wartezeit: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="67040-136">Latency : 00:00:00</span></span>

<span data-ttu-id="67040-137">Fehler: 11004, der angeforderte Name ist gültig, aber keine Daten der angeforderten</span><span class="sxs-lookup"><span data-stu-id="67040-137">Error : 11004, The requested name is valid but no data of the requested</span></span>

<span data-ttu-id="67040-138">der Typ wurde gefunden.</span><span class="sxs-lookup"><span data-stu-id="67040-138">type was found</span></span>

<span data-ttu-id="67040-139">Diagnose</span><span class="sxs-lookup"><span data-stu-id="67040-139">Diagnosis :</span></span>

<span data-ttu-id="67040-140">Test-CsLisConfiguration: kein übereinstimmender Cluster in der Topologie gefunden.</span><span class="sxs-lookup"><span data-stu-id="67040-140">Test-CsLisConfiguration : No matching cluster found in topology.</span></span>

<span data-ttu-id="67040-141">Die vorherige Ausgabe enthält beispielsweise den Hinweis "kein übereinstimmender Cluster in der Topologie gefunden".</span><span class="sxs-lookup"><span data-stu-id="67040-141">For example, the previous output includes the note “No matching cluster found in topology.”</span></span> <span data-ttu-id="67040-142">Dies deutet in der Regel auf ein Problem mit der Edgeserver hin: der LIS, der die Edgeserver verwendet, um eine Verbindung mit dem Dienstanbieter herzustellen und Adressen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="67040-142">That typically indicates a problem with the Edge Server: the LIS using the Edge Server to connect to the service provider and validate addresses.</span></span>

<span data-ttu-id="67040-143">Wenn Test-CsLisConfiguration fehlschlägt, möchten Sie den Test möglicherweise erneut ausführen, und zwar mit dem Verbose-Parameter:</span><span class="sxs-lookup"><span data-stu-id="67040-143">If Test-CsLisConfiguration fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLisConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="67040-144">Wenn der Verbose-Parameter enthalten ist, gibt Test-CsLisConfiguration eine Schritt-für-Schritt-Konto für jede Aktion zurück, die versucht wurde, als die Möglichkeit des angegebenen Benutzers geprüft wurde, sich bei lync Server anzumelden.</span><span class="sxs-lookup"><span data-stu-id="67040-144">When the Verbose parameter is included, Test-CsLisConfiguration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="67040-145">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="67040-145">For example:</span></span>

<span data-ttu-id="67040-146">Informationsdienst für den Anruf Standort.</span><span class="sxs-lookup"><span data-stu-id="67040-146">Calling Location Information Service.</span></span>

<span data-ttu-id="67040-147">Dienstpfad = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span><span class="sxs-lookup"><span data-stu-id="67040-147">Service Path = https://atl-cs-001.litwareinc.com:443/locationinformation/liservice.svc</span></span>

<span data-ttu-id="67040-148">Subnet =</span><span class="sxs-lookup"><span data-stu-id="67040-148">Subnet =</span></span>

<span data-ttu-id="67040-149">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="67040-149">BssId = 5</span></span>

<span data-ttu-id="67040-150">Fahrgestell-Nr =</span><span class="sxs-lookup"><span data-stu-id="67040-150">ChassisId =</span></span>

<span data-ttu-id="67040-151">Port-Nr =</span><span class="sxs-lookup"><span data-stu-id="67040-151">PortId =</span></span>

<span data-ttu-id="67040-152">PortIdSubType = nicht definierter Typ</span><span class="sxs-lookup"><span data-stu-id="67040-152">PortIdSubType = Undefined Type</span></span>

<span data-ttu-id="67040-153">Mac</span><span class="sxs-lookup"><span data-stu-id="67040-153">Mac</span></span>

<span data-ttu-id="67040-154">Eine Ausnahme "Standortinformationen-Webdienstanforderung ist mit dem Antwortcode Item400 fehlgeschlagen."</span><span class="sxs-lookup"><span data-stu-id="67040-154">An exception 'Location Information Web Service request has failed with a response code Item400.'</span></span> <span data-ttu-id="67040-155">während der Ausführung des Workflows "Microsoft. RTC. SyntheticTrsnactions. Workflows. STLisConfigurationWorkflow" aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="67040-155">occurred during Workflow Microsoft.Rtc.SyntheticTrsnactions.Workflows.STLisConfigurationWorkflow execution.</span></span>

<span data-ttu-id="67040-156">Wenn Sie die vorherige Ausgabe genau untersuchen, sehen Sie, dass das Cmdlet nach dem Versuch, den standortinformationsdienst aufzurufen, fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="67040-156">If you examine the previous output closely, you’ll see that the cmdlet failed after it tried to call the Location Information Service.</span></span> <span data-ttu-id="67040-157">Einer der Parameter, die in diesem Aufruf verwendet wurden, war folgende:</span><span class="sxs-lookup"><span data-stu-id="67040-157">One of the parameters that were used in that call was this:</span></span>

<span data-ttu-id="67040-158">BssId = 5</span><span class="sxs-lookup"><span data-stu-id="67040-158">BssId = 5</span></span>

<span data-ttu-id="67040-159">Dies ist kein gültiger Wert für die grundlegende Dienst-ID (Service Sets Identifier, BssID).</span><span class="sxs-lookup"><span data-stu-id="67040-159">That’s not a valid value for the Basic Service Set Identifier (BssID).</span></span> <span data-ttu-id="67040-160">Stattdessen sollte ein BssID wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="67040-160">Instead, a BssID should resemble this:</span></span>

<span data-ttu-id="67040-161">12-34-56-78-90-ab</span><span class="sxs-lookup"><span data-stu-id="67040-161">12-34-56-78-90-ab</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="67040-162">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="67040-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="67040-163">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsLisConfiguration Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="67040-163">Here are some common reasons why Test-CsLisConfiguration might fail:</span></span>

  - <span data-ttu-id="67040-164">Ein falscher Parameterwert wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="67040-164">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="67040-165">Wie im vorherigen Beispiel gezeigt, müssen die optionalen Parameter ordnungsgemäß konfiguriert sein, oder der Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="67040-165">As shown in the previous example, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="67040-166">Führen Sie den Befehl ohne die optionalen Parameter erneut aus, und überprüfen Sie, ob dies erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="67040-166">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

