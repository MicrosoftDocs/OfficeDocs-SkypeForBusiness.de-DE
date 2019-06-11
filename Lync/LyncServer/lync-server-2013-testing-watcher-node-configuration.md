---
title: 'Lync Server 2013: Testen der Monitor Knoten Konfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d2c79de4f86e490244ef63948c263d8f387fc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a><span data-ttu-id="cb22e-102">Testen der Monitor Knoten Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb22e-102">Testing watcher node configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb22e-103">_**Letztes Änderungsdatum des Themas:** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="cb22e-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb22e-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="cb22e-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="cb22e-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="cb22e-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb22e-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="cb22e-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="cb22e-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb22e-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb22e-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cb22e-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="cb22e-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="cb22e-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="cb22e-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des <strong>Test-CsWatcherNodeConfiguration-</strong> Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="cb22e-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsWatcherNodeConfiguration</strong> cmdlet.</span></span> <span data-ttu-id="cb22e-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="cb22e-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="cb22e-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb22e-112">Description</span></span>

<span data-ttu-id="cb22e-113">Wenn Sie Microsoft System Center Operations Manager zum Überwachen von lync Server 2013 verwenden, haben Sie die Möglichkeit, "Watcher-Knoten" einzurichten: Computer, die regelmäßig und automatisch synthetische Transaktionen ausführen, um zu überprüfen, ob lync Server als erwartet.</span><span class="sxs-lookup"><span data-stu-id="cb22e-113">If you are using Microsoft System Center Operations Manager to monitor Lync Server 2013 then you have the option of setting up "watcher nodes": computers that periodically, and automatically, run synthetic transactions to verify that Lync Server is working as expected.</span></span> <span data-ttu-id="cb22e-114">Watcher-Knoten werden Pools zugewiesen und mithilfe der **CsWatcherNodeConfiguration** -Cmdlets verwaltet.</span><span class="sxs-lookup"><span data-stu-id="cb22e-114">Watcher nodes are assigned to pools, and are managed by using the **CsWatcherNodeConfiguration** cmdlets.</span></span> <span data-ttu-id="cb22e-115">Beachten Sie, dass Sie keine Watcher-Knoten installieren müssen, wenn Sie System Center Operations Manager verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb22e-115">Note that you do not need to install watcher nodes if you are using System Center Operations Manager.</span></span> <span data-ttu-id="cb22e-116">Sie können Ihr System weiterhin überwachen, ohne Watcher-Knoten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb22e-116">You can still monitor your system without using watcher nodes.</span></span> <span data-ttu-id="cb22e-117">Der einzige Unterschied besteht darin, dass alle synthetischen Transaktionen, die Sie ausführen möchten, manuell aufgerufen werden müssen, anstatt von Operations Manager automatisch aufgerufen zu werden.</span><span class="sxs-lookup"><span data-stu-id="cb22e-117">The only difference is that any synthetic transactions that you want to run must be invoked manually instead of automatically invoked by Operations Manager.</span></span>

<span data-ttu-id="cb22e-118">Mit dem Cmdlet **Test-CsWatcherNodeConfiguration** können Sie überprüfen, ob ein Watcher-Knoten ordnungsgemäß konfiguriert wurde und einem gültigen lync Server 2013-Pool zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cb22e-118">The **Test-CsWatcherNodeConfiguration** cmdlet enables you to verify that a watcher node was configured correctly and is assigned to a valid Lync Server 2013 pool.</span></span> <span data-ttu-id="cb22e-119">Beachten Sie, dass das Cmdlet **Test-CsWatcherNodeConfiguration** auf dem Watcher-Knoten selbst ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="cb22e-119">Note that the **Test-CsWatcherNodeConfiguration** cmdlet must be run on the watcher node itself.</span></span> <span data-ttu-id="cb22e-120">Das Cmdlet kann nicht für Remotecomputer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cb22e-120">The cmdlet cannot be run against remote computers.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="cb22e-121">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="cb22e-121">Running the test</span></span>

<span data-ttu-id="cb22e-122">Mit dem folgenden Befehl werden die Konfigurationseinstellungen für jeden Watcher-Knoten überprüft, der in der Organisation verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb22e-122">The following command verifies the configuration settings for each watcher node that is being used in the organization.</span></span>

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="cb22e-123">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="cb22e-123">Determining success or failure</span></span>

<span data-ttu-id="cb22e-124">Die folgende erfolgreiche Beispielausgabe zeigt ein System mit vier Edge-Servern.</span><span class="sxs-lookup"><span data-stu-id="cb22e-124">The following successful sample output shows a system with four edge servers.</span></span>

<span data-ttu-id="cb22e-125">Überprüfen des ATL-CS-001.litwareinc.com des Ziel Pools gegen Topologie.</span><span class="sxs-lookup"><span data-stu-id="cb22e-125">Validating target pool atl-cs-001.litwareinc.com against topology.</span></span>

<span data-ttu-id="cb22e-126">Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com ist in der Topologie vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cb22e-126">Success: Target pool atl-cs-001.litwareinc.com exists in topology.</span></span>

<span data-ttu-id="cb22e-127">Erfolg: Ziel Pool ATL-CS-001.litwareinc.com hat die Registrierungsstelle Rolle installiert.</span><span class="sxs-lookup"><span data-stu-id="cb22e-127">Success: Target pool atl-cs-001.litwareinc.com has Registrar role installed.</span></span>

<span data-ttu-id="cb22e-128">Erfolg: Ziel Pool-ATL-CS-001.litwareinc.com wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb22e-128">Success: Target pool atl-cs-001.litwareinc.com is supported version.</span></span>

