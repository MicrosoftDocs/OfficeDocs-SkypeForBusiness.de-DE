---
title: 'Lync Server 2013: Übersicht über den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55875699e2411527d9202565ae5d31cc72e776f7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Übersicht über den Director in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Bei einem Director handelt es sich um einen Server mit lync Server 2013, der Benutzeranforderungen authentifiziert, jedoch keine Benutzerkonten aufweist. Optional können Sie einen Director in den folgenden beiden Szenarien bereitstellen:

  - Wenn Sie den Zugriff durch externe Benutzer durch die Bereitstellung von Edge-Servern aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario authentifiziert der Director die externen Benutzer und übergibt dann den Datenverkehr an interne Server. Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet Front-End-Pool Server den Aufwand für die Authentifizierung dieser Benutzer. Außerdem können interne Front-End-Pools vor bösartigem Datenverkehr wie Denial-of-Service-Angriffen isoliert werden. Wenn das Netzwerk während eines solchen Angriffs mit ungültigem externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.

  - Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, können Sie die Authentifizierungsanforderungen rationalisieren und die Leistung verbessern, indem Sie einen Director zu dieser Website hinzufügen. In diesem Szenario werden alle Anforderungen zuerst an den Director geleitet, der Sie dann an die richtige Front-End-Pool weiterleitet.

</div>

<span> </span>

</div>

</div>

</div>

