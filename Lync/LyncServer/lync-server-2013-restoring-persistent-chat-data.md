---
title: 'Lync Server 2013: Wiederherstellen von Daten für beständigen Chat'
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
ms.openlocfilehash: 38fe2e05629dea4b9194fdc0102d89232c3f6309
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Wiederherstellen von Daten für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-18_

Inhalt des beständigen Chatrooms wird in der Datenbank für beständigen Chat (MGC. mdf) gespeichert. Dies sind Geschäfts wichtige Daten, die regelmäßig gesichert werden sollten. Zusätzlich zu den Chatroom-Inhalten werden Prinzipale (wie Benutzer und Gruppen) und die Rollen und der Zugriff, die Sie für Chatrooms und Chatroom-Inhalte haben, ebenfalls in der Datenbank für beständigen Chat gespeichert.

Wie Sie Ihre Daten für beständigen Chat wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben.

  - Wenn Sie SQL Server Sicherungsverfahren verwendet haben, müssen Sie SQL Server Wiederherstellungsverfahren verwenden.

  - Wenn Sie das Cmdlet **Export-CsPersistentChatData** zum Sichern von Daten für beständigen Chat verwendet haben, müssen Sie das Cmdlet **Import-CsPersistentChatData** verwenden, um die Daten wiederherzustellen.

</div>

<span> </span>

</div>

</div>

</div>

