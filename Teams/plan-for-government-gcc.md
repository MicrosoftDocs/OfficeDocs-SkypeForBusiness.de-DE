---
title: Office 365 Government-gcc-Bereitstellungen
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Leitfaden für IT-Experten zum Steuern von Office 365-Bereitstellungen in Entitäten, die Daten verarbeiten, die von der US-amerikanischen Regierung geregelt werden
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: b93762c92d9681074124ba8ddb3fd066bdf8a60a
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665227"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="432be-103">Plan für Office 365 Government-gcc-Bereitstellungen</span><span class="sxs-lookup"><span data-stu-id="432be-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="432be-104">Diese Anleitung richtet sich an IT-Experten, die Bereitstellungen von Office 365 in den US-Bundes-, bundesstaatlichen, lokalen, Stammes-oder Gebietskörperschaften oder anderen Entitäten steuern, die Daten verarbeiten, die behördlichen Vorschriften und Anforderungen unterliegen, wobei die Verwendung von Office 365 Government-gcc geeignet ist, diese Anforderungen zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="432be-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="432be-105">Neuer März 26, 2020: verpassen Sie nicht unseren downloadbaren [schnell Start Leit Faden für gcc](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span><span class="sxs-lookup"><span data-stu-id="432be-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="432be-106">Microsoft Teams erlebt aufgrund der Coronavirus (COVID-19)-Pandemie eine enorme Spitze bei Online-anrufen und Audio/Videokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="432be-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="432be-107">Als Antwort auf die noch nie dagewesene Zunahme von Anrufen und die Gewährleistung von Kontinuität und Verfügbarkeit ermöglicht Microsoft Microsoft Teams gcc-Audio/Video-Server die Nutzung der Verarbeitungskapazität in unseren kommerziellen Rechenzentren sowie in unseren Regierungs Rechenzentren.</span><span class="sxs-lookup"><span data-stu-id="432be-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="432be-108">Diese Audio/Video-Server befinden sich auf den Microsoft Azure FedRAMP-Grenz Servern in den Vereinigten Staaten und speichern keine Kunden Inhalte.</span><span class="sxs-lookup"><span data-stu-id="432be-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="432be-109">Diese Server verarbeiten jedoch Audio-und Videodaten für Anrufe und Konferenzen und sind während dieser Zwischenzeit unter unseren kaufmännischen Mitarbeitern tätig.</span><span class="sxs-lookup"><span data-stu-id="432be-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="432be-110">Qualifizierte, geprüfte Mitarbeiter überwachen diese Server auf potenziellen Zugriff auf Kundendaten, indem Sie alle interaktiven log-ons auf diesen Servern überprüfen.</span><span class="sxs-lookup"><span data-stu-id="432be-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="432be-111">Qualifiziertes Personal erfüllt die Anforderungen von gcc für den Zugriff auf Kunden Inhalte.</span><span class="sxs-lookup"><span data-stu-id="432be-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="432be-112">Details zu den Prüfungsanforderungen finden Sie in der [gcc-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span><span class="sxs-lookup"><span data-stu-id="432be-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="432be-113">Vielen Dank für Ihre Unterstützung, während wir Schritte Unternehmen, um sicherzustellen, dass unsere Dienste in diesen außergewöhnlichen Zeiten verfügbar und zuverlässig sind.</span><span class="sxs-lookup"><span data-stu-id="432be-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="432be-114">Wenn Ihre Organisation bereits die Berechtigungsanforderungen von Office 365 Government-gcc erfüllt und in das Programm übernommen und akzeptiert wurde, können Sie die Schritte 1 und 2 überspringen und direkt zu Schritt 3 wechseln.</span><span class="sxs-lookup"><span data-stu-id="432be-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="432be-115">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="432be-115">Step 1.</span></span> <span data-ttu-id="432be-116">Ermitteln Sie, ob Ihre Organisation Office 365 Government-gcc benötigt und die Anspruchsvoraussetzungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="432be-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="432be-117">Die Office 365 Government-gcc-Umgebung bietet die Einhaltung der US-Government-Anforderungen für Cloud-Dienste, einschließlich FedRAMP moderate, und Anforderungen für Strafjustiz-und föderale Steuerinformationssystem (CJI-und FTI-Datentypen).</span><span class="sxs-lookup"><span data-stu-id="432be-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="432be-118">Neben den Features und Funktionen von Office 365 profitieren Organisationen von den folgenden Features, die für Office 365 Government-gcc einzigartig sind:</span><span class="sxs-lookup"><span data-stu-id="432be-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="432be-119">Der Kunden Inhalt Ihrer Organisation wird logisch von Kundeninhalten in den kommerziellen Office 365-Diensten von Microsoft getrennt.</span><span class="sxs-lookup"><span data-stu-id="432be-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="432be-120">Der Kunden Inhalt Ihrer Organisation wird in den Vereinigten Staaten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="432be-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="432be-121">Der Zugriff auf die Kunden Inhalte Ihrer Organisation ist auf geschirmte Microsoft-Mitarbeiter beschränkt.</span><span class="sxs-lookup"><span data-stu-id="432be-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="432be-122">Office 365 Government-gcc entspricht Zertifizierungen und Akkreditierungen, die für Kunden im öffentlichen Dienst in den USA erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="432be-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="432be-123">Weitere Informationen zum Office 365 Government-gcc-Angebot für US-Government-Kunden finden Sie unter [Office 365 Government-Pläne](https://products.office.com/government/compare-office-365-government-plans), einschließlich der [Anspruchsvoraussetzungen](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="432be-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="432be-124">Die [Office 365 US Government Service Description](https://technet.microsoft.com/library/mt774581.aspx) beschreibt die Vorteile der Plattform, die sich auf die Erfüllung der Compliance-Anforderungen in den USA konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="432be-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="432be-125">Möglicherweise möchten Sie die Tabellen mit Informationen in der Dienstbeschreibung in eine Excel-Arbeitsmappe übertragen und zwei Spalten hinzufügen, die **für meine Organisation y/n relevant** sind und **den Anforderungen meiner Organisation y/n entsprechen**.</span><span class="sxs-lookup"><span data-stu-id="432be-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="432be-126">Sie können diese Liste dann mit ihren Kollegen überprüfen, um zu bestätigen, dass dieser Dienst den Anforderungen Ihrer Organisation entspricht.</span><span class="sxs-lookup"><span data-stu-id="432be-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Ein Symbol mit Entscheidungspunkten](media/audio_conferencing_image7.png) <br/><span data-ttu-id="432be-128">Entscheidungspunkte</span><span class="sxs-lookup"><span data-stu-id="432be-128">Decision points</span></span>|<ul><li><span data-ttu-id="432be-129">Entscheiden Sie, ob Office 365 Government-gcc für Ihre Organisation geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="432be-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="432be-130">Vergewissern Sie sich, dass Ihre Organisation die Berechtigungsanforderungen erfüllt.</span><span class="sxs-lookup"><span data-stu-id="432be-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="432be-131">Office 365 Government-gcc steht nur in den Vereinigten Staaten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="432be-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="432be-132">Kunden außerhalb der US-Regierung können aus einer Reihe von [Office 365 Government-Plänen](https://products.office.com/en/government/compare-office-365-government-plans)wählen.</span><span class="sxs-lookup"><span data-stu-id="432be-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="432be-133">Schritt 2:</span><span class="sxs-lookup"><span data-stu-id="432be-133">Step 2.</span></span> <span data-ttu-id="432be-134">Bewerben für Office 365 Government-gcc</span><span class="sxs-lookup"><span data-stu-id="432be-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="432be-135">Nachdem Sie entschieden haben, dass dieser Dienst für Ihre Organisation richtig ist, starten Sie den Prozess der [Bewerbung für diesen Dienst hier](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="432be-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="432be-136">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="432be-136">Step 3.</span></span> <span data-ttu-id="432be-137">Grundlegendes zu Office 365 Government-gcc-Standardsicherheitseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="432be-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="432be-138">Wir empfehlen, dass Sie sich Zeit nehmen, um Ihre [Administrator-und Sicherheitseinstellungen](enable-features-office-365.md) sorgfältig zu überprüfen, bevor Sie Sie ändern, und die Auswirkungen auf die Kompatibilität berücksichtigen, bevor Sie Änderungen an den Standardsicherheitseinstellungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="432be-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/><span data-ttu-id="432be-140">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="432be-140">Decision point</span></span>|<ul><li><span data-ttu-id="432be-141">Entscheiden Sie, ob Sie die standardmäßigen Sicherheitseinstellungen von Office 365 Government-gcc ändern möchten, um die Auswirkungen von Änderungen, die Sie möglicherweise vornehmen, zunächst zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="432be-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="432be-142">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="432be-142">Step 4.</span></span> <span data-ttu-id="432be-143">Sie wissen, welche Funktionen zurzeit nicht verfügbar oder standardmäßig deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="432be-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="432be-144">Um den Anforderungen unserer Government Cloud-Kunden gerecht zu werden, gibt es einige Unterschiede zwischen Office 365 Government-gcc-und Enterprise-Plänen.</span><span class="sxs-lookup"><span data-stu-id="432be-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="432be-145">Informationen zu den verfügbaren Features finden Sie in der folgenden Tabelle.</span><span class="sxs-lookup"><span data-stu-id="432be-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="432be-146">Microsoft Teams-Dienstbeschreibung</span><span class="sxs-lookup"><span data-stu-id="432be-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="432be-147">Sobald andere Arbeitslasten in der gcc-Cloud vollständig verfügbar sind, werden Sie in Teams verfügbar, wenn alle zusätzlichen Integrationsarbeiten abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="432be-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/><span data-ttu-id="432be-149">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="432be-149">Decision point</span></span>|<ul><li><span data-ttu-id="432be-150">Entscheiden Sie, ob der Featuresatz für Teams die Anforderungen Ihrer Organisation erfüllt.</span><span class="sxs-lookup"><span data-stu-id="432be-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="432be-151">Schritt 5:</span><span class="sxs-lookup"><span data-stu-id="432be-151">Step 5.</span></span> <span data-ttu-id="432be-152">Plan für Governance</span><span class="sxs-lookup"><span data-stu-id="432be-152">Plan for governance</span></span>

<span data-ttu-id="432be-153">Ermitteln Sie Ihre Anforderungen für Governance und wie Sie Sie erfüllen können.</span><span class="sxs-lookup"><span data-stu-id="432be-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="432be-154">Weitere Informationen finden Sie unter [Planen von Governance in Teams](plan-teams-governance.md) .</span><span class="sxs-lookup"><span data-stu-id="432be-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/><span data-ttu-id="432be-156">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="432be-156">Decision point</span></span>|<ul><li><span data-ttu-id="432be-157">Ermitteln und dokumentieren Sie Ihre Governance-Anforderungen, und befolgen Sie die Richtlinien in [Plan for Governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="432be-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="432be-158">Schritt 6:</span><span class="sxs-lookup"><span data-stu-id="432be-158">Step 6.</span></span> <span data-ttu-id="432be-159">Bereitstellen von Teams für die Zusammenarbeit</span><span class="sxs-lookup"><span data-stu-id="432be-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="432be-160">Nachdem Sie die Office 365 Government – gcc installiert haben, befolgen Sie den empfohlenen Bereitstellungspfad, der in [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md)beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="432be-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="432be-161">Stellen Sie sicher, dass Sie sich mit Ihrem Adoptions-, Change Management-und Team-Champion beschäftigen.</span><span class="sxs-lookup"><span data-stu-id="432be-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="432be-162">Sie können auch mit der [Zusammenarbeit](https://www.microsoft.com/fasttrack) oder dem ausgewählten Partner an Bord des Diensts arbeiten.</span><span class="sxs-lookup"><span data-stu-id="432be-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="432be-163">Schritt 7:</span><span class="sxs-lookup"><span data-stu-id="432be-163">Step 7.</span></span> <span data-ttu-id="432be-164">Bereitstellen von Teams für Besprechungen und Sprachanrufe</span><span class="sxs-lookup"><span data-stu-id="432be-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="432be-165">Dies ist auch eine gute Zeit, um Teams für Ihre breitere Interessengruppe zu verwenden, um mit der Planung für das Rollout von Besprechungen und [Cloud-Sprachfeatures](cloud-voice-deployment.md)zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="432be-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

