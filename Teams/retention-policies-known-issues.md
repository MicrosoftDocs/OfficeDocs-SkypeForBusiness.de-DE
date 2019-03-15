---
title: Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
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
ms.openlocfilehash: e64bcb2959060b8237f06a1986f15a093eb321a2
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641152"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="65f7d-103">Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65f7d-103">Known issues for retention policies in Microsoft Teams</span></span>

<span data-ttu-id="65f7d-104">Im folgenden werden bekannte Probleme für Aufbewahrungsrichtlinien in Teams, die werden nachverfolgt und untersucht.</span><span class="sxs-lookup"><span data-stu-id="65f7d-104">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="65f7d-105">Klicken Sie unter Wählen Sie Teams in der Zeile Teams Channel Nachrichten Speicherort sehen Sie sich, dass Office 365-Gruppen, sind nicht auch Teams.</span><span class="sxs-lookup"><span data-stu-id="65f7d-105">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="65f7d-106">Dieses Problem wird in der Zukunft behoben werden.</span><span class="sxs-lookup"><span data-stu-id="65f7d-106">This will be addressed in the future.</span></span>

- <span data-ttu-id="65f7d-107">Klicken Sie unter Wählen Sie Benutzer in der Zeile des Teams Chat Speicherort möglicherweise Gäste und nicht-Mailbox Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65f7d-107">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="65f7d-108">Aufbewahrungsrichtlinien werden nicht vorgesehen für Gäste festgelegt werden soll, und wir arbeiten, um diese aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="65f7d-108">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="65f7d-109">Lebenszyklus der Exchange-Assistent (ELC) wird täglich ausgeführt, aber es wurde eine SLA von 7 Tage.</span><span class="sxs-lookup"><span data-stu-id="65f7d-109">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="65f7d-110">Daher ist es möglich, dass, wenn Sie eine Aufbewahrungsrichtlinie Teams zum Löschen von Elementen, die älter als 60 Tage haben, diese Elemente für bis zu 67 Tage beibehalten werden konnte.</span><span class="sxs-lookup"><span data-stu-id="65f7d-110">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="65f7d-111">Dies ist eine neue Situation nicht – es gilt das Exchange-Modell.</span><span class="sxs-lookup"><span data-stu-id="65f7d-111">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="65f7d-112">In den meisten Fällen ist natürlich keine Verzögerung.</span><span class="sxs-lookup"><span data-stu-id="65f7d-112">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Entscheidungspunktsymbol](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="65f7d-114">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="65f7d-114">Decision point</span></span>         |<span data-ttu-id="65f7d-p104">Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?</span><span class="sxs-lookup"><span data-stu-id="65f7d-p104">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Symbol für „Nächste Schritte“](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="65f7d-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="65f7d-118">Next steps</span></span>         |<span data-ttu-id="65f7d-119">Dokumentieren der erforderlichen Features für Sicherheit und Compliance.</span><span class="sxs-lookup"><span data-stu-id="65f7d-119">Document your required security and compliance features.</span></span>         |
