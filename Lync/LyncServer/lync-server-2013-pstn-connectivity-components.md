---
title: 'Lync Server 2013: PSTN-Verbindungskomponenten'
description: 'Lync Server 2013: PSTN-Verbindungskomponenten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN connectivity components
ms:assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398504(v=OCS.15)
ms:contentKeyID: 48184408
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2ae5a6a7bc5db1cd7a23c44719d7123a624317d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565681"
---
# <a name="pstn-connectivity-components-in-lync-server-2013"></a>PSTN-Verbindungskomponenten in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-04_

Eine VoIP-Lösung für Unternehmen muss ein- und ausgehende PSTN-Anrufe (Public Switched Telephone Network, Telefonfestnetz) ermöglichen, ohne dass die Dienstqualität (Quality of Service, QoS) in irgendeiner Weise beeinträchtigt wird. Außerdem sollte die zugrunde liegende Technologie für Benutzer, die Anrufe tätigen und empfangen, unbemerkt im Hintergrund arbeiten. Aus Benutzersicht sollte ein Anruf zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz wie eine ganz normale SIP-Sitzung wirken.

Für PSTN-Verbindungen können Sie entweder einen SIP-Trunk oder ein PSTN-Gateway (mit einer Nebenstellenanlage, auch als direkte SIP-Verbindung bezeichnet) oder ohne Nebenstellenanlage bereitstellen.

<div>

## <a name="sip-trunking"></a>SIP-Trunking

Als Alternative zu PSTN-Gateways können Sie Ihre Enterprise-VoIP-Lösung mithilfe von SIP-Trunking mit dem Telefonfestnetz verbinden. Mit SIP-Trunking sind folgende Szenarien möglich:

  - Ein Benutzer eines Unternehmens innerhalb oder außerhalb der Unternehmensfirewall kann ein Orts- oder Ferngespräch über eine E.164-kompatible Nummer führen, das im Telefonfestnetz als Dienst des entsprechenden Dienstanbieters beendet wird.

  - Jeder PSTN-Teilnehmer (Public Switched Telephone Network, Telefonfestnetz) kann einen Unternehmensbenutzer innerhalb oder außerhalb der Unternehmensfirewall erreichen, indem er eine DID-Nummer (Direct Inward Dialing) wählt, die dem Unternehmensbenutzer zugeordnet ist.

Für diese Bereitstellungslösung ist ein SIP-Trunking-Dienstanbieter erforderlich.

</div>

<div>

## <a name="pstn-gateways"></a>PSTN-Gateways

Bei PSTN-Gateways handelt es sich um Drittanbietergeräte, die Signale und Mediendaten zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz oder einer Nebenstellenanlage übersetzen. PSTN-Gateways arbeiten mit dem Vermittlungsserver zusammen, um Anrufe aus dem Festnetz oder über eine Nebenstellenanlage an einen Enterprise-VoIP-Client zu übergeben. Der Vermittlungsserver übergibt außerdem Anrufe von Enterprise-VoIP-Clients an das PSTN-Gateway, damit dieses sie an das Telefonfestnetz oder die Nebenstellenanlage weiterleitet. Eine Liste der Partner, die mit Microsoft zusammenarbeiten, um Geräte bereitzustellen, die mit lync Server zusammenarbeiten, finden Sie auf der Microsoft Unified Communications Partner-Website unter [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

</div>

<div>

## <a name="private-branch-exchanges"></a>Nebenstellenanlagen

Wenn Sie über eine vorhandene VoIP-Infrastruktur verfügen, die eine Nebenstellenanlage (Private Branch Exchange, PBX) verwendet, können Sie Ihre Nebenstellenanlage mit lync Server Enterprise-VoIP verwenden.

Die folgenden Szenarien mit Integration von Enterprise-VoIP und einer Nebenstellenanlage werden unterstützt:

  - IP-Nebenstellenanlage mit Unterstützung der Medienumgehung und einem Vermittlungsserver.

  - IP-Nebenstellenanlage, die ein eigenständiges PSTN-Gateway erfordert.

  - TDM-Nebenstellenanlage (Time Division Multiplexing) mit eigenständigem PSTN-Gateway.

<div>


> [!NOTE]  
> Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs. Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt. Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .



</div>

Ausführliche Informationen zu Partnern, die Enterprise-VoIP-Lösungen anbieten, finden Sie auf der Microsoft Unified Communications Partner-Website unter [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

Ausführliche Informationen zu Partnern, die Enterprise-VoIP-Hardwarelösungen anbieten, einschließlich PSTN-Gateways, finden Sie auf der Microsoft Unified Communications Partner-Website [https://go.microsoft.com/fwlink/p/?linkId=202836](https://go.microsoft.com/fwlink/p/?linkid=202836) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

