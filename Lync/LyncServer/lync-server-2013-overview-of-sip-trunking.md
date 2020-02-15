---
title: 'Lync Server 2013: Übersicht über das SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of SIP trunking
ms:assetid: 204f2c21-436f-4b2d-93ea-d6db98fa2952
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398285(v=OCS.15)
ms:contentKeyID: 48183601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbf29b02af831f82050e9a032a35f0fa57c1eb1e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046248"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-sip-trunking-in-lync-server-2013"></a>Übersicht über das SIP-Trunking in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-05_

Die Bereitstellung von SIP-Trunking kann die Telefonkommunikation in Ihrer Organisation deutlich vereinfachen und stellt gleichzeitig eine Vorbereitung auf die neuesten Funktionen für die Echtzeitkommunikation dar. Einer der Hauptvorteile beim SIP-Trunking besteht darin, dass Sie PSTN-Verbindungen (Public Switched Telephone Network, Telefonfestnetz) an einem zentralen Standort in Ihrer Organisation konsolidieren können – im Gegensatz zum Vorgänger, dem Legacy-TDM (Time Division Multiplexing)-Trunking, das in der Regel einen separaten Trunk für jeden Zweigstellenstandort erfordert.

<div>

## <a name="sip-trunking-in-lync-server"></a>SIP-Trunking in Lync Server

Die lync Server 2013 SIP-Trunking-Funktionen ermöglichen Folgendes:

  - Ein Unternehmensbenutzer, der sich innerhalb oder außerhalb der Unternehmensfirewall befindet, kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer tätigen, die im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters terminiert wird.

  - Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID (Direct Inward Dialing)-Nummer wählt, die dem Unternehmensbenutzer zugeordnet ist.

</div>

<div>

## <a name="cost-savings"></a>Kosteneinsparung

Die mit dem SIP-Trunking verbundene Kosteneinsparung kann erheblich sein:

  - Die Kosten für Ferngespräche sind bei Verwendung eines SIP-Trunks in der Regel deutlich niedriger.

  - Sie können die Verwaltungskosten senken und die Komplexität der Bereitstellung verringern.

  - Gebühren für Basisanschlüsse (Basic Rate Interface, BRI) und Primärmultiplexanschlüsse (Primary Rate Interface, PRI) entfallen, wenn Sie eine deutlich günstigere Direktverbindung zwischen SIP-Trunk und Ihrem Anbieter von Internettelefoniediensten (ISTP) konfigurieren. Beim TDM-Trunking rechnen Dienstanbieter Anrufe pro Minute ab. Die Kosten für das SIP-Trunking können auf der Bandbreitennutzung basieren, die Sie in kleineren, wirtschaftlicheren Einheiten erwerben können. (Die tatsächlichen Kosten richten sich nach dem Servicemodell des jeweiligen Anbieters von Internettelefoniediensten (ITSP).)

<div>

## <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP-Trunking im Vergleich zum Hosting eines PSTN-Gateways oder einer IP-Nebenstellenanlage

Da SIP-Trunks eine direkte Verbindung mit dem Dienstanbieter herstellen, entfallen Ihre PSTN-Gateways und die damit verbundenen Verwaltungskosten sowie die Komplexität dieser Lösung. Die Verwendung von SIP-Trunks kann durch einen geringeren Wartungs- und Verwaltungsaufwand zu einer erheblichen Kosteneinsparung beitragen.

</div>

</div>

<div>

## <a name="expanded-voip-services"></a>Erweiterte VoIP-Dienste

VoIP-Funktionen sind häufig die wichtigste Motivation für die Bereitstellung von SIP-Trunking, die VoIP-Unterstützung stellt jedoch nur den ersten Schritt dar. Mit dem SIP-Trunking können Sie VoIP-Funktionen erweitern und lync Server 2013 ermöglichen, eine umfangreichere Palette von Diensten bereitzustellen. Beispiel:

  - Die erweiterte Anwesenheitserkennung für Geräte, die nicht lync Server 2013 werden, kann eine bessere Integration mit Mobiltelefonen ermöglichen, sodass Sie sehen können, wann ein Benutzer einen Mobiltelefon Anruf ausführt.

  - E9-1-1-Notrufdienste ermöglichen es der Rettungsleitstelle, die den Notruf entgegennimmt, basierend auf der Telefonnummer den geografischen Standort des Anrufers zu ermitteln.

<div>


> [!NOTE]  
> Erkundigen Sie sich bei Ihrem ITSP, welche Dienste unterstützt werden und für Ihre Organisation aktiviert werden können.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

