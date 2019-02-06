---
title: Prüfliste für den Microsoft Teams-Gastzugriff
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/22/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
description: Verwenden Sie diese Prüfliste, um Gastzugriff in Microsoft Access-Teams Gast einrichten.
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 660b838c38da478be2f1226fcdd1b104c3b10b54
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "29753932"
---
<a name="teams-guest-access-checklist"></a><span data-ttu-id="ccfe7-103">Teams Gast Access Prüfliste</span><span class="sxs-lookup"><span data-stu-id="ccfe7-103">Teams Guest Access checklist</span></span>
==========================================

<span data-ttu-id="ccfe7-104">Verwenden Sie diese Prüfliste, mit denen Sie aktivieren und Konfigurieren des Gast Access-Features in Microsoft-Teams gemäß den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-104">Use this checklist to help you enable and configure the Guest Access feature in Microsoft Teams according to the preferences of your organization.</span></span>

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="ccfe7-105">Verstehen der Grenzen für Gäste</span><span class="sxs-lookup"><span data-stu-id="ccfe7-105">Understand the limitations for guests</span></span>

<span data-ttu-id="ccfe7-106">Die Erfahrung Gast hat Einschränkungen Verhalten ist erwünscht.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-106">The guest experience has limitations by design.</span></span> <span data-ttu-id="ccfe7-107">Stellen Sie sicher, dass die Erfahrung Gast verstehen, damit Sie nicht versuchen zu reparieren, die ein Problem nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-107">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="ccfe7-108">Hier wird beispielsweise eine Liste einiger Funktionen, die nicht an einen Gast in Microsoft-Teams zur Verfügung steht:</span><span class="sxs-lookup"><span data-stu-id="ccfe7-108">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="ccfe7-109">OneDrive für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ccfe7-109">OneDrive for Business</span></span>
- <span data-ttu-id="ccfe7-110">Suche nach Personen außerhalb von Teams</span><span class="sxs-lookup"><span data-stu-id="ccfe7-110">People search outside of Teams</span></span>
- <span data-ttu-id="ccfe7-111">Kalender, geplante Besprechungen oder Besprechungsdetails</span><span class="sxs-lookup"><span data-stu-id="ccfe7-111">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="ccfe7-112">Telefonfestnetz (PSTN)</span><span class="sxs-lookup"><span data-stu-id="ccfe7-112">PSTN</span></span>
- <span data-ttu-id="ccfe7-113">Organigramm</span><span class="sxs-lookup"><span data-stu-id="ccfe7-113">Organization chart</span></span>
- <span data-ttu-id="ccfe7-114">Erstellen Sie oder ändern Sie ein team</span><span class="sxs-lookup"><span data-stu-id="ccfe7-114">Create or revise a team</span></span>
- <span data-ttu-id="ccfe7-115">Wechseln Sie für ein team</span><span class="sxs-lookup"><span data-stu-id="ccfe7-115">Browse for a team</span></span>
- <span data-ttu-id="ccfe7-116">Hochladen von Dateien in einer Person chat</span><span class="sxs-lookup"><span data-stu-id="ccfe7-116">Upload files to a person-to-person chat</span></span>

