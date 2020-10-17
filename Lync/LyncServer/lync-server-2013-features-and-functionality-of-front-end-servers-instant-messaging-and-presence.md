---
title: 'Lync Server 2013: Features und Funktionen für Front-End-Server, Instant Messaging und Anwesenheit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26f80eb823af5ec50c18390fe2ebca2b25498874
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515372"
---
# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Features und Funktionen von Front-End-Servern, Chatnachrichten und Anwesenheitsinformationen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-17_

Front-End-Server bieten die meisten lync Server Funktionalität. Es stehen zwei Editionen zur Verfügung: lync Server Enterprise Edition, die in erster Linie für größere Organisationen entwickelt wurde, und lync Server Standard Edition, die in erster Linie für kleinere Organisationen entwickelt wurde, die einen kleineren Hardwareinvestition wünschen und keine hohe Verfügbarkeit erfordern. Beide Editionen unterstützen alle lync Server Arbeitslasten einschließlich Sofortnachrichten, Anwesenheit, Konferenzen und Enterprise-VoIP.

Mit der Sofortnachrichtenfunktion (Instant Messaging, IM) können Benutzer auf ihren Computern in Echtzeit über textbasierte Nachrichten miteinander kommunizieren. Es werden sowohl Sofortnachrichtensitzungen mit zwei Teilnehmern als auch Sitzungen mit mehreren Teilnehmern unterstützt. Ein Teilnehmer an einer Sofortnachrichtensitzung mit zwei Teilnehmern kann der Unterhaltung jederzeit einen dritten Teilnehmer hinzufügen. Wenn dies geschieht, ändert sich das Unterhaltungsfenster, um Konferenzfunktionen zu unterstützen.

<div>


> [!IMPORTANT]
> Lync-und Communicator-Clients werden, wenn Sie an einer Kommunikation mit einem einzelnen beteiligt sind, häufig als Peer-to-Peer bezeichnet. Technisch gesehen kommunizieren die beiden Clients in einer eins-zu-eins-Unterhaltung mit der Instant Messaging-Multipoint-Steuereinheit (IMMCU) in der Mitte. IMMCU ist eine Komponente von Front-End-Server. Wenn Sie die IMMCU in den erforderlichen Kommunikations Workflow einfügen, können Sie die Aufzeichnung von Anrufdetails und andere Features, die der Front-End-Server aktiviert, aktivieren. Die Kommunikation erfolgt über einen dynamischen Quell Port auf dem Client zum Front-End-Server Port TLS/TCP/5061 (vorausgesetzt, dass die empfohlene Transportschichtsicherheit verwendet wird). Die Peer-zu-Peer-Kommunikation (sowie mehr Parteien-Chat) ist nur möglich, wenn lync Server und IMMCU aktiv und verfügbar sind.



</div>

*Presence* stellt Benutzern Informationen über den Status von other im Netzwerk zur Verfügung. Der Anwesenheitsstatus eines Benutzers enthält Informationen, um anderen zu helfen, zu entscheiden, ob Sie versuchen sollen, den Benutzer zu kontaktieren und ob Chat, Telefon oder e-Mail verwendet werden sollen. Anwesenheit fördert die sofortige Kommunikation, wenn möglich, bietet aber auch Informationen darüber, ob sich ein Benutzer in einer Besprechung oder außerhalb des Büros befindet, was bedeutet, dass eine sofortige Kommunikation nicht möglich ist. Dieser Anwesenheitsstatus wird in lync und anderen Anwendungen mit Anwesenheitsinformationen als Anwesenheitssymbol angezeigt, einschließlich des Microsoft Outlook Messaging-und Zusammenarbeits Clients, der Microsoft SharePoint-Technologien, Microsoft Word und Microsoft Excel Tabellenkalkulationssoftware. Das Anwesenheitssymbol stellt die aktuelle Verfügbarkeit und Bereitschaft des Benutzers zur Kommunikation dar.

</div>

<span> </span>

</div>

</div>

</div>

