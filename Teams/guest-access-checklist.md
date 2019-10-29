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
ms.openlocfilehash: 04594f578d2375f69c38243251ee64506880d00e
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753320"
---
<a name="microsoft-teams-guest-access-checklist"></a><span data-ttu-id="1df90-103">Checkliste für den Microsoft Teams-Gastzugriff</span><span class="sxs-lookup"><span data-stu-id="1df90-103">Microsoft Teams guest access checklist</span></span>
==========================================

<span data-ttu-id="1df90-104">Verwenden Sie diese Checkliste, damit Sie den Gastzugriff in Microsoft Teams aktivieren und konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="1df90-104">Use this checklist to help you turn on and configure guest access in Microsoft Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1df90-105">Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="1df90-105">You may have to wait up to 24 hours for your changes to take effect.</span></span> 



## <a name="step-1-turn-on-guest-access-at-the-teams-org-wide-level"></a><span data-ttu-id="1df90-106">Schritt 1: Aktivieren des Gastzugriffs auf der organisationsweiten Ebene von Teams</span><span class="sxs-lookup"><span data-stu-id="1df90-106">Step 1: Turn on guest access at the Teams org-wide level</span></span>

<span data-ttu-id="1df90-107">Wenn Sie den Gastzugriff aktivieren möchten, wechseln Sie zum **Microsoft Teams Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="1df90-107">To turn on guest access, go to the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="1df90-108">Wählen Sie im Teams Admin Center **Organisationsweite Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="1df90-108">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="1df90-109">Legen Sie **Gastzugriff in Microsoft Teams ermöglichen** auf **An** fest.</span><span class="sxs-lookup"><span data-stu-id="1df90-109">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-Einstellungen](media/guest-access-checklist-set-up-guests-image1.png)

3. <span data-ttu-id="1df90-111">Aktivieren oder deaktivieren Sie auf dieser Seite die Einstellungen für **Anrufe**, **Besprechungen**und nach **richten** für Gäste.</span><span class="sxs-lookup"><span data-stu-id="1df90-111">On this same page, turn on or turn off **Calling**, **Meeting**, and **Messaging** settings for guests.</span></span>
4. <span data-ttu-id="1df90-112">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1df90-112">Click **Save**.</span></span>

> [!TIP]
> <span data-ttu-id="1df90-113">Wenn Sie die Standardeinstellungen in Azure Active Directory, SharePoint Online und Office 365-Gruppen verwenden, ist möglicherweise die Konfiguration des Gastzugriffs abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1df90-113">If you're using default settings in Azure Active Directory, SharePoint Online, and Office 365 Groups, you may be done configuring guest access.</span></span> <span data-ttu-id="1df90-114">In diesem Fall können Sie die restlichen Schritte überspringen.</span><span class="sxs-lookup"><span data-stu-id="1df90-114">In this case, you can skip the rest of the steps.</span></span> <span data-ttu-id="1df90-115">Wenn Sie sich nicht sicher sind, oder wenn Sie benutzerdefinierte Einstellungen für Aad, SharePoint Online oder Office 365-Gruppen verwenden, fahren Sie mit den restlichen Schritten in dieser Checkliste fort.</span><span class="sxs-lookup"><span data-stu-id="1df90-115">If you're not sure, or if you're using custom settings for AAD, SharePoint Online, or Office 365 Groups, continue with the rest of the steps in this checklist.</span></span>


## <a name="step-2-configure-azure-ad-business-to-business-settings"></a><span data-ttu-id="1df90-116">Schritt 2: Konfigurieren von Azure AD Business-to-Business-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1df90-116">Step 2: Configure Azure AD business-to-business settings</span></span>

