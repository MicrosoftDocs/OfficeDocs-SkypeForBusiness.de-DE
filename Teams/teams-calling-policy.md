---
title: Anrufrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Erfahren Sie mehr über die Anruf Richtlinieneinstellungen in Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-voice
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 788cc0e93b16585f1d3424d3bfa0a62693528740
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570270"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="12f0e-103">Anrufrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="12f0e-103">Calling policies in Microsoft Teams</span></span>
===================================

<span data-ttu-id="12f0e-104">In Microsoft Teams Steuern Anruf Richtlinien, welche Anruf-und Anrufweiterleitungsfunktionen Benutzern zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="12f0e-105">Anruf Richtlinien legen fest, ob ein Benutzer private Anrufe tätigen, Anrufweiterleitung oder gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern durchführen, Anrufe an Voicemail weiterleiten, Anrufe an Anrufgruppen senden, die Delegation für ein-und ausgehende Anrufe verwenden usw.</span><span class="sxs-lookup"><span data-stu-id="12f0e-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="12f0e-106">Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte Anruf Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="12f0e-107">Erstellen einer benutzerdefinierten Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="12f0e-107">Create a custom calling policy</span></span>

<span data-ttu-id="12f0e-108">Führen Sie die folgenden Schritte aus, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="12f0e-109">Wählen Sie im Microsoft Teams Admin Center die Option **VoIP** > -**Anrufrichtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="12f0e-110">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-110">Select **New policy**.</span></span>
3. <span data-ttu-id="12f0e-111">Aktivieren Sie die Features, die Sie in ihrer Anrufrichtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="12f0e-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="12f0e-112">Standardmäßig sind alle Auswahlen **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="12f0e-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="12f0e-113">Wenn Sie steuern möchten, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **immer aktiviert** oder **Benutzer gesteuert**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="12f0e-114">Wenn Sie die Weiterleitung an Voicemail verhindern möchten, wählen Sie **immer deaktiviert**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="12f0e-115">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="12f0e-116">Ändern einer vorhandenen Anrufrichtlinie</span><span class="sxs-lookup"><span data-stu-id="12f0e-116">Modify an existing calling policy</span></span>

<span data-ttu-id="12f0e-117">Führen Sie die folgenden Schritte aus, um eine vorhandene Anrufrichtlinie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="12f0e-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="12f0e-118">Wählen Sie im Microsoft Teams Admin Center die Option **VoIP** > -**Anrufrichtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="12f0e-119">Klicken Sie neben der Richtlinie, die Sie ändern möchten, auf, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="12f0e-120">Aktivieren Sie die Features, die Sie in ihrer Anrufrichtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="12f0e-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="12f0e-121">Standardmäßig sind alle Auswahlen **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="12f0e-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="12f0e-122">Wenn Sie steuern möchten, ob Benutzer eingehende Anrufe an Voicemail weiterleiten können, wählen Sie **immer aktiviert** oder **Benutzer gesteuert**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="12f0e-123">Wenn Sie die Weiterleitung an Voicemail verhindern möchten, wählen Sie **immer deaktiviert**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="12f0e-124">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="12f0e-125">Zuweisen einer Anrufrichtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="12f0e-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="12f0e-126">Führen Sie die folgenden Schritte aus, um einem Benutzer eine benutzerdefinierte Anrufrichtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="12f0e-127">Wählen Sie im Microsoft Teams Admin Center die Option **VoIP** > -**Anrufrichtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="12f0e-128">Klicken Sie neben dem Richtliniennamen auf, um ihn auszuwählen, und wählen Sie dann **Benutzer verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="12f0e-129">Suchen Sie im Bereich **Benutzer verwalten** nach dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="12f0e-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="12f0e-130">(Sie müssen mindestens drei Zeichen eingeben.)</span><span class="sxs-lookup"><span data-stu-id="12f0e-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="12f0e-131">Wählen Sie den Namen des Benutzers aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="12f0e-132">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="12f0e-133">Einstellungen für Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="12f0e-133">Calling policy settings</span></span>

<span data-ttu-id="12f0e-134">Verwenden Sie die folgenden Einstellungen, um eine benutzerdefinierte Anrufrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="12f0e-135">Der Benutzer kann private Anrufe tätigen</span><span class="sxs-lookup"><span data-stu-id="12f0e-135">User can make private calls</span></span>

