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
ms.openlocfilehash: 09a6ec1f60ca4bfc39dbeb5ba1829330c3413560
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925358"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="315d0-103">Checkliste für Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="315d0-103">Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="315d0-104">Verwenden Sie diese Checkliste, damit Sie das Feature "Gastzugriff" in Microsoft Teams entsprechend den Einstellungen Ihrer Organisation aktivieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="315d0-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="315d0-105">Einschränkungen für die Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="315d0-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="315d0-106">Grundlegendes zu den Einschränkungen für Gäste</span><span class="sxs-lookup"><span data-stu-id="315d0-106">Understand the limitations for guests</span></span>

<span data-ttu-id="315d0-107">Die Gast Erfahrung hat Einschränkungen durch Design.</span><span class="sxs-lookup"><span data-stu-id="315d0-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="315d0-108">Stellen Sie sicher, dass Sie die Gastfreundlichkeit verstehen, damit Sie nicht versuchen, etwas zu beheben, das kein Problem ist.</span><span class="sxs-lookup"><span data-stu-id="315d0-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="315d0-109">Nachfolgend finden Sie eine Liste mit einigen Funktionen, die einem Gast in Microsoft Teams nicht zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="315d0-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="315d0-110">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="315d0-110">OneDrive for Business</span></span>
- <span data-ttu-id="315d0-111">Personen suchen außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="315d0-111">People search outside of Teams</span></span>
- <span data-ttu-id="315d0-112">Kalender, geplante Besprechungen oder Besprechungs Details</span><span class="sxs-lookup"><span data-stu-id="315d0-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="315d0-113">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="315d0-113">PSTN</span></span>
- <span data-ttu-id="315d0-114">Organigramm</span><span class="sxs-lookup"><span data-stu-id="315d0-114">Organization chart</span></span>
- <span data-ttu-id="315d0-115">Erstellen oder Überarbeiten eines Teams</span><span class="sxs-lookup"><span data-stu-id="315d0-115">Create or revise a team</span></span>
- <span data-ttu-id="315d0-116">Suchen nach einem Team</span><span class="sxs-lookup"><span data-stu-id="315d0-116">Browse for a team</span></span>
- <span data-ttu-id="315d0-117">Hochladen von Dateien in einen Chat zwischen zwei Personen</span><span class="sxs-lookup"><span data-stu-id="315d0-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="315d0-118">Gäste können weiterhin nach Benutzern (außerhalb Ihres Teams) suchen und diese finden, wenn Sie die vollständige e-Mail-ID des Benutzers kennen.</span><span class="sxs-lookup"><span data-stu-id="315d0-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="315d0-119">Um dies zu verhindern, können IT-Administratoren Muster wie [Bereichs Verzeichnissuche](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) verwenden, die die Möglichkeit haben, Gäste in Ihre eigene virtuelle GAL zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="315d0-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/en-us/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="315d0-120">Weitere Informationen finden Sie unter [Was ist die Gastfreundlichkeit](guest-experience.md) und [Gastzugriff in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6)?</span><span class="sxs-lookup"><span data-stu-id="315d0-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="315d0-121">Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich</span><span class="sxs-lookup"><span data-stu-id="315d0-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="315d0-122">Zurzeit unterstützt Microsoft Teams die Rolle gastinviter nicht.</span><span class="sxs-lookup"><span data-stu-id="315d0-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="315d0-123">Die Umschaltfläche "Mitglieder können einladen" muss mindestens auf "Ja" gesetzt sein, damit Gastzugriff in Microsoft Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="315d0-123">At a minimum the "members can invite" toggle must be set to "Yes" for guest access to work in Microsoft Teams.</span></span> <span data-ttu-id="315d0-124">Wenn Sie "Mitglieder können einladen" auf "Nein" festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gast Einladungen in Ihrem Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="315d0-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="315d0-125">Nachdem sich die Gäste im Verzeichnis befinden, können Sie Teams von Mitgliedern des nicht-Administrators hinzugefügt werden, die Teambesitzer sind.</span><span class="sxs-lookup"><span data-stu-id="315d0-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="315d0-126">Wenn Ihre Gäste Lizenzfehler sehen</span><span class="sxs-lookup"><span data-stu-id="315d0-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="315d0-127">Der Gastzugriff in Microsoft Teams verwendet Azure Active Directory (Azure AD) Business to Business (B2B) und sein Lizenzierungsmodell.</span><span class="sxs-lookup"><span data-stu-id="315d0-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="315d0-128">Wenn Lizenzierungsfehler angezeigt werden, lesen Sie unbedingt die B2B- [Lizenzierungs Anleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , um die Lizenzierungsanforderungen Ihrer Organisation zu verstehen, damit Ihre Benutzer Gäste in Ihre Organisation einladen können.</span><span class="sxs-lookup"><span data-stu-id="315d0-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="315d0-129">Ein paar Dinge, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="315d0-129">A few things to remember:</span></span>

- <span data-ttu-id="315d0-130">Gäste sind Benutzer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="315d0-130">Guests are users outside your organization.</span></span> <span data-ttu-id="315d0-131">Ihre Mitarbeiter, Onsite-Vertragspartner, vor-Ort-Agents usw. können nicht als Gäste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="315d0-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="315d0-132">Das gleiche gilt für Ihre Affiliates.</span><span class="sxs-lookup"><span data-stu-id="315d0-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="315d0-133">Gast Lizenzen werden gegen die einladende Organisation gezählt.</span><span class="sxs-lookup"><span data-stu-id="315d0-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="315d0-134">Bedenken Sie dies, wenn Sie die Anzahl der benötigten Lizenzen berechnen.</span><span class="sxs-lookup"><span data-stu-id="315d0-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="315d0-135">Lizenzen werden für Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="315d0-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="315d0-136">□ Schritt 1: Konfigurieren von Einstellungen in Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="315d0-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="315d0-137">Anmelden beim Azure- [Portal](https://portal.azure.com) als mandantenadministrator.</span><span class="sxs-lookup"><span data-stu-id="315d0-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="315d0-138">Wählen Sie **Azure Active Directory** > \*\*\*\* > -Benutzer**Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="315d0-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="315d0-139">Wählen Sie unter **externe Benutzer**die Option Einstellungen für die **externe Zusammenarbeit verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="315d0-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="315d0-140">Die **Einstellungen für die externe Zusammenarbeit** sind auch auf der Seite " **organisatorische Beziehungen** " verfügbar.</span><span class="sxs-lookup"><span data-stu-id="315d0-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="315d0-141">Wechseln Sie in Azure Active Directory unter **Verwalten**zu**Einstellungen**für **Organisationsbeziehungen** > .</span><span class="sxs-lookup"><span data-stu-id="315d0-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="315d0-142">Wählen Sie auf der Seite Einstellungen für die **externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="315d0-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="315d0-143">**Gastbenutzer Berechtigungen sind limitiert**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="315d0-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="315d0-144">Wählen Sie **Ja** aus, um Gäste aus bestimmten Verzeichnisaufgaben wie dem Aufzählen von Benutzern, Gruppen oder anderen Verzeichnis Ressourcen zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="315d0-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="315d0-145">Wählen Sie **Nein** aus, um den Gästen denselben Zugriff auf Verzeichnisdaten wie reguläre Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="315d0-145">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="315d0-146">**Administratoren und Benutzer in der Rolle gastinviter können Folgendes einladen**: damit Administratoren und Benutzer in der Rolle "gastinviter" Gäste einladen können, setzen Sie diese Richtlinie auf " **Ja**".</span><span class="sxs-lookup"><span data-stu-id="315d0-146">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="315d0-147">**Mitglieder können Folgendes einladen**: damit nicht-Administrator-Mitglieder Ihres Verzeichnisses Gäste einladen können, setzen Sie diese Richtlinie auf " **Ja**".</span><span class="sxs-lookup"><span data-stu-id="315d0-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="315d0-148">Wenn Sie festlegen, dass Mitglieder auf **Nein** **einladen** und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren können, können Administratoren Gast Einladungen in Ihrem Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="315d0-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="315d0-149">Nachdem sich die Gäste im Verzeichnis befinden, können Sie Teams von Mitgliedern des nicht-Administrators hinzugefügt werden, die Teambesitzer sind.</span><span class="sxs-lookup"><span data-stu-id="315d0-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="315d0-150">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="315d0-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="315d0-151">**Gäste können Folgendes einladen**: damit Gäste andere Gäste einladen können, setzen Sie diese Richtlinie auf " **Ja**".</span><span class="sxs-lookup"><span data-stu-id="315d0-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="315d0-152">**Aktivieren der einmaligen e-Mail-Kennung für Gäste (Preview)**: Weitere Informationen zur einmaligen Kennungs Funktion finden Sie unter e-Mail-einmal [Kennungs Authentifizierung (Preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="315d0-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="315d0-153">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [zulassen oder Blockieren von Einladungen an B2B-Benutzer aus bestimmten Organisationen](allow-deny-list.md).</span><span class="sxs-lookup"><span data-stu-id="315d0-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](allow-deny-list.md).</span></span>

## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="315d0-154">□ Schritt 2: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="315d0-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="315d0-155">Wechseln Sie im Microsoft 365 Admin Center zu **Settings** > **Services #a0 Add-ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="315d0-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="315d0-156">Stellen Sie sicher, dass **Gruppenmitglieder außerhalb des Organisations Zugriffsgruppen-Inhalts** auf **ein**gesetzt sind.</span><span class="sxs-lookup"><span data-stu-id="315d0-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="315d0-157">Wenn diese Einstellung deaktiviert ist, können die Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="315d0-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="315d0-158">Stellen Sie sicher, dass **Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **ein**gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="315d0-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="315d0-159">Wenn diese Einstellung deaktiviert ist, können Team Besitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="315d0-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="315d0-160">Diese Einstellung muss mindestens aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="315d0-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![Screenshot der Office 365 Groups-Umschalter](media/guest-access-checklist-office365.png)

<span data-ttu-id="315d0-162">Ausführliche Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="315d0-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="315d0-163">□ Schritt 3: Aktivieren des Gastzugriffs auf Mandantenebene</span><span class="sxs-lookup"><span data-stu-id="315d0-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="315d0-164">Sie müssen mindestens den Gastzugriff für Microsoft Teams unter dem **Microsoft Teams Admin Center**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="315d0-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="315d0-165">Wählen Sie im Team Admin Center die Option **organisationsweite Einstellungen** > **Gastzugriff**aus.</span><span class="sxs-lookup"><span data-stu-id="315d0-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="315d0-166">Legen Sie die Option **Gastzugriff in Microsoft Teams zulassen** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="315d0-166">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="315d0-168">Konfigurieren Sie auf dieser Seite alle anderen von Ihnen gewünschten Gast Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="315d0-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="315d0-169">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="315d0-169">Click **Save**.</span></span>

<span data-ttu-id="315d0-170">Ausführliche Anweisungen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="315d0-170">For detailed instructions, see [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="315d0-171">□ Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="315d0-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="315d0-172">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="315d0-172">Make sure that users can add guests.</span></span> <span data-ttu-id="315d0-173">Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="315d0-173">Here's how:</span></span>

1. <span data-ttu-id="315d0-174">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit #a0 Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="315d0-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel für Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="315d0-176">Wählen Sie in **Freigabe**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="315d0-176">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="315d0-178">Legen Sie zulassen, dass **Benutzer dieser Organisation neue Gäste hinzufügen** auf **ein**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="315d0-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="315d0-180">Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="315d0-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="315d0-181">□ Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="315d0-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="315d0-182">Anmelden beim Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="315d0-182">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="315d0-183">Klicken Sie auf **Admin Center**, und wählen Sie dann **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="315d0-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="315d0-184">Wählen Sie im SharePoint Admin Center die Option **Freigabe**aus.</span><span class="sxs-lookup"><span data-stu-id="315d0-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="315d0-185">Stellen Sie sicher, dass die Option " **Freigabe außerhalb Ihrer Organisation nicht zulassen** " *nicht* aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="315d0-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter für SparePoint Online-Einstellungen.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="315d0-187">□ Schritt 6: Aktivieren bestimmter Einstellungen für Kanäle</span><span class="sxs-lookup"><span data-stu-id="315d0-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="315d0-188">Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, damit Gäste Kanäle erstellen, aktualisieren und löschen können.</span><span class="sxs-lookup"><span data-stu-id="315d0-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="315d0-189">Zusätzlich zu Administratoren können Teambesitzer diese Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="315d0-189">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot zeigt ein Beispiel für eine Umschaltfläche für Team/Kanal-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="315d0-191">Weitere Informationen, einschließlich Anleitungen zu Videos, finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="315d0-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="315d0-192">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="315d0-192">Troubleshooting</span></span>

<span data-ttu-id="315d0-193">Wenn Sie Probleme beim Hinzufügen von Gästen in Microsoft Teams haben, lesen Sie den [Leitfaden zur Problembehandlung für Gastzugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="315d0-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


