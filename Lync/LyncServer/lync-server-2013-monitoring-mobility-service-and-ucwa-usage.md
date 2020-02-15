---
title: 'Lync Server 2013: Überwachen des mobilitätsdiensts und der UCWA-Verwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Mobility Service and UCWA usage
ms:assetid: 8389b37a-ca3e-4047-8b51-85bc07da87e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690025(v=OCS.15)
ms:contentKeyID: 48184683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8fbdd2e411f3613519278f807caed334955810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-mobility-service-and-ucwa-usage-in-lync-server-2013"></a>Überwachen des mobilitätsdiensts und der UCWA Verwendung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-14_

Auf einer kontinuierlichen Basis sollten Sie die CPU und den Arbeitsspeicher überwachen, die vom lync Server Mobilitätsdienst (MCX) und dem Unified Communications Web API (UCWA) verwendet werden. Zum Überwachen der Verwendung können Sie Folgendes verwenden:

**Für Unified Communications Web API (UCWA):**

  - Der **LyncUcwa** -Arbeitsprozess in Internet Information Services (IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.

  - Die Leistungsindikatoren **CPU** und **Prozessor**.

Für die meisten Bereitstellungen sollte die UCWA-CPU-Auslastung im Durchschnitt unter 15 Prozent liegen. Die Arbeitsspeicherauslastung sollte innerhalb der unter [Monitoring for Server Memory Capacity Limits in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)beschriebenen Grenzen liegen.

Zusätzlich zu den Leistungsindikatoren für CPU-und Speicherauslastung können Sie die folgenden Leistungsindikatoren verwenden, um zu ermitteln, wann ein Server mit Anforderungen überladen ist:

  - **Ls: Webserver – Einschränkungs-und\\Authentifizierungs-Webdienst – Gesamtanforderungen in der Verarbeitung**, die die Anzahl der ausstehenden Webanforderungen auf dem Server angibt. Wenn dieser Leistungsindikator 10.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503-Dienst ist nicht verfügbar" fehl.

  - **ASP.net\\-Anforderungen in der Warteschlange** (sollte immer NULL sein).

<div>


> [!NOTE]  
> Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie die Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Prozessorkerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut überarbeiten und neu berechnen.



</div>

**Für den Mobilitätsdienst (MCX):**

  - Die **CSIntMcxAppPool** -und **CSExtMcxAppPool** -Arbeitsprozesse in Internet Information Services (IIS)-Manager. Sehen Sie sich im Bereich **Arbeitsprozesse** die Spalten **CPU %** und **Private Bytes (KB)** an.

  - Die Leistungsindikatoren **CPU** und **Prozessor**.

Für die meisten Bereitstellungen sollte die CPU-Auslastung des mobilitätsdiensts im Durchschnitt unter 15 Prozent liegen. Die Arbeitsspeicherauslastung sollte innerhalb der unter [Monitoring for Server Memory Capacity Limits in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)beschriebenen Grenzen liegen.

Neben den Leistungsindikatoren für die CPU- und Speicherauslastung können Sie anhand der folgenden ASP.NET-Leistungsindikatoren feststellen, ob ein Server mit Anforderungen überlastet ist:

  - **ASP.NET v 2.0.50727\\fordert Current**auf, womit die Anzahl der ausstehenden Webanforderungen auf dem Server angegeben wird. Wenn dieser Leistungsindikator 5.000 erreicht, schlagen nachfolgende Anforderungen mit der Fehlermeldung "503-Dienst ist nicht verfügbar" fehl.

  - **ASP.net\\-Anforderungen in der Warteschlange** (sollte immer NULL sein).

<div>


> [!NOTE]  
> Wenn Sie diese Werte erfüllen oder überschreiten, sollten Sie die Kapazitätsplanung für die richtige Größe der CPU, die Anzahl der Prozessorkerne und den Arbeitsspeicher für die Computer, die die Webdienste hosten, erneut überarbeiten und neu berechnen.



</div>

<div>

## <a name="see-also"></a>Siehe auch


[Überwachen der Kapazitätsgrenzwerte für Server Speicher in lync Server 2013](lync-server-2013-monitoring-for-server-memory-capacity-limits.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

