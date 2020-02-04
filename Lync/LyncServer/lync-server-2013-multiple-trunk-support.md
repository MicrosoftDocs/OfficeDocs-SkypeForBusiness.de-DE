---
title: 'Lync Server 2013: mehrere trunk-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d13ca1a28fd28a6d280ddf3a18e57e09376e668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Mehrere trunk-Unterstützung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Die lync Server 2013-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks erstellt, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungs Server Pool und einem PSTN-Gateway (Public Switched Telephone Network), Sitzungs Grenz Controller (SBC) oder IP-PBX handelt. Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (also Trunks) zu verknüpfen.

  - Um einen trunk in lync Server 2013 zuzuweisen oder zu entfernen, müssen Sie zuerst einen trunk im Topologie-Generator definieren. Ein trunk besteht aus der folgenden Zuordnung: vollständig qualifizierter Domänenname (Fully Qualified Domain Name, FQDN), Mediation Server-Abhör Port, Gateway-FQDN und Gateway-Abhör Port.

  - Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungs Server erstellen. Dies bietet zusätzliche Widerstandsfähigkeit für die Enterprise-VoIP-Infrastruktur, die besonders in interoperational-Szenarien (Private Branch Exchange) verwendet werden kann.

Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den trunk im Topologie-Generator. Dieser einfache Name wird als trunk-Name in der lync Server-Systemsteuerung verwendet, in der Trunks Routen zugeordnet werden können. Der einfache trunk-Name wird als Gateway-Name aus der lync Server-Verwaltungsshell verwendet.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungs Server zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugehörigen Vermittlungs Server, und klicken Sie dann auf **Eigenschaften**. Geben Sie das Standardgateway für den Vermittlungs Server an.

Das folgende Diagramm zeigt die verschiedenen Trunks, die für jeden Vermittlungs Server und jedes Gateway definiert sind.

**M-N trunk-Routing**

![Mehrere trunk Aufgaben.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Mehrere trunk Aufgaben.")

</div>

<span> </span>

</div>

</div>

</div>

