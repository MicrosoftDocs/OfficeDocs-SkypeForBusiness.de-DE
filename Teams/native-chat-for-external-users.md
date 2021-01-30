---
title: Native Chaterfahrung für externe Benutzer (Partnerbenutzer) in Microsoft Teams
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
description: Erfahren Sie mehr über die native Chaterfahrung von Teams für externe Benutzer (Partnerbenutzer) in Microsoft Teams, bei denen sich beide Benutzer im Upgrademodus "TeamsOnly" befinden.
ms.openlocfilehash: df9e1e41992e105937deacf898833995cdfb7714
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055657"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Native Chaterfahrung für externe Benutzer (Partnerbenutzer) in Microsoft Teams

Wenn ein Microsoft Teams-Benutzer mit einem externen (Partnerbenutzer) chatt, ist die Chaterfahrung auf Text beschränkt. Wenn sich jedoch sowohl ihr Benutzer als auch die Person in einer anderen Organisation im Upgrademodus "TeamsOnly" befinden, können Sie über eine "native Teams-Chaterfahrung" verfügen, die umfangreiche Formatierungen, @mentions und andere Chatfunktionen umfasst. Mit anderen Worten: Sie können über dieselbe umfangreiche 1:1 Teams-Chaterfahrung mit berechtigten Personen in anderen Organisationen verfügen wie mit Benutzern in Ihrer Organisation. Native Teams-Chats mit Personen in anderen Organisationen sind nur auf 1:1-Chats beschränkt.

Die native Chaterfahrung für Personen in anderen Organisationen ist für alle Teams-Mandanten aktiviert, aber nicht alle Personen sind berechtigt. Um eine systemeigene Chaterfahrung zu erhalten, müssen sowohl der Absender als auch der Empfänger für den Upgrademodus von TeamsOnly konfiguriert sein. Weitere Informationen zu Upgraderichtlinien finden Sie unter ["Festlegen der Koexistenz- und Upgradeeinstellungen".](setting-your-coexistence-and-upgrade-settings.md)

Eine Liste der Funktionen für externe Zugriffsbenutzer in Teams finden Sie unter "Vergleich des [externen und des Gastzugriffs".](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Wie kann ich wissen, ob ich in einem systemeigenen Chat bin?

Wenn Sie in Ihrem Chat nur Text mit Personen in anderen Organisationen austauschen können, sind Sie in einem Standardchat mit externem Zugriff (Partnerchat) zu finden. Wenn Sie alle anderen Chatfunktionen, einschließlich Formatierung, @mentions, Emojis usw., haben, sind Sie in einem nativen Teams-Chat. 

Teams überprüft in regelmäßigen Abständen den Upgrademodus für Personen in anderen Organisationen, und wenn teams im Upgrademodus von Teams ausgeführt wird, werden Sie aufgefordert, zu einem nativen Teams-Chat zu wechseln und den ursprünglichen Chat zu sperren.

Wenn Sie zu einem nativen Teams-Chat wechseln, führt Teams die beiden Unterhaltungen nicht zusammen. Stattdessen werden beide Chats in Ihrem Chatfeed angezeigt. Der neue, native Chat in Teams ist aktiv, aber der alte Chat, der nur Text enthält, ist gesperrt.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Was geschieht, wenn sich ein Benutzer nicht mehr im Nur-Teams-Modus befindet?

Wenn Sie einen nativen Teams-Chat mit Personen in anderen Organisationen unterhalten und dann einer von Ihnen aus dem Upgrademodus für TeamsOnly wechselt, sperrt Teams den nativen Teams-Chat und stellt Ihnen einen Link zu einem eingeschränkten, nur auf Text beschränkten Chat zur Verfügung. Sie können den nativen Teams-Chat nicht fortsetzen. Sie können den nativen Teams-Chat zwar weiterhin lesen, die Unterhaltung dort aber nicht fortsetzen.

Wenn Teams einen alten Nur-Text-Chat mit dieser Person findet, wird dieser Chat angezeigt. Andernfalls erstellt Teams einen neuen Chat, der nur Text enthält.


## <a name="related-topics"></a>Verwandte Themen

[Verwalten des externen Zugriffs in Teams](manage-external-access.md)
