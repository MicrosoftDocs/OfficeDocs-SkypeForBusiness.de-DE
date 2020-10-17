---
title: 'Lync Server 2013: Konfigurieren der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1edac7fe7b3b56cdaa5324f1c6e976bfb0b746fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517662"
---
# <a name="configure-call-admission-control-in-lync-server-2013"></a>Konfigurieren der Anrufsteuerung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Anrufsteuerung (Call Admission Control, CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite erstellt werden kann, um eine schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern. Die Anrufsteuerung steuert den echtzeitdatenverkehr nur für Audio und Video und wirkt sich nicht auf den Datenverkehr aus. CAC kann den Anruf über einen Internet Pfad weiterleiten, wenn der standardmäßige WAN-Pfad nicht über die erforderliche Bandbreite verfügt. Ausführliche Informationen finden Sie unter [Planning for Call Admission Control in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.

Dieser Abschnitt enthält eine Reihe von Beispielverfahren, die veranschaulichen, wie Sie die Anrufsteuerung in Ihrem Netzwerk bereitstellen und verwalten.

<div>


> [!IMPORTANT]  
> Bevor Sie die Anrufsteuerung bereitstellen, müssen Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerk Topologie sammeln, wie unter <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation beschrieben. Stellen Sie außerdem sicher, dass die Komponenten für die Anrufsteuerung installiert und aktiviert wurden, wie unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a Front-End-Pool or Standard Edition-Server in lync Server 2013</A> in der Bereitstellungsdokumentation beschrieben.



</div>

<div>


> [!NOTE]  
> Alle CAC-Bereitstellungs-und-Verwaltungsbeispiele in diesem Abschnitt werden mithilfe der lync Server-Verwaltungsshell ausgeführt. Alternativ können Sie auch den Abschnitt <STRONG>Netzwerkkonfiguration</STRONG> von lync Server-Systemsteuerung verwenden, um die Anrufsteuerung zu verwalten.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Zuordnen von Subnetzen zu Netzwerkstandorten für die Anrufsteuerung in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Erstellen von Netzwerk Regions Links in lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Erstellen von Netzwerk interregions-Routen in lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Erstellen von standortübergreifenden Netzwerkrichtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Aktivieren der Anrufsteuerung in lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Prüfliste zur Bereitstellung der Anrufsteuerung für lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

