---
title: 'Lync Server 2013: Routing zwischen Trunks'
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
ms.openlocfilehash: eaa41fe229e9246506fd92eb9f48767994997e4e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725675"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="intertrunk-routing-in-lync-server-2013"></a>Routing zwischen Trunks in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Lync Server 2013 kann eine IP-Telefonanlage mit einem PSTN-Gateway (Public Switched Telephone Network) verbinden, damit Anrufe von einem PBX-Telefon an das PSTN weitergeleitet werden können, und eingehende PSTN-Anrufe können an ein PBX-Telefon (Private Branch Exchange) weitergeleitet werden. In ähnlicher Weise kann lync Server 2013 zwei oder mehr IP-PBX-Systeme verbinden, damit Anrufe zwischen PBX-Telefonen von den verschiedenen IP-PBX-Systemen getätigt und empfangen werden können.

Dieses intertrunk-Routing Feature kann mithilfe des Cmdlets "lync Server-Verwaltungsshell", " **Satz-CsTrunkConfiguration**", mit dem neuen Parameter PstnUsages konfiguriert werden. Dieser Parameter gibt den Satz der zu verwendenden PSTN-Verwendungsdaten Sätze an. Ein trunk verwendet diese PSTN-Nutzung, um eine Route zu ermitteln und alle eingehenden Anrufe entsprechend weiterzuleiten.

    Set-CsTrunkConfiguration -Identity <TrunkId> -PstnUsages @{add="<UsageString>"}

Das folgende Diagramm veranschaulicht, wie lync Server 2013 die Zusammenschaltung zwischen einem PSTN-Gateway und einer IP-Telefonanlage bereitstellt.

**Intertrunk-Routing zwischen Gateway und IP-PBX**

![Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)](images/JJ721940.cc3858ca-2ee3-4d51-8a51-db078366b50b(OCS.15).jpg "Lync Server: Verbinden von PSTN-Gateway/IP-PBX (Diagramm)")

Das folgende Diagramm zeigt die Verbindung zwischen zwei IP-PBX-Systemen durch lync Server 2013.

**Intertrunk-Routing zwischen zwei IP-PBX-Anlagen**

![Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)](images/JJ721940.6ba18ec9-df70-498a-9cf7-7fc41e5ec432(OCS.15).jpg "Lync Server: Verbinden von IP-PAX-Systemen (Diagramm)")

</div>

<span> </span>

</div>

</div>

</div>

