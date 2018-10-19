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
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 256ca09b8da5ccaed3ab5797e9d67246cebfee4e
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "25678141"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="984b1-103">Teams Gast Access Prüfliste</span><span class="sxs-lookup"><span data-stu-id="984b1-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="984b1-104">Verwenden Sie diese Prüfliste, mit denen Sie aktivieren und Konfigurieren des Gast Access-Features in Microsoft-Teams gemäß den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="984b1-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>




## <a name="--enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="984b1-105">□ Gast-Zugriff auf der Ebene der Mandant aktivieren</span><span class="sxs-lookup"><span data-stu-id="984b1-105">□  Enable guest access at the tenant level</span></span>

<span data-ttu-id="984b1-106">Wechseln Sie zu der Teams & Skype für Business-Verwaltungskonsole über https://admin.teams.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="984b1-106">Go to the Teams & Skype for Business Admin Center, via https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="984b1-107">Wählen Sie hier "Org geltende Settings", und wählen Sie die Registerkarte "Gastzugriff" und schließlich auf dieser Registerkarte wählen Sie 'Zulassen Gast Access in Microsoft-Teams' auf aktiviert.</span><span class="sxs-lookup"><span data-stu-id="984b1-107">From here, select 'Org-Wide Settings', and selec the 'Guest Access' tab. Lastly, within this tab, select 'Allow guest access in Microsoft Teams' to enabled.</span></span> 

## <Need to display a photo of the new admin center>

## <a name="-enable-specific-settings-for-channels"></a><span data-ttu-id="984b1-108">□ bestimmte Einstellungen für Kanäle aktivieren</span><span class="sxs-lookup"><span data-stu-id="984b1-108">□ Enable specific settings for channels</span></span> 
<span data-ttu-id="984b1-109">Konfigurieren Sie in der Anwendung Teams auf Ebene der einzelnen Teams Gastberechtigungen, sodass Gäste erstellen, aktualisieren und Löschen von Kanäle können.</span><span class="sxs-lookup"><span data-stu-id="984b1-109">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="984b1-110">Zusätzlich zur-Administratoren können Team Besitzer dieser Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="984b1-110">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot zeigt ein Beispiel für eine Umschaltfläche Team/Channel-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)


