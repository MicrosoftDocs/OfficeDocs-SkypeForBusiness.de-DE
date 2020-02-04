---
title: 'Lync Server 2013: Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers'
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
ms.openlocfilehash: ca6fae79854356951701eaf6040fb436e787acd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a>Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-12-10_

Die flexible Enterprise-VoIP-Funktion bezieht sich auf die Flexibilität von Branch-Site, das heißt, die Möglichkeit zum Bereitstellen von kontinuierlichem Enterprise-VoIP-Service für Zweigstellenbenutzer, falls der Link zur zentralen Website nicht mehr zur Verfügung steht.

Für kleine und mittelständische Zweigstellen (Zweigstellen mit 25 bis 1.000 Benutzern) empfehlen wir die Bereitstellung einer Survival-Branch-Appliance, die PSTN-Anrufe (Public Switched Telephone Network) mit dem integrierten PSTN-Gateway oder einem SIP-Trunk zu einem Telefon beendet. Dienstanbieter. Eine Survivable Branch-Appliance ist ein Gerät eines Drittanbieters, das einen Blade-Server mit dem Betriebssystem Windows Server 2008 R2, lync Server 2013 Registrar, Mediation Server-Software und einem PSTN-Gateway umfasst, alles in einem einzigen Appliance-Chassis.

Für Zweigstellen mit 1.000-5.000-Benutzern und kein robustes WAN empfehlen wir einen Überlebenden Branch-Server, der mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen ist. Ein Survivable Branch Server ist ein Windows Server-basierter Computer, auf dem die Registrierungsstelle und die Mediationsserver Software installiert ist.

<div>


> [!NOTE]  
> Für Zweigstellen, die mehr als 5.000-Benutzer und dedizierte lync Server-Administratoren sind, empfehlen wir eine vollständige lync Server 2013-Bereitstellung, die von der des zentralen Standorts getrennt ist.<BR>Ausführliche Informationen zum Auswählen der besten Resilienz-Lösung für die Zweigstellen in Ihrer Organisation, einschließlich Voraussetzungen und Planungsüberlegungen, finden Sie unter Anforderungen an die <A href="lync-server-2013-branch-site-resiliency-requirements.md">Stabilität der Zweigstelle für lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>


> [!NOTE]  
> Benutzer, die sich in einer Überlebenden lync Server-Branch-Appliance befinden, können keine neuen Chatrooms erstellen oder die raumkarte für vorhandene Räume anzeigen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am zentralen Standort](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Bereitstellen einer Survivable Branch Appliance oder eines Survivable Branch Servers mit Lync Server 2013 – Aufgaben am Zweigstellenstandort](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Konfigurieren von Benutzern für Ausfallsicherheit für Zweigstellenstandorte in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Verwalten von Benutzern in einer Survivable Branch Appliance oder auf einem Survivable Branch Server in Lync Server 2013](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [Anhänge: Survivable Branch Appliances und Survivable Branch Server in Lync Server 2013](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

