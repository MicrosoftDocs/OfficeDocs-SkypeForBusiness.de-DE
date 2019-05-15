---
title: Definieren Sie die Benutzeroberfläche für manuell Abrufen eines Standorts in Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planen für mobile Benutzer in einer E9-1-1-Bereitstellung mit Anbietern von SIP-Trunking in Skype für Business Server Enterprise-VoIP.
ms.openlocfilehash: 503d1cb55afcf23809db851751db0b126504e4f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924164"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definieren Sie die Benutzeroberfläche für manuell Abrufen eines Standorts in Skype für Business Server
 
Planen für mobile Benutzer in einer E9-1-1-Bereitstellung mit Anbietern von SIP-Trunking in Skype für Business Server Enterprise-VoIP.
  
Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet. 
  
**Sollten Benutzer werden aufgefordert, die Eingabe eines Standorts, wenn eine nicht automatisch vom Location Information Service bereitgestellt wird?**
  
Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
Sie können die Einstellung **Standort erforderlich** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Lautet die Einstellung „Nein“, wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Lautet die Einstellung „Ja“, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch verwerfen. Mit der Einstellung „Haftungsausschluss“ wird der Benutzer zur Eingabe eines Standorts aufgefordert. Wenn er dann versucht, diese Aufforderung zu verwerfen, wird ein Haftungsausschluss angezeigt. In allen Fällen kann der Benutzer den Client weiterhin verwenden.
    
Wenn ein Benutzer einen Speicherort manuell eingibt, dem Standort zugeordnet ist, die MAC-Adresse des Standardgateways der Client-Netzwerk sowie in Tabellenform pro Benutzer befindet sich auf dem Client gespeichert ist. Wenn der Benutzer an einem Standort, der zuvor gespeicherten zurückgegeben wird, stellt der Skype für Business-Client selbst automatisch zu diesem Speicherort. 
  
> [!NOTE]
> Sie können nur den aktuellen Standort Ihres Clients ändern, aber Sie können auch alle in der Tabelle des lokalen Benutzers gespeicherten Speicherort löschen. 
  

