---
title: 'Lync Server 2013: Unterstützung für große Besprechungen'
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
ms.openlocfilehash: 19359dd785b846fa765e72adb810ccd255c2bd2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523922"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a>Unterstützen großer Besprechungen mit lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-03_

Große Besprechungen folgen nicht dem im vorherigen Abschnitt beschriebenen Testmodell, da Sie die folgenden Merkmale aufweisen:

  - Das Besprechungs Format ist eine 1: n-Präsentation.

  - Ein oder mehrere Benutzer sind Referenten, und alle anderen Personen sind nur als Teilnehmer beteiligt.

  - PowerPoint-Präsentations Freigabe ist die Hauptaktivität der Datenzusammenarbeit.

  - Audio ist erforderlich, und Video kann auch verwendet werden.

  - Eine dedizierte Person, in der Regel entweder der Besprechungsorganisator oder ein Assistent des Organisators, richtet die Besprechung rechtzeitig im Voraus ein.

  - Dedizierte Mitarbeiter (nicht die Referenten) führen die Besprechung aus, einschließlich der Verbindung mit einer Onlinebesprechung, der Überprüfung, ob Audio-, Video-und Folien Freigaben ausgeführt werden, die Verwaltung von Lobby-und Benutzerrollen, das stumm schalten und das stumm schalten von Teilnehmern, das nehmen von Fragen und das Verwalten von Aufzeichnungen, je nach Bedarf.

Die Unterstützung großer Besprechungen mit bis zu 1000 Benutzern erfordert die Behebung der Probleme im Zusammenhang mit dem freigegebenen Hardwaremodell und dem nicht Reservierungs Modell.

Um über ausreichende CPU-und Arbeitsspeicherressourcen für Besprechungen mit bis zu 1000 Benutzern verfügen zu können, sollten die hostenden Front-End-Server keine anderen Chatnachrichten und Anwesenheits-oder Enterprise-VoIP-Arbeitslasten hosten. Es sollte auch keine anderen Besprechungen hosten, unabhängig von der Größe der anderen Besprechungen. Dies bedeutet, dass das Hosten von Besprechungen mit bis zu 1000 Benutzern einen separaten lync Server Pool einrichten muss, der für das Hosten großer Besprechungen mit bis zu 1000 Benutzern vorgesehen ist.

Ein lync Server Pool, der für das Hosten großer Besprechungen vorgesehen ist, sollte nur eine Besprechung mit bis zu 1000 Benutzern gleichzeitig hosten, sodass Besprechungszeiten vorab über einen Out-of-Band-Planungsprozess reserviert werden müssen, um den dedizierten Support von den Front-End-Servern sicherzustellen. Zur gleichzeitigen Unterstützung mehrerer großer Besprechungen wird empfohlen, mehrere dedizierte große Besprechungs Pools einzurichten.

Es wird empfohlen, dass eine dedizierte Person den Online Teil einer großen Besprechung ausführt und überwacht. Diese Person ist möglicherweise der Organisator, Stellvertreter des Organisators oder Referenten oder ein Mitglied des Support Teams für große Besprechungen, je nach den Einstellungen der Organisation.

In den folgenden Abschnitten wird beschrieben, wie Sie einen dedizierten Pool für große Besprechungen implementieren, einschließlich bewährter Methoden für die Verwendung von lync Server 2013 zur Unterstützung großer Besprechungs Szenarien.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Einrichten der Unterstützung für große Besprechungen in lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Verwalten großer Besprechungen in lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

