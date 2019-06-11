---
title: 'Lync Server 2013: Übersicht über den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Director
ms:assetid: cf9919b3-e16b-47c5-be1d-2c4bc64f44ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398879(v=OCS.15)
ms:contentKeyID: 48185393
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e1c36cd556dcf641acb4571b5bb349466eb278d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-director-in-lync-server-2013"></a>Übersicht über den Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Bei einem Director handelt es sich um einen Server mit lync Server 2013, der Benutzeranforderungen authentifiziert, jedoch keine Benutzerkonten enthält. Optional können Sie einen Director in den beiden folgenden Szenarien bereitstellen:

  - Wenn Sie den Zugriff von externen Benutzern durch die Bereitstellung von Edge-Servern aktivieren, sollten Sie auch einen Director bereitstellen. In diesem Szenario authentifiziert der Director die externen Benutzer und übergibt dann den Datenverkehr an interne Server. Wenn ein Director zur Authentifizierung externer Benutzer verwendet wird, entlastet es Front-End-Pool Server vor dem mehr Aufwand bei der Authentifizierung dieser Benutzer. Darüber hinaus können Sie interne Front-End-Pools vor böswilligem Datenverkehr wie Denial-of-Service-Angriffen isolieren. Wenn das Netzwerk bei einem solchen Angriff mit einem ungültigen externen Datenverkehr überflutet wird, endet dieser Datenverkehr beim Director.

  - Wenn Sie mehrere Front-End-Pools an einem zentralen Standort bereitstellen, indem Sie dieser Website einen Director hinzufügen, können Sie Authentifizierungsanforderungen rationalisieren und die Leistung verbessern. In diesem Szenario gehen alle Anforderungen zuerst an den Director, der Sie dann an den richtigen Front-End-Pool weiterleitet.

</div>

<span> </span>

</div>

</div>

</div>

