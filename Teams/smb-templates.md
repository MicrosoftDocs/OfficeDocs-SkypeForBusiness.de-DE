---
title: Erste Schritte mit Microsoft Teams-Vorlagen für kleine und mittelständische Unternehmen
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Erste Schritte mit Microsoft Teams-Vorlagen für kleine und mittelständische Unternehmen
ms.openlocfilehash: 3ca5e78f3a61f1e272960dc1d7338bd06f81d4c6
ms.sourcegitcommit: 1de5e4d829405b75c0a87918cc7c8fa7227e0ad6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40952768"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a><span data-ttu-id="ff388-103">Erste Schritte mit Microsoft Teams-Vorlagen für kleine und mittelständische Unternehmen</span><span class="sxs-lookup"><span data-stu-id="ff388-103">Get started with Teams templates for Small and Medium Businesses</span></span>

<span data-ttu-id="ff388-104">Mit Microsoft Teams-Vorlagen können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ff388-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ff388-105">Für kleine und mittelständische Unternehmen können Vorlagen besonders leistungsstark sein, da Sie Administratoren dabei helfen, Teams in ihrer gesamten Organisation schnell bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="ff388-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="ff388-106">Mithilfe von Vorlagen können Sie Benutzer auch orientieren und mit der effektiven Verwendung von Teams beginnen.</span><span class="sxs-lookup"><span data-stu-id="ff388-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="ff388-107">Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="ff388-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="ff388-108">Wir bieten derzeit drei SMB-Vorlagen von First Party an, die Sie für unterschiedliche Situationen nutzen können.</span><span class="sxs-lookup"><span data-stu-id="ff388-108">We currently offer three first party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="ff388-109">Alle Vorlagen werden *private* Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff388-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="ff388-110">Nachdem Sie die Teams erstellt haben und bereit für das Rollout in Ihre Organisation sind, können Sie den Datenschutz je nach Bedarf auf *org-Wide* oder *Public*festlegen.</span><span class="sxs-lookup"><span data-stu-id="ff388-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="ff388-111">Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="ff388-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="ff388-112">Unternehmensweite Vorlage</span><span class="sxs-lookup"><span data-stu-id="ff388-112">Company-Wide template</span></span>
<span data-ttu-id="ff388-113">Die unternehmensweite Vorlage ist für Kommunikation und Zusammenarbeit vorgesehen, die für das gesamte Unternehmen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="ff388-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="ff388-114">Sie können den allgemeinen Kanal für unternehmensweite Ankündigungen, Branchen-News oder Executive-Beiträge verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff388-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="ff388-115">Der Personal Kanal ist ein großartiger Ort, um alle HR-bezogenen Aktivitäten wie Stellenangebote, neue Mitarbeiter Onboarding, Schulung und Entwicklung zu konsolidieren.</span><span class="sxs-lookup"><span data-stu-id="ff388-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="ff388-116">Der Fun-Stuff-Kanal bietet eine soziale Plattform für alle zufällige und lustige Beiträge.</span><span class="sxs-lookup"><span data-stu-id="ff388-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="ff388-117">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="ff388-117">Base template type</span></span>  | <span data-ttu-id="ff388-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ff388-118">baseTemplateId</span></span> | <span data-ttu-id="ff388-119">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="ff388-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="ff388-120">SMB</span><span class="sxs-lookup"><span data-stu-id="ff388-120">SMB -</span></span> <br><span data-ttu-id="ff388-121">Unternehmensweit</span><span class="sxs-lookup"><span data-stu-id="ff388-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="ff388-122">Kanäle</span><span class="sxs-lookup"><span data-stu-id="ff388-122">Channels</span></span> <ul><li><span data-ttu-id="ff388-123">Allgemein\*</span><span class="sxs-lookup"><span data-stu-id="ff388-123">General\*</span></span></li><li><span data-ttu-id="ff388-124">Personalwesen\*</span><span class="sxs-lookup"><span data-stu-id="ff388-124">Human Resources\*</span></span></li><li><span data-ttu-id="ff388-125">Lustige Sachen\*</span><span class="sxs-lookup"><span data-stu-id="ff388-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="ff388-126">Apps</span><span class="sxs-lookup"><span data-stu-id="ff388-126">Apps</span></span><ul><li><span data-ttu-id="ff388-127">Unternehmens Portal (Website an den **Personal** Kanal angeheftet)</span><span class="sxs-lookup"><span data-stu-id="ff388-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="ff388-128">Team Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ff388-128">Team properties</span></span> <ul><li><span data-ttu-id="ff388-129">Team Sichtbarkeit auf "Privat" gesetzt</span><span class="sxs-lookup"><span data-stu-id="ff388-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="ff388-130">\* Automatisch bevorzugte Kanäle</span><span class="sxs-lookup"><span data-stu-id="ff388-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="ff388-131">Um das unternehmensweite Team zu erstellen, indem Sie Standardwerte aus der vordefinierten Vorlage aufnehmen, geben Sie die JSON-Darstellung des Team Objekts im Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="ff388-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="ff388-132">Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph- [Artikel zum Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="ff388-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="ff388-133">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff388-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="ff388-134">Vorlage für das Executive-Team</span><span class="sxs-lookup"><span data-stu-id="ff388-134">Executive Team template</span></span>

