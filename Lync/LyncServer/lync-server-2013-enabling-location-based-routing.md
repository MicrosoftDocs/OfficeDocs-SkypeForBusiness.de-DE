---
title: Aktivieren von standortbasiertem Routing in Lync Server 2013
TOCTitle: Aktivieren von standortbasiertem Routing in Lync Server 2013
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ994014(v=OCS.15)
ms:contentKeyID: 52056276
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren von standortbasiertem Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Sobald Enterprise-VoIP bereitgestellt ist und Netzwerkregionen, Standorte sowie Subnetze definiert sind, können Sie standortbasiertes Routing aktivieren. Standortbasiertes Routing muss für die folgenden Enterprise-VoIP-Elemente aktiviert sein:

  - Netzwerkstandorte

  - Trunkkonfiguration

  - VoIP-Richtlinien

  - Routingkonfiguration

## Aktivieren von standortbasiertem Routing zu Netzwerkstandorten

Nachdem Sie Enterprise-VoIP bereitgestellt und Netzwerkstandorte konfiguriert haben, können Sie standortbasiertes Routing konfigurieren. Zunächst erstellen Sie eine VoIP-Routingrichtlinie, in der der jeweilige Netzwerkstandort mit den entsprechenden PSTN-Verwendungen verknüpft wird. Wenn Sie PSTN-Verwendungen mit einer VoIP-Routingrichtlinie verknüpfen, dürfen Sie nur PSTN-Verwendungen verwenden, denen VoIP-Routen zugewiesen sind, für die ein PSTN-Gateway verwendet wird, das hinsichtlich des Standorts lokal ist oder sich in einer Region befindet, in der keine Einschränkungen für standortbasiertes Routing erforderlich sind. Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsVoiceRoutingPolicy" oder die Lync Server-Systemsteuerung, um VoIP-Routingrichtlinien zu erstellen.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Weitere Informationen hierzu finden Sie unter [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoiceRoutingPolicy).

Für dieses Beispiel werden in der folgenden Tabelle und in den folgenden Windows PowerShell-Befehlen zwei VoIP-Routingrichtlinien und deren zugehörige PSTN-Verwendungen veranschaulicht, die in diesem Szenario definiert sind. Für diese Veranschaulichung werden in der Tabelle nur die Einstellungen aufgeführt, die zum standortbasierten Routing gehören.

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
<th>VoIP-Routingrichtlinie 1</th>
<th>VoIP-Routingrichtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinien-ID</p></td>
<td><p>Delhi voice routing policy</p></td>
<td><p>Hyderabad voice routing policy</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Delhi usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage, PBX Hyd usage, PBX Del usage</p></td>
</tr>
</tbody>
</table>

  

Konfigurieren Sie nun das standortbasierte Routing für die entsprechenden Netzwerkstandorte, und weisen Sie Ihre Routingrichtlinien diesen Standorten zu. Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsNetworkSite", um das standortbasierte Routing zu aktivieren sowie Ihre VoIP-Routingrichtlinien den Netzwerkstandorten zuzuweisen, in denen Routingeinschränkungen durchgesetzt werden müssen.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

In der folgenden Tabelle ist für dieses Beispiel das standortbasierte Routing für die beiden unterschiedlichen Netzwerkstandorte "Delhi" und "Hyderabad" veranschaulicht, die in diesem Szenario über Lync ServerWindows PowerShell definiert wurden. Für diese Veranschaulichung werden in der Tabelle nur die Einstellungen aufgeführt, die zum standortbasierten Routing gehören.

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
<th>Standort 1 (Delhi)</th>
<th>Standort 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Standortname</p></td>
<td><p>Delhi</p></td>
<td><p>Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Routingrichtlinie</p></td>
<td><p>Delhi voice routing policy</p></td>
<td><p>Hyderabad voice routing policy</p></td>
</tr>
<tr class="even">
<td><p>Subnetze</p></td>
<td><p>Subnetz 1 (Delhi)</p></td>
<td><p>Subnetz 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>



## Aktivieren von standortbasiertem Routing zu Trunks

Bevor eine Trunkkonfiguration für standortbasiertes Routing aktiviert werden kann, müssen Sie für jeden Trunk- oder Netzwerkstandort eine Trunkkonfiguration erstellen. Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsTrunkConfiguration", um eine Trunkkonfiguration zu erstellen. Sind einem System (d. h. Gateway oder Nebenstellenanlage) mehrere Trunks zugewiesen, muss jede Trunkkonfiguration geändert werden, wenn Einschränkungen für standortbasiertes Routing aktiviert werden sollen.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Weitere Informationen hierzu finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

Für dieses Beispiel wird mit den folgenden Windows PowerShell-Befehlen veranschaulicht, wie in der Bereitstellung, die in diesem Szenario definiert ist, eine Trunkkonfiguration für jeden Trunk erstellt wird.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Sobald es für jeden Trunk eine Trunkkonfiguration gibt, können Sie mit dem Lync ServerWindows PowerShell-Befehl "Set-CsTrunkConfiguration" standortbasiertes Routing für die Trunks aktivieren, für die Routingbeschränkungen durchgesetzt werden müssen. Aktivieren Sie standortbasiertes Routing für Trunks, über die Anrufe an PSTN-Gateways weitergeleitet werden, in denen die Anrufe an das PSTN weitergeleitet werden, und weisen Sie den Netzwerkstandort zu, in dem sich das jeweilige Gateway befindet.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Weitere Informationen hierzu finden Sie unter [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration).

