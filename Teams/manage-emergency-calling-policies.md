---
title: Verwalten von Notruf Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Microsoft Teams Notruf Richtlinien verwenden und verwalten, um zu definieren, was passiert, wenn ein Team Benutzer in Ihrer Organisation einen Notfall Anruf tätigt.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ea02c1c7f9d4142db9cb25c00714e04a28e0e5e3
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350199"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="46bed-103">Verwalten von Notruf Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46bed-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="46bed-104">Wenn Ihre Organisation Anrufpläne verwendet oder ein direktes Routing für das Telefon System bereitgestellt hat, können Sie in Microsoft Teams Notruf Richtlinien verwenden, um zu definieren, was passiert, wenn ein Team Benutzer in Ihrer Organisation einen Notfall Anruf tätigt.</span><span class="sxs-lookup"><span data-stu-id="46bed-104">If your organization uses Calling Plans or deployed Phone System Direct Routing, you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="46bed-105">Sie können festlegen, welche Personen benachrichtigt werden sollen und wie Sie benachrichtigt werden, wenn ein Benutzer, dem die Richtlinie zugewiesen ist, Notfalldienste aufruft.</span><span class="sxs-lookup"><span data-stu-id="46bed-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="46bed-106">So können Sie beispielsweise Richtlinieneinstellungen so konfigurieren, dass Sie den Security Desk Ihrer Organisation automatisch benachrichtigen und in Notrufen abhören.</span><span class="sxs-lookup"><span data-stu-id="46bed-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="46bed-107">Sie verwalten Notruf Richtlinien, indem Sie **Voice**  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Notfall Richtlinien** wechseln.</span><span class="sxs-lookup"><span data-stu-id="46bed-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="46bed-108">Die Richtlinien können Benutzern und [Netzwerk Websites](cloud-voice-network-settings.md)zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="46bed-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="46bed-109">Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46bed-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="46bed-110">Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu.</span><span class="sxs-lookup"><span data-stu-id="46bed-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="46bed-111">Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="46bed-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="46bed-112">Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="46bed-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="46bed-113">Wenn Sie einer Netzwerk Website und einem Benutzer eine Notruf Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="46bed-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="46bed-114">Erstellen einer benutzerdefinierten Notfall Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="46bed-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="46bed-115">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="46bed-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="46bed-116">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Richtlinien** .</span><span class="sxs-lookup"><span data-stu-id="46bed-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="46bed-117">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="46bed-117">Click **Add**.</span></span>
3. <span data-ttu-id="46bed-118">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="46bed-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="46bed-119">Legen Sie fest, wie Personen in Ihrer Organisation, in der Regel der Security Desk, benachrichtigt werden sollen, wenn ein Notruf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="46bed-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="46bed-120">Wählen Sie dazu unter **Benachrichtigungsmodus**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="46bed-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="46bed-121">**Nur Benachrichtigung senden**: eine Team-Chat-Nachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet.</span><span class="sxs-lookup"><span data-stu-id="46bed-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="46bed-122">**Konferenz, aber stumm geschaltet**: eine Team-Chat-Nachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet, und Sie können in der Konversation zwischen dem Anrufer und dem PSAP-Operator lauschen (aber nicht teilnehmen).</span><span class="sxs-lookup"><span data-stu-id="46bed-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="46bed-123">**Konferenz-und Stummschaltung (in** **Kürze verfügbar)**: eine Team-Chat-Nachricht wird an die von Ihnen angegebenen Benutzer und Gruppen gesendet, und Sie können die Stummschaltung aufheben, um die Unterhaltung zwischen dem Anrufer und dem PSAP-Operator zu hören und an der Unterhaltung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="46bed-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="46bed-124">Wenn Sie den Benachrichtigungsmodus für Konferenzgespräche, **aber stumm geschaltet** ausgewählt haben, können Sie im Feld **auswählnummer für Benachrichtigungen** eine PSTN-Telefonnummer eines Benutzers oder einer Gruppe eingeben, um anzurufen und an dem Notruf teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="46bed-124">If you selected the **Conferenced in but are muted** notification mode, in the **Dial-out number for notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="46bed-125">Geben Sie beispielsweise die Nummer des Security Desk Ihrer Organisation ein, der einen Anruf erhält, wenn ein Notruf durchgeführt wird, und dann den Anruf anhören kann.</span><span class="sxs-lookup"><span data-stu-id="46bed-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="46bed-126">Suchen Sie nach einem oder mehreren Benutzern oder Gruppen, wie dem Security Desk Ihrer Organisation, um zu benachrichtigen, wenn ein Notruf durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="46bed-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="46bed-127">Die Benachrichtigung kann an e-Mail-Adressen von Benutzern, Verteilergruppen und Sicherheitsgruppen gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="46bed-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="46bed-128">Es können maximal 50-Benutzer benachrichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="46bed-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="46bed-129">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46bed-129">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="46bed-130">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="46bed-130">Using PowerShell</span></span>

