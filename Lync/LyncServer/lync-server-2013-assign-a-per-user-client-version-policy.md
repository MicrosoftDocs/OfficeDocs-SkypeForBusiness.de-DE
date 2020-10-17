---
title: 'Lync Server 2013: Zuweisen einer clientversionsrichtlinie pro Benutzer'
description: 'Lync Server 2013: weisen Sie eine clientversionsrichtlinie pro Benutzer zu.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559977"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="a9110-103">Zuweisen einer clientversionsrichtlinie pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9110-103">Assign a per-user client version policy in Lync Server 2013</span></span>

 


<span data-ttu-id="a9110-104">Die clientversionsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="a9110-104">The client version policy is one of the individual settings of a user account that you can configure in the Lync Server Control Panel.</span></span>

<span data-ttu-id="a9110-105">Die Bereitstellung einer oder mehrerer clientversionsrichtlinien pro Benutzer ist optional.</span><span class="sxs-lookup"><span data-stu-id="a9110-105">Deploying one or more per-user client version policies is optional.</span></span> <span data-ttu-id="a9110-106">Sie können auch nur eine clientversionsrichtlinie auf globaler Ebene oder clientversionsrichtlinien auf Websiteebene oder Poolebene bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a9110-106">You can also deploy only a global-level client version policy, or site-level or pool-level client version policies.</span></span> <span data-ttu-id="a9110-107">Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9110-107">If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object.</span></span> <span data-ttu-id="a9110-108">Wenn keine bestimmte Richtlinie auf Website-, Pool-oder Benutzerebene zugewiesen ist, werden die Standard Clients, die sich bei lync Server 2013 registrieren dürfen, in der clientversionsrichtlinie auf globaler Ebene definiert.</span><span class="sxs-lookup"><span data-stu-id="a9110-108">When no specific site-level, pool-level, or per-user policy is assigned, the default clients that are allowed to register with Lync Server 2013 are those defined in the global-level client version policy.</span></span>

<span data-ttu-id="a9110-109">Nachdem Sie mindestens eine clientversionsrichtlinie pro Benutzer erstellt haben, weisen Sie anhand der Verfahren in diesem Thema die Richtlinie zu, die die Clientversionen angibt, die Sie für die Registrierung mit lync Server zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="a9110-109">After creating at least one per-user client version policy, use the procedures in this topic to assign the policy that specifies the client versions that you want to allow to register with Lync Server.</span></span>

<span data-ttu-id="a9110-110">Ausführliche Informationen zum Erstellen von clientversionsrichtlinien pro Benutzer finden Sie unter [angeben der Clientanwendungen, die für die Anmeldung bei lync Server 2013 verwendet werden können](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="a9110-110">For details about creating per-user client version policies, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).</span></span>

## <a name="to-assign-a-per-user-client-version-policy"></a><span data-ttu-id="a9110-111">So weisen Sie eine clientversionsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="a9110-111">To assign a per-user client version policy</span></span>

1.  <span data-ttu-id="a9110-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a9110-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a9110-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a9110-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a9110-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a9110-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a9110-115">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="a9110-115">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="a9110-116">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="a9110-116">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="a9110-117">Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="a9110-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="a9110-118">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="a9110-118">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="a9110-119">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:</span><span class="sxs-lookup"><span data-stu-id="a9110-119">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="a9110-120">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a9110-120">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="a9110-121">Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a9110-121">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="a9110-122">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="a9110-122">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="a9110-123">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="a9110-123">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a9110-124">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="a9110-124">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="a9110-125">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="a9110-125">Click **Find**.</span></span>

