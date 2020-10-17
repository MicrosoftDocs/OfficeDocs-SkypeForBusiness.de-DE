---
title: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Raums'
description: 'Lync Server 2013: Erstellen oder Bearbeiten eines neuen Raums.'
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
ms.openlocfilehash: d822eb05993f77c57200e29364f0a6a68509450b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562981"
---
# <a name="creating-or-editing-a-new-room-in-lync-server-2013"></a>Erstellen oder Bearbeiten eines neuen Raums in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-03-19_

Das Konfigurieren von beständigen Chatrooms wird häufig von Benutzern verarbeitet. ein Administrator für beständigen Chat konfiguriert oder verwaltet Chatrooms in der Regel nicht. Windows PowerShell-Cmdlets zum Verwalten von Räumen stehen nur **"cspersistentchatadministrator"** -Administratoren zur Verfügung.

Benutzer, die **Ersteller** in einer bestimmten Kategorie sind, können den lync-Client zum Erstellen und Verwalten von Räumen verwenden. Benutzer, die für einen bestimmten Chatroom als Manager bestimmt wurden, können den Chatroom auch fortlaufend verwalten, indem sie beispielsweise dessen Eigenschaften oder Mitgliedschaften bearbeiten.

<div>


> [!TIP]  
> Administratoren für beständigen Chat können auch Ersteller sein, und Sie unterliegen nicht den Einschränkungen, die den Erstellern auferlegt werden.



</div>

Optional können Sie als Administrator für beständigen Chat eine Benutzeroberfläche verwenden, um Chatrooms zu erstellen und zu verwalten, anstatt Windows PowerShell-Cmdlets zu verwenden. Aktivieren Sie dazu einen Administrator für den Server für beständigen Chat, und verwenden Sie dann den lync-Client zum Erstellen und Verwalten von Chatrooms.

Wenn Sie einen benutzerdefinierten Raum Verwaltungs Workflow für Ihre Benutzer erstellen möchten, können Sie die **RoomManagementUrl** -Eigenschaft für die Server Konfiguration für beständigen Chat festlegen, um Benutzer zu Ihrer benutzerdefinierten Lösung vom lync-Client umzuleiten.

Ausführliche Informationen zum Konfigurieren von Chatrooms mithilfe der Befehlszeilenschnittstelle Windows PowerShell finden Sie unter "Raumverwaltung" im Thema [Konfigurieren des Servers für beständigen Chat mithilfe von Windows PowerShell-Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Ausführliche Informationen zum Konfigurieren von Chatrooms finden Sie unter [configure Rooms in lync Server 2013](lync-server-2013-configure-rooms.md) in der Bereitstellungsdokumentation.

<div>


> [!NOTE]  
> Mit dem Server für beständigen Chat können Benutzer Chatrooms für eine bestimmte Website erstellen und verwalten. Benutzer können Chatrooms jedoch nicht an anderen Standorten innerhalb derselben Topologie erstellen oder verwalten. Achten Sie darauf, die Ersteller und Manager für Chatrooms für alle Websites in Ihrer Organisation anzugeben.



</div>

<div>


> [!NOTE]  
> Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

</div>

<span> </span>

</div>

</div>

</div>

