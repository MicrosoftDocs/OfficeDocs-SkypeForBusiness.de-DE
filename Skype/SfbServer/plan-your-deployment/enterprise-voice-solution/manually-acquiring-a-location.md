---
title: Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planung für Roamingbenutzer in einer E9-1-1-Bereitstellung mit SIP-Trunkinganbietern in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: 8ca43e8d81d16068806c3416687f73c090a3cbae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602380"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server
 
Planung für Roamingbenutzer in einer E9-1-1-Bereitstellung mit SIP-Trunkinganbietern in Skype for Business Server Enterprise-VoIP.
  
Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert, und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet wird. 
  
**Sollten Benutzer aufgefordert werden, einen Standort einzugeben, wenn einer nicht automatisch vom Standortinformationsdienst bereitgestellt wird?**
  
Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
Sie können die Einstellung **"Location Required"** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Wenn Sie diesen Wert auf "Nein" festlegen, wird der Benutzer nicht zur Eingabe eines Speicherorts aufgefordert. Das Festlegen dieses Werts auf "Ja" bedeutet, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird, die Eingabeaufforderung jedoch geschlossen werden kann. Das Festlegen dieses Werts auf "Haftungsausschluss" bedeutet, dass der Benutzer zur Eingabe eines Speicherorts aufgefordert wird und ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin wie gewohnt verwenden.
    
Wenn ein Benutzer manuell einen Standort eingibt, wird der Speicherort der MAC-Adresse des Standardgateways des Clientnetzwerks zugeordnet und in einer benutzerbezogenen Tabelle auf dem Client gespeichert. Wenn der Benutzer an einen zuvor gespeicherten Speicherort zurückkehrt, legt sich der Skype for Business Client automatisch auf diesen Speicherort fest. 
  
> [!NOTE]
> Sie können nur den aktuellen Speicherort Ihres Clients ändern, aber Sie können auch alle Speicherorte löschen, die in der Tabelle des lokalen Benutzers gespeichert sind. 
  

