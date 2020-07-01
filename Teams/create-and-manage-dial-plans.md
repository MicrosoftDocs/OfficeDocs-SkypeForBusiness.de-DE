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
- seo-marvel-apr2020
description: Hier erfahren Sie, wie Sie das Microsoft Teams Admin Center oder Windows PowerShell zum Erstellen und Verwalten von Wählplänen (PSTN-Wählpläne) verwenden.
ms.openlocfilehash: 0e5f45ecdb92843a77bd7a957b1b7c31b3403b92
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938234"
---
# <a name="create-and-manage-dial-plans"></a><span data-ttu-id="0de0c-103">Erstellen und Verwalten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="0de0c-103">Create and manage dial plans</span></span>

<span data-ttu-id="0de0c-104">Nachdem Sie die Wählpläne für Ihre Organisation geplant und alle Normalisierungsregeln herausgefunden haben, die für das Anrufrouting erstellt werden müssen, können Sie die Wählpläne erstellen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-104">After you plan the dial plans for your organization and figured out all the normalization rules that need to be created for call routing, you're ready to create the dial plans.</span></span> <span data-ttu-id="0de0c-105">Sie können das Microsoft Teams Admin Center oder Windows PowerShell verwenden, um Wählpläne zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0de0c-105">You can use the Microsoft Teams admin center or Windows PowerShell to create and manage dial plans.</span></span>  

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="0de0c-106">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="0de0c-106">Using the Microsoft Teams admin center</span></span>

### <a name="create-a-dial-plan"></a><span data-ttu-id="0de0c-107">Erstellen eines Wählplans</span><span class="sxs-lookup"><span data-stu-id="0de0c-107">Create a dial plan</span></span>

1. <span data-ttu-id="0de0c-108">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach**  >  **Wähl**Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-108">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="0de0c-109">Klicken Sie auf **Hinzufügen**, und geben Sie dann einen Namen und eine Beschreibung für den Wählplan ein.</span><span class="sxs-lookup"><span data-stu-id="0de0c-109">Click **Add**, and then enter a name and description for the dial plan.</span></span>
    <span data-ttu-id="0de0c-110">![Screenshot der Seite "hinzufügen" zum Erstellen eines Wählplans](media/create-dial-plan.png)</span><span class="sxs-lookup"><span data-stu-id="0de0c-110">![Screenshot showing the Add page for creating a dial plan](media/create-dial-plan.png)</span></span>
