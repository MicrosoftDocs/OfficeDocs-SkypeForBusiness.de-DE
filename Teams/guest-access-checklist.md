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
ms.openlocfilehash: 04627c74528972aad69b1e810e222f55cae49588
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902580"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="47b92-103">Checkliste für den Microsoft Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="47b92-103">Microsoft Teams guest access checklist</span></span>
=========================================

<span data-ttu-id="47b92-104">Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="47b92-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="47b92-105">Sie müssen ein globaler Administrator oder ein Teams-Administrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="47b92-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47b92-106">Möglicherweise müssen Sie einige Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="47b92-106">You may have to wait a couple of hours for your changes to take effect.</span></span> 

<span data-ttu-id="47b92-107">Schauen Sie sich dieses kurze Video an (5:31 Minuten), um zu sehen, wie Sie in Microsoft 365, einschließlich Teams, den Gastzugriff aktivieren.</span><span class="sxs-lookup"><span data-stu-id="47b92-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="47b92-108">Schritt 1: Aktivieren des Gastzugriffs in Teams auf Organisationsebene</span><span class="sxs-lookup"><span data-stu-id="47b92-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="47b92-109">Um den Gastzugriff zu aktivieren, navigieren Sie zum **Microsoft Teams Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="47b92-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="47b92-110">Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="47b92-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="47b92-111">Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="47b92-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="47b92-113">Auf derselben Seite können Sie die Einstellungen **Anruf**, **Besprechung** und **Messaging** für Gäste ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="47b92-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="47b92-114">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="47b92-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="47b92-115">Wenn Sie die Standardeinstellungen in Azure Active Directory, SharePoint Online und Microsoft 365-Gruppen verwenden, ist möglicherweise die Konfiguration des Gastzugriffs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="47b92-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Microsoft 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="47b92-116">In diesem Fall können Sie die restlichen Schritte überspringen.</span><span class="sxs-lookup"><span data-stu-id="47b92-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="47b92-117">Wenn Sie sich nicht sicher sind, oder wenn Sie benutzerdefinierte Einstellungen für Aad, SharePoint Online oder Microsoft 365-Gruppen verwenden, fahren Sie mit den restlichen Schritten in dieser Checkliste fort.</span><span class="sxs-lookup"><span data-stu-id="47b92-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Microsoft 365 Groups, continue with the rest of the steps in this checklist.</span></span>

## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="47b92-118">Schritt 2: Konfigurieren von Einstellungen in Azure AD Business-to-Business</span><span class="sxs-lookup"><span data-stu-id="47b92-118">Step 2: Configure Azure AD business-to-business settings</span></span>

