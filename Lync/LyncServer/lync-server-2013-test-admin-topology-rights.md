---
title: 'Lync Server 2013: Testen der Rechte der Administrator Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin topology rights
ms:assetid: 0c03b7fd-449a-47ad-8263-ce811164cbce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767943(v=OCS.15)
ms:contentKeyID: 63969575
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5aaeef1799ee2e35746f659ce451160854a25d89
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-admin-topology-rights-in-lync-server-2013"></a><span data-ttu-id="f9c54-102">Testen der Rechte der Administrator Topologie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9c54-102">Test admin topology rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9c54-103">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="f9c54-103">_**Topic Last Modified:** 2016-12-08_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9c54-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="f9c54-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f9c54-105">Nach der anfänglichen lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="f9c54-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="f9c54-106">Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="f9c54-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9c54-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="f9c54-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f9c54-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f9c54-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9c54-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f9c54-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f9c54-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="f9c54-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f9c54-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Cmdlets Test-CsSetupPermission verfügt.</span><span class="sxs-lookup"><span data-stu-id="f9c54-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="f9c54-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="f9c54-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsSetupPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f9c54-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9c54-113">Description</span></span>

<span data-ttu-id="f9c54-114">Standardmäßig können nur Domänenadministratoren eine lync Server Topologie aktivieren und umfangreiche Änderungen an der lync Server Infrastruktur vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f9c54-114">By default, only domain administrators can enable a Lync Server topology and make large changes to the Lync Server infrastructure.</span></span> <span data-ttu-id="f9c54-115">Dies ist kein Problem, solange die Domänenadministratoren und die lync Server Administratoren identisch sind. In vielen Organisationen lync Server Administratoren keine Administratorrechte für die gesamte Domäne besitzen.</span><span class="sxs-lookup"><span data-stu-id="f9c54-115">This won't be a problem as long as your domain administrators and your Lync Server administrators are one and the same.In many organizations Lync Server administrators do not hold administrative rights to the whole domain.</span></span> <span data-ttu-id="f9c54-116">Standardmäßig bedeutet dies, dass diese Administratoren (definiert als Mitglieder der Gruppe "RTCUniversalServerAdmins") keine Änderungen an lync Server Topologie vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="f9c54-116">By default, that means that these administrators (defined as members of the RTCUniversalServerAdmins group) can't make Lync Server topology changes.</span></span> <span data-ttu-id="f9c54-117">Um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, Topologie-Änderungen vorzunehmen, müssen Sie mithilfe des Cmdlets [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) die erforderlichen Active Directory Berechtigungen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f9c54-117">To give members of the RTCUniversalServerAdmins group the right to make topology changes, you must assign the required Active Directory permissions by using the [Grant-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsSetupPermission) cmdlet.</span></span>

<span data-ttu-id="f9c54-118">Das Cmdlet Test-CsSetupPermission überprüft, ob die erforderlichen Berechtigungen, die zum Installieren von lync Server oder einer seiner Komponenten erforderlich sind, für den angegebenen Active Directory Container konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f9c54-118">The Test-CsSetupPermission cmdlet verifies that the required permissions that are needed to install Lync Server or one of its components are configured on the specified Active Directory container.</span></span> <span data-ttu-id="f9c54-119">Wenn die Berechtigungen nicht zugewiesen sind, können Sie das Grant-CsSetupPermission-Cmdlet ausführen, um Mitgliedern der RTCUniversalServerAdmins-Gruppe das Recht zu geben, lync Server zu installieren und zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9c54-119">If the permissions are not assigned, you can then run the Grant-CsSetupPermission cmdlet to give members of the RTCUniversalServerAdmins group the right to install and enable Lync Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9c54-120">Eine detaillierte Liste der Berechtigungen, die von Grant-CsSetupPermission zugewiesen wurden, finden Sie im Blogbeitrag <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission und Grant-CsOUPermission</A>.</span><span class="sxs-lookup"><span data-stu-id="f9c54-120">For a detailed list of permissions assigned by Grant-CsSetupPermission, see the blog post <A href="https://blogs.technet.com/b/jenstr/archive/2011/02/07/grant-cssetuppermission-and-grant-csoupermission.aspx">Grant-CsSetupPermission and Grant-CsOUPermission</A>.</span></span>



</div>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f9c54-121">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="f9c54-121">Running the test</span></span>

