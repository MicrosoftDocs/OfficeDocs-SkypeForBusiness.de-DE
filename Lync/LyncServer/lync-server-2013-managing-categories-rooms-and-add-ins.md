---
title: 'Lync Server 2013: Verwalten von Kategorien, Chatrooms und Add-Ins'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89d7caadc6ccc4bd7c1030a3e7020129be14a68f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="d5614-102">Verwalten von Kategorien, Chatrooms und Add-Ins in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5614-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="d5614-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="d5614-104">In der lync Server 2013-Systemsteuerung oder mithilfe von Windows PowerShell-Cmdlets können beständige chatadministratoren mithilfe der **beständigen Chat** Seite Kategorien und Add-Ins erstellen. Zum Verwalten beständiger Chatrooms können Administratoren Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5614-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="d5614-105">Wenn der Administrator für beständigen Chat auch SIP-fähig ist, können Sie alternativ den lync-Client verwenden, um eine Webseite zum Erstellen und Verwalten von Chatrooms zu starten.</span><span class="sxs-lookup"><span data-stu-id="d5614-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="d5614-106">In den folgenden Themen wird beschrieben, wie Sie Kategorien und Chatrooms erstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="d5614-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d5614-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d5614-107">In This Section</span></span>

  - [<span data-ttu-id="d5614-108">Erstellen oder Bearbeiten einer neuen Kategorie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="d5614-109">Erstellen oder Bearbeiten eines neuen Chatrooms in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="d5614-110">Erstellen von neuen Add-Ins für Chatrooms in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="d5614-111">Festlegen der Benutzer in Lync Server 2013, die in einem Auditoriumchatroom Nachrichten veröffentlichen können</span><span class="sxs-lookup"><span data-stu-id="d5614-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="d5614-112">Deaktivieren oder Aktivieren eines Chatrooms in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="d5614-113">Verschieben eines Chatrooms von einer Kategorie in eine andere in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="d5614-114">Löschen eines Chatrooms oder einer Kategorie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="d5614-115">Löschen einer Nachricht oder Löschen von veralteten Nachrichten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d5614-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

