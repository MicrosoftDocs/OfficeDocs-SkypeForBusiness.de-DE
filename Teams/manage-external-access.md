---
title: Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/30/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Ihr IT-Administrator kann den externen Zugriff für andere Domänen (Federation) konfigurieren, damit Benutzer aus diesen Domänen an Teams teilnehmen können.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6a3dc6016eb52d58e82e9e9022d1bb8575404b
ms.sourcegitcommit: b9e7a11d8332a029a4f1cd4e396787f5a74f0a44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "34702720"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a><span data-ttu-id="64038-103">Verwaltung des externen Zugriffs (Verbund) in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="64038-103">Manage external access (federation) in Microsoft Teams</span></span>
======================================================

<span data-ttu-id="64038-104">Mit Microsoft Teams externer Zugriff können Benutzer aus anderen Domänen an ihren Chats und anrufen teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="64038-104">With Microsoft Teams external access, users from other domains can participate in your chats and calls.</span></span> <span data-ttu-id="64038-105">Sie können auch externen Benutzern, die weiterhin Skype for Business Online oder Skype for Business on-Prem verwenden, die Teilnahme erlauben.</span><span class="sxs-lookup"><span data-stu-id="64038-105">You can also allow external users who are still using Skype for Business Online or Skype for Business on-prem to participate.</span></span> 

<span data-ttu-id="64038-106">Der externe Zugriff (Föderation) und Gastzugriff unterscheiden sich von den folgenden:</span><span class="sxs-lookup"><span data-stu-id="64038-106">External access (federation) and guest access are different:</span></span>

- <span data-ttu-id="64038-107">Gastzugriff gewährt einer einzelnen Person Zugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="64038-107">Guest access gives access permission to an individual.</span></span> <span data-ttu-id="64038-108">Externer Zugriff gewährt einer gesamten Domäne Zugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="64038-108">External access gives access permission to an entire domain.</span></span>

- <span data-ttu-id="64038-109">Der Gastzugriff, nachdem er von einem Teambesitzer gewährt wurde, ermöglicht es einem Gast, auf [Ressourcen](guest-experience.md)wie Kanal Diskussionen und Dateien für ein bestimmtes Team zuzugreifen und mit anderen Benutzern in dem Team zu chatten, zu dem Sie eingeladen wurden.</span><span class="sxs-lookup"><span data-stu-id="64038-109">Guest access, once granted by a team owner, allows a guest to [access resources](guest-experience.md), such as channel discussions and files, for a specific team, and chat with other users in the team they have been invited to.</span></span> <span data-ttu-id="64038-110">Beim externen Zugriff (Federated-Chat) haben die Teilnehmer des externen Chats keinen Zugriff auf die Teams oder Teamressourcen der einladenden Organisation.</span><span class="sxs-lookup"><span data-stu-id="64038-110">With external access (federated chat), the external chat participants have no access to the inviting organization’s teams or team resources.</span></span> <span data-ttu-id="64038-111">Sie können nur an einem einzigen Partner-Chat teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="64038-111">They can only participate in one-on-one federated chat.</span></span> <span data-ttu-id="64038-112">Mandantenadministratoren können zwischen den beiden Kommunikationsoptionen wählen, je nachdem, welche Ebene der Zusammenarbeit für die externe Partei erwünscht ist.</span><span class="sxs-lookup"><span data-stu-id="64038-112">Tenant admins can choose between the two communication options depending on which level of collaboration is desirable with the external party.</span></span> <span data-ttu-id="64038-113">Administratoren können je nach Ihren organisatorischen Anforderungen entweder Ansätze oder beides auswählen, aber wir empfehlen, den Gastzugriff für eine umfassendere, kollaborative Teams-Erfahrung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="64038-113">Admins can choose either approaches or both, depending on their organizational needs, but we recommend enabling guest access for a fuller, collaborative Teams experience.</span></span> 

<span data-ttu-id="64038-114">In der folgenden Tabelle finden Sie eine Übersicht über die Features für den externen und den Gastzugriff.</span><span class="sxs-lookup"><span data-stu-id="64038-114">See the following table for a comparison of external and guest access features.</span></span>

