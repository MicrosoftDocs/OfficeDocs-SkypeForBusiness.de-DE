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
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bcba883166e01bd8a18d6d76b4622df0740500c8
ms.sourcegitcommit: 000fdb3bc1a0d4dda63fb00bab6a9a9ab0c85ab0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "39813775"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="e6c79-103">Checkliste für den Microsoft Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="e6c79-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="e6c79-104">Verwenden Sie diese Checkliste, damit Sie den Gastzugriff in Microsoft Teams aktivieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="e6c79-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span> <span data-ttu-id="e6c79-105">Sie müssen ein globaler Administrator oder ein Teamadministrator sein, um diese Änderungen vornehmen zu können.</span><span class="sxs-lookup"><span data-stu-id="e6c79-105">You need to be a Global Administrator or a Teams Administrator to make these changes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6c79-106">Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="e6c79-106">You may have to wait up to 24 hours for your changes to take effect.</span></span> 

<span data-ttu-id="e6c79-107">Schauen Sie sich dieses kurze Video (5:31 Minuten) an, um zu erfahren, wie Sie den Gastzugriff in Microsoft 365, einschließlich Teams, aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="e6c79-107">Watch this short video (5:31 minutes) to see how to turn on guest access throughout Microsoft 365, including Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="e6c79-108">Schritt 1: Aktivieren des Gastzugriffs auf der organisationsweiten Ebene von Teams</span><span class="sxs-lookup"><span data-stu-id="e6c79-108">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="e6c79-109">Wenn Sie den Gastzugriff aktivieren möchten, wechseln Sie zum **Microsoft Teams Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-109">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="e6c79-110">Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-110">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="e6c79-111">Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="e6c79-111">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="e6c79-113">Aktivieren oder deaktivieren Sie auf dieser Seite die Einstellungen für **Anrufe**, **Besprechungen**und nach **richten** für Gäste.</span><span class="sxs-lookup"><span data-stu-id="e6c79-113">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="e6c79-114">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-114">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="e6c79-115">Wenn Sie die Standardeinstellungen in Azure Active Directory, SharePoint Online und Office 365-Gruppen verwenden, ist möglicherweise die Konfiguration des Gastzugriffs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-115">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="e6c79-116">In diesem Fall können Sie die restlichen Schritte überspringen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-116">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="e6c79-117">Wenn Sie sich nicht sicher sind, oder wenn Sie benutzerdefinierte Einstellungen für Aad, SharePoint Online oder Office 365-Gruppen verwenden, fahren Sie mit den restlichen Schritten in dieser Checkliste fort.</span><span class="sxs-lookup"><span data-stu-id="e6c79-117">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="e6c79-118">Schritt 2: Konfigurieren von Azure AD Business-to-Business-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e6c79-118">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="e6c79-119">Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="e6c79-119">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="e6c79-120">Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e6c79-120">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="e6c79-121">Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.</span><span class="sxs-lookup"><span data-stu-id="e6c79-121">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e6c79-122">Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-122">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="e6c79-123">Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-123">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="e6c79-124">Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e6c79-124">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

    - <span data-ttu-id="e6c79-125">**Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="e6c79-125">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="e6c79-126">Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="e6c79-126">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="e6c79-127">Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="e6c79-127">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
     - <span data-ttu-id="e6c79-128">**Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="e6c79-128">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
     - <span data-ttu-id="e6c79-129">**Mitglieder können einladen**: Damit Mitglieder Ihres Verzeichnisses, die nicht Administratoren sind, Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="e6c79-129">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>

         > [!NOTE]
         > <span data-ttu-id="e6c79-130">Wenn Sie **Mitglieder können einladen** auf **Nein** festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="e6c79-130">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="e6c79-131">Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="e6c79-131">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="e6c79-132">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="e6c79-132">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="e6c79-133">Damit der Gastzugriff in Teams funktioniert, müssen Sie **Mitglieder können einladen** auf **Ja** festlegen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-133">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
     - <span data-ttu-id="e6c79-134">**Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="e6c79-134">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
         > [!IMPORTANT]
         > <span data-ttu-id="e6c79-135">Aktuell unterstützt Teams nicht die Rolle „Gasteinladender“. Das heißt, selbst wenn Sie **Gäste können einladen** auf **Ja** festlegen, können Gäste keine anderen Gäste in Teams einladen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-135">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
     - <span data-ttu-id="e6c79-136">**Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="e6c79-136">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
     - <span data-ttu-id="e6c79-137">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="e6c79-137">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
        > [!NOTE]
        > <span data-ttu-id="e6c79-138">Informationen zu Einschränkungen der Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="e6c79-138">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
    <span data-ttu-id="e6c79-139">Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="e6c79-139">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="e6c79-140">Schritt 3: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="e6c79-140">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="e6c79-141">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Dienste und Add-Ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-141">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="e6c79-142">Stellen Sie sicher, dass **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** auf **Ein** gestellt ist.</span><span class="sxs-lookup"><span data-stu-id="e6c79-142">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="e6c79-143">Wenn diese Einstellung deaktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-143">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="e6c79-144">Stellen Sie sicher, dass **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **Ein** gestellt ist.</span><span class="sxs-lookup"><span data-stu-id="e6c79-144">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="e6c79-145">Wenn diese Einstellung deaktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-145">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="e6c79-146">Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e6c79-146">At a minimum, this setting must be On to support guest access.</span></span>

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)

