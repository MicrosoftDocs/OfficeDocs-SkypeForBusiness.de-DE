---
title: 'Lync Server 2013: Konfigurieren von Räumen'
description: 'Lync Server 2013: Konfigurieren von Räumen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9f5b2ece8cf436fe69c000da73871cb92686d82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542771"
---
# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="2906d-103">Konfigurieren von Räumen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2906d-103">Configure rooms in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2906d-104">_**Letztes Änderungsstand des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2906d-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2906d-105">Das Konfigurieren von beständigen Chatrooms wird häufig von Benutzern oder anderen zentralen Teams mithilfe Windows PowerShell Befehlszeilenschnittstelle verarbeitet. ein Administrator verwaltet in der Regel keine Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="2906d-105">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="2906d-106">Wenn Sie jedoch Chatrooms erstellen und verwalten müssen, können Sie die Windows PowerShell Befehlszeilenschnittstelle verwenden oder sich selbst als Mitglied zu einem Chatroom hinzufügen und den lync 2013-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="2906d-106">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="2906d-107">Ausführliche Informationen zum Konfigurieren von Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="2906d-107">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="2906d-108">Verwalten von Daten in Chatrooms</span><span class="sxs-lookup"><span data-stu-id="2906d-108">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="2906d-109">Mit dem Server für beständigen Chat können Benutzer zusammenarbeiten, indem Sie Nachrichten in persistent Chatrooms veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="2906d-109">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="2906d-110">Die Daten werden auf dem Server gespeichert, und die Mitglieder des Raums können auf die Daten zugreifen, einschließlich Verlaufsdaten.</span><span class="sxs-lookup"><span data-stu-id="2906d-110">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="2906d-111">Benutzer mit unterschiedlichen Rollen haben jedoch unterschiedlichen Zugriff auf die gespeicherten Daten, wie in der folgenden Liste dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2906d-111">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="2906d-112">Administratoren können frühere Inhalte (beispielsweise Inhalte, die vor einem bestimmten Datum veröffentlicht wurden) aus einem Chatroom löschen, damit die Datenbank nicht zu groß wird.</span><span class="sxs-lookup"><span data-stu-id="2906d-112">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="2906d-113">Oder Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom als unangemessen erachtet werden.</span><span class="sxs-lookup"><span data-stu-id="2906d-113">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="2906d-114">Endbenutzer, einschließlich Nachrichten Autoren, können keine Inhalte aus Chatrooms löschen.</span><span class="sxs-lookup"><span data-stu-id="2906d-114">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="2906d-115">Chatroom-Manager können Räume deaktivieren, aber keine Räume löschen.</span><span class="sxs-lookup"><span data-stu-id="2906d-115">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="2906d-116">Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2906d-116">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="2906d-117">Wenn eine Nachricht gelöscht wird, können Sie die Aktion nicht rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="2906d-117">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="2906d-118">Gelöschte Nachrichten können jedoch wiederhergestellt werden, wenn eine Sicherung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2906d-118">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="2906d-119">Wenn ein Kompatibilitätsserver für beständigen Chat aktiviert ist, werden alte Nachrichten in der Kompatibilitätsdatenbank beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2906d-119">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2906d-120">Diese Chatroom-Datenverwendung gilt für die lync Server 2013, persistent Chat Server-API-Anwendung, außer für den Fall, wenn die Administratorrolle beteiligt ist.</span><span class="sxs-lookup"><span data-stu-id="2906d-120">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="2906d-121">Die Server-API für beständigen Chat kann nicht zur Ausführung von Administrator Vorgängen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2906d-121">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="2906d-122">Sie müssen diese Vorgänge im lync Server-Verwaltungsshell durchführen.</span><span class="sxs-lookup"><span data-stu-id="2906d-122">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

