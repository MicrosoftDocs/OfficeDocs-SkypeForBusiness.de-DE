---
title: Behandeln von Problemen mit Gastzugriff in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: corbinm
search.appverid: MET150
description: Hier erhalten Sie Hilfe bei der Problembehandlung und dem Lösen von Problemen mit dem Gastzugriff in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 7e4db423d262f939362400cdec489ca065b5d5c1
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086202"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="ef03d-103">Behandeln von Problemen mit Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ef03d-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

- <span data-ttu-id="ef03d-104">Wenn Sie wissen möchten, ob Ihr Problem bekannt ist, lesen Sie [Support Teams in Ihrer Organisation](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="ef03d-104">To see whether we know about your problem, check out [Support Teams in your organization](Known-issues.md).</span></span>
- <span data-ttu-id="ef03d-105">Wenn Sie nach Support für aktuelle Probleme mit dem Gastzugriff in Teams suchen möchten, wechseln Sie zu [Problembehandlung für Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="ef03d-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="ef03d-106">Gäste sind Benutzer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="ef03d-106">Guests are users outside your organization.</span></span> <span data-ttu-id="ef03d-107">Wenn sich eine Person in Ihrer Organisation befindet (beispielsweise ihre Mitarbeiter, Auftragnehmer oder Agenten vor Ort), können Sie nicht als Gäste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ef03d-107">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="ef03d-108">Das gleiche gilt für Ihre Partner.</span><span class="sxs-lookup"><span data-stu-id="ef03d-108">The same applies to your affiliates.</span></span>
- <span data-ttu-id="ef03d-109">Informationen zu geplanten neuen oder aktualisierten Funktionen für den Gastzugriff finden Sie in der [Microsoft Teams-Roadmap](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="ef03d-109">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="ef03d-110">Teilen Sie uns auf der [Microsoft Teams-UserVoice](https://aka.ms/TeamsUserVoice)-Website Ihre Wünsche mit.</span><span class="sxs-lookup"><span data-stu-id="ef03d-110">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="ef03d-111">Wenn Ihre Gäste Lizenzfehler sehen</span><span class="sxs-lookup"><span data-stu-id="ef03d-111">If your guests are seeing license errors</span></span>

<span data-ttu-id="ef03d-112">Für den Gastzugriff in Microsoft Teams wird Azure Active Directory (Azure AD) Business-to-Business (B2B) und dessen Lizenzierungsmodell genutzt.</span><span class="sxs-lookup"><span data-stu-id="ef03d-112">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="ef03d-113">Der Gastzugang ist in allen Abonnements von Microsoft 365 Business Standard, Office 365 Enterprise und Office 365 Education enthalten.</span><span class="sxs-lookup"><span data-stu-id="ef03d-113">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="ef03d-114">Eine zusätzliche Microsoft 365- oder Office 365-Lizenz ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ef03d-114">No additional Microsoft 365 or Office 365 license is necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="ef03d-115">Teams müssen für den Home-Mandanten eines Gasts aktiviert sein, damit Gäste sich anmelden und Teams als Gast für einen anderen (Ressourcen-) Mandanten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ef03d-115">Teams must be enabled on a guest's home tenant for guests to be able to sign in and use Teams as a guest on another (resource) tenant.</span></span>

<span data-ttu-id="ef03d-116">Wenn Lizenzierungsfehler angezeigt werden, lesen Sie die [Azure Active Directory B2B-Lizenzierungs Anleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , um die Lizenzierungsanforderungen zu ermitteln, die Ihren Anforderungen für den Gastzugriff in Ihrer Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ef03d-116">If you're seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="ef03d-117">Gastlizenzen werden für die einladende Organisation gezählt.</span><span class="sxs-lookup"><span data-stu-id="ef03d-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="ef03d-118">Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.</span><span class="sxs-lookup"><span data-stu-id="ef03d-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="ef03d-119">Lizenzen werden für Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste aus einer anderen Microsoft 365-oder Office 365-Organisation stammen oder Ihre persönlichen e-Mail-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef03d-119">Licenses are counted against your organization whether the invited guests come from another Microsoft 365 or Office 365 organization or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="ef03d-120">Unterstützung von B2B-Benutzertypen</span><span class="sxs-lookup"><span data-stu-id="ef03d-120">Support for B2B User types</span></span>
<span data-ttu-id="ef03d-121">Derzeit unterstützt Teams nur die Gastbenutzer vom Typ "Zustand 1" und "Zustand 2" [gemäß der Definition durch Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="ef03d-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef03d-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ef03d-122">Related topics</span></span>

[<span data-ttu-id="ef03d-123">Gastzugriff in Teams</span><span class="sxs-lookup"><span data-stu-id="ef03d-123">Guest access in Teams</span></span>](guest-access.md)


[<span data-ttu-id="ef03d-124">Teams-Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="ef03d-124">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)