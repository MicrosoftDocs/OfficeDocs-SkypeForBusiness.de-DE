---
title: Aktivieren von Benutzern für E9-1-1 in Skype für Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Erforderlich für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype Entscheidungen für das Business Server Enterprise-VoIP, welche Benutzer aktivieren, einschließlich und wie Benutzer mit wechselnden Arbeitsplätzen unterstützt.
ms.openlocfilehash: c5dbbc7904313ffc1706615f2aec506032e20074
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "20997194"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Aktivieren von Benutzern für E9-1-1 in Skype für Business Server
 
Erforderlich für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype Entscheidungen für das Business Server Enterprise-VoIP, welche Benutzer aktivieren, einschließlich und wie Benutzer mit wechselnden Arbeitsplätzen unterstützt.
  
Bei der Clientregistrierung verwendet Skype für Business Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP aktivierte Benutzer konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Beispielsweise enthält die Standortrichtlinie Informationen, wie wählen Sie eine Zeichenfolge, und unabhängig davon, ob ein Benutzer erforderlich ist, einen Speicherort manuell eingeben, wenn der Standortinformationen-Dienst nicht automatisch wird eine bereitstellen. Eine vollständige Definition einer ortungsrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype für Business Server](location-policies.md).
  
Skype für Business Server kann Zuweisen einer ortungsrichtlinie von Clients basierend auf Subnetz oder Benutzern basierend auf global, pro Standort oder benutzerbasierte Richtlinie. Beantworten Sie zunächst die folgenden Fragen, bevor Sie sich für eine Methode zum Aktivieren der Benutzer entscheiden.
  
 **Planen Sie die Aktivierung für alle Benutzer oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens beschränkt werden?**
  
> Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Ortungsrichtlinie verwenden. Zuweisen einer Richtlinie Speicherort für eine Skype für Netzwerkstandort Business Server, und klicken Sie dann Hinzufügen von Subnetzen zu der Website, können Sie jedoch E9-1-1-Unterstützung in ausgewählten Speicherorten innerhalb des Unternehmens zu beschränken und Angeben von E9-1-1-Routingverhalten für einzelne pro Website. 
    
 **Planen Sie die Aktivierung einzelner Benutzer über eine Benutzerrichtlinie?**
  
> Sie können bestimmten Benutzern oder Kontaktobjekten von Telefonen in öffentlichen Bereichen direkt Ortungsrichtlinien zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.
    
 **Sollen Clients auch dann für E9-1-1 aktiviert werden, wenn sie sich außerhalb des Netzwerks bewegen oder sich von einem undefinierten Subnetz aus verbinden?**
  
> Wenn Benutzer eine globale zugewiesen sind, Website, oder benutzerbasierte Standortrichtlinie, sie können einen Speicherort manuell in den Client eingeben, wenn der Client kein befinden sich innerhalb eines definierten Subnetzes ist oder kein Standort vom Dienst Standortinformationen gefunden wurde erforderlich sein. Weitere Informationen hierzu finden Sie unter [definieren die Benutzeroberfläche für manuell Abrufen eines Standorts in Skype für Business Server](manually-acquiring-a-location.md).
    

