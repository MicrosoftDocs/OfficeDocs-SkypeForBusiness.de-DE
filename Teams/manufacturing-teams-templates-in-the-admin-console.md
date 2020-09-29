---
title: Erste Schritte mit Teams-Fertigungs Vorlagen in der Admin-Konsole
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Informationen zur Verwendung von. Teams-Vorlagen zum Erstellen von Teamstrukturen, die für Produktionsanforderungen entwickelt wurden, indem Sie mithilfe der Verwaltungskonsole vordefinierte Einstellungen, Kanäle und vorinstallierte apps bereitstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ebbf765373699d07f96d11fff66e9677213bdb8
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294435"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="ad2ff-104">Verwenden von Teams-Fertigungs Vorlagen in der Admin-Konsole</span><span class="sxs-lookup"><span data-stu-id="ad2ff-104">Use Teams manufacturing templates in the admin console</span></span>

<span data-ttu-id="ad2ff-105">Mithilfe von Vorlagen für Teams können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-105">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="ad2ff-106">In den Teams-Vorlagen gibt es vorgefertigte Definitionen von Teamstrukturen, die auf die Anforderungen der Fertigung zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-106">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="ad2ff-107">Sie können die Teams-Vorlagen auch erweitern, um Teams zu erstellen, die auf Ihre spezifischen organisatorischen Anforderungen zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-107">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="ad2ff-108">In diesem Artikel werden die einzelnen Teams-Vorlagen vorgestellt, und es wird empfohlen, diese zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-108">In this article, we introduce each of the Teams templates and recommend how to use them.</span></span>

<span data-ttu-id="ad2ff-109">Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in ihrer gesamten Produktionsorganisation verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-109">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="ad2ff-110">Sie haben den Team-Service bereits in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-110">You've already deployed Teams service in your organization.</span></span> <span data-ttu-id="ad2ff-111">Wenn Sie noch keine Teams ausgearbeitet haben, lesen Sie zunächst die [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="ad2ff-111">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="ad2ff-112">Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="ad2ff-112">To learn more about team templates in general, refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="ad2ff-113">Qualität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad2ff-113">Quality and safety</span></span>

<span data-ttu-id="ad2ff-114">Zentralisieren Sie die Kommunikation, den Zugriff auf Ressourcen und den Anlagenbetrieb mit einem Produktionsanlagen Team.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-114">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="ad2ff-115">Einbeziehen von Richtlinien-und Prozedur Dokumenten, Schulungsvideos, Sicherheitshinweise, schichtübergabe Prozesse.</span><span class="sxs-lookup"><span data-stu-id="ad2ff-115">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="ad2ff-116">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="ad2ff-116">Base template type</span></span>|<span data-ttu-id="ad2ff-117">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="ad2ff-117">baseTemplateId</span></span> | <span data-ttu-id="ad2ff-118">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="ad2ff-118">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="ad2ff-119">Qualität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad2ff-119">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="ad2ff-120">Kanäle</span><span class="sxs-lookup"><span data-stu-id="ad2ff-120">Channels:</span></span> <ul><li><span data-ttu-id="ad2ff-121">Allgemein</span><span class="sxs-lookup"><span data-stu-id="ad2ff-121">General</span></span><li><span data-ttu-id="ad2ff-122">Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="ad2ff-122">Announcements</span></span></li><li><span data-ttu-id="ad2ff-123">Zeile 1</span><span class="sxs-lookup"><span data-stu-id="ad2ff-123">Line 1</span></span></li><li><span data-ttu-id="ad2ff-124">Zeile 2</span><span class="sxs-lookup"><span data-stu-id="ad2ff-124">Line 2</span></span></li><li><span data-ttu-id="ad2ff-125">Zeile 3</span><span class="sxs-lookup"><span data-stu-id="ad2ff-125">Line 3</span></span></li><li><span data-ttu-id="ad2ff-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad2ff-126">Safety</span></span></li><li><span data-ttu-id="ad2ff-127">Schulungen</span><span class="sxs-lookup"><span data-stu-id="ad2ff-127">Training</span></span></li><li><span data-ttu-id="ad2ff-128">Wartung</span><span class="sxs-lookup"><span data-stu-id="ad2ff-128">Maintenance</span></span></li><li><span data-ttu-id="ad2ff-129">Lustige Sachen</span><span class="sxs-lookup"><span data-stu-id="ad2ff-129">Fun stuff</span></span></li></ul> <span data-ttu-id="ad2ff-130">Apps</span><span class="sxs-lookup"><span data-stu-id="ad2ff-130">Apps:</span></span> <ul><li><span data-ttu-id="ad2ff-131">Wiki-</span><span class="sxs-lookup"><span data-stu-id="ad2ff-131">Wiki</span></span></li></ul>|
||||