<span data-ttu-id="12f0e-136">Mit dieser Einstellung werden alle Anruffunktionen in Teams gesteuert.</span><span class="sxs-lookup"><span data-stu-id="12f0e-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="12f0e-137">Deaktivieren Sie diese Option, um alle Anruffunktionen in Teams zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="12f0e-138">Anrufweiterleitung und gleichzeitiges Klingeln an andere Benutzer</span><span class="sxs-lookup"><span data-stu-id="12f0e-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="12f0e-139">Mit dieser Einstellung wird gesteuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können oder dass Sie eine andere Person gleichzeitig anrufen können.</span><span class="sxs-lookup"><span data-stu-id="12f0e-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="12f0e-140">Anrufweiterleitung und gleichzeitiges Klingeln an externe Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="12f0e-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="12f0e-141">Diese Einstellung steuert, ob eingehende Anrufe an eine externe Rufnummer weitergeleitet werden können oder gleichzeitig eine externe Rufnummer anrufen können.</span><span class="sxs-lookup"><span data-stu-id="12f0e-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="12f0e-142">Voicemail steht zum Weiterleiten von eingehenden Anrufen an Benutzer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="12f0e-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="12f0e-143">Mit dieser Einstellung können eingehende Anrufe an Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="12f0e-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="12f0e-144">Gültige Optionen sind:</span><span class="sxs-lookup"><span data-stu-id="12f0e-144">Valid options are:</span></span>

   - <span data-ttu-id="12f0e-145">**Immer aktiviert** Voicemail steht für eingehende Anrufe immer zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="12f0e-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="12f0e-146">**Immer deaktiviert**  Voicemail steht für eingehende Anrufe nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="12f0e-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="12f0e-147">**Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="12f0e-147">**User controlled**.</span></span> <span data-ttu-id="12f0e-148">Benutzer können feststellen, ob Voicemail verfügbar sein soll.</span><span class="sxs-lookup"><span data-stu-id="12f0e-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="12f0e-149">Eingehende Anrufe können an Anrufgruppen weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="12f0e-149">Inbound calls can be routed to call groups</span></span> 

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="12f0e-150">Diese Einstellung steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="12f0e-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="12f0e-151">Zulassen der Delegierung für eingehende und ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="12f0e-151">Allow delegation for inbound and outbound calls</span></span>

> [!Include [feature preview](includes/preview-feature.md)]

<span data-ttu-id="12f0e-152">Mit dieser Einstellung können eingehende Anrufe an Stellvertretungen weitergeleitet werden, sodass Stellvertretungen im Namen der Benutzer, für die Sie Berechtigungen delegiert haben, ausgehende Anrufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="12f0e-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="12f0e-153">Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einer Stellvertretung](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="12f0e-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="12f0e-154">Vermeidung von Maut Umgehung und Senden von Anrufen über das PSTN</span><span class="sxs-lookup"><span data-stu-id="12f0e-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="12f0e-155">Wenn Sie diese Einstellung **aktivieren** , werden Anrufe über das PSTN durchgeführt, und es fallen Gebühren an, anstatt Sie über das Netzwerk zu senden und die Mautgebühren zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="12f0e-156">Busy on Busy steht während eines Anrufs zur Verfügung</span><span class="sxs-lookup"><span data-stu-id="12f0e-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="12f0e-157">Busy on Busy (busy-Optionen)) ist eine neue Einstellung in Teams, die Richtlinien aufrufen, mit denen Sie konfigurieren können, wie eingehende Anrufe gehandhabt werden, wenn sich ein Benutzer bereits in einem Anruf oder einer Konferenz befindet oder ein Anruf in Wartestellung gesetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="12f0e-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that lets you configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="12f0e-158">Neue oder eingehende Anrufe können mit einem Besetztzeichen zurückgewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="12f0e-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="12f0e-159">Sie können die Auslastungs Optionen auf Mandantenebene oder auf Benutzerebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-159">You can enable busy options at the tenant level or at the user level.</span></span> <span data-ttu-id="12f0e-160">Unabhängig davon, wie Ihre besetzt-Optionen konfiguriert sind, werden Benutzer in einem Anruf oder einer Konferenz oder Personen mit einem Anruf in Wartestellung nicht daran gehindert, neue Anrufe oder Konferenzen zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="12f0e-161">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="12f0e-161">This setting is disabled by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="12f0e-162">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12f0e-162">See also</span></span>

[<span data-ttu-id="12f0e-163">Satz-CSTeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="12f0e-163">Set-CSTeamsCallingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)