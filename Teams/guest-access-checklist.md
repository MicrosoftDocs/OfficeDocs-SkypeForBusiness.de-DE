---
title: Prüfliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3498c3eaf81b2b8be7513ec083957f89d3f7fd00
ms.sourcegitcommit: 2f12e0d4dc2ef8e848a63bf3a9c63e07e4439cf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "35588079"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="69b6a-103">Checkliste für Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="69b6a-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="69b6a-104">Verwenden Sie diese Checkliste, damit Sie das Feature "Gastzugriff" in Microsoft Teams entsprechend den Einstellungen Ihrer Organisation aktivieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="69b6a-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="69b6a-105">Einschränkungen für die Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="69b6a-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="69b6a-106">Grundlegendes zu den Einschränkungen für Gäste</span><span class="sxs-lookup"><span data-stu-id="69b6a-106">Understand the limitations for guests</span></span>

<span data-ttu-id="69b6a-107">Die Gast Erfahrung hat Einschränkungen durch Design.</span><span class="sxs-lookup"><span data-stu-id="69b6a-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="69b6a-108">Stellen Sie sicher, dass Sie die Gastfreundlichkeit verstehen, damit Sie nicht versuchen, etwas zu beheben, das kein Problem ist.</span><span class="sxs-lookup"><span data-stu-id="69b6a-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="69b6a-109">Nachfolgend finden Sie eine Liste mit einigen Funktionen, die einem Gast in Microsoft Teams nicht zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="69b6a-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="69b6a-110">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="69b6a-110">OneDrive for Business</span></span>
- <span data-ttu-id="69b6a-111">Personen suchen außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="69b6a-111">People search outside of Teams</span></span>
- <span data-ttu-id="69b6a-112">Kalender, geplante Besprechungen oder Besprechungs Details</span><span class="sxs-lookup"><span data-stu-id="69b6a-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="69b6a-113">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="69b6a-113">PSTN</span></span>
- <span data-ttu-id="69b6a-114">Organigramm</span><span class="sxs-lookup"><span data-stu-id="69b6a-114">Organization chart</span></span>
- <span data-ttu-id="69b6a-115">Erstellen oder Überarbeiten eines Teams</span><span class="sxs-lookup"><span data-stu-id="69b6a-115">Create or revise a team</span></span>
- <span data-ttu-id="69b6a-116">Suchen nach einem Team</span><span class="sxs-lookup"><span data-stu-id="69b6a-116">Browse for a team</span></span>
- <span data-ttu-id="69b6a-117">Hochladen von Dateien in einen Chat zwischen zwei Personen</span><span class="sxs-lookup"><span data-stu-id="69b6a-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="69b6a-118">Gäste können weiterhin nach Benutzern (außerhalb Ihres Teams) suchen und diese finden, wenn Sie die vollständige e-Mail-ID des Benutzers kennen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="69b6a-119">Um dies zu verhindern, können IT-Administratoren Muster wie [Bereichs Verzeichnissuche](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) verwenden, die die Möglichkeit haben, Gäste in Ihre eigene virtuelle GAL zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="69b6a-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="69b6a-120">Weitere Informationen finden Sie unter [Was ist die Gastfreundlichkeit](guest-experience.md) und [Gastzugriff in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)?</span><span class="sxs-lookup"><span data-stu-id="69b6a-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="69b6a-121">Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich</span><span class="sxs-lookup"><span data-stu-id="69b6a-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="69b6a-122">Zurzeit unterstützt Microsoft Teams die Rolle gastinviter nicht.</span><span class="sxs-lookup"><span data-stu-id="69b6a-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="69b6a-123">Die Umschaltfläche "Mitglieder können einladen" muss mindestens auf "Ja" gesetzt sein, damit Gastzugriff in Microsoft Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="69b6a-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="69b6a-124">Wenn Sie "Mitglieder können einladen" auf "Nein" festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gast Einladungen in Ihrem Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="69b6a-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="69b6a-125">Nachdem sich die Gäste im Verzeichnis befinden, können Sie Teams von Mitgliedern des nicht-Administrators hinzugefügt werden, die Teambesitzer sind.</span><span class="sxs-lookup"><span data-stu-id="69b6a-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="69b6a-126">Wenn Ihre Gäste Lizenzfehler sehen</span><span class="sxs-lookup"><span data-stu-id="69b6a-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="69b6a-127">Der Gastzugriff in Microsoft Teams verwendet Azure Active Directory (Azure AD) Business to Business (B2B) und sein Lizenzierungsmodell.</span><span class="sxs-lookup"><span data-stu-id="69b6a-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="69b6a-128">Wenn Lizenzierungsfehler angezeigt werden, lesen Sie unbedingt die B2B- [Lizenzierungs Anleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , um die Lizenzierungsanforderungen Ihrer Organisation zu verstehen, damit Ihre Benutzer Gäste in Ihre Organisation einladen können.</span><span class="sxs-lookup"><span data-stu-id="69b6a-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="69b6a-129">Ein paar Dinge, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="69b6a-129">A few things to remember:</span></span>

- <span data-ttu-id="69b6a-130">Für jede kostenpflichtige Azure AD-Lizenz, die Sie einem Benutzer zuweisen, können Ihre Benutzer bis zu fünf Gastbenutzer unter dem Kontingent für externe Benutzer einladen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-130">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="69b6a-131">Gäste sind Benutzer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="69b6a-131">Guests are users outside your organization.</span></span> <span data-ttu-id="69b6a-132">Ihre Mitarbeiter, Onsite-Vertragspartner, vor-Ort-Agents usw. können nicht als Gäste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="69b6a-132">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="69b6a-133">Das gleiche gilt für Ihre Affiliates.</span><span class="sxs-lookup"><span data-stu-id="69b6a-133">The same applies to your affiliates.</span></span>
- <span data-ttu-id="69b6a-134">Gast Lizenzen werden gegen die einladende Organisation gezählt.</span><span class="sxs-lookup"><span data-stu-id="69b6a-134">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="69b6a-135">Bedenken Sie dies, wenn Sie die Anzahl der benötigten Lizenzen berechnen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-135">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="69b6a-136">Lizenzen werden für Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="69b6a-136">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="69b6a-137">□ Schritt 1: Konfigurieren von Einstellungen in Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="69b6a-137">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="69b6a-138">Anmelden beim Azure- [Portal](https://portal.azure.com) als mandantenadministrator.</span><span class="sxs-lookup"><span data-stu-id="69b6a-138">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="69b6a-139">Wählen Sie **Azure Active Directory** > \*\*\*\* > -Benutzer**Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="69b6a-139">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="69b6a-140">Wählen Sie unter **externe Benutzer**die Option Einstellungen für die **externe Zusammenarbeit verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="69b6a-140">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="69b6a-141">Die **Einstellungen für die externe Zusammenarbeit** sind auch auf der Seite " **organisatorische Beziehungen** " verfügbar.</span><span class="sxs-lookup"><span data-stu-id="69b6a-141">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="69b6a-142">Wechseln Sie in Azure Active Directory unter **Verwalten**zu**Einstellungen**für **Organisationsbeziehungen** > .</span><span class="sxs-lookup"><span data-stu-id="69b6a-142">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="69b6a-143">Wählen Sie auf der Seite Einstellungen für die **externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="69b6a-143">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

   ![Einstellungen für die externe Zusammenarbeit](media/control-who-to-invite.png)

  - <span data-ttu-id="69b6a-145">**Gastbenutzer Berechtigungen sind limitiert**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="69b6a-145">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="69b6a-146">Wählen Sie **Ja** aus, um Gäste aus bestimmten Verzeichnisaufgaben wie dem Aufzählen von Benutzern, Gruppen oder anderen Verzeichnis Ressourcen zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="69b6a-146">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="69b6a-147">Wählen Sie **Nein** aus, um den Gästen denselben Zugriff auf Verzeichnisdaten wie reguläre Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="69b6a-147">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="69b6a-148">**Administratoren und Benutzer in der Rolle gastinviter können Folgendes einladen**: damit Administratoren und Benutzer in der Rolle "gastinviter" Gäste einladen können, setzen Sie diese Richtlinie auf " **Ja**".</span><span class="sxs-lookup"><span data-stu-id="69b6a-148">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="69b6a-149">**Mitglieder können Folgendes einladen**: damit nicht-Administrator-Mitglieder Ihres Verzeichnisses Gäste einladen können, setzen Sie diese Richtlinie auf " **Ja**".</span><span class="sxs-lookup"><span data-stu-id="69b6a-149">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="69b6a-150">Wenn Sie festlegen, dass Mitglieder auf **Nein** **einladen** und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren können, können Administratoren Gast Einladungen in Ihrem Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="69b6a-150">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="69b6a-151">Nachdem sich die Gäste im Verzeichnis befinden, können Sie Teams von Mitgliedern des nicht-Administrators hinzugefügt werden, die Teambesitzer sind.</span><span class="sxs-lookup"><span data-stu-id="69b6a-151">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="69b6a-152">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="69b6a-152">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="69b6a-153">**Gäste können Folgendes einladen**: damit Gäste andere Gäste einladen können, setzen Sie diese Richtlinie auf " **Ja**".</span><span class="sxs-lookup"><span data-stu-id="69b6a-153">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="69b6a-154">**Aktivieren der einmaligen e-Mail-Kennung für Gäste (Preview)**: Weitere Informationen zur einmaligen Kennungs Funktion finden Sie unter e-Mail-einmal [Kennungs Authentifizierung (Preview)](one-time-passcode.md).</span><span class="sxs-lookup"><span data-stu-id="69b6a-154">**Enable Email One-Time Passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](one-time-passcode.md).</span></span>
   - <span data-ttu-id="69b6a-155">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](allow-deny-list.md).</span><span class="sxs-lookup"><span data-stu-id="69b6a-155">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="69b6a-156">□ Schritt 2: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="69b6a-156">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="69b6a-157">Wechseln Sie im Microsoft 365 Admin Center zu **Settings** > **Services #a0 Add-ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="69b6a-157">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="69b6a-158">Stellen Sie sicher, dass **Gruppenmitglieder außerhalb des Organisations Zugriffsgruppen-Inhalts** auf **ein**gesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="69b6a-158">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="69b6a-159">Wenn diese Einstellung deaktiviert ist, können die Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-159">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="69b6a-160">Stellen Sie sicher, dass **Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **ein**gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="69b6a-160">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="69b6a-161">Wenn diese Einstellung deaktiviert ist, können Team Besitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-161">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="69b6a-162">Diese Einstellung muss mindestens aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-162">At a minimum, this setting must be On to support guest access.</span></span>

     ![Screenshot der Office 365 Groups-Umschalter](media/guest-access-checklist-office365.png)