<span data-ttu-id="ff388-135">Die Vorlage für das Executive-Team eignet sich hervorragend zum Erstellen eines Teams für Führungskräfte von Unternehmen, um Unternehmensinitiativen wie jährliche Prioritäten, Finanzbudgets, strategische Initiativen, Top-Kunden usw. zu kommunizieren und zusammenzuarbeiten. Diese Vorlage enthält einen *privaten* Kanal, in dem Sie ausgewählte Benutzer zu bestimmten Themen einladen können.</span><span class="sxs-lookup"><span data-stu-id="ff388-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="ff388-136">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="ff388-136">Base template type</span></span>  | <span data-ttu-id="ff388-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ff388-137">baseTemplateId</span></span> | <span data-ttu-id="ff388-138">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="ff388-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="ff388-139">SMB</span><span class="sxs-lookup"><span data-stu-id="ff388-139">SMB -</span></span> <br><span data-ttu-id="ff388-140">Führungskräfte Team</span><span class="sxs-lookup"><span data-stu-id="ff388-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="ff388-141">Kanäle</span><span class="sxs-lookup"><span data-stu-id="ff388-141">Channels</span></span> <ul><li><span data-ttu-id="ff388-142">Allgemein\*</span><span class="sxs-lookup"><span data-stu-id="ff388-142">General\*</span></span></li><li><span data-ttu-id="ff388-143">Private\*</span><span class="sxs-lookup"><span data-stu-id="ff388-143">Private \*</span></span></li></ul> <span data-ttu-id="ff388-144">Apps</span><span class="sxs-lookup"><span data-stu-id="ff388-144">Apps</span></span><ul><li><span data-ttu-id="ff388-145">OneNote (an den **privaten** Kanal angeheftet)</span><span class="sxs-lookup"><span data-stu-id="ff388-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="ff388-146">Planner (an den **privaten** Kanal angeheftet)</span><span class="sxs-lookup"><span data-stu-id="ff388-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="ff388-147">Team Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ff388-147">Team properties</span></span> <ul><li><span data-ttu-id="ff388-148">Team Sichtbarkeit auf "Privat" gesetzt</span><span class="sxs-lookup"><span data-stu-id="ff388-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="ff388-149">\* Automatisch bevorzugte Kanäle</span><span class="sxs-lookup"><span data-stu-id="ff388-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="ff388-150">Um das Executives-Team zu erstellen, indem Sie Standardwerte aus der vordefinierten Vorlage aufnehmen, geben Sie die JSON-Darstellung des Team Objekts im Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="ff388-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="ff388-151">Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph- [Artikel zum Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="ff388-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="ff388-152">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff388-152">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="ff388-153">Abteilungs Team Vorlage</span><span class="sxs-lookup"><span data-stu-id="ff388-153">Departmental Team template</span></span>

