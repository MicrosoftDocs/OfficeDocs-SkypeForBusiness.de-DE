---
title: Aktivieren von Benutzern für E9-1-1 in Skype für Business Server
ms.reviewer: ''
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Erforderlich für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype Entscheidungen für das Business Server Enterprise-VoIP, welche Benutzer aktivieren, einschließlich und wie Benutzer mit wechselnden Arbeitsplätzen unterstützt.
ms.openlocfilehash: 57a84d18bec0547f1179e62013c9b957afdd2c53
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32206922"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="8ee13-103">Aktivieren von Benutzern für E9-1-1 in Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="8ee13-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="8ee13-104">Erforderlich für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype Entscheidungen für das Business Server Enterprise-VoIP, welche Benutzer aktivieren, einschließlich und wie Benutzer mit wechselnden Arbeitsplätzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8ee13-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="8ee13-105">Bei der Clientregistrierung verwendet Skype für Business Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP aktivierte Benutzer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8ee13-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="8ee13-106">Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8ee13-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="8ee13-107">Beispielsweise enthält die Standortrichtlinie Informationen, wie wählen Sie eine Zeichenfolge, und unabhängig davon, ob ein Benutzer erforderlich ist, einen Speicherort manuell eingeben, wenn der Standortinformationen-Dienst nicht automatisch wird eine bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8ee13-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="8ee13-108">Eine vollständige Definition einer ortungsrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype für Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="8ee13-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="8ee13-109">Skype für Business Server kann Zuweisen einer ortungsrichtlinie von Clients basierend auf Subnetz oder Benutzern basierend auf global, pro Standort oder benutzerbasierte Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="8ee13-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="8ee13-110">Um besser entscheiden, wie Sie Benutzer aktiviert werden, sollten Sie zunächst die folgenden Fragen beantworten.</span><span class="sxs-lookup"><span data-stu-id="8ee13-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="8ee13-111">**Möchten Sie alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens?**</span><span class="sxs-lookup"><span data-stu-id="8ee13-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="8ee13-112">Sie können einen Speicherort für alle Benutzer im Unternehmen mithilfe einer globalen ortungsrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8ee13-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="8ee13-113">Zuweisen einer Richtlinie Speicherort für eine Skype für Netzwerkstandort Business Server, und klicken Sie dann Hinzufügen von Subnetzen zu der Website, können Sie jedoch E9-1-1-Unterstützung in ausgewählten Speicherorten innerhalb des Unternehmens zu beschränken und Angeben von E9-1-1-Routingverhalten für einzelne pro Website.</span><span class="sxs-lookup"><span data-stu-id="8ee13-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="8ee13-114">**Planen Sie so aktivieren Sie einzelne Benutzer über eine Benutzerrichtlinie?**</span><span class="sxs-lookup"><span data-stu-id="8ee13-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="8ee13-115">Sie können anhand von Standortrichtlinien direkt auf bestimmte Benutzer oder common Area Phone Contact-Objekte zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ee13-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="8ee13-116">**Wenn Clients Roaming von außerhalb des Netzwerks oder von einem undefinierten Subnetz verbinden, sollte die Clients weiterhin für E9-1-1 werden aktiviert?**</span><span class="sxs-lookup"><span data-stu-id="8ee13-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="8ee13-117">Wenn Benutzer eine globale zugewiesen sind, Website, oder benutzerbasierte Standortrichtlinie, sie können einen Speicherort manuell in den Client eingeben, wenn der Client kein befinden sich innerhalb eines definierten Subnetzes ist oder kein Standort vom Dienst Standortinformationen gefunden wurde erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="8ee13-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="8ee13-118">Weitere Informationen hierzu finden Sie unter [definieren die Benutzeroberfläche für manuell Abrufen eines Standorts in Skype für Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="8ee13-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

