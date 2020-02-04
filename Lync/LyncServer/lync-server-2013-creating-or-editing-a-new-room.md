---
title: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Chatrooms'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or editing a new room
ms:assetid: aa8f4349-cfd9-4036-9c4d-de8fb2c4c8a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215880(v=OCS.15)
ms:contentKeyID: 48706008
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bd0fdbce300f417764e093fec3acb8705b2d17b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Erstellen oder Bearbeiten eines neuen Chatrooms in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-03-19_

Die Konfiguration beständiger Chatrooms wird häufig von Benutzern gehandhabt. ein beständiger Chat Administrator konfiguriert oder verwaltet in der Regel keine Chatrooms. Windows PowerShell-Cmdlets zum Verwalten von Räumen stehen nur **CsPersistentChatAdministrator** -Administratoren zur Verfügung.

Benutzer, die in einer bestimmten Kategorie **Schöpfer** sind, können den lync-Client verwenden, um Räume zu erstellen und zu verwalten. Benutzer, die als Manager für einen bestimmten Chatroom festgelegt wurden, können auch die laufende Verwaltung des Raums durchführen, beispielsweise das Bearbeiten der Raumeigenschaften oder der Mitgliedschaft.

<div>


> [!TIP]  
> Administratoren für beständigen Chat können auch Ersteller sein, und Sie unterliegen nicht den Einschränkungen, die den Erstellern auferlegt werden.



</div>

Wenn Sie ein beständiger Chat-Administrator sind, können Sie optional eine Benutzeroberfläche verwenden, um Chatrooms zu erstellen und zu verwalten, anstatt Windows PowerShell-Cmdlets zu verwenden. Aktivieren Sie dazu einen Administrator für beständigen Chat Server, und verwenden Sie dann den lync-Client, um Chatrooms zu erstellen und zu verwalten.

Wenn Sie einen benutzerdefinierten Raum Verwaltungs Workflow für Ihre Benutzer erstellen möchten, können Sie die **RoomManagementUrl** -Eigenschaft für die Konfiguration des beständigen Chat Servers so festlegen, dass Benutzer vom lync-Client zu Ihrer benutzerdefinierten Lösung umgeleitet werden.

Weitere Informationen zum Konfigurieren von Chatrooms mithilfe der Windows PowerShell-Befehlszeilenschnittstelle finden Sie unter "Room Management" in [Konfigurieren des beständigen Chat Servers mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Details zum Konfigurieren von Chatrooms finden Sie unter [Konfigurieren von Räumen in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> Der beständige Chat Server ermöglicht Benutzern, Chatrooms für eine bestimmte Website zu erstellen und zu verwalten. Benutzer können Chatrooms jedoch nicht auf anderen Websites innerhalb derselben Topologie erstellen oder verwalten. Stellen Sie sicher, dass Sie für alle Websites in Ihrer Organisation Chatroom-Ersteller und-Manager angeben.



</div>

<div>


> [!NOTE]  
> Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

</div>

<span> </span>

</div>

</div>

</div>

