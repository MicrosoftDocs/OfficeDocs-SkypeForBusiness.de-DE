---
title: Checkliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/21/2019
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83cd25ed9f675f04f090255cbc387275c0dee90d
ms.sourcegitcommit: 5ec5df597614d402917e0585575dd69acda22172
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2019
ms.locfileid: "36253918"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="512cc-103">Checkliste für den Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="512cc-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="512cc-104">Verwenden Sie diese Checkliste, um die Gastzugriffs-Funktionen in Microsoft Teams gemäß den Präferenzen Ihrer Organisation einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="512cc-104">Use this checklist to help you enable and configure the guest access feature in Microsoft Teams according to the preferences of your organization.</span></span>

> [!NOTE] 
> <span data-ttu-id="512cc-105">Informationen zu Einschränkungen für die Zusammenarbeit finden Sie unter [Einrichten der externen B2B-Zusammenarbeit und verwalten, wer Gäste einladen kann](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="512cc-105">For collaboration restrictions see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="512cc-106">Grundlegendes zu den Einschränkungen für Gäste</span><span class="sxs-lookup"><span data-stu-id="512cc-106">Understand the limitations for guests</span></span>

<span data-ttu-id="512cc-107">Die Gastumgebung hat Beschränkungen, die beabsichtigt sind.</span><span class="sxs-lookup"><span data-stu-id="512cc-107">The guest experience has limitations by design.</span></span> <span data-ttu-id="512cc-108">Stellen Sie sicher, dass Sie die Gastumgebung verstehen, damit Sie nicht versuchen, ein Problem zu beheben, das keines ist.</span><span class="sxs-lookup"><span data-stu-id="512cc-108">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="512cc-109">Hier finden Sie beispielsweise eine Liste der Funktionen, die für einen Gast in Microsoft Teams nicht verfügbar sind:</span><span class="sxs-lookup"><span data-stu-id="512cc-109">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="512cc-110">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="512cc-110">OneDrive for Business Standalone SKU</span></span>
- <span data-ttu-id="512cc-111">Personensuche außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="512cc-111">People search outside of Teams</span></span>
- <span data-ttu-id="512cc-112">Kalender, geplante Besprechungen oder Besprechungsdetails</span><span class="sxs-lookup"><span data-stu-id="512cc-112">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="512cc-113">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="512cc-113">PSTN</span></span>
- <span data-ttu-id="512cc-114">Organigramm</span><span class="sxs-lookup"><span data-stu-id="512cc-114">Organization Chart</span></span>
- <span data-ttu-id="512cc-115">Erstellen oder Überarbeiten eines Teams</span><span class="sxs-lookup"><span data-stu-id="512cc-115">Create or revise a team</span></span>
- <span data-ttu-id="512cc-116">Suche nach Teams</span><span class="sxs-lookup"><span data-stu-id="512cc-116">Browse for a team</span></span>
- <span data-ttu-id="512cc-117">Hochladen von Dateien in einen persönlichen Chat</span><span class="sxs-lookup"><span data-stu-id="512cc-117">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="512cc-118">Gäste können weiterhin Benutzer (außerhalb Ihres Teams) suchen und finden, wenn Sie die vollständige e-Mail-ID des Benutzers kennen.</span><span class="sxs-lookup"><span data-stu-id="512cc-118">Guests can still search and find users (outside their team) if they know the user's full email ID.</span></span> <span data-ttu-id="512cc-119">Um das zu verhindern, können IT-Administratoren Muster wie den [Umfang der Verzeichnissuche](https://docs.microsoft.com/de-DE/MicrosoftTeams/teams-scoped-directory-search) verwenden, die Gäste auf Ihre eigene virtuelle GAL beschränken können.</span><span class="sxs-lookup"><span data-stu-id="512cc-119">To prevent this, IT admins can use patterns like [scoped directory search](https://docs.microsoft.com/de-DE/MicrosoftTeams/teams-scoped-directory-search) that have the ability to restrict Guests into their own virtual GAL.</span></span>

<span data-ttu-id="512cc-120">Weitere Details finden Sie unter [Gastfunktionalität](guest-experience.md) und [Gastzugriff in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="512cc-120">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="512cc-121">Gastzugriff und externer Zugriff (Partnerverbund) im Vergleich</span><span class="sxs-lookup"><span data-stu-id="512cc-121">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

> [!NOTE] 
> <span data-ttu-id="512cc-122">Derzeit unterstützt Microsoft Teams nicht die Rolle „Gasteinladender“.</span><span class="sxs-lookup"><span data-stu-id="512cc-122">Currently, Microsoft Teams does not support the guest inviter role.</span></span> <span data-ttu-id="512cc-123">Mindestens die Umschaltfläche „Mitglieder können einladen“ muss auf „Ja“ festgelegt werden, damit der Gastzugriff in Microsoft Teams funktioniert.</span><span class="sxs-lookup"><span data-stu-id="512cc-123">at a minimum the Members can invite toggle must be set to Yes for guest access to work in Teams.</span></span> <span data-ttu-id="512cc-124">Wenn Sie „Mitglieder können einladen“ auf „Nein“ festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="512cc-124">If you set "members can invite" to "No" and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="512cc-125">Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="512cc-125">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="512cc-126">Wenn Ihre Gäste Lizenzfehler sehen</span><span class="sxs-lookup"><span data-stu-id="512cc-126">If your guests are seeing license errors</span></span>

<span data-ttu-id="512cc-127">Für den Gastzugriff in Microsoft Teams wird Azure Active Directory (Azure AD) Business-to-Business (B2B) und dessen Lizenzierungsmodell genutzt.</span><span class="sxs-lookup"><span data-stu-id="512cc-127">Guest access in Microsoft Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="512cc-128">Wenn Sie auf Lizenzfehler stoßen, lesen Sie bitte die [B2B-Lizenzierungsanleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance), um die Lizenzierungsanforderungen Ihrer Organisation zu verstehen und sicherzustellen, dass Ihre Benutzer Gäste in Ihre Organisation einladen können.</span><span class="sxs-lookup"><span data-stu-id="512cc-128">If you’re seeing licensing errors, make sure to read the [B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="512cc-129">Einige Dinge, die Sie beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="512cc-129">A few things to remember:</span></span>

- <span data-ttu-id="512cc-130">Gäste sind Benutzer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="512cc-130">Guests are users outside your organization.</span></span> <span data-ttu-id="512cc-131">Ihre Mitarbeiter, Auftragnehmer oder Agenten vor Ort usw. können nicht als Gäste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="512cc-131">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="512cc-132">Das gleiche gilt für Ihre Partner.</span><span class="sxs-lookup"><span data-stu-id="512cc-132">The same applies to your affiliates.</span></span>
- <span data-ttu-id="512cc-133">Gastlizenzen werden für die einladende Organisation gezählt.</span><span class="sxs-lookup"><span data-stu-id="512cc-133">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="512cc-134">Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.</span><span class="sxs-lookup"><span data-stu-id="512cc-134">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="512cc-135">Lizenzen werden gegen Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="512cc-135">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="512cc-136">□  Schritt 1: Konfigurieren von Einstellungen in Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="512cc-136">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="512cc-137">Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="512cc-137">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="512cc-138">Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="512cc-138">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="512cc-139">Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.</span><span class="sxs-lookup"><span data-stu-id="512cc-139">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="512cc-140">Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="512cc-140">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="512cc-141">Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="512cc-141">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="512cc-142">Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="512cc-142">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="512cc-143">**Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="512cc-143">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="512cc-144">Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="512cc-144">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="512cc-145">Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="512cc-145">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
   - <span data-ttu-id="512cc-146">**Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="512cc-146">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span>
   - <span data-ttu-id="512cc-147">**Mitglieder können einladen**: Damit Mitglieder Ihres Verzeichnisses, die nicht Administratoren sind, Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="512cc-147">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="512cc-148">Wenn Sie **Mitglieder können einladen** auf **Nein** festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="512cc-148">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="512cc-149">Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="512cc-149">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="512cc-150">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="512cc-150">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
   
   - <span data-ttu-id="512cc-151">**Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="512cc-151">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="512cc-152">**Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="512cc-152">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>

   - <span data-ttu-id="512cc-153">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="512cc-153">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
    
## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="512cc-154">□ Schritt 2: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="512cc-154">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="512cc-155">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Dienste und Add-Ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="512cc-155">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="512cc-156">Stellen Sie sicher, dass **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** auf **Ein** gestellt ist.</span><span class="sxs-lookup"><span data-stu-id="512cc-156">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="512cc-157">Wenn diese Einstellung deaktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="512cc-157">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="512cc-158">Stellen Sie sicher, dass **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **Ein** gestellt ist.</span><span class="sxs-lookup"><span data-stu-id="512cc-158">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="512cc-159">Wenn diese Einstellung deaktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="512cc-159">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="512cc-160">Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="512cc-160">At a minimum, this setting must be On to support guest access.</span></span>

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)

<span data-ttu-id="512cc-162">Detaillierte Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/de-DE/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="512cc-162">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="512cc-163">□ Schritt 3: Aktivieren des Gastzugriffs auf Mandantenebene</span><span class="sxs-lookup"><span data-stu-id="512cc-163">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="512cc-164">Sie müssen im **Microsoft Teams Admin Center** mindestens den Gastzugriff für Microsoft Teams aktivieren.</span><span class="sxs-lookup"><span data-stu-id="512cc-164">At a minimum, you must turn on guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="512cc-165">Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="512cc-165">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="512cc-166">Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="512cc-166">Set the **Allow guest access in Microsoft Teams** toggle switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="512cc-168">Konfigurieren Sie auf dieser Seite alle anderen für Sie erforderlichen Gasteinstellungen.</span><span class="sxs-lookup"><span data-stu-id="512cc-168">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="512cc-169">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="512cc-169">Click **Save**.</span></span>

<span data-ttu-id="512cc-170">Detaillierte Anweisungen finden Sie unter [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="512cc-170">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="512cc-171">□ Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="512cc-171">□  Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="512cc-172">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="512cc-172">Make sure that users can add guests.</span></span> <span data-ttu-id="512cc-173">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="512cc-173">Here's how.</span></span>

1. <span data-ttu-id="512cc-174">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="512cc-174">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="512cc-176">Wählen Sie unter **Freigabe** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="512cc-176">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="512cc-178">Legen Sie **Benutzer dürfen neue Gäste zur Organisation hinzufügen** auf **Ein** fest und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="512cc-178">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="512cc-180">Diese Einstellung entspricht der Einstellung **Mitglieder können einladen** in  **Benutzereinstellungen** > **Externe Benutzer**  in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="512cc-180">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="512cc-181">□ Schritt 5: Überprüfen der Freigabeeinstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="512cc-181">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="512cc-182">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="512cc-182">Sign in to the Microsoft Teams admin center.</span></span>
2. <span data-ttu-id="512cc-183">Klicken Sie auf **Admin Center** und wählen Sie dann **SharePoint** aus.</span><span class="sxs-lookup"><span data-stu-id="512cc-183">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="512cc-184">Wählen Sie im SharePoint Admin Center **Freigabe** aus.</span><span class="sxs-lookup"><span data-stu-id="512cc-184">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="512cc-185">Vergewissern Sie sich, dass die Option für **Freigabe außerhalb Ihrer Organisation nicht zulassen** *nicht* aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="512cc-185">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter von Einstellungen in SharePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="512cc-187">□ Schritt 6: Aktivieren spezifischer Einstellungen für Kanäle</span><span class="sxs-lookup"><span data-stu-id="512cc-187">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="512cc-188">Konfigurieren Sie in der Teams-Anwendung die Gastberechtigungen auf der einzelnen Teamebene so, dass Gäste Kanäle erstellen, aktualisieren und löschen können.</span><span class="sxs-lookup"><span data-stu-id="512cc-188">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="512cc-189">Neben den Administratoren können Teambesitzer diese Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="512cc-189">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="512cc-191">Weitere Informationen sowie Anleitungsvideos finden Sie unter [Gastzugriff in Microsoft Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="512cc-191">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="512cc-192">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="512cc-192">Troubleshooting</span></span>

<span data-ttu-id="512cc-193">Solten Sie Probleme beim Hinzufügen von Gästen in Microsoft Teams haben, lesen Sie den [Leitfaden zur Problembehandlung bei Gastzugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="512cc-193">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


