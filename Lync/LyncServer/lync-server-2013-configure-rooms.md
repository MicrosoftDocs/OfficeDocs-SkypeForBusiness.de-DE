---
title: 'Lync Server 2013: Konfigurieren von Räumen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure rooms
ms:assetid: 8956bd2c-c863-4704-bc65-5c0d83556258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205067(v=OCS.15)
ms:contentKeyID: 48184750
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3521e533dee1ff995fae417b8a7f29a75a77ac63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-rooms-in-lync-server-2013"></a>Konfigurieren von Räumen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Das Konfigurieren von beständigen Chatrooms wird häufig von Benutzern oder anderen zentralen Teams mithilfe Windows PowerShell Befehlszeilenschnittstelle verarbeitet. ein Administrator verwaltet in der Regel keine Chatrooms. Wenn Sie jedoch Chatrooms erstellen und verwalten müssen, können Sie die Windows PowerShell Befehlszeilenschnittstelle verwenden oder sich selbst als Mitglied zu einem Chatroom hinzufügen und den lync 2013-Client verwenden.

Ausführliche Informationen zum Konfigurieren von Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

<div>

## <a name="managing-data-in-chat-rooms"></a>Verwalten von Daten in Chatrooms

Mit dem Server für beständigen Chat können Benutzer zusammenarbeiten, indem Sie Nachrichten in persistent Chatrooms veröffentlichen. Die Daten werden auf dem Server gespeichert, und die Mitglieder des Raums können auf die Daten zugreifen, einschließlich Verlaufsdaten. Benutzer mit unterschiedlichen Rollen haben jedoch unterschiedlichen Zugriff auf die gespeicherten Daten, wie in der folgenden Liste dargestellt.

  - Administratoren können frühere Inhalte (beispielsweise Inhalte, die vor einem bestimmten Datum veröffentlicht wurden) aus einem Chatroom löschen, damit die Datenbank nicht zu groß wird. Oder Sie können Nachrichten entfernen oder ersetzen, die für einen bestimmten Chatroom als unangemessen erachtet werden.

  - Endbenutzer, einschließlich Nachrichten Autoren, können keine Inhalte aus Chatrooms löschen.

  - Chatroom-Manager können Räume deaktivieren, aber keine Räume löschen. Nur Administratoren können einen Chatroom löschen, nachdem er erstellt wurde.

Wenn eine Nachricht gelöscht wird, können Sie die Aktion nicht rückgängig machen. Gelöschte Nachrichten können jedoch wiederhergestellt werden, wenn eine Sicherung vorhanden ist. Wenn ein Kompatibilitätsserver für beständigen Chat aktiviert ist, werden alte Nachrichten in der Kompatibilitätsdatenbank beibehalten.

<div>


> [!NOTE]  
> Diese Chatroom-Datenverwendung gilt für die lync Server 2013, persistent Chat Server-API-Anwendung, außer für den Fall, wenn die Administratorrolle beteiligt ist. Die Server-API für beständigen Chat kann nicht zur Ausführung von Administrator Vorgängen verwendet werden. Sie müssen diese Vorgänge im lync Server-Verwaltungsshell durchführen.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

