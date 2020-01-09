---
title: Zuweisen einer pro-Benutzer-PIN-Richtlinie in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d8211c64-0b63-4193-a074-673da7d14287
description: 'Zusammenfassung: Stage AV-und OAuth-Zertifikate für Skype for Business Server.'
ms.openlocfilehash: 7591464d55970a9aee4fb1f7ddbb28c2efbac601
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992722"
---
# <a name="assign-a-per-user-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="2ecf2-103">Zuweisen einer pro-Benutzer-PIN-Richtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ecf2-103">Assign a per-user PIN policy in Skype for Business Server</span></span>

<span data-ttu-id="2ecf2-104">**Zusammenfassung:** Stage AV-und OAuth-Zertifikate für Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-104">**Summary:** Stage AV and OAuth certificates for Skype for Business Server.</span></span>
  
<span data-ttu-id="2ecf2-105">Die Richtlinie für Einwahlkonferenzen (persönliche Identifikationsnummer) ist eine der individuellen Einstellungen eines Benutzerkontos, das in der Skype for Business Server-Systemsteuerung konfiguriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-105">The dial-in conferencing personal identification number (PIN) policy is one of the individual settings of a user account that can be configured in the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="2ecf2-p101">Die Bereitstellung einer oder mehrerer PIN-Richtlinien auf Benutzerebene ist optional. Sie können stattdessen auch nur eine globale PIN-Richtlinie oder eine PIN-Richtlinie auf Standortebene bereitstellen. Wenn Sie Richtlinien auf Benutzerebene bereitstellen, müssen Sie sie Benutzern, Gruppen oder Kontaktobjekten explizit zuweisen. Wenn keine Richtlinie für den Standort oder einzelne Benutzer zugewiesen wurde, gelten automatisch die Benutzerrechte und Berechtigungen im Hinblick auf die Verwendung von PINs für Einwahlkonferenzen, die in der globalen PIN-Richtlinie definiert sind.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-p101">Deploying one or more per-user PIN policies is optional. You can also deploy only a global-level PIN policy or site-level PIN policy. If you do deploy per-user policies, you must explicitly assign them to users, groups, or contact object. User rights and permissions regarding the use of PINs for dial-in conferencing automatically default to those defined in the global-level PIN policy when no specific site-level or per-user policy is assigned.</span></span>
  
<span data-ttu-id="2ecf2-110">Nachdem Sie mindestens eine PIN-Richtlinie auf Benutzerebene erstellt haben, weisen Sie sie mithilfe der Verfahren in diesem Thema zu. Die zugewiesene Richtlinie gibt die Einschränkungen an, die der Server auf die PIN-Erstellung und -Verwendung durch einen bestimmten Benutzer anwenden soll.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-110">After creating at least one per-user PIN policy, use the procedures in this topic to assign the policy that specifies the constraints you want the server to impose on the PINs created by and used by a particular user.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy"></a><span data-ttu-id="2ecf2-111">So weisen Sie eine PIN-Richtlinie auf Benutzerebene zu</span><span class="sxs-lookup"><span data-stu-id="2ecf2-111">To assign a per-user PIN policy</span></span>

1. <span data-ttu-id="2ecf2-112">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2ecf2-113">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-113">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="2ecf2-114">Klicken Sie in der linken Navigationsleiste auf **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-114">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="2ecf2-115">Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:</span><span class="sxs-lookup"><span data-stu-id="2ecf2-115">Use one of the following methods to locate a user:</span></span>
    
   - <span data-ttu-id="2ecf2-116">Geben Sie im Feld **Benutzer suchen** den vollständigen oder teilweisen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-116">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account, and then click **Find**.</span></span>
    
   - <span data-ttu-id="2ecf2-117">Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-117">If you have a saved query, click the **Open query** icon, use the **Open** dialog box to retrieve the query (a .usf file), and then click **Find**.</span></span>
    
