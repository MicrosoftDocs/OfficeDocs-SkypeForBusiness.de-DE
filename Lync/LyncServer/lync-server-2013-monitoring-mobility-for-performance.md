---
title: 'Lync Server 2013: Überwachen der Mobilität für Leistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3532a6ebb8d8b095383f0737083d4b070e3aa882
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Überwachen der Mobilität auf Leistung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-14_

Der lync Server Mobilitätsdienst (MCX) und die Unified Communications Web API (UCWA) die Last auf Front-End-Servern und Front-End-Pools zu verbessern. Mobile Geräte, die eine Verbindung mit dem Server auch dann aufrecht erhalten, wenn die Mobile Anwendung minimiert ist, wie etwa Android-und Nokia-Geräte, auf denen lync 2010 Mobile ausgeführt wird, sowie Android-und Apple-Geräte, auf denen lync 2013 Mobile ausgeführt wird, stellen eine höhere Last als Geräte dar, die Beenden Sie die Verbindung mit dem Server, wenn die Mobile Anwendung minimiert ist. Wenn Ihre Mobilitäts Nutzung zunimmt, müssen Sie die Mobilitätsleistung überwachen, um zu ermitteln, wann Sie Ihre Kapazität erhöhen müssen.

Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:

  - Verfügbarer Speicher

  - Anforderungswarteschlangenlimit

  - Gleichzeitige Verbindungen

  - IIS-Warteschlangenlänge

Andere Grenzwerte für Server, die die Mobilitätsleistung beeinflussen können, sind maximal zwölf gleichzeitige Anmeldungen, Authentifizierungen, Sitzungs Verlängerungen und Terminierungen. Diese Maximalwerte müssen für die meisten Bereitstellungen nicht geändert werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Überwachen der Kapazitätsgrenzwerte für Server Speicher in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Überwachen des mobilitätsdiensts und der UCWA Verwendung in lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Konfigurieren des mobilitätsdiensts für hohe Leistung in lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Überwachen von Protokolldateien für die Protokollierung von IIS-Anforderungen in lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Mobilitäts Leistungsindikatoren in lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

