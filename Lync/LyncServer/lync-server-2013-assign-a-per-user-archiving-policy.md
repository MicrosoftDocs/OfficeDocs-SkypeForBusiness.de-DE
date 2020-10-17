---
title: 'Lync Server 2013: Zuweisen einer Archivierungsrichtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine benutzerspezifische Archivierungsrichtlinie zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c81d7e426f16c298196aba733d720a92d0854bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559991"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a><span data-ttu-id="70757-103">Zuweisen einer benutzerbasierten Archivierungsrichtlinie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70757-103">Assign a per-user archiving policy in Lync Server 2013</span></span>

 


<span data-ttu-id="70757-104">Die Archivierungsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server 2013-Systemsteuerung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="70757-104">The archiving policy is one of the individual settings of a user account that you can configure in the Lync Server 2013 Control Panel.</span></span>

<span data-ttu-id="70757-p101">Die Bereitstellung einer oder mehrerer Archivierungsrichtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine Archivierungsrichtlinie auf globaler oder Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer definiert wurde, werden automatisch die Archivierungsanforderungen in der globalen Konferenzrichtlinie verwendet.</span><span class="sxs-lookup"><span data-stu-id="70757-p101">Deploying one or more per-user archiving policies is optional. You can also deploy only a global-level archiving policy or site-level archiving policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. Archiving requirements automatically default to those defined in the global-level conferencing policy when no specific site-level or per-user policy is assigned.</span></span>

<span data-ttu-id="70757-109">Nachdem Sie mindestens eine Archivierungsrichtlinie auf Benutzerebene erstellt haben, können Sie anhand der Verfahren in diesem Thema diese Richtlinie zuweisen, mit der gemäß Ihren Anforderungen angegeben wird, ob die interne und/oder externe Kommunikation eines bestimmten Benutzers vom Server archiviert wird.</span><span class="sxs-lookup"><span data-stu-id="70757-109">After creating at least one per-user archiving policy, use the procedures in this topic to assign the policy that appropriately specifies whether a particular user’s internal communications, external communications, or both, will be archived by the server.</span></span>

<span data-ttu-id="70757-110">Ausführliche Informationen zum Erstellen von benutzerspezifischen Archivierungsrichtlinien finden Sie unter [Erstellen einer Archivierungsrichtlinie in lync Server 2013, um die Archivierung der internen oder externen Kommunikation für bestimmte Websites oder Benutzer zu aktivieren oder zu deaktivieren](lync-server-2013-create-archiving-policy-sites-users.md).</span><span class="sxs-lookup"><span data-stu-id="70757-110">For details about creating per-user archiving policies, see [Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of Internal or external communications for specific sites or users](lync-server-2013-create-archiving-policy-sites-users.md).</span></span>

## <a name="to-assign-a-per-user-archiving-policy"></a><span data-ttu-id="70757-111">So weisen Sie eine Archivierungsrichtlinie auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="70757-111">To assign a per-user archiving policy</span></span>

1.  <span data-ttu-id="70757-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="70757-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="70757-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="70757-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="70757-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="70757-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="70757-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="70757-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="70757-116">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="70757-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="70757-117">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="70757-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="70757-118">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="70757-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="70757-119">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="70757-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="70757-120">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="70757-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="70757-121">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="70757-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="70757-122">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="70757-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="70757-123">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="70757-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="70757-124">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="70757-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="70757-125">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="70757-125">Click **Find**.</span></span>

6.  <span data-ttu-id="70757-126">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="70757-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="70757-127">Wenn Sie dieselbe Benutzerarchivierungsrichtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf <STRONG>Aktionen</STRONG> und anschließend auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="70757-127">If you want the same per-user archiving policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="70757-128">Führen Sie im Abschnitt **Richtlinien zuweisen** unter **Archivierungsrichtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="70757-128">In **Assign Policies**, under **Archiving policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="70757-129">Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="70757-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="70757-130">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="70757-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="70757-131">Zulassen, dass lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene auswählen.</span><span class="sxs-lookup"><span data-stu-id="70757-131">Allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="70757-132">Klicken Sie auf der Seite **Archivierungsrichtlinie** auf den Namen einer Archivierungsrichtlinie auf Benutzerebene, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="70757-132">Click the name of a per-user archiving policy you previously defined on the **Archiving Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="70757-133">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="70757-133">To help you decide the policy that you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="70757-134">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="70757-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="70757-135">Zuweisen einer Per-User Archivierungsrichtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="70757-135">Assigning a Per-User Archiving Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="70757-136">Sie können benutzerspezifische Archivierungsrichtlinien zuweisen, indem Sie Windows PowerShell und das **Grant-CsArchivingPolicy-** Cmdlet verwenden.</span><span class="sxs-lookup"><span data-stu-id="70757-136">You can assign per-user archiving policies by using Windows PowerShell and the **Grant-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="70757-137">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="70757-137">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="70757-138">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="70757-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a><span data-ttu-id="70757-139">So weisen Sie einem einzelnen Benutzer eine benutzerspezifische Archivierungsrichtlinie zu</span><span class="sxs-lookup"><span data-stu-id="70757-139">To assign a per-user archiving policy to a single user</span></span>

  - <span data-ttu-id="70757-140">Mit dem folgenden Befehl wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" dem Benutzer "Ken Myer" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="70757-140">The following command assigns the per-user archiving policy RedmondArchivingPolicy to the user Ken Myer.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a><span data-ttu-id="70757-141">So weisen Sie mehreren Benutzern eine benutzerspezifische Archivierungsrichtlinie zu</span><span class="sxs-lookup"><span data-stu-id="70757-141">To assign a per-user archiving policy to multiple users</span></span>

  - <span data-ttu-id="70757-142">Mithilfe dieses Befehls wird die benutzerbezogene Archivierungsrichtlinie "RedmondArchivingPolicy" allen Benutzern zugeordnet, deren Konten im Registrar-Pool "atl-cs-001.litwareinc.com" verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="70757-142">This command assigns the per-user archiving policy RedmondArchivingPolicy to all the users who have accounts homed on the Registrar pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="70757-143">Weitere Informationen zum in diesem Befehl verwendeten Filter-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="70757-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a><span data-ttu-id="70757-144">So heben Sie die Zuweisung einer benutzerbasierten Archivierungsrichtlinie auf</span><span class="sxs-lookup"><span data-stu-id="70757-144">To unassign a per-user archiving policy</span></span>

  - <span data-ttu-id="70757-p106">Der folgende Befehl hebt alle bestehenden Zuweisungen von benutzerbezogenen Archivierungsrichtlinien zu "Ken Myer" auf. Danach wird Ken Myer automatisch von der globalen Richtlinie oder, wenn vorhanden, von der Richtlinie für seinen lokalen Standort verwaltet. (Standortrichtlinien haben Vorrang vor der globalen Richtlinie).</span><span class="sxs-lookup"><span data-stu-id="70757-p106">The following command unassigns any per-user archiving policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="70757-148">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsArchivingPolicy-](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="70757-148">For more information, see the help topic for the [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="70757-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70757-149">See Also</span></span>


[<span data-ttu-id="70757-150">Erstellen einer Archivierungsrichtlinie in lync Server 2013 zum Aktivieren oder Deaktivieren der Archivierung interner oder externer Kommunikation für bestimmte Websites oder Benutzer</span><span class="sxs-lookup"><span data-stu-id="70757-150">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)  


[<span data-ttu-id="70757-151">Zuweisen von Richtlinien pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="70757-151">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)

