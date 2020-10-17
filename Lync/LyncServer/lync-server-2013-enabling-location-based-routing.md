---
title: 'Lync Server 2013: Aktivieren des Location-Based Routings'
description: 'Lync Server 2013: Aktivieren des Location-Based Routings.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7844af5792468cd5645b6b42c857c63b943c2df1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557621"
---
# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Aktivieren Location-Based Routings in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-04-26_

Nachdem Enterprise-VoIP bereitgestellt wurde und netzwerkregionen,-Standorte und-Subnetze definiert sind, können Sie Location-Based Routing aktivieren. Für die folgenden Enterprise-VoIP-Elemente muss Location-Based Routing aktiviert sein:

  - Netzwerkstandorte

  - Trunk Konfigurationen

  - VoIP-Richtlinien

  - Routing Konfiguration

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Aktivieren Location-Based Routings an Netzwerkstandorte

Nachdem Sie Enterprise-VoIP bereitgestellt und Netzwerkstandorte konfiguriert haben, können Sie Location-Based Routing konfigurieren. Zunächst erstellen Sie eine VoIP-Routing Richtlinie, um dem Netzwerkstandort die entsprechenden PSTN-Verwendungen zuzuordnen. Wenn Sie PSTN-Verwendungen einer VoIP-Routing Richtlinie zuweisen, sollten Sie sicherstellen, dass Sie nur PSTN-Verwendungen verwenden, die VoIP-Routen zugeordnet sind, die ein lokales PSTN-Gateway für den Standort oder ein PSTN-Gateway verwenden, das sich in einer Region befindet, in der keine Location-Based Routing Einschränkungen erforderlich sind. Verwenden Sie die lync Server Windows PowerShell-Befehl, New-csvoiceroutingpolicy "oder lync Server-Systemsteuerung, um VoIP-Routing Richtlinien zu erstellen.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Weitere Informationen finden Sie unter [New-csvoiceroutingpolicy "](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

In diesem Beispiel werden in den folgenden Tabellen-und Windows PowerShell Befehlen zwei VoIP-Routing Richtlinien und die zugehörigen in diesem Szenario definierten PSTN-Verwendungen veranschaulicht. Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Routing Richtlinie 1</th>
<th>VoIP-Routing Richtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinien-ID</p></td>
<td><p>VoIP-Routing Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Routing Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Verwendung von Delhi, PBX del Usage, PBX Hyd</p></td>
<td><p>Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</p></td>
</tr>
</tbody>
</table>

  

Konfigurieren Sie als nächstes Location-Based Routing für die entsprechenden Netzwerkstandorte, und ordnen Sie Ihnen die Richtlinien für das VoIP-Routing zu. Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsNetworkSite, um Location-Based Routing zu aktivieren und VoIP-Routing Richtlinien ihren Netzwerkstandorten zuzuordnen, die Routing Einschränkungen erzwingen müssen.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

In diesem Beispiel wird in der folgenden Tabelle Location-Based Routing für zwei verschiedene Netzwerkstandorte (Delhi und Hyderabad) veranschaulicht, die in diesem Szenario mithilfe der lync Server Windows PowerShell definiert wurden. Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Website 1 (Delhi)</th>
<th>Standort 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name der Website</p></td>
<td><p>Website 1 (Delhi)</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Routingrichtlinie</p></td>
<td><p>VoIP-Routing Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Routing Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>Subnetze</p></td>
<td><p>Subnetz 1 (Delhi)</p></td>
<td><p>Subnetz 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Location-Based Routing an Trunks aktivieren

Bevor eine trunkkonfiguration für Location-Based Routing aktiviert werden kann, müssen Sie für jeden trunk oder jeden Netzwerkstandort eine trunkkonfiguration erstellen. Verwenden Sie den Befehl lync Server Windows PowerShell, New-CsTrunkConfiguration, um eine trunkkonfiguration zu erstellen. Wenn mehrere Trunks einem bestimmten System (also Gateway oder Nebenstellenanlage) zugeordnet sind, muss jede trunkkonfiguration so geändert werden, dass Location-Based Routing Einschränkungen aktiviert sind.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In diesem Beispiel veranschaulichen die folgenden Windows PowerShell Befehle das Erstellen einer trunkkonfiguration für jeden trunk in der in diesem Szenario definierten Bereitstellung.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Nachdem Sie eine trunkkonfiguration pro trunk konfiguriert haben, können Sie mit dem Befehl lync Server Windows PowerShell-CsTrunkConfiguration Location-Based Routing an Ihre Trunks aktivieren, die Routing Einschränkungen erzwingen müssen. Aktivieren Sie Location-Based Routing an Trunks, die Anrufe an PSTN-Gateways weiterleiten, die Anrufe an das PSTN weiterleiten, und ordnen Sie den Netzwerkstandort zu, auf dem sich das Gateway befindet.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Weitere Informationen finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

In diesem Beispiel ist Location-Based Routing für jeden trunk aktiviert, der PSTN-Gateways in Delhi und Hyderabad zugeordnet ist:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Aktivieren Sie Location-Based Routing nicht für Trunks, die keine Anrufe an das PSTN weiterleiten; Sie müssen den trunk jedoch weiterhin dem Netzwerkstandort zuordnen, in dem sich das System befindet, da Location-Based Routing Einschränkungen für PSTN-Anrufe erzwungen werden müssen, die über diesen Trunk verbundene Endpunkte erreichen. In diesem Beispiel ist Location-Based Routing für jeden trunk, der PBX-Systemen in Delhi und Hyderabad zugeordnet ist, nicht aktiviert:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Endpunkte, die mit Systemen verbunden sind, die keine Anrufe an das PSTN (d. h. eine Nebenstellenanlage) weiterleiten, haben ähnliche Einschränkungen wie lync-Endpunkte von Benutzern, die für Location-Based Routing aktiviert werden. Dies bedeutet, dass diese Benutzer unabhängig vom Standort des Benutzers Anrufe an und von lync-Benutzern tätigen und empfangen können. Sie können auch Anrufe an und von anderen Systemen ablegen, die Anrufe nicht an das PSTN-Netzwerk weiterleiten (d. h. an einen Endpunkt, der mit einer anderen Nebenstellenanlage verbunden ist), unabhängig vom Netzwerkstandort, dem das System zugeordnet ist. Alle eingehenden Anrufe, ausgehende Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen Location-Based Routing-Erzwingung. Für solche Anrufe müssen nur PSTN-Gateways verwendet werden, die als lokal für solche Systeme definiert sind.

In der folgenden Tabelle ist die trunkkonfiguration von vier Trunks an zwei unterschiedlichen Netzwerkstandorten dargestellt: zwei mit PSTN-Gateways und zwei mit PBX-Systemen verbunden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Wert "pstngateway: trunk 1 del-GW</p></td>
<td><p>Richtig</p></td>
<td><p>Website 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>Wert "pstngateway: trunk 2 Hyd-GW</p></td>
<td><p>Richtig</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>Wert "pstngateway: trunk 3 del-PBX</p></td>
<td><p>False</p></td>
<td><p>Website 1 (Delhi)</p></td>
</tr>
<tr class="even">
<td><p>Wert "pstngateway: trunk 4 Hyd-PBX</p></td>
<td><p>False</p></td>
<td><p>Standort 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Aktivieren Location-Based Weiterleitung an VoIP-Richtlinien

Um Location-Based Routing für bestimmte Benutzer zu erzwingen, konfigurieren Sie die VoIP-Richtlinie dieser Benutzer, um eine PSTN-Maut Umgehung zu verhindern. Verwenden Sie die lync Server Windows PowerShell-Befehl, New-CsVoicePolicy, um eine neue VoIP-Richtlinie oder CsVoicePolicy zu erstellen, wenn Sie eine vorhandene Richtlinie verwenden, um Location-Based Routing zu aktivieren, indem Sie die PSTN-Maut Umgehung verhindern.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Weitere Informationen finden Sie unter [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

In diesem Beispiel veranschaulichen die folgenden Tabellen-und Windows PowerShell Befehle das Aktivieren der Aktivierung der PSTN-Maut Umgehung für die in diesem Szenario definierten VoIP-Richtlinien in Delhi und Hyderabad. Zur Veranschaulichung werden nur Einstellungen, die für Location-Based Routing spezifisch sind, in die Tabelle einbezogen.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Richtlinie 1</th>
<th>VoIP-Richtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinien-ID</p></td>
<td><p>VoIP-Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Verwendung von Delhi, PBX del Usage, PBX Hyd</p></td>
<td><p>Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Aktivieren Location-Based Routings in der Routingkonfiguration

Schließlich können Sie Location-Based Routing an Ihre Routingkonfiguration Global aktivieren. Verwenden Sie den Befehl lync Server Windows PowerShell, New-CsRoutingConfiguration, um Location-Based Routing zu aktivieren.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Weitere Informationen finden Sie unter [Sets-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> während Location-Based Routing über eine globale Konfiguration aktiviert werden muss, wird der Satz von angewendeten Regeln nur für die Standorte, Benutzer und Trunks erzwungen, für die er gemäß der in dieser Dokumentation angegebenen Konfiguration konfiguriert wurde.



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren Location-Based Routings in lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

