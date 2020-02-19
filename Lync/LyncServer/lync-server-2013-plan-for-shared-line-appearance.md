---
title: 'Lync Server 2013: Planen der Darstellung freigegebener Leitungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Plan for Shared Line Appearance
ms:assetid: a35c83d8-f531-445b-a8d2-d5d8cec77c6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Mt712151(v=OCS.15)
ms:contentKeyID: 72522136
ms.date: 03/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c7b8d66370ef542351f15bdd5f577f29c3a7251
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="plan-for-shared-line-appearance-in-lync-server-2013"></a>Planen der Darstellung freigegebener Leitungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-03-21_

Lesen Sie dieses Thema, um zu erfahren, wie Sie die gemeinsame Darstellung von Leitungen (SLA) in lync Server 2013, Kumulatives Update April 2016, planen.

Die Darstellung freigegebener Leitungen ist ein Feature in lync Server 2013, Kumulatives Update April 2016 für die Verarbeitung mehrerer Anrufe für eine bestimmte Nummer, die als freigegebene Nummer bezeichnet wird. Mit SLA können alle Enterprise-VoIP-aktivierten lync-Benutzer als freigegebene Nummer mit mehreren Zeilen konfiguriert werden, um auf mehrere Anrufe zu reagieren. Die Anrufe werden nicht tatsächlich auf der freigegebenen Nummer empfangen, sondern werden an Benutzer weitergeleitet, die als Stellvertreter für die freigegebene Nummer fungieren. Jeder der Stellvertretungen kann den Anruf annehmen, während der Rest der Stellvertreter eine Benachrichtigung auf seinem Telefon erhält, wer den Anruf abgeholt hat und welche Leitung damit beschäftigt geworden ist. Sowohl die Anzahl der Zeilen als auch die Stellvertretungen können für eine freigegebene Nummer in SLA konfiguriert werden. Darüber hinaus können erweiterte Optionen wie BusyOption (was in einer Situation passiert, wenn alle Zeilen beschäftigt sind) und MissedCallOption (der Fall, in dem keine der Stellvertreter einen Anruf abruft) auch für eine freigegebene Nummer konfiguriert werden.

SLA wird nur auf den folgenden Telefongeräten unterstützt (wird für lync-Clients auf Computern, Mobiltelefonen oder anderen Geräten nicht unterstützt):

  - Polycom VVX300 mit Firmware-Update 5.4.1

  - Polycom VVX400 mit Firmware-Update 5.4.1

  - Polycom VVX500 mit Firmware-Update 5.4.1

  - Polycom VVX600 mit Firmware-Update 5.4.1

SLA ist ein neues Feature in lync Server 2013, Kumulatives Update April 2016.

Informationen zum Bereitstellen von SLA finden Sie unter [Deploy Shared Online Appearance in lync Server 2013](lync-server-2013-deploy-shared-line-appearance.md).

<div>

## <a name="feature-list"></a>Funktionsliste

Das Einrichten einer SLA-Gruppe ermöglicht Folgendes:

  - Alle Stellvertretungen in der Gruppe können eingehende Anrufe an dieselbe freigegebene Nummer beantworten. Die Anrufe können PSTN-basiert oder auf SIP-Basis erfolgen.

  - Stellvertretungen können Anrufe abhalten und annehmen.

  - Delegaten können Anrufe an eine Nummer außerhalb der SLA-Gruppe weiterleiten.

  - Stellvertretungen können sehen, wie viele Anrufe derzeit für die freigegebene Nummer verwendet werden, und den Status jedes dieser Anrufe anzeigen.

  - Sie können eine maximale Anzahl gleichzeitiger Anrufe für die freigegebene Nummer konfigurieren. Sie können auch festlegen, wie zusätzliche Anrufe verarbeitet werden sollen, nachdem dieser Höchstwert erreicht wurde. Überschüssige Anrufe können mit einem Besetztzeichen zurückgewiesen, an eine Alternative Nummer weitergeleitet oder an Voicemail weitergeleitet werden.

  - Sie können konfigurieren, wie verpasste Anrufe (Anrufe, die nach einer bestimmten Zeit nicht aufgenommen wurden) verarbeitet werden sollen. Wenn Sie Voicemail für die Gruppenidentität aktivieren, gehen verpasste Anrufe automatisch zu Voicemail. Wenn für die Gruppenidentität (freigegebene Nummer) keine Voicemail aktiviert ist, können Sie auswählen, dass verpasste Anrufe mit einem Besetztzeichen abgelehnt, an eine Alternative Nummer weitergeleitet oder getrennt werden.

</div>

</div>

<span> </span>

</div>

</div>

</div>

