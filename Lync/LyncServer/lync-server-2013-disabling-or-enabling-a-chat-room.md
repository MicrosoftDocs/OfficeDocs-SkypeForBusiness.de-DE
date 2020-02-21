---
title: 'Lync Server 2013: deaktivieren oder Aktivieren eines Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling or enabling a chat room
ms:assetid: db0908fc-aae3-46e8-bc0b-245e9adfa1e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215883(v=OCS.15)
ms:contentKeyID: 48706011
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74c8c5d1bc78f41d4c1a2694e50fb99b869b9247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-or-enabling-a-chat-room-in-lync-server-2013"></a>Deaktivieren oder Aktivieren eines Chatrooms in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Wenn das Thema eines beständigen Chatrooms nicht mehr relevant ist, können Sie den Chatroom für Benutzer nicht mehr verfügbar machen, indem Sie ihn deaktivieren. Wird ein Chatroom deaktiviert, dann werden alle Mitglieder vom Chatroom getrennt. Nach der Deaktivierung eines Chatrooms können Benutzer dem Chatroom nicht wieder beitreten, und er wird auch nicht bei der Suche nach Chatrooms gefunden.

Ein deaktivierter Chatroom kann später von einem Administrator für beständigen Chat aktiviert werden. Wenn ein Chatroom deaktiviert wurde, bleiben die zugehörigen Mitgliederlisten und sonstigen Einstellungen erhalten. Wenn Sie den Chatroom also wieder aktivieren, müssen Sie die Einstellungen nicht manuell neu erstellen.

Wenn der Verlauf des Chatrooms gespeichert wird (das Speichern des Chatroomverlaufs ist eine optionale Einstellung in einer Kategorie, die für alle Chatrooms innerhalb dieser Kategorie gilt; standardmäßig wird der Verlauf gespeichert, was aber durch Deaktivieren der Option **Chatverlauf aktivieren** für diese Kategorie abgestellt werden kann), bleiben die Inhalte beim Deaktivieren des Chatrooms erhalten. Allerdings werden diese Inhalte in Suchvorgängen nicht angezeigt, solange der Chatroom deaktiviert ist. Wenn Sie den Chatroom später wieder aktivieren, können Benutzer nach Nachrichten suchen, die vor der Deaktivierung des Chatrooms bereitgestellt wurden.

Ausführliche Informationen zum Deaktivieren und Aktivieren von Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md). Verwenden Sie einen Befehl wie den folgenden, um einen Chatroom zu deaktivieren:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $True

Um einen Chatroom zu aktivieren, legen Sie die Disabled-Eigenschaft auf false fest:

    Set-CsPersistentChatRoom -Identity "atl-cs-001.litwareinc.com\ITChatRoom" -Disabled $False

Beachten Sie, dass Chatrooms nicht mithilfe der lync Server-Systemsteuerung aktiviert oder deaktiviert werden können.

Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [configure Rooms in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

