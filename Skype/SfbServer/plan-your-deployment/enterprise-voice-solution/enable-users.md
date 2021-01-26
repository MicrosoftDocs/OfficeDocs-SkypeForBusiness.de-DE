---
title: Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
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
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der zu aktivierenden Benutzer und der Unterstützung von Roamingbenutzern.
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825745"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
 
Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der zu aktivierenden Benutzer und der Unterstützung von Roamingbenutzern.
  
Während der Clientregistrierung verwendet Skype for Business Server eine Standortrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-VoIP zu konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Die Standortrichtlinie enthält z. B. Informationen wie die Notrufwählzeichenfolge und ob ein Benutzer manuell einen Standort eingeben muss, wenn der Standortinformationsdienst nicht automatisch einen standortinformationendienst zur Verfügung stellt. Eine vollständige Definition einer Standortrichtlinie finden Sie unter ["Planen von Standortrichtlinien für Skype for Business Server".](location-policies.md)
  
Skype for Business Server kann Clients basierend auf dem Subnetz oder Benutzern basierend auf einer globalen, standortbezogenen oder benutzerbasierten Richtlinie eine Standortrichtlinie zuweisen. Beantworten Sie zunächst die folgenden Fragen, bevor Sie sich für eine Methode zum Aktivieren der Benutzer für E9-1-1 entscheiden.
  
 **Planen Sie die Aktivierung für alle Benutzer, oder soll die Unterstützung auf spezifische geografische Bereiche innerhalb des Unternehmens beschränkt werden?**
  
> Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Ortungsrichtlinie verwenden. Durch zuweisen einer Standortrichtlinie zu einem Skype for Business Server-Netzwerkstandort und anschließendes Hinzufügen von Subnetzen zum Standort können Sie die E9-1-1-Unterstützung jedoch auf ausgewählte Standorte innerhalb des Unternehmens beschränken und das Routingverhalten von E9-1-1 pro Standort angeben. 
    
 **Planen Sie die Aktivierung einzelner Benutzer über eine Benutzerrichtlinie?**
  
> Sie können bestimmten Benutzern oder Kontaktobjekten von Telefonen in öffentlichen Bereichen direkt Ortungsrichtlinien zuweisen, wenn Sie die E9-1-1-Unterstützung anpassen möchten.
    
 **Sollen Clients auch dann für E9-1-1 aktiviert werden, wenn sie sich außerhalb des Netzwerks bewegen oder sich von einem undefinierten Subnetz aus verbinden?**
  
> Wenn Benutzern eine globale Standortrichtlinie, eine Standortrichtlinie auf Standort- oder Benutzerseite zugewiesen ist, können sie manuell einen Standort in den Client eingeben müssen, wenn sich der Client nicht in einem definierten Subnetz befindet oder der Standortinformationsdienst keinen Standort gefunden hat. Weitere Informationen finden Sie unter ["Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server".](manually-acquiring-a-location.md)
    

