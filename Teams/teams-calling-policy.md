---
title: Anrufrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Informationen zum Erstellen, ändern und Hinzufügen von Benutzern zu benutzerdefinierten Anruf Richtlinien in Microsoft Teams sowie zu verschiedenen Anruf Richtlinieneinstellungen.
localization_priority: Normal
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a67952854f608512e88786c2b49d1e2ad8dfcf9
ms.sourcegitcommit: 184f4f61a3e739a1cfa533c6d95d405d887ea25d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "44592952"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="40a88-103">Anrufrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="40a88-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="40a88-104">In Microsoft Teams Steuern Anruf Richtlinien, welche Anruf-und Anrufweiterleitungsfunktionen Benutzern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="40a88-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="40a88-105">Anruf Richtlinien legen fest, ob ein Benutzer private Anrufe tätigen, Anrufweiterleitung oder gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern durchführen, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, die Delegation für ein-und ausgehende Anrufe verwenden usw.</span><span class="sxs-lookup"><span data-stu-id="40a88-105">Calling policies determine whether a user can make private calls, use call forwarding or simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="40a88-106">Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte Anruf Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="40a88-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="40a88-107">Erstellen einer benutzerdefinierten Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="40a88-107">Create a custom calling policy</span></span>

<span data-ttu-id="40a88-108">Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="40a88-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="40a88-109">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Anruf Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="40a88-109">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="40a88-110">Wählen Sie **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-110">Select **Add**.</span></span>
3. <span data-ttu-id="40a88-111">Aktivieren oder deaktivieren Sie die Features, die Sie in ihrer Anrufrichtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="40a88-111">Turn on or turn off the features that you want to use in your calling policy.</span></span>
4. <span data-ttu-id="40a88-112">Wenn Sie steuern möchten, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **aktiviert** oder **Benutzer gesteuert**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-112">To control whether users can route inbound calls to voicemail, select **Enabled** or **User controlled**.</span></span> <span data-ttu-id="40a88-113">Wenn Sie die Weiterleitung an Voicemail verhindern möchten, wählen Sie **deaktiviert**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-113">To prevent routing to voicemail, select **Disabled**.</span></span>
5. <span data-ttu-id="40a88-114">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-114">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="40a88-115">Ändern einer vorhandenen Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="40a88-115">Modify an existing calling policy</span></span>

<span data-ttu-id="40a88-116">Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="40a88-116">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="40a88-117">Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers die Option **VoIP**-  >  **Anruf Richtlinien**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-117">In the left navigation of the Microsoft Teams admin center, select **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="40a88-118">Klicken Sie neben der Richtlinie, die Sie ändern möchten, auf, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-118">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="40a88-119">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="40a88-119">Make the changes that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-calling-policy-to-users"></a><span data-ttu-id="40a88-120">Zuweisen einer benutzerdefinierten Anrufrichtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="40a88-120">Assign a custom calling policy to users</span></span>

<span data-ttu-id="40a88-121">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="40a88-121">To assign a policy to one user:</span></span>

1. <span data-ttu-id="40a88-122">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="40a88-122">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="40a88-123">Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="40a88-123">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="40a88-124">Wählen Sie unter **Anrufrichtlinie**die Anrufrichtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="40a88-124">Under **Calling policy**, select the calling policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="40a88-125">So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="40a88-125">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="40a88-126">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="40a88-126">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="40a88-127">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-127">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="40a88-128">Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="40a88-128">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="40a88-129">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="40a88-129">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="40a88-130">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="40a88-130">Or, you can also do the following:</span></span>

1. <span data-ttu-id="40a88-131">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**-  >  **Anruf Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="40a88-131">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="40a88-132">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="40a88-132">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="40a88-133">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-133">Select **Manage users**.</span></span>
4. <span data-ttu-id="40a88-134">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="40a88-134">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="40a88-135">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.</span><span class="sxs-lookup"><span data-stu-id="40a88-135">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="40a88-136">Nachdem Sie das Hinzufügen von Benutzern abgeschlossen haben, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="40a88-136">After you finish adding users, select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="40a88-137">Einstellungen für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="40a88-137">Calling policy settings</span></span>

<span data-ttu-id="40a88-138">Hier sind die Einstellungen, die Sie für Anruf Richtlinien konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="40a88-138">Here's the settings that you can configure for calling policies.</span></span>

### <a name="make-private-calls"></a><span data-ttu-id="40a88-139">Private Anrufe führen</span><span class="sxs-lookup"><span data-stu-id="40a88-139">Make private calls</span></span>

<span data-ttu-id="40a88-140">Mit dieser Einstellung werden alle Anruffunktionen in Teams gesteuert.</span><span class="sxs-lookup"><span data-stu-id="40a88-140">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="40a88-141">Deaktivieren Sie diese Option, um alle Anruffunktionen in Teams zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="40a88-141">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a><span data-ttu-id="40a88-142">Anrufweiterleitung und gleichzeitiges Klingeln an Personen in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="40a88-142">Call forwarding and simultaneous ringing to people in your organization</span></span>

