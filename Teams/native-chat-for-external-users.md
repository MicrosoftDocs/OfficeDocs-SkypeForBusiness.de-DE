---
title: Systemeigene Chat-Umgebung für externe (Federated-) Benutzer in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Erfahren Sie mehr über die native Teams-Chat-Erfahrung für externe Access (Federated)-Benutzer in Microsoft Teams, die zwischen externen Benutzern verfügbar sind, bei denen sich beide Benutzer im TeamsOnly-Aktualisierungsmodus befinden.
ms.openlocfilehash: a7a66693bbff98aa707c369a9da08d0ccfe48f69
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2019
ms.locfileid: "37754341"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Systemeigene Chat-Umgebung für externe (Federated-) Benutzer in Microsoft Teams
======================================

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Wenn ein Microsoft Teams-Benutzer mit einem externen (Föderations-) Benutzer chattet, ist die Chat-Erfahrung auf Text begrenzt. Wenn sich jedoch sowohl der Mandant des Teams als auch der des externen Benutzers im TeamsOnly-Upgrademodus befinden, können Sie eine "Native-Teams-Chat Erfahrung" verwenden, die Rich-Formatierung, @Mentions und andere Chat Features umfasst. Mit anderen Worten: Sie können dieselbe Rich-1:1-Team-Chat-Erfahrung mit berechtigten externen Benutzern haben, wie Sie dies bei Benutzern in Ihrer Organisation tun würden. Native Teams-Chats mit externen Benutzern sind weiterhin nur auf 1:1-Chats limitiert (externe Benutzer können keine Gruppen-Chats durchführen).

Die native Chat-Umgebung für externe Benutzer ist für alle Teams-Mandanten aktiviert, aber nicht alle Benutzer sind berechtigt. Um eine native Chat-Erfahrung anbieten zu können, müssen sich Absender und Empfänger in einem Teams-Mandanten befinden, der den TeamsOnly-Aktualisierungsmodus ausführt. Weitere Informationen zu Aktualisierungsrichtlinien finden Sie unter [Festlegen der Koexistenz-und Aktualisierungseinstellungen](setting-your-coexistence-and-upgrade-settings.md).

Informationen zum Anzeigen einer Liste der Funktionen für Benutzer mit externem Zugriff in Teams finden Sie unter [Vergleichen von externem und Gastzugriff](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Wie kann ich feststellen, ob ich in einem nativen Chat bin?

Wenn Sie nur Text in Ihrem Chat mit einem externen Benutzer austauschen können, befinden Sie sich in einem standardmäßigen externen Zugriff (Federated-Chat). Wenn Sie alle anderen Chat-Funktionen, einschließlich Formatierung, @Mentions, Emojis usw., haben, sind Sie in einem nativen Teams-Chat mit Ihrem externen Benutzer. 

Teams überprüft in regelmäßigen Abständen den Upgrademodus für externe Benutzer, und wenn ein externer Benutzer Teams im TeamsOnly-Aktualisierungsmodus ausführt, werden Sie aufgefordert, zu einem nativen Teamchat zu wechseln und den ursprünglichen Chat zu sperren.

Wenn Sie zu einem systemeigenen Teamchat wechseln, werden die beiden Konversationen nicht von Teams zusammengeführt. Stattdessen werden beide Chats in Ihrem Chat-Feed angezeigt. Der neue Chat in der systemeigenen Teams ist aktiv, aber der alte, nur-Text-Chat ist gesperrt.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Was passiert, wenn sich ein Benutzer nicht mehr im Modus "Teams" befindet?

Wenn Sie einen eigenen Teams-Chat mit einem externen Nutzer führen und dann einer von Ihnen aus dem TeamsOnly-Upgrade-Modus ausgetauscht wird, sperrt Teams den Native Teams-Chat und gibt Ihnen einen Link zu einem limitierten, nur-Text-Chat. Sie können im Native Teams-Chat nicht fortfahren. Sie können immer noch den Chat in der systemeigenen Teams lesen, aber Sie können die Unterhaltung dort nicht fortsetzen.

Wenn Teams einen alten, nur-Text-Chat mit diesem externen Nutzer findet, wird dieser Chat wieder belebt. Andernfalls erstellt Teams einen neuen, nur-Text-Chat.


## <a name="related-topics"></a>Verwandte Themen

[Verwalten des externen Zugriffs in Teams](manage-external-access.md)
