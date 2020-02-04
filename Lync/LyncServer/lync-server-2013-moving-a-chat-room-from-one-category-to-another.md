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
ms.openlocfilehash: 72f9774e53321ff6fe667b3b8c8dcfe0e78bcdaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a><span data-ttu-id="05fe2-102">Verschieben eines Chatrooms von einer Kategorie in eine andere in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05fe2-102">Moving a chat room from one category to another in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05fe2-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="05fe2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="05fe2-104">Wir empfehlen, dass Sie die Kategorie eines beständigen Chatrooms nach dem Erstellen des Chatrooms nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="05fe2-104">We recommend that you do not change the category of a Persistent Chat room after the chat room is created.</span></span> <span data-ttu-id="05fe2-105">Wenn der Chatroom-Manager jedoch über **Creator** -Privilegien in einer anderen Kategorie verfügt, kann er den Chatroom von einer Kategorie in eine andere verschieben.</span><span class="sxs-lookup"><span data-stu-id="05fe2-105">However, if the chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="05fe2-106">Der Raum wird nicht gelöscht und neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="05fe2-106">The room is not deleted and recreated.</span></span> <span data-ttu-id="05fe2-107">Es handelt sich um eine Änderung der Zuordnung innerhalb der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="05fe2-107">It is a change of association within the database.</span></span>

<span data-ttu-id="05fe2-108">Das Ändern einer Chatroom-Kategorie sollte selten erfolgen.</span><span class="sxs-lookup"><span data-stu-id="05fe2-108">Changing a chat room category should be done rarely.</span></span> <span data-ttu-id="05fe2-109">Eine Kategorie bestimmt die zulässige Mitgliedschaft für den Chatroom, sodass beim Verschieben eines Chatrooms in eine andere Kategorie alle Systemzugriffssteuerungslisten (SACLs), die von der neuen Kategorie nicht mehr unterstützt werden, gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="05fe2-109">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="05fe2-110">Wenn ein Benutzer beispielsweise Mitglied des Chatrooms und nicht mehr ein **AllowedMember** in der neuen Kategorie ist, wird die Raummitgliedschaft geändert, und der Benutzer wird aus dem Chatroom entfernt.</span><span class="sxs-lookup"><span data-stu-id="05fe2-110">For example, if a user was a member of the room and is no longer an **AllowedMember** in the new category, the room membership will be modified and the user will be removed from the room.</span></span>

<span data-ttu-id="05fe2-111">Ausführliche Informationen zum Verschieben eines Chatrooms mithilfe der Windows PowerShell-Befehlszeilenoberfläche finden Sie unter "Room Management" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="05fe2-111">For details about moving a chat room by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<span data-ttu-id="05fe2-112">Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="05fe2-112">For details about configuring chat rooms, see [Configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) in the Deployment documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

