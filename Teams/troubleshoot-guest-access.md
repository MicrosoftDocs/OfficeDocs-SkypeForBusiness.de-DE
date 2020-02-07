---
title: Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams
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
description: Erhalten Sie Hilfe bei der Problembehandlung und Beheben von Problemen mit dem Gastzugriff in Microsoft Teams.
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0c0f65f7026e6c083d9230551d689f0dd19d6b0d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837635"
---
<a name="troubleshoot-problems-with-guest-access-in-microsoft-teams"></a><span data-ttu-id="c3f78-103">Behandeln von Problemen mit dem Gastzugriff in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3f78-103">Troubleshoot problems with guest access in Microsoft Teams</span></span>
======================================================

> [!IMPORTANT]
> <span data-ttu-id="c3f78-104">Möglicherweise müssen Sie bis zu 24 Stunden warten, bis Ihre Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c3f78-104">You may have to wait up to 24 hours for your changes to take effect.</span></span> 


- <span data-ttu-id="c3f78-105">Wenn Sie nach aktuellen Supportproblemen mit Gastzugriff in Teams suchen möchten, wechseln Sie zur [Problembehandlung für Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span><span class="sxs-lookup"><span data-stu-id="c3f78-105">To check for current support issues with guest access in Teams, go to [Teams Troubleshooting](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/).</span></span>
- <span data-ttu-id="c3f78-106">Wenn Sie wissen möchten, ob Ihr Problem bekannt ist, lesen Sie [bekannte Probleme für Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c3f78-106">To see whether we know about your problem, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="c3f78-107">Gäste sind Benutzer außerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c3f78-107">Guests are users outside your organization.</span></span> <span data-ttu-id="c3f78-108">Wenn sich eine Person in Ihrer Organisation befindet (einschließlich ihrer Mitarbeiter, vor-Ort-Auftragnehmer oder vor-Ort-Agents), können Sie nicht als Gäste hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c3f78-108">If someone is inside your organization (including your employees, onsite contractors, or onsite agents), they can't be added as guests.</span></span> <span data-ttu-id="c3f78-109">Das gleiche gilt für Ihre Partner.</span><span class="sxs-lookup"><span data-stu-id="c3f78-109">The same applies to your affiliates.</span></span>
- <span data-ttu-id="c3f78-110">Informieren Sie sich über die bevorstehenden neuen oder aktualisierten Features für den Gastzugriff in der [Roadmap für Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="c3f78-110">Find out about upcoming new or updated guest access features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="c3f78-111">Teilen Sie uns mit, was Sie in [Teams UserVoice](https://aka.ms/TeamsUserVoice)möchten.</span><span class="sxs-lookup"><span data-stu-id="c3f78-111">Tell us what you want in [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>

## <a name="if-your-guests-are-seeing-license-errors"></a><span data-ttu-id="c3f78-112">Wenn Ihre Gäste Lizenzfehler sehen</span><span class="sxs-lookup"><span data-stu-id="c3f78-112">If your guests are seeing license errors</span></span>

<span data-ttu-id="c3f78-113">Der Gastzugriff in Teams verwendet Azure Active Directory (Azure AD) Business to Business (B2B) und sein Lizenzierungsmodell.</span><span class="sxs-lookup"><span data-stu-id="c3f78-113">Guest access in Teams uses Azure Active Directory (Azure AD) Business to Business (B2B) and its licensing model.</span></span> <span data-ttu-id="c3f78-114">Gastzugriff ist in allen Office 365 Business Premium-, Office 365 Enterprise- und Office 365 Education-Abonnements enthalten.</span><span class="sxs-lookup"><span data-stu-id="c3f78-114">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="c3f78-115">Eine zusätzliche Office 365-Lizenz ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c3f78-115">No additional Office 365 license is necessary.</span></span>

<span data-ttu-id="c3f78-116">Wenn Lizenzierungsfehler angezeigt werden, lesen Sie die [Azure Active Directory B2B-Lizenzierungs Anleitung](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) , um die Lizenzierungsanforderungen zu ermitteln, die Ihren Anforderungen für den Gastzugriff in Ihrer Organisation entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c3f78-116">If you’re seeing licensing errors, make sure to read the [Azure Active Directory B2B licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance) to determine licensing requirements to meet your needs for guest access in your organization.</span></span>


- <span data-ttu-id="c3f78-117">Gastlizenzen werden für die einladende Organisation gezählt.</span><span class="sxs-lookup"><span data-stu-id="c3f78-117">Guest licenses are counted against the inviting organization.</span></span> <span data-ttu-id="c3f78-118">Denken Sie daran, wenn Sie die Anzahl der benötigten Lizenzen berechnen.</span><span class="sxs-lookup"><span data-stu-id="c3f78-118">Consider this when you calculate the number of licenses you need.</span></span>
- <span data-ttu-id="c3f78-119">Lizenzen werden gegen Ihre Organisation gezählt, unabhängig davon, ob die eingeladenen Gäste von einem anderen Office 365-Mandanten stammen oder Ihre persönlichen e-Mail-Adressen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3f78-119">Licenses are counted against your organization whether the invited guests come from another Office 365 tenant or are using their personal email addresses.</span></span>

## <a name="support-for-b2b-user-types"></a><span data-ttu-id="c3f78-120">Unterstützung für B2B-Benutzertypen</span><span class="sxs-lookup"><span data-stu-id="c3f78-120">Support for B2B User types</span></span>
<span data-ttu-id="c3f78-121">Zurzeit unterstützt Teams nur die Typen von Gastbenutzern des Status 1 und des Status 2 [, wie Sie von Azure B2B definiert werden](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span><span class="sxs-lookup"><span data-stu-id="c3f78-121">Currently Teams only has support for State 1 and State 2 types of Guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c3f78-122">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c3f78-122">Related topics</span></span>

[<span data-ttu-id="c3f78-123">Gastzugriff in Teams</span><span class="sxs-lookup"><span data-stu-id="c3f78-123">Guest access in Teams</span></span>](guest-access.md)


