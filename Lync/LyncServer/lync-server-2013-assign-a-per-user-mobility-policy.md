---
title: 'Lync Server 2013: Zuweisen einer Mobilitätsrichtlinie für einzelne Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20b5929959e87f4a39c69ab09f7836a471e16b66
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722845"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="06b16-102">Zuweisen einer Mobilitätsrichtlinie für einzelne Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b16-102">Assign a per-user mobility policy in Lync Server 2013</span></span>

 


<span data-ttu-id="06b16-103">Die Mobilitätsrichtlinie ist eine der individuellen Einstellungen eines Benutzerkontos, das Sie in der lync Server-Systemsteuerung oder in der lync Server-Verwaltungsshell konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="06b16-103">The mobility policy is one of the individual settings of a user account that you can configure in Lync Server Control Panel or Lync Server Management Shell.</span></span>

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="06b16-104">So weisen Sie eine Mobilitätsrichtlinie für einzelne Benutzer mit der lync Server-Systemsteuerung zu</span><span class="sxs-lookup"><span data-stu-id="06b16-104">To assign a per-user mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="06b16-105">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="06b16-105">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="06b16-106">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="06b16-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="06b16-107">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="06b16-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="06b16-108">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="06b16-108">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="06b16-109">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="06b16-109">Use one of the following methods to locate a user:</span></span>
    
      - <span data-ttu-id="06b16-110">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="06b16-110">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
      - <span data-ttu-id="06b16-111">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="06b16-111">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>

5.  <span data-ttu-id="06b16-112">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="06b16-112">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
    1.  <span data-ttu-id="06b16-113">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="06b16-113">Click **Add Filter**.</span></span>
    
    2.  <span data-ttu-id="06b16-114">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="06b16-114">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
    3.  <span data-ttu-id="06b16-115">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="06b16-115">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
    4.  <span data-ttu-id="06b16-116">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="06b16-116">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="06b16-117">Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="06b16-117">To add additional search clauses to your query, click <STRONG>Add Filter</STRONG>.</span></span>

    
    5.  <span data-ttu-id="06b16-118">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="06b16-118">Click **Find**.</span></span>

6.  <span data-ttu-id="06b16-119">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="06b16-119">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    

    > [!TIP]  
    > <span data-ttu-id="06b16-120">Wenn dieselbe Mobilitätsrichtlinie für einzelne Benutzer für mehrere Benutzer gelten soll, wählen Sie in den Suchergebnissen mehrere Benutzer aus, klicken Sie dann auf <STRONG>Aktionen</STRONG>, und klicken Sie dann auf <STRONG>Richtlinien zuweisen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="06b16-120">If you want the same per-user mobility policy to apply to multiple users, select multiple users in the search results, then click <STRONG>Actions</STRONG>, and then click <STRONG>Assign policies</STRONG>.</span></span>



7.  <span data-ttu-id="06b16-121">Führen Sie in **Richtlinien zuweisen**unter **Mobilitätsrichtlinie**eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="06b16-121">In **Assign Policies**, under **Mobility policy**, do one of the following:</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="06b16-122">Da es mehrere Richtlinien gibt, die Sie unter <STRONG>Zuweisen von Richtlinien</STRONG>konfigurieren können, <STRONG> &lt;&gt; </STRONG> ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="06b16-122">Because there are multiple policies that you can configure in <STRONG>Assign Policies</STRONG>, <STRONG>&lt;Keep as is&gt;</STRONG> is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="06b16-123">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="06b16-123">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>

    
      - <span data-ttu-id="06b16-124">Wählen \*\* \<Sie\> automatisch\*\* aus, damit lync Server 2013 automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="06b16-124">Select **\<Automatic\>** to allow Lync Server 2013 to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
      - <span data-ttu-id="06b16-125">Klicken Sie auf den Namen der benutzerdefinierten Mobilitätsrichtlinie, die Sie zuvor auf der Seite **Mobilitätsrichtlinie** definiert haben.</span><span class="sxs-lookup"><span data-stu-id="06b16-125">Click the name of a per-user mobility policy you previously defined on the **Mobility Policy** page.</span></span>
        

        > [!TIP]  
        > <span data-ttu-id="06b16-126">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf <STRONG>Anzeigen</STRONG>, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="06b16-126">To help you decide the policy you want to assign, after you click a policy name, click <STRONG>View</STRONG> to view the user rights and permissions defined in the policy.</span></span>



8.  <span data-ttu-id="06b16-127">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="06b16-127">When you are finished, click **OK**.</span></span>

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="06b16-128">Zuweisen einer Mobilitätsrichtlinie für einzelne Benutzer mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="06b16-128">Assigning a Per-User Mobility Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="06b16-129">Sie können mobilitätsrichtlinien für einzelne Benutzer mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsMobilityPolicy** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="06b16-129">You can assign per-user mobility policies by using Windows PowerShell and the **Grant-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="06b16-130">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="06b16-130">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="06b16-131">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="06b16-131">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a><span data-ttu-id="06b16-132">So weisen Sie einem einzelnen Benutzer eine Mobilitätsrichtlinie pro Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="06b16-132">To assign a per-user mobility policy to a single user</span></span>

  - <span data-ttu-id="06b16-133">Mit dem folgenden Befehl wird die benutzerspezifische mobilitätsrichtlinien-RedmondMobilityPolicy dem Benutzer Ken Myers zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="06b16-133">The following command assigns the per-user mobility policy RedmondMobilityPolicy to the user Ken Myer.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a><span data-ttu-id="06b16-134">So weisen Sie mehreren Benutzern eine Mobilitätsrichtlinie für einzelne Benutzer zu</span><span class="sxs-lookup"><span data-stu-id="06b16-134">To assign a per-user mobility policy to multiple users</span></span>

  - <span data-ttu-id="06b16-135">Mit dem folgenden Befehl werden die benutzerbezogenen mobilitätsrichtlinien RedmondMobilityPolicy allen Benutzern zugewiesen, denen zurzeit die Richtlinien NorthAmericaMobilityPolicy zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="06b16-135">The following command assigns the per-user mobility policy RedmondMobilityPolicy to all the users who are currently assigned the policy NorthAmericaMobilityPolicy.</span></span> <span data-ttu-id="06b16-136">Details zu dem in diesem Befehl verwendeten Filter Parameter finden Sie unter [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="06b16-136">For details about the Filter parameter used in this command, see [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).</span></span>
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a><span data-ttu-id="06b16-137">So heben Sie die Zuweisung einer Mobilitätsrichtlinie für einzelne Benutzer auf</span><span class="sxs-lookup"><span data-stu-id="06b16-137">To unassign a per-user mobility policy</span></span>

  - <span data-ttu-id="06b16-138">Mit dem folgenden Befehl werden alle benutzerbezogenen mobilitätsrichtlinien, die Ken Myers zuvor zugewiesen wurden, aufheben.</span><span class="sxs-lookup"><span data-stu-id="06b16-138">The following command unassigns any per-user mobility policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="06b16-139">Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet.</span><span class="sxs-lookup"><span data-stu-id="06b16-139">After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy.</span></span> <span data-ttu-id="06b16-140">Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="06b16-140">A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="06b16-141">Ausführliche Informationen finden Sie unter [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="06b16-141">For details, see [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).</span></span>

## <a name="see-also"></a><span data-ttu-id="06b16-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="06b16-142">See Also</span></span>


[<span data-ttu-id="06b16-143">Konfigurieren der Mobilitätsrichtlinie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06b16-143">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)

