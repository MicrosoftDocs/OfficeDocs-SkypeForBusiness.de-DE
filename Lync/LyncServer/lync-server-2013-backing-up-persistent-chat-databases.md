---
title: 'Lync Server 2013: Sichern von Datenbanken für beständigen Chat'
description: 'Lync Server 2013: Sichern von Datenbanken für beständigen Chat.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563291"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="db7d8-103">Sichern von Datenbanken für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db7d8-103">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db7d8-104">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="db7d8-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="db7d8-105">Inhalt des beständigen Chatrooms wird in der Datenbank für beständigen Chat (MGC. mdf) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="db7d8-105">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="db7d8-106">Dies sind Geschäfts wichtige Daten, die regelmäßig gesichert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="db7d8-106">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="db7d8-107">Zusätzlich zum Chatroom-Inhalt werden in der Datenbank für beständigen Chat auch Informationen über die Prinzipale (wie Benutzer und Benutzergruppen) sowie die Rollen und der Zugriff auf Chatrooms und Chatrooms gespeichert.</span><span class="sxs-lookup"><span data-stu-id="db7d8-107">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="db7d8-108">Es gibt zwei Möglichkeiten zum Sichern von Daten für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="db7d8-108">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="db7d8-109">SQL Server Sicherung</span><span class="sxs-lookup"><span data-stu-id="db7d8-109">SQL Server Backup</span></span>

  - <span data-ttu-id="db7d8-110">Das `Export-CsPersistentChatData` Cmdlet, das persistent Chat-Daten als Datei exportiert</span><span class="sxs-lookup"><span data-stu-id="db7d8-110">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="db7d8-111">Daten, die mit SQL Server Sicherung erstellt werden, erfordern deutlich mehr Speicherplatz (möglicherweise 20 mal mehr) als die von erstellten `Export-CsPersistentChatData` , aber SQL Server Sicherung ist eher ein Verfahren, mit dem Administratoren vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="db7d8-111">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