<span data-ttu-id="e6c79-148">Detaillierte Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="e6c79-148">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="e6c79-149">Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="e6c79-149">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="e6c79-150">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="e6c79-150">Make sure that users can add guests.</span></span> <span data-ttu-id="e6c79-151">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="e6c79-151">Here's how:</span></span>

1. <span data-ttu-id="e6c79-152">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-152">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="e6c79-154">Wählen Sie unter **Freigabe** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="e6c79-154">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="e6c79-156">Legen Sie **Benutzer dürfen neue Gäste zur Organisation hinzufügen** auf **Ein** fest und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e6c79-156">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
    > [!NOTE]
    > <span data-ttu-id="e6c79-158">Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e6c79-158">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="e6c79-159">Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="e6c79-159">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="e6c79-160">Das hier ist ein bisschen ein Rätsel.</span><span class="sxs-lookup"><span data-stu-id="e6c79-160">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="e6c79-161">Gastzugriff in Teams funktioniert nicht, wenn im SharePoint Admin Center die Einstellung " **Freigabe außerhalb Ihrer Organisation nicht zulassen** " aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e6c79-161">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="e6c79-162">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="e6c79-162">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="e6c79-163">Klicken Sie auf **Admin Center** und wählen Sie dann **SharePoint** aus.</span><span class="sxs-lookup"><span data-stu-id="e6c79-163">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="e6c79-164">Wählen Sie im SharePoint Admin Center **Freigabe** aus.</span><span class="sxs-lookup"><span data-stu-id="e6c79-164">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="e6c79-165">Vergewissern Sie sich, dass die Option für **Freigabe außerhalb Ihrer Organisation nicht zulassen** *nicht* aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e6c79-165">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter von Einstellungen in SharePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="e6c79-167">Schritt 6: Einrichten von Gastbenutzer Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e6c79-167">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="e6c79-168">Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, die Steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="e6c79-168">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="e6c79-169">Teams-Administratoren und Teambesitzer können diese Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e6c79-169">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="e6c79-171">Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="e6c79-171">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="e6c79-172">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="e6c79-172">Troubleshooting</span></span>

<span data-ttu-id="e6c79-173">Wenn Sie Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams haben, verwenden Sie diese Ressourcen, um Ihnen zu helfen:</span><span class="sxs-lookup"><span data-stu-id="e6c79-173">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="e6c79-174">Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e6c79-174">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="e6c79-175">Problembehandlung für Teams</span><span class="sxs-lookup"><span data-stu-id="e6c79-175">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



