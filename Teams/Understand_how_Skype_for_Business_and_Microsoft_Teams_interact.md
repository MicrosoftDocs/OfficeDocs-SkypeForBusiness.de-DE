---
title: Interaktion von Skype for Business und Microsoft Teams | Microsoft-Support
author: LolaJacobsen
ms.author: lolaj
manager: serdar
ms.date: 08/11/2017
ms.topic: overview
ms.prod: teams
description: "Erfahren Sie hier, wie Skype for Business und Microsoft Teams interagieren – von Chats bis zu Anrufen."
ms.openlocfilehash: cb459fa444f7324a358fbd325e3ddb5cfd4c1966
ms.sourcegitcommit: 3b9b3f07f4f67cd5f43da68f48d62222d7e49167
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2017
---
<a name="how-skype-for-business-and-microsoft-teams-interact"></a>Interaktion von Skype for Business und Microsoft Teams
===================================================

Wenn Ihre Organisation Skype for Business verwendet, sind Kenntnisse über die Interaktion zwischen Skype for Business und Microsoft Teams von großer Bedeutung.

Im Hinblick auf die allgemeine Verfügbarkeit von Microsoft Teams ist die grundlegende Interoperabilität zwischen Microsoft Teams und Skype for Business Online oder Hybrid nur für Peer-zu-Peer (P2P)-Instant Messaging verfügbar.

Standardmäßig meldet sich der Microsoft Teams-Client sowohl bei den Microsoft Teams-Backend-Diensten als auch bei den Skype for Business-Diensten an (ein auf einem dualen Stapel basierter Ansatz). Der Microsoft Teams-Client stellt Skype for Business nur Instant Messaging-Funktionen zur Verfügung. Bei der Suche nach einem Microsoft Teams-Benutzer über Skype for Business wird der Benutzer wie im oberen Beispiel gezeigt mit „Nur Instant Messaging“ gekennzeichnet (Alix Wilber ist nur beim Microsoft Teams-Client angemeldet).

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image1.png)

In Microsoft Teams können Benutzer andere Benutzer innerhalb ihrer Organisation suchen, die derzeit nicht für Skype for Business aktiviert sind, und Instant Messaging-Chatsitzungen durchführen.

Benutzer von Skype for Business können auf die Sofortnachrichten antworten, die im Chatfenster von Microsoft Teams ankommen.

![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image2.png)

Falls Benutzer von Microsoft Teams ebenfalls für Skype for Business aktiviert sind, können sich mit ihren eigenen Clients gleichzeitig bei Microsoft Teams und bei Skype for Business anmelden.

Der letzte aktive Endpunkt wird berücksichtigt. Wenn der Benutzer also Microsoft Teams aktiv verwendet, werden alle von einem Skype for Business-Benutzer gesendeten Sofortnachrichten im Microsoft Teams-Chatfenster angezeigt. Wenn der Benutzer Skype for Business zum Empfangen oder Tätigen von Telefonanrufen verwendet oder einfach nur einen Anruf über Skype for Business beendet und nicht zum Microsoft Teams-Client zurückkehrt, kommen die von einem Skype for Business-Benutzer gesendeten eingehenden Sofortnachrichten beim Skype for Business-Client an, da dies der aktivste Endpunkt darstellt.

Da Microsoft Teams derzeit nur Peer-zu-Peer (P2P)-Instant Messaging-Interoperabilität zwischen Skype for Business unterstützt, kommen alle Audio- bzw. Videoanrufe oder Einladungen zur Teilnahme an einer Skype for Business-Besprechung von anderen Skype for Business-Benutzern nur beim Skype for Business-Client an. Umgekehrt kommen alle Audio- bzw. Videoanrufe oder Einladungen zur Teilnahme an einem Gruppenanruf nur beim Microsoft Teams-Client an.

Basierend auf dem oben erläuterten Verhalten können Endbenutzer Microsoft Teams und Skype for Business bequem gleichzeitig benutzen und den jeweiligen Kommunikationsanforderungen mit dem richtigen Tool begegnen. Für eine optimale Erfahrung der Endbenutzer können jedoch Kenntnisse über die Interoperabilität und deren Auswirkungen erforderlich sein.


|  |  |
|---------|---------|
|![](media/Understand_how_Skype_for_Business_and_Microsoft_Teams_interact_image3.png)<br>Hinweis</br>      |Mit der Interoperabilität von Skype for Business werden in Teams ankommende Sofortnachrichten nicht im Skype for Business-Unterhaltungsverlauf aufgezeichnet.         |

Microsoft Teams bietet Benutzern die Möglichkeit, die Interoperabilität von Skype for Business in den Benachrichtigungseinstellungen zu deaktivieren. Diese Einstellung ist benutzerdefiniert, sodass jeder Benutzer sich für das jeweilige Verhalten entscheiden kann.