6.  <span data-ttu-id="a9110-126">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="a9110-126">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="a9110-127">Wenn Sie dieselbe clientversionsrichtlinie auf Benutzerbasis auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>und dann auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a9110-127">If you want the same per-user client version policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="a9110-128">Führen Sie in **Richtlinien zuweisen**unter **Client Versionsrichtlinie**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a9110-128">In **Assign Policies**, under **Client version policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="a9110-129">Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds <STRONG>Richtlinien zuweisen</STRONG> konfigurieren können, ist für jede Richtlinie im Dialogfeld standardmäßig <STRONG> &lt; &gt; beizubehalten</STRONG> aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a9110-129">Because there are multiple policies that you can configure by using the <STRONG>Assign Policies</STRONG> dialog box, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="a9110-130">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="a9110-130">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="a9110-131">Zulassen, dass lync Server automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Standortebene oder auf Poolebene auswählen.</span><span class="sxs-lookup"><span data-stu-id="a9110-131">Allow Lync Server to automatically choose either the global-level policy or, if defined, the site-level policy or pool-level policy.</span></span>
    
      - <span data-ttu-id="a9110-132">Klicken Sie auf der Seite **clientversionsrichtlinie** auf den Namen einer benutzerbasierten clientversionsrichtlinie, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="a9110-132">Click the name of a per-user client version policy you previously defined on the **Client Version Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="a9110-133">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a9110-133">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="a9110-134">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9110-134">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a9110-135">Zuweisen einer Per-User Client-Versionsrichtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a9110-135">Assigning a Per-User Client Version Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a9110-136">Sie können benutzerbasierte clientversionsrichtlinien mithilfe des Grant-CsClientVersionPolicy-Cmdlets zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a9110-136">You can assign per-user client version policies by using the Grant-CsClientVersionPolicy cmdlet.</span></span> <span data-ttu-id="a9110-137">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="a9110-137">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a9110-138">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a9110-138">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a><span data-ttu-id="a9110-139">So weisen Sie einem einzelnen Benutzer eine clientversionsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="a9110-139">To assign a per-user client version policy to a single user</span></span>

  - <span data-ttu-id="a9110-140">Mit dem folgenden Befehl wird dem Benutzer Ken Myers die clientversionsrichtlinie für die benutzerspezifische RedmondClientVersionPolicy zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a9110-140">The following command assigns the per-user client version policy RedmondClientVersionPolicy to the user Ken Myer.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a><span data-ttu-id="a9110-141">So weisen Sie mehreren Benutzern eine clientversionsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="a9110-141">To assign a per-user client version policy to multiple users</span></span>

  - <span data-ttu-id="a9110-142">Mit diesem Befehl wird die benutzerbasierte clientversionsrichtlinie RedmondClientVersionPolicy allen Benutzern zugewiesen, denen derzeit die VoIP-Richtlinie "redmondvoicepolicy" zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a9110-142">This command assigns the per-user client version policy RedmondClientVersionPolicy to all the users who are currently assigned the voice policy RedmondVoicePolicy.</span></span> <span data-ttu-id="a9110-143">Weitere Informationen zum in diesem Befehl verwendeten Filter-Parameter finden Sie in der Dokumentation zum Cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="a9110-143">For more information on the Filter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a><span data-ttu-id="a9110-144">So heben Sie die Zuweisung einer clientversionsrichtlinie pro Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="a9110-144">To unassign a per-user client version policy</span></span>

  - <span data-ttu-id="a9110-145">Mit dem folgenden Befehl wird die Zuweisung einer clientversionsrichtlinie für einzelne Benutzer aufgehoben, die Ken Myers zuvor zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="a9110-145">The following command unassigns any per-user client version policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="a9110-146">Nachdem die Zuweisung der benutzerbezogenen Richtlinie aufgehoben wurde, wird Ken Myers automatisch mithilfe der globalen Richtlinie, seiner lokalen Standortrichtlinie (sofern vorhanden) oder der seiner Registrierungsstelle zugewiesenen Dienstbereichs Richtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a9110-146">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy, his local site policy (if one exists), or the service-scope policy assigned to his Registrar.</span></span> <span data-ttu-id="a9110-147">Eine Dienstbereichs Richtlinie hat Vorrang vor jeder Standortrichtlinie, und eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="a9110-147">A service scope policy takes precedence over any site policy, and a site policy takes precedence over the global policy.</span></span>
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="a9110-148">Weitere Informationen finden Sie im Hilfethema zum [Grant-CsClientVersionPolicy-](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a9110-148">For more information, see the help topic for the [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9110-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9110-149">See Also</span></span>


[<span data-ttu-id="a9110-150">Zuweisen von Richtlinien pro Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9110-150">Assigning per-user policies in Lync Server 2013</span></span>](lync-server-2013-assigning-per-user-policies.md)  
[<span data-ttu-id="a9110-151">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9110-151">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)

