---
title: Erste Schritte mit Teams Vorlagen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Erfahren Sie, wie Teams Vorlagen verwenden, um ein Team mit vordefinierten Kanälen zu erstellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801464"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="d510b-103">Erste Schritte mit Teams Vorlagen</span><span class="sxs-lookup"><span data-stu-id="d510b-103">Get started with Teams templates</span></span> 

<span data-ttu-id="d510b-104">Teams Vorlagen werden vor dem Definitionen von ein Team Struktur entwickelt, um eine geschäftlicher Bedarf oder ein Projekt erstellt.</span><span class="sxs-lookup"><span data-stu-id="d510b-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="d510b-105">Vorlagen für Teams können schnell und erstellen umfassender Zusammenarbeit Leerzeichen mit Kanäle für verschiedene Themen und Vorinstallieren von apps in unternehmenswichtige Inhalte und Dienste abrufen.</span><span class="sxs-lookup"><span data-stu-id="d510b-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="d510b-106">Teams Vorlagen bieten eine vordefinierte Teamstruktur, die Sie auf einfache Weise konsistent Teams innerhalb Ihrer Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="d510b-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="d510b-107">In diesem Artikel wird die Eigenschaften, die in Vorlagen, welche Basisvorlage definiert werden können, sind, erläutert, und wie Sie verwenden können, Beispiel wenige Anforderungen an ein Team aus einer Vorlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d510b-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="d510b-108">Dieser Artikel ist für Sie, wenn Sie sind:</span><span class="sxs-lookup"><span data-stu-id="d510b-108">This article is for you if you're:</span></span>

- <span data-ttu-id="d510b-109">Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams innerhalb Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="d510b-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="d510b-110">Ein Entwickler aus, um ein Team programmgesteuert mit vordefinierten Kanäle und apps erstellen werden soll</span><span class="sxs-lookup"><span data-stu-id="d510b-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="d510b-111">Teams Vorlage Funktionen</span><span class="sxs-lookup"><span data-stu-id="d510b-111">Teams template capabilities</span></span>

<span data-ttu-id="d510b-112">Die meisten Eigenschaften in einem Team sind enthalten und von Vorlagen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d510b-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="d510b-113">Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d510b-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="d510b-114">Die folgende Tabelle enthält eine kurze Zusammenfassung der Umfang von hat und was nicht in Teams Vorlagen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d510b-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="d510b-115">**Eigenschaften von Team von Teams Vorlagen unterstützt**</span><span class="sxs-lookup"><span data-stu-id="d510b-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="d510b-116">**Eigenschaften von Team von Teams Vorlagen noch nicht unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="d510b-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="d510b-117">Basisvorlage-Typ</span><span class="sxs-lookup"><span data-stu-id="d510b-117">Base template type</span></span> | <span data-ttu-id="d510b-118">Teammitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="d510b-118">Team membership</span></span> |
| <span data-ttu-id="d510b-119">Teamname</span><span class="sxs-lookup"><span data-stu-id="d510b-119">Team name</span></span> | <span data-ttu-id="d510b-120">Team-Bild</span><span class="sxs-lookup"><span data-stu-id="d510b-120">Team picture</span></span> |
| <span data-ttu-id="d510b-121">Team Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d510b-121">Team description</span></span> | <span data-ttu-id="d510b-122">Kanal-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d510b-122">Channel settings</span></span> |
| <span data-ttu-id="d510b-123">Team Sichtbarkeit (öffentlich oder privat)</span><span class="sxs-lookup"><span data-stu-id="d510b-123">Team visibility (public or private)</span></span> | <span data-ttu-id="d510b-124">Connectors</span><span class="sxs-lookup"><span data-stu-id="d510b-124">Connectors</span></span> |
| <span data-ttu-id="d510b-125">Team-Einstellungen (beispielsweise Member, Gast @ erwähnungen)</span><span class="sxs-lookup"><span data-stu-id="d510b-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="d510b-126">Dateien und Inhalte</span><span class="sxs-lookup"><span data-stu-id="d510b-126">Files and content</span></span> |
| <span data-ttu-id="d510b-127">Automatische Favoriten DDE-Kanal</span><span class="sxs-lookup"><span data-stu-id="d510b-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="d510b-128">Installierte app</span><span class="sxs-lookup"><span data-stu-id="d510b-128">Installed app</span></span> | |
| <span data-ttu-id="d510b-129">Angeheftete Registerkarten</span><span class="sxs-lookup"><span data-stu-id="d510b-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="d510b-130">Wir werden werden weitere Funktionen in zukünftigen Versionen des Microsoft-Teams, hinzufügen, für die die aktuellsten Informationen zu unterstützten Eigenschaften überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d510b-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="d510b-131">Was sind Basisvorlage Typen?</span><span class="sxs-lookup"><span data-stu-id="d510b-131">What are base template types?</span></span>

