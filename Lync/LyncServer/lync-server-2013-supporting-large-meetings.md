---
title: 'Lync Server 2013: unterstützen von umfangreichen Besprechungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d2c36d99bc5af62771aabb643df1223db3a291c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Unterstützen von umfangreichen Besprechungen mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Große Besprechungen folgen nicht dem im vorherigen Abschnitt beschriebenen Testmodell, da Sie die folgenden Merkmale aufweisen:

  - Das Besprechungsformat entspricht einem 1:n-Format.

  - Ein oder wenige Benutzer fungieren als Referenten, und alle anderen Benutzer sind Teilnehmer.

  - Die Freigabe von PowerPoint-Präsentationen stellt die Hauptaktivität hinsichtlich der Datenzusammenarbeit dar.

  - Die Übertragung von Audiosignalen ist erforderlich, Videobilder können ebenfalls übertragen werden.

  - Eine dedizierte Person, im Allgemeinen entweder der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung rechtzeitig ein.

  - Spezielle Mitarbeiter (nicht die Referenten) führen durch die Besprechung, kümmern sich um das Herstellen von Verbindungen zu Onlinebesprechungen, stellen sicher, dass das Teilen von Audio-, Video- und Folieninhalten funktioniert, verwalten den Wartebereich und die Benutzerrollen, schalten Teilnehmer stumm bzw. heben deren Stummschaltung auf, nehmen Fragen entgegen und verwalten Aufzeichnungen nach Bedarf.

Zur Unterstützung von umfangreichen Besprechungen mit bis zu 1000 Benutzern müssen die Probleme im Zusammenhang mit dem freigegebenen Hardwaremodell und dem nicht Reservierungs Modell behoben werden.

Um ausreichende Speicherressourcen sowie die erforderliche CPU-Leistung für Besprechungen mit bis zu 1.000 Teilnehmern bereitstellen zu können, sollten auf dem Front-End-Server, der als Host fungiert, keine anderen Sofortnachrichten-, Anwesenheits- oder Enterprise-VoIP-Arbeitslasten verarbeitet werden. Es sollte auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen. Das bedeutet, dass für das Hosten von Besprechungen mit bis zu 1000 Benutzern ein separater lync Server-Pool eingerichtet werden muss, der für das Hosten von umfangreichen Besprechungen mit bis zu 1000 Benutzern dediziert ist.

Ein lync-Server Pool, der für das Hosten von umfangreichen Besprechungen dediziert ist, sollte nur eine Besprechung mit bis zu 1000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten im Voraus über einen Out-of-Band-Planungsprozess reserviert werden müssen, um eine dedizierte Unterstützung vom Front-End-Serv zu gewährleisten. ERS. Wenn Sie mehrere große Besprechungen gleichzeitig unterstützen möchten, empfiehlt es sich, mehrere dedizierte große Besprechungs Pools einzurichten.

Wir empfehlen, dass eine dedizierte Person den Online-Teil einer groß Besprechung ausführt und überwacht. Diese Person kann je nach den Einstellungen des Unternehmens der Organisator, die Stellvertretung des Organisators oder Referenten oder ein Mitglied des dedizierten Teams für große Besprechungen sein.

In den folgenden Abschnitten wird beschrieben, wie Sie einen dedizierten Pool für umfangreiche Besprechungen implementieren, einschließlich bewährter Methoden für die Verwendung von lync Server 2013 zur Unterstützung großer Besprechungs Szenarien.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Einrichten der Unterstützung für umfangreiche Besprechungen in lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Verwalten von umfangreichen Besprechungen in lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