<span data-ttu-id="69b6a-164">Ausführliche Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="69b6a-164">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="69b6a-165">□ Schritt 3: Aktivieren des Gastzugriffs auf Mandantenebene</span><span class="sxs-lookup"><span data-stu-id="69b6a-165">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="69b6a-166">Sie müssen mindestens den Gastzugriff für Microsoft Teams unter dem **Microsoft Teams Admin Center**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="69b6a-166">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="69b6a-167">Wählen Sie im Team Admin Center die Option **organisationsweite Einstellungen** > **Gastzugriff**aus.</span><span class="sxs-lookup"><span data-stu-id="69b6a-167">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="69b6a-168">Legen Sie die Option **Gastzugriff in Microsoft Teams zulassen** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="69b6a-168">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="69b6a-170">Konfigurieren Sie auf dieser Seite alle anderen von Ihnen gewünschten Gast Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="69b6a-170">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="69b6a-171">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="69b6a-171">Click **Save**.</span></span>

<span data-ttu-id="69b6a-172">Ausführliche Anweisungen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="69b6a-172">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="69b6a-173">□ Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="69b6a-173">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="69b6a-174">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="69b6a-174">Make sure that users can add guests.</span></span> <span data-ttu-id="69b6a-175">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="69b6a-175">Here's how:</span></span>

