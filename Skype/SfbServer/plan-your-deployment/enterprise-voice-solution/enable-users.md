---
title: Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der Benutzer, die aktiviert werden sollen und wie Roaming-Benutzer unterstützt werden.
ms.openlocfilehash: 1e714e5296e8176c9052b50a5d4ce4f2c0d6184b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276901"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a><span data-ttu-id="71402-103">Aktivieren von Benutzern für E9-1-1 in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="71402-103">Enable users for E9-1-1 in Skype for Business Server</span></span>
 
<span data-ttu-id="71402-104">Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der Benutzer, die aktiviert werden sollen und wie Roaming-Benutzer unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="71402-104">Decisions necessary for the location policy for an E9-1-1 deployment in Skype for Business Server Enterprise Voice, including which users to enable and how to support roaming users.</span></span>
  
<span data-ttu-id="71402-105">Während der Clientregistrierung verwendet Skype for Business Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-sprachaktivierte Benutzer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="71402-105">During client registration, Skype for Business Server uses a location policy to configure the E9-1-1 properties for Enterprise Voice-enabled users.</span></span> <span data-ttu-id="71402-106">Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="71402-106">This policy contains the settings that define how E9-1-1 is implemented.</span></span> <span data-ttu-id="71402-107">Beispielsweise enthält die Standortrichtlinie Informationen wie die Notrufnummern Zeichenfolge und ob ein Benutzer manuell einen Standort eingeben muss, wenn der standortinformationsdienst nicht automatisch einen Speicherort bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="71402-107">For example, the location policy contains information such as the emergency dial string, and whether or not a user is required to manually enter a location if the Location Information service does not automatically provide one.</span></span> <span data-ttu-id="71402-108">Eine vollständige Definition einer Standortrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype for Business Server](location-policies.md).</span><span class="sxs-lookup"><span data-stu-id="71402-108">For a complete definition of a location policy, see [Plan location policies for Skype for Business Server](location-policies.md).</span></span>
  
<span data-ttu-id="71402-109">Skype for Business Server kann Clients, die auf einem Subnetz basieren, oder Benutzern, die auf einer globalen, pro-Site-oder pro-Benutzer-Richtlinie basieren, eine ortungsrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="71402-109">Skype for Business Server can assign a location policy to clients based on subnet, or to users based on a global, per-site, or per-user policy.</span></span> <span data-ttu-id="71402-110">Damit Sie entscheiden können, wie Sie die Benutzer aktivieren können, sollten Sie zunächst die folgenden Fragen beantworten.</span><span class="sxs-lookup"><span data-stu-id="71402-110">To help decide how you will enable users, you should first answer the following questions.</span></span>
  
 <span data-ttu-id="71402-111">**Beabsichtigen Sie, alle Benutzer zu aktivieren oder die Unterstützung auf bestimmte geografische Bereiche des Unternehmens zu begrenzen?**</span><span class="sxs-lookup"><span data-stu-id="71402-111">**Do you plan to enable all users, or limit support to specific geographic areas of the enterprise?**</span></span>
  
> <span data-ttu-id="71402-112">Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Standortrichtlinie verwenden.</span><span class="sxs-lookup"><span data-stu-id="71402-112">You can assign a location to all users in your enterprise by using a global location policy.</span></span> <span data-ttu-id="71402-113">Wenn Sie jedoch eine Standortrichtlinie einer Skype for Business Server-Netzwerk Website zuweisen und dann Subnetze zur Website hinzufügen, können Sie die E9-1-1-Unterstützung auf ausgewählte Standorte innerhalb des Unternehmens begrenzen und das Routingverhalten von E9-1-1 pro Website angeben.</span><span class="sxs-lookup"><span data-stu-id="71402-113">However, by assigning a location policy to a Skype for Business Server network site and then adding subnets to the site, you can limit E9-1-1 support to selected locations within the enterprise and specify E9-1-1 routing behavior on a per-site basis.</span></span> 
    
 <span data-ttu-id="71402-114">**Beabsichtigen Sie, einzelne Benutzer über eine Benutzerrichtlinie zu aktivieren?**</span><span class="sxs-lookup"><span data-stu-id="71402-114">**Do you plan to enable individual users through a user policy?**</span></span>
  
> <span data-ttu-id="71402-115">Sie können Standortrichtlinien bestimmten Benutzern oder öffentlichen Telefon Kontaktobjekten direkt zuweisen, wenn Sie Ihre E9-1-1-Unterstützung anpassen möchten.</span><span class="sxs-lookup"><span data-stu-id="71402-115">You can assign location policies directly to specific users or common area phone contact objects if you want to customize their E9-1-1 support.</span></span>
    
 <span data-ttu-id="71402-116">**Wenn Clients außerhalb des Netzwerks oder mit einem nicht definierten Subnetz verbunden sind, sollten die Clients weiterhin für E9-1-1 aktiviert sein?**</span><span class="sxs-lookup"><span data-stu-id="71402-116">**When clients roam outside the network or connect from an undefined subnet, should the clients still be enabled for E9-1-1?**</span></span>
  
> <span data-ttu-id="71402-117">Wenn Benutzern eine Global-, Site-oder pro-User-ortungsrichtlinie zugewiesen ist, kann es erforderlich sein, einen Standort manuell in den Client einzugeben, wenn sich der Client nicht in einem definierten Subnetz befindet oder vom standortinformationsdienst kein Standort gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="71402-117">If users are assigned a global, site, or per-user location policy, they can be required to manually enter a location into the client if the client is not located within a defined subnet or no location has been found by the Location Information service.</span></span> <span data-ttu-id="71402-118">Ausführliche Informationen finden Sie unter [Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server](manually-acquiring-a-location.md).</span><span class="sxs-lookup"><span data-stu-id="71402-118">For details, see [Define the user experience for manually acquiring a location in Skype for Business Server](manually-acquiring-a-location.md).</span></span>
    

