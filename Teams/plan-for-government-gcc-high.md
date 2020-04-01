---
title: Planen von Microsoft 365 Government – GCC High-Bereitstellungen – Microsoft Teams
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Leitfaden für IT-Experten zum Steuern von Office 365-Bereitstellungen in Entitäten, die Daten verarbeiten, die von der US-amerikanischen Regierung geregelt werden.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7be9916a1c51b7e98467d1e8c44a18dd6d227d35
ms.sourcegitcommit: 4e1647d19501b37860d9fc79370fa4347f76f85f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2020
ms.locfileid: "43079417"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="4f648-103">Plan für Microsoft 365 Government-gcc-höchst Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="4f648-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="4f648-104">Diese Anleitung richtet sich an IT-Experten, die die Bereitstellung von Office 365 in US-amerikanischen Bundesbehörden oder anderen Entitäten vorantreiben, die Daten verarbeiten, die behördlichen Vorschriften und Anforderungen unterliegen, wobei die Verwendung von Microsoft 365 Government – gcc-höchst angemessen ist, um diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="4f648-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="4f648-105">Wenn Ihre Organisation bereits die Anforderungen von Microsoft 365 Government – gcc für höchste Ansprüche erfüllt und in das Programm übernommen und akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt zu Schritt 3 wechseln.</span><span class="sxs-lookup"><span data-stu-id="4f648-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="4f648-106">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="4f648-106">Step 1.</span></span> <span data-ttu-id="4f648-107">Ermitteln Sie, ob Ihre Organisation Microsoft 365 Government-gcc-höchstanforderungen erfüllt und die Anspruchsvoraussetzungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="4f648-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="4f648-108">Die Microsoft 365 Government-gcc-Umgebung bietet die Einhaltung der Anforderungen der US-Regierung für Cloud-Services.</span><span class="sxs-lookup"><span data-stu-id="4f648-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="4f648-109">Neben der Nutzung der Features und Funktionen von Office 365 profitieren Organisationen von den folgenden Features, die für die Microsoft 365 Government – gcc-Höchstleistung einzigartig sind:</span><span class="sxs-lookup"><span data-stu-id="4f648-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="4f648-110">Der Kunden Inhalt Ihrer Organisation wird logisch von Kundeninhalten in den kommerziellen Office 365-Diensten von Microsoft getrennt.</span><span class="sxs-lookup"><span data-stu-id="4f648-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="4f648-111">Der Kunden Inhalt Ihrer Organisation wird in den Vereinigten Staaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4f648-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="4f648-112">Der Zugriff auf die Kunden Inhalte Ihrer Organisation ist auf geschirmte Microsoft-Mitarbeiter beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4f648-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="4f648-113">Microsoft 365 Government – gcc-Höchstleistung entspricht Zertifizierungen und Akkreditierungen, die für Kunden im öffentlichen Dienst in den USA erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="4f648-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="4f648-114">Weitere Informationen zum Microsoft 365 Government – gcc-Angebot für Kunden der US-Regierung finden Sie unter [Office 365 Government-Pläne](https://products.office.com/government/compare-office-365-government-plans), einschließlich der [Anspruchsvoraussetzungen](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="4f648-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="4f648-115">Die [Office 365 US Government Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) beschreibt die Vorteile der Plattform, die auf die Erfüllung der Compliance-Anforderungen in den USA ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="4f648-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="4f648-116">Möglicherweise möchten Sie die Tabellen mit Informationen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen, die **für meine Organisation y/n relevant** sind und **den Anforderungen meiner Organisation y/n entsprechen**.</span><span class="sxs-lookup"><span data-stu-id="4f648-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="4f648-117">Sie können diese Liste dann mit ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="4f648-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/><span data-ttu-id="4f648-119">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="4f648-119">Decision points</span></span>|<ul><li><span data-ttu-id="4f648-120">Entscheiden Sie, ob Microsoft 365 Government-gcc-höchst für Ihre Organisation geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="4f648-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="4f648-121">Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="4f648-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="4f648-122">Microsoft 365 Government-gcc-höchst steht nur in den USA zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4f648-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="4f648-123">Kunden außerhalb der US-Regierung können aus einer Reihe von [Office 365 Government-Plänen](https://products.office.com/en/government/compare-office-365-government-plans)wählen.</span><span class="sxs-lookup"><span data-stu-id="4f648-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="4f648-124">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="4f648-124">Step 2.</span></span> <span data-ttu-id="4f648-125">Bewerben für Microsoft 365 Government-gcc-höchst</span><span class="sxs-lookup"><span data-stu-id="4f648-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="4f648-126">Nachdem Sie entschieden haben, dass dieser Dienst für Ihre Organisation richtig ist, beginnen Sie mit dem Verfahren [zur Beantragung dieses Diensts](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="4f648-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="4f648-127">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="4f648-127">Step 3.</span></span> <span data-ttu-id="4f648-128">Grundlegendes zu den Microsoft 365 Government-gcc-Standardsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="4f648-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="4f648-129">Wir empfehlen, dass Sie sich Zeit nehmen, um Ihre [Administrator-und Sicherheitseinstellungen](enable-features-office-365.md) sorgfältig zu überprüfen, bevor Sie Sie ändern, und die Auswirkungen auf die Kompatibilität berücksichtigen, bevor Sie Änderungen an den Standardsicherheitseinstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4f648-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/><span data-ttu-id="4f648-131">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="4f648-131">Decision point</span></span>|<ul><li><span data-ttu-id="4f648-132">Entscheiden Sie, ob Sie die standardmäßigen Microsoft 365 Government-gcc-Sicherheitseinstellungen ändern müssen, um zunächst die Auswirkungen von Änderungen zu verstehen, die Sie möglicherweise vornehmen.</span><span class="sxs-lookup"><span data-stu-id="4f648-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="4f648-133">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="4f648-133">Step 4.</span></span> <span data-ttu-id="4f648-134">Grundlegendes zu den Teamfunktionen, die derzeit in Microsoft 365 Government verfügbar sind – gcc-höchst</span><span class="sxs-lookup"><span data-stu-id="4f648-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="4f648-135">Um den Anforderungen unserer Government Cloud-Kunden gerecht zu werden, gibt es einige Unterschiede zwischen Teams in Microsoft 365 Government-gcc-höchst-und Teams in den Enterprise-Plänen.</span><span class="sxs-lookup"><span data-stu-id="4f648-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="4f648-136">Informationen zu den verfügbaren Features finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4f648-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="4f648-137">Microsoft Teams-Dienstbeschreibung</span><span class="sxs-lookup"><span data-stu-id="4f648-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="4f648-138">Schritt 5:</span><span class="sxs-lookup"><span data-stu-id="4f648-138">Step 5.</span></span> <span data-ttu-id="4f648-139">Plan für Governance</span><span class="sxs-lookup"><span data-stu-id="4f648-139">Plan for governance</span></span>

<span data-ttu-id="4f648-140">Ermitteln Sie Ihre Anforderungen für Governance und wie Sie Sie erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="4f648-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="4f648-141">Weitere Informationen finden Sie unter [Planen von Governance in Teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="4f648-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="4f648-142">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="4f648-142">Decision point</span></span> |<ul><li><span data-ttu-id="4f648-143">Ermitteln und dokumentieren Sie Ihre Governance-Anforderungen, und befolgen Sie die Richtlinien in [Plan for Governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="4f648-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="4f648-144">Schritt 6:</span><span class="sxs-lookup"><span data-stu-id="4f648-144">Step 6.</span></span> <span data-ttu-id="4f648-145">Bereitstellen von Teams für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="4f648-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="4f648-146">Nachdem Sie die Microsoft 365 Government – gcc-hoch installiert haben, befolgen Sie den empfohlenen Bereitstellungspfad, der in [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4f648-146">After you've been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="4f648-147">Stellen Sie sicher, dass Sie sich mit Ihrem Adoptions-, Change Management-und Team-Champion beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="4f648-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="4f648-148">Sie können auch mit der [Zusammenarbeit](https://www.microsoft.com/fasttrack) oder dem ausgewählten Partner an Bord des Diensts arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4f648-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

