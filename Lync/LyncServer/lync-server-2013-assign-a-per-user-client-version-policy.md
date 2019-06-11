---
title: 'Lync Server 2013: Zuweisen einer clientversionsrichtlinie für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bfd26aff4ae2e5d8dacf7ec145bec0e3247facf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839753"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="10dbd-102">Zuweisen einer clientversionsrichtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dbd-102">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="10dbd-103">Die clientversionsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="10dbd-103">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="10dbd-104">Das Bereitstelleneiner oder mehrerer clientversionsrichtlinien für einzelne Benutzer ist optional.</span><span class="sxs-lookup"><span data-stu-id="10dbd-104">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="10dbd-105">Sie können auch nur eine clientversionsrichtlinie auf globaler Ebene oder clientversionsrichtlinien auf Websiteebene oder auf Poolebene bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-105">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="10dbd-106">Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-106">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="10dbd-107">Wenn keine bestimmte Richtlinie auf Websiteebene, Poolebene oder pro Benutzer zugewiesen ist, werden die Standard Clients, die bei lync Server 2013 registriert werden können, in den clientversionsrichtlinien auf globaler Ebene definiert.</span><span class="sxs-lookup"><span data-stu-id="10dbd-107">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="10dbd-108">Nachdem Sie mindestens eine clientversionsrichtlinie für einzelne Benutzer erstellt haben, verwenden Sie die Verfahren in diesem Thema, um die Richtlinie zuzuweisen, die die Clientversionen angibt, die Sie für die Registrierung bei lync Server zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="10dbd-108">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="10dbd-109">Details zum Erstellen von clientversionsrichtlinien für einzelne Benutzer finden Sie unter [angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013 verwendet werden können](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="10dbd-109">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="10dbd-110">So weisen Sie eine clientversionsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="10dbd-110">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="10dbd-111">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="10dbd-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10dbd-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="10dbd-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="10dbd-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="10dbd-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-114">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="10dbd-115">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="10dbd-115">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="10dbd-116">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="10dbd-117">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="10dbd-118">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="10dbd-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="10dbd-119">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-119">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="10dbd-120">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-120">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="10dbd-121">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="10dbd-121">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="10dbd-122">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="10dbd-122">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="10dbd-123">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="10dbd-123">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="10dbd-124">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-124">Click **Find**.</span></span>

6.  <span data-ttu-id="10dbd-125">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-125">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="10dbd-126">Wenn Sie möchten, dass die gleiche clientversionsrichtlinie für einzelne Benutzer auf mehrere Benutzer angewendet wird, wählen Sie in den Suchergebnissen mehrere Benutzer aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>, und klicken Sie dann auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="10dbd-126">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="10dbd-127">Führen Sie in **Richtlinien zuweisen**unter **Client Versionsrichtlinie**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="10dbd-127">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="10dbd-128">Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren <STRONG> &lt;&gt; </STRONG> können, ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="10dbd-128">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="10dbd-129">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="10dbd-129">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="10dbd-130">Zulassen, dass lync Server automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene oder auf Poolebene wählt.</span><span class="sxs-lookup"><span data-stu-id="10dbd-130">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="10dbd-131">Klicken Sie auf den Namen der benutzerdefinierten clientversionsrichtlinie, die Sie zuvor auf der Seite **clientversionsrichtlinie** definiert haben.</span><span class="sxs-lookup"><span data-stu-id="10dbd-131">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="10dbd-132">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-132">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="10dbd-133">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="10dbd-133">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="10dbd-134">Zuweisen einer Client Versionsrichtlinie für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="10dbd-134">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="10dbd-135">Mithilfe des Cmdlets Grant-CsClientVersionPolicy können Sie clientversionsrichtlinien für einzelne Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-135">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="10dbd-136">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-136">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="10dbd-137">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="10dbd-137">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="10dbd-138">So weisen Sie einem einzelnen Benutzer eine clientversionsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="10dbd-138">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="10dbd-139">Mit dem folgenden Befehl wird dem Benutzer Ken Myers die Richtlinie für benutzerspezifische clientversionsrichtlinien RedmondClientVersionPolicy zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="10dbd-139">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="10dbd-140">So weisen Sie mehreren Benutzern eine Richtlinie für die benutzerspezifische Client Version zu</span><span class="sxs-lookup"><span data-stu-id="10dbd-140">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="10dbd-141">Dieser Befehl weist allen Benutzern, denen zurzeit die VoIP-Richtlinien RedmondVoicePolicy zugewiesen sind, die Richtlinien für die Benutzer-RedmondClientVersionPolicy-Client Version zu.</span><span class="sxs-lookup"><span data-stu-id="10dbd-141">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="10dbd-142">Weitere Informationen zu dem in diesem Befehl verwendeten Filter Parameter finden Sie in der Dokumentation für das Cmdlet " [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) ".</span><span class="sxs-lookup"><span data-stu-id="10dbd-142">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="10dbd-143">So heben Sie die Zuweisung einer clientversionsrichtlinie für einzelne Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="10dbd-143">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="10dbd-144">Mit dem folgenden Befehl wird die Zuweisung einer benutzerseitigen clientversionsrichtlinie, die Ken Myers zuvor zugewiesen wurde, aufheben.</span><span class="sxs-lookup"><span data-stu-id="10dbd-144">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="10dbd-145">Nachdem die Richtlinie für einzelne Benutzer nicht zugewiesen wurde, wird Ken Myers automatisch mithilfe der globalen Richtlinie, seiner lokalen Website Richtlinie (sofern vorhanden) oder der seiner Registrierungsstelle zugewiesenen Dienstbereichs Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="10dbd-145">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="10dbd-146">Eine Dienstbereichs Richtlinie hat Vorrang vor jeder Website Richtlinie, und eine Website Richtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="10dbd-146">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="10dbd-147">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="10dbd-147">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="10dbd-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10dbd-148">See Also</span></span>


[<span data-ttu-id="10dbd-149">Zuweisen von Richtlinien für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dbd-149">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="10dbd-150">Verwalten von Geräten, Telefonen und Clientanwendungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dbd-150">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

