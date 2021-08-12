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
description: Erfahren Sie mehr über die systemeigene Teams-Chats für externe Benutzer (Partnerbenutzer) in Microsoft Teams, in denen sich beide Benutzer im Upgrademodus "TeamsOnly" befinden.
ms.openlocfilehash: 3d94c55dc184d80edbc22be53f1df18c256423c5aa04b7e342b8964463db1aa7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350597"
---
# <a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a>Native Chaterfahrung für externe Benutzer (Partnerbenutzer) in Microsoft Teams

Wenn ein Microsoft Teams mit einem externen Benutzer (Partnerbenutzer) chatt, ist die Chaterfahrung auf Text beschränkt. Wenn sich jedoch sowohl Ihr Teams-Benutzer als auch die Person in einer anderen Organisation im TeamsOnly-Upgrademodus befinden, können Sie über eine "native Teams-Chaterfahrung" verfügen, die umfangreiche Formatierungen, @mentions und andere Chatfunktionen umfasst. Native Teams-Chats mit Personen in anderen Organisationen sind auf 1:1-Chats beschränkt.

Die native Chaterfahrung für Personen in anderen Organisationen ist für alle Mandanten Teams aktiviert, aber nicht alle Personen sind berechtigt. Um eine systemeigene Chaterfahrung zu erhalten, müssen sowohl der Absender als auch der Empfänger für den TeamsOnly-Upgrademodus konfiguriert sein. Weitere Informationen zu Upgraderichtlinien finden Sie unter [Festlegen der Koexistenz- und Upgradeeinstellungen.](setting-your-coexistence-and-upgrade-settings.md)

Eine Liste der Funktionen für benutzer mit externem Zugriff in einer Teams Sie unter Vergleich von externem [und Gastzugriff.](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)

## <a name="how-do-i-know-if-im-in-a-native-chat"></a>Wie kann ich wissen, ob ich in einem nativen Chat bin?

Wenn Sie in Ihrem Chat nur Text mit Personen in anderen Organisationen austauschen können, sind Sie in einem Standardchat mit externem Zugriff (Partnerchat) zu finden. Wenn Sie andere Chatfunktionen wie Formatierung, @mentions, Emojis usw. haben, sind Sie in einem nativen Chat Teams Chat. 

Teams überprüft in regelmäßigen Abständen den Upgrademodus für Personen in anderen Organisationen. Wenn ein Benutzer gefunden wird, der Teams im TeamsOnly-Upgrademodus ausgeführt wird, werden Sie aufgefordert, zu einem systemeigenen Teams-Chat zu wechseln und den ursprünglichen Chat zu sperren.

Wenn Sie zu einem systemeigenen Chat Teams, führt Teams die beiden Unterhaltungen nicht zusammen. Stattdessen werden beide Chats in Ihrem Chatfeed angezeigt. Der neue, systemeigene Chat Teams ist aktiv, aber der alte Chat, der nur Text enthält, ist gesperrt.



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a>Was geschieht, wenn sich ein Benutzer nicht mehr im Teams Nur Modus befindet?

Wenn Sie über einen nativen Teams-Chat mit Personen in anderen Organisationen unterhalten und eine von Ihnen aus dem Upgrademodus für TeamsOnly gewechselt wird, sperrt Teams den systemeigenen Teams-Chat und stellt Ihnen einen Link zu einem eingeschränkten, auf Text beschränkten Chat zur Verfügung. Sie können im systemeigenen Chat nicht Teams fortfahren. Sie können den nativen Chat weiterhin Teams, aber Sie können die Unterhaltung dort nicht fortsetzen.

Wenn Teams person einen alten Chat, der nur Text enthält, mit dieser Person findet, wird dieser Chat chatten. Andernfalls erstellt Teams einen neuen Chat, der nur Text enthält.


## <a name="related-topics"></a>Verwandte Themen

[Externer Zugriff in Teams verwalten](manage-external-access.md)