<span data-ttu-id="984b1-112">Weitere Informationen, einschließlich videoanleitungen finden Sie unter [Gast Access in Microsoft-Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="984b1-112">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>



## <a name="--configure-sharing-in-office-365"></a><span data-ttu-id="984b1-113">□ Konfigurieren der Freigabe von in Office 365</span><span class="sxs-lookup"><span data-stu-id="984b1-113">□  Configure Sharing in Office 365</span></span> 

<span data-ttu-id="984b1-114">□ Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="984b1-114">□ Make sure users can add guests.</span></span> <span data-ttu-id="984b1-115">Hier ist wie:</span><span class="sxs-lookup"><span data-stu-id="984b1-115">Here's how:</span></span>

1. <span data-ttu-id="984b1-116">Wechseln Sie in das Office 365 Administrationscenter auf **Einstellungen** > **Sicherheit und Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="984b1-116">In the Office 365 admin center, go to **Settings** > **Security & privacy**.</span></span>
<span data-ttu-id="984b1-117">![Screenshot zeigt ein Beispiel einer Services-Einstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)</span><span class="sxs-lookup"><span data-stu-id="984b1-117">![Screenshot shows an example of a Services settings](media/guest-access-checklist-Office365Admin_Services_addins.png)</span></span>
1. <span data-ttu-id="984b1-118">Wählen Sie in der **Freigabe** **Bearbeiten**. ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen Bearbeiten-Schaltfläche](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span><span class="sxs-lookup"><span data-stu-id="984b1-118">In **Sharing**, select **Edit**.![Screenshot shows an example of a Sharing Settings edit button](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)</span></span>
2. <span data-ttu-id="984b1-119">Legen Sie **dazu, Benutzern das Hinzufügen von neuen Gäste auf diese Organisation** auf **aktiviert**, und klicken Sie dann auf **Speichern**. ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span><span class="sxs-lookup"><span data-stu-id="984b1-119">Set **Let users add new guests to this organization** to **On**, and then click **Save**.![Screenshot shows an example of a Sharing Settings toggle](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)</span></span>
 

 > [!NOTE]
> <span data-ttu-id="984b1-120">Diese Einstellung entspricht der Einstellung **Mitglieder einladen können** in benutzereinstellungen > externe Benutzer in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="984b1-120">This setting is equivalent to the **Members can invite** setting in  User settings > External users  in Azure AD.</span></span>  




## <a name="-configure-office-365-groups"></a><span data-ttu-id="984b1-121">□ Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="984b1-121">□ Configure Office 365 Groups</span></span>

<span data-ttu-id="984b1-122">Wechseln Sie in das Office 365 Administrationscenter auf **Einstellungen** > **Services & -Add-ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="984b1-122">In the Office 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>

<span data-ttu-id="984b1-123">Stellen Sie sicher, dass **Let Gruppenmitglieder außerhalb der Organisation Access Gruppe Inhalt** auf **aktiviert**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="984b1-123">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="984b1-124">Wenn diese Einstellung deaktiviert ist, werden nicht Gäste auf eine beliebige Gruppe Inhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="984b1-124">If this setting is turned off, guests won't be able to access any group content.</span></span>

<span data-ttu-id="984b1-125">Stellen Sie sicher, dass **Let Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **aktiviert**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="984b1-125">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="984b1-126">Wenn diese Einstellung deaktiviert ist, werden nicht Besitzer Team neue Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="984b1-126">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="984b1-127">Mindestens muss diese Einstellung für die Unterstützung Gast Zugriffs "auf" sein.</span><span class="sxs-lookup"><span data-stu-id="984b1-127">At a minimum,  this setting must be "on" to support guest access.</span></span>

<span data-ttu-id="984b1-128">Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie im Abschnitt "Office 365 Groups" im [Autorisieren Gast in Microsoft-Teams](Teams-dependencies.md) und [Zulassen/Blockieren Gastzugriff auf Office 365-Gruppen](https://go.microsoft.com/fwlink/?linkid=869658).</span><span class="sxs-lookup"><span data-stu-id="984b1-128">For detailed instructions about configuring these settings, see the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md) and [Allow/Block guest access to Office 365 groups](https://go.microsoft.com/fwlink/?linkid=869658).</span></span>
 


## <a name="-configure-settings-in-azure-ad-business-to-business-b2b"></a><span data-ttu-id="984b1-129">□ Configure Settings in Azure AD Business-to-Business (B2B)</span><span class="sxs-lookup"><span data-stu-id="984b1-129">□ Configure settings in Azure AD business-to-business (B2B)</span></span>
1. <span data-ttu-id="984b1-130">Melden Sie sich bei https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="984b1-130">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="984b1-131">Klicken Sie im linken Bereich auf **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="984b1-131">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="984b1-132">Klicken Sie unter **Verwalten**auf **benutzereinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="984b1-132">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="984b1-133">Klicken Sie unter **externe Benutzer**klicken Sie auf **Einstellungen für externe verwalten für die Zusammenarbeit**</span><span class="sxs-lookup"><span data-stu-id="984b1-133">Under **External users**, click **Manage External collaboration settings**</span></span>
5. <span data-ttu-id="984b1-134">Klicken Sie auf der Seite **Einstellungen für die externe Zusammenarbeit** sicherstellen Sie, dass **Mitglieder können einladen** auf **Ja**festgelegt ist. ![Screenshot zeigt ein Beispiel für eine Umschaltfläche AAD Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="984b1-134">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.![Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    

<span data-ttu-id="984b1-135">► Mindestens Gäste unterstützen, müssen **Mitglieder einladen können** auf **Ja**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="984b1-135">► At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>

> > [!NOTE]
> > <span data-ttu-id="984b1-136">Wenn Sie auf **Nein** **können Mitglieder einladen festlegen** und Gastzugriff in Office 365-Gruppen und Microsoft-Teams, aktivieren, können Administratoren Gast Einladungen an Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="984b1-136">If you set **Members can invite** to **No** and enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="984b1-137">Nachdem das Verzeichnis Gäste sind, können sie Teams von nicht-Administrator Membern (Team Besitzer) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="984b1-137">After guests are in the directory, they can be added to Teams by non-admin members (team owners).</span></span>


<span data-ttu-id="984b1-138">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="984b1-138">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>







## <a name="-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="984b1-139">□ Verify sharing Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="984b1-139">□ Verify sharing setting in SharePoint</span></span>
1. <span data-ttu-id="984b1-140">Melden Sie sich beim Office 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="984b1-140">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="984b1-141">Klicken Sie auf **Administrationscenter**, und wählen Sie dann **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="984b1-141">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="984b1-142">Wählen Sie in der SharePoint-Verwaltungskonsole **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="984b1-142">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="984b1-143">Stellen Sie sicher, dass die Option für **nicht zulassen Freigabe außerhalb Ihrer Organisation** *nicht* ausgewählt ist. ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Sparepoint Online-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="984b1-143">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.![Screenshot shows an example of a Sparepoint Online Settings toggle.</span></span> ](media/guest-access-checklist-SPOSettings1.png)



## <a name="-verify-account-licenses-and-types"></a><span data-ttu-id="984b1-144">□ Verify Konto Lizenzen und Typen</span><span class="sxs-lookup"><span data-stu-id="984b1-144">□ Verify account licenses and types</span></span>

- <span data-ttu-id="984b1-145">**Konto für Teams lizenziert**: bei einem Gastkonto "" als Stamm eines echten Benutzerkontos in einige andere Office 365-Mandanten mit echten dem Benutzerkonto muss lizenziert für Teams für "Gast"aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="984b1-145">**Account licensed for Teams**: For a "Guest" account rooted in a real user account in some other Office 365 tenant, that real user account must be licensed for Teams for “Guest”.</span></span> 
- <span data-ttu-id="984b1-146">**Konto muss Office 365 Schule oder arbeiten, oder MSA Konto**: aktuell, können Benutzer, die e-Mail-Adresse für ein Azure Active Directory, Office 365 Arbeit oder Schule Konto oder einem Microsoft-Konto (MSA) als Gast hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="984b1-146">**Account must be Office 365 school or work account, or MSA account**: Currently, users who have an email address corresponding to an Azure Active Directory, Office 365 work or school account, or a Microsoft account (MSA) can be added as a guest user.</span></span> 
 
## <a name="-configure-environment"></a><span data-ttu-id="984b1-147">□ Konfigurieren-Umgebung</span><span class="sxs-lookup"><span data-stu-id="984b1-147">□ Configure environment</span></span>


<span data-ttu-id="984b1-148">Gäste sind erforderlich, um die mehrstufige Authentifizierung (mehrstufiger Authentifizierung das) verwenden, wenn der hosting Mandanten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="984b1-148">Guests are required to use multi-factor authentication (MFA) if the hosting tenant requires it.</span></span>
<span data-ttu-id="984b1-149">Weitere Informationen finden Sie unter [Modelle Identität und Authentifizierung in Microsoft-Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="984b1-149">For more details, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

## <a name="-understand-limitations-for-guests"></a><span data-ttu-id="984b1-150">□ Machen Sie sich mit Einschränkungen für Gäste</span><span class="sxs-lookup"><span data-stu-id="984b1-150">□ Understand limitations for guests</span></span>

<span data-ttu-id="984b1-151">Die Erfahrung Gast hat Einschränkungen Verhalten ist erwünscht.</span><span class="sxs-lookup"><span data-stu-id="984b1-151">The guest experience has limitations by design.</span></span> <span data-ttu-id="984b1-152">Stellen Sie sicher, dass die Erfahrung Gast verstehen, damit Sie nicht versuchen zu reparieren, die ein Problem nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="984b1-152">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span>
<span data-ttu-id="984b1-153">Hier wird beispielsweise eine Liste einiger Funktionen, die nicht an einen Gast in Microsoft-Teams zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="984b1-153">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="984b1-154">OneDrive für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="984b1-154">OneDrive for Business</span></span>
- <span data-ttu-id="984b1-155">Suche nach Personen außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="984b1-155">People search outside of Teams</span></span>
- <span data-ttu-id="984b1-156">Kalender, geplante Besprechungen oder Besprechungsdetails</span><span class="sxs-lookup"><span data-stu-id="984b1-156">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="984b1-157">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="984b1-157">PSTN</span></span>
- <span data-ttu-id="984b1-158">Organigramm</span><span class="sxs-lookup"><span data-stu-id="984b1-158">Organization chart</span></span>
- <span data-ttu-id="984b1-159">Erstellen Sie oder ändern Sie ein team</span><span class="sxs-lookup"><span data-stu-id="984b1-159">Create or revise a team</span></span>
- <span data-ttu-id="984b1-160">Wechseln Sie für ein team</span><span class="sxs-lookup"><span data-stu-id="984b1-160">Browse for a team</span></span>
- <span data-ttu-id="984b1-161">Hochladen von Dateien in einer Person chat</span><span class="sxs-lookup"><span data-stu-id="984b1-161">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="984b1-162">Weitere Informationen finden Sie unter [Was die Erfahrung Gast entspricht](guest-experience.md) und [Gast Access in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="984b1-162">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>




## <a name="troubleshooting"></a><span data-ttu-id="984b1-163">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="984b1-163">Troubleshooting</span></span>

<span data-ttu-id="984b1-164">Wenn Sie Probleme beim Hinzufügen von Gäste in Microsoft-Teams haben, finden Sie im [Handbuch zur Problembehandlung für Gast Zugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="984b1-164">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


