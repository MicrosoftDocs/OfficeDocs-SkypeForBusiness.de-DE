---
title: 'Lync Server 2013: Konfigurieren des mobilitätsdiensts für eine höhere Leistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Mobility Service for high performance
ms:assetid: c2b8aadb-cffb-49f0-ba7a-e8541a1ff475
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690042(v=OCS.15)
ms:contentKeyID: 48185332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29eaea1e45c5d3b745debbc2f97370a76e6d16db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-service-for-high-performance-in-lync-server-2013"></a>Konfigurieren des mobilitätsdiensts für die Höchstleistung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-17_

<div>


> [!IMPORTANT]  
> Dieses Thema bezieht sich nur auf den lync Server 2013 Mobility Service (MCX) und gilt nicht für Unified Communications Web API (UCWA), wie Sie in den kumulativen Updates für lync Server 2013: Februar 2013 bereitgestellt werden.



</div>

Wenn Sie den Mobilitätsdienst (MCX) auf Internet Informationsdienste (IIS) 7,5 installieren, konfiguriert das Mobilitätsdienst-Installationsprogramm einige Leistungseinstellungen auf dem Front-End-Server. Es wird empfohlen, IIS 7.5 für die Mobilität zu verwenden. Diese Einstellungen wirken sich auf die maximale Anzahl gleichzeitiger Benutzeranforderungen und die maximale Anzahl von Threads aus, die für den Mobilitätsdienst zulässig sind.

Die Leistungseinstellungen lauten wie folgt:

<div>

## <a name="settings-for-mcx-on-iis-75"></a>Einstellungen für Mcx auf IIS 7.5

1.  **maxConcurrentThreadsPerCPU** ist auf null (0) gesetzt.

2.  **maxConcurrentRequestsPerCPU** ist auf null (0) gesetzt.

3.  Das ASP.NET-Prozessmodell ist auf AutoConfig (nur für IIS 7.5) gesetzt.

4.  Das Limit für die HTTP.SYS-Warteschlange ist standardmäßig auf 1.000 gesetzt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

