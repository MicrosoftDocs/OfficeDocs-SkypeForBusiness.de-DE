---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786019"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a><span data-ttu-id="dba1d-103">Contoso-Fallstudie: Upgradeplan für Teams</span><span class="sxs-lookup"><span data-stu-id="dba1d-103">Contoso case study: Teams upgrade plan</span></span>

<span data-ttu-id="dba1d-104">Bei der Entscheidung, von Skype for Business zu Teams zu migrieren, wollte Contoso eine einfache Übergangserfahrung für Endbenutzer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dba1d-104">In the decision to migrate from Skype for Business to Teams, Contoso wanted to provide an easy transition experience for end users.</span></span> <span data-ttu-id="dba1d-105">Anstatt alle Personen gleichzeitig zu Teams zu wechseln, haben Sie sich entschlossen, die Hybrid Konnektivität einzurichten, und die überlappenden Funktionen verwenden, um Benutzer in Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="dba1d-105">Instead of switching everyone to Teams at the same time, they decided to set up hybrid connectivity, and use the overlapping capabilities method to move users to Teams.</span></span> <span data-ttu-id="dba1d-106">Dies ermöglichte Benutzern in Teams und Skype for Business lokal, Anwesenheitsinformationen freizugeben und zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="dba1d-106">This allowed users in Teams and Skype for Business on-premises to share presence and communicate.</span></span> <span data-ttu-id="dba1d-107">Als Benutzer in das Pilotprojekt für das Telefon System eintraten, wurden Sie in den Modus nur für Teams verschoben.</span><span class="sxs-lookup"><span data-stu-id="dba1d-107">As users entered the pilot for Phone System, they were moved to Teams Only mode.</span></span>

<span data-ttu-id="dba1d-108">Wenn Sie grundlegende Konzepte zu Upgrades, Methoden und Modi verstehen möchten, lesen Sie die folgenden Artikel:</span><span class="sxs-lookup"><span data-stu-id="dba1d-108">To understand fundamental concepts about upgrade, methods, and modes, Contoso read the following articles:</span></span>

- [<span data-ttu-id="dba1d-109">Erste Schritte mit dem Upgrade von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dba1d-109">Getting started with your Microsoft Teams upgrade</span></span>](upgrade-start-here.md)
- [<span data-ttu-id="dba1d-110">Upgrade von Skype for Business auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dba1d-110">Upgrade from Skype for Business to Teams</span></span>](upgrade-to-teams-on-prem-overview.md) 
- [<span data-ttu-id="dba1d-111">Leitfaden zur Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="dba1d-111">Migration and interoperability guidance</span></span>](migration-interop-guidance-for-teams-with-skype.md)
 
<span data-ttu-id="dba1d-112">Contoso nahm auch an der Ignite 2019-Sitzung Teil [, in der Sie Ihren Weg von Skype for Business zu Teams entwerfen](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="dba1d-112">Contoso also attended the Ignite 2019 session [Designing your path from Skype for Business to Teams](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions).</span></span> <span data-ttu-id="dba1d-113">Contoso hat Folgendes gelernt:</span><span class="sxs-lookup"><span data-stu-id="dba1d-113">Contoso learned about:</span></span>

- <span data-ttu-id="dba1d-114">Grundlegende Konzepte wie Interoperabilität, Verbund und Upgrade-Verhalten</span><span class="sxs-lookup"><span data-stu-id="dba1d-114">Fundamental concepts such as interoperability, federation, and upgrade behavior</span></span> 

- <span data-ttu-id="dba1d-115">Koexistenzmodus und-Verwaltung auf Grundlage von TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="dba1d-115">Coexistence modes and management based on TeamsUpgradePolicy</span></span> 

- <span data-ttu-id="dba1d-116">Endbenutzererfahrung für:</span><span class="sxs-lookup"><span data-stu-id="dba1d-116">End user experience for:</span></span> 

  - <span data-ttu-id="dba1d-117">Chat und Anrufe</span><span class="sxs-lookup"><span data-stu-id="dba1d-117">Chat and Calling</span></span> 

  - <span data-ttu-id="dba1d-118">Besprechungsplanung</span><span class="sxs-lookup"><span data-stu-id="dba1d-118">Meeting scheduling</span></span> 

  - <span data-ttu-id="dba1d-119">Verfügbarkeit der Zusammenarbeits Funktionalität in Microsoft Teams-Clients</span><span class="sxs-lookup"><span data-stu-id="dba1d-119">Availability of collaboration functionality in Teams clients</span></span> 

<span data-ttu-id="dba1d-120">Zum Planen und Konfigurieren von Hybrid Konnektivität ist der erste Schritt beim Verschieben Ihrer lokalen Umgebung in die Cloud, der Contoso Read [Plan-Hybrid Konnektivität](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) und die [Konfiguration der Hybrid Konnektivität](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) , um zu verstehen, wie:</span><span class="sxs-lookup"><span data-stu-id="dba1d-120">To plan and configure hybrid connectivity, the first step in moving their on-premises environment to the cloud, Contoso read [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) and [Configure hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) to understand how to:</span></span> 

  - <span data-ttu-id="dba1d-121">Konfigurieren Sie Ihren lokalen Umgebungs Dienst für die Föderation mit Office 365.</span><span class="sxs-lookup"><span data-stu-id="dba1d-121">Configure their on-premises environment service to federate with Office 365.</span></span> 

  - <span data-ttu-id="dba1d-122">Konfigurieren Ihrer lokalen Umgebung, um Office 365 zu Vertrauen und den freigegebenen SIP-Adressraum mit Office 365 zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="dba1d-122">Configure their on-premises environment to trust Office 365 and enable shared SIP address space with Office 365</span></span> 

  - <span data-ttu-id="dba1d-123">Aktivieren Sie den freigegebenen SIP-Adressraum in Ihrem Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="dba1d-123">Enable shared SIP address space in their Office 365 tenant.</span></span>

  - <span data-ttu-id="dba1d-124">Verwenden Sie den Modus "Inseln" während des technischen Pilotprojekts.</span><span class="sxs-lookup"><span data-stu-id="dba1d-124">Use Islands mode during the technical pilot.</span></span>

  - <span data-ttu-id="dba1d-125">Wechseln Sie Benutzer in den TeamsOnly-Modus, nachdem der Benutzer für das Telefon System aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="dba1d-125">Switch users to TeamsOnly mode once the user is enabled for Phone System.</span></span> <span data-ttu-id="dba1d-126">Der TeamsOnly-Modus ist für den Anruf Plan und das direkte Routing erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dba1d-126">TeamsOnly mode is required for  Calling Plan and Direct Routing.</span></span> 
