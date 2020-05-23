---
title: Verwalten von VoIP-Routing Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords: ''
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie VoIP-Routing Richtlinien in Microsoft Teams erstellen und verwalten.
ms.openlocfilehash: 061e8066e06c4514a27ea302dab96acfad004ac4
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44350189"
---
# <a name="manage-voice-routing-policies-in-microsoft-teams"></a><span data-ttu-id="919e8-103">Verwalten von VoIP-Routing Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="919e8-103">Manage voice routing policies in Microsoft Teams</span></span>

<span data-ttu-id="919e8-104">Wenn Sie in Ihrer Organisation ein [Direktes Routing für das Telefon System](direct-routing-landing-page.md) bereitgestellt haben, können Sie mithilfe der VoIP-Routing Richtlinien Teams und Skype for Business Online-Benutzern das empfangen und tätigen von Telefon anrufen mit dem öffentlichen Telefonnetz (PSTN) über Ihre lokale Telefonie-Infrastruktur ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="919e8-104">If you've deployed [Phone System Direct Routing](direct-routing-landing-page.md) in your organization, you use voice routing policies to allow Teams and Skype for Business Online users to receive and make phone calls to the Public Switched Telephone Network (PSTN) using your on-premises telephony infrastructure.</span></span>

<span data-ttu-id="919e8-105">Eine VoIP-Routing Richtlinie ist ein Container für PSTN-Verwendungsdaten Sätze.</span><span class="sxs-lookup"><span data-stu-id="919e8-105">A voice routing policy is a container for PSTN usage records.</span></span> <span data-ttu-id="919e8-106">Sie können VoIP-Routing Richtlinien erstellen und verwalten, **Voice**indem Sie  >  im Microsoft Teams Admin Center oder mithilfe von Windows PowerShell zu VoIP-**Routing Richtlinien** wechseln.</span><span class="sxs-lookup"><span data-stu-id="919e8-106">You create and manage voice routing policies by going to **Voice** > **Voice routing policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

<span data-ttu-id="919e8-107">Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="919e8-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="919e8-108">Benutzer erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen eine benutzerdefinierte Richtlinie und weisen diese zu.</span><span class="sxs-lookup"><span data-stu-id="919e8-108">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="919e8-109">Beachten Sie, dass Sie die Einstellungen in der globalen Richtlinie bearbeiten, aber nicht umbenennen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="919e8-109">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span>

<span data-ttu-id="919e8-110">Es ist wichtig zu wissen, dass es für das Zuweisen einer VoIP-Routing Richtlinie zu einem Benutzer nicht möglich ist, in Teams PSTN-Anrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="919e8-110">It's important to know that assigning a voice routing policy to a user doesn't enable them to make PSTN calls in Teams.</span></span> <span data-ttu-id="919e8-111">Darüber hinaus müssen Sie den Benutzer für das direkte Routing des Telefonsystems aktivieren und andere Konfigurationsschritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="919e8-111">You'll also need to enable the user for Phone System Direct Routing and complete other configuration steps.</span></span> <span data-ttu-id="919e8-112">Weitere Informationen finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="919e8-112">To learn more, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

## <a name="create-a-custom-voice-routing-policy"></a><span data-ttu-id="919e8-113">Erstellen einer benutzerdefinierten VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="919e8-113">Create a custom voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="919e8-114">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="919e8-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="919e8-115">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="919e8-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**, and then click **Add**.</span></span><br>
    <span data-ttu-id="919e8-116">![Screenshot der Seite "VoIP-Routing Richtlinie hinzufügen" im Microsoft Teams Admin Center](media/manage-voice-routing-policies.png)</span><span class="sxs-lookup"><span data-stu-id="919e8-116">![Screenshot of the Add voice routing policy page in the Microsoft Teams admin center ](media/manage-voice-routing-policies.png)</span></span> 
