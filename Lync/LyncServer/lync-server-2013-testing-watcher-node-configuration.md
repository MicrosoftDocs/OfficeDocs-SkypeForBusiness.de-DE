---
title: 'Lync Server 2013: Testen der Konfiguration des Watcher-Knotens'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a52b251f238b8d79602e5fe1bf2803902cbae23f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503812"
---
# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="fe141-102">Testen der Konfiguration des Watcher-Knotens in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe141-102">Testing watcher node configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe141-103">_**Letztes Änderungsstand des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="fe141-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe141-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="fe141-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fe141-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="fe141-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe141-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="fe141-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fe141-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fe141-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe141-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="fe141-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fe141-109">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="fe141-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fe141-110">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets <strong>Test-CsWatcherNodeConfiguration</strong> verfügt.</span><span class="sxs-lookup"><span data-stu-id="fe141-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="fe141-111">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="fe141-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fe141-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe141-112">Description</span></span>

<span data-ttu-id="fe141-113">Wenn Sie Microsoft System Center Operations Manager zum Überwachen von lync Server 2013 verwenden, haben Sie die Möglichkeit, "Watcher-Knoten" einzurichten: Computer, die regelmäßig und automatisch synthetische Transaktionen ausführen, um zu überprüfen, ob lync Server erwartungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="fe141-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="fe141-114">Watcher-Knoten werden Pools zugewiesen und mit den **CsWatcherNodeConfiguration** -Cmdlets verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fe141-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="fe141-115">Beachten Sie, dass Sie keine Watcher-Knoten installieren müssen, wenn Sie System Center Operations Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe141-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="fe141-116">Sie können Ihr System weiterhin überwachen, ohne Watcher-Knoten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe141-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="fe141-117">Der einzige Unterschied besteht darin, dass alle synthetischen Transaktionen, die Sie ausführen möchten, manuell aufgerufen werden müssen, anstatt von Operations Manager automatisch aufgerufen zu werden.</span><span class="sxs-lookup"><span data-stu-id="fe141-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="fe141-118">Mit dem Cmdlet **Test-CsWatcherNodeConfiguration** können Sie überprüfen, ob ein Watcher-Knoten ordnungsgemäß konfiguriert wurde und einem gültigen lync Server 2013-Pool zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="fe141-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="fe141-119">Beachten Sie, dass das Cmdlet **Test-CsWatcherNodeConfiguration** auf dem Watcher-Knoten selbst ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="fe141-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="fe141-120">Das Cmdlet kann nicht für Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fe141-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fe141-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="fe141-121">Running the test</span></span>

<span data-ttu-id="fe141-122">Mit dem folgenden Befehl werden die Konfigurationseinstellungen für alle Watcher-Knoten überprüft, die in der Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe141-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fe141-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="fe141-123">Determining success or failure</span></span>

<span data-ttu-id="fe141-124">Die folgende erfolgreiche Beispielausgabe zeigt ein System mit vier Edge-Servern.</span><span class="sxs-lookup"><span data-stu-id="fe141-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="fe141-125">Überprüfen des Ziel Pool ATL-CS-001.litwareinc.com für die Topologie.</span><span class="sxs-lookup"><span data-stu-id="fe141-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="fe141-126">Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com ist in der Topologie vorhanden.</span><span class="sxs-lookup"><span data-stu-id="fe141-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="fe141-127">Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com ist die Registrierungsstellen Rolle installiert.</span><span class="sxs-lookup"><span data-stu-id="fe141-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="fe141-128">Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com wird unterstützt Version.</span><span class="sxs-lookup"><span data-stu-id="fe141-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="fe141-129">Erfolg: Port Nummer für 5061 Ziel Pool ATL-CS-001.litwareinc.com ist richtig.</span><span class="sxs-lookup"><span data-stu-id="fe141-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="fe141-130">Die Überprüfung auf fehlende Pools in der Konfiguration des Watcher-Knotens wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="fe141-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="fe141-131">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="fe141-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="fe141-132">Die Überprüfung auf fehlende Pools in der Konfiguration des Watcher-Knotens ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fe141-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="fe141-133">Die Überprüfung auf Watcher-Knoten Registrierungsschlüssel, die von Watcher-Knoten Installation erstellt wurden, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="fe141-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="fe141-134">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="fe141-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="fe141-135">Die Überprüfung auf die Registrierungsschlüssel des Watcher-Knotens, die von Watcher-Knoten Installation erstellt wurden, ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fe141-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="fe141-136">Der erkannte Authentifizierungstyp wird verhandelt.</span><span class="sxs-lookup"><span data-stu-id="fe141-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="fe141-137">Das vorhanden sein der Anmeldeinformationen des Testbenutzers wurde erfolgreich überprüft SIP: user1@ ATL-CS-001.litwareinc.com im Credential Management Store.</span><span class="sxs-lookup"><span data-stu-id="fe141-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="fe141-138">Das vorhanden sein der Anmeldeinformationen des Testbenutzers wurde erfolgreich überprüft SIP: User2@ ATL-CS-001.litwareinc.com im Credential Management Store.</span><span class="sxs-lookup"><span data-stu-id="fe141-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="fe141-139">Die Überprüfung auf fehlende Pools in der Konfiguration des Watcher-Knotens wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="fe141-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="fe141-140">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="fe141-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="fe141-141">Warnung: Pool ATL-CS-001.litwareinc.com hat eine Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="fe141-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="fe141-142">Rolle installiert, aber es sind keine Testbenutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fe141-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="fe141-143">Die Überprüfung auf fehlende Pools in der Konfiguration des Watcher-Knotens ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fe141-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="fe141-144">Die Überprüfung auf die Registrierungsschlüssel des Watcher-Knotens, die von Watcher-Knoten Installation erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="fe141-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="fe141-145">begann.</span><span class="sxs-lookup"><span data-stu-id="fe141-145">started.</span></span> <span data-ttu-id="fe141-146">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="fe141-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="fe141-147">Test-CsWatcherNodeConfiguration: Integritäts Registrierungsschlüssel kann nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="fe141-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="fe141-148">Software \\ \\ -Microsoft-Echtzeitkommunikation.</span><span class="sxs-lookup"><span data-stu-id="fe141-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="fe141-149">Stellen Sie sicher, dass Watcher Node. msi</span><span class="sxs-lookup"><span data-stu-id="fe141-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="fe141-150">ordnungsgemäß installiert.</span><span class="sxs-lookup"><span data-stu-id="fe141-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fe141-151">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="fe141-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="fe141-152">Im folgenden werden einige häufige Gründe aufgeführt, warum das **Testen von CsWatcherNodeConfiguration** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="fe141-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="fe141-153">Watcher-Knoten ist nicht ordnungsgemäß installiert.</span><span class="sxs-lookup"><span data-stu-id="fe141-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="fe141-154">Es wurden keine Testbenutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="fe141-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe141-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe141-155">See Also</span></span>


[<span data-ttu-id="fe141-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="fe141-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="fe141-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="fe141-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="fe141-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="fe141-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="fe141-159">Gruppe-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="fe141-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

