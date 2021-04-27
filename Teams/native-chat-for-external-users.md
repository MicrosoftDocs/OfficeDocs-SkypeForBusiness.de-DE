---
title: Native Chaterfahrung für externe (Verbundbenutzer) in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über die native Chaterfahrung von Teams für externe Benutzer (Verbundbenutzer) in Microsoft Teams, in denen sich beide Benutzer im Microsoft TeamsOnly-Upgrademodus befinden.
ms.openlocfilehash: a06532ab4cd1d1c5ffe3f30d2a6036b2c34c716f
ms.sourcegitcommit: 5a39061c2156531f4b7f5f69eecf81a8c8b238d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2021
ms.locfileid: "52030115"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Native Chaterfahrung für externe (Verbundbenutzer) in Microsoft Teams

Wenn ein Microsoft Teams-Benutzer mit einem externen (Verbundbenutzer) chatt, ist die Chaterfahrung auf Text beschränkt. Wenn sich jedoch sowohl Ihr Teams-Benutzer als auch die Person in einer anderen Organisation im TeamsOnly-Upgrademodus befinden, können Sie über eine "native-Teams-Chaterfahrung" verfügen, die umfangreiche Formatierungen, @mentions und andere Chatfeatures umfasst. Native Teams-Chats mit Personen in anderen Organisationen sind nur auf 1:1-Chats beschränkt.

Die native Chaterfahrung für Personen in anderen Organisationen ist für alle Teams-Mandanten aktiviert, aber nicht alle Personen sind berechtigt. Um eine systemeigene Chaterfahrung zu erhalten, müssen sowohl der Absender als auch der Empfänger für den TeamsOnly-Upgrademodus konfiguriert werden. Weitere Informationen zu Upgraderichtlinien finden Sie unter [Festlegen der Koexistenz- und Upgradeeinstellungen.](setting-your-coexistence-and-upgrade-settings.md)

Eine Liste der Funktionen für externe Zugriffsbenutzer in Teams finden Sie unter Vergleichen von externem und [Gastzugriff.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Wo kann ich wissen, ob ich in einem nativen Chat bin?

Wenn Sie in Ihrem Chat nur Text mit Personen in anderen Organisationen austauschen können, sind Sie in einem standardmäßigen externen (Verbund-)Chat. Wenn Sie alle anderen Chatfunktionen wie Formatierung, @mentions, Emojis usw. haben, sind Sie in einem systemeigenen Teams-Chat. 

Teams überprüft in regelmäßigen Abständen den Upgrademodus für Personen in anderen Organisationen, und wenn teams im Upgrademodus von Teams ausgeführt wird, werden Sie aufgefordert, zu einem systemeigenen Teams-Chat zu wechseln und den ursprünglichen Chat zu sperren.

Wenn Sie zu einem nativen Teams-Chat wechseln, führt Teams die beiden Unterhaltungen nicht zusammen. Stattdessen werden beide Chats in Ihrem Chatfeed angezeigt. Der neue, native Teams-Chat ist aktiv, aber der alte, nur textgesperrte Chat ist gesperrt.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Was geschieht, wenn sich ein Benutzer nicht mehr im Modus "Nur Teams" befindet?

Wenn Sie einen nativen Teams-Chat mit Personen in anderen Organisationen hatten und dann einer von Ihnen aus dem TeamsOnly-Upgrademodus gewechselt wird, sperrt Teams den nativen Teams-Chat und gibt Ihnen einen Link für einen begrenzten, nur textigen Chat. Sie können den systemeigenen Teams-Chat nicht fortsetzen. Sie können den nativen Teams-Chat weiterhin lesen, aber sie können die Unterhaltung dort nicht fortsetzen.

Wenn Teams einen alten Nur-Text-Chat mit dieser Person findet, wird dieser Chat wiederbelebt. Andernfalls erstellt Teams einen neuen Nur-Text-Chat.


## <a name="related-topics"></a>Verwandte Themen

[Externer Zugriff in Teams verwalten](manage-external-access.md)
