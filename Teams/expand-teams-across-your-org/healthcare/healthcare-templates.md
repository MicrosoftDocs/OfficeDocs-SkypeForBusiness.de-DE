---
title: Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen
ms.openlocfilehash: 282c28661de3d2678f7b4b29129de4f80dece491
ms.sourcegitcommit: 89b866a3c383555f6f89dc77bebd74cddf9e40fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013217"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="e825c-103">Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="e825c-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="e825c-104">Microsoft-Teams Vorlagen können Sie schnell und einfach Teams durch die Bereitstellung von Einstellungen, Kanäle und vorinstallierte apps einer vordefinierten Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="e825c-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="e825c-105">Für Unternehmen aus dem Gesundheitswesen können Vorlagen besonders leistungsstarke entsprechen, wie Struktur für Benutzer mit der Verwendung Verwaltungsberichte von Teams am besten effektiv zu nutzen ausgerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="e825c-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="e825c-106">Vorlagen ermöglichen Administratoren das konsistente Teams in ihrer Organisation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e825c-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="e825c-107">Dieser Artikel ist für Sie, wenn Sie die für die Planung, Bereitstellung und Verwaltung mehrere Teams für Ihre Organisation zuständig sind.</span><span class="sxs-lookup"><span data-stu-id="e825c-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="e825c-108">Wir derzeit bieten zwei ersten Teilnehmer aus dem Gesundheitswesen Vorlagen, die Sie für eine Vielzahl von Situationen nutzen können.</span><span class="sxs-lookup"><span data-stu-id="e825c-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="e825c-109">Weitere Informationen zu Team finden finden Sie unter Vorlagen im Allgemeinen bitte [Erste Schritte mit Teams Vorlagen](../../get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="e825c-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="e825c-110">Bezirk-Vorlage</span><span class="sxs-lookup"><span data-stu-id="e825c-110">Ward template</span></span>

<span data-ttu-id="e825c-111">Die Vorlage Bezirk ist für die Kommunikation und Zusammenarbeit innerhalb einer Bezirk, Pod oder Abteilung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e825c-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="e825c-112">Die Vorlage kann verwendet werden, um patientenverwaltungs-als auch Bedarf für den Betrieb von einem Bezirk zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="e825c-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="e825c-113">Beispielsweise Bezirk Ansagen im Kanal *Ankündigungen* gebucht werden und Schichten in *Personal*verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="e825c-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="e825c-114">Wenn Sie zur Optimierung Ihrer Bezirk Vorgänge angezeigt werden, ist dieser Vorlage für Sie.</span><span class="sxs-lookup"><span data-stu-id="e825c-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="e825c-115">Basisvorlage-Typ</span><span class="sxs-lookup"><span data-stu-id="e825c-115">Base Template Type</span></span> |<span data-ttu-id="e825c-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e825c-116">baseTemplateId</span></span> |<span data-ttu-id="e825c-117">Geplante Vorlage Kanäle</span><span class="sxs-lookup"><span data-stu-id="e825c-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="e825c-118">Gesundheitswesen - Bezirk</span><span class="sxs-lookup"><span data-stu-id="e825c-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="e825c-119">Ansagen\*</span><span class="sxs-lookup"><span data-stu-id="e825c-119">Announcements\*</span></span> <br> <span data-ttu-id="e825c-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="e825c-120">Huddles\*</span></span> <br> <span data-ttu-id="e825c-121">Rundet\*</span><span class="sxs-lookup"><span data-stu-id="e825c-121">Rounds\*</span></span> <br> <span data-ttu-id="e825c-122">Koordiniertes\*</span><span class="sxs-lookup"><span data-stu-id="e825c-122">Staffing\*</span></span> <br> <span data-ttu-id="e825c-123">Schulung\*</span><span class="sxs-lookup"><span data-stu-id="e825c-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="e825c-124">\*Automatische favorisierte</span><span class="sxs-lookup"><span data-stu-id="e825c-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="e825c-125">Krankenhaus-Vorlage</span><span class="sxs-lookup"><span data-stu-id="e825c-125">Hospital template</span></span>

<span data-ttu-id="e825c-126">Die Vorlage Krankenhaus ist für die Kommunikation und Zusammenarbeit zwischen mehreren Patientenbett einsetzen, folgende und Abteilungen innerhalb einer Krankenhaus vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="e825c-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="e825c-127">In dieser Vorlage sind mehrere operative Kanäle einschließlich, *Ansagen*, *Custodial*und *Apotheke*enthalten, aber wir auch stellen ein Skript Unterschreitung erweitert die Vorlage mit einer Vielzahl von zusätzlichen Abteilung oder spezielle-centric Kanäle, denen Sie hinzufügen können, löschen aus, oder bearbeiten nach Belieben.</span><span class="sxs-lookup"><span data-stu-id="e825c-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="e825c-128">Beispielsweise wenn Sie über eine Abteilung *Endokrinologie* , jedoch nicht einen Kanal für *Ophthalmology benötigen*, kann dann das Skript angepasst werden, um einen DDE-Kanal *Endokrinologie* enthalten, und entfernen Sie den Kanal *Ophthalmology* .</span><span class="sxs-lookup"><span data-stu-id="e825c-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="e825c-129">Es wird empfohlen, diese spezielle oder Bezirk modelliert Kanäle nicht automatisch-favorisierte Benachrichtigung Sättigung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="e825c-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="e825c-130">Im Allgemeinen bevorzugten Benutzer alle Kanäle, dass sie relevanten finden.</span><span class="sxs-lookup"><span data-stu-id="e825c-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="e825c-131">Basisvorlage-Typ</span><span class="sxs-lookup"><span data-stu-id="e825c-131">Base Template Type</span></span> |<span data-ttu-id="e825c-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="e825c-132">baseTemplateId</span></span> |<span data-ttu-id="e825c-133">Geplante Vorlage Kanäle</span><span class="sxs-lookup"><span data-stu-id="e825c-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="e825c-134">Gesundheitswesen - Krankenhaus</span><span class="sxs-lookup"><span data-stu-id="e825c-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="e825c-135">Ansagen\*</span><span class="sxs-lookup"><span data-stu-id="e825c-135">Announcements\*</span></span> <br> <span data-ttu-id="e825c-136">Beachtung\*</span><span class="sxs-lookup"><span data-stu-id="e825c-136">Compliance\*</span></span> <br> <span data-ttu-id="e825c-137">Freiheitsentziehenden</span><span class="sxs-lookup"><span data-stu-id="e825c-137">Custodial</span></span> <br> <span data-ttu-id="e825c-138">Personalwesen</span><span class="sxs-lookup"><span data-stu-id="e825c-138">Human Resources</span></span> <br> <span data-ttu-id="e825c-139">Apotheke</span><span class="sxs-lookup"><span data-stu-id="e825c-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="e825c-140">\*Automatische favorisierte</span><span class="sxs-lookup"><span data-stu-id="e825c-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="e825c-141">So verwenden Sie die erste Partei-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="e825c-141">How to use first party templates</span></span>

<span data-ttu-id="e825c-142">Um diese Vorlagen zu verwenden, ändern Sie einfach die Eigenschaft 'template@odata.bind' im Textkörper Anforderung von'standard' der oben genannten TemplateIDs.</span><span class="sxs-lookup"><span data-stu-id="e825c-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="e825c-143">Weitere Informationen zum Bereitstellen von Vorlagen für Teams, finden im Microsoft Graph- [Artikel über das Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="e825c-143">For more information on how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="e825c-144">Beispiel: Krankenhaus Vorlage Erweiterungsskript</span><span class="sxs-lookup"><span data-stu-id="e825c-144">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women’s Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```
