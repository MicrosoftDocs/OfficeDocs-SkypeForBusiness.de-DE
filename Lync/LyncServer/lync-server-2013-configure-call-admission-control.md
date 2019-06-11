---
title: 'Lync Server 2013: Konfigurieren der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86961c9f282e1a486bf7cf94eda494d37c415cf6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839426"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Konfigurieren der Anrufsteuerung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Anrufannahme Steuerung (CAC) ist eine Lösung, die bestimmt, ob eine Echtzeitsitzung basierend auf der verfügbaren Bandbreite eingerichtet werden kann, um die schlechte Audio-und Videoqualität für Benutzer in überlasteten Netzwerken zu verhindern. CAC steuert den Echtzeitverkehr nur für Audio und Video und hat keinen Einfluss auf den Datenverkehr. CAC kann den Anruf über einen Internet Pfad weiterleiten, wenn der standardmäßige WAN-Pfad nicht die erforderliche Bandbreite aufweist. Ausführliche Informationen finden Sie unter [Planen der Anrufsteuerung in lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) in der Planungsdokumentation.

Dieser Abschnitt enthält eine Reihe von Beispielverfahren, die veranschaulichen, wie CAC in Ihrem Netzwerk bereitgestellt und verwaltet wird.

<div>


> [!IMPORTANT]  
> Bevor Sie CAC bereitstellen, müssen Sie alle erforderlichen Informationen für Ihre Unternehmensnetzwerk Topologie sammeln, wie in <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation beschrieben. Stellen Sie außerdem sicher, dass CAC-Komponenten installiert und aktiviert wurden, wie in der Bereitstellungsdokumentation unter <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definieren und Konfigurieren eines Front-End-Pools oder Standard Edition-Servers in lync Server 2013</A> beschrieben.



</div>

<div>


> [!NOTE]  
> Alle Beispiele für die CAC-Bereitstellung und-Verwaltung in diesem Abschnitt werden mithilfe der lync Server-Verwaltungsshell ausgeführt. Alternativ können Sie auch den Abschnitt <STRONG>Netzwerkkonfiguration</STRONG> der lync Server-Systemsteuerung verwenden, um CAC zu verwalten.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von netzwerkregionen für CAC in lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Erstellen von Bandbreitenrichtlinien Profilen in lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Konfigurieren von Netzwerk Websites für CAC in lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Zuordnen von Subnetzen zu Netzwerkstandorten für CAC in lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Erstellen von Netzwerkbereichs Links in lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Erstellen von Netzwerk interregions-Routen in lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Erstellen von Netzwerk-standortübergreifenden Richtlinien in lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Aktivieren der Anrufsteuerung in lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Checkliste für die Bereitstellung der Anrufsteuerung für lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

