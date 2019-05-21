---
title: Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planen der Roaming-Benutzer in einer E9-1-1-Bereitstellung unter Verwendung von SIP-Trunking-Anbietern in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 221c123c9630996d487644d0f5358b95d65fe1a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276719"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server
 
Planen der Roaming-Benutzer in einer E9-1-1-Bereitstellung unter Verwendung von SIP-Trunking-Anbietern in Skype for Business Server Enterprise-VoIP
  
Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet. 
  
**Sollten Benutzer zur Eingabe eines Speicherorts aufgefordert werden, wenn Sie nicht automatisch vom standortinformationsdienst bereitgestellt werden?**
  
Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
Sie können die Einstellung **Standort erforderlich** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung „Nein“, wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung „Ja“, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung „Haftungsausschluss“ wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn er dann versucht, diese Aufforderung zu verwerfen, wird ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
Wenn ein Benutzer einen Speicherort manuell eingibt, wird der Speicherort der Mac-Adresse des Standardgateways des Clientnetzwerks zugeordnet und in einer pro Benutzer-Tabelle auf dem Client gespeichert. Wenn der Benutzer zu einem zuvor gespeicherten Speicherort zurückkehrt, setzt sich der Skype for Business-Client automatisch an diesen Standort. 
  
> [!NOTE]
> Sie können nur die aktuelle Position des Clients ändern, aber Sie können auch alle Speicherorte löschen, die in der Tabelle des lokalen Benutzers gespeichert sind. 
  

