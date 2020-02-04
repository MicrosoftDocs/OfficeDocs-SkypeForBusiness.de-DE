---
title: 'Lync Server 2013: Sichern von persistenten Chat Datenbanken'
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
ms.openlocfilehash: f186552b9e0d5c78d0f40416cd92e41d5705e93a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a><span data-ttu-id="ffdb1-102">Sichern von persistenten Chat Datenbanken in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffdb1-102">Backing up Persistent Chat databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffdb1-103">_**Letztes Änderungsdatum des Themas:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="ffdb1-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="ffdb1-104">Beständiger Chatroom-Inhalt wird in der persistent Chat-Datenbank (MGC. mdf) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-104">Persistent Chat room content is stored in the Persistent Chat database (Mgc.mdf).</span></span> <span data-ttu-id="ffdb1-105">Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-105">This is business-critical data that should be backed up regularly.</span></span> <span data-ttu-id="ffdb1-106">Zusätzlich zu den Chatroom-Inhalten speichert die persistente Chat-Datenbank auch Informationen zu den Prinzipalen (wie Benutzer und Benutzergruppen) sowie zu den Rollen und dem Zugriff, die Sie für Chatrooms und Chatrooms haben.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-106">In addition to the chat room content, the Persistent Chat database also stores information about the principals (such as users and user groups), and the roles and access that they have to chat rooms and chat room.</span></span>

<span data-ttu-id="ffdb1-107">Es gibt zwei Möglichkeiten, persistente Chat-Daten zu sichern.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-107">There are two ways of backing up Persistent Chat data.</span></span>

  - <span data-ttu-id="ffdb1-108">Die SQL Server-Sicherung</span><span class="sxs-lookup"><span data-stu-id="ffdb1-108">SQL Server Backup</span></span>

  - <span data-ttu-id="ffdb1-109">Das `Export-CsPersistentChatData` Cmdlet, das persistente Chat-Daten als Datei exportiert</span><span class="sxs-lookup"><span data-stu-id="ffdb1-109">The `Export-CsPersistentChatData` cmdlet, which exports Persistent Chat data as a file</span></span>

<span data-ttu-id="ffdb1-110">Daten, die mit der SQL Server-Sicherung erstellt werden, erfordern erheblich mehr Speicherplatz – möglicherweise 20 mal mehr `Export-CsPersistentChatData`– als die von Ihnen erstellten, aber die SQL Server-Sicherung ist wahrscheinlicher eine Prozedur, mit der Administratoren vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="ffdb1-110">Data that is created by using SQL Server backup requires significantly more disk space—possibly 20 times more—than that created by `Export-CsPersistentChatData`, but SQL Server backup is more likely to be a procedure that administrators are familiar with.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

