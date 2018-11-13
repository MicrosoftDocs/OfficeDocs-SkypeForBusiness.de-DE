---
title: Erste Schritte mit Teams Vorlagen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295007"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="dc293-103">Erste Schritte mit Teams Vorlagen</span><span class="sxs-lookup"><span data-stu-id="dc293-103">Get started with Teams templates</span></span> 

<span data-ttu-id="dc293-104">Definitionen von entwickelt, um ein geschäftlicher Bedarf oder Projekt ein Team Struktur werden vor dem Teamvorlagen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="dc293-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="dc293-105">Teamvorlagen können schnell und erstellen umfassender Zusammenarbeit Leerzeichen mit Kanäle für verschiedene Themen und Vorinstallieren von apps in unternehmenswichtige Inhalte und Dienste abrufen.</span><span class="sxs-lookup"><span data-stu-id="dc293-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="dc293-106">Teamvorlagen bieten eine vordefinierte Teamstruktur, die Sie auf einfache Weise konsistent Teams innerhalb Ihrer Organisation helfen.</span><span class="sxs-lookup"><span data-stu-id="dc293-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="dc293-107">In diesem Artikel wird die Eigenschaften, die in Vorlagen, welche Basisvorlage definiert werden können, sind, erläutert, und wie Sie verwenden können, Beispiel wenige Anforderungen an ein Team aus einer Vorlage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dc293-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="dc293-108">Dieser Artikel ist für Sie, wenn Sie sind:</span><span class="sxs-lookup"><span data-stu-id="dc293-108">This article is for you if you're:</span></span>

<span data-ttu-id="dc293-109">• Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrere Teams für Ihre Organisation • ein Entwickler suchen So erstellen Sie ein Team mit vordefinierten Kanäle und apps programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="dc293-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="dc293-110">Funktionen für Team-Vorlage</span><span class="sxs-lookup"><span data-stu-id="dc293-110">Team template capabilities</span></span>

<span data-ttu-id="dc293-111">Die meisten Eigenschaften in einem Team sind enthalten und von Vorlagen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc293-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="dc293-112">Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="dc293-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="dc293-113">Die folgende Tabelle enthält eine kurze Zusammenfassung der Umfang von hat und was nicht in Teams Vorlagen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="dc293-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="dc293-114">**Eigenschaften von Team von Teams Vorlagen unterstützt**</span><span class="sxs-lookup"><span data-stu-id="dc293-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="dc293-115">**Eigenschaften von Team von Teams Vorlagen noch nicht unterstützt.**</span><span class="sxs-lookup"><span data-stu-id="dc293-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="dc293-116">Basisvorlage-Typ</span><span class="sxs-lookup"><span data-stu-id="dc293-116">Base template type</span></span> | <span data-ttu-id="dc293-117">Teammitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="dc293-117">Team membership</span></span> |
| <span data-ttu-id="dc293-118">Teamname</span><span class="sxs-lookup"><span data-stu-id="dc293-118">Team name</span></span> | <span data-ttu-id="dc293-119">Team-Bild</span><span class="sxs-lookup"><span data-stu-id="dc293-119">Team picture</span></span> |
| <span data-ttu-id="dc293-120">Team Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc293-120">Team description</span></span> | <span data-ttu-id="dc293-121">Kanal-Einstellungen (beispielsweise automatische Favoriten und Datenschutz)</span><span class="sxs-lookup"><span data-stu-id="dc293-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="dc293-122">Team Sichtbarkeit (öffentlich oder privat)</span><span class="sxs-lookup"><span data-stu-id="dc293-122">Team visibility (public or private)</span></span> | <span data-ttu-id="dc293-123">Connectors</span><span class="sxs-lookup"><span data-stu-id="dc293-123">Connectors</span></span> |
| <span data-ttu-id="dc293-124">Team-Einstellungen (beispielsweise Member, Gast @ erwähnungen)</span><span class="sxs-lookup"><span data-stu-id="dc293-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="dc293-125">Dateien und Inhalte</span><span class="sxs-lookup"><span data-stu-id="dc293-125">Files and content</span></span> |
| <span data-ttu-id="dc293-126">Automatische Favoriten DDE-Kanal</span><span class="sxs-lookup"><span data-stu-id="dc293-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="dc293-127">Installierte app</span><span class="sxs-lookup"><span data-stu-id="dc293-127">Installed app</span></span> | |
| <span data-ttu-id="dc293-128">Angeheftete Registerkarten</span><span class="sxs-lookup"><span data-stu-id="dc293-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="dc293-129">Wir werden werden weitere Funktionen in zukünftigen Versionen des Microsoft-Teams, hinzufügen, für die die aktuellsten Informationen zu unterstützten Eigenschaften überprüfen.</span><span class="sxs-lookup"><span data-stu-id="dc293-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="dc293-130">Was sind Basisvorlage Typen?</span><span class="sxs-lookup"><span data-stu-id="dc293-130">What are base template types?</span></span>

