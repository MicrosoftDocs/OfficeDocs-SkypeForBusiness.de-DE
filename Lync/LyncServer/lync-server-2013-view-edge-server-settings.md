---
title: 'Lync Server 2013: Anzeigen von Edgeserver-Einstellungen'
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
ms.openlocfilehash: 6eaab70f2f6d651d6446aaa4a569277494b7a9ee
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-edge-server-settings-in-lync-server-2013"></a>Anzeigen von Edgeserver-Einstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-05-20_

Allgemeine Edgeserver-Konfigurationen sollten anhand der Daten in der Konfigurationsverwaltungsdatenbank überprüft werden, um sicherzustellen, dass alle Änderungen gemäß den definierten Änderungskontrollverfahren dokumentiert wurden.

Weitere Prüfungen können die in den folgenden Abschnitten beschriebenen enthalten:

<div>

## <a name="verify-the-allow-and-block-lists"></a>Überprüfen der Listen "zulassen" und "blockieren"

Überprüfen Sie die SIP-URI-Listen "zulassen" und "blockieren" für Verbunddomänen, um zu ermitteln, ob aufgelistete Namespaces weiterhin gültig sind.

Sie können Windows PowerShell verwenden, um die zulässigen und blockierten Listen anzuzeigen. Führen Sie den folgenden Windows PowerShell-Befehl aus, um die Domänen in der Liste zugelassene Domänen zu überprüfen:

`Get-CsAllowedDomain`

Dieser Befehl gibt ähnliche Informationen für die Domänen in der Liste der zulässigen Domänen zurück:

Identität: contoso.com

Domäne: contoso.com

ProxyFqdn :

Kommentar

MarkForMonitoring: falsch

Kommentar

Verwenden Sie den folgenden Befehl, um die Domänen in der Liste der blockierten Domänen zu überprüfen:

`Get-CsBlockedDomain`

Sie erhalten wiederum Informationen wie diesen für jede blockierte Domäne:

Identität: tailspintoys.com

Domäne: tailspintoys.com

Mit Windows PowerShell können Sie auch überprüfen, ob Sie eine Verbindung mit den Domänen in der Liste der zulässigen Domänen herstellen können. Mit diesem Befehl wird beispielsweise die Verbindung zwischen Ihrem Edgeserver (dem TargetFqdn) und dem Verbunddomänen-contoso.com überprüft:

`Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"`

Dieser Befehl überprüft die Verbindung zwischen Ihrem Edgeserver und allen Domänen, die in der Liste der zulässigen Domänen enthalten sind:

`Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Domain}`

</div>

<div>

## <a name="verify-multiple-edge-servers-are-identical"></a>Überprüfen, ob mehrere Edgeserver identisch sind

Wenn mehrere Edgeserver in einem Lastenausgleichsarray bereitgestellt werden, sollten Sie überprüfen, ob alle Edgeserver im Array auf die gleiche Weise konfiguriert sind.

Sie können die Einstellungen für Edgeserver im Detailbereich der lync Server 2013-Erweiterung für das Computerverwaltungs-Snap-in anzeigen.

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

