---
title: 'Lync Server 2013: Zuweisen einer Standortrichtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine ortungsrichtlinie pro Benutzer zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81631740e0a6c908c392ccacb6b37d7033d9224c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559881"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a><span data-ttu-id="e55ac-103">Zuweisen einer Standortrichtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e55ac-103">Assign a per-user location policy in Lync Server 2013</span></span>

 


<span data-ttu-id="e55ac-104">Die ortungsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e55ac-104">The location policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="e55ac-p101">Die Bereitstellung einer oder mehrerer Ortungsrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine Ortungsrichtlinie auf globaler oder auf Subnetzebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. E9-1-1-Einstellungen werden standardmäßig auf die in der Ortungsrichtlinie auf globaler Ebene definierten Einstellungen festgelegt, wenn keine spezifische Richtlinie auf Subnetz- oder Benutzerebene zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e55ac-p101">Deploying one or more per-user location policies is optional. You can also deploy only a global-level location policy or subnet-level location policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Enhanced 9-1-1 (E9-1-1) settings automatically default to those defined in the global-level location policy when no specific subnet-level or per-user policy is assigned.</span></span>

<span data-ttu-id="e55ac-109">Nach Erstellung mindestens einer Ortungsrichtlinie auf Benutzerebene führen Sie die Schritte in diesem Thema aus, um die Richtlinie mit den Einstellungen zuzuweisen, die der Server auf Notrufe von einem bestimmten Benutzer anwenden soll.</span><span class="sxs-lookup"><span data-stu-id="e55ac-109">After creating at least one per-user location policy, use the procedures in this topic to assign to the policy that specifies the settings that you want the server to apply for emergency calls placed by a particular user.</span></span>

<span data-ttu-id="e55ac-110">Eine Liste aller verfügbaren Standortrichtlinien Einstellungen finden Sie unter [Definieren der ortungsrichtlinie für lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e55ac-110">For a list of all available location policy settings, see [Defining the location policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).</span></span>

<span data-ttu-id="e55ac-111">Ausführliche Informationen zum Erstellen von ortungsrichtlinien finden Sie unter [Create Location Policies in lync Server 2013](lync-server-2013-create-location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e55ac-111">For details about creating location policies, see [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).</span></span>

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a><span data-ttu-id="e55ac-112">So weisen Sie eine benutzerspezifische ortungsrichtlinie dem lync Server-Systemsteuerung zu</span><span class="sxs-lookup"><span data-stu-id="e55ac-112">To assign a per-user location policy with the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e55ac-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e55ac-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e55ac-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e55ac-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e55ac-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e55ac-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e55ac-116">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e55ac-117">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="e55ac-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="e55ac-118">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="e55ac-119">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="e55ac-120">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="e55ac-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="e55ac-121">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="e55ac-122">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e55ac-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="e55ac-123">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="e55ac-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="e55ac-124">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="e55ac-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e55ac-125">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="e55ac-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="e55ac-126">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-126">Click **Find**.</span></span>

6.  <span data-ttu-id="e55ac-127">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="e55ac-128">Wenn Sie dieselbe Benutzerortungsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e55ac-128">If you want the same per-user location policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="e55ac-129">Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Ortungsrichtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e55ac-129">In **Assign Policies**, under **Location policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e55ac-130">Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e55ac-130">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="e55ac-131">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="e55ac-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="e55ac-132">Zulassen, dass lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Subnetzebene wählt.</span><span class="sxs-lookup"><span data-stu-id="e55ac-132">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the subnet-level policy.</span></span>
    
      - <span data-ttu-id="e55ac-133">Klicken Sie auf den Namen einer Benutzerortungsrichtlinie, die Sie zuvor durch Ausführen des Cmdlets **New-CsLocationPolicy** definiert haben.</span><span class="sxs-lookup"><span data-stu-id="e55ac-133">Click the name of a per-user location policy you previously defined by running the **New-CsLocationPolicy** cmdlet.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e55ac-134">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e55ac-134">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="e55ac-135">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e55ac-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a><span data-ttu-id="e55ac-136">Zuweisen einer Per-User ortungsrichtlinie mithilfe von lync Server-Verwaltungsshell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e55ac-136">Assigning a Per-User Location Policy by Using Lync Server Management Shell Cmdlets</span></span>

<span data-ttu-id="e55ac-137">Sie können benutzerspezifische ortungsrichtlinien zuweisen, indem Sie das Grant-CsLocationPolicy-Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="e55ac-137">You can assign per-user location policies by using the Grant-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="e55ac-138">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="e55ac-138">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e55ac-139">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e55ac-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a><span data-ttu-id="e55ac-140">So weisen Sie eine benutzerbasierte Standortrichtlinie einem einzelnen Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="e55ac-140">To assign a per-user location policy to a single user</span></span>

  - <span data-ttu-id="e55ac-141">Mit dem folgenden Befehl wird die benutzerbasierte Standortrichtlinie RedmondLocationPolicy dem Benutzer Ken Myer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e55ac-141">The following command assigns the per-user location policy RedmondLocationPolicy to the user Ken Myer.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a><span data-ttu-id="e55ac-142">So weisen Sie eine benutzerbasierte Standortrichtlinie mehreren Benutzern zu</span><span class="sxs-lookup"><span data-stu-id="e55ac-142">To assign a per-user location policy to multiple users</span></span>

  - <span data-ttu-id="e55ac-143">Mit diesem Befehl wird die benutzerspezifische ortungsrichtlinie AccountingDepartmentLocationPolicy allen Benutzern zugewiesen, die für die Buchhaltungsabteilung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="e55ac-143">This command assigns the per-user location policy AccountingDepartmentLocationPolicy to all the users who work for the Accounting department.</span></span> <span data-ttu-id="e55ac-144">Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="e55ac-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a><span data-ttu-id="e55ac-145">So heben Sie die Zuweisung der benutzerbasierten Standortrichtlinie auf</span><span class="sxs-lookup"><span data-stu-id="e55ac-145">To unassign a per-user location policy</span></span>

  - <span data-ttu-id="e55ac-p106">Mit dem folgenden Befehl wird die für den Benutzer Ken Myer vorgenommene Zuweisung einer benutzerbasierten Standortrichtlinie aufgehoben. Nach dem Aufheben der benutzerbasierten Standortrichtlinie wird Ken Myer automatisch mithilfe der globalen Richtlinie verwaltet oder, sofern vorhanden, mit der ihm zugewiesenen lokalen Standortrichtlinie. Eine Standortrichtlinie hat Vorrang vor einer globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="e55ac-p106">The following command unassigns any per-user location policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="e55ac-149">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsLocationPolicy-](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e55ac-149">For more information, see the help topic for the [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) cmdlet.</span></span>