<span data-ttu-id="40a88-143">Mit dieser Einstellung wird gesteuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder dass Sie eine andere Person gleichzeitig anrufen können.</span><span class="sxs-lookup"><span data-stu-id="40a88-143">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="40a88-144">Anrufweiterleitung und gleichzeitiges Klingeln an externe Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="40a88-144">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="40a88-145">Diese Einstellung steuert, ob eingehende Anrufe an eine externe Rufnummer weitergeleitet werden können oder gleichzeitig eine externe Rufnummer anrufen können.</span><span class="sxs-lookup"><span data-stu-id="40a88-145">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls"></a><span data-ttu-id="40a88-146">Voicemail steht zum Weiterleiten von eingehenden Anrufen zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="40a88-146">Voicemail is available for routing inbound calls</span></span>

<span data-ttu-id="40a88-147">Mit dieser Einstellung können eingehende Anrufe an Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="40a88-147">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="40a88-148">Gültige Optionen sind:</span><span class="sxs-lookup"><span data-stu-id="40a88-148">Valid options are:</span></span>

- <span data-ttu-id="40a88-149">**Aktiviert** Voicemail steht für eingehende Anrufe immer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40a88-149">**Enabled** Voicemail is always available for inbound calls.</span></span> 
- <span data-ttu-id="40a88-150">**Deaktiviert**  Voicemail steht für eingehende Anrufe nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40a88-150">**Disabled**  Voicemail is not available for inbound calls.</span></span> 
- <span data-ttu-id="40a88-151">**Benutzer gesteuert** Benutzer können feststellen, ob Voicemail verfügbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="40a88-151">**User controlled** Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="40a88-152">Eingehende Anrufe können an Anrufgruppen weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="40a88-152">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="40a88-153">Diese Einstellung steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="40a88-153">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="40a88-154">Zulassen der Delegierung für eingehende und ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="40a88-154">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="40a88-155">Mit dieser Einstellung können eingehende Anrufe an Stellvertretungen weitergeleitet werden, sodass Stellvertretungen im Namen der Benutzer, für die Sie Berechtigungen delegiert haben, ausgehende Anrufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="40a88-155">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="40a88-156">Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="40a88-156">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="40a88-157">Vermeidung von Maut Umgehung und Senden von Anrufen über das PSTN</span><span class="sxs-lookup"><span data-stu-id="40a88-157">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="40a88-158">Wenn Sie diese Einstellung **aktivieren** , werden Anrufe über das PSTN durchgeführt, und es fallen Gebühren an, anstatt Sie über das Netzwerk zu senden und die Mautgebühren zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="40a88-158">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="40a88-159">Busy on Busy steht während eines Anrufs zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="40a88-159">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="40a88-160">Busy on Busy (busy-Optionen) ist eine neue Einstellung, mit der Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="40a88-160">Busy on Busy (Busy Options) is a new setting that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="40a88-161">Neue oder eingehende Anrufe können mit einem Besetztzeichen zurückgewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="40a88-161">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="40a88-162">Sie können die Auslastungs Optionen auf Mandantenebene oder auf Benutzerebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="40a88-162">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="40a88-163">Unabhängig davon, wie Ihre besetzt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder Personen mit einem Anruf in Wartestellung nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="40a88-163">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="40a88-164">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="40a88-164">This setting is disabled by default.</span></span>

### <a name="allow-web-pstn-calling"></a><span data-ttu-id="40a88-165">Zulassen von webpstn-anrufen</span><span class="sxs-lookup"><span data-stu-id="40a88-165">Allow web PSTN calling</span></span>

<span data-ttu-id="40a88-166">Mit dieser Einstellung können Benutzer PSTN-Nummern über den Microsoft Teams-WebClient anrufen.</span><span class="sxs-lookup"><span data-stu-id="40a88-166">This setting enables users to call PSTN numbers using the Teams web client.</span></span>

### <a name="allow-music-on-hold"></a><span data-ttu-id="40a88-167">Musik in Wartestellung zulassen</span><span class="sxs-lookup"><span data-stu-id="40a88-167">Allow music on hold</span></span>

<span data-ttu-id="40a88-168">Mit dieser Einstellung können Sie die Musik im Wartebereich aktivieren oder deaktivieren, wenn ein PSTN-Anrufer in Wartestellung gesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="40a88-168">This setting allows you to turn on or turn off music on hold when a PSTN caller is placed on hold.</span></span> <span data-ttu-id="40a88-169">Sie ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="40a88-169">It's turned on by default.</span></span> <span data-ttu-id="40a88-170">Diese Einstellung gilt nicht für die Features von Park-und Boss-Stellvertretungen und steht derzeit nur über PowerShell zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="40a88-170">This setting doesn't apply to call park and boss delegate features, and is currently only available via PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="40a88-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40a88-171">See also</span></span>

[<span data-ttu-id="40a88-172">Satz-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="40a88-172">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)
