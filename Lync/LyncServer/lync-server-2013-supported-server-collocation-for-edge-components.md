---
title: 'Lync Server 2013: Unterstützte Serverkollokation für Edgekomponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3ad78cc1060c64181a75acefa21e64809e0d7b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Unterstützte Serverkollokation für Edgekomponenten in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Der Zugriffs-Edgedienst, der Webkonferenz-Edgedienst, der A/V-Edgedienst und der XMPP-Proxy Dienst sind auf den Edgeserver verfügbar. Die folgenden Server stellen Funktionen bereit, die für den Zugriff durch externe Benutzer erforderlich sind, und müssen als dedizierte Server bereitgestellt werden:

  - Edgeserver

  - Director (optional)

  - Reverseproxy

<div>


> [!IMPORTANT]  
> Der Reverse-Proxy muss nicht nur für die Bereitstellung von lync Server 2013 dediziert sein. So können Sie beispielsweise Dienste bereitstellen, um die lync Server-Webdienste zu veröffentlichen, und gleichzeitig eine veröffentlichte Website für eine andere Website bereitstellen, die überhaupt keine Auswirkungen auf lync Server hat. Wenn Sie bereits über einen Reverse Proxy-Server im Umkreisnetzwerk verfügen, um andere Dienste zu unterstützen, können Sie ihn für lync Server 2013 verwenden.



</div>

</div>

<span> </span>

</div>

</div>

</div>

