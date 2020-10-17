---
title: 'Lync Server 2013: Zuweisen einer konferenzrichtlinie für einzelne Benutzer'
description: 'Lync Server 2013: Zuweisen einer konferenzrichtlinie auf Benutzerbasis.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819d1431a2a7a921ff8c306c47c8b5f86bf5d5bb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559921"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="e77c4-103">Zuweisen einer benutzerbezogenen konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e77c4-103">Assign a per-user conferencing policy in Lync Server 2013</span></span>

 


<span data-ttu-id="e77c4-104">Die konferenzrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in lync Server-Systemsteuerung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e77c4-104">The conferencing policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel.</span></span>

<span data-ttu-id="e77c4-p101">Die Bereitstellung einer oder mehrerer Konferenzrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale Konferenzrichtlinie oder eine Konferenzrichtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer definiert wurde, werden automatisch die Konferenzbenutzerrechte und -berechtigungen in der globalen Konferenzrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="e77c4-p101">Deploying one or more per-user conferencing policies is optional. You can also deploy only a global-level conferencing policy or site-level conferencing policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact objects. Conferencing user rights and permissions automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="e77c4-109">Nach Erstellung mindestens einer Konferenzrichtlinie auf Benutzerebene führen Sie die Schritte in diesem Thema aus, um die Richtlinie mit den Benutzerrechten und -berechtigungen zuzuweisen, die der Server den von einem bestimmten Benutzer organisierten Besprechungen erteilen soll.</span><span class="sxs-lookup"><span data-stu-id="e77c4-109">After creating at least one per-user conferencing policy, use the procedures in this topic to assign the policy that specifies the user rights and permissions that you want the server to grant to the meetings organized by a particular user.</span></span>

<span data-ttu-id="e77c4-110">Eine Liste aller verfügbaren konferenzrichtlinieneinstellungen finden Sie unter [Conferencing Policy Settings Reference for lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="e77c4-110">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<span data-ttu-id="e77c4-111">Ausführliche Informationen zum Erstellen von Konferenzrichtlinien finden Sie unter [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span><span class="sxs-lookup"><span data-stu-id="e77c4-111">For details about creating conferencing policies, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy"></a><span data-ttu-id="e77c4-112">So weisen Sie eine Konferenzrichtlinie auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="e77c4-112">To assign a per-user conferencing policy</span></span>

1.  <span data-ttu-id="e77c4-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e77c4-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e77c4-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e77c4-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e77c4-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e77c4-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e77c4-116">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="e77c4-117">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="e77c4-117">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="e77c4-118">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-118">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="e77c4-119">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-119">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="e77c4-120">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="e77c4-120">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="e77c4-121">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-121">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="e77c4-122">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e77c4-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="e77c4-123">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="e77c4-123">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="e77c4-124">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="e77c4-124">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e77c4-125">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="e77c4-125">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="e77c4-126">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-126">Click **Find**.</span></span>

6.  <span data-ttu-id="e77c4-127">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-127">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="e77c4-128">Wenn Sie dieselbe Benutzerkonferenzrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e77c4-128">If you want the same per-user conferencing policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="e77c4-129">Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Konferenzrichtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="e77c4-129">In **Assign Policies**, under **Conferencing policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="e77c4-130">Da es mehrere Richtlinien gibt, die Sie in <STRONG>Zuweisungsrichtlinien</STRONG>konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e77c4-130">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="e77c4-131">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="e77c4-131">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="e77c4-132">Aktivieren Sie **\<Automatic\>** diese Option, damit lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="e77c4-132">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="e77c4-133">Klicken Sie auf der Seite **Konferenzrichtlinie** auf den Namen einer Konferenzrichtlinie auf Benutzerebene, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="e77c4-133">Click the name of a per-user conferencing policy you previously defined on the **Conferencing Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="e77c4-134">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e77c4-134">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="e77c4-135">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e77c4-135">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="e77c4-136">Zuweisen einer Per-User konferenzrichtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e77c4-136">Assigning a Per-User Conferencing Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="e77c4-137">Benutzerspezifische Konferenzrichtlinien können mithilfe von Windows PowerShell und dem Grant-CsConferencingPolicy-Cmdlet zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e77c4-137">Per-user conferencing policies can be assigned by using Windows PowerShell and the Grant-CsConferencingPolicy cmdlet.</span></span> <span data-ttu-id="e77c4-138">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e77c4-138">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="e77c4-139">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="e77c4-139">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a><span data-ttu-id="e77c4-140">So weisen Sie einem einzelnen Benutzer eine konferenzrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="e77c4-140">To assign a per-user conferencing policy to a single user</span></span>

  - <span data-ttu-id="e77c4-141">Der folgende Befehl weist dem Benutzer Ken Myer die Konferenzrichtlinie „RedmondConferencingPolicy“ auf Benutzerebene zu.</span><span class="sxs-lookup"><span data-stu-id="e77c4-141">The following command assigns the per-user conferencing policy RedmondConferencingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a><span data-ttu-id="e77c4-142">So weisen Sie mehreren Benutzern eine benutzerspezifische konferenzrichtlinie zu</span><span class="sxs-lookup"><span data-stu-id="e77c4-142">To assign a per-user conferencing policy to multiple users</span></span>

  - <span data-ttu-id="e77c4-143">Dieser Befehl weist die Konferenzrichtlinie „HRConferencingPolicy“ auf Benutzerebene allen Benutzern zu, die in der Personalabteilung tätig sind.</span><span class="sxs-lookup"><span data-stu-id="e77c4-143">This command assigns the per-user conferencing policy HRConferencingPolicy to all the users who work for the Human Resources department.</span></span> <span data-ttu-id="e77c4-144">Weitere Informationen zum LdapFilter-Parameter, der in diesem Befehl verwendet wird, finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="e77c4-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a><span data-ttu-id="e77c4-145">So heben Sie die Zuweisung einer konferenzrichtlinie pro Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="e77c4-145">To unassign a per-user conferencing policy</span></span>

  - <span data-ttu-id="e77c4-p106">Mit dem folgenden Befehl wird die Zuweisung sämtlicher Konferenzrichtlinien, die dem Benutzer Ken Myer zuvor zugeordnet wurden, aufgehoben. Nach der Aufhebung der Konferenzrichtlinie auf Benutzerebene wird Ken Myer automatisch unter Verwendung der globalen Richtlinie bzw. (sofern vorhanden) von der Richtlinie seines lokalen Standorts verwaltet. Die Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="e77c4-p106">The following command unassigns any per-user conferencing policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="e77c4-149">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsConferencingPolicy-](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e77c4-149">For more information, see the help topic for the [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="e77c4-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e77c4-150">See Also</span></span>


[<span data-ttu-id="e77c4-151">Erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e77c4-151">Create or modify a conferencing policy in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[<span data-ttu-id="e77c4-152">Zuweisen von Richtlinien pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e77c4-152">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

