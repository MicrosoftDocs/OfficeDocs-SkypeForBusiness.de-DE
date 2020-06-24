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
f1.keywords:
- NOCSH
description: Erfahren Sie mehr über die native Teams-Chat-Erfahrung für externe Access (Federated)-Benutzer in Microsoft Teams, die zwischen externen Benutzern verfügbar sind, bei denen sich beide Benutzer im TeamsOnly-Aktualisierungsmodus befinden.
ms.openlocfilehash: 1a8cd038f8ff65ea24abb790e564d2cb30ef0ed1
ms.sourcegitcommit: 44e47c3b2eb44c38cb8d761befdc6c0cef7c61bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2020
ms.locfileid: "44842006"
---
<a name="native-chat-experience-for-external-federated-users-in-microsoft-teams"></a><span data-ttu-id="0e9d9-103">Systemeigene Chat-Umgebung für externe (Federated-) Benutzer in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0e9d9-103">Native chat experience for external (federated) users in Microsoft Teams</span></span>
======================================

<span data-ttu-id="0e9d9-104">Wenn ein Microsoft Teams-Benutzer mit einem externen (Föderations-) Benutzer chattet, ist die Chat-Erfahrung auf Text begrenzt.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-104">When a Microsoft Teams user is chatting with an external (federated) user, the chat experience is limited to text.</span></span> <span data-ttu-id="0e9d9-105">Wenn sich jedoch sowohl der Benutzer Ihres Teams als auch der externe Benutzer im TeamsOnly-Upgrademodus befinden, können Sie eine "Native-Teams-Chat Erfahrung" verwenden, die Rich-Formatierung, @Mentions und andere Chat Features umfasst.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-105">However, if both your Teams user and the external user is in the TeamsOnly upgrade mode, you can have a "native-Teams chat experience," which includes rich formatting, @mentions, and other chat features.</span></span> <span data-ttu-id="0e9d9-106">Mit anderen Worten: Sie können dieselbe Rich-1:1-Team-Chat-Erfahrung mit berechtigten externen Benutzern haben, wie Sie dies bei Benutzern in Ihrer Organisation tun würden.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-106">In other words, you can have the same rich 1:1 Teams chat experience with eligible external users as you'd have with users in your organization.</span></span> <span data-ttu-id="0e9d9-107">Native Teams-Chats mit externen Benutzern sind weiterhin nur auf 1:1-Chats limitiert (externe Benutzer können keine Gruppen-Chats durchführen).</span><span class="sxs-lookup"><span data-stu-id="0e9d9-107">Native Teams chats with external users are still limited to 1:1 chats only (external users can't do group chats).</span></span>