<span data-ttu-id="f9c54-122">Rufen Sie das Cmdlet Test-CsSetupPermission auf, um zu bestimmen, ob Setup Berechtigungen für einen Active Directory Container zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="f9c54-122">To determine whether setup permissions are assigned for an Active Directory container, call the Test-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="f9c54-123">Geben Sie den Distinguished Name des Containers an, der überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9c54-123">Specify the distinguished name of the container to be checked.</span></span> <span data-ttu-id="f9c54-124">Mit diesem Befehl werden beispielsweise die Setup Berechtigungen für den Container ou = CsServers, DC = litwareinc, DC = com überprüft:</span><span class="sxs-lookup"><span data-stu-id="f9c54-124">For example, this command verifies setup permissions on the container ou=CsServers,dc=litwareinc,dc=com:</span></span>

    Test-CsSetupPermission -ComputerOU "ou=CsServers,dc=litwareinc,dc=com"

<span data-ttu-id="f9c54-125">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="f9c54-125">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f9c54-126">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="f9c54-126">Determining success or failure</span></span>

<span data-ttu-id="f9c54-127">Wenn Test-CsSetupPermission feststellt, dass die erforderlichen Berechtigungen bereits für einen Active Directory Container festgelegt wurden, gibt das Cmdlet den Wert true zurück:</span><span class="sxs-lookup"><span data-stu-id="f9c54-127">If Test-CsSetupPermission determines that the required permissions have already been set on an Active Directory container then the cmdlet will return the value True:</span></span>

<span data-ttu-id="f9c54-128">Wahr</span><span class="sxs-lookup"><span data-stu-id="f9c54-128">True</span></span>

<span data-ttu-id="f9c54-129">Wenn Berechtigungen nicht festgelegt sind, gibt Test-CsSetupPermission den Wert false zurück.</span><span class="sxs-lookup"><span data-stu-id="f9c54-129">If permissions are not set, Test-CsSetupPermission will return the value False.</span></span> <span data-ttu-id="f9c54-130">Beachten Sie, dass dieser Wert in der Regel in viele Warnmeldungen eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f9c54-130">Note that this value will typically be enclosed in many warning messages.</span></span> <span data-ttu-id="f9c54-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f9c54-131">For example:</span></span>

<span data-ttu-id="f9c54-132">Warnung: Zugriffssteuerungseintrag (Access Control Entry, ACE) ATL\\-CS-001 RTCUniversalServerAdmins; Ermöglichen ExtendedRight; Keine Keine 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span><span class="sxs-lookup"><span data-stu-id="f9c54-132">WARNING: Access control entry (ACE) atl-cs-001\\RTCUniversalServerAdmins; Allow; ExtendedRight; None; None; 1131f6aa-9c07-11d1-f79f-00c04fc2dcd2</span></span>

<span data-ttu-id="f9c54-133">Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "CN = Computers, DC = litwareinc, DC = com" sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f9c54-133">WARNING: The access control entries (ACEs) on the object "CN=Computers,DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="f9c54-134">False</span><span class="sxs-lookup"><span data-stu-id="f9c54-134">False</span></span>

<span data-ttu-id="f9c54-135">Warnung: "Test-CsSetupPermission"-Verarbeitung wurde mit Warnungen abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9c54-135">WARNING: "Test-CsSetupPermission" processing has completed with warnings.</span></span> <span data-ttu-id="f9c54-136">"2"-Warnungen wurden während dieser Ausführung aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f9c54-136">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="f9c54-137">Warnung: detaillierte Ergebnisse finden Sie unter "C\\: Users\\admin\\APPDATA\\local\\Temp\\Test-CsSetupPermission-1da99ba6-ABE2-45e4-8b16-dfd244763118. html".</span><span class="sxs-lookup"><span data-stu-id="f9c54-137">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsSetupPermission-1da99ba6-abe2-45e4-8b16-dfd244763118.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f9c54-138">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="f9c54-138">Reasons why the test might have failed</span></span>

<span data-ttu-id="f9c54-139">Obwohl es seltene Ausnahmen gibt, wenn Test-CsSetupPermission fehlschlägt, bedeutet dies normalerweise, dass dem angegebenen Active Directory Container keine Setup Berechtigungen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="f9c54-139">Although there are rare exceptions, if Test-CsSetupPermission fails that typically means that setup permissions are not assigned for the specified Active Directory container.</span></span> <span data-ttu-id="f9c54-140">Diese Berechtigungen können mithilfe des Cmdlets Grant-CsSetupPermission zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f9c54-140">Those permissions can be assigned by using the Grant-CsSetupPermission cmdlet.</span></span> <span data-ttu-id="f9c54-141">Beispielsweise erteilt dieser Befehl dem Computer Container in der Domäne litwareinc.com Setup Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="f9c54-141">For example, this command grants setup permissions to the Computers container in the domain litwareinc.com:</span></span>

    Grant-CsSetupPermission -ComputerOU "cn=Computers,dc=litwareinc,dc=com"

<span data-ttu-id="f9c54-142">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) .</span><span class="sxs-lookup"><span data-stu-id="f9c54-142">For more information, see the help topic for the [Test-CsSetupPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsSetupPermission) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

