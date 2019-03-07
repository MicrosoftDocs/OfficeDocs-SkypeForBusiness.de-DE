---
title: Bekannte Probleme beim Aufbewahrungsrichtlinien in Microsoft-Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Aktuelle Liste bekannter Probleme bei Microsoft-Teams, Aufbewahrungsrichtlinien.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 411ef4bf12d55af0b913443219a00f3f56c7eba2
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461188"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="7a5f6-103">Bekannte Probleme beim Aufbewahrungsrichtlinien in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="7a5f6-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="7a5f6-104">Im folgenden werden bekannte Probleme für Aufbewahrungsrichtlinien in Teams, die werden nachverfolgt und untersucht.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="7a5f6-105">Klicken Sie unter Wählen Sie Teams in der Zeile Teams Channel Nachrichten Speicherort sehen Sie sich, dass Office 365-Gruppen, sind nicht auch Teams.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="7a5f6-106">Dieses Problem wird in der Zukunft behoben werden.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="7a5f6-107">Klicken Sie unter Wählen Sie Benutzer in der Zeile des Teams Chat Speicherort möglicherweise Gäste und nicht-Mailbox Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="7a5f6-108">Aufbewahrungsrichtlinien werden nicht vorgesehen für Gäste festgelegt werden soll, und wir arbeiten, um diese aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="7a5f6-109">Lebenszyklus der Exchange-Assistent (ELC) wird täglich ausgeführt, aber es wurde eine SLA von 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="7a5f6-110">Daher ist es möglich, dass, wenn Sie eine Aufbewahrungsrichtlinie Teams zum Löschen von Elementen, die älter als 60 Tage haben, diese Elemente für bis zu 67 Tage beibehalten werden konnte.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="7a5f6-111">Dies ist eine neue Situation nicht – es gilt das Exchange-Modell.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="7a5f6-112">In den meisten Fällen ist natürlich keine Verzögerung.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="7a5f6-114">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="7a5f6-114">Decision point</span></span>         |<span data-ttu-id="7a5f6-p104">Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?</span><span class="sxs-lookup"><span data-stu-id="7a5f6-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="7a5f6-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7a5f6-118">Next steps</span></span>         |<span data-ttu-id="7a5f6-119">Dokumentieren der erforderlichen Features für Sicherheit und Compliance.</span><span class="sxs-lookup"><span data-stu-id="7a5f6-119">Document your required security and compliance features.</span></span>         |
