---
title: 'Lync Server 2013: Löschen eines Chatrooms oder einer Kategorie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a chat room or category
ms:assetid: adccb869-0015-4eba-ac73-718bac7843b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215881(v=OCS.15)
ms:contentKeyID: 48706009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74cf41679a21612e67c4a793c09ae3484377ef6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-chat-room-or-category-in-lync-server-2013"></a>Löschen eines Chatrooms oder einer Kategorie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Beständige Chatrooms können gelöscht werden. Wenn Sie über einen Chatroom verfügen, der nicht mehr verwendet wird, können Sie ihn deaktivieren. Ausführliche Informationen finden Sie unter [deaktivieren oder Aktivieren eines Chatrooms in lync Server 2013](lync-server-2013-disabling-or-enabling-a-chat-room.md).

Ein Administrator für beständigen Chat kann nach deaktivierten Chatrooms suchen und die Chatrooms in regelmäßigen Abständen mit dem Windows PowerShell **-Cmdlet Remove-CsPersistentChatRoom**löschen und endgültig löschen.

Kategorien können gelöscht werden. Um eine Kategorie zu löschen, müssen Sie jedoch zunächst entweder alle Chatrooms darunter löschen oder die Chatrooms in eine neue Kategorie verschieben, wodurch eine leere Kategorie zum Löschen bleibt. Mit dem Server für beständigen Chat können Sie keine Kategorie löschen, die Chatrooms enthält. Ausführliche Informationen finden Sie unter [Verschieben eines Chatrooms von einer Kategorie in eine andere in lync Server 2013](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md).

Details zum Löschen von leeren Kategorien mithilfe der Windows PowerShell-Befehlszeilenoberfläche finden Sie unter "roomverwaltung" unter [Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Details zu Chatrooms und Kategorien finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) und [Konfigurieren von Kategorien in lync Server 2013](lync-server-2013-configure-categories.md) in der Bereitstellungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

