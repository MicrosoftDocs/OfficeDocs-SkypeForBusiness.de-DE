---
title: Verwalten von externen Zugriff (Verbund) im Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: karvell
search.appverid: MET150
description: Ihre IT-Administrator kann den Zugriff durch andere Domänen (Verbund) können Benutzer über diese Domänen Teams teilnehmen konfigurieren.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56e4171421cc52ec1ca79895aba3c0f259d20201
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2019
ms.locfileid: "29708797"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="9ebbb-103">Verwalten von externen Zugriff (Verbund) im Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="9ebbb-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="9ebbb-104">Mit Microsoft-Teams, externen Zugriff können Benutzer aus anderen Domänen in Ihrer Chats und Anrufe teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="9ebbb-105">Sie können auch externe Benutzer zulassen, die noch Skype für Unternehmen Teilnahme an.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-105">You can also allow external users who are still using Skype for Business to participate.</span></span> 

<span data-ttu-id="9ebbb-106">Externen Zugriff (Verbund) und Gast Access unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="9ebbb-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="9ebbb-107">Gast Access erteilt eine einzelne Zugriffsberechtigung.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="9ebbb-108">Externer Zugriff erhält die Zugriffsberechtigung, eine gesamte Domäne.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="9ebbb-109">Einmal durch einen Teambesitzer gewährten Gast-Zugriffs kann Gastsystem auf [Ressourcen zugreifen](guest-experience.md)wie Channel Diskussionen und Dateien, für ein bestimmtes Team und Chat mit anderen Benutzern in das Team aus, dem sie eingeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="9ebbb-110">Mit externem Zugriff (federated Chat) haben die Teilnehmer externe Chat keinen Zugriff auf der einladen Organisation Teams oder Teamressourcen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="9ebbb-111">Sie können nur Angebot federated Chat teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="9ebbb-112">Mandanten-Admins können zwischen den beiden Optionen, je nachdem, welcher Ebene der Zusammenarbeit mit der externen Partei wünschenswert ist.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="9ebbb-113">Administratoren können dann Ansätze oder beides, je nach ihren Anforderungen in der Organisation, aber es wird empfohlen, um zukünftig einen Gastzugriff eine vollständigere, gemeinsame Teams wünschen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="9ebbb-114">Finden Sie in der folgenden Tabelle einen Vergleich von externen und Gast-Funktionen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="9ebbb-115">Funktion</span><span class="sxs-lookup"><span data-stu-id="9ebbb-115">Feature</span></span> | <span data-ttu-id="9ebbb-116">Zugriff durch externe Benutzer</span><span class="sxs-lookup"><span data-stu-id="9ebbb-116">External access users</span></span> | <span data-ttu-id="9ebbb-117">Gast Access-Benutzer</span><span class="sxs-lookup"><span data-stu-id="9ebbb-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="9ebbb-118">Benutzer kann mit einer anderen Person in einem anderen Unternehmen chat.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-118">User can chat with someone in another company</span></span> | <span data-ttu-id="9ebbb-119">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-119">Yes</span></span> |<span data-ttu-id="9ebbb-120">Ja </span><span class="sxs-lookup"><span data-stu-id="9ebbb-120">Yes</span></span> |
| <span data-ttu-id="9ebbb-121">Benutzer kann eine Person in einem anderen Unternehmen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-121">User can call someone in another company</span></span> | <span data-ttu-id="9ebbb-122">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-122">Yes</span></span> | <span data-ttu-id="9ebbb-123">Ja </span><span class="sxs-lookup"><span data-stu-id="9ebbb-123">Yes</span></span> |
| <span data-ttu-id="9ebbb-124">Benutzer kann sehen, wenn jemand aus einem anderen Unternehmen für Anruf oder Chat verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="9ebbb-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="9ebbb-125">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-125">Yes</span></span> | <span data-ttu-id="9ebbb-126">Ja,<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="9ebbb-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="9ebbb-127">Benutzer kann externe konstant nach Benutzern suchen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-127">User can search for users across external tenants</span></span> | <span data-ttu-id="9ebbb-128">Ja,<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="9ebbb-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="9ebbb-129">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-129">No</span></span> |
| <span data-ttu-id="9ebbb-130">Benutzer kann Dateien freigeben.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-130">User can share files</span></span> | <span data-ttu-id="9ebbb-131">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-131">No</span></span> | <span data-ttu-id="9ebbb-132">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-132">Yes</span></span> |
| <span data-ttu-id="9ebbb-133">Benutzer kann Teams Ressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-133">User can access Teams resources</span></span> | <span data-ttu-id="9ebbb-134">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-134">No</span></span> | <span data-ttu-id="9ebbb-135">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-135">Yes</span></span> |
| <span data-ttu-id="9ebbb-136">Benutzer kann einen Gruppenchat hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="9ebbb-136">User can be added to a group chat</span></span> | <span data-ttu-id="9ebbb-137">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-137">No</span></span> | <span data-ttu-id="9ebbb-138">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-138">Yes</span></span> |
| <span data-ttu-id="9ebbb-139">Benutzer kann an einer Besprechung hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="9ebbb-139">User can be added to a meeting</span></span> | <span data-ttu-id="9ebbb-140">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-140">Yes</span></span> | <span data-ttu-id="9ebbb-141">Ja </span><span class="sxs-lookup"><span data-stu-id="9ebbb-141">Yes</span></span> |
| <span data-ttu-id="9ebbb-142">Weitere Benutzer können einen Chat mit einem externen Benutzer hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="9ebbb-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="9ebbb-143">Keine<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="9ebbb-143">No<sup>3</sup></span></span> | <span data-ttu-id="9ebbb-144">n/v</span><span class="sxs-lookup"><span data-stu-id="9ebbb-144">N/A</span></span> |
| <span data-ttu-id="9ebbb-145">Benutzer wird als von externer Seite identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-145">User is identified as an external party</span></span> | <span data-ttu-id="9ebbb-146">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-146">Yes</span></span> | <span data-ttu-id="9ebbb-147">Ja </span><span class="sxs-lookup"><span data-stu-id="9ebbb-147">Yes</span></span> |
| <span data-ttu-id="9ebbb-148">Anwesenheitsinformationen wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-148">Presence is displayed</span></span> | <span data-ttu-id="9ebbb-149">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-149">Yes</span></span> | <span data-ttu-id="9ebbb-150">Ja </span><span class="sxs-lookup"><span data-stu-id="9ebbb-150">Yes</span></span> |
| <span data-ttu-id="9ebbb-151">Abwesend wird Nachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-151">Out of office message is shown</span></span> | <span data-ttu-id="9ebbb-152">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-152">No</span></span> | <span data-ttu-id="9ebbb-153">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-153">Yes</span></span> |
| <span data-ttu-id="9ebbb-154">Einzelner Benutzer kann ausgeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="9ebbb-154">Individual user can be blocked</span></span> | <span data-ttu-id="9ebbb-155">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-155">No</span></span> | <span data-ttu-id="9ebbb-156">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-156">Yes</span></span> |
| <span data-ttu-id="9ebbb-157">@mentions werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-157">@mentions are supported</span></span> | <span data-ttu-id="9ebbb-158">Nein</span><span class="sxs-lookup"><span data-stu-id="9ebbb-158">No</span></span> | <span data-ttu-id="9ebbb-159">Ja</span><span class="sxs-lookup"><span data-stu-id="9ebbb-159">Yes</span></span> |
||||

