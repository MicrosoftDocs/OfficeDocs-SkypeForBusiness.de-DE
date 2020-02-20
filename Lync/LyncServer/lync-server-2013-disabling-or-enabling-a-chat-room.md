---
title: 'Lync Server 2013: deaktivieren oder Aktivieren eines Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96ad55bd6396cdac9b30441eb8b41bebaba834ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="89902-102">Deaktivieren oder Aktivieren eines Chatrooms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89902-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89902-103">_**Letztes Änderungsstand des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="89902-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="89902-104">Wenn das Thema eines beständigen Chatrooms nicht mehr relevant ist, können Sie den Chatroom für Benutzer nicht mehr verfügbar machen, indem Sie ihn deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="89902-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="89902-105">Wird ein Chatroom deaktiviert, dann werden alle Mitglieder vom Chatroom getrennt.</span><span class="sxs-lookup"><span data-stu-id="89902-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="89902-106">Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten, und er wird auch nicht bei der Suche nach Chatrooms gefunden.</span><span class="sxs-lookup"><span data-stu-id="89902-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="89902-107">Ein deaktivierter Chatroom kann später von einem Administrator für beständigen Chat aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="89902-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="89902-108">Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="89902-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="89902-109">Wenn Sie den Chatroom also wieder aktivieren, müssen Sie die Einstellungen nicht manuell neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89902-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="89902-p103">Wenn der Verlauf des Chatrooms gespeichert wird (das Speichern des Chatroomverlaufs ist eine optionale Einstellung in einer Kategorie, die für alle Chatrooms innerhalb dieser Kategorie gilt; standardmäßig wird der Verlauf gespeichert, was aber durch Deaktivieren der Option **Chatverlauf aktivieren** für diese Kategorie abgestellt werden kann), bleiben die Inhalte beim Deaktivieren des Chatrooms erhalten. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="89902-p103">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled. However, that content will not appear in searches during the time that the chat room remains in a disabled state. If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="89902-113">Ausführliche Informationen zum Deaktivieren und Aktivieren von Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="89902-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="89902-114">Verwenden Sie einen Befehl wie den folgenden, um einen Chatroom zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="89902-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="89902-115">Um einen Chatroom zu aktivieren, legen Sie die Disabled-Eigenschaft auf false fest:</span><span class="sxs-lookup"><span data-stu-id="89902-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="89902-116">Beachten Sie, dass Chatrooms nicht mithilfe der lync Server-Systemsteuerung aktiviert oder deaktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="89902-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="89902-117">Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [configure Rooms in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="89902-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