<span data-ttu-id="46bed-131">Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="46bed-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="46bed-132">Bearbeiten einer Notruf Richtlinie</span><span class="sxs-lookup"><span data-stu-id="46bed-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="46bed-133">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="46bed-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="46bed-134">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46bed-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="46bed-135">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Richtlinien** .</span><span class="sxs-lookup"><span data-stu-id="46bed-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="46bed-136">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="46bed-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="46bed-137">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46bed-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="46bed-138">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="46bed-138">Using PowerShell</span></span>

<span data-ttu-id="46bed-139">Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="46bed-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="46bed-140">Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="46bed-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="46bed-141">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="46bed-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="46bed-142">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="46bed-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="46bed-143">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="46bed-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="46bed-144">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="46bed-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="46bed-145">Wählen Sie unter **Notruf Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46bed-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="46bed-146">So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="46bed-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="46bed-147">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, suchen Sie nach den Benutzern, oder Filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46bed-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="46bed-148">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="46bed-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="46bed-149">Wenn Sie alle Benutzer auswählen möchten, klicken Sie oben in der Tabelle auf das &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="46bed-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="46bed-150">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="46bed-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="46bed-151">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="46bed-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="46bed-152">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Richtlinien** .</span><span class="sxs-lookup"><span data-stu-id="46bed-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="46bed-153">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="46bed-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="46bed-154">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="46bed-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="46bed-155">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="46bed-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="46bed-156">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="46bed-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="46bed-157">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="46bed-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="46bed-158">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="46bed-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="46bed-159">Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="46bed-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="46bed-160">Siehe [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span><span class="sxs-lookup"><span data-stu-id="46bed-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="46bed-161">Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie zu Benutzern in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="46bed-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="46bed-162">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Notruf Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46bed-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="46bed-163">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46bed-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="46bed-164">Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="46bed-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="46bed-165">In diesem Beispiel weisen wir allen Benutzern in der Contoso-Vorgangsgruppe eine Richtlinie mit dem Namen "Operations Emergency Calling Policy" zu.</span><span class="sxs-lookup"><span data-stu-id="46bed-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="46bed-166">Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="46bed-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="46bed-167">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="46bed-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="46bed-168">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="46bed-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="46bed-169">Zuweisen aller Benutzer in der Gruppe zu einer bestimmten Teamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="46bed-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="46bed-170">In diesem Beispiel handelt es sich um die Richtlinie für die Notfall Anrufweiterleitung.</span><span class="sxs-lookup"><span data-stu-id="46bed-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="46bed-171">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="46bed-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="46bed-172">Zuweisen einer benutzerdefinierten Notfall Anrufrichtlinie zu einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="46bed-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="46bed-173">Verwenden Sie das Cmdlet " [Satz-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notruf Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="46bed-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="46bed-174">Im folgenden Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Contoso Emergency Calling Policy 1" zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="46bed-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="46bed-175">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="46bed-175">Related topics</span></span>

- [<span data-ttu-id="46bed-176">Verwalten von Notfall Anruf Weiterleitungsrichtlinien in Teams</span><span class="sxs-lookup"><span data-stu-id="46bed-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="46bed-177">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46bed-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="46bed-178">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46bed-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
