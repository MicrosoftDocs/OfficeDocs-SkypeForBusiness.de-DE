---
title: 'Lync Server 2013: Konfigurieren von Chatrooms'
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
ms.openlocfilehash: 06fea4fcda27eaedd671d833a4f53ed0ddec67c6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730030"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a><span data-ttu-id="e81ca-102">Konfigurieren von Chatrooms in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e81ca-102">Configure rooms in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e81ca-103">_**Letztes Änderungsdatum des Themas:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="e81ca-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="e81ca-104">Die Konfiguration beständiger Chatrooms wird in der Regel von Benutzern oder anderen zentralen Teams mithilfe der Windows PowerShell-Befehlszeilenschnittstelle abgewickelt. ein Administrator verwaltet in der Regel keine Chatrooms.</span><span class="sxs-lookup"><span data-stu-id="e81ca-104">Configuring Persistent Chat rooms is commonly handled by users or other central teams by using Windows PowerShell command-line interface; an administrator typically does not manage chat rooms.</span></span> <span data-ttu-id="e81ca-105">Wenn Sie jedoch Chatrooms erstellen und verwalten müssen, können Sie die Windows PowerShell-Befehlszeilenschnittstelle verwenden oder sich selbst als Mitglied zu einem Chatroom hinzufügen und den lync 2013-Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="e81ca-105">However, if you have to create and manage chat rooms, you can use the Windows PowerShell command-line interface, or add yourself as a member to a chat room and use the Lync 2013 client.</span></span>

<span data-ttu-id="e81ca-106">Weitere Informationen zum Konfigurieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Room Management" in [Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span><span class="sxs-lookup"><span data-stu-id="e81ca-106">For details about configuring chat rooms by using the Windows PowerShell command-line interface, see "Room Management" in [Configuring Persistent Chat Server by using Windows PowerShell cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).</span></span>

<div>

## <a name="managing-data-in-chat-rooms"></a><span data-ttu-id="e81ca-107">Verwalten von Daten in Chatrooms</span><span class="sxs-lookup"><span data-stu-id="e81ca-107">Managing Data in Chat Rooms</span></span>

<span data-ttu-id="e81ca-108">Mit dem Server für beständigen Chat können Benutzer zusammenarbeiten, indem Sie Nachrichten in persistente Chatrooms Posten.</span><span class="sxs-lookup"><span data-stu-id="e81ca-108">Persistent Chat Server lets users collaborate by posting messages into Persistent Chat rooms.</span></span> <span data-ttu-id="e81ca-109">Die Daten werden auf dem Server beibehalten, und die Mitglieder des Raums können auf die Daten zugreifen, einschließlich historischer Daten.</span><span class="sxs-lookup"><span data-stu-id="e81ca-109">The data is persisted on the server, and members of the room can have access to the data, including historical data.</span></span> <span data-ttu-id="e81ca-110">Benutzer mit unterschiedlichen Rollen haben jedoch unterschiedlichen Zugriff auf die beibehaltenen Daten, wie in der folgenden Liste dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e81ca-110">However, users with different roles have different access to the persisted data, as outlined in the following list.</span></span>

  - <span data-ttu-id="e81ca-111">Administratoren können frühere Inhalte aus jedem Chatroom löschen (z. B. Inhalte, die vor einem bestimmen Datum veröffentlicht wurden), um zu verhindern, dass die Datenbanken zu groß werden.</span><span class="sxs-lookup"><span data-stu-id="e81ca-111">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="e81ca-112">Oder Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom als unangemessen erachtet werden.</span><span class="sxs-lookup"><span data-stu-id="e81ca-112">Or, they can remove or replace messages that are considered inappropriate for a particular chat room.</span></span>

  - <span data-ttu-id="e81ca-113">Endbenutzer, einschließlich Autoren von Nachrichten, können keine Inhalte aus Chatrooms entfernen.</span><span class="sxs-lookup"><span data-stu-id="e81ca-113">End users, including message authors, cannot delete content from any chat room.</span></span>

  - <span data-ttu-id="e81ca-114">Chatroom-Manager können Räume deaktivieren, aber nicht löschen.</span><span class="sxs-lookup"><span data-stu-id="e81ca-114">Chat room managers can disable rooms, but cannot delete rooms.</span></span> <span data-ttu-id="e81ca-115">Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e81ca-115">Only administrators can delete a chat room after it has been created.</span></span>

<span data-ttu-id="e81ca-116">Wenn eine Nachricht gelöscht wird, können Sie die Aktion nicht rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="e81ca-116">When a message is deleted, you cannot undo the action.</span></span> <span data-ttu-id="e81ca-117">Gelöschte Nachrichten können jedoch wiederhergestellt werden, wenn eine Sicherung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e81ca-117">However, deleted messages can be restored if there is a backup.</span></span> <span data-ttu-id="e81ca-118">Wenn ein beständiger Chat-Kompatibilitätsserver aktiviert ist, werden alte Nachrichten in der Kompatibilitätsdatenbank beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e81ca-118">If a Persistent Chat Compliance server is enabled, old messages are persisted in the compliance database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e81ca-119">Diese Chatroom-Datenverwendung bezieht sich auf die lync Server 2013, persistent Chat Server-API-Anwendung, mit Ausnahme des Falls, wenn die Administratorrolle involviert ist.</span><span class="sxs-lookup"><span data-stu-id="e81ca-119">This chat room data usage applies to the Lync Server 2013, Persistent Chat Server API application, except for the case when the administrator role is involved.</span></span> <span data-ttu-id="e81ca-120">Die Server-API für beständigen Chat kann nicht zum Ausführen eines Administrator Vorgangs verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e81ca-120">The Persistent Chat Server API cannot be used to do any of the administrator’s operations.</span></span> <span data-ttu-id="e81ca-121">Sie müssen diese Vorgänge in der lync Server-Verwaltungsshell ausführen.</span><span class="sxs-lookup"><span data-stu-id="e81ca-121">You must perform these operations in the Lync Server Management Shell.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

