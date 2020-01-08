---
title: Checkliste für den Microsoft Teams-Gastzugriff
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Checkliste, um den Gastzugriff in Microsoft Teams einzurichten.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3354f7b503b2f1ea91c050a751b5d7d9ab0537a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962533"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="998c5-103">Checkliste für den Microsoft Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="998c5-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="998c5-104">Verwenden Sie diese Checkliste, damit Sie den Gastzugriff in Microsoft Teams aktivieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="998c5-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="998c5-105">Sie müssen ein globaler Administrator oder ein Teamadministrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="998c5-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="998c5-106">Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="998c5-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="998c5-107">Schauen Sie sich dieses kurze Video (5:31 Minuten) an, um zu erfahren, wie Sie den Gastzugriff in Microsoft 365, einschließlich Teams, aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="998c5-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="998c5-108">Schritt 1: Aktivieren des Gastzugriffs auf der organisationsweiten Ebene von Teams</span><span class="sxs-lookup"><span data-stu-id="998c5-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="998c5-109">Wenn Sie den Gastzugriff aktivieren möchten, wechseln Sie zum **Microsoft Teams Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="998c5-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="998c5-110">Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="998c5-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="998c5-111">Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="998c5-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="998c5-113">Aktivieren oder deaktivieren Sie auf dieser Seite die Einstellungen für **Anrufe**, **Besprechungen**und nach **richten** für Gäste.</span><span class="sxs-lookup"><span data-stu-id="998c5-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="998c5-114">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="998c5-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="998c5-115">Wenn Sie die Standardeinstellungen in Azure Active Directory, SharePoint Online und Office 365-Gruppen verwenden, ist möglicherweise die Konfiguration des Gastzugriffs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="998c5-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="998c5-116">In diesem Fall können Sie die restlichen Schritte überspringen.</span><span class="sxs-lookup"><span data-stu-id="998c5-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="998c5-117">Wenn Sie sich nicht sicher sind, oder wenn Sie benutzerdefinierte Einstellungen für Aad, SharePoint Online oder Office 365-Gruppen verwenden, fahren Sie mit den restlichen Schritten in dieser Checkliste fort.</span><span class="sxs-lookup"><span data-stu-id="998c5-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="998c5-118">Schritt 2: Konfigurieren von Azure AD Business-to-Business-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="998c5-118">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="998c5-119">Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="998c5-119">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="998c5-120">Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="998c5-120">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="998c5-121">Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.</span><span class="sxs-lookup"><span data-stu-id="998c5-121">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="998c5-122">Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="998c5-122">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="998c5-123">Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="998c5-123">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="998c5-124">Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="998c5-124">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="998c5-125">**Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="998c5-125">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="998c5-126">Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="998c5-126">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="998c5-127">Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="998c5-127">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="998c5-128">**Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="998c5-128">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="998c5-129">**Mitglieder können einladen**: Damit Mitglieder Ihres Verzeichnisses, die nicht Administratoren sind, Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="998c5-129">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>

         > [!NOTE]
         > <span data-ttu-id="998c5-130">Wenn Sie **Mitglieder können einladen** auf **Nein** festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="998c5-130">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="998c5-131">Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="998c5-131">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="998c5-132">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="998c5-132">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="998c5-133">Damit der Gastzugriff in Teams funktioniert, müssen Sie **Mitglieder können einladen** auf **Ja** festlegen.</span><span class="sxs-lookup"><span data-stu-id="998c5-133">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
     - <span data-ttu-id="998c5-134">**Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="998c5-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="998c5-135">Aktuell unterstützt Teams nicht die Rolle „Gasteinladender“. Das heißt, selbst wenn Sie **Gäste können einladen** auf **Ja** festlegen, können Gäste keine anderen Gäste in Teams einladen.</span><span class="sxs-lookup"><span data-stu-id="998c5-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="998c5-136">**Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="998c5-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="998c5-137">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="998c5-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="998c5-138">Informationen zu Einschränkungen der Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="998c5-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
    <span data-ttu-id="998c5-139">Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="998c5-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="998c5-140">Schritt 3: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="998c5-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="998c5-141">Wechseln Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Services #a0-Add-ins**, und wählen Sie dann **Office 365-Gruppen**aus.</span><span class="sxs-lookup"><span data-stu-id="998c5-141">In the Microsoft 365 admin center, go to **Settings** > **Services & add-ins**, and then select **Office 365 Groups**.</span></span>

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)
2. <span data-ttu-id="998c5-143">Stellen Sie sicher, dass das Kontrollkästchen **Gruppenmitglieder außerhalb des Organisations Zugriffs auf Gruppeninhalte zulassen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="998c5-143">Make sure that the **Let group members outside the organization access group content** check box is selected.</span></span> <span data-ttu-id="998c5-144">Wenn diese Einstellung nicht aktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="998c5-144">If this setting is not selected, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="998c5-145">Stellen Sie sicher, dass das Kontrollkästchen **Gruppenbesitzer Personen außerhalb des Unternehmens hinzufügen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="998c5-145">Make sure that the **Let group owners add people outside the organization to groups** check box is selected.</span></span> <span data-ttu-id="998c5-146">Wenn diese Einstellung nicht aktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="998c5-146">If this setting is not selected, team owners won't be able to add new guests.</span></span> <span data-ttu-id="998c5-147">Diese Einstellung muss mindestens aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="998c5-147">At a minimum, this setting must be on to support guest access.</span></span>