1. <span data-ttu-id="1df90-117">Melden Sie sich als Mandantenadministrator beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="1df90-117">Sign in to the [Azure portal](https://portal.azure.com) as a tenant administrator.</span></span>
2. <span data-ttu-id="1df90-118">Wählen Sie **Azure Active Directory** > **Benutzer** > **Benutzereinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="1df90-118">Select **Azure Active Directory** > **Users** > **User settings**.</span></span>
3. <span data-ttu-id="1df90-119">Wählen Sie unter **Externe Benutzer** die Option **Manage external collaboration settings** (Einstellungen für externe Zusammenarbeit verwalten) aus.</span><span class="sxs-lookup"><span data-stu-id="1df90-119">Under **External users**, select **Manage external collaboration settings**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="1df90-120">Sie können auch über die Seite **Organisationsbeziehungen** auf die **Einstellungen für externe Zusammenarbeit** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1df90-120">The **External collaboration settings** are also available from the **Organizational relationships** page.</span></span> <span data-ttu-id="1df90-121">Navigieren Sie in Azure Active Directory unter **Verwalten** zu **Organisationsbeziehungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="1df90-121">In Azure Active Directory, under **Manage**, go to **Organizational relationships** > **Settings**.</span></span>
4. <span data-ttu-id="1df90-122">Wählen Sie auf der Seite **Einstellungen für externe Zusammenarbeit** die Richtlinien aus, die Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1df90-122">On the **External collaboration settings** page, choose the policies you want to enable.</span></span>

  - <span data-ttu-id="1df90-123">**Berechtigungen für Gastbenutzer sind eingeschränkt**: Diese Richtlinie bestimmt die Berechtigungen für Gäste in Ihrem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="1df90-123">**Guest users permissions are limited**: This policy determines permissions for guests in your directory.</span></span> <span data-ttu-id="1df90-124">Wählen Sie **Ja**, um Gäste für bestimmte Verzeichnisaufgaben, z. B. dem Auflisten von Benutzern, Gruppen oder anderen Verzeichnisressourcen, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="1df90-124">Select **Yes** to block guests from certain directory tasks, like enumerating users, groups, or other directory resources.</span></span> <span data-ttu-id="1df90-125">Wählen Sie **Nein**, um Gästen denselben Zugriff auf Verzeichnisdaten wie normale Benutzer in Ihrem Verzeichnis zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="1df90-125">Select **No** to give guests the same access to directory data as  regular users in your directory.</span></span>
   - <span data-ttu-id="1df90-126">**Administratoren und Benutzer mit der Rolle „Einladender“ können einladen**: Damit Administratoren und Benutzern mit der Rolle „Einladender“ Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="1df90-126">**Admins and users in the guest inviter role can invite**: To allow admins and users in the "Guest Inviter" role to invite guests, set this policy to **Yes**.</span></span>
   - <span data-ttu-id="1df90-127">**Mitglieder können einladen**: Damit Mitglieder Ihres Verzeichnisses, die nicht Administratoren sind, Gäste einladen können, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="1df90-127">**Members can invite**: To allow non-admin members of your directory to invite guests, set this policy to **Yes**.</span></span>
   
       > [!NOTE]
       > <span data-ttu-id="1df90-128">Wenn Sie **Mitglieder können einladen** auf **Nein** festlegen und dann den Gastzugriff in Office 365-Gruppen und Microsoft Teams aktivieren, können Administratoren Gasteinladungen auf Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="1df90-128">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="1df90-129">Nachdem sich Gäste im Verzeichnis befinden, können sie von Nicht-Administratormitgliedern, die Teambesitzer sind, Teams hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="1df90-129">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span> <span data-ttu-id="1df90-130">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="1df90-130">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="1df90-131">Damit Gastzugriff überhaupt in Teams funktioniert, müssen Sie die **Mitglieder können** auf **Ja**einladen einstellen.</span><span class="sxs-lookup"><span data-stu-id="1df90-131">For guest access to work at all in Teams, you must set **Members can invite** to **Yes**.</span></span>   
   - <span data-ttu-id="1df90-132">**Gäste können einladen**: Wenn Sie Gästen ermöglichen wollen, andere Gäste einzuladen, legen Sie diese Richtlinie auf **Ja** fest.</span><span class="sxs-lookup"><span data-stu-id="1df90-132">**Guests can invite**: To allow guests to invite other guests, set this policy to **Yes**.</span></span>
       > [!IMPORTANT]
       > <span data-ttu-id="1df90-133">Derzeit unterstützt Teams die Rolle "gastinviter" nicht, daher können Gäste keine anderen Gäste in Teams einladen, selbst wenn Sie die Möglichkeit haben, die Gäste zu " **Ja**" **einzuladen** .</span><span class="sxs-lookup"><span data-stu-id="1df90-133">Currently, Teams doesn't support the guest inviter role, so even if you set **Guests can invite** to **Yes**, guests can't invite other guests in Teams.</span></span>
   - <span data-ttu-id="1df90-134">**Einmalkennung per E-Mail für Gastbenutzer aktivieren (Vorschauversion)**: Weitere Informationen zum Feature Einmalkennung finden Sie unter [Authentifizierung mit Einmalkennung per E-Mail (Vorschauversion)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span><span class="sxs-lookup"><span data-stu-id="1df90-134">**Enable email one-time passcode for guests (Preview)**: For more information about the one-time passcode feature, see [Email one-time passcode authentication (preview)](https://docs.microsoft.com/azure/active-directory/b2b/one-time-passcode).</span></span>
   - <span data-ttu-id="1df90-135">**Einschränkungen für die Zusammenarbeit**: Weitere Informationen zum Zulassen oder Blockieren von Einladungen zu bestimmten Domänen finden Sie unter [Zulassen oder Blockieren von Einladungen für B2B-Benutzer von bestimmten Organisationen](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span><span class="sxs-lookup"><span data-stu-id="1df90-135">**Collaboration restrictions**: For more information about allowing or blocking invitations to specific domains, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>
      > [!NOTE]
      > <span data-ttu-id="1df90-136">Informationen zu Einschränkungen der Zusammenarbeit finden Sie unter [Aktivieren der externen B2B-Zusammenarbeit und Verwalten der Personen, die Gäste einladen können](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="1df90-136">For collaboration restrictions, see [Enable B2B external collaboration and manage who can invite guests](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>
      
 
<span data-ttu-id="1df90-137">Weitere Informationen zum Steuern der Einladung von Gästen finden Sie unter [Delegieren von Einladungen für Azure Active Directory B2B-Zusammenarbeit](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span><span class="sxs-lookup"><span data-stu-id="1df90-137">For more information about controlling who can invite guests, see [Delegate invitations for Azure Active Directory B2B collaboration](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations).</span></span>


## <a name="step-3-configure-office-365-groups"></a><span data-ttu-id="1df90-138">Schritt 3: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="1df90-138">Step 3: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="1df90-139">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Dienste und Add-Ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="1df90-139">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="1df90-140">Stellen Sie sicher, dass **Gruppenmitglieder von außerhalb Ihrer Organisation dürfen auf Gruppeninhalte zugreifen** auf **Ein** gestellt ist.</span><span class="sxs-lookup"><span data-stu-id="1df90-140">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="1df90-141">Wenn diese Einstellung deaktiviert ist, können Gäste nicht auf Gruppeninhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1df90-141">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="1df90-142">Stellen Sie sicher, dass **Gruppenbesitzer dürfen Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **Ein** gestellt ist.</span><span class="sxs-lookup"><span data-stu-id="1df90-142">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="1df90-143">Wenn diese Einstellung deaktiviert ist, können Teambesitzer keine neuen Gäste hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1df90-143">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="1df90-144">Mindestens diese Einstellung muss aktiviert sein, um den Gastzugriff zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1df90-144">At a minimum, this setting must be On to support guest access.</span></span>

     ![Screenshot der Schaltflächen für Office 365-Gruppen](media/guest-access-checklist-office365.png)

<span data-ttu-id="1df90-146">Detaillierte Anweisungen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten des Gastzugriffs in Office 365-Gruppen](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und [Steuern des Gastzugriffs in Office 365-Gruppen](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="1df90-146">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 Groups](https://support.office.com/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and [Control guest access in Office 365 Groups](Teams-dependencies.md#control-guest-access-in-office-365-groups).</span></span>
 

## <a name="step-4-configure-sharing-in-office-365"></a><span data-ttu-id="1df90-147">Schritt 4: Konfigurieren der Freigabe in Office 365</span><span class="sxs-lookup"><span data-stu-id="1df90-147">Step 4: Configure sharing in Office 365</span></span> 

<span data-ttu-id="1df90-148">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="1df90-148">Make sure that users can add guests.</span></span> <span data-ttu-id="1df90-149">Dazu gehen Sie so vor:</span><span class="sxs-lookup"><span data-stu-id="1df90-149">Here's how:</span></span>

1. <span data-ttu-id="1df90-150">Navigieren Sie dazu im Microsoft 365 Admin Center zu **Einstellungen** > **Sicherheit & Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="1df90-150">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Diensteinstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="1df90-152">Wählen Sie unter **Freigabe** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="1df90-152">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="1df90-154">Legen Sie **Benutzer dürfen neue Gäste zur Organisation hinzufügen** auf **Ein** fest und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1df90-154">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für einen Umschalter von Freigabeeinstellungen](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="1df90-156">Diese Einstellung entspricht der Einstellung " **Mitglieder können einladen** " in den **Benutzereinstellungen** > "**externe Benutzer** " in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="1df90-156">This setting is equivalent to the **Members can invite** setting in **User settings** > **External users** in Azure AD.</span></span>  


## <a name="step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="1df90-157">Schritt 5: Überprüfen der Freigabe Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="1df90-157">Step 5: Verify sharing setting in SharePoint</span></span>

<span data-ttu-id="1df90-158">Das hier ist ein bisschen ein Rätsel.</span><span class="sxs-lookup"><span data-stu-id="1df90-158">This one's a bit of a brain teaser.</span></span> <span data-ttu-id="1df90-159">Gastzugriff in Teams funktioniert nicht, wenn im SharePoint Admin Center die Einstellung " **Freigabe außerhalb Ihrer Organisation nicht zulassen** " aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1df90-159">Guest access in Teams doesn't work if the **Don't allow sharing outside your organization** setting is selected in the SharePoint admin center.</span></span>

1. <span data-ttu-id="1df90-160">Melden Sie sich beim Microsoft 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="1df90-160">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="1df90-161">Klicken Sie auf **Admin Center** und wählen Sie dann **SharePoint** aus.</span><span class="sxs-lookup"><span data-stu-id="1df90-161">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="1df90-162">Wählen Sie im SharePoint Admin Center **Freigabe** aus.</span><span class="sxs-lookup"><span data-stu-id="1df90-162">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="1df90-163">Vergewissern Sie sich, dass die Option für **Freigabe außerhalb Ihrer Organisation nicht zulassen** *nicht* aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1df90-163">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Screenshot zeigt ein Beispiel für einen Umschalter von Einstellungen in SharePoint.](media/guest-access-checklist-SPOSettings1.png)


## <a name="step-6-set-up-guest-user-permissions"></a><span data-ttu-id="1df90-165">Schritt 6: Einrichten von Gastbenutzer Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1df90-165">Step 6: Set up guest user permissions</span></span>

<span data-ttu-id="1df90-166">Konfigurieren Sie in der Teams-Anwendung auf der einzelnen Teamebene Gastberechtigungen, die Steuern, ob Gäste Kanäle erstellen, aktualisieren oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="1df90-166">In the Teams application, at the individual team level, configure guest permissions that control whether guests can create, update, or delete channels.</span></span> <span data-ttu-id="1df90-167">Teams-Administratoren und Teambesitzer können diese Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1df90-167">Teams admins as well as team owners can configure these settings.</span></span>

![Screenshot zeigt ein Beispiel für einen Umschalter von Teams-/Kanaleinstellungen.](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="1df90-169">Weitere Informationen zum Gastzugriff finden Sie unter [Gastzugriff in Teams](guest-access.md) und [Aktivieren oder Deaktivieren des Gastzugriffs auf Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="1df90-169">To learn more about guest access, see [Guest access in Teams](guest-access.md) and [Turn on or turn off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="1df90-170">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="1df90-170">Troubleshooting</span></span>

<span data-ttu-id="1df90-171">Wenn Sie Probleme beim Einrichten des Gastzugriffs oder beim Hinzufügen von Gästen in Teams haben, verwenden Sie diese Ressourcen, um Ihnen zu helfen:</span><span class="sxs-lookup"><span data-stu-id="1df90-171">If you have problems setting up guest access or adding guests in Teams, use these resources to help you:</span></span>

[<span data-ttu-id="1df90-172">Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1df90-172">Troubleshoot problems with guest access in Microsoft Teams</span></span>](troubleshoot-guest-access.md)

[<span data-ttu-id="1df90-173">Problembehandlung für Teams</span><span class="sxs-lookup"><span data-stu-id="1df90-173">Teams troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/)



