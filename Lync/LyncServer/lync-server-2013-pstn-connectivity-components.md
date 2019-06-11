---
title: 'Lync Server 2013: PSTN-Verbindungskomponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecda38b4164a70cd4dbb21271ff6efedb08cd498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-connectivity-components-in-lync-server-2013"></a>Komponenten für PSTN-Konnektivität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird. Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten. Aus Sicht des Benutzers sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem PSTN wie nur eine weitere SIP-Sitzung aussehen.

Für PSTN-Verbindungen können Sie entweder einen SIP-Trunk oder ein PSTN-Gateway bereitstellen – mit Nebenstellenanlage (was auch als direkte SIP-Verbindung bezeichnet wird) oder ohne Nebenstellenanlage.

<div>

## <a name="sip-trunking"></a>SIP-Trunking

Als Alternative zur Verwendung von PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking mit dem PSTN verbinden. Mit SIP-Trunking sind folgende Szenarien möglich:

  - Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.

  - Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.

Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich.

</div>

<div>

## <a name="pstn-gateways"></a>PSTN-Gateways

PSTN-Gateways sind Geräte von Drittanbietern, die Signal-und Medienübertragung zwischen der Enterprise-VoIP-Infrastruktur und einem PSTN oder einer Telefonanlage übersetzen. PSTN-Gateways arbeiten mit dem Vermittlungs Server zusammen, um einem Enterprise-VoIP-Client einen PSTN-oder PBX-Anruf zu präsentieren. Der Vermittlungs Server stellt auch Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway zum Weiterleiten an das PSTN oder die Telefonanlage vor. Eine Liste der Partner, die mit Microsoft zusammenarbeiten, um Geräte bereitzustellen, die mit lync Server funktionieren, finden Sie auf [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)der Microsoft Unified Communications Partners-Website unter.

</div>

<div>

## <a name="private-branch-exchanges"></a>Nebenstellenanlagen

Wenn Sie über eine vorhandene VoIP-Infrastruktur verfügen, die eine PBX (Private Branch Exchange) verwendet, können Sie Ihre Telefonanlage mit lync Server Enterprise-VoIP verwenden.

Die unterstützten Enterprise-VoIP-Integrationsszenarien sind wie folgt:

  - IP-Telefonanlage, die die medienumgehung mit einem Vermittlungs Server unterstützt.

  - IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.

  - TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.

<div>


> [!NOTE]  
> Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen oder SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>lync Server unter aufgeführt sind.



</div>

Details zu Partnern, die Enterprise-VoIP-Lösungen anbieten, finden Sie auf [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)der Microsoft Unified Communications Partners-Website unter.

Details zu Partnern, die Enterprise-VoIP-Hardwarelösungen anbieten, einschließlich PSTN-Gateways, finden Sie auf [http://go.microsoft.com/fwlink/p/?linkId=202836](http://go.microsoft.com/fwlink/p/?linkid=202836)der Microsoft Unified Communications Partners-Website.

</div>

</div>

<span> </span>

</div>

</div>

</div>

