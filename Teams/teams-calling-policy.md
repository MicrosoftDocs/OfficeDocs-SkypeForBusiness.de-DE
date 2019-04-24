---
title: Anrufrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Informationen Sie zu Richtlinieneinstellungen in der Microsoft-Teams aufrufen.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e56f0c89859b940a82e76f8de35ff524a757ec9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225000"
---
<a name="calling-policies-in-microsoft-teams"></a><span data-ttu-id="39308-103">Anrufrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="39308-103">Calling policies in Microsoft Teams</span></span>
==========================================

<span data-ttu-id="39308-104">In Microsoft-Teams Richtlinien-Steuerelements aufrufen, denen der Aufruf und Features für die anrufweiterleitung für Benutzer verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="39308-104">In Microsoft Teams, calling policies control which calling and call forwarding features are available to users.</span></span> <span data-ttu-id="39308-105">Aufrufen von Standortrichtlinien wird bestimmt, ob ein Benutzer private aufgerufen werden kann, verwenden Sie die anrufweiterleitung oder Gleichzeitiges Klingeln an andere Benutzer oder externe Telefonnummern, Weiterleitung von Anrufen an Voicemail, senden Anrufe an Gruppen aufrufen Delegierung für eingehende und ausgehende Anrufe, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="39308-105">Calling policies determine whether a user can make private calls, use call forwarding or  simultaneous ringing to other users or external phone numbers, route calls to voicemail, send calls to Call Groups, use delegation for inbound and outbound calls, and so on.</span></span> <span data-ttu-id="39308-106">Eine globale Standardrichtlinie wird automatisch erstellt, aber Administratoren können auch benutzerdefinierte aufrufende Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="39308-106">A default global policy is created automatically, but admins can also create and assign custom calling policies.</span></span>

## <a name="create-a-custom-calling-policy"></a><span data-ttu-id="39308-107">Erstellen Sie eine benutzerdefinierte Richtlinie an aufrufende</span><span class="sxs-lookup"><span data-stu-id="39308-107">Create a custom calling policy</span></span>

<span data-ttu-id="39308-108">Befolgen Sie diese Schritte, um eine benutzerdefinierte aufrufende Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="39308-108">Follow these steps to create a custom calling policy.</span></span>

1. <span data-ttu-id="39308-109">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="39308-109">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="39308-110">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="39308-110">Select **New policy**.</span></span>
3. <span data-ttu-id="39308-111">Aktivieren Sie die Features, die Sie in der aufrufenden Richtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="39308-111">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="39308-112">Alle ausgewählten Optionen sind standardmäßig **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="39308-112">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="39308-113">Um zu steuern, ob Benutzer eingehende Anrufe an die Voicemail weitergeleitet werden können, wählen Sie **immer aktiviert** , oder **Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="39308-113">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="39308-114">Um zu verhindern, an die Voicemail-routing, wählen Sie **immer deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="39308-114">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="39308-115">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="39308-115">Select **Save**.</span></span>

## <a name="modify-an-existing-calling-policy"></a><span data-ttu-id="39308-116">Ändern einer vorhandenen Richtlinie aufrufen</span><span class="sxs-lookup"><span data-stu-id="39308-116">Modify an existing calling policy</span></span>

<span data-ttu-id="39308-117">Befolgen Sie diese Schritte zum Ändern einer vorhandenen Richtlinie aufrufen.</span><span class="sxs-lookup"><span data-stu-id="39308-117">Follow these steps to modify an existing calling policy.</span></span>

1. <span data-ttu-id="39308-118">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="39308-118">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="39308-119">Klicken Sie neben der Richtlinie, die Sie ändern, und wählen Sie **Bearbeiten**möchten.</span><span class="sxs-lookup"><span data-stu-id="39308-119">Click next to the policy that you want to modify, and then select **Edit**.</span></span>
3. <span data-ttu-id="39308-120">Aktivieren Sie die Features, die Sie in der aufrufenden Richtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="39308-120">Turn on the features that you want to use in your calling policy.</span></span> <span data-ttu-id="39308-121">Alle ausgewählten Optionen sind standardmäßig **deaktiviert** .</span><span class="sxs-lookup"><span data-stu-id="39308-121">All selections are **Off** by default.</span></span>
4. <span data-ttu-id="39308-122">Um zu steuern, ob Benutzer eingehende Anrufe an die Voicemail weitergeleitet werden können, wählen Sie **immer aktiviert** , oder **Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="39308-122">To control whether users can route inbound calls to voicemail, select **Always enabled** or **User controlled**.</span></span> <span data-ttu-id="39308-123">Um zu verhindern, an die Voicemail-routing, wählen Sie **immer deaktiviert**.</span><span class="sxs-lookup"><span data-stu-id="39308-123">To prevent routing to voicemail, select **Always disabled**.</span></span>
5. <span data-ttu-id="39308-124">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="39308-124">Select **Save**.</span></span>

