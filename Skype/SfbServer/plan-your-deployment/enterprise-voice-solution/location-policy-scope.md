---
title: Zuweisen eines Standortrichtlinienbereichs in Skype for Business Server
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
ms.openlocfilehash: 586aabe919ea4236dc724446da717b5f300d88e9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825525"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Zuweisen eines Standortrichtlinienbereichs in Skype for Business Server
 
Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP.
  
Wie bei anderen Skype for Business Server-Richtlinien können Standortrichtlinien auf mehreren Ebenen zugewiesen werden: global, Standort und Benutzer. Der Umfang von Standortrichtlinien auf Benutzerebene verhält sich jedoch etwas anders als bei anderen Skype for Business Server-Richtlinien. Standortrichtlinien auf Benutzer können nicht nur auf Endpunktobjekte (z. B. Benutzer und Kontaktobjekte für Telefone in common Area Phone) angewendet werden, sondern auch auf Skype for Business Server-Netzwerkstandorte. Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln). Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist. Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor jeglichen benutzerspezifischen Richtlinieneinstellungen.
  
Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen, und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.
  
> [!NOTE]
> Der Grund für dieses spezielle Richtlinienverhalten ist, dass, wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon gelten, welchem Pool oder welchem Standort der Benutzer zugewiesen ist. 
  

