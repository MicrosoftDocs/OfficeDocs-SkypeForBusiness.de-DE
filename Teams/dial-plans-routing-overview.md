---
title: Wählpläne und Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
description: Wählpläne und Routing in Microsoft Teams
ms.openlocfilehash: 89332b5e5756bc33c92a67b641bab85b826bfe70
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606784"
---
# <a name="overview"></a>Übersicht

In den Artikeln in diesem Abschnitt werden Wählpläne und Anrufweiterleitung in Microsoft Teams beschrieben. 

- [Was sind Wählpläne?](what-are-dial-plans.md)
- [Erstellen und Verwalten von Wählplänen](create-and-manage-dial-plans.md)
- [Weiterleiten von Anrufen an nicht zugewiesene Nummern](routing-calls-to-unassigned-numbers.md)

Die Artikel in diesem Abschnitt gelten für alle Optionen für die Verbindung mit dem Telefonfestnetz (Public Switched Telephone Network, PSTN): Anrufplan, Telefonieanbieter, Telefonieanbieter mit Mobil (Public Preview Release) und Direct Routing. Weitere Informationen zu allen PSTN-Konnektivitätsoptionen finden Sie unter [PSTN-Konnektivitätsoptionen](pstn-connectivity.md).

Wenn Sie Anrufplan, Telefonieanbieter oder Telefonieanbieter mit Mobil auswählen, wird die meisten Anrufweiterleitung entweder von Microsoft oder Ihrem Anbieter verarbeitet. Direct Routing erfordert jedoch zusätzliche Schritte, um das Anrufrouting zu konfigurieren. 

Für direktes Routing müssen Sie das Anrufrouting konfigurieren, indem Sie die VoIP-Routen angeben und den Benutzern VoIP-Routing-Richtlinien zuweisen. Sie können Wählpläne für die Nummernübersetzung auf Amtsleitungsebene konfigurieren, um die Interoperabilität mit Session Border Controllers (SBCs) sicherzustellen. Weitere Informationen finden Sie unter [Voice-Routing für Direct Routing konfigurieren ](direct-routing-voice-routing.md), [Voice-Routing-Richtlinien verwalten ](manage-voice-routing-policies.md) und [ Telefonnummern übersetzen](direct-routing-translate-numbers.md).

Beachten Sie, dass Sie eine Direct Routing-Online-VoIP-Routingrichtlinie zu Anrufplan- und Operator Connect-Benutzern zuweisen können. Sie können dies beispielsweise tun, um Benutzern das direkte Einwählen in ein Callcenter zu ermöglichen. Sie können einen Direct Routing-Trunk für das Callcenter einrichten.

Wenn ein Benutzer beispielsweise über eine Anrufplanlizenz verfügt, werden die ausgehenden Anrufe dieses Benutzers automatisch über die PSTN-Infrastruktur des Microsoft-Anrufplans weitergeleitet. Wenn Sie eine Direct Routing-Online-VoIP-Routingrichtlinie konfigurieren und dem Benutzer zuweisen, werden die ausgehenden Anrufe des Benutzers überprüft, um festzustellen, ob die gewählte Nummer einem Nummernmuster entspricht, das in der Online-VoIP-Routingrichtlinie definiert ist. Wenn eine Übereinstimmung vorliegt, wird der Anruf über den Direct Routing-Trunk weitergeleitet. Wenn keine Übereinstimmung vorliegt, wird der Anruf über die PSTN-Infrastruktur des Anrufplans weitergeleitet.

Weitere Informationen finden Sie unter [Überlegungen zur Direct Routing-VoIP-Routingrichtlinie](direct-routing-voice-routing.md#voice-routing-policy-considerations).



