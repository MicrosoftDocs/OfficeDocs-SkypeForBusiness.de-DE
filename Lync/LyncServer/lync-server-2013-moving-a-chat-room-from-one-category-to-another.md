---
title: 'Lync Server 2013: Verschieben eines Chatrooms von einer Kategorie in eine andere'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bde33220c13b5a484f66131ce6090d57d3b9bae
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="4a983-102">Verschieben eines Chatrooms von einer Kategorie in eine andere in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a983-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a983-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4a983-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4a983-104">Es wird empfohlen, die Kategorie eines beständigen Chatrooms nicht zu ändern, nachdem der Chatroom erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a983-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="4a983-105">Wenn der Chatroom-Manager jedoch über **Creator**-Berechtigungen in einer anderen Kategorie verfügt, kann er den Room von einer Kategorie in eine andere verschieben.</span><span class="sxs-lookup"><span data-stu-id="4a983-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="4a983-106">Der Room wird hierbei weder gelöscht noch neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a983-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="4a983-107">Es wird lediglich die Zuordnung in der Datenbank geändert.</span><span class="sxs-lookup"><span data-stu-id="4a983-107">It is a change of association within the database.</span></span>

<span data-ttu-id="4a983-p102">Chatroomkategorien sollten eher selten geändert werden. Eine Kategorie legt die erlaubte Mitgliedschaft für einen Chatroom fest. Wenn also der Chatroom in eine andere Kategorie verschoben wird, werden alle Systemzugriffssteuerungslisten (SACLs) gelöscht, die von der neuen Kategorie nicht unterstützt werden. Wenn beispielsweise ein Benutzer Mitglied eines Chatrooms war und nun kein **AllowedMember** der neuen Kategorie mehr ist, wird die Mitgliedschaft für den Chatroom geändert und der Benutzer aus diesem entfernt.</span><span class="sxs-lookup"><span data-stu-id="4a983-p102">Changing a chat room category should be done rarely. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="4a983-111">Ausführliche Informationen zum Verschieben eines Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="4a983-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="4a983-112">Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [configure Rooms in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4a983-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