<span data-ttu-id="0e9d9-108">Die native Chat-Umgebung für externe Benutzer ist für alle Teams-Mandanten aktiviert, aber nicht alle Benutzer sind berechtigt.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-108">The native chat experience for external users is turned on for all Teams tenants, but not all users are eligible.</span></span> <span data-ttu-id="0e9d9-109">Um eine native Chat-Erfahrung anbieten zu können, müssen sowohl der Absender als auch der Empfänger für den TeamsOnly-Aktualisierungsmodus konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-109">To be offered a native chat experience, both the sender and receiver need to be configured for TeamsOnly upgrade mode.</span></span> <span data-ttu-id="0e9d9-110">Weitere Informationen zu Aktualisierungsrichtlinien finden Sie unter [Festlegen der Koexistenz-und Aktualisierungseinstellungen](setting-your-coexistence-and-upgrade-settings.md).</span><span class="sxs-lookup"><span data-stu-id="0e9d9-110">To learn more about upgrade policies, read [Setting your coexistence and upgrade settings](setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="0e9d9-111">Informationen zum Anzeigen einer Liste der Funktionen für Benutzer mit externem Zugriff in Teams finden Sie unter [Vergleichen von externem und Gastzugriff](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span><span class="sxs-lookup"><span data-stu-id="0e9d9-111">To see a list of capabilities for external access users in Teams, see [Compare external and guest access](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access).</span></span>

## <a name="how-do-i-know-if-im-in-a-native-chat"></a><span data-ttu-id="0e9d9-112">Wie kann ich feststellen, ob ich in einem nativen Chat bin?</span><span class="sxs-lookup"><span data-stu-id="0e9d9-112">How do I know if I'm in a native chat?</span></span>

<span data-ttu-id="0e9d9-113">Wenn Sie nur Text in Ihrem Chat mit einem externen Benutzer austauschen können, befinden Sie sich in einem standardmäßigen externen Zugriff (Federated-Chat).</span><span class="sxs-lookup"><span data-stu-id="0e9d9-113">If you can only exchange text in your chat with an external user, then you're in a standard external-access (federated) chat.</span></span> <span data-ttu-id="0e9d9-114">Wenn Sie alle anderen Chat-Funktionen, einschließlich Formatierung, @Mentions, Emojis usw., haben, sind Sie in einem nativen Teams-Chat mit Ihrem externen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-114">If you've got all of the other chat functionality, including formatting, @mentions, emojis, etc., then you're in a native Teams chat with your external user.</span></span> 

<span data-ttu-id="0e9d9-115">Teams überprüft in regelmäßigen Abständen den Upgrademodus für externe Benutzer, und wenn ein externer Benutzer Teams im TeamsOnly-Aktualisierungsmodus ausführt, werden Sie aufgefordert, zu einem nativen Teamchat zu wechseln und den ursprünglichen Chat zu sperren.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-115">Teams periodically checks the upgrade mode for external users and, when it finds an external user running Teams in the TeamsOnly upgrade mode, it'll prompt you to switch to a native Teams chat and lock the original chat.</span></span>

<span data-ttu-id="0e9d9-116">Wenn Sie zu einem systemeigenen Teamchat wechseln, werden die beiden Konversationen nicht von Teams zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-116">When you switch to a native Teams chat, Teams doesn't merge the two conversations.</span></span> <span data-ttu-id="0e9d9-117">Stattdessen werden beide Chats in Ihrem Chat-Feed angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-117">Instead, you'll see both of the chats in your chat feed.</span></span> <span data-ttu-id="0e9d9-118">Der neue Chat in der systemeigenen Teams ist aktiv, aber der alte, nur-Text-Chat ist gesperrt.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-118">The new, native-Teams chat is active, but the old, text-only chat is locked.</span></span>



## <a name="what-happens-if-a-user-isnt-in-teams-only-mode-anymore"></a><span data-ttu-id="0e9d9-119">Was passiert, wenn sich ein Benutzer nicht mehr im Modus "Teams" befindet?</span><span class="sxs-lookup"><span data-stu-id="0e9d9-119">What happens if a user isn't in Teams Only mode anymore?</span></span>

<span data-ttu-id="0e9d9-120">Wenn Sie einen eigenen Teams-Chat mit einem externen Nutzer führen und dann einer von Ihnen aus dem TeamsOnly-Upgrade-Modus ausgetauscht wird, sperrt Teams den Native Teams-Chat und gibt Ihnen einen Link zu einem limitierten, nur-Text-Chat.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-120">If you were having a native Teams chat with an external user and then one of you gets switched out of the TeamsOnly upgrade mode, Teams locks the native Teams chat and gives you a link for a limited, text-only chat.</span></span> <span data-ttu-id="0e9d9-121">Sie können im Native Teams-Chat nicht fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-121">You won't be able to continue in the native Teams chat.</span></span> <span data-ttu-id="0e9d9-122">Sie können immer noch den Chat in der systemeigenen Teams lesen, aber Sie können die Unterhaltung dort nicht fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-122">You can still read the native Teams chat, but you can't continue the conversation there.</span></span>

<span data-ttu-id="0e9d9-123">Wenn Teams einen alten, nur-Text-Chat mit diesem externen Nutzer findet, wird dieser Chat wieder belebt.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-123">If Teams finds an old text-only chat with this external user, it'll revive that chat.</span></span> <span data-ttu-id="0e9d9-124">Andernfalls erstellt Teams einen neuen, nur-Text-Chat.</span><span class="sxs-lookup"><span data-stu-id="0e9d9-124">Otherwise, Teams creates a new text-only chat.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0e9d9-125">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0e9d9-125">Related topics</span></span>

[<span data-ttu-id="0e9d9-126">Verwalten des externen Zugriffs in Teams</span><span class="sxs-lookup"><span data-stu-id="0e9d9-126">Manage external access in Teams</span></span>](manage-external-access.md)
