---
title: Zuweisen des Bereichs für eine Standortrichtlinie in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype Business Server Enterprise-VoIP.
ms.openlocfilehash: 472ca2e6382a92005476eb7ed7c6bcfb22e71f85
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="assign-location-policy-scope-in-skype-for-business-server-2015"></a>Zuweisen des Bereichs für eine Standortrichtlinie in Skype for Business Server 2015
 
Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype Business Server Enterprise-VoIP.
  
Wie mit anderen Skype für Business Server-Richtlinien, anhand von Standortrichtlinien auf mehreren Ebenen der Bereich zugewiesen werden können: global, Standort und Benutzer. Der Umfang der Richtlinien auf Benutzerebene Speicherort verhält sich aber etwas anders als mit anderen Skype für Business Server-Richtlinien. Nicht nur anhand von Standortrichtlinien pro Benutzer angewendet werden können an Endpoint-Objekte (wie Benutzer und Common Area Phone Contact-Objekte), sie können auch auf angewendet werden Skype für Business Server-Netzwerk-Sites. Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln). Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist. Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor allen benutzerspezifischen Richtlinieneinstellungen.
  
Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.
  
> [!NOTE]
> Dieses spezielle Richtlinienverhalten hat folgenden Grund: Wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, gelten die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon, welchem Pool oder welchem Standort der Benutzer zugewiesen ist. 
  

