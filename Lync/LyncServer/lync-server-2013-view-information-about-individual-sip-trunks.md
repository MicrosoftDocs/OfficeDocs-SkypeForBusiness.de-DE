---
title: 'Lync Server 2013: Anzeigen von Informationen zu einzelnen SIP-Trunks'
description: 'Lync Server 2013: Anzeigen von Informationen zu einzelnen SIP-Trunks.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55c2f9fb1df4e916615cf7f95f95ae167d7216ab
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569611"
---
# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a>Anzeigen von Informationen zu einzelnen SIP-Trunks in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

SIP-Trunks werden verwendet, um lync Server 2013 Voice-over-IP-Telefonnetz mit dem öffentlichen Telefonnetz zu verbinden. In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet, und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt. Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch. Für Administratoren bedeutete dies, dass sie Informationen zu einem einzelnen SIP-Trunk anzeigen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufrufen.

In lync Server 2013 können jedoch mehrere Trunks nun einem einzelnen PSTN-Gateway zugewiesen werden; Dies bedeutet, dass Gateways und Trunks nicht mehr identisch sind. Dies bedeutet wiederum, dass Administratoren das neue Cmdlet [Get-cstrunk "](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.

Das Get-CsTrunk-Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a>So zeigen Sie Informationen für alle SIP-Trunks an

  - Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a>So zeigen Sie Informationen für einen bestimmten SIP-Trunk an

  - Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a>Anzeigen von Informationen für alle einem Pool zugeordneten SIP-Trunks

  - In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

