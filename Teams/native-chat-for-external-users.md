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
description: Erfahren Sie mehr über die systemeigene Teams-Chats für externe Benutzer (Partnerbenutzer) in Microsoft Teams wo sich beide Benutzer im Upgrademodus "TeamsOnly" befinden.
ms.openlocfilehash: 992b4dd28d17f1ba8abf7217d622da18813c3118
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138231"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Native Chaterfahrung für externe Benutzer (Partnerbenutzer) in Microsoft Teams

Wenn ein Microsoft Teams mit einem externen Benutzer (Partnerbenutzer) chatt, ist die Chaterfahrung auf Text beschränkt. Wenn sich jedoch sowohl Ihr Teams-Benutzer als auch die Person in einer anderen Organisation im TeamsOnly-Upgrademodus befinden, können Sie über eine "native Teams-Chaterfahrung" verfügen, die umfangreiche Formatierungen, @mentions und andere Chatfunktionen umfasst.

Die native Chaterfahrung für Personen in anderen Organisationen ist für alle Mandanten Teams aktiviert, aber nicht alle Personen sind berechtigt. Um eine systemeigene Chaterfahrung zu erhalten, müssen sowohl der Absender als auch der Empfänger für den TeamsOnly-Upgrademodus konfiguriert sein. Weitere Informationen zu Upgraderichtlinien finden Sie unter [Festlegen der Koexistenz- und Upgradeeinstellungen.](setting-your-coexistence-and-upgrade-settings.md)

Eine Liste der Funktionen für benutzer mit externem Zugriff in Teams Sie unter [Vergleich von externem und Gastzugriff.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Wie kann ich wissen, ob ich in einem nativen Chat bin?

Wenn Sie in Ihrem Chat nur Text mit Personen in anderen Organisationen austauschen können, sind Sie in einem Standardchat mit externem Zugriff (Partnerchat) zu finden. Wenn Sie andere Chatfunktionen haben, einschließlich Formatierung, @mentions, Emojis usw., sind Sie in einem nativen Chat Teams Chat. 

Teams überprüft in regelmäßigen Abständen den Upgrademodus für Personen in anderen Organisationen, und wenn ein Benutzer gefunden wird, der Teams im Upgrademodus für TeamsOnly ausgeführt wird, werden Sie aufgefordert, zu einem systemeigenen Teams-Chat zu wechseln und den ursprünglichen Chat zu sperren.

Wenn Sie zu einem systemeigenen Teams wechseln, führt Teams die beiden Unterhaltungen nicht zusammen. Stattdessen werden beide Chats in Ihrem Chatfeed angezeigt. Der neue, systemeigene Chat Teams ist aktiv, aber der alte Chat, der nur Text enthält, ist gesperrt.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Was geschieht, wenn sich ein Benutzer nicht mehr im Teams Nur Modus befindet?

Wenn Sie einen nativen Teams-Chat mit Personen in anderen Organisationen unterhalten und eine von Ihnen aus dem Upgrademodus für TeamsOnly gewechselt wird, sperrt Teams den nativen Teams-Chat und stellt Ihnen einen Link zu einem eingeschränkten, auf Text beschränkten Chat zur Verfügung. Sie können in der systemeigenen Chat-Teams fortfahren. Sie können den nativen Chat weiterhin Teams, aber Sie können die Unterhaltung dort nicht fortsetzen.

Wenn Teams mit dieser Person einen alten Chat gefunden hat, der nur Text enthält, wird dieser Chat verungllebt. Andernfalls erstellt Teams einen neuen Chat, der nur Text enthält.


## <a name="related-topics"></a>Verwandte Themen

[Externer Zugriff in Teams verwalten](manage-external-access.md)
