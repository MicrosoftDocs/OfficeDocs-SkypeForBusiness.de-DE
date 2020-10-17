---
title: 'Lync Server 2013: Informationen zu netzwerkregionen, Standorten und Subnetzen'
description: 'Lync Server 2013: Informationen zu netzwerkregionen, Standorten und Subnetzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c7f660f3c72003527e0721c3f9702865e9b9b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568931"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Informationen zu netzwerkregionen, Standorten und Subnetzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Für die in diesem Abschnitt beschriebenen erweiterten Enterprise-VoIP-Funktionen gelten einige gemeinsame Konfigurationsanforderungen für Netzwerkregionen, Netzwerkstandorte und Subnetze. Beispielsweise ist es für alle drei erweiterten Funktionen erforderlich, dass jedes Subnetz in Ihrer Topologie einem bestimmten *Netzwerkstandort* und jeder Netzwerkstandort einer *Netzwerkregion* zugeordnet wird.

<div>


> [!IMPORTANT]  
> Bevor Sie mit der Netzwerkkonfiguration für die Anrufsteuerung, mit E9-1-1 oder mit der medienumgehung beginnen, stellen Sie sicher, dass Sie in der Planungsdokumentation zusätzliche Informationen zu den Netzwerkeinstellungen im Thema <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für die erweiterten Enterprise-VoIP-Features in lync Server 2013</A> überprüft haben. Ausführliche Informationen zur Netzwerkkonfiguration in erster Linie zur Anrufsteuerung finden Sie auch unter <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren der Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation.



</div>

Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:

  - Die Anrufsteuerung erfordert, dass ein *Bandbreitenrichtlinienprofil* für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten. Wenn Sie die Bereitstellung der Anrufsteuerung planen, müssen Sie [bandbreitenrichtlinienprofile in lync Server 2013 erstellen](lync-server-2013-create-bandwidth-policy-profiles.md) , bevor Sie Ihre Netzwerkstandorte konfigurieren.

  - Für E9-1-1 ist es erforderlich, dass für jeden Standort eine *Standortrichtlinie* angegeben ist. Wenn Sie die Bereitstellung von E9-1-1 planen, müssen Sie [Standortrichtlinien in lync Server 2013 erstellen](lync-server-2013-create-location-policies.md) , bevor Sie Ihre Netzwerkstandorte konfigurieren.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Erstellen oder Ändern von Netzwerkregionen, Netzwerkstandorten und Subnetzen

In den folgenden Themen werden die Schritte zum Erstellen oder Ändern von Netzwerkregionen und Netzwerkstandorten sowie zum Zuordnen von Subnetzen zu Netzwerkstandorten beschrieben. Diese Themen sind nicht auf eine bestimmte erweiterte Enterprise-VoIP-Funktion beschränkt.

  - [Erstellen oder Ändern einer netzwerkregion in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