## <a name="assign-a-calling-policy-to-a-user"></a><span data-ttu-id="39308-125">Zuweisen einer Richtlinie für aufrufenden zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="39308-125">Assign a calling policy to a user</span></span>

<span data-ttu-id="39308-126">Befolgen Sie diese Schritte, um eine benutzerdefinierte Richtlinie an aufrufen, die einem Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="39308-126">Follow these steps to assign a custom calling policy to a user.</span></span>

1. <span data-ttu-id="39308-127">Wählen Sie in der Verwaltungskonsole von Microsoft-Teams, **Stimme** > **Richtlinie aufrufen**.</span><span class="sxs-lookup"><span data-stu-id="39308-127">In the Microsoft Teams admin center, select **Voice** > **Calling policy**.</span></span>
2. <span data-ttu-id="39308-128">Klicken Sie neben den Namen der Richtlinie, wählen Sie sie aus, und wählen Sie dann auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="39308-128">Click next to the policy name to select it, and then select **Manage users**.</span></span>
3. <span data-ttu-id="39308-129">Suchen Sie nach den Namen des Benutzers, klicken Sie im Bereich **Benutzer verwalten** .</span><span class="sxs-lookup"><span data-stu-id="39308-129">In the **Manage users** pane, search for the user’s name.</span></span> <span data-ttu-id="39308-130">(Sie müssen mindestens drei Zeichen eingeben.)</span><span class="sxs-lookup"><span data-stu-id="39308-130">(You must enter at least three characters.)</span></span>
4. <span data-ttu-id="39308-131">Wählen Sie den Namen des Benutzers aus, und wählen Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="39308-131">Select the user’s name, and then select **Add**.</span></span>
5. <span data-ttu-id="39308-132">Wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="39308-132">Select **Save**.</span></span>

## <a name="calling-policy-settings"></a><span data-ttu-id="39308-133">Aufrufen von Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="39308-133">Calling policy settings</span></span>

<span data-ttu-id="39308-134">Verwenden Sie die folgenden Einstellungen, um eine benutzerdefinierte aufrufende Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="39308-134">Use the following settings to create a custom calling policy.</span></span>

### <a name="user-can-make-private-calls"></a><span data-ttu-id="39308-135">Benutzer kann private Anrufe tätigen.</span><span class="sxs-lookup"><span data-stu-id="39308-135">User can make private calls</span></span>

<span data-ttu-id="39308-136">Diese Einstellung steuert alle aufrufende Funktionen in Teams.</span><span class="sxs-lookup"><span data-stu-id="39308-136">This setting controls all calling capabilities in Teams.</span></span> <span data-ttu-id="39308-137">Deaktivieren Sie diese Option deaktivieren alle Anruffunktionen in Teams.</span><span class="sxs-lookup"><span data-stu-id="39308-137">Turn this off to turn off all calling functionality in Teams.</span></span>

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a><span data-ttu-id="39308-138">Die anrufweiterleitung und Gleichzeitiges Klingeln an andere Benutzer</span><span class="sxs-lookup"><span data-stu-id="39308-138">Call forwarding and simultaneous ringing to other users</span></span>

<span data-ttu-id="39308-139">Diese Einstellung steuert, ob eingehende Anrufe an andere Benutzer weitergeleitet werden können, oder eine andere Person gleichzeitig anrufen können.</span><span class="sxs-lookup"><span data-stu-id="39308-139">This setting controls whether incoming calls can be forwarded to other users or can ring another person at the same time.</span></span> 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a><span data-ttu-id="39308-140">Die anrufweiterleitung und Gleichzeitiges Klingeln an externe Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="39308-140">Call forwarding and simultaneous ringing to external phone numbers</span></span>

<span data-ttu-id="39308-141">Diese Einstellung steuert, ob eingehende Anrufe an eine externe Nummer weitergeleitet werden können, oder eine externe Nummer gleichzeitig anrufen können.</span><span class="sxs-lookup"><span data-stu-id="39308-141">This setting controls whether incoming calls can be forwarded to an external number or can ring an external number at the same time.</span></span>

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a><span data-ttu-id="39308-142">Voicemail wird für eingehende Anrufe an die Benutzer verfügbar</span><span class="sxs-lookup"><span data-stu-id="39308-142">Voicemail is available for routing inbound calls to users</span></span>