3. <span data-ttu-id="0de0c-111">Geben Sie unter **Wähl Plan Details**eine externe Wähl Vorwahl an, wenn Benutzer eine oder mehrere zusätzliche führende stellen (beispielsweise 9) wählen müssen, um eine externe Leitung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0de0c-111">Under **Dial plan details**, specify an external dialing prefix if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span> <span data-ttu-id="0de0c-112">Gehen Sie dazu so vor:</span><span class="sxs-lookup"><span data-stu-id="0de0c-112">To do this:</span></span>
    1. <span data-ttu-id="0de0c-113">Geben Sie im Feld **externe Wähl Vorwahl** eine externe Wähl Vorwahl ein.</span><span class="sxs-lookup"><span data-stu-id="0de0c-113">In the **External dialing prefix** box, enter an external dialing prefix.</span></span> <span data-ttu-id="0de0c-114">Das Präfix kann bis zu vier Zeichen (#, \* und 0-9) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-114">The prefix can be up to four characters (#,\*, and 0-9).</span></span>
    2. <span data-ttu-id="0de0c-115">Aktivieren Sie die **optimierte Gerätewahl**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-115">Turn on **Optimized device dialing**.</span></span> <span data-ttu-id="0de0c-116">Wenn Sie eine externe Wähl Vorwahl angeben, müssen Sie auch diese Einstellung aktivieren, um das Präfix anzuwenden, damit Anrufe außerhalb Ihrer Organisation getätigt werden können.</span><span class="sxs-lookup"><span data-stu-id="0de0c-116">If you specify an external dialing prefix, you must also turn on this setting to apply the prefix so calls can be made outside your organization.</span></span>
4. <span data-ttu-id="0de0c-117">Konfigurieren und verknüpfen Sie unter **Normalisierungsregeln**eine oder mehrere [Normalisierungsregeln](what-are-dial-plans.md#normalization-rules) für den Wählplan.</span><span class="sxs-lookup"><span data-stu-id="0de0c-117">Under **Normalization rules**, configure and associate one or more [normalization rules](what-are-dial-plans.md#normalization-rules) for the dial plan.</span></span> <span data-ttu-id="0de0c-118">Jedem Wählplan muss mindestens eine Normalisierungsregel zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="0de0c-118">Each dial plan must have at least one normalization rule associated with it.</span></span>  <span data-ttu-id="0de0c-119">Führen Sie dazu eine oder mehrere der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0de0c-119">To do this, do one or more of the following:</span></span>
    - <span data-ttu-id="0de0c-120">Wenn Sie eine neue Normalisierungsregel erstellen und dem Wählplan zuordnen möchten, klicken Sie auf **Hinzufügen**, und definieren Sie die Regel.</span><span class="sxs-lookup"><span data-stu-id="0de0c-120">To create a new normalization rule and associate it with the dial plan, click **Add**, and then define the rule.</span></span>
    - <span data-ttu-id="0de0c-121">Wenn Sie eine Normalisierungsregel bearbeiten möchten, die dem Wählplan bereits zugeordnet ist, wählen Sie die Regel aus, indem Sie links neben dem Regelnamen klicken, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-121">To edit a normalization rule that's already associated with the dial plan, select the rule by clicking to the left of the rule name, and then click **Edit**.</span></span> <span data-ttu-id="0de0c-122">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-122">Make the changes you want, and then click **Save**.</span></span>
    - <span data-ttu-id="0de0c-123">Wenn Sie eine Normalisierungsregel aus dem Wählplan entfernen möchten, wählen Sie die Regel aus, indem Sie links neben dem Regelnamen klicken, und klicken Sie dann auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-123">To remove a normalization rule from the dial plan, select the rule by clicking to the left of the rule name, and then click **Remove**.</span></span>
5. <span data-ttu-id="0de0c-124">Ordnen Sie die Normalisierungsregeln in der gewünschten Reihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="0de0c-124">Arrange the normalization rules in the order that you want.</span></span> <span data-ttu-id="0de0c-125">Klicken Sie auf nach **oben** oder nach **unten** , um die Position der Regeln in der Liste zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0de0c-125">Click **Move up** or **Move down** to change the position of rules in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0de0c-126">Teams durchlaufen die Liste der Normalisierungsregeln von oben nach unten und verwenden die erste Regel, die der gewählten Nummer entspricht.</span><span class="sxs-lookup"><span data-stu-id="0de0c-126">Teams traverses the list of normalization rules from the top down and uses the first rule that matches the dialed number.</span></span> <span data-ttu-id="0de0c-127">Wenn Sie einen Wählplan so einrichten, dass eine gewählte Nummer mit mehr als einer Normalisierungsregel übereinstimmen kann, stellen Sie sicher, dass die restriktiveren Regeln über die weniger restriktiven Regeln sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="0de0c-127">If you set up a dial plan so that a dialed number can match more than one normalization rule, make sure the more restrictive rules are sorted above the less restrictive ones.</span></span>

6. <span data-ttu-id="0de0c-128">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-128">Click **Save**.</span></span>
7. <span data-ttu-id="0de0c-129">Wenn Sie den Wählplan testen möchten, geben Sie unter **Wähleinstellungen testen**eine Telefonnummer ein, und klicken Sie dann auf **Testen**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-129">If you want to test the dial plan, under **Test dial plan**, enter a phone number, and then click **Test**.</span></span>

### <a name="edit-a-dial-plan"></a><span data-ttu-id="0de0c-130">Bearbeiten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="0de0c-130">Edit a dial plan</span></span>

1. <span data-ttu-id="0de0c-131">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **sprach**  >  **Wähl**Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Dial plan**.</span></span>
2. <span data-ttu-id="0de0c-132">Wählen Sie den Wählplan aus, indem Sie links neben dem Namen des Wählplans klicken, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-132">Select the dial plan by clicking to the left of the dial plan name, and then click **Edit**.</span></span>
3. <span data-ttu-id="0de0c-133">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-133">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-dial-plan-to-users"></a><span data-ttu-id="0de0c-134">Zuweisen von Wähleinstellungen zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="0de0c-134">Assign a dial plan to users</span></span>

<span data-ttu-id="0de0c-135">Sie weisen einen Wählplan auf die gleiche Weise zu, wie Sie Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-135">You assign a dial plan in the same way you assign policies.</span></span> [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a><span data-ttu-id="0de0c-136">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="0de0c-136">Using PowerShell</span></span>
  
### <a name="verify-and-start-remote-powershell"></a><span data-ttu-id="0de0c-137">Überprüfen und starten von Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="0de0c-137">Verify and start Remote PowerShell</span></span>

 <span data-ttu-id="0de0c-138">**Überprüfen Sie, ob Sie Windows PowerShell, Version 3,0 oder höher, ausführen.**</span><span class="sxs-lookup"><span data-stu-id="0de0c-138">**Check that you are running Windows PowerShell version 3.0 or later**</span></span>
  
1. <span data-ttu-id="0de0c-139">So überprüfen Sie, ob Sie Version 3,0 oder höher ausführen: **Startmenü**von  >  **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="0de0c-139">To verify that you're running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0de0c-140">Überprüfen Sie die Version, indem Sie im Fenster _Windows PowerShell_ die Zeichenfolge **Get-Host** eingeben.</span><span class="sxs-lookup"><span data-stu-id="0de0c-140">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="0de0c-141">Wenn Sie nicht über Version 3,0 oder höher verfügen, laden Sie Updates für Windows PowerShell herunter, und installieren Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="0de0c-141">If you don't have version 3.0 or later, download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="0de0c-142">Informationen zum herunterladen und Aktualisieren von Windows PowerShell auf Version 4,0 finden Sie unter [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) .</span><span class="sxs-lookup"><span data-stu-id="0de0c-142">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="0de0c-143">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0de0c-143">Restart your computer when you're prompted.</span></span>
    
4. <span data-ttu-id="0de0c-144">Außerdem müssen Sie das Windows PowerShell-Modul für Skype for Business Online installieren, mit dem Sie eine Windows PowerShell-Remotesitzung erstellen können, die eine Verbindung mit Skype for Business Online herstellt.</span><span class="sxs-lookup"><span data-stu-id="0de0c-144">You'll also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="0de0c-145">Sie können dieses Modul, das nur auf 64-Bit-Computern unterstützt wird, im [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-145">You can download this module, which is supported only on 64-bit computers, at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span></span> <span data-ttu-id="0de0c-146">Starten Sie Ihren Computer neu, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="0de0c-146">Restart your computer if you're prompted.</span></span>
    
<span data-ttu-id="0de0c-147">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="0de0c-147">To learn more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>
  
 <span data-ttu-id="0de0c-148">**Starten einer Windows PowerShell-Sitzung**</span><span class="sxs-lookup"><span data-stu-id="0de0c-148">**Start a Windows PowerShell session**</span></span>
  
1. <span data-ttu-id="0de0c-149">Klicken **Start**Sie auf  >  **Windows PowerShell**starten.</span><span class="sxs-lookup"><span data-stu-id="0de0c-149">Click **Start** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="0de0c-150">Stellen Sie im **Windows PowerShell** -Fenster eine Verbindung mit Microsoft 365 oder Office 365 her, indem Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="0de0c-150">In the **Windows PowerShell** window, connect to Microsoft 365 or Office 365 by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0de0c-151">Sie müssen den Befehl **Import-Module** nur bei der ersten Verwendung des Windows PowerShell-Moduls für Skype for Business Online ausführen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-151">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a><span data-ttu-id="0de0c-152">Erstellen und Verwalten von Wählplänen</span><span class="sxs-lookup"><span data-stu-id="0de0c-152">Create and manage your dial plans</span></span>

<span data-ttu-id="0de0c-153">Sie können entweder ein einzelnes Cmdlet oder ein PowerShell-Skript verwenden, um Mandanten-Wählpläne zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0de0c-153">You can either use a single cmdlet or a PowerShell script to create and manage tenant dial plans.</span></span>
  
#### <a name="using-single-cmdlets"></a><span data-ttu-id="0de0c-154">Verwenden einzelner Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0de0c-154">Using single cmdlets</span></span>

- <span data-ttu-id="0de0c-155">Wenn Sie einen neuen Wählplan erstellen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="0de0c-155">To create a new dial plan, run:</span></span>
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="0de0c-156">Weitere Beispiele und Parameter finden Sie unter [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="0de0c-156">For other examples and parameters, see [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).</span></span>
    
- <span data-ttu-id="0de0c-157">Um die Einstellungen eines vorhandenen Wählplans zu bearbeiten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="0de0c-157">To edit the settings of an existing dial plan, run:</span></span>
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    <span data-ttu-id="0de0c-158">Weitere Beispiele und Parameter finden Sie unter [Satz-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="0de0c-158">For other examples and parameters, see [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).</span></span>
    
- <span data-ttu-id="0de0c-159">Führen Sie Folgendes aus, um Benutzer zu einem Wählplan hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="0de0c-159">To add users to a dial plan, run:</span></span>
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    <span data-ttu-id="0de0c-160">Weitere Beispiele und Parameter finden Sie unter [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="0de0c-160">For other examples and parameters, see [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).</span></span>
    
- <span data-ttu-id="0de0c-161">Führen Sie die folgenden Optionen aus, um die Einstellungen für einen Wählplan anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="0de0c-161">To view the settings on a dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    <span data-ttu-id="0de0c-162">Weitere Beispiele und Parameter finden Sie unter [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0de0c-162">For other examples and parameters, see [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="0de0c-163">Um einen Wählplan zu löschen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="0de0c-163">To delete a dial plan, run:</span></span>
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    <span data-ttu-id="0de0c-164">Weitere Beispiele und Parameter finden Sie unter [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0de0c-164">For other examples and parameters, see [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).</span></span>
    
- <span data-ttu-id="0de0c-165">Um die Einstellungen des effektiven Wählplans anzuzeigen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="0de0c-165">To see the settings of the effective dial plan, run:</span></span>
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="0de0c-166">Weitere Beispiele und Parameter finden Sie unter [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span><span class="sxs-lookup"><span data-stu-id="0de0c-166">For other examples and parameters, see [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).</span></span>
    
- <span data-ttu-id="0de0c-167">Um die effektiven Einstellungen eines Wählplans zu testen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="0de0c-167">To test the effective settings of a dial plan, run:</span></span>
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    <span data-ttu-id="0de0c-168">Weitere Beispiele und Parameter finden Sie unter [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0de0c-168">For other examples and parameters, see [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).</span></span>
    
#### <a name="using-a-powershell-script"></a><span data-ttu-id="0de0c-169">Verwenden eines PowerShell-Skripts</span><span class="sxs-lookup"><span data-stu-id="0de0c-169">Using a PowerShell script</span></span>

<span data-ttu-id="0de0c-170">Führen Sie diese Aktion aus, um eine Normalisierungsregel zu löschen, die einem Mandanten Wählplan zugeordnet ist, ohne zuerst den Mandanten Wähl Plan löschen zu müssen:</span><span class="sxs-lookup"><span data-stu-id="0de0c-170">Run this to delete a normalization rule that is associated with a tenant dial plan without needing to delete the tenant dial plan first:</span></span>
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
<span data-ttu-id="0de0c-171">Führen Sie diese Schritte aus, um die folgende Normalisierungsregel zum vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-171">Run this to add the following normalization rule to the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
<span data-ttu-id="0de0c-172">Führen Sie diese Option aus, um die folgende Normalisierungsregel aus dem vorhandenen Mandanten Wähl Plan mit dem Namen redmonddialplan "zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-172">Run this to remove the following normalization rule from the existing tenant dial plan named RedmondDialPlan.</span></span>
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

<span data-ttu-id="0de0c-173">Führen Sie die folgenden Schritte aus, wenn Sie auch die vorhandenen Normalisierungsregeln untersuchen, ermitteln möchten, welche Sie löschen möchten, und dann deren Index verwenden, um Sie zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-173">Run the following when you want to also examine the existing normalization rules, determine which one you want to delete, and then use its index to remove it.</span></span> <span data-ttu-id="0de0c-174">Das Array von Normalisierungsregeln beginnt mit Index 0.</span><span class="sxs-lookup"><span data-stu-id="0de0c-174">The array of normalization rules starts with index 0.</span></span> <span data-ttu-id="0de0c-175">Wir möchten die dreistellige Normalisierungsregel entfernen, also Index 1.</span><span class="sxs-lookup"><span data-stu-id="0de0c-175">We would like to remove the 3-digit normalization rule, so that is index 1.</span></span>
  
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

<span data-ttu-id="0de0c-176">Führen Sie diese Aktion aus, um alle Benutzer zu finden, denen der redmonddialplan "-Mandanten Wählplan gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="0de0c-176">Run this to find all users who have been granted the RedmondDialPlan tenant dial plan.</span></span>
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

<span data-ttu-id="0de0c-177">Führen Sie diesen Vorgang aus, um alle zugewiesenen TenantDialPlan von allen Benutzern zu entfernen, die über einen Hostinganbieter von sipfed.online.lync.com verfügen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-177">Run this to remove any assigned TenantDialPlan from all users who have a HostingProvider of sipfed.online.lync.com.</span></span>
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
```

<span data-ttu-id="0de0c-178">Führen Sie diese aus, um den vorhandenen lokalen Wählplan mit dem Namen OPDP1 als Mandanten Wähl Plan für Ihre Organisation hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-178">Run these to add the existing on-premises dial plan named OPDP1 as a tenant dial plan for your organization.</span></span> <span data-ttu-id="0de0c-179">Sie müssen den lokalen Wählplan zunächst in einer XML-Datei speichern und dann zum Erstellen des neuen Mandanten Wähl Plans verwenden.</span><span class="sxs-lookup"><span data-stu-id="0de0c-179">You need to first save the on-premises dial plan to an .xml file, and then use it to create the new tenant dial plan.</span></span>
  
<span data-ttu-id="0de0c-180">Führen Sie diese Aktion aus, um den lokalen Wählplan in der XML-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0de0c-180">Run this to save the on-premises dial plan to the .xml file.</span></span>
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

<span data-ttu-id="0de0c-181">Führen Sie diese Aktion aus, um den neuen Mandanten Wählplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0de0c-181">Run this to create the new tenant dial plan.</span></span>
  
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
    
## <a name="related-topics"></a><span data-ttu-id="0de0c-182">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0de0c-182">Related topics</span></span>

- [<span data-ttu-id="0de0c-183">Was sind Wählpläne?</span><span class="sxs-lookup"><span data-stu-id="0de0c-183">What are dial plans?</span></span>](what-are-dial-plans.md)
- [<span data-ttu-id="0de0c-184">Übertragen von Telefonnummern – häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0de0c-184">Transferring phone numbers common questions</span></span>](transferring-phone-numbers-common-questions.md)
- [<span data-ttu-id="0de0c-185">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="0de0c-185">Different kinds of phone numbers used for Calling Plans</span></span>](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [<span data-ttu-id="0de0c-186">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="0de0c-186">Manage phone numbers for your organization</span></span>](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [<span data-ttu-id="0de0c-187">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="0de0c-187">Emergency calling terms and conditions</span></span>](emergency-calling-terms-and-conditions.md)
- <span data-ttu-id="0de0c-188">[Disclaimer-Label für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0de0c-188">[Emergency calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>
- [<span data-ttu-id="0de0c-189">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0de0c-189">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
