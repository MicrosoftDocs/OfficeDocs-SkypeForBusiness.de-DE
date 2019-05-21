---
title: Zuweisen von Standortrichtlinien Bereich in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e4c66517-c593-4253-b900-7b4dd8bddf2f
description: Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP
ms.openlocfilehash: 04eb04733649e2967980e0121d17cf71221f5387
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276740"
---
# <a name="assign-location-policy-scope-in-skype-for-business-server"></a>Zuweisen von Standortrichtlinien Bereich in Skype for Business Server
 
Planen von Standortrichtlinien für eine E9-1-1-Bereitstellung in Skype for Business Server Enterprise-VoIP
  
Wie bei anderen Skype for Business-Server Richtlinien können Standortrichtlinien auf mehreren Bereichsebenen zugewiesen werden: Global, Website und Benutzer. Der Umfang der Standortrichtlinien auf Benutzerebene verhält sich jedoch etwas anders als bei anderen Skype for Business-Server Richtlinien. Auf Endpunkt Objekte (wie Benutzer und Telefon Kontaktobjekte im öffentlichen Bereich) können nicht nur Orts Richtlinien für einzelne Benutzer angewendet werden, sondern Sie können auch auf Skype for Business Server-Netzwerk Websites angewendet werden. Netzwerkstandorte sind Gruppierungen von Client-Subnetzen, die einem geografischen Standort zugeordnet sind (jedoch muss es sich nicht zwingend um alle Subnetze an einem zentralen Standort oder in einer Zweigniederlassung handeln). Alle Clients, die mit den Subnetzen an einem Netzwerkstandort verbunden sind, übernehmen automatisch die Standortrichtlinie, die dem jeweiligen Netzwerkstandort zugewiesen ist. Wenn eine Standortrichtlinie auf Benutzerebene sowohl einem Benutzer als auch einem Netzwerkstandort zugewiesen ist, hat die auf dem Netzwerkstandort basierende Standortrichtlinie Vorrang vor allen benutzerspezifischen Richtlinieneinstellungen.
  
Jedem Netzwerkstandort ist eine Standortrichtlinie zugewiesen und jeder Richtlinie sind andere Werte für PSTN-Verwendungen, Benachrichtigungs-URIs und Konferenz-URIs zugewiesen.
  
> [!NOTE]
> Dieses spezielle Richtlinienverhalten hat folgenden Grund: Wenn ein Benutzer, der einem Pool an einem Bürostandort angehört, einen anderen Standort besucht und einen Notruf tätigen muss, gelten die Einstellungen für die E9-1-1-Anrufumleitung für diesen Netzwerkstandort unabhängig davon, welchem Pool oder welchem Standort der Benutzer zugewiesen ist. 
  