<span data-ttu-id="39308-143">Diese Einstellung aktiviert eingehende Anrufe an die Voicemail gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="39308-143">This setting enables inbound calls to be sent to voicemail.</span></span> <span data-ttu-id="39308-144">Gültige Optionen sind:</span><span class="sxs-lookup"><span data-stu-id="39308-144">Valid options are:</span></span>

   - <span data-ttu-id="39308-145">**Immer aktiviert** Voicemail ist immer für eingehende Anrufe verfügbar.</span><span class="sxs-lookup"><span data-stu-id="39308-145">**Always enabled** Voicemail is always available for inbound calls.</span></span> 
   - <span data-ttu-id="39308-146">**Immer deaktiviert**  Voicemail ist nicht verfügbar für eingehende Anrufe.</span><span class="sxs-lookup"><span data-stu-id="39308-146">**Always disabled**  Voicemail is not available for inbound calls.</span></span> 
   - <span data-ttu-id="39308-147">**Benutzer gesteuert**.</span><span class="sxs-lookup"><span data-stu-id="39308-147">**User controlled**.</span></span> <span data-ttu-id="39308-148">Benutzer können bestimmen, ob sie Voicemail verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="39308-148">Users can determine whether they want voicemail to be available.</span></span>

### <a name="inbound-calls-can-be-routed-to-call-groups"></a><span data-ttu-id="39308-149">Zum Aufrufen von Gruppen können eingehende Anrufe weitergeleitet werden</span><span class="sxs-lookup"><span data-stu-id="39308-149">Inbound calls can be routed to call groups</span></span> 

<span data-ttu-id="39308-150">Diese Einstellung steuert, ob eingehende Anrufe an eine anrufgruppe weitergeleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="39308-150">This setting controls whether incoming calls can be forwarded to a call group.</span></span>

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a><span data-ttu-id="39308-151">Erlaubt die Delegierung für eingehende und ausgehende Anrufe</span><span class="sxs-lookup"><span data-stu-id="39308-151">Allow delegation for inbound and outbound calls</span></span>

<span data-ttu-id="39308-152">Diese Einstellung aktiviert eingehende Anrufe an die Stellvertretungen, Stellvertretungen zu ausgehenden Anrufe im Namen der Benutzer, für den sie Berechtigungen delegiert wurden, zulassen weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="39308-152">This setting enables inbound calls to be routed to delegates, allowing delegates to make outbound calls on behalf of the users for whom they have delegated permissions.</span></span> <span data-ttu-id="39308-153">Weitere Informationen finden Sie unter [Freigeben einer Telefonleitung mit einem Delegaten](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span><span class="sxs-lookup"><span data-stu-id="39308-153">For more information, see [Share a phone line with a delegate](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).</span></span>

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a><span data-ttu-id="39308-154">Verhindern, dass Gebühren umgehen und senden Sie Anrufe über das Telefonfestnetz</span><span class="sxs-lookup"><span data-stu-id="39308-154">Prevent toll bypass and send calls through the PSTN</span></span> 

<span data-ttu-id="39308-155">Durch Festlegen auf **auf** Anrufe über das Telefonfestnetz sendet und Gebühren statt sie über das Netzwerk gesendet werden und umgeht die Gebühren anfallen.</span><span class="sxs-lookup"><span data-stu-id="39308-155">Setting this to **On** will send calls through the PSTN and incur charges rather than sending them through the network and bypassing the tolls.</span></span>

### <a name="busy-on-busy-is-available-while-in-a-call"></a><span data-ttu-id="39308-156">Beschäftigt auf beschäftigt steht während eines Anrufs</span><span class="sxs-lookup"><span data-stu-id="39308-156">Busy on Busy is available while in a call</span></span>

<span data-ttu-id="39308-157">Beschäftigt auf beschäftigt (beschäftigt Optionen)) ist, dass eine neue Einstellung in Teams aufrufende Richtlinien, die Sie Konfigurieren eingehender Anrufe können behandelt werden, wenn ein Benutzer bereits in einem Anruf oder einer Konferenz oder einen Anruf hat in der Warteschleife platziert.</span><span class="sxs-lookup"><span data-stu-id="39308-157">Busy on Busy (Busy Options)) is a new setting in Teams calling policies that allows you to configure how incoming calls are handled when a user is already in a call or conference or has a call placed on hold.</span></span> <span data-ttu-id="39308-158">Neue oder eingehende Anrufe können mit einer Besetztzeichen abgelehnt werden.</span><span class="sxs-lookup"><span data-stu-id="39308-158">New or incoming calls can be rejected with a busy signal.</span></span> <span data-ttu-id="39308-159">Sie können auf einer Ebene Mandanten oder auf der Benutzerebene beschäftigt Optionen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="39308-159">You can enable busy options at a tenant level or at a user level.</span></span> <span data-ttu-id="39308-160">Unabhängig davon, wie ihre beschäftigt Optionen konfiguriert werden sind Benutzer in einen Anruf oder Konferenz oder die durch einen Anruf in der Warteschleife nicht verhindert neue anrufen oder Konferenzen initiieren.</span><span class="sxs-lookup"><span data-stu-id="39308-160">Regardless of how their busy options are configured, users in a call or conference or those with a call on hold are not prevented from initiating new calls or conferences.</span></span> <span data-ttu-id="39308-161">Diese Einstellung ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="39308-161">This setting is disabled by default.</span></span>

