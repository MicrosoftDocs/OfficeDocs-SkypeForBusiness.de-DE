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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879307"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Aktivieren von Benutzern für E9-1-1 in Skype für Business Server
 
Erforderlich für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype Entscheidungen für das Business Server Enterprise-VoIP, welche Benutzer aktivieren, einschließlich und wie Benutzer mit wechselnden Arbeitsplätzen unterstützt.
  
Bei der Clientregistrierung verwendet Skype für Business Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP aktivierte Benutzer konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Beispielsweise enthält die Standortrichtlinie Informationen, wie wählen Sie eine Zeichenfolge, und unabhängig davon, ob ein Benutzer erforderlich ist, einen Speicherort manuell eingeben, wenn der Standortinformationen-Dienst nicht automatisch wird eine bereitstellen. Eine vollständige Definition einer ortungsrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype für Business Server](location-policies.md).
  
Skype für Business Server kann Zuweisen einer ortungsrichtlinie von Clients basierend auf Subnetz oder Benutzern basierend auf global, pro Standort oder benutzerbasierte Richtlinie. Um besser entscheiden, wie Sie Benutzer aktiviert werden, sollten Sie zunächst die folgenden Fragen beantworten.
  
 **Möchten Sie alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens?**
  
> Sie können einen Speicherort für alle Benutzer im Unternehmen mithilfe einer globalen ortungsrichtlinie zuweisen. Zuweisen einer Richtlinie Speicherort für eine Skype für Netzwerkstandort Business Server, und klicken Sie dann Hinzufügen von Subnetzen zu der Website, können Sie jedoch E9-1-1-Unterstützung in ausgewählten Speicherorten innerhalb des Unternehmens zu beschränken und Angeben von E9-1-1-Routingverhalten für einzelne pro Website. 
    
 **Planen Sie so aktivieren Sie einzelne Benutzer über eine Benutzerrichtlinie?**
  
> Sie können anhand von Standortrichtlinien direkt auf bestimmte Benutzer oder common Area Phone Contact-Objekte zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.
    
 **Wenn Clients Roaming von außerhalb des Netzwerks oder von einem undefinierten Subnetz verbinden, sollte die Clients weiterhin für E9-1-1 werden aktiviert?**
  
> Wenn Benutzer eine globale zugewiesen sind, Website, oder benutzerbasierte Standortrichtlinie, sie können einen Speicherort manuell in den Client eingeben, wenn der Client kein befinden sich innerhalb eines definierten Subnetzes ist oder kein Standort vom Dienst Standortinformationen gefunden wurde erforderlich sein. Weitere Informationen hierzu finden Sie unter [definieren die Benutzeroberfläche für manuell Abrufen eines Standorts in Skype für Business Server](manually-acquiring-a-location.md).
    

