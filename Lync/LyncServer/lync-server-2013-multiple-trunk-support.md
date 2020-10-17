---
title: 'Lync Server 2013: Multiple trunk-Unterstützung'
description: 'Lync Server 2013: Multiple trunk Support.'
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
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552421"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Unterstützung mehrerer Trunks in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Lync Server 2013 Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern. Diese Zuordnungen werden durch Definieren eines Trunks vorgenommen, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungsserver Pool und einem PSTN-Gateway (Public Switched Telephone Network), einem SBC (Session Border Controller) oder einer IP-Nebenstellenanlage handelt. Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (Trunks) zu verknüpfen.

  - Um einen trunk in lync Server 2013 zuzuweisen oder zu entfernen, müssen Sie zunächst einen trunk im Topologie-Generator definieren. Ein trunk besteht aus der folgenden Zuordnung: Vermittlungsserver vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN), dem Vermittlungsserver Überwachungsport, dem FQDN des Gateways und dem Überwachungs Port des Gateways.

  - Um mehrere Trunks zu konfigurieren, können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungsserver erstellen. Dies stellt eine zusätzliche Ausfallsicherheit für die Enterprise-VoIP-Infrastruktur dar, was besonders in interoperational-Szenarien mit PBX-Anlagen (Private Branch Exchange) hilfreich ist.

Beim Definieren eines Trunks muss er einer Route zugeordnet werden. Um einen trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den trunk im Topologie-Generator. Dieser einfache Name wird als trunkname in der lync Server-Systemsteuerung verwendet, wobei Trunks Routen zugeordnet werden können. Der Name des einfachen Trunks wird als Gatewayname aus dem lync Server-Verwaltungsshell verwendet.

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungsserver zugeordnet ist. Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugeordneten Vermittlungsserver, und klicken Sie dann auf **Eigenschaften**. Geben Sie das Standardgateway für die Vermittlungsserver an.

Das folgende Diagramm zeigt die mehrere Trunks, die für jede Vermittlungsserver und jedes Gateway definiert sind.

**M-N Trunk-Routing**

![Mehrere trunk Zuordnungen.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Mehrere trunk Zuordnungen.")

</div>

<span> </span>

</div>

</div>

</div>

