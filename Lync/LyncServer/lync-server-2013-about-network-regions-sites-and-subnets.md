---
title: 'Lync Server 2013: Informationen zu Netzwerkregionen, Standorten und Subnetzen'
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
ms.openlocfilehash: 1f85d392f7d5f987bf14197fd5027c6568965ae8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>Informationen zu Netzwerkregionen, Standorten und Subnetzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Die in diesem Abschnitt beschriebenen erweiterten Enterprise-VoIP-Features geben bestimmte Konfigurationsanforderungen für netzwerkregionen, Netzwerk Websites und Subnetze frei. Für alle drei erweiterten Features ist es beispielsweise erforderlich, dass jedes Subnetz in Ihrer Topologie einer bestimmten *Netzwerk Website*zugeordnet ist, und jede Netzwerk Website muss einem *Netzwerkbereich*zugeordnet sein.

<div>


> [!IMPORTANT]  
> Bevor Sie mit der Netzwerkkonfiguration für die Anrufsteuerung, E9-1-1 oder Media Bypass beginnen, stellen Sie sicher, dass Sie weitere Informationen zu den Netzwerkeinstellungen in den <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Netzwerkeinstellungen für das erweiterte Enterprise Voice-Feature in lync Server 2013</A> in der Planungsdokumentation überprüft haben. Details zur Netzwerkkonfiguration in erster Linie zur Anrufsteuerung finden Sie auch unter <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Definieren Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013</A> in der Planungsdokumentation.



</div>

Für die Anrufsteuerung und E9-1-1 gelten bei den Netzwerkstandorten zusätzliche Konfigurationsanforderungen:

  - Die Anrufsteuerung erfordert, dass ein *Bandbreitenrichtlinienprofil* für jeden Standort angegeben wird, für den WAN-Bandbreiteneinschränkungen gelten. Wenn Sie beabsichtigen, die Anrufsteuerung bereitzustellen, müssen Sie die [bandbreitenrichtlinienprofile in lync Server 2013 erstellen](lync-server-2013-create-bandwidth-policy-profiles.md) , bevor Sie Ihre Netzwerk Websites konfigurieren.

  - Für E9-1-1 ist es erforderlich, dass für jeden Standort eine *Standortrichtlinie* angegeben ist. Wenn Sie die Bereitstellung von E9-1-1 planen, müssen Sie [in lync Server 2013 Standortrichtlinien erstellen](lync-server-2013-create-location-policies.md) , bevor Sie Ihre Netzwerk Websites konfigurieren.

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>Erstellen oder Ändern von netzwerkregionen, Netzwerk Websites und Subnetzen

Die folgenden Themen enthalten Schritte zum Erstellen oder Ändern von netzwerkregionen und Netzwerk Websites sowie zum Zuordnen von Subnetzen zu Netzwerkstandorten. Diese Themen sind für keine spezielle erweiterte Enterprise-VoIP-Funktion spezifisch.

  - [Erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013](lync-server-2013-create-or-modify-a-network-region.md)

  - [Erstellen oder Ändern eines Netzwerkstandorts in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)

  - [Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

