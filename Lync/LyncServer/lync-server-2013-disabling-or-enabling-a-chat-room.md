---
title: 'Lync Server 2013: Deaktivieren oder Aktivieren eines Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89862b4f7e38a637fa183641f8cdc75e0491379
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Deaktivieren oder Aktivieren eines Chatrooms in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn das Thema eines beständigen Chatrooms nicht mehr relevant ist, können Sie den Chatroom für Benutzer nicht mehr zur Verfügung stellen, indem Sie ihn deaktivieren. Wenn ein Chatroom deaktiviert wird, werden alle Mitglieder vom Chatroom getrennt. Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten und er wird auch nicht bei der Suche nach Chatrooms gefunden.

Ein deaktivierter Chatroom kann später von einem Administrator für beständigen Chat aktiviert werden. Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten. Wenn Sie den Chatroom erneut aktivieren, müssen Sie die Einstellungen nicht manuell erneut erstellen.

Wenn der Verlauf des Chatrooms beibehalten wird (die Dauerhaftigkeit des Chatrooms ist eine optionale Einstellung für eine Kategorie, die für alle Räume innerhalb der Kategorie gilt; die Standardeinstellung ist, dass Sie beibehalten wird, aber deaktiviert werden kann, indem Sie das **Chat-Protokoll** für die Kategorie aktivieren auf false): der Inhalt bleibt erhalten, wenn der Chatroom deaktiviert ist. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden.

Details zum Deaktivieren und Aktivieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Room Management" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)-Cmdlets. Um einen Chatroom zu deaktivieren, verwenden Sie einen ähnlichen Befehl wie den folgenden:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Um einen Chatroom zu aktivieren, setzen Sie die Disabled-Eigenschaft auf false:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Beachten Sie, dass Chatrooms mithilfe der lync Server-Systemsteuerung nicht aktiviert oder deaktiviert werden können.

Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

