---
title: 'Lync Server 2013: Sichern von Datenbanken für beständigen Chat'
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
ms.openlocfilehash: 5eec65c22465ee5a2198e7f7147db2d0d014cc2b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523142"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="cef69-102">Sichern von Datenbanken für beständigen Chat in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cef69-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cef69-103">_**Letztes Änderungsstand des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="cef69-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="cef69-104">Inhalt des beständigen Chatrooms wird in der Datenbank für beständigen Chat (MGC. mdf) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cef69-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="cef69-105">Dies sind Geschäfts wichtige Daten, die regelmäßig gesichert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="cef69-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="cef69-106">Zusätzlich zum Chatroom-Inhalt werden in der Datenbank für beständigen Chat auch Informationen über die Prinzipale (wie Benutzer und Benutzergruppen) sowie die Rollen und der Zugriff auf Chatrooms und Chatrooms gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cef69-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="cef69-107">Es gibt zwei Möglichkeiten zum Sichern von Daten für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="cef69-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="cef69-108">SQL Server Sicherung</span><span class="sxs-lookup"><span data-stu-id="cef69-108">SQL Server Backup</span></span>

  - <span data-ttu-id="cef69-109">Das `Export-CsPersistentChatData` Cmdlet, das persistent Chat-Daten als Datei exportiert</span><span class="sxs-lookup"><span data-stu-id="cef69-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="cef69-110">Daten, die mit SQL Server Sicherung erstellt werden, erfordern deutlich mehr Speicherplatz (möglicherweise 20 mal mehr) als die von erstellten `Export-CsPersistentChatData` , aber SQL Server Sicherung ist eher ein Verfahren, mit dem Administratoren vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="cef69-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

