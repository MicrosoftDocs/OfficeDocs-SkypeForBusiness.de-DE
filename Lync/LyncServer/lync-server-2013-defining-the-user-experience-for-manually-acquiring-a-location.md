---
title: Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5be01e4cf35d51b457cd575ef31254475bfda5bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832696"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Definieren der Benutzeroberfläche für den manuellen Erwerb eines Speicherorts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet.

  - **Sollten Benutzer zur Eingabe eines Speicherorts aufgefordert werden, wenn Sie nicht automatisch vom standortinformationsdienst bereitgestellt werden?**  
    Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
    Sie können die Einstellung **Standort erforderlich** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung „Nein“, wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung „Ja“, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung „Haftungsausschluss“ wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn er dann versucht, diese Aufforderung zu verwerfen, wird ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.

Wenn ein Benutzer einen Standort manuell eingibt, wird dieser basierend auf der MAC-Adresse des Standardgateways des Clientnetzwerks zugeordnet und in einer benutzerspezifischen Tabelle auf dem Client gespeichert. Wenn der Benutzer zu einem zuvor gespeicherten Speicherort zurückkehrt, legt sich der lync-Client automatisch an diesen Speicherort fest.

<div>


> [!NOTE]
> Sie können nur den aktuellen Standort Ihres Clients ändern. Darüber hinaus können Sie jeden Standort, der in der Tabelle des lokalen Benutzers gespeichert ist, löschen.



</div>

</div>

<span> </span>

</div>

</div>

</div>

