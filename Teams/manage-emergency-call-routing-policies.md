---
title: Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Routing Richtlinien für Notfälle für das Dynamic E911-Feature in Microsoft Teams verwenden und verwalten.
f1keywords: ms.teamsadmincenter.voice.emergencycallroutingpolicies.overview
ms.openlocfilehash: e7a1295d481db2d970fae2c77be2cff6834c6448
ms.sourcegitcommit: d349922409f49b52048597a56b81501163749a69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2019
ms.locfileid: "37401831"
---
# <a name="manage-emergency-call-routing-policies-in-microsoft-teams"></a><span data-ttu-id="bf8f3-103">Verwalten von Notfall Anruf-Routing Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf8f3-103">Manage emergency call routing policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="bf8f3-104">Wenn Sie in Ihrer Organisation ein direktes Routing für Telefonsysteme bereitgestellt haben, können Sie in Microsoft Teams Notfall-Anruf Weiterleitungsrichtlinien verwenden, um Notrufnummern einzurichten und festzulegen, wie Notrufe weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-104">If you've deployed Phone System Direct Routing in your organization, you can use emergency call routing policies in Microsoft Teams to set up emergency numbers and specify how emergency calls are routed.</span></span> <span data-ttu-id="bf8f3-105">Eine Notruf Routing-Richtlinie legt fest, ob erweiterte Notfalldienste für Benutzer aktiviert sind, denen die Richtlinie zugewiesen ist, die Nummern, mit denen Notrufdienste aufgerufen werden (beispielsweise 911 in den USA) und wie Anrufe an Notfalldienste weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-105">An emergency call routing policy determines whether enhanced emergency services is enabled for users who are assigned the policy, the numbers used to call emergency services (for example, 911 in the United States), and how calls to emergency services are routed.</span></span>

<span data-ttu-id="bf8f3-106">Sie verwalten Notruf Routing Richtlinien, indem Sie im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu **VoIP** > -**Notfall Richtlinien** wechseln.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-106">You manage emergency call routing policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="bf8f3-107">Die Richtlinien können Benutzern und [Netzwerk Websites](location-based-routing-terminology.md)zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-107">The policies can be assigned to users and [network sites](location-based-routing-terminology.md).</span></span>

