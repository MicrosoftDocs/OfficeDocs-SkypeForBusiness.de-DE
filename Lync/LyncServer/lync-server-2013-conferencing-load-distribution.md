---
title: Lync Server 2013-Konferenz Lastverteilung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baa8230470fc765bbda7c3b2bf49e6962b3db22f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Verteilung von Konferenz Lasten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Im Gegensatz zu einigen anderen dedizierten Konferenzlösungen handelt es sich bei der lync Server-Architektur um ein freigegebenes Hardwaremodell. Das bedeutet, dass die gleiche Hardware von vielen Softwarekomponenten freigegeben wird, die jeweils unterschiedliche Echtzeitkommunikationen unterstützen. Jede Art von Echtzeitkommunikation platziert bestimmte Lasten auf den Servern. So kann beispielsweise der Front-End-Server die SIP-Routingkomponenten (Session Initiation Protocol), Webanwendungen (wie Adressbuchsuche), Webkonferenzdienst, A/V-Konferenzdienst, Enterprise-VoIP-Anwendungen (beispielsweise die Anwendungs-und reaktionsgruppenanwendung der Konferenzzentrale) und den Vermittlungsserver ausführen. Eine Gruppe von Datenbanken auf dem Front-End-Server bietet auch Speicher und Verarbeitung für Benutzer-, Kontakt-, Anwesenheits-, Konferenz-und VoIP-Routingdaten. Wenn diese Hardware Freigabe, Komponenten, Dienste und Prozesse für CPU-und Arbeitsspeicherressourcen konkurrieren, wirken sich nicht-Konferenz Arbeitslasten direkt auf die Server Skalierung aus.

Im Vergleich zu anderen Hardware-portbasierten Konferenzlösungen ist die lync Server-Konferenz Architektur kein Reservierungs Modell. Wenn ein Benutzer eine Besprechung plant, erstellt lync Server einen Eintrag in der Konferenzdatenbank, in dem Konferenzdaten gespeichert werden, reserviert aber keine Hardwareressourcen für die geplante Besprechung im voraus. Stattdessen verfügt lync Server über integrierte Lastenausgleichs Logik, um Konferenzressourcen auf Front-End-Servern so dynamisch zuzuweisen, dass Lasten gleichmäßig über alle Front-End-Server im Pool verteilt werden. Diese Bestimmungen und nutzt Hardwareressourcen, macht es aber schwierig, sehr große Besprechungen zu unterstützen (insbesondere ohne angemessene Planung). Wenn beispielsweise ein lync Server 2013-Pool nahezu an seiner obersten Kapazität ausgeführt wird, kann jeder Front-End-Server ungefähr 125 Besprechungen mit durchschnittlicher Größe hosten. Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, doch das Hinzufügen einer Besprechung für 1000-Benutzer wäre ein Problem, da die Front-End-Server wahrscheinlich nicht in der Lage sind, eine so große Besprechung zur gleichen Zeit wie die anderen 125-Besprechungen zu unterstützen.

</div>

<span> </span>

</div>

</div>

</div>

