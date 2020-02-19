---
title: 'Lync Server 2013: Bereitstelleneiner Survivable Branch Appliance oder eines Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 835a12cb49c8474389b8ae3cc26773fcea2e4157
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-12-10_

Belastbare Enterprise-VoIP bezieht sich auf die Ausfallsicherheit von Zweigstellenstandorten, also auf die Möglichkeit, den Zweigstellenbenutzern kontinuierliche Enterprise-VoIP-Dienste bereitzustellen, falls der Link zum zentralen Standort nicht mehr verfügbar ist.

Für kleine und mittelgroße Zweigstellenstandorte (Zweigstellen mit 25 bis 1.000 Benutzern) wird die Bereitstellungeines Survivable Branch Appliance empfohlen, mit dem das Telefon Festnetz (Public Switched Telephone Network, PSTN) mithilfe des integrierten PSTN-Gateways oder eines SIP-Trunks an ein Telefon beendet wird. Dienstanbieter. Ein Survivable Branch Appliance ist ein Gerät eines Drittanbieters, das einen Blade-Server mit dem Windows Server 2008 R2-Betriebssystem, lync Server 2013 Registrierungsstelle, Vermittlungsserver Software und einem PSTN-Gateway in einem einzigen Gerätegehäuse enthält.

Für Zweigstellen mit 1.000 bis 5.000-Benutzern und ohne ausfallsicheres WAN empfehlen wir eine Survivable Branch Server, die mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefonanbieter verbunden ist. Ein Survivable Branch Server ist ein Windows Server-basierter Computer, auf dem die Registrierungsstellen-und Vermittlungsserver Software installiert ist.

<div>


> [!NOTE]  
> Für Zweigstellenstandorte mit mehr als 5.000 Benutzern und dedizierten lync Server Administratoren wird eine vollständige lync Server 2013-Bereitstellung empfohlen, die sich von der des zentralen Standorts unterscheidet.<BR>Ausführliche Informationen zur Auswahl der besten ausfallsicherheitslösung für die Zweigstellenstandorte in Ihrer Organisation, einschließlich Voraussetzungen und Planungsüberlegungen, finden Sie unter Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Ausfallsicherheit an Zweigstellenstandorten für lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>


> [!NOTE]  
> Benutzer, die in einer lync Server Survivable Branch Appliance verwaltet werden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-zentralen Websiteaufgaben](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Bereitstelleneiner Survivable Branch Appliance oder eines Servers mit lync Server 2013-Branch-Standort Aufgabe](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Privatbenutzer auf einem Survivable Branch Appliance oder Server in lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Anhänge: Survivable Branch Appliances und Server in lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

