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
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planen von Roamingbenutzern in einer E9-1-1-Bereitstellung mithilfe von SIP-Trunking-Anbietern, in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: dd43d78b4c139b4fb30a0b4ba379d96150314332
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825425"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server
 
Planen von Roamingbenutzern in einer E9-1-1-Bereitstellung mithilfe von SIP-Trunking-Anbietern, in Skype for Business Server Enterprise-VoIP.
  
Wenn ein Client sich außerhalb des Netzwerks oder in einem nicht definierten Subnetz befindet, kann der Benutzer manuell einen Standort eingeben. Bei einem Notruf wird der Anruf jedoch zuerst an ein nationales/regionales Telefoncenter für Notrufe (Emergency Call Response Center, ECRC) und erst anschließend an eine Rettungsleitstelle (Public Safety Answering Point, PSAP) weitergeleitet. Der Anrufer wird vom ECRC zur Angabe seines Standorts aufgefordert, und anschließend wird der Notruf anhand der bereitgestellten Informationen an die entsprechende Rettungsleitstelle weitergeleitet wird. 
  
**Sollen Benutzer zur Eingabe eines Standorts aufgefordert werden, wenn dieser nicht automatisch vom Standortinformationsdienst bereitgestellt wird?**
  
Wenn ein Client sich beispielsweise in einem nicht definierten Subnetz, zu Hause, in einem Hotel oder an einem anderen Standort außerhalb des Netzwerks befindet, sollte der Benutzer zur Eingabe eines Standorts aufgefordert werden?
    
Sie können die Einstellung **"Location Required"** in der Standortrichtlinie konfigurieren, um das Clientverhalten zu definieren. Wenn Sie diesen Wert auf "Nein" festlegen, wird der Benutzer nicht zur Eingabe eines Standorts aufgefordert. Wenn Sie diesen Wert auf "Ja" festlegen, wird der Benutzer zur Eingabe eines Standorts aufgefordert, kann die Eingabeaufforderung jedoch schließen. Das Festlegen dieses Werts auf "Haftungsausschluss" bedeutet, dass der Benutzer zur Eingabe eines Standorts aufgefordert wird und ein Haftungsausschluss angezeigt wird, wenn er versucht, die Eingabeaufforderung zu schließen. In allen Fällen kann der Benutzer den Client weiterhin wie gewohnt verwenden.
    
Wenn ein Benutzer manuell einen Standort eintritt, wird der Standort der MAC-Adresse des Standardgateways des Clientnetzwerks zugeordnet und in einer Benutzertabelle gespeichert, die sich auf dem Client befindet. Wenn der Benutzer zu einem zuvor gespeicherten Speicherort zurückkehrt, legt sich der Skype for Business-Client automatisch auf diesen Speicherort fest. 
  
> [!NOTE]
> Sie können nur den aktuellen Speicherort Ihres Clients ändern, aber Sie können auch jeden beliebigen Speicherort löschen, der in der Tabelle des lokalen Benutzers gespeichert ist. 
  

