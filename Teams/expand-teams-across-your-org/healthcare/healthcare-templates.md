---
title: Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen
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
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen
ms.openlocfilehash: 756f9a50dac14575250a521750f80dbe8d1242b8
ms.sourcegitcommit: 9ae5dadaab999acd061cc9418dbd55d98b82980e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "38702316"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="2a1d5-103">Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="2a1d5-103">Get started with Teams templates for Healthcare organizations</span></span>

<span data-ttu-id="2a1d5-104">Mit Microsoft Teams-Vorlagen können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="2a1d5-105">Für Organisationen im Gesundheitswesen können Vorlagen besonders leistungsstark sein, da Sie die Struktur für Benutzer bereitstellen, um sich mit der effektiven Nutzung von Teams auszurichten.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to best leverage Teams effectively.</span></span> <span data-ttu-id="2a1d5-106">Mit Vorlagen können Administratoren auch konsistente Teams in ihren Organisationen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="2a1d5-107">Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in ihrer gesamten Gesundheitsorganisation verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your Healthcare organization.</span></span>

<span data-ttu-id="2a1d5-108">Wir bieten derzeit zwei First Party Healthcare-Vorlagen an, die Sie für unterschiedliche Situationen nutzen können.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-108">We currently offer two first party healthcare templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="2a1d5-109">Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](../../get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="2a1d5-109">To learn more about team templates in general, please see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="2a1d5-110">Ward-Vorlage</span><span class="sxs-lookup"><span data-stu-id="2a1d5-110">Ward template</span></span>

<span data-ttu-id="2a1d5-111">Die Ward-Vorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Pod oder einer Abteilung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="2a1d5-112">Die Vorlage kann verwendet werden, um die Patientenverwaltung sowie die betrieblichen Anforderungen einer Station zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="2a1d5-113">So können beispielsweise Ward-Ankündigungen im *Ankündigungen* -Kanal veröffentlicht werden, und Schichten können in der *Besetzung*verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="2a1d5-114">Wenn Sie Ihre Abteilungen optimieren möchten, ist diese Vorlage für Sie.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-114">If you’re looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="2a1d5-115">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="2a1d5-115">Base Template Type</span></span> |<span data-ttu-id="2a1d5-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2a1d5-116">baseTemplateId</span></span> |<span data-ttu-id="2a1d5-117">Baseline-Vorlagen Kanäle</span><span class="sxs-lookup"><span data-stu-id="2a1d5-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2a1d5-118">Healthcare – Ward</span><span class="sxs-lookup"><span data-stu-id="2a1d5-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="2a1d5-119">Ankündigungen\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-119">Announcements\*</span></span> <br> <span data-ttu-id="2a1d5-120">Kauert\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-120">Huddles\*</span></span> <br> <span data-ttu-id="2a1d5-121">Runden\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-121">Rounds\*</span></span> <br> <span data-ttu-id="2a1d5-122">Personal\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-122">Staffing\*</span></span> <br> <span data-ttu-id="2a1d5-123">Ausbildung\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="2a1d5-124">\*Automatisch Favoriten</span><span class="sxs-lookup"><span data-stu-id="2a1d5-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="2a1d5-125">Vorlage für Krankenhaus</span><span class="sxs-lookup"><span data-stu-id="2a1d5-125">Hospital template</span></span>

<span data-ttu-id="2a1d5-126">Die Vorlage für das Krankenhaus ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Hülsen und Abteilungen innerhalb eines Krankenhauses vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="2a1d5-127">In dieser Vorlage sind mehrere operationelle Kanäle enthalten, einschließlich *Ankündigungen*, *Freiheitsentzug*und *Pharmazie*, aber wir bieten auch ein Skript, das die Vorlage mit einer Reihe weiterer Abteilungs-oder Spezial orientierter Kanäle erweitert, die Sie Ihren Wünschen hinzufügen, löschen oder bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-127">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="2a1d5-128">Wenn Sie beispielsweise über eine *Endokrinologie* -Abteilung verfügen, aber keinen Kanal für die *Augenheilkunde*benötigen, kann das Skript so angepasst werden, dass es einen *Endokrinologie* -Kanal enthält, und den *Ophthalmologie* -Kanal entfernen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-128">For example, if you have an *Endocrinology* department, but don’t need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="2a1d5-129">Wir empfehlen, dass diese Spezial-oder Stations modellierten Kanäle nicht automatisch als Favorit festgelegt werden, um eine Benachrichtigungs Sättigung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="2a1d5-130">Benutzer können in der Regel alle Kanäle, die für Sie relevant sind, als Favoriten festlegen.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="2a1d5-131">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="2a1d5-131">Base Template Type</span></span> |<span data-ttu-id="2a1d5-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="2a1d5-132">baseTemplateId</span></span> |<span data-ttu-id="2a1d5-133">Baseline-Vorlagen Kanäle</span><span class="sxs-lookup"><span data-stu-id="2a1d5-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="2a1d5-134">Gesundheitswesen – Krankenhaus</span><span class="sxs-lookup"><span data-stu-id="2a1d5-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="2a1d5-135">Ankündigungen\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-135">Announcements\*</span></span> <br> <span data-ttu-id="2a1d5-136">Compliance\*</span><span class="sxs-lookup"><span data-stu-id="2a1d5-136">Compliance\*</span></span> <br> <span data-ttu-id="2a1d5-137">Freiheits</span><span class="sxs-lookup"><span data-stu-id="2a1d5-137">Custodial</span></span> <br> <span data-ttu-id="2a1d5-138">Personalwesen</span><span class="sxs-lookup"><span data-stu-id="2a1d5-138">Human Resources</span></span> <br> <span data-ttu-id="2a1d5-139">Apotheke</span><span class="sxs-lookup"><span data-stu-id="2a1d5-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="2a1d5-140">\*Automatisch Favoriten</span><span class="sxs-lookup"><span data-stu-id="2a1d5-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="2a1d5-141">Verwenden von Vorlagen für Erstanbieter</span><span class="sxs-lookup"><span data-stu-id="2a1d5-141">How to use first party templates</span></span>

<span data-ttu-id="2a1d5-142">Wenn Sie diese Vorlagen verwenden möchten, ändern Sie einfach die Eigenschaft "Template@odata. Bind" im Anforderungstext von "Standard" in das obige TemplateIDs.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-142">To use these templates, simply change the ‘template@odata.bind’ property in the request body from ‘standard’ to the TemplateIDs above.</span></span>  <span data-ttu-id="2a1d5-143">Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="2a1d5-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="2a1d5-144">Die Kanäle in der Vorlage werden auf der RegisterkarteAllgemein automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="2a1d5-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="2a1d5-145">Beispiel: Erweiterungs Skript für Krankenhaus Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2a1d5-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="2a1d5-146">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2a1d5-146">Related topics</span></span>

[<span data-ttu-id="2a1d5-147">Erste Schritte mit Teams-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="2a1d5-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="2a1d5-148">Erste Schritte mit Teams für Organisationen im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="2a1d5-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
