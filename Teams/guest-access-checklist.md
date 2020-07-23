---
title: Checkliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Hier erfahren Sie, wie Sie den Gastzugriff in Microsoft Teams als globaler Administrator oder als Teamadministrator aktivieren und konfigurieren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d38b0adf1a342c4398d2779e2f0b5ec3aa310144
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372004"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="9338f-103">Checkliste für den Microsoft Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="9338f-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="9338f-104">Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9338f-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="9338f-105">Sie müssen ein globaler Administrator oder ein Teams-Administrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="9338f-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9338f-106">Möglicherweise müssen Sie einige Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="9338f-106">You may have to wait a few hours for your changes to take effect.</span></span>

<span data-ttu-id="9338f-107">Schauen Sie sich dieses kurze Video an (5:31 Minuten), um zu sehen, wie Sie in Microsoft 365, einschließlich Teams, den Gastzugriff aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9338f-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="9338f-108">Schritt 1: Aktivieren des Gastzugriffs in Teams auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="9338f-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="9338f-109">Sie müssen ein Team Dienstadministrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="9338f-109">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="9338f-110">Informationen zum Abrufen von Administratorrollen und-Berechtigungen finden Sie unter [Verwenden von Teams-Administratorrollen zum Verwalten von Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="9338f-110">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="9338f-111">Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="9338f-111">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="9338f-112">Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="9338f-112">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="9338f-114">Auf derselben Seite können Sie die Einstellungen **Anruf**, **Besprechung** und **Messaging** für Gäste ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="9338f-114">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="9338f-115">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="9338f-115">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="9338f-116">Wenn Sie die Standardeinstellungen in Azure Active Directory, SharePoint Online und Microsoft 365-Gruppen verwenden, ist möglicherweise die Konfiguration des Gastzugriffs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9338f-116">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="9338f-117">In diesem Fall können Sie die restlichen Schritte überspringen.</span><span class="sxs-lookup"><span data-stu-id="9338f-117">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="9338f-118">Wenn Sie sich nicht sicher sind, oder wenn Sie benutzerdefinierte Einstellungen für Aad, SharePoint Online oder Microsoft 365-Gruppen verwenden, fahren Sie mit den restlichen Schritten in dieser Checkliste fort.</span><span class="sxs-lookup"><span data-stu-id="9338f-118">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="9338f-119">Schritt 2: Konfigurieren von Einstellungen in Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="9338f-119">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="9338f-120">Hierbei handelt es sich um die Azure AD-Einstellungen, die den Gastzugriff in Teams unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9338f-120">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="9338f-121">Sobald diese Einstellungen konfiguriert sind, können Sie Gäste in Teams [hinzufügen](add-guests.md) und [verwalten](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="9338f-121">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="9338f-122">Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="9338f-122">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="9338f-123">Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="9338f-123">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="9338f-124">Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.</span><span class="sxs-lookup"><span data-stu-id="9338f-124">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="9338f-125">Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9338f-125">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="9338f-126">Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="9338f-126">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="9338f-127">Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9338f-127">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="9338f-128">**Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9338f-128">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="9338f-129">Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="9338f-129">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="9338f-130">Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="9338f-130">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="9338f-131">**Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="9338f-131">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="9338f-132">**Mitglieder können einladen**: Um Mitgliedern Ihres Verzeichnisses, die keine Administratoren SIND; zu erlauben, Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="9338f-132">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="9338f-133">Wenn Sie nur Administratoren erlauben möchten, Gäste hinzuzufügen, können Sie diese Richtlinie auf **Nein** festlegen.</span><span class="sxs-lookup"><span data-stu-id="9338f-133">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="9338f-134">Denken Sie daran, dass die Einstellung **Nein** die Gasterfahrung für Besitzer von Teams, die keine Administratoren sind, einschränkt. Sie können nur Gäste zu Teams hinzufügen, die bereits vom Administrator in AAD hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="9338f-134">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="9338f-135">**Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="9338f-135">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="9338f-136">Aktuell unterstützt Teams nicht die Rolle „Gasteinladender“. Das heißt, selbst wenn Sie **Gäste können einladen** auf **Ja** festlegen, können Gäste keine anderen Gäste in Teams einladen.</span><span class="sxs-lookup"><span data-stu-id="9338f-136">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="9338f-137">**Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="9338f-137">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="9338f-138">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="9338f-138">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="9338f-139">Informationen zu Einschränkungen für die Zusammenarbeit finden Sie unter [Einrichten der externen B2B-Zusammenarbeit und verwalten, wer Gäste einladen kann](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="9338f-139">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

    <span data-ttu-id="9338f-140">Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="9338f-140">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="9338f-141">Schritt 3: Konfigurieren von Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="9338f-141">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="9338f-142">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen**  >  **org-Einstellungen**, klicken Sie auf **Dienste**, und wählen Sie dann **Microsoft 365-Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="9338f-142">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![Screenshot der Microsoft 365-Gruppeneinstellungen](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="9338f-144">Stellen Sie sicher, dass das Kontrollkästchen **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9338f-144">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="9338f-145">Wenn diese Einstellung nicht aktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9338f-145">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Screenshot der Microsoft 365-Gruppeneinstellungen](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="9338f-147">Stellen Sie sicher, dass das Kontrollkästchen **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9338f-147">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="9338f-148">Wenn diese Einstellung nicht aktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9338f-148">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="9338f-149">Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="9338f-149">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="9338f-150">Ausführliche Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Microsoft 365-Gruppen](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Microsoft 365-Gruppen](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="9338f-150">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-microsoft-365"></a><span data-ttu-id="9338f-151">Schritt 4: Konfigurieren der Freigabe in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9338f-151">Step 4: Configure sharing in Microsoft 365</span></span>

<span data-ttu-id="9338f-152">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="9338f-152">Make sure that users can add guests.</span></span> <span data-ttu-id="9338f-153">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="9338f-153">Here's how:</span></span>

1. <span data-ttu-id="9338f-154">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen**  >  **org-Einstellungen**, klicken Sie auf **Sicherheit & Datenschutz**, und wählen Sie dann **Freigeben**aus.</span><span class="sxs-lookup"><span data-stu-id="9338f-154">In the Microsoft 365 admin center, go to **Settings** > **Org Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-security-privacy-settings.png)

2. <span data-ttu-id="9338f-156">Aktivieren Sie das Kontrollkästchen **Benutzer dürfen neue Gäste zur Organisation hinzufügen**, und klicken Sie dann auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="9338f-156">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-sharing-setting.png)

    > [!NOTE]
    > <span data-ttu-id="9338f-158">Diese Einstellung entspricht der Einstellung **Mitglieder können einladen** in **Benutzereinstellungen** > **Externe Benutzer** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9338f-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="9338f-159">Schritt 5: Überprüfen der Freigabeeinstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="9338f-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="9338f-160">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="9338f-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="9338f-161">Wählen Sie unter **Admin Center** die Option **SharePoint** aus.</span><span class="sxs-lookup"><span data-stu-id="9338f-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="9338f-162">Wählen Sie im neuen SharePoint Admin Center unter **Websites** die Option **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="9338f-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Aktive Websites im SharePoint Online Admin Center](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="9338f-164">Wählen Sie die Website aus, und klicken Sie dann auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="9338f-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="9338f-165">Stellen Sie sicher, dass die Option auf **Jeder** oder **Neue und vorhandene Gäste** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9338f-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Screenshot eines Beispiels für einen Umschalter von Einstellungen in SharePoint](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="9338f-167">Schritt 6: Einrichten von Gastbenutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="9338f-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="9338f-168">Konfigurieren Sie in der Teams-Anwendung auf Ebene der einzelnen Teams Gastberechtigungen, die steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="9338f-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="9338f-169">Sowohl die Teamadministratoren als auch die Teambesitzer können diese Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="9338f-169">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot zeigt ein Beispiel für einen Umschalter von Team-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="9338f-171">Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="9338f-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="9338f-172">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="9338f-172">Troubleshooting</span></span>

<span data-ttu-id="9338f-173">Wenn Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams auftreten, finden Sie in diesen Ressourcen Hilfe:</span><span class="sxs-lookup"><span data-stu-id="9338f-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="9338f-174">Behandeln von Problemen mit Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9338f-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="9338f-175">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="9338f-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
