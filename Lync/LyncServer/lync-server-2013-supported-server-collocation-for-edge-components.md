---
title: 'Lync Server 2013: unterstützte Server Zusammenstellung für Edge-Komponenten'
description: 'Lync Server 2013: unterstützte Server Zusammenstellung für Edge-Komponenten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported server collocation for edge components
ms:assetid: 435c4dd8-36af-4b71-9b88-3ffcf0fc5c65
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425934(v=OCS.15)
ms:contentKeyID: 48183978
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7bf253e5210e077ca62b3d00f7f130d54d8392a5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556361"
---
# <a name="supported-server-collocation-for-edge-components-in-lync-server-2013"></a>Unterstützte Server Zusammenstellungen für Edge-Komponenten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Der Zugriffs-Edgedienst-, Webkonferenz-Edgedienst-, A/V-Edgedienst-und XMPP-Proxy Dienst befinden sich auf den Edge-Servern. Die folgenden Server bieten für den Zugriff durch externe Benutzer erforderliche Funktionen und müssen als dedizierte Server bereitgestellt werden:

  - Edgeserver

  - Director (optional)

  - Reverseproxy

<div>


> [!IMPORTANT]  
> Der Reverseproxy muss nicht nur für lync Server 2013 reserviert werden. Beispielsweise können Sie Dienste zum Veröffentlichen der lync Server-Webdienste bereitstellen und gleichzeitig eine veröffentlichte Website für eine andere Website bereitstellen, die keinen Einfluss auf lync Server hat. Wenn Sie bereits einen Reverseproxy im Umkreisnetzwerk haben, um andere Dienste zu unterstützen, können Sie ihn für lync Server 2013 verwenden.



</div>

</div>

<span> </span>

</div>

</div>

</div>