<span data-ttu-id="bf8f3-108">Für Benutzer können Sie die globale (organisationsweite Standardrichtlinie) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-108">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="bf8f3-109">Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-109">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="bf8f3-110">Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-110">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="bf8f3-111">Für Netzwerk Websites erstellen und zuweisen Sie benutzerdefinierte Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-111">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="bf8f3-112">Wenn Sie einer Netzwerk Website und einem Benutzer eine Notfall Anruf-Routing Richtlinie zugewiesen haben und sich dieser Benutzer an dieser Netzwerk Website befindet, überschreibt die der Netzwerk Website zugewiesene Richtlinie die Richtlinie, die dem Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-112">If you assigned an emergency call routing policy to a network site and to a user and if that  user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-call-routing-policy"></a><span data-ttu-id="bf8f3-113">Erstellen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe</span><span class="sxs-lookup"><span data-stu-id="bf8f3-113">Create a custom emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf8f3-114">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="bf8f3-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="bf8f3-115">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .</span><span class="sxs-lookup"><span data-stu-id="bf8f3-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="bf8f3-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-116">Click **Add**.</span></span>
3. <span data-ttu-id="bf8f3-117">Geben Sie einen Namen und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-117">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="bf8f3-118">Aktivieren Sie erweiterte **Notfalldienste,** um erweiterte Notfalldienste zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-118">To enable enhanced emergency services, turn on **Enhanced emergency services**.</span></span> <span data-ttu-id="bf8f3-119">Wenn erweiterte Notfalldienste aktiviert sind, ruft Teams Richtlinien-und Standortinformationen vom Dienst ab und enthält diese Informationen im Rahmen des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-119">When enhanced emergency services is enabled, Teams retrieves policy and location information from the service and includes that information as part of the emergency call.</span></span>
5. <span data-ttu-id="bf8f3-120">Definieren Sie eine der weiteren Notrufnummern.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-120">Define one of more emergency numbers.</span></span> <span data-ttu-id="bf8f3-121">Gehen Sie dazu unter **Notrufnummern**wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="bf8f3-121">To do this, under **Emergency numbers**, do the following:</span></span>
    1. <span data-ttu-id="bf8f3-122">**Notfall Wahl Zeichenfolge**: Geben Sie die Notrufnummer ein.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-122">**Emergency dial string**: Enter the emergency dial string.</span></span> <span data-ttu-id="bf8f3-123">Diese Wählzeichenfolge zeigt an, dass ein Anruf ein Notruf ist.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-123">This dial string indicates that a call is an emergency call.</span></span>
    2. <span data-ttu-id="bf8f3-124">**Notfall-Wähl Maske**: Sie können für jede Notrufnummer NULL oder mehr Notrufnummern angeben.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-124">**Emergency dial mask**: For each emergency number, you can specify zero or more emergency dial masks.</span></span> <span data-ttu-id="bf8f3-125">Eine Wähl Maske ist die Nummer, die Sie in den Wert der Notruf-Wählzeichenfolge übersetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-125">A dial mask is the number that you want to translate into the value of the emergency dial string.</span></span> <span data-ttu-id="bf8f3-126">Auf diese Weise können alternative Notrufnummern gewählt werden, und der Anruf kann auch Notfalldienste erreichen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services.</span></span> <br><span data-ttu-id="bf8f3-127">Beispielsweise fügen Sie 112 als Notruf Maske hinzu, bei der es sich um die Notrufnummer für die meisten Europa und 911 als Notruf Zeichenfolge handelt.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-127">For example, you add 112 as the emergency dial mask, which is the emergency service number for most of Europe, and 911 as the emergency dial string.</span></span> <span data-ttu-id="bf8f3-128">Ein Team Nutzer aus Europa, der gerade besucht, weiß möglicherweise nicht, dass 911 die Notrufnummer in den Vereinigten Staaten ist, und wenn Sie 112 wählen, wird der Anruf an 911 durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-128">A Teams user from Europe who is visiting may not know that 911 is the emergency number in the United States, and when they dial 112, the call is made to 911.</span></span> <span data-ttu-id="bf8f3-129">Wenn Sie mehrere Wähl Masken definieren möchten, trennen Sie die einzelnen Werte durch ein Semikolon.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-129">To define multiple dial masks, separate each value by a semicolon.</span></span> <span data-ttu-id="bf8f3-130">Beispiel: 112; 212.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-130">For example, 112;212.</span></span>
    3. <span data-ttu-id="bf8f3-131">**PSTN-Verwendung**: Wählen Sie die Verwendung des öffentlichen Switched Telephone Network (PSTN) aus.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-131">**PSTN Usage**: Select the public switched telephone network (PSTN) usage.</span></span> <span data-ttu-id="bf8f3-132">Die PSTN-Nutzung wird verwendet, um zu ermitteln, welche Route zur Weiterleitung von Notrufen von Benutzern verwendet wird, die zur Verwendung autorisiert sind.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-132">The PSTN usage is used to determine which route is used to route emergency calls from users who are authorized to use them.</span></span> <span data-ttu-id="bf8f3-133">Die Route, die mit dieser Verwendung verknüpft ist, sollte auf einen SIP-Stammverweisen, der für Notrufe vorgesehen ist, oder für ein Notfall Standort-Identifikationsnummer (Elin)-Gateway, das Notrufe an den nächstgelegenen öffentlichen Sicherheits-Anrufbeantworter (PSAP) weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-133">The route associated with this usage should point to an SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span>

    > [!NOTE]
    > <span data-ttu-id="bf8f3-134">Wählzeichenfolgen und Wähl Masken müssen innerhalb einer Richtlinie eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-134">Dial strings and dial masks must be unique within a policy.</span></span> <span data-ttu-id="bf8f3-135">Das bedeutet, dass Sie für eine Richtlinie mehrere Notfallnummern definieren können, und Sie können mehrere Wähl Masken für eine Wählzeichenfolge festlegen, aber jede Wählzeichenfolge und Wähl Maske darf nur einmal verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-135">This means that for a policy, you can define multiple emergency numbers and you can set multiple dial masks for a dial string, but each dial string and dial mask must only be used one time.</span></span>

6. <span data-ttu-id="bf8f3-136">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-136">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf8f3-137">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf8f3-137">Using PowerShell</span></span>

