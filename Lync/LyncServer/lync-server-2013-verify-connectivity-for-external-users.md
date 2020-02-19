---
title: 'Lync Server 2013: Überprüfen der Konnektivität für externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89f1721967ec693556fecd12d31f45b9b3d108d4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a>Überprüfen der Konnektivität für externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Zum Überprüfen der Konnektivität für externe Benutzer müssen Sie sicherstellen, dass sich die Benutzer mit dem Server und mit dem Port für den Zugriffs-Edgedienst verbinden können.

Eine wertvolle Ressource für die Bestätigung Ihrer Konfiguration und die Möglichkeit zum Verbinden, senden und empfangen der richtigen Nachrichten für die Szenarien, die der externe Benutzer Zugriff benötigt, ist die Remote<http://www.testocsconnectivity.com>Connectivity Analyzer-Website (). Die Website wird vom Microsoft-Support verwaltet und verwaltet. Um die Remoteverbindungsanalyse zu verwenden, öffnen Sie die Website in einem Browser, und folgen Sie den Anweisungen zum Auswählen des Szenarios.

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a>Testen der Konnektivität externer Benutzer und des externen Zugriffs

Tests für den Zugriff durch externe Benutzer sollten sämtliche Typen von externen Benutzern umfassen, die von Ihrer Organisation unterstützt werden. Dazu können die folgenden Typen zählen:

  - Benutzer aus mindestens einer Partnerdomäne sowie Testen von IM-, Anwesenheits-, A/V-Funktionen und Desktopfreigabe.

  - Benutzer öffentlicher IM-Dienstanbieter, die von Ihrer Organisation unterstützt werden (und für welche die Bereitstellung abgeschlossen wurde).

  - Anonyme Benutzer.

  - Benutzer innerhalb Ihrer Organisation, die sich remote bei Lync anmelden, jedoch kein VPN verwenden.

Mithilfe dieser Tests wird ermittelt, ob Ihr Edgeserver folgende Aufgaben ausführt:

  - Überwachen der erforderlichen Ports durch Verwendung eines telnet-Clients außerhalb Ihres Netzwerks.
    
      - Beispiel: telnet sip.contoso.com 443
    
      - Ausführen des vorstehenden Tests für Ports, die Sie abhängig von Ihrer Bereitstellung auf dem Edgeserver oder Edgeserverpool verwenden.

  - Ausführen einer präzisen externen DNS-Auflösung.
    
      - Senden Sie von außerhalb Ihres Netzwerks ein Pingsignal an jeden externen FQDN Ihres Edgeservers oder Edgeserverpools. Selbst wenn das Pingen nicht erfolgreich ist, werden die IP-Adressen angezeigt, die Sie mit den von Ihnen zugewiesenen Adressen vergleichen können.

</div>

</div>

<span> </span>

</div>

</div>

</div>