In diesem Beispiel wird standortbasiertes Routing für jeden Trunk aktiviert, der dem PSTN-Gateway in Delhi oder Hyderabad zugewiesen ist:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Aktivieren Sie standortbasiertes Routing nicht für Trunks, über die keine Anrufe an das PSTN weitergeleitet werden. Trotzdem müssen Sie einen solchen Trunk dem Netzwerkstandort zuweisen, in dem sich das System befindet, denn für PSTN-Anrufe an Endgeräte, die über diesen Trunk angeschlossen sind, müssen Beschränkungen für standortbasiertes Routing durchgesetzt werden. In diesem Beispiel wird standortbasiertes Routing für keinen der Trunks aktiviert, die Nebenstellenanlagen (PBX-Systemen) in Delhi oder Hyderabad zugewiesen sind:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Endgeräte, die an Systeme angeschlossen sind, die keine Anrufe an das PSTN weiterleiten (d. h. eine Nebenstellenanlage), haben ähnliche Beschränkungen wie Lync-Endgeräte von Benutzern, für die standortbasiertes Routing aktiviert ist. Das heißt, dass diese Benutzer Anrufe an Lync-Benutzer tätigen oder von Lync-Benutzern empfangen können, egal, an welchem Standort sich der jeweilige Lync-Benutzer befindet. Außerdem können sie Anrufe an andere Systeme tätigen oder über andere Systeme empfangen, die keine Anrufe an das PSTN-Netzwerk weiterleiten (d. h. ein Endgerät, das an eine andere Nebenstellenanlage angeschlossen ist), wobei es keine Rolle spielt, welchem Netzwerkstandort das System zugewiesen ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anrufdurchstellungen und Anrufweiterleitungen, an denen PSTN-Endgeräte beteiligt sind, werden den Beschränkungen für standortbasiertes Routing unterworfen. Für solche Anrufe dürfen nur PSTN-Gateways verwendet werden, die für solche Systeme als lokal definiert sind.

In der folgenden Tabelle wird die Trunkkonfiguration von vier Trunks in zwei unterschiedlichen Netzwerkstandorten veranschaulicht: zwei Trunks, die mit PSTN-Gateways, und zwei Trunks, die mit Nebenstellenanlagen (PBX-Systemen) verbunden sind.


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
<td><p>PstnGateway:Trunk 1 DEL-GW</p></td>
<td><p>True</p></td>
<td><p>Delhi</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 2 HYD-GW</p></td>
<td><p>True</p></td>
<td><p>Hyderabad</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway:Trunk 3 DEL-PBX</p></td>
<td><p>False</p></td>
<td><p>Delhi</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway:Trunk 4 HYD-PBX</p></td>
<td><p>False</p></td>
<td><p>Hyderabad</p></td>
</tr>
</tbody>
</table>



## Aktivieren von standortbasiertem Routing zu VoIP-Richtlinien

Wenn Sie standortbasiertes Routing zu bestimmten Benutzern aktivieren möchten, müssen Sie die VoIP-Richtlinie für diese Benutzer so konfigurieren, dass ein Umgehen von gebührenpflichtigen PSTN-Telefonnummern verhindert wird. Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsVoicePolicy", wenn Sie eine neue VoIP-Richtlinie erstellen möchten, oder "Set-CsVoicePolicy", wenn Sie eine vorhandene Richtlinie verwenden möchten, um standortbasiertes Routing zu aktivieren, indem PSTN-Gebührenumgehung verhindert wird.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Weitere Informationen hierzu finden Sie unter [New-CsVoicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsVoicePolicy).

Für dieses Beispiel wird in der folgenden Tabelle und in den folgenden Windows PowerShell-Befehlen veranschaulicht, wie ein Verhindern von PSTN-Gebührenumgehung für die Delhi- und Hyderabad-VoIP-Routingrichtlinien aktiviert wird, die in diesem Szenario definiert sind. Für diese Veranschaulichung werden in der Tabelle nur die Einstellungen aufgeführt, die zum standortbasierten Routing gehören.

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
<td><p>Delhi voice policy</p></td>
<td><p>Hyderabad voice policy</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Delhi usage, PBX Del usage, PBX Hyd usage</p></td>
<td><p>Hyderabad usage, PBX Hyd usage, PBX Del usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>True</p></td>
<td><p>True</p></td>
</tr>
</tbody>
</table>



## Aktivieren von standortbasiertem Routing in der Routingkonfiguration

Aktivieren Sie schließlich standortbasiertes Routing global für Ihre Routingkonfiguration. Verwenden Sie den Lync ServerWindows PowerShell-Befehl "New-CsRoutingConfiguration", um standortbasiertes Routing zu aktivieren.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Weitere Informationen hierzu finden Sie unter [Set-CsRoutingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsRoutingConfiguration).


> [!NOTE]
> Auch wenn standortbasiertes Routing über eine globale Konfiguration aktiviert werden muss, werden die anzuwendenden Regeln nur für die Standorte, Benutzer und Trunks durchgesetzt, für die die Konfiguration gemäß den Angaben in dieser Dokumentation erstellt wurde.




## Siehe auch

#### Weitere Ressourcen

[Konfigurieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)

