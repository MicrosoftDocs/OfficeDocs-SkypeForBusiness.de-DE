---
title: 'Lync Server 2013: Anzeigen von Edgeserver Einstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Edge Server settings
ms:assetid: 684154cc-cffc-4d2e-8baa-be52c625e5d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747890(v=OCS.15)
ms:contentKeyID: 63969612
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3f536a0aadb181b1b740d74c8f61715efed21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506392"
---
# <a name="view-edge-server-settings-in-lync-server-2013"></a>Anzeigen von Edgeserver Einstellungen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-20_

Allgemeine Edgeserver Konfigurationen sollten anhand der Daten in der Konfigurationsverwaltungsdatenbank überprüft werden, damit sichergestellt ist, dass alle Änderungen gemäß den definierten Änderungskontrollverfahren dokumentiert wurden.

Weitere Überprüfungen könnten die in den folgenden Abschnitten beschriebenen umfassen:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Überprüfen der Zulassungs-und Sperrlisten

Überprüfen Sie die Listen SIP-URI "zulassen" und "blockieren" für Verbunddomänen, um zu ermitteln, ob aufgelistete Namespaces noch gültig sind.

Sie können Windows PowerShell verwenden, um die zulässigen und blockierten Listen anzuzeigen. Um die Domänen in der Liste zugelassene Domänen zu überprüfen, führen Sie den folgenden Windows PowerShell Befehl aus:

`Get-CsAllowedDomain`

Dieser Befehl gibt Informationen wie diese für die Domänen in der Liste der zugelassenen Domänen zurück:

Identity: contoso.com

Domäne: contoso.com

ProxyFqdn

Kommentar

MarkForMonitoring: false

Kommentar

Verwenden Sie den folgenden Befehl, um die Domänen in der Liste blockierter Domänen zu überprüfen:

`Get-CsBlockedDomain`

Sie erhalten wiederum Informationen wie diese für jede blockierte Domäne:

Identity: tailspintoys.com

Domäne: tailspintoys.com

Mit Windows PowerShell können Sie auch überprüfen, ob Sie eine Verbindung mit den Domänen in der Liste der zugelassenen Domänen herstellen können. Mit diesem Befehl wird beispielsweise die Verbindung zwischen dem Edgeserver (TargetFqdn) und der contoso.com der Verbunddomäne überprüft:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Mit diesem Befehl wird die Verbindung zwischen Ihrem Edgeserver und allen Domänen überprüft, die in der Liste der zugelassenen Domänen gefunden werden:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Überprüfen, ob mehrere Edgeserver identisch sind

Wenn mehrere Edgeserver in einem Lastenausgleichsarray bereitgestellt werden, sollten Sie überprüfen, ob alle Edgeserver im Array auf die gleiche Weise konfiguriert sind.

Sie können Einstellungen für Edgeserver im Detailbereich der lync Server 2013-Erweiterung für das Snap-in "Computer Verwaltung" anzeigen.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsAllowedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsAllowedDomain)  
[Get-CsBlockedDomain](https://docs.microsoft.com/powershell/module/skype/Get-CsBlockedDomain)  
[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

