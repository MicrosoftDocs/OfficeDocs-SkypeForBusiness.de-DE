---
title: 'Lync Server 2013: Testen der Administratorberechtigungen'
description: 'Lync Server 2013: Testen der Administratorberechtigungen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568521"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="65f41-103">Testen von Administratorberechtigungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65f41-103">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65f41-104">_**Letztes Änderungsstand des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="65f41-104">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65f41-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="65f41-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="65f41-106">Nach der anfänglichen lync Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="65f41-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="65f41-107">Bei Bedarf, wenn berechtigungsbezogene Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="65f41-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f41-108">Test Tool</span><span class="sxs-lookup"><span data-stu-id="65f41-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="65f41-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65f41-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f41-110">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="65f41-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="65f41-111">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="65f41-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="65f41-112">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsOUPermission-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="65f41-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="65f41-113">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="65f41-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="65f41-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65f41-114">Description</span></span>

<span data-ttu-id="65f41-115">Wenn Sie lync Server 2013 1 der Aufgaben installieren, die vom Setup Programm ausgeführt wurden, gibt die RTCUniversalUserAdmins-Gruppe die Active Directory Berechtigungen, die zum Verwalten von Benutzern, Computern, Kontakten, Anwendungs Kontakten und inetOrgPerson Personen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="65f41-115">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="65f41-116">Wenn Sie die Vererbung von Berechtigungen in Active Directory Setup deaktiviert haben, können diese Berechtigungen nicht zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="65f41-116">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="65f41-117">Daher können Mitglieder der RTCUniversalUserAdmins-Gruppe lync Server Entitäten nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="65f41-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="65f41-118">Diese Verwaltungsprivilegien sind nur für Domänenadministratoren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65f41-118">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="65f41-119">Das Test-CsOUPermission-Cmdlet überprüft, ob die erforderlichen Berechtigungen zum Verwalten von Benutzern, Computern und anderen Objekten für einen Active Directory Container festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="65f41-119">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="65f41-120">Wenn diese Berechtigungen nicht festgelegt sind, können Sie dieses Problem beheben, indem Sie das [Grant-CsOUPermission-](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) Cmdlet ausführen.</span><span class="sxs-lookup"><span data-stu-id="65f41-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="65f41-121">Beachten Sie, dass Grant-CsOUPermission nur Mitgliedern der Gruppe RTCUniversalUserAdmins Berechtigungen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="65f41-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="65f41-122">Dieses Cmdlet kann nicht verwendet werden, um einem beliebigen Benutzer oder einer Gruppe Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="65f41-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="65f41-123">Wenn Sie möchten, dass ein anderer Benutzer oder eine andere Gruppe über Benutzer Verwaltungsberechtigungen verfügt, sollten Sie diesen Benutzer (oder diese Gruppe) der Gruppe RTCUniversalUserAdmins hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="65f41-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="65f41-124">Weitere Informationen zu ou-Berechtigungen finden Sie im Artikel die [Vererbung von Berechtigungen ist für Computer, Benutzer oder inetOrgPerson-Container in lync Server 2013 deaktiviert](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="65f41-124">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="65f41-125">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="65f41-125">Running the test</span></span>

<span data-ttu-id="65f41-126">Um zu überprüfen, ob Verwaltungsberechtigungen für einen Container festgelegt sind, führen Sie das Test-CsOUPermission-Cmdlet gefolgt vom DN (Distinguished Name) des Containers und dem Typ der Berechtigungen aus, die Sie überprüfen.</span><span class="sxs-lookup"><span data-stu-id="65f41-126">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="65f41-127">Mit diesem Befehl wird beispielsweise überprüft, ob die Benutzerberechtigungen für die OU ou = Redmond, DC = litwareinc, DC = com festgelegt sind:</span><span class="sxs-lookup"><span data-stu-id="65f41-127">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="65f41-128">Wenn Sie mehrere Berechtigungen mithilfe eines einzelnen Befehls überprüfen möchten, schließen Sie die in Anführungszeichen eingeschlossenen Berechtigungstypen ein, und trennen Sie diese Typen dann durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="65f41-128">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="65f41-129">Mit diesem Befehl werden beispielsweise Benutzer-, Computer-und Kontakt Berechtigungen überprüft:</span><span class="sxs-lookup"><span data-stu-id="65f41-129">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="65f41-130">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="65f41-130">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="65f41-131">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="65f41-131">Determining success or failure</span></span>

<span data-ttu-id="65f41-132">Wenn die erforderlichen Berechtigungen bereits festgelegt wurden, gibt Test-CsOUPermission eine Antwort mit einem Wort zurück:</span><span class="sxs-lookup"><span data-stu-id="65f41-132">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="65f41-133">Richtig</span><span class="sxs-lookup"><span data-stu-id="65f41-133">True</span></span>

<span data-ttu-id="65f41-134">Wenn die erforderlichen Berechtigungen nicht festgelegt sind, gibt Test-CsOUPermission den Wert false zurück.</span><span class="sxs-lookup"><span data-stu-id="65f41-134">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="65f41-135">Möglicherweise müssen Sie einen Moment suchen, um diesen Wert zu finden.</span><span class="sxs-lookup"><span data-stu-id="65f41-135">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="65f41-136">Sie wird in der Regel in mehrere begleitende Warnungen eingebettet.</span><span class="sxs-lookup"><span data-stu-id="65f41-136">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="65f41-137">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="65f41-137">For example:</span></span>

<span data-ttu-id="65f41-138">Warnung: Zugriffssteuerungseintrag (Access Control Entry, ACE) ATL-CS-001 \\ RTCUniversalUserReadOnlyGroup hinzugefügt; Allow; ReadProperty ContainerInherit Nachfolger bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="65f41-138">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="65f41-139">Warnung: die Zugriffssteuerungseinträge (ACEs) für das Objekt "ou = Northamerica, DC = ATL-CS-001 \\ DC = litwareinc, DC = com" sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="65f41-139">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="65f41-140">False</span><span class="sxs-lookup"><span data-stu-id="65f41-140">False</span></span>

<span data-ttu-id="65f41-141">Warnung: "Test-CsOUPermission"-Verarbeitung wurde mit Warnungen abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="65f41-141">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="65f41-142">"2"-Warnungen wurden während dieser Ausführung aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="65f41-142">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="65f41-143">Warnung: detaillierte Ergebnisse finden Sie unter "C: \\ Users \\ Admin \\ AppData \\ local \\ Temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="65f41-143">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="65f41-144">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="65f41-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="65f41-145">Wenn Test-CsOUPermission fehlschlägt, bedeutet dies normalerweise, dass die angegebene Berechtigung nicht der Gruppe RTCUniversalUserAdmins zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="65f41-145">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="65f41-146">Sie können dieses Problem beheben und die erforderlichen Berechtigungen mithilfe des Grant-CsOUPermission-Cmdlets zuweisen.</span><span class="sxs-lookup"><span data-stu-id="65f41-146">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="65f41-147">Mit diesem Befehl erhalten Sie beispielsweise die OU-Berechtigungen für Benutzer, Kontakte und InetOrgPersons für die RTCUniversalUserAdmins-Gruppe:</span><span class="sxs-lookup"><span data-stu-id="65f41-147">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="65f41-148">Weitere Informationen finden Sie im Hilfethema zum Cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="65f41-148">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

