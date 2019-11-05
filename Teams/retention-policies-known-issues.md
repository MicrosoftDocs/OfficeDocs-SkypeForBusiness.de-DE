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
ms.openlocfilehash: 5565409ea2f3dbb83754ced08a78e12283b1601c
ms.sourcegitcommit: 4a22bf77f529cfc2e68a6498a0c4aa9030ee2168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "37968336"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a><span data-ttu-id="00576-103">Bekannte Probleme mit Aufbewahrungsrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="00576-103">Known issues for retention policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="00576-104">Wir unterstützen noch keine Konfiguration für die Aufbewahrung privater Kanal Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="00576-104">We don’t yet support configuration for retention of private channel messages.</span></span> <span data-ttu-id="00576-105">Die Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="00576-105">Retention of files shared in private channels is supported.</span></span>

<span data-ttu-id="00576-106">Im folgenden werden bekannte Probleme bei Aufbewahrungsrichtlinien in Teams aufgeführt, die nachverfolgt und untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="00576-106">The following are known issues for retention policies in Teams that are being tracked and investigated.</span></span>

- <span data-ttu-id="00576-107">Unter "Teams auswählen" in der Zeile "Standort" des Teams "Channel-Nachrichten" werden möglicherweise Office 365-Gruppen angezeigt, die nicht auch Teams sind.</span><span class="sxs-lookup"><span data-stu-id="00576-107">Under Choose Teams in the Teams Channel messages location row, you may see Office 365 Groups that are not also Teams.</span></span> <span data-ttu-id="00576-108">Dies wird in Zukunft behoben.</span><span class="sxs-lookup"><span data-stu-id="00576-108">This will be addressed in the future.</span></span>

- <span data-ttu-id="00576-109">Unter Benutzer in der Zeile Teamchat-Standort auswählen werden möglicherweise Gäste und nicht-Postfachbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="00576-109">Under Choose Users in the Teams Chat location row, you may see guests and non-mailbox users.</span></span> <span data-ttu-id="00576-110">Aufbewahrungsrichtlinien sollen nicht für Gäste eingerichtet werden, und wir arbeiten daran, diese aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="00576-110">Retention policies are not meant to be set for guests, and we are working to remove these from the list.</span></span>

- <span data-ttu-id="00576-111">Exchange-Lebenszyklus-Assistent (ELC) wird täglich ausgeführt, hat aber eine SLA von 7 Tagen.</span><span class="sxs-lookup"><span data-stu-id="00576-111">Exchange Life Cycle assistant (ELC) runs daily, but it has an SLA of 7 days.</span></span> <span data-ttu-id="00576-112">Daher ist es möglich, dass diese Elemente für bis zu 67 Tage beibehalten werden, wenn Sie über eine Aufbewahrungsrichtlinie für Teams verfügen, um Elemente zu löschen, die älter als 60 Tage sind.</span><span class="sxs-lookup"><span data-stu-id="00576-112">As a result, it's possible that, if you have a Teams retention policy to delete items older than 60 days, these items could persist for up to 67 days.</span></span> <span data-ttu-id="00576-113">Dies ist keine neue Situation – Sie folgt dem Exchange-Modell.</span><span class="sxs-lookup"><span data-stu-id="00576-113">This isn't a new situation - it follows the Exchange model.</span></span> <span data-ttu-id="00576-114">In den meisten Fällen gibt es natürlich keine Verzögerung.</span><span class="sxs-lookup"><span data-stu-id="00576-114">Of course, in most cases, there is no delay.</span></span>


| | | |
|---------|---------|---------|
|![Ein Symbol, das einen Entscheidungspunkt darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |<span data-ttu-id="00576-116">Entscheidungspunkt</span><span class="sxs-lookup"><span data-stu-id="00576-116">Decision point</span></span>         |<span data-ttu-id="00576-p105">Welche Sicherheits- und Compliance-Funktionen benötigt Ihre Organisation? Verfügt Ihre Organisation über die erforderlichen Lizenzen, um die geschäftlichen Sicherheits- und Compliance-Anforderungen zu erfüllen?</span><span class="sxs-lookup"><span data-stu-id="00576-p105">What security and compliance features does your organization require? Does your organization have the required licenses to meet Security and Compliance business requirements?</span></span>         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |<span data-ttu-id="00576-120">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="00576-120">Next steps</span></span>         |<span data-ttu-id="00576-121">Dokumentieren Sie die erforderlichen Sicherheits-und Compliance-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="00576-121">Document your required security and compliance features.</span></span>         |
