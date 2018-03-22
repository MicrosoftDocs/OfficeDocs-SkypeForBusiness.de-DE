---
title: Microsoft-Teams Gast Access Prüfliste
author: romanma
ms.author: romanma
manager: serdars
ms.date: 2/15/18
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Verwenden Sie diese Prüfliste, um Gastzugriff in Microsoft Access-Teams Gast einrichten.
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53800ddf452fd6596abe3e4404c79352483e946
ms.sourcegitcommit: ccbe086ccb2c0be716984010a1253a4c8c0276b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2018
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="481a5-103">Teams Gast Access Prüfliste</span><span class="sxs-lookup"><span data-stu-id="481a5-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="481a5-104">Verwenden Sie diese Prüfliste, mit denen Sie aktivieren und Konfigurieren des Gast Access-Features in Microsoft-Teams gemäß den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="481a5-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="481a5-105">□ Gast-Zugriff auf der Ebene der Mandant aktivieren</span><span class="sxs-lookup"><span data-stu-id="481a5-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="481a5-106">Zumindest müssen Sie Microsoft-Teams, für alle Benutzer des Lizenztyps **Gast**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="481a5-106">At a minimum, you must turn on Microsoft Teams for all users of the license type **Guest**.</span></span> <span data-ttu-id="481a5-107">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Gastzugriff auf Microsoft-Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="481a5-107">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>

![Screenshot zeigt ein Beispiel für eine Umschaltfläche Teams Einstellungen](media/guest-access-checklist-TeamsSettings1.png)



## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="481a5-109">□ bestimmte Einstellungen für Kanäle aktivieren</span><span class="sxs-lookup"><span data-stu-id="481a5-109">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="481a5-110">Konfigurieren Sie in der Anwendung Teams auf Ebene der einzelnen Teams Gastberechtigungen, sodass Gäste erstellen, aktualisieren und Löschen von Kanäle können.</span><span class="sxs-lookup"><span data-stu-id="481a5-110">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="481a5-111">Zusätzlich zur-Administratoren können Team Besitzer dieser Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="481a5-111">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot zeigt ein Beispiel für eine Umschaltfläche Team/Channel-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="481a5-113">Weitere Informationen, einschließlich videoanleitungen finden Sie unter [Gast Access in Microsoft-Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="481a5-113">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="481a5-114">□ Konfigurieren der Freigabe von in Office 365</span><span class="sxs-lookup"><span data-stu-id="481a5-114">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="481a5-115">□ Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="481a5-115">□ Make sure users can add guests.</span></span> <span data-ttu-id="481a5-116">Hier ist wie:</span><span class="sxs-lookup"><span data-stu-id="481a5-116">Here's how:</span></span>

