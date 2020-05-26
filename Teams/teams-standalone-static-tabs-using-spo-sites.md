---
title: Erstellen einer Intranet-Portal-App für Teams von einer SharePoint Online-Website oder -Seite aus
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Verwenden Sie eine vorhandene SharePoint Online-Website oder -Seite und erstellen Sie eine eigenständige statische Registerkarte, die als Intranet-Portal für Ihre Organisation verwendet werden kann.
localization_priority: Priority
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326582"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="0d285-103">Erstellen einer Intranet-Portal-App für Teams von einer SharePoint Online-Website oder -Seite aus</span><span class="sxs-lookup"><span data-stu-id="0d285-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="0d285-104">Führen Sie die in diesem Artikel aufgeführten Schritte aus, um eine eigenständige und statische App innerhalb von Teams zu erstellen, die mit der Intranet-Seite Ihrer Organisation verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="0d285-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="0d285-105">Eine *Persönliche Teams-App* Ihrer SharePoint-Intranet-Website wird erstellt und als Registerkarte innerhalb von Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d285-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="0d285-106">Diese Registerkarte enthält Informationen, die für alle Teammitglieder wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="0d285-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="0d285-107">Es ist eine schnelle und bequeme Möglichkeit für die Benutzer von Teams, auf Updates zuzugreifen, die nur einen Tab-Klick entfernt sind.</span><span class="sxs-lookup"><span data-stu-id="0d285-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="0d285-108">Beachten Sie, dass für den gezeigten Vorgang eine *moderne* SharePoint-Website oder -Seite verwendet werden **muss**.</span><span class="sxs-lookup"><span data-stu-id="0d285-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="0d285-109">Diese Vorgehensweise ist für *klassische* Websites oder Seiten nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d285-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d285-110">Stellen Sie sicher, dass Side-Loading von Teams-Apps für Ihren Mandanten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0d285-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="0d285-111">Je nachdem, wo Sie sich im Migrationsprozess des Teams-Administratorportals befinden, müssen Sie dies möglicherweise entweder unter Teams > Administrator oder unter Administrator > Einstellungen > Dienste und Add-Ins > Microsoft Teams > Apps > Externe Apps in der vorherigen Version des Portals aktivieren!</span><span class="sxs-lookup"><span data-stu-id="0d285-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="0d285-112">Verwenden von App Studio zum Erstellen einer eigenständigen SharePoint Online-App</span><span class="sxs-lookup"><span data-stu-id="0d285-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="0d285-113">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="0d285-113">Before you begin:</span></span>

1. <span data-ttu-id="0d285-114">Sie müssen die URL einer modernen SharePoint Online-Kommunikations- oder-Team-Website oder-Seite kennen.</span><span class="sxs-lookup"><span data-stu-id="0d285-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="0d285-115">Diese Websites verfügen immer über */teams/* oder */sites/* in ihren Pfaden.</span><span class="sxs-lookup"><span data-stu-id="0d285-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="0d285-116">Sie müssen die Unterdomäne Ihres Mandanten kennen, die im Platzhalter **{{subdomain}}** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d285-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="0d285-117">In diesem Artikel wird **{{siteUrl}}** als Platzhalter für die *URL* der ausgewählten Website oder Seite verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d285-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="0d285-118">Beispiel-*URLs*:   https://contoso.sharepoint.com/teams/Contoso   *oder* https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="0d285-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="0d285-119">Außerdem wird **{{sitePath}}** dazu verwendet, den *Pfad* der URL (beispielsweise: /teams/contoso) zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="0d285-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="0d285-120">*Beispielpfade*:   /teams/Contoso   *oder* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="0d285-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="0d285-121">Beginnen Sie mit den folgenden Schritten:</span><span class="sxs-lookup"><span data-stu-id="0d285-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="0d285-122">Wechseln Sie zum Teams-Store.</span><span class="sxs-lookup"><span data-stu-id="0d285-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="0d285-123">Installieren oder öffnen Sie App Studio.</span><span class="sxs-lookup"><span data-stu-id="0d285-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="0d285-124">Klicken Sie neben der App-Option auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="0d285-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="0d285-125">Klicken Sie bei geöffnetem App Studio auf **Manifest-Editor**.</span><span class="sxs-lookup"><span data-stu-id="0d285-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="0d285-126">**Erstellen Sie eine neue App**.</span><span class="sxs-lookup"><span data-stu-id="0d285-126">**Create a new app**.</span></span>

