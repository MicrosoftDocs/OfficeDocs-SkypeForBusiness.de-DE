---
title: 'Lync Server 2013: Konfigurieren von Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08b7cb0146f96b151af021a63ef97a485a0a9dc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Konfigurieren von Chatrooms in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

Die Konfiguration beständiger Chatrooms wird in der Regel von Benutzern oder anderen zentralen Teams mithilfe der Windows PowerShell-Befehlszeilenschnittstelle abgewickelt. ein Administrator verwaltet in der Regel keine Chatrooms. Wenn Sie jedoch Chatrooms erstellen und verwalten müssen, können Sie die Windows PowerShell-Befehlszeilenschnittstelle verwenden oder sich selbst als Mitglied zu einem Chatroom hinzufügen und den lync 2013-Client verwenden.

Weitere Informationen zum Konfigurieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Room Management" in Konfigurieren des beständigen [Chat Servers mithilfe von Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)-Cmdlets.

<div>

## <a name="managing-data-in-chat-rooms"></a>Verwalten von Daten in Chatrooms

Mit dem Server für beständigen Chat können Benutzer zusammenarbeiten, indem Sie Nachrichten in persistente Chatrooms Posten. Die Daten werden auf dem Server beibehalten, und die Mitglieder des Raums können auf die Daten zugreifen, einschließlich historischer Daten. Benutzer mit unterschiedlichen Rollen haben jedoch unterschiedlichen Zugriff auf die beibehaltenen Daten, wie in der folgenden Liste dargestellt.

  - Administratoren können frühere Inhalte aus jedem Chatroom löschen (z. B. Inhalte, die vor einem bestimmen Datum veröffentlicht wurden), um zu verhindern, dass die Datenbanken zu groß werden. Oder Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom als unangemessen erachtet werden.

  - Endbenutzer, einschließlich Autoren von Nachrichten, können keine Inhalte aus Chatrooms entfernen.

  - Chatroom-Manager können Räume deaktivieren, aber nicht löschen. Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.

Wenn eine Nachricht gelöscht wird, können Sie die Aktion nicht rückgängig machen. Gelöschte Nachrichten können jedoch wiederhergestellt werden, wenn eine Sicherung vorhanden ist. Wenn ein beständiger Chat-Kompatibilitätsserver aktiviert ist, werden alte Nachrichten in der Kompatibilitätsdatenbank beibehalten.

<div>


> [!NOTE]  
> Diese Chatroom-Datenverwendung bezieht sich auf die lync Server 2013, persistent Chat Server-API-Anwendung, mit Ausnahme des Falls, wenn die Administratorrolle involviert ist. Die Server-API für beständigen Chat kann nicht zum Ausführen eines Administrator Vorgangs verwendet werden. Sie müssen diese Vorgänge in der lync Server-Verwaltungsshell ausführen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

