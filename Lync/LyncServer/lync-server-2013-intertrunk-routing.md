---
title: 'Lync Server 2013: intertrunk-Routing'
description: 'Lync Server 2013: intertrunk-Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Intertrunk routing
ms:assetid: d3a33b4a-8bf4-4a8c-a371-8ef79e740780
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205272(v=OCS.15)
ms:contentKeyID: 48185442
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30c838ee94a2df0807195c172d7e2a3a393523af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553141"
---
# <a name="intertrunk-routing-in-lync-server-2013"></a>Intertrunk-Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

Lync Server 2013 können eine IP-Nebenstellenanlage mit einem PSTN-Gateway (Public Switched Telephone Network) verbinden, sodass Anrufe von einem PBX-Telefon an das PSTN weitergeleitet werden können und eingehende PSTN-Anrufe an ein PBX-Telefon (Private Branch Exchange) weitergeleitet werden können. Auf ähnliche Weise können lync Server 2013 zwei oder mehr IP-PBX-Systeme miteinander verbinden, sodass Anrufe zwischen Nebenstellen Geräten von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.

Dieses intertrunk-Routing Feature kann mithilfe des lync Server-Verwaltungsshell-Cmdlets, " **CsTrunkConfiguration**", mit dem neuen Parameter "PstnUsages" konfiguriert werden. Dieser Parameter gibt die Gruppe der zu verwendenden PSTN-Verwendungsdaten Sätze an. Ein trunk verwendet diese PSTN-Verwendung, um eine Route zu bestimmen und alle eingehenden Anrufe entsprechend weiterzuleiten.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Das folgende Diagramm zeigt lync Server 2013 die Bereitstellung von Verbindungen zwischen einem PSTN-Gateway und einer IP-Nebenstellenanlage.

**Intertrunk-Routing zwischen Gateway und IP-Nebenstellenanlage**

![Lync Server verbinden des PSTN-Gateways/IP-PBX-Diagramms](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server verbinden des PSTN-Gateways/IP-PBX-Diagramms")

Das folgende Diagramm veranschaulicht lync Server 2013 Verbinden von zwei IP-PBX-Systemen.

**Intertrunk-Routing zwischen zwei IP-Nebenstellenanlagen**

![Diagramm für lync Server Verbindung zwischen IP-Pax-Systemen](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Diagramm für lync Server Verbindung zwischen IP-Pax-Systemen")

</div>

<span> </span>

</div>

</div>

</div>