6. <span data-ttu-id="0d285-127">Füllen Sie alle **App-Details** aus.</span><span class="sxs-lookup"><span data-stu-id="0d285-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="0d285-128">Klicken Sie auf **Registerkarten** unter Funktionen.</span><span class="sxs-lookup"><span data-stu-id="0d285-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="0d285-129">Klicken Sie unter persönliche Registerkarte auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0d285-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="0d285-130">Füllen Sie den **Namen** aus, und wählen Sie **eine neue eindeutige Entitäts-ID** aus.</span><span class="sxs-lookup"><span data-stu-id="0d285-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="0d285-131">Füllen Sie die **contentURL und Website-URL** aus.</span><span class="sxs-lookup"><span data-stu-id="0d285-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="0d285-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="0d285-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="0d285-133">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="0d285-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="0d285-134">Beispiel-**contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="0d285-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="0d285-135">Navigieren Sie zu **Domänen und Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="0d285-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="0d285-136">Stellen Sie sicher, dass der Abschnitt gültige Domänen Ihren SharePoint Online-Domänennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="0d285-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="0d285-137">Beispiel: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="0d285-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="0d285-138">Fügen Sie die folgenden Web App-Eigenschaften für **Einmaliges Anmelden (Single Sign-on, SSO)** hinzu:</span><span class="sxs-lookup"><span data-stu-id="0d285-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="0d285-139">Beispiel:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="0d285-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![Web App-Single Sign-On, mit ID und URL.](media/personal-app.png)

13. <span data-ttu-id="0d285-141">**Speichern Sie** diese Eigenschaften und navigieren Sie dann zu **Testen und Verteilen**.</span><span class="sxs-lookup"><span data-stu-id="0d285-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="0d285-142">Installieren Sie die App, um die Anwendung persönlich zu testen.</span><span class="sxs-lookup"><span data-stu-id="0d285-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d285-143">Wenn Sie nicht mit Teams App Studio arbeiten, müssen Sie die soeben erstellte manifest.JSON-Datei als .zip komprimieren, zum App Store in Teams navigieren und auf den Link **benutzerdefinierte App hochladen** (unten rechts im App Store) klicken.</span><span class="sxs-lookup"><span data-stu-id="0d285-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="0d285-144">Dadurch wird die App für Sie verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0d285-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="0d285-145">Die App ist nun als statische Registerkarte verfügbar, die Sie laden und in Teams anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="0d285-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="0d285-146">Testen und Betrachten Sie Ihre statische Registerkarte</span><span class="sxs-lookup"><span data-stu-id="0d285-146">Test and view your new static tab</span></span>

<span data-ttu-id="0d285-147">Um die neue Registerkarte im Team-Desktop anzuzeigen, navigieren Sie auf der linken Seite der App-Leiste zu den Auslassungszeichen (**...**).</span><span class="sxs-lookup"><span data-stu-id="0d285-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="0d285-148">Suchen Sie Ihre neue App, laden Sie sie herunter und testen Sie Ihre eigenständige Anwendung in Teams.</span><span class="sxs-lookup"><span data-stu-id="0d285-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="0d285-149">Wenn Sie die neue App im linken Menü an einer höheren Position verfügbar machen möchten, müssen Sie dafür eine App-Richtlinieneinstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d285-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="0d285-150">Diese Einstellung finden Sie im Abschnitt Team Administrator > App-Richtlinie > Hinzufügen einer angehefteten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="0d285-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="0d285-151">Wenn Sie einem Benutzer die Richtlinie zum Test zuweisen, wird die Änderung wenige Stunden später angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0d285-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="0d285-152">In diesem Sinne sollten Sie frühzeitig entscheiden, wo die App angezeigt werden soll, um Verzögerungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0d285-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="0d285-153">Wenn Sie die neue App auf einem mobilen Gerät anzeigen und testen möchten, öffnen Sie die App-Schublade, indem Sie auf das Chevron (**^**) oberhalb der Registerkartenleiste am unteren Rand des Bildschirms tippen.</span><span class="sxs-lookup"><span data-stu-id="0d285-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="0d285-154">Suchen Sie Ihre App, und navigieren Sie auf Ihrem mobilen Gerät zu ihr.</span><span class="sxs-lookup"><span data-stu-id="0d285-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="0d285-155">Die Unterstützung für Mobilgeräte befindet sich derzeit im Developer Preview.</span><span class="sxs-lookup"><span data-stu-id="0d285-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="0d285-156">Um Developer Preview zu aktivieren, navigieren Sie zu Einstellungen > Info, und aktivieren Sie dann den Developer Preview-Modus.</span><span class="sxs-lookup"><span data-stu-id="0d285-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="0d285-157">Eine Manifest.JSON-Beispieldatei</span><span class="sxs-lookup"><span data-stu-id="0d285-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="0d285-158">Die von Ihnen generierte JSON-Datei sieht in etwa so wie die nachfolgende aus.</span><span class="sxs-lookup"><span data-stu-id="0d285-158">The JSO        file you generate will look something like the one below.</span></span>

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

            "name": "Contoso Net",

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/",

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet",

            "scopes": [

                "personal"

            ]

        },

        {

            "entityId": "teamSiteTab",

            "name": "Team Contoso",

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/",

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso",

            "scopes": [

                "personal"

            ]

        }

    ],

    "permissions": [

        "identity",

        "messageTeamMembers"

    ],

    "validDomains": [

        "contoso.sharepoint.com"

    ],

    "webApplicationInfo": {

        "id": "00000003-0000-0ff1-ce00-000000000000",

        "resource": "https://contoso.sharepoint.com"

    }

}
```
