---
title: Testen der lync Server 2013 Skalierbarkeit
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scalability testing
ms:assetid: bf41bac6-d4ec-4de6-9a44-a82d01a87279
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205226(v=OCS.15)
ms:contentKeyID: 48185289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e23cd1bf0382a392cba951d90cd9dfa80c4880
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511012"
---
# <a name="scalability-testing-in-lync-server-2013"></a>Skalierbarkeitstests in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Lync Server 2013 stellt die Server Infrastruktur für alle lync Server Echtzeitkommunikation bereit, einschließlich Instant Messaging (Sofortnachrichten) und Anwesenheit, Konferenzen und Enterprise-VoIP. Dies umfasst alle Features, die die Hardwareressourcen eines lync Server 2013 Pools verwenden und sich daher auf Leistung und Skalierung auswirken. Nicht alle Organisationen verwenden alle Features gleichermaßen.

Einige Organisationen können beispielsweise Videos in Konferenzen sehr stark verwenden, während andere möglicherweise wenig oder gar keine Videonutzung haben. Einige Organisationen bevorzugen PowerPoint-Folien Freigaben für die Anwendungsfreigabe, während andere das Gegenteil bevorzugen. Für Organisationen, die Enterprise-VoIP bereitstellen, wird die Reaktionsgruppenanwendung möglicherweise stark verwendet. In den meisten Organisationen werden Monitoring Server bereitgestellt, aber nicht viele von Ihnen stellen Archivierungsserver bereit. Darüber hinaus verfügen Organisationen nicht alle über die gleichen Infrastrukturen, einschließlich Hardwarekapazitäten, Netzwerkkapazitäten und der Anzahl der bereitgestellten Pools und der Größe von Pools. Die Vielfalt an Features und Infrastrukturen stellt eine Herausforderung für Skalierbarkeitstests dar – es ist nicht möglich, alle möglichen Kombinationen von Features und Infrastrukturen zu simulieren.

Um die Skalierbarkeits Unterstützung für lync Server zu ermitteln, führen wir Tests durch, indem wir alle lync Server Funktionen gleichzeitig verwenden, basierend auf einem durchschnittlichen Verwendungsmodell (Benutzermodell). Zur Bestimmung eines geeigneten Benutzermodells für lync Server Arbeitslasten analysieren wir zahlreiche Datenpunkte, einschließlich Kundenumfragen, Feedback aus dem Microsoft-Programm zur Verbesserung der Benutzerfreundlichkeit, lync Server Nutzungsdaten aus der internen IT-Abteilung bei Microsoft sowie Daten, die aus unserem Live Meeting-Dienst gewonnen wurden. In vielen Fällen ist das Benutzermodell für umfangreichere Auslastungen ausgelegt, um eine bequeme Nutzung innerhalb einer Organisation zu ermöglichen.

In unseren Skalierbarkeitstests richten wir lync Server 2013 Pools gemäß den empfohlenen Hardware-und Software Spezifikationen ein, einschließlich Infrastrukturkomponenten wie Active Directory-Domänendienste, Hardwarelastenausgleich und Firewalls. Wir richten lync Server Umgebungen so nah wie möglich an typischen Umgebungen in der realen Welt ein. Anschließend verwenden wir das lync Server 2013 Stress and Performance-Tool, um lync Server 2013 Lasten zu simulieren (basierend auf unserem Benutzermodell). .

Wir führen die Skalierbarkeitstests mehrmals aus (einschließlich mehrerer dreiwöchiger Testläufe). Die Ergebnisse aller Tests verwenden wir dann zur Leistungsoptimierung und zum Überprüfen der Unterstützung der Skalierbarkeitszahlen in unserem Benutzermodell.

</div>

<span> </span>

</div>

</div>

</div>