<span data-ttu-id="d510b-132">Basisvorlage Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d510b-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="d510b-133">Diese Basis Vorlagen enthalten häufig proprietäre apps, die nicht in den Speicher und die Team-Eigenschaften zur Verfügung stehen, die noch nicht einzeln in Teams Formularvorlagen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="d510b-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="d510b-134">Nachdem ein Basisvorlage Typ definiert ist, können Sie erweitern oder außer Kraft setzen diese speziellen Vorlagen mit zusätzlichen Eigenschaften, die Sie angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="d510b-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="d510b-135">Jedoch einige Basisvorlage Typen enthalten Eigenschaften, die nicht überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="d510b-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="d510b-136">Standardmäßig ist die Basisvorlage auf **Standard** festgelegt, die keine zusätzlichen proprietäre apps oder spezielle Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="d510b-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="d510b-137">Unten ist die aktuelle Liste der Typen Basis Vorlagen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d510b-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="d510b-138">Basisvorlage-Typ</span><span class="sxs-lookup"><span data-stu-id="d510b-138">Base template type</span></span> | <span data-ttu-id="d510b-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d510b-139">baseTemplateId</span></span> | <span data-ttu-id="d510b-140">Basisvorlage proprietäre apps und spezielle Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d510b-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="d510b-141">Standard</span><span class="sxs-lookup"><span data-stu-id="d510b-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="d510b-142">Keine zusätzliche apps und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d510b-142">No additional apps and properties</span></span> |
| <span data-ttu-id="d510b-143">Education-</span><span class="sxs-lookup"><span data-stu-id="d510b-143">Education -</span></span> <br><span data-ttu-id="d510b-144">Klasse Team<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d510b-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="d510b-145">Apps:</span><span class="sxs-lookup"><span data-stu-id="d510b-145">Apps:</span></span><ul><li><span data-ttu-id="d510b-146">OneNote-Klasse-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="d510b-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="d510b-147">Assignments-app (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="d510b-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="d510b-148">Team-Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="d510b-148">Team properties:</span></span><ul><li><span data-ttu-id="d510b-149">Legen Sie die Sichtbarkeit Team auf **HiddenMembership** (können nicht überschrieben werden)</span><span class="sxs-lookup"><span data-stu-id="d510b-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="d510b-150">Education-</span><span class="sxs-lookup"><span data-stu-id="d510b-150">Education -</span></span><br><span data-ttu-id="d510b-151">Mitarbeiter Team<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="d510b-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="d510b-152">Apps:</span><span class="sxs-lookup"><span data-stu-id="d510b-152">Apps:</span></span><ul><li><span data-ttu-id="d510b-153">OneNote-Personal-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="d510b-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="d510b-154">Education-</span><span class="sxs-lookup"><span data-stu-id="d510b-154">Education -</span></span><br><span data-ttu-id="d510b-155">PLC-team</span><span class="sxs-lookup"><span data-stu-id="d510b-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="d510b-156">Apps:</span><span class="sxs-lookup"><span data-stu-id="d510b-156">Apps:</span></span><ul><li><span data-ttu-id="d510b-157">OneNote PLC-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="d510b-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="d510b-158"><sup>1</sup> -Publikation in spät Oktober, 2018</span><span class="sxs-lookup"><span data-stu-id="d510b-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="d510b-159">Wir können Sie Hinzufügen weiterer Basisvorlage Typen in zukünftigen Versionen von Microsoft-Teams, damit die Kontrollkästchen für die aktuellsten Informationen zu Eigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d510b-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="d510b-160">Beispiele</span><span class="sxs-lookup"><span data-stu-id="d510b-160">Examples</span></span> 

<span data-ttu-id="d510b-161">Sie können die mithilfe einer Vorlage um ein Team erstellen mithilfe der [Microsoft Graph-API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)starten.</span><span class="sxs-lookup"><span data-stu-id="d510b-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="d510b-162">Erstellen Sie ein Team aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="d510b-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="d510b-163">Anfragen</span><span class="sxs-lookup"><span data-stu-id="d510b-163">Requests</span></span>

<span data-ttu-id="d510b-164">**Erstellen Sie ein Team mit standard Basisvorlage anfordern**</span><span class="sxs-lookup"><span data-stu-id="d510b-164">**Request to create a team with the standard base template**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

<span data-ttu-id="d510b-165">**Erstellen Sie ein Team mit zusätzlichen einen DDE-Kanal und die nicht Mitglieder löschen Kanäle zulassen**</span><span class="sxs-lookup"><span data-stu-id="d510b-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

<span data-ttu-id="d510b-166">**Erstellen Sie ein Team mit allen unterstützten Eigenschaften anfordern**</span><span class="sxs-lookup"><span data-stu-id="d510b-166">**Request to create a team with all supported properties**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a><span data-ttu-id="d510b-167">Abrufen des status</span><span class="sxs-lookup"><span data-stu-id="d510b-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="d510b-168">Anforderung</span><span class="sxs-lookup"><span data-stu-id="d510b-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="d510b-169">Reaktion</span><span class="sxs-lookup"><span data-stu-id="d510b-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="d510b-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d510b-170">Related topics</span></span>

- <span data-ttu-id="d510b-171">[Create-team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="d510b-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="d510b-172">Neues Team</span><span class="sxs-lookup"><span data-stu-id="d510b-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="d510b-173">Administrator-Schulung für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d510b-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)