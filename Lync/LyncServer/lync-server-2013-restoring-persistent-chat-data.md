---
title: 'Lync Server 2013: Wiederherstellen von Daten für beständigen Chat'
description: 'Lync Server 2013: Wiederherstellen von Daten für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c75683e151daaadab8374ed5b41886da9a3aea3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575516"
---
# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a><span data-ttu-id="b0355-103">Wiederherstellen von Daten für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0355-103">Restoring Persistent Chat data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0355-104">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="b0355-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="b0355-105">Inhalt des beständigen Chatrooms wird in der Datenbank für beständigen Chat (MGC. mdf) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b0355-105">Persistent Chat room content is stored in the Persistent Chat database (mgc.mdf).</span></span> <span data-ttu-id="b0355-106">Dies sind Geschäfts wichtige Daten, die regelmäßig gesichert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="b0355-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="b0355-107">Zusätzlich zu den Chatroom-Inhalten werden Prinzipale (wie Benutzer und Gruppen) und die Rollen und der Zugriff, die Sie für Chatrooms und Chatroom-Inhalte haben, ebenfalls in der Datenbank für beständigen Chat gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b0355-107">In addition to the chat room content, principals (such as users and groups) and the roles and access that they have to chat rooms and chat room content, is also stored in the Persistent Chat database.</span></span>

<span data-ttu-id="b0355-108">Wie Sie Ihre Daten für beständigen Chat wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="b0355-108">How you restore your Persistent Chat data depends on the method that you used to back it up.</span></span>

  - <span data-ttu-id="b0355-109">Wenn Sie SQL Server Sicherungsverfahren verwendet haben, müssen Sie SQL Server Wiederherstellungsverfahren verwenden.</span><span class="sxs-lookup"><span data-stu-id="b0355-109">If you used SQL Server backup procedures, you must use SQL Server restore procedures.</span></span>

  - <span data-ttu-id="b0355-110">Wenn Sie das Cmdlet **Export-CsPersistentChatData** zum Sichern von Daten für beständigen Chat verwendet haben, müssen Sie das Cmdlet **Import-CsPersistentChatData** verwenden, um die Daten wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="b0355-110">If you used the **Export-CsPersistentChatData** cmdlet to back up Persistent Chat data, then you must use the **Import-CsPersistentChatData** cmdlet to restore the data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

