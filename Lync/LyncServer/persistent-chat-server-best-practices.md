---
title: Bewährte Methoden für den Server für beständigen Chat
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="d2486-102">Bewährte Methoden für den Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="d2486-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2486-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d2486-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d2486-104">Wenn Sie Ihre Kategorien und beständige Chatrooms erstellen und Ihr Scoping und Ihre Mitgliedschaft entwerfen, können Ihnen die folgenden Tipps bei der Planung helfen:</span><span class="sxs-lookup"><span data-stu-id="d2486-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="d2486-105">Wenn in Ihrem Unternehmen keine ethische Mauer erforderlich ist, schränken Sie den Bereich in der Kategoriestruktur nicht ein.</span><span class="sxs-lookup"><span data-stu-id="d2486-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="d2486-106">Fügen Sie alle Ihre Benutzer in den Bereich einer Kategorie ein, und erstellen Sie alle Chatrooms in dieser Kategorie.</span><span class="sxs-lookup"><span data-stu-id="d2486-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="d2486-107">Verwenden Sie anschließend nur Mitgliedschaftslisten, um den Zugriff auf jeden Chatroom zu gewähren oder einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="d2486-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="d2486-108">In den meisten Fällen sollten Sie es Benutzern ermöglichen, neue Chatrooms zu erstellen, damit Diskussionen zu neuen Themen zu einem beliebigen Zeitpunkt gestartet werden können.</span><span class="sxs-lookup"><span data-stu-id="d2486-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="d2486-109">Machen Sie dies, indem \*\*\*\* Sie die Liste der Ersteller auf die gleiche Weise wie die **AllowedMembers** -Liste erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2486-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="d2486-110">Wenn Sie jedoch nur einem zentralen Support Team oder bestimmten Benutzern das Erstellen von Räumen gestatten möchten, stellen Sie \*\*\*\* die Liste der Ersteller als geeignete Teilmenge dar.</span><span class="sxs-lookup"><span data-stu-id="d2486-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="d2486-111">Geben Sie jedem Chatroom einen vollständigen Namen und eine Beschreibungs Zusammenfassung, die beschreibt, wo er in Ihre Organisation passt.</span><span class="sxs-lookup"><span data-stu-id="d2486-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="d2486-112">Da Benutzer den Kategorienamen nicht sehen können, wenn Sie den Chatroom verwenden, können Sie sich nicht darauf verlassen, dass der Kategorienname Benutzern hilft, das vorgesehene Diskussionsforum für den Chatroom zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="d2486-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="d2486-113">Möglicherweise möchten Sie einen benutzerdefinierten Raum Erstellungs Workflow haben, wenn bestimmte Benennungskonventionen oder andere Zugriffssteuerungen oder Validierungen implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="d2486-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="d2486-114">Mit der Konfiguration für beständigen Chat können Sie die **RoomManagementUrl** auf einen Host anpassen.</span><span class="sxs-lookup"><span data-stu-id="d2486-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="d2486-115">Wenn Benutzer beispielsweise auf **einen Chatroom** in Ihrem lync-Client erstellen klicken, können Sie an Ihre benutzerdefinierte Lösung umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d2486-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="d2486-116">Erstellen Sie eine Vielzahl von Add-Ins, mit denen Sie die Erfahrung von Chatrooms verbessern können, indem Sie andere Geschäftsdaten in Chatrooms einbringen.</span><span class="sxs-lookup"><span data-stu-id="d2486-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="d2486-117">Administratoren müssen die Add-Ins registrieren, die im System zugelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d2486-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="d2486-118">Chatroom-Manager und-Entwickler können aus der Liste der zulässigen Add-Ins für diejenigen auswählen, die für die jeweiligen Chatrooms am relevantesten sind.</span><span class="sxs-lookup"><span data-stu-id="d2486-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d2486-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2486-119">See Also</span></span>


[<span data-ttu-id="d2486-120">Verwalten von Kategorien, Chatrooms und Add-Ins in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2486-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

