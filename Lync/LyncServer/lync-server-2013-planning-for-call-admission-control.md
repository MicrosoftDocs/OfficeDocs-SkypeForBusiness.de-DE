---
title: 'Lync Server 2013: Planung der Anrufsteuerung'
description: 'Lync Server 2013: Planung der Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call admission control (CAC)
ms:assetid: ca367138-adf5-4119-bc40-5ddf335ed22f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398842(v=OCS.15)
ms:contentKeyID: 48185652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: afbc3ca411fcf0a3a1c869a23cddccdb87f09ed6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554311"
---
# <a name="planning-for-call-admission-control-in-lync-server-2013"></a>Planung der Anrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Für UC-Anwendungen (Unified Communications), die IP-basiert sind, wie Telefonie, Video und Anwendungsfreigabe, wird die verfügbare Bandbreite von Unternehmensnetzwerken im Allgemeinen nicht als limitierender Faktor in LAN-Umgebungen betrachtet. Bei WAN-Verbindungen, die Standorte miteinander verbinden, kann die Netzwerkbandbreite jedoch eingeschränkt werden. Wenn ein Zustrom von Netzwerkdatenverkehr eine WAN-Verbindung überzeichnet, werden aktuelle Mechanismen wie Warteschlangen, Pufferung und das Herunterfahren von Paketen verwendet, um die Überlastung zu beheben. Der zusätzliche Datenverkehr wird in der Regel verzögert, bis die Überlastung des Netzwerks oder, falls erforderlich, der Datenverkehr gelöscht wird. Für konventionellen Datenverkehr in solchen Situationen kann der empfangende Client wiederhergestellt werden. Für echtzeitdatenverkehr wie Unified Communications kann die Netzwerküberlastung auf diese Weise nicht aufgelöst werden, da der Unified Communications-Datenverkehr sowohl auf Wartezeit als auch auf Paketverlust reagiert. Überlastung im WAN kann zu einer schlechten Qualität der Benutzerfreundlichkeit (QoE) führen. Für den echtzeitdatenverkehr in überlasteten Bedingungen ist es besser, Anrufe zu verweigern, als Verbindungen mit schlechter Qualität bereitzustellen.

Anrufsteuerung (Call Admission Control, CAC) bestimmt, ob genügend Netzwerkbandbreite vorhanden ist, um eine Echtzeitsitzung mit akzeptabler Qualität einzurichten. In lync Server 2013 steuert die Anrufsteuerung den echtzeitdatenverkehr nur für Audio und Video, wirkt sich jedoch nicht auf den Datenverkehr aus. Wenn der standardmäßige WAN-Pfad nicht über die erforderliche Bandbreite verfügt, kann CAC versuchen, den Anruf über einen Internet Pfad oder das Telefon Festnetz (Public Switched Telephone Network, PSTN) weiterzuleiten. Die Anrufsteuerung ist nur in lync Server verfügbar.

In diesem Abschnitt wird die Funktion zur Anrufsteuerung beschrieben und erläutert, wie die Anrufsteuerung geplant wird.

<div>


> [!NOTE]  
> Lync Server verfügt über drei erweiterte Enterprise-VoIP-Funktionen: Anrufsteuerung (Call Admission Control, CAC), Notrufdienste (E9-1-1) und medienumgehung. Eine Übersicht über die Planungsinformationen, die für alle drei dieser Features verwendet werden, finden Sie unter <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Funktionen in lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Übersicht über die Anrufsteuerung in lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)

  - [Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md)

  - [Beispiel: Sammeln der Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)

  - [Komponenten und Topologien für die Anrufsteuerung in lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md)

  - [Bewährte Methoden für die Anrufsteuerung in lync Server 2013](lync-server-2013-best-practices-for-call-admission-control.md)

  - [Prüfliste für die Bereitstellung der Anrufsteuerung in lync Server 2013](lync-server-2013-deployment-checklist-for-call-admission-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

