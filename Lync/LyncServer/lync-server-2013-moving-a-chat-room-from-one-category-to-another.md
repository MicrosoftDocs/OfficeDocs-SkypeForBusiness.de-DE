---
title: 'Lync Server 2013: Verschieben eines Chatrooms von einer Kategorie in eine andere'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Verschieben eines Chatrooms von einer Kategorie in eine andere in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wir empfehlen, dass Sie die Kategorie eines beständigen Chatrooms nach dem Erstellen des Chatrooms nicht ändern. Wenn der Chatroom-Manager jedoch über **Creator** -Privilegien in einer anderen Kategorie verfügt, kann er den Chatroom von einer Kategorie in eine andere verschieben. Der Raum wird nicht gelöscht und neu erstellt. Es handelt sich um eine Änderung der Zuordnung innerhalb der Datenbank.

Das Ändern einer Chatroom-Kategorie sollte selten erfolgen. Eine Kategorie bestimmt die zulässige Mitgliedschaft für den Chatroom, sodass beim Verschieben eines Chatrooms in eine andere Kategorie alle Systemzugriffssteuerungslisten (SACLs), die von der neuen Kategorie nicht mehr unterstützt werden, gelöscht werden. Wenn ein Benutzer beispielsweise Mitglied des Chatrooms und nicht mehr ein **AllowedMember** in der neuen Kategorie ist, wird die Raummitgliedschaft geändert, und der Benutzer wird aus dem Chatroom entfernt.

Ausführliche Informationen zum Verschieben eines Chatrooms mithilfe der Windows PowerShell-Befehlszeilenoberfläche finden Sie unter "Room Management" in [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)-Cmdlets.

Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

</div>

<span> </span>

</div>

</div>

</div>