<span data-ttu-id="998c5-148">Detaillierte Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="998c5-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="998c5-149">Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="998c5-149">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="998c5-150">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="998c5-150">Make sure that users can add guests.</span></span> <span data-ttu-id="998c5-151">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="998c5-151">Here's how:</span></span>

1. <span data-ttu-id="998c5-152">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="998c5-152">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="998c5-154">Wählen Sie unter **Freigabe** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="998c5-154">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="998c5-156">Legen Sie **Benutzer dürfen neue Gäste zur Organisation hinzufügen** auf **Ein** fest und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="998c5-156">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > <span data-ttu-id="998c5-158">Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="998c5-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="998c5-159">Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="998c5-159">Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="998c5-160">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="998c5-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="998c5-161">Wählen Sie unter **Admin Center**die Option **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="998c5-161">Under **Admin centers**, select  **SharePoint**.</span></span>
3. <span data-ttu-id="998c5-162">Wählen Sie im neuen SharePoint Admin Center unter **Websites**die Option **aktive Websites**aus.</span><span class="sxs-lookup"><span data-stu-id="998c5-162">In the new SharePoint admin center,  under **Sites**, select **Active sites**.</span></span>

    ![Aktive Websites im SharePoint Admin Center](media/guest-access-checklist-SPOSettings0.png)

3. <span data-ttu-id="998c5-164">Wählen Sie die Website aus, und klicken Sie dann auf **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="998c5-164">Select the site, and then click **Sharing**.</span></span>
4. <span data-ttu-id="998c5-165">Stellen Sie sicher, dass die Option auf **jeder** oder **neuen und vorhandenen Gästen**festgesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="998c5-165">Make sure that the option is set to **Anyone** or **New and existing guests**.</span></span>
 
     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche für SharePoint Online-Einstellungen](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="998c5-167">Schritt 6: Einrichten von Gastbenutzer Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="998c5-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="998c5-168">Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, die Steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="998c5-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="998c5-169">Teams-Administratoren und Teambesitzer können diese Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="998c5-169">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="998c5-171">Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="998c5-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="998c5-172">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="998c5-172">Troubleshooting</span></span>

<span data-ttu-id="998c5-173">Wenn Sie Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams haben, verwenden Sie diese Ressourcen, um Ihnen zu helfen:</span><span class="sxs-lookup"><span data-stu-id="998c5-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="998c5-174">Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="998c5-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="998c5-175">Problembehandlung für Teams</span><span class="sxs-lookup"><span data-stu-id="998c5-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