<span data-ttu-id="ff388-154">Die Vorlage für ein Abteilungs Team kann zum Erstellen eines Teams für einzelne Abteilungen oder für Projekte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ff388-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="ff388-155">Die Vorlage "Finanzteam" eignet sich ideal für alle Beiträge, Ankündigungen und tägliche Zusammenarbeit und Kommunikation innerhalb der Mitglieder des Finance-Teams (und den Mitgliedern des Executive-Teams entsprechend).</span><span class="sxs-lookup"><span data-stu-id="ff388-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="ff388-156">Die Vorlage enthält einen *privaten* Kanal, in dem Sie ausgewählte Benutzer zu bestimmten Themen einladen können.</span><span class="sxs-lookup"><span data-stu-id="ff388-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="ff388-157">Darüber hinaus stellen wir das unten aufgeführte Skript für das Finance-Team bereit, mit dem die Vorlage auf weitere Abteilungen oder bestimmte Projekte ausgeweitet werden kann, indem Sie Ihre Wünsche hinzufügen, löschen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ff388-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="ff388-158">Wenn Sie beispielsweise über eine *Marketing* Abteilung verfügen, können Sie das Skript anpassen, indem Sie das Team von *Finance* in *Marketing* umbenennen, um ein neues Marketing Team zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff388-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="ff388-159">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="ff388-159">Base template type</span></span> | <span data-ttu-id="ff388-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ff388-160">baseTemplateId</span></span> | <span data-ttu-id="ff388-161">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="ff388-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="ff388-162">SMB</span><span class="sxs-lookup"><span data-stu-id="ff388-162">SMB -</span></span> <br><span data-ttu-id="ff388-163">Finanzen</span><span class="sxs-lookup"><span data-stu-id="ff388-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="ff388-164">Kanäle</span><span class="sxs-lookup"><span data-stu-id="ff388-164">Channels</span></span> <ul><li><span data-ttu-id="ff388-165">Allgemein\*</span><span class="sxs-lookup"><span data-stu-id="ff388-165">General\*</span></span></li><li><span data-ttu-id="ff388-166">Private\*</span><span class="sxs-lookup"><span data-stu-id="ff388-166">Private \*</span></span></li></ul><br> <span data-ttu-id="ff388-167">Apps</span><span class="sxs-lookup"><span data-stu-id="ff388-167">Apps</span></span><ul><li><span data-ttu-id="ff388-168">OneNote (an den **privaten** Kanal angeheftet)</span><span class="sxs-lookup"><span data-stu-id="ff388-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="ff388-169">Planner (an den **privaten** Kanal angeheftet)</span><span class="sxs-lookup"><span data-stu-id="ff388-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="ff388-170">Team Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="ff388-170">Team properties</span></span> <ul><li><span data-ttu-id="ff388-171">Team Sichtbarkeit auf "Privat" gesetzt</span><span class="sxs-lookup"><span data-stu-id="ff388-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="ff388-172">\* Automatisch bevorzugte Kanäle</span><span class="sxs-lookup"><span data-stu-id="ff388-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="ff388-173">Um das Finance-Team zu erstellen, indem Sie Standardwerte aus der vordefinierten Vorlage aufnehmen, geben Sie die JSON-Darstellung des Team Objekts im Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="ff388-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="ff388-174">Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph- [Artikel zum Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="ff388-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="ff388-175">Anforderung</span><span class="sxs-lookup"><span data-stu-id="ff388-175">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="ff388-176">Beispiel: Skript zur Erweiterung der Finanz Team Vorlage</span><span class="sxs-lookup"><span data-stu-id="ff388-176">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="ff388-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ff388-177">Related topics</span></span>

- [<span data-ttu-id="ff388-178">Erste Schritte mit Teams-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="ff388-178">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="ff388-179">[Team erstellen](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="ff388-179">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