| <span data-ttu-id="64038-115">Feature</span><span class="sxs-lookup"><span data-stu-id="64038-115">Feature</span></span> | <span data-ttu-id="64038-116">Benutzer für externen Zugriff</span><span class="sxs-lookup"><span data-stu-id="64038-116">External access users</span></span> | <span data-ttu-id="64038-117">Gastzugriff-Benutzer</span><span class="sxs-lookup"><span data-stu-id="64038-117">Guest access users</span></span> |
|---------|-----------------------|--------------------|
| <span data-ttu-id="64038-118">Der Benutzer kann mit jemandem in einem anderen Unternehmen chatten.</span><span class="sxs-lookup"><span data-stu-id="64038-118">User can chat with someone in another company</span></span> | <span data-ttu-id="64038-119">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-119">Yes</span></span> |<span data-ttu-id="64038-120">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-120">Yes</span></span> |
| <span data-ttu-id="64038-121">Der Benutzer kann jemanden in einem anderen Unternehmen anrufen</span><span class="sxs-lookup"><span data-stu-id="64038-121">User can call someone in another company</span></span> | <span data-ttu-id="64038-122">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-122">Yes</span></span> | <span data-ttu-id="64038-123">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-123">Yes</span></span> |
| <span data-ttu-id="64038-124">Der Benutzer kann sehen, ob jemand aus einem anderen Unternehmen für Anrufe oder Chats zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="64038-124">User can see if someone from another company is available for call or chat</span></span> | <span data-ttu-id="64038-125">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-125">Yes</span></span> | <span data-ttu-id="64038-126">Ja<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="64038-126">Yes<sup>1</sup></span></span> |
| <span data-ttu-id="64038-127">Benutzer kann über externe Mandanten nach Benutzern suchen</span><span class="sxs-lookup"><span data-stu-id="64038-127">User can search for users across external tenants</span></span> | <span data-ttu-id="64038-128">Ja<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="64038-128">Yes<sup>2</sup></span></span> | <span data-ttu-id="64038-129">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-129">No</span></span> |
| <span data-ttu-id="64038-130">Benutzer kann Dateien freigeben</span><span class="sxs-lookup"><span data-stu-id="64038-130">User can share files</span></span> | <span data-ttu-id="64038-131">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-131">No</span></span> | <span data-ttu-id="64038-132">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-132">Yes</span></span> |
| <span data-ttu-id="64038-133">Benutzer kann auf Teamressourcen zugreifen</span><span class="sxs-lookup"><span data-stu-id="64038-133">User can access Teams resources</span></span> | <span data-ttu-id="64038-134">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-134">No</span></span> | <span data-ttu-id="64038-135">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-135">Yes</span></span> |
| <span data-ttu-id="64038-136">Benutzer kann zu einem Gruppen-Chat hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="64038-136">User can be added to a group chat</span></span> | <span data-ttu-id="64038-137">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-137">No</span></span> | <span data-ttu-id="64038-138">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-138">Yes</span></span> |
| <span data-ttu-id="64038-139">Benutzer kann zu einer Besprechung hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="64038-139">User can be added to a meeting</span></span> | <span data-ttu-id="64038-140">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-140">Yes</span></span> | <span data-ttu-id="64038-141">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-141">Yes</span></span> |
| <span data-ttu-id="64038-142">Zusätzliche Benutzer können einem Chat mit einem externen Benutzer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="64038-142">Additional users can be added to a chat with an external user</span></span> | <span data-ttu-id="64038-143">Nr.<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="64038-143">No<sup>3</sup></span></span> | <span data-ttu-id="64038-144">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="64038-144">N/A</span></span> |
| <span data-ttu-id="64038-145">Der Benutzer wird als externer Partner identifiziert</span><span class="sxs-lookup"><span data-stu-id="64038-145">User is identified as an external party</span></span> | <span data-ttu-id="64038-146">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-146">Yes</span></span> | <span data-ttu-id="64038-147">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-147">Yes</span></span> |
| <span data-ttu-id="64038-148">Anwesenheit wird angezeigt</span><span class="sxs-lookup"><span data-stu-id="64038-148">Presence is displayed</span></span> | <span data-ttu-id="64038-149">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-149">Yes</span></span> | <span data-ttu-id="64038-150">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-150">Yes</span></span> |
| <span data-ttu-id="64038-151">Abwesenheitsnachricht wird angezeigt</span><span class="sxs-lookup"><span data-stu-id="64038-151">Out of office message is shown</span></span> | <span data-ttu-id="64038-152">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-152">No</span></span> | <span data-ttu-id="64038-153">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-153">Yes</span></span> |
| <span data-ttu-id="64038-154">Der einzelne Benutzer kann blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="64038-154">Individual user can be blocked</span></span> | <span data-ttu-id="64038-155">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-155">No</span></span> | <span data-ttu-id="64038-156">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-156">Yes</span></span> |
| <span data-ttu-id="64038-157">@Mentions werden unterstützt</span><span class="sxs-lookup"><span data-stu-id="64038-157">@mentions are supported</span></span> | <span data-ttu-id="64038-158">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-158">No</span></span> | <span data-ttu-id="64038-159">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-159">Yes</span></span> |
| <span data-ttu-id="64038-160">Private Anrufe tätigen</span><span class="sxs-lookup"><span data-stu-id="64038-160">Make Private Calls</span></span> | <span data-ttu-id="64038-161">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-161">Yes</span></span> | <span data-ttu-id="64038-162">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-162">Yes</span></span> |
| <span data-ttu-id="64038-163">IP-Video zulassen</span><span class="sxs-lookup"><span data-stu-id="64038-163">Allow IP Video</span></span> | <span data-ttu-id="64038-164">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-164">Yes</span></span> | <span data-ttu-id="64038-165">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-165">Yes</span></span> |
| <span data-ttu-id="64038-166">Bildschirmfreigabe Modus</span><span class="sxs-lookup"><span data-stu-id="64038-166">Screen Sharing Mode</span></span> | <span data-ttu-id="64038-167">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-167">Yes</span></span> | <span data-ttu-id="64038-168">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-168">Yes</span></span> |
| <span data-ttu-id="64038-169">Sofortbesprechung zulassen</span><span class="sxs-lookup"><span data-stu-id="64038-169">Allow Meet Now</span></span> | <span data-ttu-id="64038-170">Nein</span><span class="sxs-lookup"><span data-stu-id="64038-170">No</span></span> | <span data-ttu-id="64038-171">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-171">Yes</span></span> |
| <span data-ttu-id="64038-172">Bearbeiten von gesendeten Nachrichten</span><span class="sxs-lookup"><span data-stu-id="64038-172">Edit Sent Messages</span></span> | <span data-ttu-id="64038-173">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-173">Yes</span></span> | <span data-ttu-id="64038-174">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-174">Yes</span></span> |
| <span data-ttu-id="64038-175">Kann gesendete Nachrichten löschen</span><span class="sxs-lookup"><span data-stu-id="64038-175">Can Delete Sent Messages</span></span> | <span data-ttu-id="64038-176">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-176">Yes</span></span> | <span data-ttu-id="64038-177">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-177">Yes</span></span> |
| <span data-ttu-id="64038-178">Verwenden von Giphy in einer Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="64038-178">Use Giphy In Conversation</span></span> | <span data-ttu-id="64038-179">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-179">Yes</span></span> | <span data-ttu-id="64038-180">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-180">Yes</span></span> |
| <span data-ttu-id="64038-181">Verwenden von Memen in einer Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="64038-181">Use Memes In Conversation</span></span> | <span data-ttu-id="64038-182">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-182">Yes</span></span> | <span data-ttu-id="64038-183">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-183">Yes</span></span> |
| <span data-ttu-id="64038-184">Verwenden von Aufklebern in einer Unterhaltung</span><span class="sxs-lookup"><span data-stu-id="64038-184">Use Stickers In Conversation</span></span> | <span data-ttu-id="64038-185">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-185">Yes</span></span> | <span data-ttu-id="64038-186">Ja</span><span class="sxs-lookup"><span data-stu-id="64038-186">Yes</span></span> |
||||

