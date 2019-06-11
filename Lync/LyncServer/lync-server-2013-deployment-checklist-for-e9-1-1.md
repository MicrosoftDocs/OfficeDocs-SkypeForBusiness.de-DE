---
title: 'Lync Server 2013: Bereitstellungscheckliste für E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9a48ba3d999e55106298d7419e4590147e1e9e5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Bereitstellungscheckliste für E9-1-1 in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Um effektiv für Enhanced 9-1-1 (E9-1-1) zu planen, müssen Sie unbedingt die folgenden Bereitstellungsanforderungen berücksichtigen:

  - Voraussetzungen für die Bereitstellung von E9-1-1.

  - Schritte, die für die Bereitstellung von E9-1-1 erforderlich sind.

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>Voraussetzungen für die Bereitstellung von E9-1-1

Bevor Sie E9-1-1 bereitstellen, müssen Sie bereits die internen lync Server-Server bereitgestellt haben, einschließlich eines zentralen Verwaltungsspeichers, eines Front-End-Pools oder eines Standard Edition-Servers, eines oder mehrerer Vermittlungsserver oder Mediation Server-Pools und lync Server-Clients. Darüber hinaus benötigen Sie für eine E9-1-1-Bereitstellung einen SIP-Trunk zu einem qualifizierten E9-1-1-Dienstanbieter oder ein ELIN-Gateway (Emergency Location Identification Number) zu Ihrem Telefonfestnetz (Public Switched Telephone Network, PSTN). Lync Server unterstützt die Verwendung von E9-1-1-Dienstanbietern nur innerhalb der Vereinigten Staaten.

</div>

<div>

## <a name="deployment-process"></a>Bereitstellungsprozess

Die folgende Tabelle zeigt eine Übersicht über den E9-1-1-Bereitstellungsprozess. Ausführliche Informationen zu Bereitstellungsschritten finden Sie unter [Konfigurieren von erweitertem 9-1-1 in lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in der Bereitstellungsdokumentation.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konfigurieren von VoIP-Nutzungen, Routen und Trunks</p></td>
<td><ol>
<li><p>Erstellen Sie einen neuen PSTN-Verwendungseintrag. Hierbei handelt es sich um den gleichen Namen, der in der Standortrichtlinie für die Einstellung <strong>PSTN-Verwendung</strong> verwendet wird.</p></li>
<li><p>Erstellen Sie eine VoIP-Route oder weisen Sie dem im vorherigen Schritt erstellten PSTN-Verwendungseintrag eine solche zu und lassen Sie das Gatewayattribut auf den E9-1-1-SIP-Trunk oder das ELIN-Gateway verweisen. </p></li>
<li><p>Stellen Sie für SIP-Trunk-E9-1-1-Dienstanbieter den Trunk, der E9-1-1-Anrufe über SIP verarbeiten soll, so ein, dass PIDF-LO-Daten weitergegeben werden. Verwenden Sie dazu das Cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</p></li>
<li><p>Optional können Sie für SIP-Trunk-E9-1-1-Dienstanbieter eine lokale PSTN-Route für Anrufe erstellen oder zuweisen, die nicht vom SIP-Trunk des E9-1-1-Dienstanbieters verwaltet werden. Diese Route wird verwendet, wenn keine Verbindung zum E9-1-1-Dienstanbieter besteht. Wenn dies von Ihrem E9-1-1-Dienstanbieter unterstützt wird, weisen Sie dem Gateway eine Trunkkonfigurationsregel zu, die die Notrufzeichenfolge in die DID (Direct Inward Dialing)-Nummer des nationalen/regionalen Telefoncenters für Notrufe (Emergency Call Response Center, ECRC) übersetzt.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Konfigurieren einer E9-1-1-VoIP-Route in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Erstellen von Standortrichtlinien und Zuweisen dieser Standortrichtlinien zu Benutzern und Subnetzen</p></td>
<td><ol>
<li><p>Überprüfen Sie die globale Standortrichtlinie.</p></li>
<li><p>Erstellen Sie eine Standortrichtlinie auf Benutzerebene oder erstellen Sie, wenn die Organisation über mehr als einen Standort mit verschiedenen Notfallverwendungen verfügt, eine Standortrichtlinie auf Netzwerkebene.</p></li>
<li><p>Weisen Sie die Standortrichtlinie Netzwerkstandorten zu.</p></li>
<li><p>Fügen Sie dem Netzwerkstandort geeignete Subnetze hinzu.</p></li>
<li><p>(Optional) Weisen Sie die Standortrichtlinie Benutzerrichtlinien zu.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (außer bei Erstellung von Standortrichtlinien)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Erstellen von Standortrichtlinien in lync Server 2013</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Hinzufügen einer Standortrichtlinie zu einer Netzwerk Website in lync Server 2013</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Zuordnen von Subnetzen zu Netzwerkstandorten für E9-1-1 in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Konfigurieren der Standortdatenbank</p></td>
<td><ol>
<li><p>Füllen Sie die Datenbank mit einer Zuordnung von Netzwerkelementen zu Standorten auf.</p></li>
<li><p>Für Elin-Gateways fügen Sie die Elins zur Spalte &lt;CompanyName&gt; hinzu.</p></li>
<li><p>Konfigurieren Sie für die Verbindung zum E9-1-1-Dienstanbieter die Überprüfung der Adressen.</p></li>
<li><p>Gleichen Sie die Adressen mit dem E9-1-1-Dienstanbieter ab.</p></li>
<li><p>Veröffentlichen Sie die aktualisierte Datenbank.</p></li>
<li><p>Laden Sie für ELIN-Gateways die ELINs in die ALI (Automatic Location Identification)-Datenbank Ihres PSTN-Betreibers hoch.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren von erweiterten Funktionen (optional)</p></td>
<td><ol>
<li><p>Konfigurieren Sie die URL für die SNMP-Anwendung.</p></li>
<li><p>Konfigurieren Sie die URL für den Speicherort des Informationsdiensts für sekundären Standort.</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Konfigurieren einer SNMP-Anwendung in lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Konfigurieren eines sekundären Standort Informationsdiensts in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

