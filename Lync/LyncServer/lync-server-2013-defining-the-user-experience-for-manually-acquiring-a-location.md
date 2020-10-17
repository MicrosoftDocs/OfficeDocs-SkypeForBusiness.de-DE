---
title: Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fa9c7242351417c4ea82ed7ce6183963bc9730e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504472"
---
# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="5afd3-102">Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5afd3-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5afd3-103">_**Letztes Änderungsstand des Themas:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="5afd3-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="5afd3-p101">Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert, und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="5afd3-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="5afd3-107">**Sollten Benutzer zur Eingabe eines Speicherorts aufgefordert werden, wenn dieser nicht automatisch vom Standortinformationsdienst bereitgestellt wird?**</span><span class="sxs-lookup"><span data-stu-id="5afd3-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="5afd3-108">Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?</span><span class="sxs-lookup"><span data-stu-id="5afd3-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="5afd3-109">Sie können die Einstellung **Standort erforderlich** in der ortungsrichtlinie konfigurieren, um das Clientverhalten zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5afd3-109">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="5afd3-110">Wenn Sie diesen Wert auf "Nein" festlegen, wird der Benutzer nicht zur Eingabe eines Speicherorts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="5afd3-110">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="5afd3-111">Wenn Sie diesen Wert auf Yes festlegen, bedeutet dies, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird, die Eingabeaufforderung jedoch entlassen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5afd3-111">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="5afd3-112">Wenn Sie diesen Wert auf Haftungsausschluss festlegen, bedeutet dies, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird und ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5afd3-112">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="5afd3-113">In allen Fällen kann der Benutzer den Client weiterhin wie gewohnt verwenden.</span><span class="sxs-lookup"><span data-stu-id="5afd3-113">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="5afd3-p103">Wenn ein Benutzer manuell einen Standort eingibt, wird dieser basierend auf der MAC-Adresse des Standardgateways für das Netzwerk des Clients zugeordnet und in einer benutzerspezifischen Tabelle auf dem Client gespeichert. Kehrt der Benutzer an einen zuvor gespeicherten Standort zurück, wird der Lync-Client automatisch auf diesen Standort eingestellt.</span><span class="sxs-lookup"><span data-stu-id="5afd3-p103">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client. When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5afd3-116">Sie können nur den aktuellen Standort Ihres Clients ändern. Darüber hinaus können Sie jeden Standort, der in der Tabelle des lokalen Benutzers gespeichert ist, löschen.</span><span class="sxs-lookup"><span data-stu-id="5afd3-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

