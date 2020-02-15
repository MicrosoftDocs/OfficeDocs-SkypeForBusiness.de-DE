---
title: 'Lync Server 2013: Löschen eines Chatrooms oder einer Kategorie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e94068337747feee592ec25669e9d7b5fc10bc3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a><span data-ttu-id="34e1f-102">Löschen eines Chatrooms oder einer Kategorie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34e1f-102">Deleting a chat room or category in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e1f-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="34e1f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="34e1f-104">Räume für beständigen Chatrooms können gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="34e1f-104">Persistent Chat rooms can be deleted.</span></span> <span data-ttu-id="34e1f-105">Wenn ein Chatroom nicht mehr verwendet wird, können Sie ihn deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="34e1f-105">If you have a chat room that is no longer being used, you can disable it.</span></span> <span data-ttu-id="34e1f-106">Ausführliche Informationen finden Sie unter [deaktivieren oder Aktivieren eines Chatrooms in lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span><span class="sxs-lookup"><span data-stu-id="34e1f-106">For details, see [Disabling or enabling a chat room in Lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).</span></span>

<span data-ttu-id="34e1f-107">Ein Administrator für beständigen Chat kann deaktivierte Chatrooms Abfragen und die Chatrooms regelmäßig löschen und endgültig löschen, indem Sie das Windows PowerShell **-Cmdlet Remove-CsPersistentChatRoom**verwenden.</span><span class="sxs-lookup"><span data-stu-id="34e1f-107">A Persistent Chat administrator can query for disabled chat rooms, and can periodically purge and permanently delete the chat rooms, by using the Windows PowerShell cmdlet, **Remove-CsPersistentChatRoom**.</span></span>

<span data-ttu-id="34e1f-108">Kategorien können gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="34e1f-108">Categories can be deleted.</span></span> <span data-ttu-id="34e1f-109">Zum Löschen einer Kategorie müssen Sie jedoch zunächst alle Chatrooms in dieser Kategorie löschen oder die Chatrooms in eine neue Kategorie verschieben, sodass eine leere Kategorie für die Löschung übrig bleibt.</span><span class="sxs-lookup"><span data-stu-id="34e1f-109">However, to delete a category, you must first either delete all chat rooms under it or move the chat rooms to a new category, leaving an empty category for deletion.</span></span> <span data-ttu-id="34e1f-110">Mit dem Server für beständigen Chat können Sie keine Kategorie löschen, die Chatrooms enthält.</span><span class="sxs-lookup"><span data-stu-id="34e1f-110">Persistent Chat Server does not allow you to delete a category that contains chat rooms.</span></span> <span data-ttu-id="34e1f-111">Ausführliche Informationen finden Sie unter [Verschieben eines Chatrooms von einer Kategorie in eine andere in lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span><span class="sxs-lookup"><span data-stu-id="34e1f-111">For details, see [Moving a chat room from one category to another in Lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).</span></span>

<span data-ttu-id="34e1f-112">Ausführliche Informationen zum Löschen leerer Kategorien mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="34e1f-112">For details about deleting empty categories by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="34e1f-113">Ausführliche Informationen zu Chatrooms und Kategorien finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) und [Konfigurieren von Kategorien in lync Server 2013](lync-server-2013-configure-categories.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="34e1f-113">For details about chat rooms and categories, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) and [Configure categories in Lync Server 2013](lync-server-2013-configure-categories.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

