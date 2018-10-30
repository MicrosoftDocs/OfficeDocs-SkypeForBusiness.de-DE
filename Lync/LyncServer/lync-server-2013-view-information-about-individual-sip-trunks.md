---
title: Anzeigen von Informationen zu einzelnen SIP-Trunks in Lync Server 2013
TOCTitle: Anzeigen von Informationen zu einzelnen SIP-Trunks in Lync Server 2013
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49890895
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anzeigen von Informationen zu einzelnen SIP-Trunks in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

SIP-Trunks werden zum Herstellen einer Verbindung zwischen dem Microsoft Lync Server 2013-VoIP-Telefonnetzwerk und dem Telefonfestnetz (Public Switched Telephone Network, PSTN) verwendet. In der vorherigen Produktversion wurden Trunks zum Weiterleiten ausgehender Anrufe von einem Vermittlungsserver an ein PSTN-Gateway verwendet, und die einzelnen Gateways waren auf einen einzelnen Trunk beschränkt. Demzufolge waren PSTN-Gateways und SIP-Trunks im Wesentlichen identisch. Für Administratoren bedeutete dies, dass sie Informationen zu einem einzelnen SIP-Trunk anzeigen konnten, indem sie einfach die Informationen zu dem zugeordneten PSTN-Gateway aufrufen.

In Lync Server 2013 können nun jedoch mehrere Trunks einem einzelnen PSTN-Gateway zugewiesen werden. Demnach sind Gateways und Trunks nicht mehr ein und dasselbe. Das heißt wiederum, dass Administratoren das neue Cmdlet [Get-CsTrunk](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsTrunk) verwenden müssen, um Informationen zu einem einzelnen SIP-Trunk anzuzeigen.

Das Cmdlet "Get-CsTrunk" kann über die Verwaltungsshell für Lync Server 2013 oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Remoteverwendung von Windows PowerShell, um eine Verbindung zu einem Lync-Server herzustellen, finden Sie im Lync Server Windows PowerShell-Blog "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" unter [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Anzeigen von Informationen für alle SIP-Trunks

  - Der folgende Befehl gibt Informationen zu allen in Ihrer Organisation verwendeten SIP-Trunks zurück:
    
        Get-CsTrunk

## Anzeigen von Informationen für einen bestimmten SIP-Trunk

  - Dieser Befehl gibt nur für den SIP-Trunk mit dem Identitätswert "PstnGateway:192.168.0.240" Informationen zurück:
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

## Anzeigen von Informationen für alle einem Pool zugeordneten SIP-Trunks

  - In diesem Beispiel werden für alle SIP-Trunks Informationen zurückgegeben, die dem Pool "atl-cs-001.litwareinc.com" zugeordnet sind:
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