<span data-ttu-id="9ebbb-160"><sup>1</sup> bereitgestellt, dass der Benutzer wurde als Gast hinzugefügt und als Gast, die dem Mandanten Gast angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-160"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="9ebbb-161"><sup>2</sup> nur per e-Mail oder Adresse Session Initiation Protocol (SIP).</span><span class="sxs-lookup"><span data-stu-id="9ebbb-161"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="9ebbb-162"><sup>3</sup> externe (Verbund) Chat ist 1:1.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-162"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

## <a name="turn-on-or-turn-off-external-access"></a><span data-ttu-id="9ebbb-163">Aktivieren Sie oder deaktivieren Sie des externen Zugriffs</span><span class="sxs-lookup"><span data-stu-id="9ebbb-163">Turn on or turn off external access</span></span>

<span data-ttu-id="9ebbb-164">Die Microsoft-Teams & Skype für Business Admin Center können Sie um externen Zugriff zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-164">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="9ebbb-165">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-165">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Screenshot des externen Zugriff für die gesamte Org-Einstellungen](media/manage-external-access-1.png)<span data-ttu-id="9ebbb-167">.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-167"></span></span>

2. <span data-ttu-id="9ebbb-168">Bringen Sie den **externen Zugriff** Schalter zum **ein-** oder **Ausschalten**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-168">Toggle the **External access** switch to **On** or **Off**.</span></span>

     ![Screenshot des externen Zugriffs Switch eingeschaltet](media/manage-external-access-2.png)<span data-ttu-id="9ebbb-170">.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-170"></span></span>

3. <span data-ttu-id="9ebbb-171">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-171">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="9ebbb-172">Hinzufügen oder eine Domäne blockieren</span><span class="sxs-lookup"><span data-stu-id="9ebbb-172">Add or block a domain</span></span>

<span data-ttu-id="9ebbb-173">Befolgen Sie diese Schritte zum Hinzufügen einer Domäne oder Deaktivieren des externen Zugriffs für eine Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-173">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="9ebbb-174">Wählen Sie in der Microsoft-Teams & Skype für Business Admin Center **Org geltende Einstellungen** > **externen Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-174">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="9ebbb-175">Wählen Sie **eine Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-175">Select **Add a domain**.</span></span> 
 
    ![Screenshot des externen Zugriffs-Seite mit einen Domäne Link hinzufügen](media/manage-external-access-3.png)<span data-ttu-id="9ebbb-177">.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-177"></span></span>

   <span data-ttu-id="9ebbb-178">Der Bereich **Domäne hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-178">The **Add a domain** pane appears.</span></span>

    ![Screenshot des Hinzufügen einer Domäne-Bereich](media/manage-external-access-4.png)<span data-ttu-id="9ebbb-180">.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-180"></span></span>


3. <span data-ttu-id="9ebbb-181">Geben Sie den Namen der Domäne, klicken Sie unter **Hinzufügen einer Domäne**; Geben Sie beispielsweise "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="9ebbb-181">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="9ebbb-182">Wählen Sie **zugelassen** oder **blockiert**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-182">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="9ebbb-183">Sie können diese Einstellung jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-183">You can change this setting at any time.</span></span>

2. <span data-ttu-id="9ebbb-184">Wählen Sie **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-184">Select **Done**.</span></span>

<span data-ttu-id="9ebbb-185">Nachdem Sie eine Domäne hinzugefügt haben, sehen Sie den Domänennamen und den Status der Liste der Domänen auf der Seite externen Zugriff hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="9ebbb-185">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="9ebbb-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9ebbb-186">More information</span></span>

<span data-ttu-id="9ebbb-187">Informationen über Gast in Microsoft-Teams finden Sie unter [Manage Gast Access in Microsoft-Teams](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="9ebbb-187">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>