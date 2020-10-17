---
title: Bewährte Methoden für beständigen Chat Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fceea7401a6d5442738a0cc64e9a2bafbfd83827
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500142"
---
# <a name="persistent-chat-server-best-practices"></a>Bewährte Methoden für beständigen Chat Server

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-06_

Wenn Sie Ihre Kategorien und beständige Chatrooms erstellen und Ihr Bereichs-und Mitgliedschafts Design entwerfen, können Ihnen die folgenden Tipps bei der Planung helfen:

  - Wenn in Ihrem Unternehmen keine "Chinesische Mauer" notwendig ist, schränken Sie den Bereich in der Kategoriestruktur nicht ein. Nehmen Sie alle Benutzer in den Bereich einer Kategorie auf, und erstellen Sie alle Chatrooms in dieser Kategorie. Verwenden Sie dann nur Mitgliederlisten, um den Zugriff auf die einzelnen Chatrooms zu erteilen oder zu beschränken.

  - In den meisten Fällen sollten Sie zulassen, dass die Benutzer neue Chatrooms erstellen können. Dann können jederzeit Diskussionen über neue Themen aufgenommen werden. Dazu müssen die Listen **Creators** und **AllowedMembers** identisch sein. Wenn Sie jedoch nur einem zentralen Supportteam oder bestimmten Benutzern das Erstellen von Chatrooms erlauben möchten, sollte die Liste **Creators** die entsprechenden Benutzer enthalten.

  - Geben Sie für jeden Chatroom einen vollständigen Namen und eine zusammenfassende Beschreibung ein, damit die Benutzer den Chatroom innerhalb Ihrer Organisation richtig zuordnen können. Da die Benutzer den Kategorienamen nicht sehen können, wenn sie den Chatroom verwenden, hilft der Kategoriename den Benutzern nicht unbedingt, das vorgesehene Diskussionsforum für den Chatroom zu erkennen.

  - Sie können einen benutzerdefinierten Workflow zum Erstellen von Chatrooms verwenden, falls bestimmte Benennungskonventionen oder sonstige Zugriffssteuerungen oder Überprüfungen implementiert werden müssen. Mit der Konfiguration für beständigen Chat können Sie die **RoomManagementUrl** auf etwas anpassen, das Sie hosten. Wenn Benutzer beispielsweise auf **einen Chatroom** in Ihrem lync-Client erstellen klicken, können Sie zu Ihrer benutzerdefinierten Lösung umgeleitet werden.

  - Sie können eine Vielzahl von Add-Ins erstellen, mit der Sie die Verwendung von Chatrooms optimieren können, indem andere Geschäftsdaten in Chatrooms eingebracht werden. Administratoren müssen die Add-Ins registrieren, die im System zulässig sein sollen. Chatroommanager und -ersteller können in der Liste der zulässigen Add-Ins die für ihre Chatrooms relevantesten Add-Ins auswählen.

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten von Kategorien, Räumen und Add-Ins in lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

