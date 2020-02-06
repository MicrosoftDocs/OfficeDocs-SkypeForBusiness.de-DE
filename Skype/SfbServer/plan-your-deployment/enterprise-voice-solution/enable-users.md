---
title: Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der Benutzer, die aktiviert werden sollen und wie Roaming-Benutzer unterstützt werden.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802955"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Aktivieren von Benutzern für E9-1-1 in Skype for Business Server
 
Entscheidungen, die für die Standortrichtlinie für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP erforderlich sind, einschließlich der Benutzer, die aktiviert werden sollen und wie Roaming-Benutzer unterstützt werden.
  
Während der Clientregistrierung verwendet Skype for Business Server eine ortungsrichtlinie, um die E9-1-1-Eigenschaften für Enterprise-sprachaktivierte Benutzer zu konfigurieren. Diese Richtlinie enthält die Einstellungen, die definieren, wie E9-1-1 implementiert wird. Beispielsweise enthält die Standortrichtlinie Informationen wie die Notrufnummern Zeichenfolge und ob ein Benutzer manuell einen Standort eingeben muss, wenn der standortinformationsdienst nicht automatisch einen Speicherort bereitstellt. Eine vollständige Definition einer Standortrichtlinie finden Sie unter [Planen von Standortrichtlinien für Skype for Business Server](location-policies.md).
  
Skype for Business Server kann Clients, die auf einem Subnetz basieren, oder Benutzern, die auf einer globalen, pro-Site-oder pro-Benutzer-Richtlinie basieren, eine ortungsrichtlinie zuweisen. Damit Sie entscheiden können, wie Sie die Benutzer aktivieren können, sollten Sie zunächst die folgenden Fragen beantworten.
  
 **Beabsichtigen Sie, alle Benutzer zu aktivieren oder die Unterstützung auf bestimmte geografische Bereiche des Unternehmens zu begrenzen?**
  
> Sie können allen Benutzern in Ihrem Unternehmen einen Standort zuweisen, indem Sie eine globale Standortrichtlinie verwenden. Wenn Sie jedoch eine Standortrichtlinie einer Skype for Business Server-Netzwerk Website zuweisen und dann Subnetze zur Website hinzufügen, können Sie die E9-1-1-Unterstützung auf ausgewählte Standorte innerhalb des Unternehmens begrenzen und das Routingverhalten von E9-1-1 pro Website angeben. 
    
 **Beabsichtigen Sie, einzelne Benutzer über eine Benutzerrichtlinie zu aktivieren?**
  
> Sie können Standortrichtlinien bestimmten Benutzern oder öffentlichen Telefon Kontaktobjekten direkt zuweisen, wenn Sie Ihre E9-1-1-Unterstützung anpassen möchten.
    
 **Wenn Clients außerhalb des Netzwerks oder mit einem nicht definierten Subnetz verbunden sind, sollten die Clients weiterhin für E9-1-1 aktiviert sein?**
  
> Wenn Benutzern eine Global-, Site-oder pro-User-ortungsrichtlinie zugewiesen ist, kann es erforderlich sein, einen Standort manuell in den Client einzugeben, wenn sich der Client nicht in einem definierten Subnetz befindet oder vom standortinformationsdienst kein Standort gefunden wurde. Ausführliche Informationen finden Sie unter [Definieren der Benutzeroberfläche für den manuellen Erwerb eines Standorts in Skype for Business Server](manually-acquiring-a-location.md).
    