<span data-ttu-id="bf8f3-138">Weitere Informationen finden Sie unter [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="bf8f3-138">See [New-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallroutingpolicy).</span></span>

## <a name="edit-an-emergency-call-routing-policy"></a><span data-ttu-id="bf8f3-139">Bearbeiten einer Notfall Anruf-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="bf8f3-139">Edit an emergency call routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf8f3-140">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="bf8f3-140">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="bf8f3-141">Sie können die globale Richtlinie oder alle von Ihnen erstellten benutzerdefinierten Richtlinien bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-141">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="bf8f3-142">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .</span><span class="sxs-lookup"><span data-stu-id="bf8f3-142">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="bf8f3-143">Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken und dann auf **Bearbeiten**klicken.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-143">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="bf8f3-144">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-144">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf8f3-145">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf8f3-145">Using PowerShell</span></span>

<span data-ttu-id="bf8f3-146">Weitere Informationen finden Sie unter [Satz-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="bf8f3-146">See [Set-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallroutingpolicy).</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-users"></a><span data-ttu-id="bf8f3-147">Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="bf8f3-147">Assign a custom emergency call routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bf8f3-148">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="bf8f3-148">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="bf8f3-149">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-149">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="bf8f3-150">Klicken Sie auf **Richtlinien**und dann neben **zugewiesene Richtlinien**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-150">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="bf8f3-151">Wählen Sie unter **Notruf Weiterleitungs Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-151">Under **Emergency call routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="bf8f3-152">Informationen zum Zuweisen einer benutzerdefinierten Teams-Richtlinie zu mehreren Benutzern gleichzeitig finden Sie unter [Bearbeiten von Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="bf8f3-152">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="bf8f3-153">Oder Sie können auch die folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="bf8f3-153">Or, you can also do the following:</span></span>

1. <span data-ttu-id="bf8f3-154">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > -**Notfall Richtlinien**, und klicken Sie dann auf die Registerkarte **Anruf Weiterleitungsrichtlinien** .</span><span class="sxs-lookup"><span data-stu-id="bf8f3-154">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Call routing policies** tab.</span></span>
2. <span data-ttu-id="bf8f3-155">Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-155">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="bf8f3-156">Wählen Sie **Benutzer verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-156">Select **Manage users**.</span></span>
4. <span data-ttu-id="bf8f3-157">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="bf8f3-158">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-158">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="bf8f3-159">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-159">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bf8f3-160">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf8f3-160">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-call-routing-policy-to-a-user"></a><span data-ttu-id="bf8f3-161">Zuweisen einer benutzerdefinierten Routing Richtlinie für Notfallanrufe an einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="bf8f3-161">Assign a custom emergency call routing policy to a user</span></span>

<span data-ttu-id="bf8f3-162">Siehe [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="bf8f3-162">See [Grant-CsTeamsEmergencyCallRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallroutingpolicy).</span></span>

### <a name="assign-a-custom-emergency-call-routing-policy-to-users-in-a-group"></a><span data-ttu-id="bf8f3-163">Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie für Benutzer in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="bf8f3-163">Assign a custom emergency call routing policy to users in a group</span></span>

<span data-ttu-id="bf8f3-164">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Notfall Routing Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-164">You may want to assign a custom emergency call routing policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="bf8f3-165">So können Sie beispielsweise allen Benutzern in einer Sicherheits-oder Verteilergruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-165">For example, you may want to assign a policy to all users in a security or distribution group.</span></span> <span data-ttu-id="bf8f3-166">Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-166">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="bf8f3-167">In diesem Beispiel weisen wir allen Benutzern in der Gruppe Contoso HR eine Richtlinie mit dem Namen "HR Emergency Call Routing Policy" zu.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-167">In this example, we assign a policy called HR Emergency Call Routing Policy to all users in the Contoso HR group.</span></span>  

> [!NOTE]
> <span data-ttu-id="bf8f3-168">Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-168">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="bf8f3-169">Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-169">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso HR"
```
<span data-ttu-id="bf8f3-170">Rufen Sie die Mitglieder der angegebenen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-170">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="bf8f3-171">Weisen Sie alle Benutzer in der Gruppe einer bestimmten Teams-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-171">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="bf8f3-172">In diesem Beispiel handelt es sich um eine Personal Notruf-Routing-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-172">In this example, it's HR Emergency Call Routing Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "HR Emergency Call Routing Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="bf8f3-173">Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-173">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-call-routing-policy-to-a-network-site"></a><span data-ttu-id="bf8f3-174">Zuweisen einer benutzerdefinierten Notfall Routing Richtlinie zu einer Netzwerk Website</span><span class="sxs-lookup"><span data-stu-id="bf8f3-174">Assign a custom emergency call routing policy to a network site</span></span>

<span data-ttu-id="bf8f3-175">Verwenden Sie das Cmdlet " [CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) ", um einer Netzwerk Website eine Notfall Anruf-Routing Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-175">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling routing policy to a network site.</span></span>

<span data-ttu-id="bf8f3-176">In diesem Beispiel wird gezeigt, wie der site1-Website eine Richtlinie namens "Emergency Call Routing Policy 1" zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bf8f3-176">This example shows how to assign a policy called Emergency Call Routing Policy 1 to the Site1 site.</span></span>

```
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Emergency Call Routing Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="bf8f3-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bf8f3-177">Related topics</span></span>

- [<span data-ttu-id="bf8f3-178">Verwalten von Notruf Richtlinien in Teams</span><span class="sxs-lookup"><span data-stu-id="bf8f3-178">Manage emergency calling policies in Teams</span></span>](manage-emergency-calling-policies.md)
- [<span data-ttu-id="bf8f3-179">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf8f3-179">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
