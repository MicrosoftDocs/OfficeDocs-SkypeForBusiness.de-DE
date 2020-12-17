---
title: Installieren, verwalten und Zuweisen von Berechtigungen für die Lern-App für Teams (private Preview)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Verwenden Sie die Microsoft Teams Learning-APP, um einen zentralen Hub für das Lernen zu erstellen, in dem Mitarbeiter Inhaltsbibliotheken in einer Organisation freigeben, zuweisen und daraus lernen können.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703426"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="44281-103">Installieren, verwalten und Zuweisen von Berechtigungen für die Lern-App für Teams (private Preview)</span><span class="sxs-lookup"><span data-stu-id="44281-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="44281-104">*Dieser Artikel enthält vorläufige Inhalte für die Learning-App für Teams, die sich in der privaten Vorschau befindet.*</span><span class="sxs-lookup"><span data-stu-id="44281-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="44281-105">Die Microsoft Teams Learning-app (private Preview) befähigt Teams und Einzelpersonen in Ihrer Organisation, das Lernen zu einem natürlichen Teil Ihres Tages zu machen.</span><span class="sxs-lookup"><span data-stu-id="44281-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="44281-106">Die App erstellt einen zentralen Hub in Teams, in dem Mitarbeiter Inhaltsbibliotheken in Ihrer Organisation freigeben, zuweisen und daraus lernen können.</span><span class="sxs-lookup"><span data-stu-id="44281-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="44281-107">Administratoren setzen Berechtigungen und ermöglichen das Erlernen von Inhaltsquellen für die app.</span><span class="sxs-lookup"><span data-stu-id="44281-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="44281-108">Zu den Lerninhalten können LinkedIn Learning, Microsoft Learn, Microsoft 365-Schulungen, die in SharePoint Online gespeicherten Inhalte Ihrer Organisation sowie Drittanbieter gehören, die von der App unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="44281-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="44281-109">Um die Lern-App für Teams einzurichten (private Preview), müssen Sie Folgendes einbeziehen:</span><span class="sxs-lookup"><span data-stu-id="44281-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="44281-110">Team Admin Center-Administrator</span><span class="sxs-lookup"><span data-stu-id="44281-110">Teams admin center admin</span></span>
-   <span data-ttu-id="44281-111">Microsoft 365 Admin Center-Administrator (also ein globaler Administrator)</span><span class="sxs-lookup"><span data-stu-id="44281-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="44281-112">Wissens Administrator (eine neue Rolle im Microsoft 365 Admin Center, die ein globaler Administrator (auch bekannt als IT-Administrator oder Microsoft 365-Administrator) beliebigen Personen in der Organisation zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="44281-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="44281-113">Diese Rolle verwaltet die Lerninhalts Quellen der Organisation über das Microsoft 365 Admin Center.)</span><span class="sxs-lookup"><span data-stu-id="44281-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="44281-114">Verwalten der Lern-App für Teams (private Preview) im Team Admin Center</span><span class="sxs-lookup"><span data-stu-id="44281-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="44281-115">Der Teamadministrator installiert die Lern-App für Teams (private Preview) aus dem App Store und wendet die Richtlinien für die APP-Einrichtung,-Verwaltung und-Berechtigungen über das Team Admin Center an.</span><span class="sxs-lookup"><span data-stu-id="44281-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="44281-116">Verwalten der Lern-App für Teams (private Preview)</span><span class="sxs-lookup"><span data-stu-id="44281-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="44281-117">Führen Sie die folgenden Schritte aus, um die Einstellungen für die APP zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="44281-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="44281-118">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps**  >  **Verwalten von apps**.</span><span class="sxs-lookup"><span data-stu-id="44281-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Linke Navigationsleiste im Team Admin Center mit Teams-apps und Abschnitt "Apps verwalten"](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="44281-120">Geben Sie auf der Seite **apps verwalten** im Suchfeld den Text *Learning* ein, um nach der Lern-App für Teams zu suchen (private Preview).</span><span class="sxs-lookup"><span data-stu-id="44281-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Seite "Apps verwalten" im Team Admin Center mit dem Suchfeld](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="44281-122">Auf der  Lernseite:</span><span class="sxs-lookup"><span data-stu-id="44281-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="44281-123">Wählen Sie unter **Status** die Option **erlaubt** aus, um die APP zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44281-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="44281-124">Wechseln Sie auf der Registerkarte **Einstellungen** im Abschnitt **App-Einstellungen** zum Microsoft 365 Admin Center, um Lerninhalts Quellen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44281-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Seite "Lernen" im Team Admin Center mit Status-und App-Einstellungen](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="44281-126">Nachdem Sie die App-Einstellungen **verwaltet** haben, wechseln Sie zu **Berechtigungen und Einrichten von Richtlinien** , um Mitarbeitern, die Zugriff auf die APP haben sollen, als Teil der Teilnahme Ihrer Organisation an der privaten Vorschau die Berechtigung zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="44281-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="44281-127">Wenn sich Ihre Organisation im Rahmen des Teams TAP100-Programms in Ring 4,0 befindet, müssen Sie möglicherweise die folgenden Schritte ausführen, um zugelassene Benutzer in Ring 3,0 für den Zugriff auf die Lern-App für Teams (private Preview) zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="44281-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="44281-128">Im Rahmen der privaten Vorschau wird die Lern-App für Teams (private Preview) in Ring 3,0 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="44281-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="44281-129">Wenn sich Ihre Organisation in Ring 4,0 befindet, wird die APP nicht im App Store angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44281-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="44281-130">Um die APP zu testen, müssen Sie eine benutzerdefinierte Berechtigungsrichtlinie für Apps erstellen, diese so festlegen, **dass alle apps** zugelassen werden, und Sie den von 3,0 genehmigten Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="44281-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Tippen-AppsPermission-Plcy-Seite mit der Option "alle apps zulassen"](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="44281-132">Konfigurieren von Lerninhalts Quellen im Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="44281-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="44281-133">Die Administratoren für das Microsoft 365 Admin Center – entweder alleine oder durch Zuweisen der Rolle des Wissens Administrators zu ausgewählten Personen in Ihrer Organisation – können Einstellungen verwalten, die sich auf die Lern-App für Teams (private Preview) beziehen, und können die Lerninhalts Quellen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44281-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="44281-134">Der Knowledge-Administrator sollte mittelmäßig technisch sein und über vorhandene SharePoint-Administratoranmeldeinformationen verfügen, vorzugsweise eine Person, die in der Bildungs-, Lern-, Schulungs-oder Mitarbeiter Erfahrung des Unternehmens gut vertraut ist.</span><span class="sxs-lookup"><span data-stu-id="44281-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="44281-135">Der Administrator wählt aus, welche Lerninhalts Quellen (wie LinkedIn Learning oder SharePoint) in der app verfügbar sein sollen.</span><span class="sxs-lookup"><span data-stu-id="44281-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="44281-136">Der Administrator konfiguriert dann diese Quellen, um sicherzustellen, dass der Inhalt für die Suche und Ermittlung zur Verfügung steht, und kann von den Mitarbeitern durchsucht werden, die die APP verwenden.</span><span class="sxs-lookup"><span data-stu-id="44281-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="44281-137">Zuweisen der Rolle des Wissens Administrators [optional]</span><span class="sxs-lookup"><span data-stu-id="44281-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="44281-138">Diese Schritte müssen vom Administrator für das Microsoft 365 Admin Center ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="44281-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="44281-139">Wechseln Sie in der linken Navigationsleiste des Microsoft 365 Admin Center zu **Rollen**.</span><span class="sxs-lookup"><span data-stu-id="44281-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="44281-140">Wählen Sie auf der Seite **Rollen** auf der Registerkarte **Azure AD** den Eintrag **Wissens Administrator** aus.</span><span class="sxs-lookup"><span data-stu-id="44281-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="44281-141">Wählen Sie auf der Seite **Wissens Administrator** im Abschnitt **zugewiesene Administratoren** die Option **Hinzufügen** aus, und fügen Sie dann die für die Rolle ausgewählte Person hinzu.</span><span class="sxs-lookup"><span data-stu-id="44281-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="44281-142">Konfigurieren von Einstellungen für die Lerninhalts Quellen für die APP</span><span class="sxs-lookup"><span data-stu-id="44281-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="44281-143">Diese Schritte müssen vom Microsoft 365-Administrator oder vom Knowledge-Administrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="44281-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="44281-144">Navigieren Sie in der linken Navigationsleiste des Microsoft 365 Admin Center zu **Einstellungen**  >  **org-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="44281-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="44281-145">Wählen Sie auf der Seite " **Einstellungen** " auf der Registerkarte **Dienste & Add-ins** die Option **Lern-App** aus.</span><span class="sxs-lookup"><span data-stu-id="44281-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Seite ' Einstellungen ' im Microsoft 365 Admin Center mit der aufgelisteten Lern-App](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="44281-147">Wählen Sie im Lernprogramm- **App** -Panel die Lerninhalts Quellen aus, die Sie für die Organisation konfigurieren möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="44281-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Bereich "Learning app" im Microsoft 365 Admin Center mit Optionen für Inhaltsquellen](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="44281-149">Unter allen vorhandenen Lernquellen sind einige standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="44281-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="44281-150">Hierzu zählen folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="44281-150">These include:</span></span>

- <span data-ttu-id="44281-151">LinkedIn Learning (﻿Kostenlose Inhalte)</span><span class="sxs-lookup"><span data-stu-id="44281-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="44281-152">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="44281-152">Microsoft Learn</span></span>
- <span data-ttu-id="44281-153">Microsoft 365-Schulung</span><span class="sxs-lookup"><span data-stu-id="44281-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="44281-154">Wenn Ihre Organisation über ein LinkedIn Learning Standard-oder pro-Abonnement verfügt, wird das Inhalts-Repository für die Mitarbeiter in Ihrer Organisation freigegeben.</span><span class="sxs-lookup"><span data-stu-id="44281-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="44281-155">Nur Mitarbeiter, die über die Berechtigung verfügen, können das gesamte Inhalts-Repository verwenden.</span><span class="sxs-lookup"><span data-stu-id="44281-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="44281-156">Andere Quellen müssen möglicherweise manuell aktiviert oder konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="44281-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="44281-157">Lernquellen, die nicht von Microsoft stammen, sind separat zwischen Ihrer Organisation und dem Drittanbieter lizenziert.</span><span class="sxs-lookup"><span data-stu-id="44281-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="44281-158">Sie müssen sicherstellen, dass Sie sich für das Lernen für Sie und Ihre Benutzer angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="44281-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="44281-159">Wenn Sie eine Lerninhalts Quelle aktivieren oder deaktivieren möchten, aktivieren Sie das Kontrollkästchen neben der Quelle.</span><span class="sxs-lookup"><span data-stu-id="44281-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="44281-160">Wenn eine Quelle aktiviert ist, wird ein Häkchen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="44281-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="44281-161">Konfigurieren von SharePoint als Lerninhalts Quelle</span><span class="sxs-lookup"><span data-stu-id="44281-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="44281-162">Sie konfigurieren SharePoint als Lerninhalts Quelle für die Lern-app "Teams" (private Preview) im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="44281-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="44281-163">Übersicht</span><span class="sxs-lookup"><span data-stu-id="44281-163">Overview</span></span>

<span data-ttu-id="44281-164">Der Knowledge-Administrator stellt eine Website-URL bereit, in der der Lerndienst ein leeres zentrales Learning Content-Repository in Form einer strukturierten SharePoint-Liste erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="44281-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="44281-165">Diese Liste kann von der Organisation verwendet werden, um Links zu unternehmensübergreifenden SharePoint-Ordnern mit Lerninhalten zu unterhalten.</span><span class="sxs-lookup"><span data-stu-id="44281-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="44281-166">Administratoren sind für das Sammeln und kuratiert einer Liste von URLs für Ordner verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="44281-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="44281-167">Diese Ordner sollten nur Inhalte enthalten, die in der Lern-App für Teams zur Verfügung gestellt werden können (private Preview).</span><span class="sxs-lookup"><span data-stu-id="44281-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="44281-168">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="44281-168">Permissions</span></span>

<span data-ttu-id="44281-169">Ordner-URLs können von jeder SharePoint-Website in der Organisation erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="44281-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="44281-170">Alle Inhalte in diesen Ordnern sind durchsuchbar, jedoch können nur Inhalte verwendet werden, für die der einzelne Mitarbeiter über Berechtigungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="44281-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="44281-171">Learning Service</span><span class="sxs-lookup"><span data-stu-id="44281-171">Learning Service</span></span>

<span data-ttu-id="44281-172">Der Schulungs Dienst verwendet die bereitgestellten Ordner-URLs, um Metadaten aus allen Inhalten abzurufen, die in diesen Ordnern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="44281-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="44281-173">Innerhalb von 24 Stunden nach der Bereitstellung der Ordner-URL im zentralen Repository können die Mitarbeiter den Unternehmensinhalt in der APP suchen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="44281-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="44281-174">Das Löschen von Inhalten aus dem Repository wird an dieser Stelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="44281-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="44281-175">Unbeabsichtigt aufgetauchte Inhalte können nur entfernt werden, indem eine neue SharePoint-Website-URL im Microsoft 365 Admin Center bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="44281-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="44281-176">Konfigurieren von SharePoint als Quelle</span><span class="sxs-lookup"><span data-stu-id="44281-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="44281-177">Diese Schritte müssen vom Microsoft 365-Administrator oder dem Knowledge-Administrator ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="44281-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="44281-178">Wechseln Sie in der linken Navigationsleiste des Microsoft 365 Admin Center zu **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="44281-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="44281-179">Wählen Sie auf der Seite " **Einstellungen** " auf der Registerkarte **Dienste & Add-ins** die Option **Lern-App** aus.</span><span class="sxs-lookup"><span data-stu-id="44281-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Seite ' Einstellungen ' im Microsoft 365 Admin Center mit der aufgelisteten Lern-App](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="44281-181">Stellen Sie im App-Bereich für **Lernende** die Website-URL für die SharePoint-Website bereit, auf der die APP ein zentrales Repository erstellen soll.</span><span class="sxs-lookup"><span data-stu-id="44281-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Bereich "Learning app" im Microsoft 365 Admin Center mit ausgewähltem SharePoint](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="44281-183">Eine SharePoint-Liste wird automatisch auf der SharePoint-Website der bereitgestellten Organisation erstellt.</span><span class="sxs-lookup"><span data-stu-id="44281-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="44281-184">Wählen Sie in der linken Navigationsleiste der SharePoint-Website die Option **Learning App Content Repository** aus.</span><span class="sxs-lookup"><span data-stu-id="44281-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Links Navigation in SharePoint mit dem Abschnitt "Learning App Content Repository"](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="44281-186">Füllen Sie auf der Seite **Learning App Content Repository** die SharePoint-Liste mit URLs für die Lerninhalts Ordner.</span><span class="sxs-lookup"><span data-stu-id="44281-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="44281-187">Wählen Sie **neu** aus, um den Abschnitt **Neues Element** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="44281-187">Select **New** to view the **New item** panel.</span></span> 

   ![Seite "Learning App Content Repository" in SharePoint mit der neuen Option](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="44281-189">Fügen Sie im Bereich **Neues Element** im Feld **Titel** einen Verzeichnisnamen Ihrer Wahl hinzu.</span><span class="sxs-lookup"><span data-stu-id="44281-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="44281-190">Fügen Sie im Feld **Ordner-URL** die URL zum Ordner Learning Content hinzu.</span><span class="sxs-lookup"><span data-stu-id="44281-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="44281-191">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="44281-191">Select **Save**.</span></span>

   ![Bereich "Neues Element" in SharePoint mit den Feldern "Titel" und "Ordner-URL"](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="44281-193">Die Seite "Learning App Content Repository" wird mit dem neuen Lerninhalt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="44281-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Seite "Learning App Content Repository" in SharePoint mit aktualisierten Informationen](media/learning-app-content-repository-populated.png)


 


