---
title: 'Lync Server 2013: Überwachen der Mobilität für die Leistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring mobility for performance
ms:assetid: 9c831c63-9a7d-48ec-9118-f8a7e80ddd04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690033(v=OCS.15)
ms:contentKeyID: 48184908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3b6cbdefcb7c78f68fe8838109dea3be5b8203d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-for-performance-in-lync-server-2013"></a>Überwachen der Mobilität für die Leistung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-14_

Der lync Server Mobility Service (MCX) und die Unified Communications Web-API (UCWA) erhöhen die Auslastung von Front-End-Servern und Front-End-Pools. Mobile Geräte, die eine Verbindung mit dem Server beibehalten, auch wenn die Mobile Anwendung minimiert ist, wie etwa Android-und Nokia-Geräte mit lync 2010 Mobile sowie Android-und Apple-Geräte, auf denen lync 2013 Mobile ausgeführt wird, stellen eine größere Belastung als Geräte dar, die die Verbindung zum Server wird beendet, wenn die Mobile Anwendung minimiert wird. Nimmt die Nutzung der Mobilitätsdienste zu, müssen Sie die Mobilitätsleistung überwachen, um festzustellen, ob die Kapazität erhöht werden muss.

Die Mobilitätsleistung wird durch mehrere Limits beeinflusst:

  - Verfügbarer Speicher

  - Anforderungswarteschlangenlimit

  - Gleichzeitige Verbindungen

  - IIS-Warteschlangenlänge

Andere Grenzwerte für Server, die die Mobilitätsleistung beeinflussen können, sind maximal zwölf gleichzeitige Anmeldungen, Authentifizierungen, Sitzungs Verlängerungen und Kündigungen. Diese Höchstwerte müssen für die meisten Bereitstellungen nicht geändert werden.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Überwachen der Speicher Kapazitätsgrenzwerte von Servern in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)

  - [Überwachen des mobilitätsdiensts und der UCWA-Verwendung in lync Server 2013](lync-server-2013-monitoring-mobility-service-and-ucwa-usage.md)

  - [Konfigurieren des mobilitätsdiensts für die Höchstleistung in lync Server 2013](lync-server-2013-configuring-mobility-service-for-high-performance.md)

  - [Überwachen von IIS-Anforderungs Protokollierungs Protokolldateien in lync Server 2013](lync-server-2013-monitoring-iis-request-tracing-log-files.md)

  - [Mobilitäts Leistungsindikatoren in lync Server 2013](lync-server-2013-mobility-performance-counters.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

