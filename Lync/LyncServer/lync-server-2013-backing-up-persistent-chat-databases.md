---
title: 'Lync Server 2013: Sichern von Datenbanken für beständigen Chat'
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
ms.openlocfilehash: 98d4d69a09ad58d4578c0636f7e6bce54497cb9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Sichern von Datenbanken für beständigen Chat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-17_

Inhalt des beständigen Chatrooms wird in der Datenbank für beständigen Chat (MGC. mdf) gespeichert. Dies sind Geschäfts wichtige Daten, die regelmäßig gesichert werden sollten. Zusätzlich zum Chatroom-Inhalt werden in der Datenbank für beständigen Chat auch Informationen über die Prinzipale (wie Benutzer und Benutzergruppen) sowie die Rollen und der Zugriff auf Chatrooms und Chatrooms gespeichert.

Es gibt zwei Möglichkeiten zum Sichern von Daten für beständigen Chat.

  - SQL Server Sicherung

  - Das `Export-CsPersistentChatData` Cmdlet, das persistent Chat-Daten als Datei exportiert

Daten, die mit SQL Server Sicherung erstellt werden, erfordern deutlich mehr Speicherplatz (möglicherweise 20 mal mehr) als `Export-CsPersistentChatData`die von erstellten, aber SQL Server Sicherung ist eher ein Verfahren, mit dem Administratoren vertraut sind.

</div>

<span> </span>

</div>

</div>

</div>

