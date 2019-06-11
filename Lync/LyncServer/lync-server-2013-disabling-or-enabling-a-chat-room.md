---
title: 'Lync Server 2013: Deaktivieren oder Aktivieren eines Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a><span data-ttu-id="11f67-102">Deaktivieren oder Aktivieren eines Chatrooms in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11f67-102">Disabling or enabling a chat room in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11f67-103">_**Letztes Änderungsdatum des Themas:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="11f67-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="11f67-104">Wenn das Thema eines beständigen Chatrooms nicht mehr relevant ist, können Sie den Chatroom für Benutzer nicht mehr zur Verfügung stellen, indem Sie ihn deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="11f67-104">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="11f67-105">Wenn ein Chatroom deaktiviert wird, werden alle Mitglieder vom Chatroom getrennt.</span><span class="sxs-lookup"><span data-stu-id="11f67-105">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="11f67-106">Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten und er wird auch nicht bei der Suche nach Chatrooms gefunden.</span><span class="sxs-lookup"><span data-stu-id="11f67-106">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>

<span data-ttu-id="11f67-107">Ein deaktivierter Chatroom kann später von einem Administrator für beständigen Chat aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="11f67-107">A disabled chat room can be enabled later by a Persistent Chat administrator.</span></span> <span data-ttu-id="11f67-108">Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="11f67-108">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="11f67-109">Wenn Sie den Chatroom erneut aktivieren, müssen Sie die Einstellungen nicht manuell erneut erstellen.</span><span class="sxs-lookup"><span data-stu-id="11f67-109">If you enable the room again, you do not need to manually re-create the settings.</span></span>

<span data-ttu-id="11f67-110">Wenn der Verlauf des Chatrooms beibehalten wird (die Dauerhaftigkeit des Chatrooms ist eine optionale Einstellung für eine Kategorie, die für alle Räume innerhalb der Kategorie gilt; die Standardeinstellung ist, dass Sie beibehalten wird, aber deaktiviert werden kann, indem Sie das **Chat-Protokoll** für die Kategorie aktivieren auf false): der Inhalt bleibt erhalten, wenn der Chatroom deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11f67-110">If the chat room’s history persists (chat room history persistence is an optional setting on a category that applies to all rooms within the category; the default is that it is persisted, but can be turned off by setting the category’s **Enable Chat History** to false), the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="11f67-111">Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="11f67-111">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="11f67-112">Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="11f67-112">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span>

<span data-ttu-id="11f67-113">Details zum Deaktivieren und Aktivieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Room Management" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)-Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="11f67-113">For details about disabling and enabling chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span> <span data-ttu-id="11f67-114">Um einen Chatroom zu deaktivieren, verwenden Sie einen ähnlichen Befehl wie den folgenden:</span><span class="sxs-lookup"><span data-stu-id="11f67-114">To disable a chat room, use a command similar to this:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

<span data-ttu-id="11f67-115">Um einen Chatroom zu aktivieren, setzen Sie die Disabled-Eigenschaft auf false:</span><span class="sxs-lookup"><span data-stu-id="11f67-115">To enabled a chat room, set the Disabled property to False:</span></span>

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

<span data-ttu-id="11f67-116">Beachten Sie, dass Chatrooms mithilfe der lync Server-Systemsteuerung nicht aktiviert oder deaktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="11f67-116">Note that chat rooms cannot be enabled or disabled by using the Lync Server Control Panel.</span></span>

<span data-ttu-id="11f67-117">Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="11f67-117">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

