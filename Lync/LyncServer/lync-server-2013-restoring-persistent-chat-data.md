---
title: 'Lync Server 2013: Wiederherstellen beständiger Chat-Daten'
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
ms.openlocfilehash: 5734296a9b3463740b28e6ead33cc64234640432
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Wiederherstellen beständiger Chat-Daten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Beständiger Chatroom-Inhalt wird in der persistent Chat-Datenbank (MGC. mdf) gespeichert. Es handelt sich hierbei um unternehmenswichtige Daten, die regelmäßig gesichert werden sollten. Zusätzlich zu den Chatroom-Inhalten werden Prinzipale (wie Benutzer und Gruppen) und die Rollen und der Zugriff, die Sie für Chatrooms und Chatroom-Inhalte haben, auch in der persistenten Chat-Datenbank gespeichert.

Wie Sie Ihre beständigen Chat-Daten wiederherstellen, hängt von der Methode ab, die Sie zum Sichern verwendet haben.

  - Wenn Sie SQL Server-Sicherungsverfahren verwendet haben, müssen Sie SQL Server-Wiederherstellungsverfahren verwenden.

  - Wenn Sie das Cmdlet **Export-CsPersistentChatData** zum Sichern beständiger Chat-Daten verwendet haben, müssen Sie die Daten mithilfe des Cmdlets **Import-CsPersistentChatData** wiederherstellen.

</div>

<span> </span>

</div>

</div>

</div>