<span data-ttu-id="ccfe7-117">Weitere Informationen finden Sie unter [Was die Erfahrung Gast entspricht](guest-experience.md) und [Gast Access in Office 365-Gruppen](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="ccfe7-117">For more details, see [What the guest experience is like](guest-experience.md) and [Guest access in Office 365 groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>

### <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="ccfe7-118">Gastzugriff im Vergleich zum externen Zugriff (Verbund)</span><span class="sxs-lookup"><span data-stu-id="ccfe7-118">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="ccfe7-119">Wenn Ihre Gäste Lizenz Fehlermeldungen angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="ccfe7-119">If your guests are seeing license errors</span></span>

<span data-ttu-id="ccfe7-120">Gast Access in Microsoft-Teams verwendet Azure Active Directory-Business, Business (B2B) und seine Lizenzierungsmodell.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-120">Guest access in Microsoft Teams uses Azure Active Directory Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="ccfe7-121">Wenn Sie die Lizenzierung Fehler angezeigt werden, stellen Sie sicher, lesen die Lizenzierung B2B-Anweisungen, um die Lizenzierung Anforderungen vertraut zu machen, die Ihre Organisation verfügt, damit Ihre Benutzer Gäste zu Ihrer Organisation einladen können.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-121">If you’re seeing licensing errors, make sure to read the B2B licensing guidance to understand the licensing requirements your organization has so that your users are able to invite guests to your organization.</span></span>

<span data-ttu-id="ccfe7-122">Einige Dinge bedenken:</span><span class="sxs-lookup"><span data-stu-id="ccfe7-122">A few things to remember:</span></span>

- <span data-ttu-id="ccfe7-123">Für jede Azure AD-Lizenz, die Sie einem Benutzer zuweisen kostenpflichtige, können die Benutzer bis zu fünf Gastbenutzer unter der Vergütung für externe Benutzer einladen.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-123">For each paid Azure AD license that you assign to a user, your users can invite up to five guest users under the External User Allowance.</span></span>
- <span data-ttu-id="ccfe7-124">Gäste sind Benutzer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-124">Guests are users outside your organization.</span></span> <span data-ttu-id="ccfe7-125">Ihre Mitarbeiter, Auftragnehmer vor Ort, vor-Ort-Agents und usw. können nicht als Gäste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-125">Your employees, onsite contractors, onsite agents, and so on can't be added as guests.</span></span> <span data-ttu-id="ccfe7-126">Das gleiche gilt für Ihre Erwerbs.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-126">The same applies to your affiliates.</span></span>
- <span data-ttu-id="ccfe7-127">Gast Lizenzen gegen die Organisation einladen, werden gezählt.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-127">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="ccfe7-128">Berücksichtigen Sie dies, wenn Sie die Anzahl der Lizenzen berechnen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-128">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="ccfe7-129">Ob die eingeladene Gäste aus einer anderen Office 365-Mandanten stammen oder ihre persönlichen e-Mail-Adressen verwenden, werden anhand Ihrer Organisation Lizenzen gezählt.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-129">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="--step-1-configure-settings-in-azure-ad-business-to-business"></a><span data-ttu-id="ccfe7-130">□ Schritt 1: Konfigurieren von Einstellungen in Azure AD-B2B</span><span class="sxs-lookup"><span data-stu-id="ccfe7-130">□  Step 1: Configure settings in Azure AD business-to-business</span></span>

1. <span data-ttu-id="ccfe7-131">Melden Sie sich bei https://portal.azure.com.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-131">Sign in to https://portal.azure.com.</span></span>
2. <span data-ttu-id="ccfe7-132">Klicken Sie im linken Bereich auf **Azure Active Directory** .</span><span class="sxs-lookup"><span data-stu-id="ccfe7-132">Click **Azure Active directory** in the left pane.</span></span>
3. <span data-ttu-id="ccfe7-133">Klicken Sie unter **Verwalten**auf **benutzereinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-133">Under **Manage**, click **User settings**.</span></span>
4. <span data-ttu-id="ccfe7-134">Klicken Sie unter **externe Benutzer**klicken Sie auf **Einstellungen für externe verwalten für die Zusammenarbeit**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-134">Under **External users**, click **Manage External collaboration settings**.</span></span>
5. <span data-ttu-id="ccfe7-135">Klicken Sie auf der Seite **Einstellungen für die externe Zusammenarbeit** sicherstellen Sie, dass **Mitglieder können einladen** auf **Ja**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-135">On the **External collaboration settings** page make sure **Members can invite** is set to **Yes**.</span></span>

      ![<span data-ttu-id="ccfe7-136">Screenshot zeigt ein Beispiel für eine Umschaltfläche AAD Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-136">Screenshot shows an example of a AAD Settings toggle.</span></span> ](media/guest-access-checklist-AADSettings1.png)

    <span data-ttu-id="ccfe7-137">Zur Unterstützung der Gäste müssen **Mitglieder können einladen** auf **Ja**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-137">To support guests, **Members can invite** must be set to **Yes**.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="ccfe7-138">Wenn Sie auf **Nein** festlegen **Mitglieder einladen können** und anschließend Gast Access in Office 365-Gruppen und Microsoft-Teams aktivieren, können Administratoren Gast Einladungen an Ihr Verzeichnis steuern.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-138">If you set **Members can invite** to **No** and then enable guest access in Office 365 Groups and Microsoft Teams, admins can control guest invitations to your directory.</span></span> <span data-ttu-id="ccfe7-139">Nachdem Gäste im Verzeichnis vorhanden sind, können sie Teams von Membern von nicht-Administrator hinzugefügt werden, die Eigentümer Team sind.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-139">After guests are in the directory, they can be added to teams by non-admin members who are team owners.</span></span>

<span data-ttu-id="ccfe7-140">Weitere Informationen finden Sie unter [Autorisieren des Gastzugriffs in Microsoft Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="ccfe7-140">For more information, see [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>


## <a name="-step-2-configure-office-365-groups"></a><span data-ttu-id="ccfe7-141">□ Schritt 2: Konfigurieren von Office 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="ccfe7-141">□ Step 2: Configure Office 365 Groups</span></span>

1. <span data-ttu-id="ccfe7-142">Wechseln Sie in der Microsoft-365-Verwaltungskonsole zu **Einstellungen** > **Services &-Add-ins** > **Office 365-Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-142">In the Microsoft 365 admin center, go to **Settings** > **Services & Add-ins** > **Office 365 Groups**.</span></span>
2. <span data-ttu-id="ccfe7-143">Stellen Sie sicher, dass **Let Gruppenmitglieder außerhalb der Organisation Access Gruppe Inhalt** auf **aktiviert**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-143">Make sure **Let group members outside the organization access group content** is set to **On**.</span></span> <span data-ttu-id="ccfe7-144">Wenn diese Einstellung deaktiviert ist, werden nicht Gäste auf eine beliebige Gruppe Inhalte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-144">If this setting is turned off, guests won't be able to access any group content.</span></span>
3. <span data-ttu-id="ccfe7-145">Stellen Sie sicher, dass **Let Gruppenbesitzer Personen außerhalb der Organisation zu Gruppen hinzufügen** auf **aktiviert**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-145">Make sure **Let group owners add people outside the organization to groups** is set to **On**.</span></span> <span data-ttu-id="ccfe7-146">Wenn diese Einstellung deaktiviert ist, werden nicht Besitzer Team neue Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-146">If this setting is turned off, Team owners won't be able to add new guests.</span></span> <span data-ttu-id="ccfe7-147">Diese Einstellung muss mindestens bei Support Gast Access.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-147">At a minimum, this setting must be On to support guest access.</span></span>

     ![Screenshot zeigt die Office 365 Gruppen schaltet](media/guest-access-checklist-office365.png)

<span data-ttu-id="ccfe7-149">Weitere Informationen zum Konfigurieren dieser Einstellungen finden Sie unter [Verwalten Gast Benutzerzugriffs in Office 365-Gruppen](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) und im Abschnitt "Office 365 Groups" im [Autorisieren Gast Access in Microsoft-Teams](Teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="ccfe7-149">For detailed instructions about configuring these settings, see [Manage guest access in Office 365 groups](https://support.office.com/en-us/article/manage-guest-access-in-office-365-groups-9de497a9-2f5c-43d6-ae18-767f2e6fe6e0?appver=MOE150) and the section "Office 365 Groups" in [Authorize guest access in Microsoft Teams](Teams-dependencies.md).</span></span>
 

## <a name="-step-3-enable-guest-access-at-the-tenant-level"></a><span data-ttu-id="ccfe7-150">□ Schritt 3: Aktivieren des Zugriffs auf der Ebene der Mandant Gast</span><span class="sxs-lookup"><span data-stu-id="ccfe7-150">□ Step 3: Enable guest access at the tenant level</span></span>

<span data-ttu-id="ccfe7-151">Zumindest müssen Sie Gast Access für Microsoft-Teams, unter der **Microsoft-Teams, Administrationscenter**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-151">At a minimum, you must turn on Guest access for Microsoft Teams under the **Microsoft Teams admin center**.</span></span> 

1. <span data-ttu-id="ccfe7-152">Wählen Sie in der Verwaltungskonsole Teams **Org geltende Einstellungen** > **Gastzugriff**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-152">In the Teams admin center, select **Org-Wide settings** > **Guest access**.</span></span>
2. <span data-ttu-id="ccfe7-153">Legen Sie die Option **Zulassen Gast Access in Microsoft-Teams** auf **aktiviert**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-153">Set the **Allow guest access in Microsoft Teams** switch to **On**.</span></span>

    ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Teams Einstellungen](media/set-up-guests-image1.png)

3. <span data-ttu-id="ccfe7-155">Klicken Sie auf der gleichen Seite konfigurieren Sie alle anderen Gast-Einstellungen, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-155">On this same page, configure any other guest settings that you require.</span></span>
4. <span data-ttu-id="ccfe7-156">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-156">Click **Save**.</span></span>

<span data-ttu-id="ccfe7-157">Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Gastzugriff auf Microsoft-Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="ccfe7-157">For detailed instructions, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span>


## <a name="--step-4-configure-sharing-in-office-365"></a><span data-ttu-id="ccfe7-158">□ Schritt 4: Konfigurieren der Freigabe von in Office 365</span><span class="sxs-lookup"><span data-stu-id="ccfe7-158">□  Step 4: Configure Sharing in Office 365</span></span> 

<span data-ttu-id="ccfe7-159">Stellen Sie sicher, dass Benutzer Gäste hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-159">Make sure that users can add guests.</span></span> <span data-ttu-id="ccfe7-160">Hier ist wie:</span><span class="sxs-lookup"><span data-stu-id="ccfe7-160">Here's how:</span></span>

1. <span data-ttu-id="ccfe7-161">Wechseln Sie in der Microsoft-365-Verwaltungskonsole zu **Einstellungen** > **Sicherheit & Datenschutz**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-161">In the Microsoft 365 admin center, go to **Settings** > **Security & privacy**.</span></span>

     ![Screenshot zeigt ein Beispiel einer Services-Einstellungen](media/guest-access-checklist-Office365Admin_Services_addins.png)

2. <span data-ttu-id="ccfe7-163">Wählen Sie in der **Freigabe** **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-163">In **Sharing**, select **Edit**.</span></span>

     ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing1.png)
 
3. <span data-ttu-id="ccfe7-165">Legen Sie **dazu, Benutzern das Hinzufügen von neuen Gäste auf diese Organisation** auf **aktiviert**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-165">Set **Let users add new guests to this organization** to **On**, and then click **Save**.</span></span>

     ![Screenshot zeigt ein Beispiel für eine Freigabe Einstellungen umschalten](media/guest-access-checklist-Office365Admin_Services_addins_Sharing2.png)
 
> [!NOTE]
> <span data-ttu-id="ccfe7-167">Diese Einstellung entspricht der Einstellung **Mitglieder einladen können** in **benutzereinstellungen** > **externe Benutzer** in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-167">This setting is equivalent to the **Members can invite** setting in  **User settings** > **External users**  in Azure AD.</span></span>  


## <a name="-step-5-verify-sharing-setting-in-sharepoint"></a><span data-ttu-id="ccfe7-168">□ Schritt 5: Überprüfen Sie die Freigabe Einstellung in SharePoint</span><span class="sxs-lookup"><span data-stu-id="ccfe7-168">□ Step 5: Verify sharing setting in SharePoint</span></span>

1. <span data-ttu-id="ccfe7-169">Melden Sie sich beim Office 365 Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-169">Sign in to the Office 365 admin center.</span></span>
2. <span data-ttu-id="ccfe7-170">Klicken Sie auf **Administrationscenter**, und wählen Sie dann **SharePoint**aus.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-170">Click **Admin center**, and then select **SharePoint**.</span></span>
3. <span data-ttu-id="ccfe7-171">Wählen Sie in der SharePoint-Verwaltungskonsole **Freigabe**.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-171">In the SharePoint admin center, select **Sharing**.</span></span>
4. <span data-ttu-id="ccfe7-172">Stellen Sie sicher, dass die Option für **nicht zulassen Freigabe außerhalb Ihrer Organisation** *nicht* ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-172">Make sure the option for **Don’t allow sharing outside your organization** is *not* selected.</span></span>
 
     ![Screenshot zeigt ein Beispiel für eine Umschaltfläche Sparepoint Online-Einstellungen.](media/guest-access-checklist-SPOSettings1.png)


## <a name="-step-6-enable-specific-settings-for-channels"></a><span data-ttu-id="ccfe7-174">□ Schritt 6: Aktivieren Sie bestimmte Einstellungen für Kanäle</span><span class="sxs-lookup"><span data-stu-id="ccfe7-174">□ Step 6: Enable specific settings for channels</span></span> 

<span data-ttu-id="ccfe7-175">Konfigurieren Sie in der Anwendung Teams auf Ebene der einzelnen Teams Gastberechtigungen, sodass Gäste erstellen, aktualisieren und Löschen von Kanäle können.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-175">In the Teams application, at the individual team level, configure guest permissions so that guests can create, update, and delete channels.</span></span> <span data-ttu-id="ccfe7-176">Zusätzlich zur-Administratoren können Team Besitzer dieser Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ccfe7-176">In addition to admins,  team owners can configure this setting.</span></span>

![Screenshot zeigt ein Beispiel für eine Umschaltfläche Team/Channel-Einstellungen](media/guest-access-checklist-TeamsSettings2.png)

<span data-ttu-id="ccfe7-178">Weitere Informationen, einschließlich videoanleitungen finden Sie unter [Gast Access in Microsoft-Teams](guest-access.md).</span><span class="sxs-lookup"><span data-stu-id="ccfe7-178">For more information, including how-to videos, see [Guest access in Microsoft Teams](guest-access.md).</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="ccfe7-179">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="ccfe7-179">Troubleshooting</span></span>

<span data-ttu-id="ccfe7-180">Wenn Sie Probleme beim Hinzufügen von Gäste in Microsoft-Teams haben, finden Sie im [Handbuch zur Problembehandlung für Gast Zugriff](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span><span class="sxs-lookup"><span data-stu-id="ccfe7-180">If you have problems with adding guests in Microsoft Teams, see the [Guest Access Troubleshooting Guide](https://techcommunity.microsoft.com/t5/Microsoft-Teams/Guest-Access-Troubleshooting-Guide/td-p/119797).</span></span>


