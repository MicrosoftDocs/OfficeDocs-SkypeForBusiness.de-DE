---
title: Definieren des Benutzererlebnisses für die manuelle Erfassung eines Standorts in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planen für mobile Benutzer in einer E9-1-1-Bereitstellung mit Anbietern von SIP-Trunking in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 6a22883fb5f028288ab3fab0246d6c2b3b693987
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a><span data-ttu-id="b67ab-103">Definieren des Benutzererlebnisses für die manuelle Erfassung eines Standorts in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="b67ab-103">Define the user experience for manually acquiring a location in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b67ab-104">Planen für mobile Benutzer in einer E9-1-1-Bereitstellung mit Anbietern von SIP-Trunking in Skype für Business Server Enterprise-VoIP.</span><span class="sxs-lookup"><span data-stu-id="b67ab-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="b67ab-p101">Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="b67ab-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="b67ab-108">**Sollten Benutzer werden aufgefordert, die Eingabe eines Standorts, wenn eine nicht automatisch vom Location Information Service bereitgestellt wird?**</span><span class="sxs-lookup"><span data-stu-id="b67ab-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="b67ab-109">Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?</span><span class="sxs-lookup"><span data-stu-id="b67ab-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="b67ab-p102">Sie können die Einstellung **Standort erforderlich** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung „Nein“, wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung „Ja“, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung „Haftungsausschluss“ wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn er dann versucht, diese Aufforderung zu verwerfen, wird ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.</span><span class="sxs-lookup"><span data-stu-id="b67ab-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="b67ab-115">Wenn ein Benutzer einen Speicherort manuell eingibt, dem Standort zugeordnet ist, die MAC-Adresse des Standardgateways der Client-Netzwerk sowie in Tabellenform pro Benutzer befindet sich auf dem Client gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="b67ab-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="b67ab-116">Wenn der Benutzer an einem Standort, der zuvor gespeicherten zurückgegeben wird, stellt der Skype für Business-Client selbst automatisch zu diesem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b67ab-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b67ab-117">Sie können nur den aktuellen Standort Ihres Clients ändern, aber Sie können auch alle in der Tabelle des lokalen Benutzers gespeicherten Speicherort löschen.</span><span class="sxs-lookup"><span data-stu-id="b67ab-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