<span data-ttu-id="47b92-119">Hierbei handelt es sich um die Azure AD-Einstellungen, die den Gastzugriff in Teams unterstützen.</span><span class="sxs-lookup"><span data-stu-id="47b92-119">These are the Azure AD settings that support guest access in Teams.</span></span> <span data-ttu-id="47b92-120">Sobald diese Einstellungen konfiguriert sind, können Sie Gäste in Teams [hinzufügen](add-guests.md) und [verwalten](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="47b92-120">Once these settings are configured, you'll be able to [add](add-guests.md) and [manage guests](manage-guests.md) in Teams.</span></span>

1. <span data-ttu-id="47b92-121">Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="47b92-121">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="47b92-122">Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="47b92-122">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="47b92-123">Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.</span><span class="sxs-lookup"><span data-stu-id="47b92-123">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="47b92-124">Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="47b92-124">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="47b92-125">Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="47b92-125">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="47b92-126">Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="47b92-126">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="47b92-127">**Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="47b92-127">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="47b92-128">Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="47b92-128">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="47b92-129">Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="47b92-129">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="47b92-130">**Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="47b92-130">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="47b92-131">**Mitglieder können einladen**: Um Mitgliedern Ihres Verzeichnisses, die keine Administratoren SIND; zu erlauben, Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="47b92-131">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes** (recommended).</span></span> <span data-ttu-id="47b92-132">Wenn Sie nur Administratoren erlauben möchten, Gäste hinzuzufügen, können Sie diese Richtlinie auf **Nein** festlegen.</span><span class="sxs-lookup"><span data-stu-id="47b92-132">If you prefer that only admins be able to add guests, you can set this policy to **No**.</span></span> <span data-ttu-id="47b92-133">Denken Sie daran, dass die Einstellung **Nein** die Gasterfahrung für Besitzer von Teams, die keine Administratoren sind, einschränkt. Sie können nur Gäste zu Teams hinzufügen, die bereits vom Administrator in AAD hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="47b92-133">Keep in mind that setting **No** will limit the guest experience for non-admin teams owners; they'll only be able to add guests in Teams that have already been added in AAD by the admin.</span></span>
     - <span data-ttu-id="47b92-134">**Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="47b92-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="47b92-135">Aktuell unterstützt Teams nicht die Rolle „Gasteinladender“. Das heißt, selbst wenn Sie **Gäste können einladen** auf **Ja** festlegen, können Gäste keine anderen Gäste in Teams einladen.</span><span class="sxs-lookup"><span data-stu-id="47b92-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="47b92-136">**Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="47b92-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="47b92-137">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="47b92-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="47b92-138">Informationen zu Einschränkungen für die Zusammenarbeit finden Sie unter [Einrichten der externen B2B-Zusammenarbeit und verwalten, wer Gäste einladen kann](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="47b92-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
    <span data-ttu-id="47b92-139">Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="47b92-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>

## <a name="step-3-configure-microsoft-365-groups"></a><span data-ttu-id="47b92-140">Schritt 3: Konfigurieren von Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="47b92-140">Step 3: Configure Microsoft 365 Groups</span></span>

1. <span data-ttu-id="47b92-141">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Einstellungen, klicken**Sie auf **Dienste**, und wählen Sie dann **Microsoft 365-Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="47b92-141">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Services**, and then select **Microsoft 365 Groups**.</span></span>

     ![Screenshot der Microsoft 365-Gruppeneinstellungen](media/guest-access-checklist-services-settings.png)
2. <span data-ttu-id="47b92-143">Stellen Sie sicher, dass das Kontrollkästchen **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="47b92-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="47b92-144">Wenn diese Einstellung nicht aktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="47b92-144">If this setting is not selected, guests won't be able to access any group content.</span></span>

    ![Screenshot der Microsoft 365-Gruppeneinstellungen](media/guest-access-checklist-office365.png)
3. <span data-ttu-id="47b92-146">Stellen Sie sicher, dass das Kontrollkästchen **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="47b92-146">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="47b92-147">Wenn diese Einstellung nicht aktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="47b92-147">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="47b92-148">Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="47b92-148">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="47b92-149">Ausführliche Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Microsoft 365-Gruppen](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Microsoft 365-Gruppen](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span><span class="sxs-lookup"><span data-stu-id="47b92-149">For detailed instructions about configuring these settings, see [Manage guest access in Microsoft 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Microsoft 365 Groups](Teams-dependencies.md#control-guest-access-in-microsoft-365-groups).</span></span>

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="47b92-150">Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="47b92-150">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="47b92-151">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="47b92-151">Make sure that users can add guests.</span></span> <span data-ttu-id="47b92-152">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="47b92-152">Here's how:</span></span>

1. <span data-ttu-id="47b92-153">Navigieren Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Einstellungen**, klicken Sie auf **Sicherheit und Datenschutz**, und wählen Sie dann **Freigabe** aus.</span><span class="sxs-lookup"><span data-stu-id="47b92-153">In the Microsoft 365 admin center, go to **Settings** > **Settings**, click **Security & privacy**, and then select **Sharing**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-security-privacy-settings.png)
 
2. <span data-ttu-id="47b92-155">Aktivieren Sie das Kontrollkästchen **Benutzer dürfen neue Gäste zur Organisation hinzufügen**, und klicken Sie dann auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="47b92-155">Select the **Let users add new guests to this organization** check box, and then click **Save changes**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-sharing-setting.png)
 
    > [!NOTE]
    > <span data-ttu-id="47b92-157">Diese Einstellung entspricht der Einstellung **Mitglieder können einladen** in **Benutzereinstellungen** > **Externe Benutzer** in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="47b92-157">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  

## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="47b92-158">Schritt 5: Überprüfen der Freigabeeinstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="47b92-158">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="47b92-159">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="47b92-159">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="47b92-160">Wählen Sie unter **Admin Center** die Option **SharePoint** aus.</span><span class="sxs-lookup"><span data-stu-id="47b92-160">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="47b92-161">Wählen Sie im neuen SharePoint Admin Center unter **Websites** die Option **Aktive Websites** aus.</span><span class="sxs-lookup"><span data-stu-id="47b92-161">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Aktive Websites im SharePoint Online Admin Center](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="47b92-163">Wählen Sie die Website aus, und klicken Sie dann auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="47b92-163">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="47b92-164">Stellen Sie sicher, dass die Option auf **Jeder** oder **Neue und vorhandene Gäste** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="47b92-164">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>

     ![Screenshot eines Beispiels für einen Umschalter von Einstellungen in SharePoint](media/guest-access-checklist-SPOSettings1.png)

## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="47b92-166">Schritt 6: Einrichten von Gastbenutzerberechtigungen</span><span class="sxs-lookup"><span data-stu-id="47b92-166">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="47b92-167">Konfigurieren Sie in der Teams-Anwendung auf Ebene der einzelnen Teams Gastberechtigungen, die steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="47b92-167">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="47b92-168">Sowohl die Teamadministratoren als auch die Teambesitzer können diese Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="47b92-168">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot zeigt ein Beispiel für einen Umschalter von Team-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="47b92-170">Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="47b92-170">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="47b92-171">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="47b92-171">Troubleshooting</span></span>

<span data-ttu-id="47b92-172">Wenn Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams auftreten, finden Sie in diesen Ressourcen Hilfe:</span><span class="sxs-lookup"><span data-stu-id="47b92-172">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="47b92-173">Behandeln von Problemen mit Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="47b92-173">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="47b92-174">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="47b92-174">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)
