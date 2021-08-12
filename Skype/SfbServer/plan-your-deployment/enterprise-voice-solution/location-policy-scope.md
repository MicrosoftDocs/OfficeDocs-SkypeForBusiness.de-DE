---
title: Zuweisen des Standortrichtlinienbereichs in Skype for Business Server
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
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
ms.openlocfilehash: b56b3fa2205939b458635d5a461dc4f8d55134cf2703ce1872a2be2141d5d635
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286504"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Zuweisen des Standortrichtlinienbereichs in Skype for Business Server
 
Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
  
Wie bei anderen Skype for Business Server Richtlinien können Standortrichtlinien auf mehreren Ebenen zugewiesen werden: global, Standort und Benutzer. Der Umfang von Standortrichtlinien auf Benutzerebene verhält sich jedoch etwas anders als bei anderen Skype for Business Server Richtlinien. Standortrichtlinien können nicht nur auf Endpunktobjekte (z. B. Benutzer und Gemeinsame Bereiche Telefon Kontaktobjekte) angewendet werden, sie können auch auf Skype for Business Server Netzwerkstandorte angewendet werden. Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln). Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist. Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor jeglichen benutzerspezifischen Richtlinieneinstellungen.
  
Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen, und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.
  
> [!NOTE]
> Der Grund für dieses spezielle Richtlinienverhalten ist, dass, wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon gelten, welchem Pool oder welchem Standort der Benutzer zugewiesen ist. 
  