1. <span data-ttu-id="481a5-117">Wechseln Sie in das Office 365 Administrationscenter auf **Einstellungen** > **Sicherheit und Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="481a5-117">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="481a5-118">![Screenshot zeigt ein Beispiel einer Services-Einstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="481a5-118">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="481a5-119">Wählen Sie in der **Freigabe** **Bearbeiten**. ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen Bearbeiten-Schaltfläche](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="481a5-119">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="481a5-120">Legen Sie **dazu, Benutzern das Hinzufügen von neuen Gäste auf diese Organisation** auf **aktiviert**, und klicken Sie dann auf **Speichern**. ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="481a5-120">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="481a5-121">Diese Einstellung entspricht der Einstellung **Mitglieder einladen können** in benutzereinstellungen > externe Benutzer in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="481a5-121">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="481a5-122">□ Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="481a5-122">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="481a5-123">Wechseln Sie in das Office 365 Administrationscenter auf **Einstellungen** > **Services & -Add-ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="481a5-123">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="481a5-124">Stellen Sie sicher, dass **Let Gruppenmitglieder außerhalb der Organisation Access Gruppe Inhalt** auf **aktiviert**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="481a5-124">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="481a5-125">Wenn diese Einstellung deaktiviert ist, werden nicht Gäste auf eine beliebige Gruppe Inhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="481a5-125">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="481a5-126">Stellen Sie sicher, dass **Let Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **aktiviert**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="481a5-126">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="481a5-127">Wenn diese Einstellung deaktiviert ist, werden nicht Besitzer Team neue Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="481a5-127">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="481a5-128">(Allerdings, wenn ein Administrator Gast Azure AD hinzugefügt haben, klicken Sie dann der Besitzer Team hinzufügen, dass der Benutzer an das Team wäre.) Mindestens muss diese Einstellung für die Unterstützung Gast Zugriffs "auf" sein.</span><span class="sxs-lookup"><span data-stu-id="481a5-128">(However, if an admin had added a guest user to Azure AD, then the Team owner would be able to add that user to the Team.) At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="481a5-129">Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie im Abschnitt "Office 365 Groups" im [Autorisieren Gast in Microsoft-Teams](Teams-dependencies.md) und [Zulassen/Blockieren Gastzugriff auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="481a5-129">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="481a5-130">□ Configure Settings in Azure AD Business-to-Business (B2B)</span><span class="sxs-lookup"><span data-stu-id="481a5-130">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="481a5-131">Melden Sie sich bei https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="481a5-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="481a5-132">Klicken Sie im linken Bereich auf **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="481a5-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="481a5-133">Klicken Sie unter **Verwalten**auf **benutzereinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="481a5-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="481a5-134">**Externe Benutzer**stellen Sie sicher, dass **Mitglieder können einladen** auf **Ja**festgelegt ist. ![Screenshot zeigt ein Beispiel für eine Umschaltfläche AAD Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="481a5-134">In **External users**, make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="481a5-135">► Mindestens Gäste unterstützen, müssen **Mitglieder einladen können** auf **Ja**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="481a5-135">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> <span data-ttu-id="481a5-136">Wenn Sie auf **Nein** **können Mitglieder einladen festlegen** und Gastzugriff in Office 365-Gruppen und Microsoft-Teams, aktivieren, können Administratoren Gast Einladungen an Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="481a5-136">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="481a5-137">Nachdem das Verzeichnis Gäste sind, können sie Teams von nicht-Administrator Membern (Team Besitzer) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="481a5-137">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="481a5-138">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="481a5-138">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="481a5-139">□ Verify sharing Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="481a5-139">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="481a5-140">Melden Sie sich beim Office 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="481a5-140">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="481a5-141">Klicken Sie auf **Administrationscenter**, und wählen Sie dann **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="481a5-141">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="481a5-142">Wählen Sie in der SharePoint-Verwaltungskonsole **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="481a5-142">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="481a5-143">Stellen Sie sicher, dass die Option für **nicht zulassen Freigabe außerhalb Ihrer Organisation** *nicht* ausgewählt ist. ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Sparepoint Online-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="481a5-143">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="481a5-144">□ Verify Konto Lizenzen und Typen</span><span class="sxs-lookup"><span data-stu-id="481a5-144">□ Verify account licenses and types</span></span>

- <span data-ttu-id="481a5-145">**Konto für Teams lizenziert**: bei einem Gastkonto "" als Stamm eines echten Benutzerkontos in einige andere Office 365-Mandanten mit echten dem Benutzerkonto muss lizenziert für Teams für "Gast"aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="481a5-145">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="481a5-146">**Konto muss Office 365 Schule oder arbeiten, oder MSA Konto**: aktuell, können Benutzer, die e-Mail-Adresse für ein Azure Active Directory, Office 365 Arbeit oder Schule Konto oder einem Microsoft-Konto (MSA) als Gast hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="481a5-146">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="481a5-147">□ Konfigurieren-Umgebung</span><span class="sxs-lookup"><span data-stu-id="481a5-147">□ Configure environment</span></span>


<span data-ttu-id="481a5-148">Gäste sind erforderlich, um die mehrstufige Authentifizierung (mehrstufiger Authentifizierung das) verwenden, wenn der hosting Mandanten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="481a5-148">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="481a5-149">Weitere Informationen finden Sie unter [Modelle Identität und Authentifizierung in Microsoft-Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="481a5-149">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="481a5-150">□ Machen Sie sich mit Einschränkungen für Gäste</span><span class="sxs-lookup"><span data-stu-id="481a5-150">□ Understand limitations for guests</span></span>

<span data-ttu-id="481a5-151">Die Erfahrung Gast hat Einschränkungen Verhalten ist erwünscht.</span><span class="sxs-lookup"><span data-stu-id="481a5-151">The guest experience has limitations by design.</span></span> <span data-ttu-id="481a5-152">Stellen Sie sicher, dass die Erfahrung Gast verstehen, damit Sie nicht versuchen zu reparieren, die ein Problem nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="481a5-152">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="481a5-153">Hier wird beispielsweise eine Liste einiger Funktionen, die nicht an einen Gast in Microsoft-Teams zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="481a5-153">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="481a5-154">OneDrive für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="481a5-154">OneDrive for Business</span></span>
- <span data-ttu-id="481a5-155">Suche nach Personen außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="481a5-155">People search outside of Teams</span></span>
- <span data-ttu-id="481a5-156">Kalender, geplante Besprechungen oder Besprechungsdetails</span><span class="sxs-lookup"><span data-stu-id="481a5-156">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="481a5-157">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="481a5-157">PSTN</span></span>
- <span data-ttu-id="481a5-158">Organigramm</span><span class="sxs-lookup"><span data-stu-id="481a5-158">Organization chart</span></span>
- <span data-ttu-id="481a5-159">Erstellen Sie oder ändern Sie ein team</span><span class="sxs-lookup"><span data-stu-id="481a5-159">Create or revise a team</span></span>
- <span data-ttu-id="481a5-160">Wechseln Sie für ein team</span><span class="sxs-lookup"><span data-stu-id="481a5-160">Browse for a team</span></span>
- <span data-ttu-id="481a5-161">Hochladen von Dateien in einer Person chat</span><span class="sxs-lookup"><span data-stu-id="481a5-161">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="481a5-162">Weitere Informationen finden Sie unter [Was die Erfahrung Gast entspricht](guest-experience.md) und [Gast Access in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="481a5-162">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="481a5-163">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="481a5-163">Troubleshooting</span></span>

<span data-ttu-id="481a5-164">Wenn Sie Probleme beim Hinzufügen von Gäste in Microsoft-Teams haben, finden Sie im [Handbuch zur Problembehandlung für Gast Zugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="481a5-164">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


