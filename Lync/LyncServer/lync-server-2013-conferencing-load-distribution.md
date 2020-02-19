---
title: Lync Server 2013 der Verteilung von Konferenz Lasten
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
ms.openlocfilehash: b37c61be4d715751b18581c643babfddae06ea5e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Verteilung von Konferenz Lasten in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

Im Gegensatz zu anderen dedizierten Konferenzlösungen ist lync Server Architektur ein freigegebenes Hardwaremodell. Dies bedeutet, dass die gleiche Hardware von vielen Softwarekomponenten gemeinsam genutzt wird, von denen jede andere Echtzeitkommunikation unterstützt. Jeder Typ von Echtzeitkommunikation stellt bestimmte Lasten auf den Servern. Beispielsweise können die Front-End-Server die SIP-Routingkomponenten (Session Initiation Protocol), Webanwendungen (wie Adressbuchsuche), Webkonferenzdienst, A/V-Konferenzdienst, Enterprise-VoIP-Anwendungen (beispielsweise Konferenzzentrale und Reaktionsgruppenanwendung) und Vermittlungsserver ausführen. Eine Gruppe von Datenbanken im Front-End-Server bieten auch Speicherung und Verarbeitung für Benutzer-, Kontakt-, Anwesenheits-, Konferenz-und VoIP-Routingdaten. Mit dieser Hardware Teilung konkurrieren Komponenten, Dienste und Prozesse um CPU-und Arbeitsspeicherressourcen, sodass nicht-Konferenz Arbeitslasten direkte Auswirkungen auf die Server Skalierung haben.

Im Vergleich zu anderen Konferenzlösungen mit Port basierter Hardware ist lync Server Konferenz Architektur kein Reservierungs Modell. Wenn ein Benutzer eine Besprechung plant, erstellt lync Server einen Datensatz in der Konferenzdatenbank, in dem Konferenzdaten gespeichert werden, reserviert jedoch keine Hardwareressourcen für die geplante Besprechung im voraus. Stattdessen verfügt lync Server über integrierte Lastenausgleichs Logik zum dynamischen Zuordnen von Konferenzressourcen auf Front-End-Servern auf eine Weise, die Lasten gleichmäßig auf alle Front-End-Server im Pool verteilt. Dadurch werden Hardwareressourcen effektiv bereitgestellt und verwendet, es stellt jedoch eine Herausforderung dar, sehr große Besprechungen (insbesondere ohne entsprechende Planung) zu unterstützen. Wenn beispielsweise ein lync Server 2013-Pool knapp an seiner Spitzenkapazität liegt, kann jeder Front-End-Server ungefähr 125 Besprechungen mit durchschnittlicher Größe hosten. Das Hinzufügen einer weiteren kleinen Besprechung wäre kein Problem, aber das Hinzufügen einer Besprechung für 1000 Benutzer würde ein Problem sein, da die Front-End-Server eine solche große Besprechung möglicherweise nicht gleichzeitig mit den anderen 125-Besprechungen unterstützen können.

</div>

<span> </span>

</div>

</div>

</div>

