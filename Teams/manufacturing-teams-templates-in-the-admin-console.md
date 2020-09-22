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
description: Erfahren Sie, wie Sie mithilfe von Teams-Vorlagen Teamstrukturen erstellen, die für die Herstellung benötigt werden, indem Sie mithilfe der Verwaltungskonsole vordefinierte Einstellungen, Kanäle und vorinstallierte apps bereitstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 919bfc1bc3e13985ac90484cd203bf93201babd2
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171029"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="57fcf-103">Verwenden von Teams-Fertigungs Vorlagen in der Admin-Konsole</span><span class="sxs-lookup"><span data-stu-id="57fcf-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="57fcf-104">Mithilfe von Vorlagen für Teams können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="57fcf-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="57fcf-105">In den Teams-Vorlagen gibt es vorgefertigte Definitionen von Teamstrukturen, die auf die Anforderungen der Fertigung zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="57fcf-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="57fcf-106">Sie können die Teams-Vorlagen auch erweitern, um Teams zu erstellen, die auf Ihre spezifischen organisatorischen Anforderungen zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="57fcf-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="57fcf-107">In diesem Artikel werden die einzelnen Teams-Vorlagen vorgestellt, und es wird empfohlen, diese zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="57fcf-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="57fcf-108">Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in ihrer gesamten Produktionsorganisation verantwortlich sind.</span><span class="sxs-lookup"><span data-stu-id="57fcf-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="57fcf-109">Wir gehen davon aus, dass Sie bereits einen Team Dienst in Ihrer Organisation bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="57fcf-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="57fcf-110">Wenn Sie noch keine Teams ausgearbeitet haben, lesen Sie zunächst die [Anleitung zum Rollout von Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="57fcf-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="57fcf-111">Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="57fcf-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="57fcf-112">Qualität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="57fcf-112">Quality and safety</span></span>

<span data-ttu-id="57fcf-113">Zentralisieren Sie die Kommunikation, den Zugriff auf Ressourcen und den Anlagenbetrieb mit einem Produktionsanlagen Team.</span><span class="sxs-lookup"><span data-stu-id="57fcf-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="57fcf-114">Einbeziehen von Richtlinien-und Prozedur Dokumenten, Schulungsvideos, Sicherheitshinweise, schichtübergabe Prozesse.</span><span class="sxs-lookup"><span data-stu-id="57fcf-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="57fcf-115">Basis Vorlagentyp</span><span class="sxs-lookup"><span data-stu-id="57fcf-115">Base template type</span></span>|<span data-ttu-id="57fcf-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="57fcf-116">baseTemplateId</span></span> | <span data-ttu-id="57fcf-117">Eigenschaften, die mit dieser Basisvorlage geliefert werden</span><span class="sxs-lookup"><span data-stu-id="57fcf-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="57fcf-118">Qualität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="57fcf-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="57fcf-119">Kanäle</span><span class="sxs-lookup"><span data-stu-id="57fcf-119">Channels:</span></span> <ul><li><span data-ttu-id="57fcf-120">Allgemein</span><span class="sxs-lookup"><span data-stu-id="57fcf-120">General</span></span><li><span data-ttu-id="57fcf-121">Ankündigungen</span><span class="sxs-lookup"><span data-stu-id="57fcf-121">Announcements</span></span></li><li><span data-ttu-id="57fcf-122">Zeile 1</span><span class="sxs-lookup"><span data-stu-id="57fcf-122">Line 1</span></span></li><li><span data-ttu-id="57fcf-123">Zeile 2</span><span class="sxs-lookup"><span data-stu-id="57fcf-123">Line 2</span></span></li><li><span data-ttu-id="57fcf-124">Zeile 3</span><span class="sxs-lookup"><span data-stu-id="57fcf-124">Line 3</span></span></li><li><span data-ttu-id="57fcf-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="57fcf-125">Safety</span></span></li><li><span data-ttu-id="57fcf-126">Schulungen</span><span class="sxs-lookup"><span data-stu-id="57fcf-126">Training</span></span></li><li><span data-ttu-id="57fcf-127">Wartung</span><span class="sxs-lookup"><span data-stu-id="57fcf-127">Maintenance</span></span></li><li><span data-ttu-id="57fcf-128">Lustige Sachen</span><span class="sxs-lookup"><span data-stu-id="57fcf-128">Fun stuff</span></span></li></ul> <span data-ttu-id="57fcf-129">Apps</span><span class="sxs-lookup"><span data-stu-id="57fcf-129">Apps:</span></span> <ul><li><span data-ttu-id="57fcf-130">Wiki-</span><span class="sxs-lookup"><span data-stu-id="57fcf-130">Wiki</span></span></li></ul>|
||||