5. <span data-ttu-id="2ecf2-118">(Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse einzuschränken:</span><span class="sxs-lookup"><span data-stu-id="2ecf2-118">(Optional) Specify additional search criteria to narrow the results:</span></span>
    
   <span data-ttu-id="2ecf2-119">a.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-119">a.</span></span> <span data-ttu-id="2ecf2-120">Klicken Sie auf **Filter hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-120">Click **Add Filter**.</span></span>
    
   <span data-ttu-id="2ecf2-121">b.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-121">b.</span></span> <span data-ttu-id="2ecf2-122">Geben Sie die Benutzereigenschaft ein, indem Sie sie über die Tastatur eintippen oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-122">Enter the user property by typing it or by clicking the arrow in the drop-down list to select the property.</span></span>
    
   <span data-ttu-id="2ecf2-123">c.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-123">c.</span></span> <span data-ttu-id="2ecf2-124">Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).</span><span class="sxs-lookup"><span data-stu-id="2ecf2-124">In the **Equal to** drop-down list, click the operator (for example, **Equal to** or **Not equal to**).</span></span>
    
   <span data-ttu-id="2ecf2-125">d.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-125">d.</span></span> <span data-ttu-id="2ecf2-126">Geben Sie je nach gewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein oder klicken Sie auf den Pfeil in der Dropdownliste.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-126">Depending on the user property you selected, enter the criteria you want to use to filter the search results by typing it or by clicking the arrow in the drop-down list.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2ecf2-127">Klicken Sie auf **Filter hinzufügen**, um zusätzliche Suchklauseln einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-127">To add additional search clauses to your query, click **Add Filter**.</span></span> 
  
   <span data-ttu-id="2ecf2-128">e.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-128">e.</span></span> <span data-ttu-id="2ecf2-129">Klicken Sie auf **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-129">Click **Find**.</span></span>
    
6. <span data-ttu-id="2ecf2-130">Klicken Sie in den Suchergebnissen auf einen Benutzer, klicken Sie auf **Aktion** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-130">Click a user in the search results, click **Action**, and then click **Assign policies**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="2ecf2-131">Wenn Sie dieselbe PIN-Richtlinie auf mehrere Benutzer anwenden möchten, wählen Sie mehrere Benutzer in den Suchergebnissen aus, klicken Sie auf **Aktionen** und anschließend auf **Richtlinien zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-131">If you want the same per-user PIN policy to apply to multiple users, select multiple users in the search results, then click **Actions**, and then click **Assign policies**.</span></span> 
  
7. <span data-ttu-id="2ecf2-132">Führen Sie im Abschnitt **Richtlinien zuweisen** unter **PIN-Richtlinie** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2ecf2-132">In **Assign Policies**, under **PIN policy**, do one of the following:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="2ecf2-133">Da es mehrere Richtlinien gibt, die Sie mithilfe des Dialogfelds **Richtlinien zuweisen** konfigurieren \*\* \<\> \*\* können, ist für jede Richtlinie im Dialogfeld standardmäßig beibehalten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-133">Because there are multiple policies that you can configure by using the **Assign Policies** dialog box, **\<Keep as is\>** is selected by default for every policy in the dialog box.</span></span> <span data-ttu-id="2ecf2-134">Wenn Sie an dieser Einstellung keine Änderung vornehmen, wird eine zuvor zugewiesene Richtlinie weiterhin auf den Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-134">Continue using the policy previously assigned to the user by making no changes to this setting.</span></span>
  
   - <span data-ttu-id="2ecf2-135">Erlauben Sie Skype for Business Server, automatisch entweder die Richtlinie auf globaler Ebene oder, falls definiert, die Richtlinie auf Websiteebene zu wählen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-135">Allow Skype for Business Server to automatically choose either the global-level policy or, if defined, the site-level policy.</span></span>
    
   - <span data-ttu-id="2ecf2-136">Klicken Sie auf der Seite **PIN-Richtlinie** auf den Namen einer PIN-Richtlinie auf Benutzerebene, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-136">Click the name of a per-user PIN policy you previously defined on the **PIN Policy** page.</span></span>
    
     > [!TIP]
     > <span data-ttu-id="2ecf2-137">Um besser entscheiden zu können, welche Richtlinie zugewiesen werden soll, klicken Sie auf einen Richtliniennamen und anschließend auf **Anzeigen**, um die in der Richtlinie definierten Benutzerrechte und -berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-137">To help you decide the policy you want to assign, after you click a policy name, click **View** to view the user rights and permissions defined in the policy.</span></span>
  
8. <span data-ttu-id="2ecf2-138">Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-138">When you are finished, click **OK**.</span></span>
    
## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2ecf2-139">Zuweisen einer pro-Benutzer-PIN-Richtlinie mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2ecf2-139">Assigning a Per-User PIN Policy by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2ecf2-140">Sie können benutzerspezifische PIN-Richtlinien mithilfe von Windows PowerShell und dem Cmdlet **Grant-CsPinPolicy** zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-140">You can assign per-user PIN policies by using Windows PowerShell and the **Grant-CsPinPolicy** cmdlet.</span></span> <span data-ttu-id="2ecf2-141">Sie können dieses Cmdlet über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-141">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2ecf2-142">Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="2ecf2-142">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="2ecf2-143">Der Vorgang ist in Skype for Business Server identisch.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-143">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a><span data-ttu-id="2ecf2-144">So weisen Sie einem einzelnen Benutzer eine benutzerbasierte PIN-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="2ecf2-144">To assign a per-user PIN policy to a single user</span></span>

- <span data-ttu-id="2ecf2-145">Mit dem folgenden Befehl wird die benutzerbasierte PIN-Richtlinie RedmondPinPolicy dem Benutzer Ken Myer zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-145">The following command assigns the per-user PIN policy RedmondPinPolicy to the user Ken Myer.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"
  ```

### <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a><span data-ttu-id="2ecf2-146">So weisen Sie mehreren Benutzern eine benutzerbasierte PIN-Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="2ecf2-146">To assign a per-user PIN policy to multiple users</span></span>

- <span data-ttu-id="2ecf2-147">Mit dem folgenden Befehl wird die benutzerbasierte Richtlinie RedmondUsersPinPolicy allen Benutzern in der Stadt Redmond zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-147">The following command assigns the per-user PIN policy RedmondUsersPinPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="2ecf2-148">Details zu dem in diesem Befehl verwendeten LdapFilter-Parameter finden Sie unter [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2ecf2-148">For details about the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```PowerShell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"
  ```

### <a name="to-unassign-a-per-user-pin-policy"></a><span data-ttu-id="2ecf2-149">So heben Sie die Zuweisung einer benutzerbasierten PIN-Richtlinie auf</span><span class="sxs-lookup"><span data-stu-id="2ecf2-149">To unassign a per-user PIN policy</span></span>

- <span data-ttu-id="2ecf2-p110">Mit dem folgenden Befehl wird jede benutzerbasierte PIN-Richtlinie, die zuvor Ken Myer zugewiesen wurde, aufgehoben. Anschließend wird Ken Myer automatisch mithilfe der globalen Richtlinie oder, soweit vorhanden, mit seiner lokalen Standortrichtlinie verwaltet. Eine Standortrichtlinie hat Vorrang vor der globalen Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="2ecf2-p110">The following command unassigns any per-user PIN policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
  ```PowerShell
  Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

<span data-ttu-id="2ecf2-153">Ausführliche Informationen finden Sie unter [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2ecf2-153">For details, see [Grant-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cspinpolicy?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2ecf2-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ecf2-154">See also</span></span>

[<span data-ttu-id="2ecf2-155">Erstellen einer neuen PIN-Richtlinie in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2ecf2-155">Create a new PIN policy in Skype for Business Server</span></span>](create-a-new-pin-policy.md)
