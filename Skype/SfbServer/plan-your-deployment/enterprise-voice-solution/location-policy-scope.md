---
title: Zuweisen des Gültigkeitsbereichs der Standortrichtlinie in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype Business Server Enterprise-VoIP.
ms.openlocfilehash: 28759d88be1586149b0dd482d934c5bbc89a1853
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881885"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a><span data-ttu-id="76dde-103">Zuweisen des Gültigkeitsbereichs der Standortrichtlinie in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="76dde-103">Assign location policy scope in Skype for Business Server</span></span>
 
<span data-ttu-id="76dde-104">Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="76dde-104">Planning location policies for an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="76dde-105">Wie mit anderen Skype für Business Server-Richtlinien, anhand von Standortrichtlinien auf mehreren Ebenen der Bereich zugewiesen werden können: global, Standort und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="76dde-105">As with other Skype for Business Server policies, location policies can be assigned at multiple scope levels: global, site, and user.</span></span> <span data-ttu-id="76dde-106">Der Umfang der Richtlinien auf Benutzerebene Speicherort verhält sich aber etwas anders als mit anderen Skype für Business Server-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="76dde-106">However, the scope of user-level location policies behaves a bit differently than with other Skype for Business Server policies.</span></span> <span data-ttu-id="76dde-107">Nicht nur anhand von Standortrichtlinien pro Benutzer angewendet werden können an Endpoint-Objekte (wie Benutzer und Common Area Phone Contact-Objekte), sie können auch auf angewendet werden Skype für Business Server-Netzwerk-Sites.</span><span class="sxs-lookup"><span data-stu-id="76dde-107">Not only can per-user location policies be applied to endpoint objects (such as Users and Common Area Phone contact objects), they can also be applied to Skype for Business Server network sites.</span></span> <span data-ttu-id="76dde-108">Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln).</span><span class="sxs-lookup"><span data-stu-id="76dde-108">Network sites are groupings of client subnets associated with a geographical location (but may not necessarily be all subnets in an entire central site or branch site).</span></span> <span data-ttu-id="76dde-109">Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="76dde-109">Any clients connected to the subnets in a network site automatically pick up the location policy assigned to that network site.</span></span> <span data-ttu-id="76dde-110">Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor allen benutzerspezifischen Richtlinieneinstellungen.</span><span class="sxs-lookup"><span data-stu-id="76dde-110">In cases where a user-level location policy is assigned both to a user and to a network site, the network site-based location policy overrides any per-user policy setting.</span></span>
  
<span data-ttu-id="76dde-111">Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="76dde-111">Each network site has a location policy assigned to it, and each policy will have different PSTN Usages, Notification URIs, and Conference URIs values assigned to it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="76dde-112">Dieses spezielle Richtlinienverhalten hat folgenden Grund: Wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, gelten die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon, welchem Pool oder welchem Standort der Benutzer zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="76dde-112">The reason for this special policy scoping behavior is so that when a user homed on a pool at one office site visits another site and has to make an emergency call, the E9-1-1 call routing settings appropriate to that network site will apply no matter what pool or site the user is assigned to.</span></span> 
  