<span data-ttu-id="cb22e-129">Erfolgreich: Port Nummer für 5061 Ziel Pool ATL-CS-001.litwareinc.com ist richtig.</span><span class="sxs-lookup"><span data-stu-id="cb22e-129">Success: Port number for 5061 Target pool atl-cs-001.litwareinc.com is correct.</span></span>

<span data-ttu-id="cb22e-130">Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="cb22e-130">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="cb22e-131">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="cb22e-131">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="cb22e-132">Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration ist nicht mehr erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cb22e-132">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="cb22e-133">Die Überprüfung auf die Registrierungsschlüssel für Watcher-Knoten, die von Watcher-Knoten Installation erstellt wurden, wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="cb22e-133">Checking for watcher node registry keys created by watcher node installation, is started.</span></span> <span data-ttu-id="cb22e-134">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="cb22e-134">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="cb22e-135">Die Überprüfung der Registrierungsschlüssel für Watcher-Knoten, die von Watcher-Knoten Installation erstellt wurden, ist zu Ende.</span><span class="sxs-lookup"><span data-stu-id="cb22e-135">Checking for watcher node registry keys created by watcher node installation, is finished.</span></span> <span data-ttu-id="cb22e-136">Der erkannte Authentifizierungstyp ist Negotiate.</span><span class="sxs-lookup"><span data-stu-id="cb22e-136">Detected authentication type is Negotiate.</span></span>

<span data-ttu-id="cb22e-137">Das vorhanden sein der Anmeldeinformationen des Testbenutzers wurde erfolgreich überprüft SIP: Benutzer1 @ ATL-CS-001.litwareinc.com im Anmelde Informations Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="cb22e-137">Successfully validated existence of test user’s credential sip:user1@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="cb22e-138">Das vorhanden sein der Anmeldeinformationen des Testbenutzers wurde erfolgreich überprüft SIP: User2 @ ATL-CS-001.litwareinc.com im Anmelde Informations Verwaltungsspeicher.</span><span class="sxs-lookup"><span data-stu-id="cb22e-138">Successfully validated existence of test user’s credential sip:user2@ atl-cs-001.litwareinc.com in credential management store.</span></span>

<span data-ttu-id="cb22e-139">Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="cb22e-139">Checking for missing pools in watcher node configuration is started.</span></span> <span data-ttu-id="cb22e-140">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="cb22e-140">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="cb22e-141">Warnung: Pool ATL-CS-001.litwareinc.com hat die Registrierungsstelle</span><span class="sxs-lookup"><span data-stu-id="cb22e-141">WARNING: Pool atl-cs-001.litwareinc.com has Registrar</span></span>

<span data-ttu-id="cb22e-142">Rolle installiert, aber es sind keine Testbenutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cb22e-142">role installed, but there are no test users configured for it.</span></span>

<span data-ttu-id="cb22e-143">Das Überprüfen auf fehlende Pools in Watcher-Knoten Konfiguration ist nicht mehr erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="cb22e-143">Checking for missing pools in watcher node configuration is finished.</span></span>

<span data-ttu-id="cb22e-144">Überprüfen der Registrierungsschlüssel für Watcher-Knoten, die von Watcher-Knoten Installation erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="cb22e-144">Checking for watcher node registry keys created by watcher node installation, is</span></span>

<span data-ttu-id="cb22e-145">begann.</span><span class="sxs-lookup"><span data-stu-id="cb22e-145">started.</span></span> <span data-ttu-id="cb22e-146">Wenn ein Fehler erkannt wird, wird er gedruckt.</span><span class="sxs-lookup"><span data-stu-id="cb22e-146">If any error is detected, it will be printed.</span></span>

<span data-ttu-id="cb22e-147">Test-CsWatcherNodeConfiguration: Integritäts Registrierungsschlüssel kann nicht gefunden werden</span><span class="sxs-lookup"><span data-stu-id="cb22e-147">Test-CsWatcherNodeConfiguration : Cannot find Health registry key in</span></span>

<span data-ttu-id="cb22e-148">Software\\Microsoft\\-Echtzeitkommunikation.</span><span class="sxs-lookup"><span data-stu-id="cb22e-148">Software\\Microsoft\\Real-Time Communications.</span></span> <span data-ttu-id="cb22e-149">Stellen Sie sicher, dass Watcher Node. msi</span><span class="sxs-lookup"><span data-stu-id="cb22e-149">Make sure watcher node .msi is</span></span>

<span data-ttu-id="cb22e-150">ordnungsgemäß installiert.</span><span class="sxs-lookup"><span data-stu-id="cb22e-150">installed properly.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="cb22e-151">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="cb22e-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="cb22e-152">Nachfolgend finden Sie einige häufige Gründe, warum **Test-CsWatcherNodeConfiguration** möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="cb22e-152">Here are some common reasons why **Test-CsWatcherNodeConfiguration** might fail:</span></span>

  - <span data-ttu-id="cb22e-153">Watcher-Knoten ist nicht ordnungsgemäß installiert.</span><span class="sxs-lookup"><span data-stu-id="cb22e-153">Watcher node is not correctly installed.</span></span>

  - <span data-ttu-id="cb22e-154">Es sind keine Testbenutzer konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="cb22e-154">No test users are configured.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cb22e-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb22e-155">See Also</span></span>


[<span data-ttu-id="cb22e-156">Get-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb22e-156">Get-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[<span data-ttu-id="cb22e-157">New-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb22e-157">New-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[<span data-ttu-id="cb22e-158">Remove-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb22e-158">Remove-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[<span data-ttu-id="cb22e-159">Set-CsWatcherNodeConfiguration</span><span class="sxs-lookup"><span data-stu-id="cb22e-159">Set-CsWatcherNodeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