2. <span data-ttu-id="919e8-117">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="919e8-117">Enter a name and description for the policy.</span></span>
3. <span data-ttu-id="919e8-118">Klicken Sie unter **PSTN-Verwendungsdaten Sätze**auf **PSTN-Verwendung hinzufügen**, und wählen Sie dann die Datensätze aus, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="919e8-118">Under **PSTN usage records**, click **Add PSTN usage**, and then select the records that you want to add.</span></span> <span data-ttu-id="919e8-119">Wenn Sie einen neuen PSTN-Verwendungsdaten Satz erstellen müssen, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="919e8-119">If you need to create a new PSTN usage record, click **Add**.</span></span>
4. <span data-ttu-id="919e8-120">Wenn Sie mehrere PSTN-Verwendungsdaten Sätze hinzugefügt haben, ordnen Sie diese in der gewünschten Reihenfolge an.</span><span class="sxs-lookup"><span data-stu-id="919e8-120">If you added multiple PSTN usage records, arrange them in the order that you want.</span></span>
5. <span data-ttu-id="919e8-121">Wenn Sie fertig sind, klicken Sie auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="919e8-121">When you're done, click **Apply**.</span></span>
6. <span data-ttu-id="919e8-122">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="919e8-122">Click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="919e8-123">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="919e8-123">Using PowerShell</span></span>

<span data-ttu-id="919e8-124">Weitere Informationen finden Sie unter [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="919e8-124">See [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy).</span></span>

## <a name="edit-a-voice-routing-policy"></a><span data-ttu-id="919e8-125">Bearbeiten einer VoIP-Routing Richtlinie</span><span class="sxs-lookup"><span data-stu-id="919e8-125">Edit a voice routing policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="919e8-126">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="919e8-126">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="919e8-127">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="919e8-127">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="919e8-128">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="919e8-128">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="919e8-129">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="919e8-129">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="919e8-130">Klicken Sie auf **PSTN-Verwendungsdaten Sätze hinzufügen/entfernen**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="919e8-130">Click **Add/remove PSTN usage records**, make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="919e8-131">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="919e8-131">Using PowerShell</span></span>

<span data-ttu-id="919e8-132">Weitere Informationen finden Sie unter [Satz-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="919e8-132">See [Set-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceroutingpolicy).</span></span>

## <a name="assign-a-custom-voice-routing-policy-to-users"></a><span data-ttu-id="919e8-133">Zuweisen einer benutzerdefinierten VoIP-Routing Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="919e8-133">Assign a custom voice routing policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="919e8-134">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="919e8-134">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="919e8-135">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="919e8-135">To assign a policy to one user:</span></span>

1. <span data-ttu-id="919e8-136">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="919e8-136">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="919e8-137">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="919e8-137">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="919e8-138">Wählen Sie unter **VoIP-Routing Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="919e8-138">Under **Voice routing policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="919e8-139">So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="919e8-139">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="919e8-140">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, suchen Sie nach den Benutzern, oder Filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="919e8-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="919e8-141">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="919e8-141">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="919e8-142">Wenn Sie alle Benutzer auswählen möchten, klicken Sie oben in der Tabelle auf das &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="919e8-142">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="919e8-143">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="919e8-143">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="919e8-144">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="919e8-144">Or, you can also do the following:</span></span>

1. <span data-ttu-id="919e8-145">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Routing Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="919e8-145">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Voice routing policies**.</span></span>
2. <span data-ttu-id="919e8-146">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="919e8-146">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="919e8-147">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="919e8-147">Select **Manage users**.</span></span>
4. <span data-ttu-id="919e8-148">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="919e8-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="919e8-149">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="919e8-149">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="919e8-150">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="919e8-150">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="919e8-151">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="919e8-151">Using PowerShell</span></span>

<span data-ttu-id="919e8-152">Siehe [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span><span class="sxs-lookup"><span data-stu-id="919e8-152">See [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="919e8-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="919e8-153">Related topics</span></span>

- [<span data-ttu-id="919e8-154">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="919e8-154">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="919e8-155">Konfigurieren des VoIP-Routings für das direkte Routing</span><span class="sxs-lookup"><span data-stu-id="919e8-155">Configure voice routing for Direct Routing</span></span>](direct-routing-voice-routing.md)
- [<span data-ttu-id="919e8-156">Aktivieren des standortbasierten Routings für direktes Routing</span><span class="sxs-lookup"><span data-stu-id="919e8-156">Enable Location-Based Routing for Direct Routing</span></span>](location-based-routing-enable.md)
- [<span data-ttu-id="919e8-157">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="919e8-157">Assign policies to your users in Teams</span></span>](assign-policies.md)