1. <span data-ttu-id="69b6a-176">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit #a0 Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="69b6a-176">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel für Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="69b6a-178">Wählen Sie in **Freigabe**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="69b6a-178">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="69b6a-180">Legen Sie zulassen, dass **Benutzer dieser Organisation neue Gäste hinzufügen** auf **ein**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="69b6a-180">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="69b6a-182">Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="69b6a-182">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="69b6a-183">□ Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="69b6a-183">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="69b6a-184">Anmelden beim Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="69b6a-184">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="69b6a-185">Klicken Sie auf **Admin Center**, und wählen Sie dann **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="69b6a-185">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="69b6a-186">Wählen Sie im SharePoint Admin Center die Option **Freigabe**aus.</span><span class="sxs-lookup"><span data-stu-id="69b6a-186">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="69b6a-187">Stellen Sie sicher, dass die Option " **Freigabe außerhalb Ihrer Organisation nicht zulassen** " *nicht* aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="69b6a-187">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter für SparePoint Online-Einstellungen.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="69b6a-189">□ Schritt 6: Aktivieren bestimmter Einstellungen für Kanäle</span><span class="sxs-lookup"><span data-stu-id="69b6a-189">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="69b6a-190">Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, damit Gäste Kanäle erstellen, aktualisieren und löschen können.</span><span class="sxs-lookup"><span data-stu-id="69b6a-190">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="69b6a-191">Zusätzlich zu Administratoren können Teambesitzer diese Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="69b6a-191">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Team/Kanal-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="69b6a-193">Weitere Informationen, einschließlich Anleitungen zu Videos, finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="69b6a-193">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="69b6a-194">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="69b6a-194">Troubleshooting</span></span>

<span data-ttu-id="69b6a-195">Wenn Sie Probleme beim Hinzufügen von Gästen in Microsoft Teams haben, lesen Sie den [Leitfaden zur Problembehandlung für Gastzugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="69b6a-195">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