<span data-ttu-id="dc293-131">Basisvorlage Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc293-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="dc293-132">Diese Basis Vorlagen enthalten häufig proprietäre apps, die nicht in den Speicher und die Team-Eigenschaften, die noch nicht einzeln in Teams Formularvorlagen unterstützt verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dc293-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="dc293-133">Nachdem ein Basisvorlage Typ definiert ist, können Sie erweitern oder außer Kraft setzen diese speziellen Vorlagen mit zusätzlichen Eigenschaften, die Sie angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="dc293-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="dc293-134">Einige Basisvorlage Typen enthalten jedoch Eigenschaften, die nicht überschrieben werden können.</span><span class="sxs-lookup"><span data-stu-id="dc293-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="dc293-135">Standardmäßig ist die Basisvorlage auf **Standard** festgelegt, die keine zusätzlichen proprietäre apps oder spezielle Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="dc293-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="dc293-136">Unten ist die aktuelle Liste der Typen Basis Vorlagen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dc293-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="dc293-137">Basisvorlage-Typ</span><span class="sxs-lookup"><span data-stu-id="dc293-137">Base template type</span></span> | <span data-ttu-id="dc293-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="dc293-138">baseTemplateId</span></span> | <span data-ttu-id="dc293-139">Basisvorlage proprietäre apps und spezielle Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc293-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="dc293-140">Standard</span><span class="sxs-lookup"><span data-stu-id="dc293-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="dc293-141">Keine zusätzliche apps und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc293-141">No additional apps and properties</span></span> |
| <span data-ttu-id="dc293-142">Gesundheitswesen - Vorsicht Koordinierung</span><span class="sxs-lookup"><span data-stu-id="dc293-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="dc293-143">Apps:</span><span class="sxs-lookup"><span data-stu-id="dc293-143">Apps:</span></span><br/> <span data-ttu-id="dc293-144">-Patienten app (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="dc293-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="dc293-145">Kanäle:</span><span class="sxs-lookup"><span data-stu-id="dc293-145">Channels:</span></span> <br/> <span data-ttu-id="dc293-146">-Ansagen</span><span class="sxs-lookup"><span data-stu-id="dc293-146">- Announcements</span></span><br/> <span data-ttu-id="dc293-147">-Diabetes</span><span class="sxs-lookup"><span data-stu-id="dc293-147">- Diabetes</span></span><br/> <span data-ttu-id="dc293-148">-Herz-Kreislauf-Erkrankungen</span><span class="sxs-lookup"><span data-stu-id="dc293-148">- Cardiovascular</span></span><br/> <span data-ttu-id="dc293-149">-Registered Pflegepersonal</span><span class="sxs-lookup"><span data-stu-id="dc293-149">- Registered nurses</span></span> |
| <span data-ttu-id="dc293-150">Gesundheitswesen - Prozess drängeln</span><span class="sxs-lookup"><span data-stu-id="dc293-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="dc293-151">Kanäle:</span><span class="sxs-lookup"><span data-stu-id="dc293-151">Channels:</span></span><br/> <span data-ttu-id="dc293-152">-Vermeidbare Todesfälle</span><span class="sxs-lookup"><span data-stu-id="dc293-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="dc293-153">-Mortalität Überprüfung</span><span class="sxs-lookup"><span data-stu-id="dc293-153">- Mortality review</span></span> <br/> <span data-ttu-id="dc293-154">-Fällt verhindern</span><span class="sxs-lookup"><span data-stu-id="dc293-154">- Preventing falls</span></span> <br/> <span data-ttu-id="dc293-155">-Sepsis Pläne</span><span class="sxs-lookup"><span data-stu-id="dc293-155">- Sepsis plans</span></span> |
| <span data-ttu-id="dc293-156">Education - Klasse Team<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dc293-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="dc293-157">Apps:</span><span class="sxs-lookup"><span data-stu-id="dc293-157">Apps:</span></span><br/> <span data-ttu-id="dc293-158">-OneNote Klasse Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="dc293-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="dc293-159">-Assignments app (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="dc293-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="dc293-160">Team-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="dc293-160">Team properties</span></span> <br/> <span data-ttu-id="dc293-161">-Legen Sie die Sichtbarkeit Team auf **HiddenMembership** (können nicht überschrieben werden)</span><span class="sxs-lookup"><span data-stu-id="dc293-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="dc293-162">Education - team-Mitarbeiter<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="dc293-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="dc293-163">Apps</span><span class="sxs-lookup"><span data-stu-id="dc293-163">Apps</span></span><br/> <span data-ttu-id="dc293-164">-OneNote Personal-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</span><span class="sxs-lookup"><span data-stu-id="dc293-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="dc293-165"><sup>1</sup> -Publikation in spät Oktober, 2018</span><span class="sxs-lookup"><span data-stu-id="dc293-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="dc293-166">Wir können Sie Hinzufügen weiterer Basisvorlage Typen in zukünftigen Versionen von Microsoft-Teams, damit die Kontrollkästchen für die aktuellsten Informationen zu Eigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc293-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="dc293-167">Beispiele</span><span class="sxs-lookup"><span data-stu-id="dc293-167">Examples</span></span> 