<span data-ttu-id="64038-187"><sup>1</sup> vorausgesetzt, dass der Benutzer als Gast hinzugefügt wurde und als Gast für den Gast Mandanten angemeldet ist.</span><span class="sxs-lookup"><span data-stu-id="64038-187"><sup>1</sup> Provided that the user has been added as a guest and is signed in as a guest to the guest tenant.</span></span><br>
<span data-ttu-id="64038-188"><sup>2</sup> nur per e-Mail oder SIP-Adresse (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="64038-188"><sup>2</sup> Only by email or Session Initiation Protocol (SIP) address.</span></span><br>
<span data-ttu-id="64038-189"><sup>3</sup> externer Chat (Federated) ist nur 1:1.</span><span class="sxs-lookup"><span data-stu-id="64038-189"><sup>3</sup> External (federated) chat is 1:1 only.</span></span>

> [!NOTE]
> <span data-ttu-id="64038-190">Weitere Informationen zu Gast Features und der Gast Erfahrung finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) und [der Art der Gast Erfahrung](https://docs.microsoft.com/microsoftteams/guest-experience).</span><span class="sxs-lookup"><span data-stu-id="64038-190">For more information on guest features and the guest experience, see [Turn on or off guest access to Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) and [What the guest experience is like](https://docs.microsoft.com/microsoftteams/guest-experience).</span></span>

## <a name="turn-on-or-turn-off-external-access-users-can-communicate-with-skype-for-business-and-teams-users"></a><span data-ttu-id="64038-191">Aktivieren oder Deaktivieren des externen Zugriffs (Benutzer können mit Skype for Business-und Teams-Benutzern kommunizieren)</span><span class="sxs-lookup"><span data-stu-id="64038-191">Turn on or turn off external access (Users can communicate with Skype for Business and Teams users)</span></span>

<span data-ttu-id="64038-192">Sie können die Microsoft Teams #a0 Skype for Business Admin Center verwenden, um den externen Zugriff zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="64038-192">You can use the Microsoft Teams & Skype for Business Admin Center to manage external access.</span></span>

1. <span data-ttu-id="64038-193">Wählen Sie im Microsoft Teams #a0 Skype for Business Admin Center die Option **organisationsweite Einstellungen** > **externer Zugriff**aus.</span><span class="sxs-lookup"><span data-stu-id="64038-193">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

     ![Screenshot der organisationsweiten Einstellungen für externen Zugriff](media/manage-external-access-1.png)<span data-ttu-id="64038-195">.</span><span class="sxs-lookup"><span data-stu-id="64038-195"></span></span>

2. <span data-ttu-id="64038-196">Aktivieren oder **Deaktivieren**Sie die **Benutzer können mit Skype for Business und Teams kommunizieren** . \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="64038-196">Toggle the **Users can communicate with Skype for Business and Teams users** switch to **On** or **Off**.</span></span>

     ![Screenshot des aktivierten externen Zugriffs Schalters](media/manage-external-access-2.png)<span data-ttu-id="64038-198">.</span><span class="sxs-lookup"><span data-stu-id="64038-198"></span></span>

3. <span data-ttu-id="64038-199">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="64038-199">Click **Save**.</span></span> 

## <a name="add-or-block-a-domain"></a><span data-ttu-id="64038-200">Hinzufügen oder blockieren einer Domäne</span><span class="sxs-lookup"><span data-stu-id="64038-200">Add or block a domain</span></span>

<span data-ttu-id="64038-201">Führen Sie die folgenden Schritte aus, um eine Domäne hinzuzufügen oder den externen Zugriff für eine Domäne zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="64038-201">Follow these steps to add a domain or turn off external access for a domain.</span></span>

1. <span data-ttu-id="64038-202">Wählen Sie im Microsoft Teams #a0 Skype for Business Admin Center die Option **organisationsweite Einstellungen** > **externer Zugriff**aus.</span><span class="sxs-lookup"><span data-stu-id="64038-202">In the Microsoft Teams & Skype for Business Admin Center, select **Org-wide settings** > **External access**.</span></span>

2. <span data-ttu-id="64038-203">Wählen Sie **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="64038-203">Select **Add a domain**.</span></span> 
 
    ![Screenshot der Seite ' externer Zugriff ' mit Link ' Domäne hinzufügen '](media/manage-external-access-3.png)<span data-ttu-id="64038-205">.</span><span class="sxs-lookup"><span data-stu-id="64038-205"></span></span>

   <span data-ttu-id="64038-206">Der Bereich **Domäne hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64038-206">The **Add a domain** pane appears.</span></span>

    ![Screenshot des Bereichs "Domäne hinzufügen"](media/manage-external-access-4.png)<span data-ttu-id="64038-208">.</span><span class="sxs-lookup"><span data-stu-id="64038-208"></span></span>


3. <span data-ttu-id="64038-209">Geben **Sie Unterdomäne hinzufügen**den Namen der Domäne ein. Geben Sie beispielsweise contoso.com ein.</span><span class="sxs-lookup"><span data-stu-id="64038-209">Under **Add a domain**, type the name of the domain; for example, type Contoso.com.</span></span>

4. <span data-ttu-id="64038-210">Wählen Sie **Zulässig** oder **Blockiert**.</span><span class="sxs-lookup"><span data-stu-id="64038-210">Select **Allowed** or **Blocked**.</span></span> <span data-ttu-id="64038-211">Sie können diese Einstellung jederzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="64038-211">You can change this setting at any time.</span></span>

2. <span data-ttu-id="64038-212">Wählen Sie **Fertig**aus.</span><span class="sxs-lookup"><span data-stu-id="64038-212">Select **Done**.</span></span>

<span data-ttu-id="64038-213">Nachdem Sie eine Domäne hinzugefügt haben, werden der Domänenname und der Status der Liste der Domänen auf der Seite "externer Zugriff" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64038-213">After you add a domain, you will see the domain name and status added to the list of domains on the External access page.</span></span>

## <a name="more-information"></a><span data-ttu-id="64038-214">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64038-214">More information</span></span>

<span data-ttu-id="64038-215">Informationen zum Gastzugriff in Microsoft Teams finden Sie unter [Verwalten des Gastzugriffs in Microsoft Teams](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="64038-215">For information about guest access in Microsoft Teams, see [Manage guest access in Microsoft Teams](manage-guests.md).</span></span>
