---
title: Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der zu aktivierenden Benutzer und der Unterstützung von Roamingbenutzern.
ms.openlocfilehash: 877e813df4d1ace9084586702836db96dbb149a5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392427"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
 
Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der zu aktivierenden Benutzer und der Unterstützung von Roamingbenutzern.
  
Während der Clientregistrierung verwendet Skype for Business Server eine Standortrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP aktivierte Benutzer zu konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Die Standortrichtlinie enthält beispielsweise Informationen wie die Notrufwählzeichenfolge und ob ein Benutzer manuell einen Standort eingeben muss, wenn der Standortinformationsdienst diesen nicht automatisch bereitstellt. Eine vollständige Definition einer Standortrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype for Business Server](location-policies.md).
  
Skype for Business Server können Clients basierend auf subnetzbasierten Oder Benutzern basierend auf einer globalen, standort- oder benutzerbasierten Richtlinie eine Standortrichtlinie zuweisen. Beantworten Sie zunächst die folgenden Fragen, bevor Sie sich für eine Methode zum Aktivieren der Benutzer für E9-1-1 entscheiden.
  
 **Planen Sie die Aktivierung für alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens beschränkt werden?**
  
> Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Ortungsrichtlinie verwenden. Durch Zuweisen einer Standortrichtlinie zu einem Skype for Business Server Netzwerkstandort und anschließendes Hinzufügen von Subnetzen zum Standort können Sie jedoch die E9-1-1-Unterstützung auf ausgewählte Standorte innerhalb des Unternehmens beschränken und das E9-1-1-Routingverhalten pro Standort angeben. 
    
 **Planen Sie die Aktivierung einzelner Benutzer über eine Benutzerrichtlinie?**
  
> Sie können bestimmten Benutzern oder Kontaktobjekten von Telefonen in öffentlichen Bereichen direkt Ortungsrichtlinien zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.
    
 **Sollen Clients auch dann für E9-1-1 aktiviert werden, wenn sie sich außerhalb des Netzwerks bewegen oder sich von einem undefinierten Subnetz aus verbinden?**
  
> Wenn Benutzern eine globale Standort-, Standort- oder Standortrichtlinie pro Benutzer zugewiesen wird, kann es erforderlich sein, manuell einen Standort in den Client einzugeben, wenn sich der Client nicht in einem definierten Subnetz befindet oder kein Standort vom Standortinformationsdienst gefunden wurde. Ausführliche Informationen finden [Sie unter "Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server](manually-acquiring-a-location.md)".
    