<span data-ttu-id="dc293-168">Sie können mit dem Erstellen eines Teams über Vorlage durch Installieren von [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span><span class="sxs-lookup"><span data-stu-id="dc293-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="dc293-169">Erstellen Sie ein Team aus einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="dc293-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="dc293-170">Anfragen</span><span class="sxs-lookup"><span data-stu-id="dc293-170">Requests</span></span>

<span data-ttu-id="dc293-171">**Erstellen Sie ein Team mit standard Basisvorlage anfordern**</span><span class="sxs-lookup"><span data-stu-id="dc293-171">**Request to create a team with the standard base template**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

<span data-ttu-id="dc293-172">**Erstellen Sie ein Team mit zusätzlichen einen DDE-Kanal und die nicht Mitglieder löschen Kanäle zulassen**</span><span class="sxs-lookup"><span data-stu-id="dc293-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

<span data-ttu-id="dc293-173">**Erstellen Sie ein Team mit allen unterstützten Eigenschaften anfordern**</span><span class="sxs-lookup"><span data-stu-id="dc293-173">**Request to create a team with all supported properties**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a><span data-ttu-id="dc293-174">Reaktion</span><span class="sxs-lookup"><span data-stu-id="dc293-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="dc293-175">Abrufen des status</span><span class="sxs-lookup"><span data-stu-id="dc293-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="dc293-176">Anforderung</span><span class="sxs-lookup"><span data-stu-id="dc293-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="dc293-177">Reaktion</span><span class="sxs-lookup"><span data-stu-id="dc293-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="dc293-178">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="dc293-178">Related topics</span></span>

- <span data-ttu-id="dc293-179">[Create-team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="dc293-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="dc293-180">Neues Team</span><span class="sxs-lookup"><span data-stu-id="dc293-180">New-Team</span></span>](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="dc293-181">Administratorschulungen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dc293-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)