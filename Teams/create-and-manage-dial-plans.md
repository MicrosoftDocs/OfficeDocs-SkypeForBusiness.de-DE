---
title: Erstellen und Verwalten von Wählplänen
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Informationen zum Erstellen und Verwalten von Wählplänen für Anrufe (PSTN-Wählpläne) und deren Verwaltung.
ms.openlocfilehash: 774b0a78f39b91b634ed0833be3497935cb25c4f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826923"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="45752-103">Erstellen und Verwalten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="45752-103">Create and manage dial plans</span></span>

<span data-ttu-id="45752-104">Nachdem Sie die Wählpläne für Ihre Organisation geplant und alle Normalisierungsregeln herausgefunden haben, die für das Anrufrouting erstellt werden müssen, können Sie die Wählpläne erstellen.</span><span class="sxs-lookup"><span data-stu-id="45752-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="45752-105">Sie können das Microsoft Teams Admin Center oder Windows PowerShell verwenden, um Wählpläne zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="45752-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="45752-106">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="45752-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="45752-107">Erstellen eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="45752-107">Create a dial plan</span></span>

1. <span data-ttu-id="45752-108">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach** > **Wähl**Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="45752-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="45752-109">Klicken Sie auf **Hinzufügen**, und geben Sie dann einen Namen und eine Beschreibung für den Wählplan ein.</span><span class="sxs-lookup"><span data-stu-id="45752-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="45752-110">![Screenshot der Seite "hinzufügen" zum Erstellen eines Wählplans](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="45752-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="45752-111">Geben Sie unter **Wähl Plan Details**eine externe Wähl Vorwahl an, wenn Benutzer eine oder mehrere zusätzliche führende stellen (beispielsweise 9) wählen müssen, um eine externe Leitung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="45752-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="45752-112">Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="45752-112">To do this:</span></span>
    1. <span data-ttu-id="45752-113">Geben Sie im Feld **externe Wähl Vorwahl** eine externe Wähl Vorwahl ein.</span><span class="sxs-lookup"><span data-stu-id="45752-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="45752-114">Das Präfix kann bis zu vier Zeichen (#, \* und 0-9) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="45752-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="45752-115">Aktivieren Sie die **optimierte Gerätewahl**.</span><span class="sxs-lookup"><span data-stu-id="45752-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="45752-116">Wenn Sie eine externe Wähl Vorwahl angeben, müssen Sie auch diese Einstellung aktivieren, um das Präfix anzuwenden, damit Anrufe außerhalb Ihrer Organisation getätigt werden können.</span><span class="sxs-lookup"><span data-stu-id="45752-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="45752-117">Konfigurieren und verknüpfen Sie unter **Normalisierungsregeln**eine oder mehrere [Normalisierungsregeln](what-are-dial-plans.md#normalization-rules) für den Wählplan.</span><span class="sxs-lookup"><span data-stu-id="45752-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="45752-118">Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="45752-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="45752-119">Führen Sie dazu eine oder mehrere der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="45752-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="45752-120">Wenn Sie eine neue Normalisierungsregel erstellen und dem Wählplan zuordnen möchten, klicken Sie auf **Hinzufügen**, und definieren Sie die Regel.</span><span class="sxs-lookup"><span data-stu-id="45752-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="45752-121">Wenn Sie eine Normalisierungsregel bearbeiten möchten, die dem Wählplan bereits zugeordnet ist, wählen Sie die Regel aus, indem Sie links neben dem Regelnamen klicken, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45752-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="45752-122">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45752-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="45752-123">Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, wählen Sie die Regel aus, indem Sie links neben dem Regelnamen klicken, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="45752-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="45752-124">Ordnen Sie die Normalisierungsregeln in der gewünschten Reihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="45752-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="45752-125">Klicken Sie auf nach **oben** oder nach **unten** , um die Position der Regeln in der Liste zu ändern.</span><span class="sxs-lookup"><span data-stu-id="45752-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="45752-126">Teams durchlaufen die Liste der Normalisierungsregeln von oben nach unten und verwenden die erste Regel, die der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="45752-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="45752-127">Wenn Sie einen Wählplan so einrichten, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, stellen Sie sicher, dass die restriktiveren Regeln über die weniger restriktiven Regeln sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="45752-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="45752-128">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45752-128">Click **Save**.</span></span>
7. <span data-ttu-id="45752-129">Wenn Sie den Wählplan testen möchten, geben Sie unter **Wähleinstellungen testen**eine Telefonnummer ein, und klicken Sie dann auf **Testen**.</span><span class="sxs-lookup"><span data-stu-id="45752-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="45752-130">Bearbeiten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="45752-130">Edit a dial plan</span></span>

1. <span data-ttu-id="45752-131">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach** > **Wähl**Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="45752-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="45752-132">Wählen Sie den Wählplan aus, indem Sie links neben dem Namen des Wählplans klicken, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="45752-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="45752-133">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="45752-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="add-users-to-a-dial-plan"></a><span data-ttu-id="45752-134">Hinzufügen von Benutzern zu einem Wählplan</span><span class="sxs-lookup"><span data-stu-id="45752-134">Add users to a dial plan</span></span>

1. <span data-ttu-id="45752-135">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach** > **Wähl**Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="45752-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="45752-136">Wählen Sie den Wählplan aus, indem Sie links neben dem Namen des Wählplans klicken.</span><span class="sxs-lookup"><span data-stu-id="45752-136">Select the dial plan by clicking to the left of the dial plan name.</span></span>
3. <span data-ttu-id="45752-137">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="45752-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="45752-138">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="45752-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="45752-139">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="45752-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="45752-140">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie über **nehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="45752-140">When you're finished adding users, select **Apply**.</span></span>

## <a name="using-powershell"></a><span data-ttu-id="45752-141">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="45752-141">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="45752-142">Überprüfen und starten von Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="45752-142">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="45752-143">**Überprüfen Sie, ob Sie Windows PowerShell, Version 3,0 oder höher, ausführen.**</span><span class="sxs-lookup"><span data-stu-id="45752-143">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="45752-144">So überprüfen Sie, ob Sie Version 3,0 oder höher ausführen: **Startmenü** > von**Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="45752-144">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="45752-145">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="45752-145">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="45752-146">Wenn Sie nicht über Version 3,0 oder höher verfügen, laden Sie Updates für Windows PowerShell herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="45752-146">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="45752-147">Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="45752-147">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="45752-148">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="45752-148">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="45752-149">Außerdem müssen Sie das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="45752-149">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="45752-150">Sie können dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, im [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="45752-150">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="45752-151">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="45752-151">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="45752-152">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="45752-152">To learn more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="45752-153">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="45752-153">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="45752-154">Klicken Sie auf**Windows PowerShell** **starten** > .</span><span class="sxs-lookup"><span data-stu-id="45752-154">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="45752-155">Stellen Sie im Fenster **Windows PowerShell** eine Verbindung mit Ihrer Office 365-Organisation her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="45752-155">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="45752-156">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="45752-156">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="45752-157">Erstellen und Verwalten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="45752-157">Create and manage your dial plans</span></span>

<span data-ttu-id="45752-158">Sie können entweder ein einzelnes Cmdlet oder ein PowerShell-Skript verwenden, um Mandanten-Wählpläne zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="45752-158">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="45752-159">Verwenden einzelner Cmdlets</span><span class="sxs-lookup"><span data-stu-id="45752-159">Using single cmdlets</span></span>

- <span data-ttu-id="45752-160">Wenn Sie einen neuen Wählplan erstellen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="45752-160">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="45752-161">Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="45752-161">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="45752-162">Um die Einstellungen eines vorhandenen Wählplans zu bearbeiten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="45752-162">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="45752-163">Weitere Beispiele und Parameter finden Sie unter [Satz-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="45752-163">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="45752-164">Führen Sie Folgendes aus, um Benutzer zu einem Wählplan hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="45752-164">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="45752-165">Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="45752-165">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="45752-166">Führen Sie die folgenden Optionen aus, um die Einstellungen für einen Wählplan anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="45752-166">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="45752-167">Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="45752-167">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="45752-168">Um einen Wählplan zu löschen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="45752-168">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="45752-169">Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="45752-169">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="45752-170">Um die Einstellungen des effektiven Wählplans anzuzeigen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="45752-170">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="45752-171">Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="45752-171">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="45752-172">Um die effektiven Einstellungen eines Wählplans zu testen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="45752-172">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="45752-173">Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="45752-173">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="45752-174">Verwenden eines PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="45752-174">Using a PowerShell script</span></span>

<span data-ttu-id="45752-175">Führen Sie diese Aktion aus, um eine Normalisierungsregel zu löschen, die einem Mandanten Wählplan zugeordnet ist, ohne zuerst den Mandanten Wähl Plan löschen zu müssen:</span><span class="sxs-lookup"><span data-stu-id="45752-175">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="45752-176">Führen Sie diese Schritte aus, um die folgende Normalisierungsregel zum vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="45752-176">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="45752-177">Führen Sie diese Option aus, um die folgende Normalisierungsregel aus dem vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="45752-177">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="45752-178">Führen Sie die folgenden Schritte aus, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, ermitteln möchten, welche Sie löschen möchten, und dann deren Index verwenden, um Sie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="45752-178">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="45752-179">Das Array von Normalisierungsregeln beginnt mit Index 0.</span><span class="sxs-lookup"><span data-stu-id="45752-179">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="45752-180">Wir möchten die dreistellige Normalisierungsregel entfernen, also Index 1.</span><span class="sxs-lookup"><span data-stu-id="45752-180">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="45752-181">Führen Sie diese Aktion aus, um alle Benutzer zu finden, denen der redmonddialplan "-Mandanten Wählplan gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="45752-181">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="45752-182">Führen Sie diesen Vorgang aus, um alle zugewiesenen TenantDialPlan von allen Benutzern zu entfernen, die über einen Hostinganbieter von sipfed.online.lync.com verfügen.</span><span class="sxs-lookup"><span data-stu-id="45752-182">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="45752-183">Führen Sie diese aus, um den vorhandenen lokalen Wählplan mit dem Namen OPDP1 als Mandanten Wähl Plan für Ihre Organisation hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="45752-183">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="45752-184">Sie müssen den lokalen Wählplan zunächst in einer XML-Datei speichern und dann zum Erstellen des neuen Mandanten Wähl Plans verwenden.</span><span class="sxs-lookup"><span data-stu-id="45752-184">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="45752-185">Führen Sie diese Aktion aus, um den lokalen Wählplan in der XML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="45752-185">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="45752-186">Führen Sie diese Aktion aus, um den neuen Mandanten Wählplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="45752-186">Run this to create the new tenant dial plan.</span></span>
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a><span data-ttu-id="45752-187">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="45752-187">Related topics</span></span>

- [<span data-ttu-id="45752-188">Was sind Wählpläne?</span><span class="sxs-lookup"><span data-stu-id="45752-188">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="45752-189">Übertragen von Telefonnummern – häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="45752-189">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="45752-190">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="45752-190">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="45752-191">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="45752-191">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="45752-192">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="45752-192">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="45752-193">[Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="45752-193">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="45752-194">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="45752-194">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
