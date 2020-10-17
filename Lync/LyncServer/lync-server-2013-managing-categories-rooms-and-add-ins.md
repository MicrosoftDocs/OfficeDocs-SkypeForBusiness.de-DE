---
title: 'Lync Server 2013: Verwalten von Kategorien, Räumen und Add-ins'
description: 'Lync Server 2013: Verwalten von Kategorien, Räumen und Add-Ins.'
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
ms.openlocfilehash: ba09ed3e021ba24f424d28bbb2c5c379ab975741
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569131"
---
# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="39688-103">Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-103">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39688-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="39688-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="39688-105">In lync Server 2013 Systemsteuerung oder mithilfe von Windows PowerShell-Cmdlets können Administratoren für beständigen Chat die Seite **beständigen** Chat verwenden, um Kategorien und Add-Ins zu erstellen. Für die Verwaltung beständiger Chatrooms können Administratoren Windows PowerShell-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="39688-105">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="39688-106">Wenn der Administrator für beständigen Chat auch SIP-fähig ist, können Sie alternativ den lync-Client verwenden, um eine Webseite zum Erstellen und Verwalten von Chatrooms zu starten.</span><span class="sxs-lookup"><span data-stu-id="39688-106">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="39688-107">In den folgenden Themen wird beschrieben, wie Kategorien und Chatrooms erstellt und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39688-107">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="39688-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="39688-108">In This Section</span></span>

  - [<span data-ttu-id="39688-109">Erstellen oder Bearbeiten einer neuen Kategorie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-109">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="39688-110">Erstellen oder Bearbeiten eines neuen Raums in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-110">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="39688-111">Erstellen von neuen Add-Ins für Chatrooms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-111">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="39688-112">Einstellung, wer Nachrichten in einem Auditorium-Chatroom in lync Server 2013 veröffentlichen kann</span><span class="sxs-lookup"><span data-stu-id="39688-112">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="39688-113">Deaktivieren oder Aktivieren eines Chatrooms in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-113">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="39688-114">Verschieben eines Chatrooms von einer Kategorie in eine andere in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-114">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="39688-115">Löschen eines Chatrooms oder einer Kategorie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-115">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="39688-116">Löschen einer Nachricht oder bereinigen veralteter Nachrichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39688-116">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

