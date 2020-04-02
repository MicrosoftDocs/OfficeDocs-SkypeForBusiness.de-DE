---
title: Erstellen einer Intranet-Portal-App für Teams über eine SharePoint Online-Website oder-Seite
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Führen Sie eine vorhandene SharePoint Online-Website oder-Seite aus, und erstellen Sie eine eigenständige statische Registerkarte, die als Intranet-Portal für Ihre Organisation verwendet werden kann.
localization_priority: Normal
ms.openlocfilehash: 0215a2e1f79627f55bc14c00a099b25d2859b6f9
ms.sourcegitcommit: f0f2fa999c1ca4a1118377c7938a247f79217609
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106632"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="2fe49-103">Erstellen einer Intranet-Portal-App für Teams über eine SharePoint Online-Website oder-Seite</span><span class="sxs-lookup"><span data-stu-id="2fe49-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="2fe49-104">Führen Sie die in diesem Artikel beschriebenen Schritte aus, um eine eigenständige und statische APP innerhalb von Teams zu erstellen, die mit der Intranetsite für Ihre Organisation verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="2fe49-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="2fe49-105">Eine *persönliche Team-App* Ihrer SharePoint-Intranet-Website wird erstellt und als Registerkarte innerhalb von Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fe49-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="2fe49-106">Diese Registerkarte kann Informationen enthalten, die für alle Benutzer von Teams wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="2fe49-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="2fe49-107">Es ist eine schnelle und bequeme Möglichkeit für die Benutzer von Teams, auf Updates zuzugreifen, nur einen Klick entfernt.</span><span class="sxs-lookup"><span data-stu-id="2fe49-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="2fe49-108">Beachten Sie, dass der angezeigte Prozess eine *moderne* SharePoint-Website oder-Seite **verwenden muss** , um zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2fe49-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="2fe49-109">Dieser Prozess steht für *klassische* Websites oder Seiten nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2fe49-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fe49-110">Stellen Sie sicher, dass das Seiten Laden von Teams-Apps für Ihren Mandanten aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2fe49-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="2fe49-111">Je nachdem, wo Sie sich im Migrationsprozess des Teams-Administrator Portals befinden, müssen Sie möglicherweise entweder unter Teams > Administrator oder unter Administrator > Einstellungen > Dienste und Add-ins > Microsoft Teams > apps > externen apps in der vorherigen Version des Portals aktivieren!</span><span class="sxs-lookup"><span data-stu-id="2fe49-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="2fe49-112">Verwenden von App Studio zum Erstellen ihrer eigenständigen SharePoint Online-App</span><span class="sxs-lookup"><span data-stu-id="2fe49-112">Use App Studio to create your standalone SharePoint Online app</span></span>
<span data-ttu-id="2fe49-113">' ' ' Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="2fe49-113">''' Before you begin:</span></span>
1. <span data-ttu-id="2fe49-114">Sie müssen die URL einer modernen SharePoint Online-Kommunikation oder einer Team Website oder einer Seite kennen.</span><span class="sxs-lookup"><span data-stu-id="2fe49-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="2fe49-115">Auf diesen Websites gibt es immer entweder */Teams/* oder */Sites/* in ihren Pfaden.</span><span class="sxs-lookup"><span data-stu-id="2fe49-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="2fe49-116">Sie müssen die Unterdomäne Ihres Mandanten kennen, die im Platzhalter **{{Subdomain}}** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2fe49-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="2fe49-117">In diesem Artikel wird **{{SiteUrl}}** -Platzhalter für die *URL* der Website oder Seite verwendet, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="2fe49-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="2fe49-118">Beispiel- *URLs*: https://contoso.sharepoint.com/teams/Contoso *oder*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="2fe49-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="2fe49-119">Darüber hinaus wird **{{sitePath}}** verwendet, um den *Pfad* der URL zu kennzeichnen (z. b.:/Teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="2fe49-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="2fe49-120">Beispiel *Pfade*:/Teams/Contoso *oder* /Sites/contoso</span><span class="sxs-lookup"><span data-stu-id="2fe49-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="2fe49-121">Führen Sie zunächst die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2fe49-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="2fe49-122">Wechseln Sie zum Store für Teams.</span><span class="sxs-lookup"><span data-stu-id="2fe49-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="2fe49-123">Installieren oder öffnen Sie App Studio.</span><span class="sxs-lookup"><span data-stu-id="2fe49-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="2fe49-124">Klicken Sie neben der app-Option auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="2fe49-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="2fe49-125">Klicken Sie bei geöffnetem App Studio auf **Manifest-Editor**.</span><span class="sxs-lookup"><span data-stu-id="2fe49-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="2fe49-126">**Erstellen Sie eine neue APP**.</span><span class="sxs-lookup"><span data-stu-id="2fe49-126">**Create a new app**.</span></span>

6. <span data-ttu-id="2fe49-127">Füllen Sie alle **App-Details**aus.</span><span class="sxs-lookup"><span data-stu-id="2fe49-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="2fe49-128">Klicken Sie auf **Registerkarten** unter Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2fe49-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="2fe49-129">Klicken Sie unter persönliche Registerkarte auf **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="2fe49-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="2fe49-130">Geben Sie den **Namen** ein, und wählen Sie **eine neue eindeutige Entitäts-ID**aus.</span><span class="sxs-lookup"><span data-stu-id="2fe49-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="2fe49-131">Füllen Sie die **URL für contentURL und Website**aus.</span><span class="sxs-lookup"><span data-stu-id="2fe49-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="2fe49-132">**contentUrl**: {{siteurl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="2fe49-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="2fe49-133">**web'iteUrl**: {{siteurl}} ' ' Beispiel **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="2fe49-133">**web'iteUrl**: {{siteUrl}} ''   Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="2fe49-134">Navigieren Sie zu **Domänen und Permissi'ns**.</span><span class="sxs-lookup"><span data-stu-id="2fe49-134">Navigate to **Domains and Permissi'ns**.</span></span> <span data-ttu-id="2fe49-135">Stellen Sie sicher, dass der Abschnitt gültige Domänen Ihren SharePoint Online-Domänennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="2fe49-135">Make sure the valid domains section contains your SharePoint online domain name.</span></span>
<span data-ttu-id="2fe49-136">' ' Beispiel: contoso.SharePoint.com</span><span class="sxs-lookup"><span data-stu-id="2fe49-136">'' Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="2fe49-137">Fügen Sie die folgenden Web App-Eigenschaften **für einmaliges Anmelden** hinzu: ' ' Beispiel: ' ' ' ' **Aad-Anwendungs-ID**: 00000003-0000-0ff1-ce00-000000000000- **Ressourcen-URL**: {{Subdomain}} ![. SharePoint. com ' ' ' Web-App-einmaliges Anmelden mit ID und URL.](media/personal-app.png)</span><span class="sxs-lookup"><span data-stu-id="2fe49-137">Add the following web app **single sign-on** properties:  ''  Example:''''  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com' '' ![Web app single sign-on, with ID and URL.](media/personal-app.png)</span></span>

13. <span data-ttu-id="2fe49-138">**Speichern** Sie diese Eigenschaften, und navigieren Sie dann zu **Testen und verteilen**.</span><span class="sxs-lookup"><span data-stu-id="2fe49-138">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="2fe49-139">Installieren Sie die APP, um die Anwendung persönlich zu testen.</span><span class="sxs-lookup"><span data-stu-id="2fe49-139">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2fe49-140">Wenn Sie Teams App Studio nicht verwenden, müssen Sie das Manifest komprimieren. JSON-Datei, die Sie soeben erstellt haben, navigieren Sie in Microsoft Teams zum App Store, und klicken Sie auf **benutzerdefinierten App** -Link Hochladen (unten rechts im App Store).</span><span class="sxs-lookup"><span data-stu-id="2fe49-140">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="2fe49-141">Damit steht Ihnen die APP zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2fe49-141">This will make the app available to you.</span></span>

15. <span data-ttu-id="2fe49-142">Nun steht die APP als statische Registerkarte zum Laden und anzeigen in Teams zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2fe49-142">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="2fe49-143">Testen und Anzeigen der neuen statischen Registerkarte</span><span class="sxs-lookup"><span data-stu-id="2fe49-143">Test and view your new static tab</span></span>

<span data-ttu-id="2fe49-144">Navigieren Sie auf der linken Seite der APP-Leiste zu den Auslassungszeichen (**...**), um die neue Registerkarte auf dem Desktop der Teams anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2fe49-144">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="2fe49-145">Suchen Sie Ihre neue APP, laden Sie Sie, und testen Sie Ihre eigenständige Anwendung in Teams.</span><span class="sxs-lookup"><span data-stu-id="2fe49-145">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="2fe49-146">Wenn Sie die neue APP im linken Menü an einer höheren Position verfügbar machen möchten, müssen Sie hierfür eine APP-Richtlinieneinstellung verwenden.</span><span class="sxs-lookup"><span data-stu-id="2fe49-146">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="2fe49-147">Diese Einstellung finden Sie im Abschnitt Team Administrator > App-Richtlinie > hinzufügen einer angehefteten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2fe49-147">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="2fe49-148">Wenn Sie die Richtlinie einem Benutzer zum Testen zuweisen, wird die Änderung 24 Stunden später angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2fe49-148">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="2fe49-149">In diesem Sinn sollten Sie entscheiden, wo die APP möglichst früh angezeigt werden soll, um Verzögerungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2fe49-149">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="2fe49-150">Wenn Sie die neue APP auf einem mobilen Gerät anzeigen und testen möchten, öffnen Sie die APP-Schublade, indem Sie auf**^** den Chevron () oberhalb der Tab-Leiste am unteren Rand des Bildschirms tippen.</span><span class="sxs-lookup"><span data-stu-id="2fe49-150">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="2fe49-151">Suchen Sie Ihre APP, und navigieren Sie auf Ihrem mobilen Gerät zu ihr.</span><span class="sxs-lookup"><span data-stu-id="2fe49-151">Find your app and navigate to it on your mobile device.</span></span>
        
> [!CAUTION]
> <span data-ttu-id="2fe49-152">Der Mobile Support befindet sich derzeit in der Entwicklervorschau.</span><span class="sxs-lookup"><span data-stu-id="2fe49-152">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="2fe49-153">Navigieren Sie zum Aktivieren der Entwicklervorschau zu Einstellungen > Info, und aktivieren Sie dann den Entwicklervorschau Modus.</span><span class="sxs-lookup"><span data-stu-id="2fe49-153">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="2fe49-154">Eine Beispieldatei für Manifest. JSON</span><span class="sxs-lookup"><span data-stu-id="2fe49-154">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="2fe49-155">Die JSO-Datei, die Sie generieren, sieht ungefähr wie die folgende aus.</span><span class="sxs-lookup"><span data-stu-id="2fe49-155">The JSO        file you generate will look something like the one below.</span></span>

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
''
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