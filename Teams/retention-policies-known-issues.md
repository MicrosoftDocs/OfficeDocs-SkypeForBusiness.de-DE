---
title: Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anach
description: Aktuelle Liste bekannter Probleme für Microsoft Teams-Aufbewahrungsrichtlinien.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a7dd5bac7c82814befab66247b1bfa8cf4943f6
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569962"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="c3bd9-103">Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c3bd9-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="c3bd9-104">Im folgenden werden bekannte Probleme bei Aufbewahrungsrichtlinien in Teams aufgeführt, die nachverfolgt und untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="c3bd9-105">Unter "Teams auswählen" in der Zeile "Standort" des Teams "Channel-Nachrichten" werden möglicherweise Office 365-Gruppen angezeigt, die nicht auch Teams sind.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="c3bd9-106">Dies wird in Zukunft behoben.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="c3bd9-107">Unter Benutzer in der Zeile Teamchat-Standort auswählen werden möglicherweise Gäste und nicht-Postfachbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="c3bd9-108">Aufbewahrungsrichtlinien sollen nicht für Gäste eingerichtet werden, und wir arbeiten daran, diese aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="c3bd9-109">Exchange-Lebenszyklus-Assistent (ELC) wird täglich ausgeführt, hat aber eine SLA von 7 Tagen.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="c3bd9-110">Daher ist es möglich, dass diese Elemente für bis zu 67 Tage beibehalten werden, wenn Sie über eine Aufbewahrungsrichtlinie für Teams verfügen, um Elemente zu löschen, die älter als 60 Tage sind.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="c3bd9-111">Dies ist keine neue Situation – Sie folgt dem Exchange-Modell.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="c3bd9-112">In den meisten Fällen gibt es natürlich keine Verzögerung.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="c3bd9-114">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="c3bd9-114">Decision point</span></span>         |<span data-ttu-id="c3bd9-p104">Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?</span><span class="sxs-lookup"><span data-stu-id="c3bd9-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="c3bd9-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c3bd9-118">Next steps</span></span>         |<span data-ttu-id="c3bd9-119">Dokumentieren Sie die erforderlichen Sicherheits-und Compliance-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="c3bd9-119">Document your required security and compliance features.</span></span>         |
