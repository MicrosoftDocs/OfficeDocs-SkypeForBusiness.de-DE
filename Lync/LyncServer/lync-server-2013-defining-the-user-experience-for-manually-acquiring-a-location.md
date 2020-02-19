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
ms.openlocfilehash: 20bd88f9c9f619e67c9aec8f6b0111320fa3ed2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a>Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert, und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet wird.

  - **Sollten Benutzer zur Eingabe eines Speicherorts aufgefordert werden, wenn dieser nicht automatisch vom Standortinformationsdienst bereitgestellt wird?**  
    Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
    Sie können die Einstellung **Standort erforderlich** in der ortungsrichtlinie konfigurieren, um das Clientverhalten zu definieren. Wenn Sie diesen Wert auf "Nein" festlegen, wird der Benutzer nicht zur Eingabe eines Speicherorts aufgefordert. Wenn Sie diesen Wert auf Yes festlegen, bedeutet dies, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird, die Eingabeaufforderung jedoch entlassen werden kann. Wenn Sie diesen Wert auf Haftungsausschluss festlegen, bedeutet dies, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird und ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin wie gewohnt verwenden.

Wenn ein Benutzer manuell einen Standort eingibt, wird dieser basierend auf der MAC-Adresse des Standardgateways für das Netzwerk des Clients zugeordnet und in einer benutzerspezifischen Tabelle auf dem Client gespeichert. Kehrt der Benutzer an einen zuvor gespeicherten Standort zurück, wird der Lync-Client automatisch auf diesen Standort eingestellt.

<div>


> [!NOTE]
> Sie können nur den aktuellen Standort Ihres Clients ändern. Darüber hinaus können Sie jeden Standort, der in der Tabelle des lokalen Benutzers gespeichert ist, löschen.



</div>

</div>

<span> </span>

</div>

</div>

</div>

