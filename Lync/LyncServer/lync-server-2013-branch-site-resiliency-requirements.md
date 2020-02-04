---
title: 'Lync Server 2013: Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f146f2c358e6eb6718aa60f8a51106430e6a4a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-25_

In diesem Thema finden Sie Informationen dazu, wie Sie Benutzer auf die Ausfallsicherheit von Zweigstellen und Voicemail vorbereiten sowie die entsprechenden Hardware-und Softwareanforderungen angeben.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Vorbereiten von Verzweigungs Benutzern für die Stabilität des Zweig Standorts

Bereiten Sie die Benutzer auf die Ausfallsicherheit von Zweigstellen vor, indem Sie deren Registrierungspool als Survivable Branch Appliance (SBA) oder Survivable Branch Server festlegen.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Registrierungsstellen Zuweisungen für Verzweigungs Benutzer

Unabhängig davon, welche Lösung für eine Zweigstellen-Ausfallsicherheit Sie wählen, müssen Sie jedem Benutzer eine primäre Registrierungsstelle zuweisen. Benutzer von Verzweigungs Websites sollten sich immer bei der Registrierungsstelle an der Zweigstelle anmelden, und zwar unabhängig davon, ob sich die Registrierungsstelle in der Survivable Branch-Appliance, dem Überlebenden Branch-Server oder einem eigenständigen lync Server 2013 Standard-oder Enterprise Edition-Server befindet. Ein DNS-Service-Ressourceneintrag (Domain Name System) ist erforderlich, damit ein Client seinen Registrierungspool ermitteln kann. Wenn die Survivable Branch-Appliance nicht mehr zur Verfügung steht, finden die Zweigstellenclients automatisch die Sicherungs Registrierungsstelle.

Wenn eine Verzweigungs Website nicht über einen DNS-Server verfügt, gibt es zwei alternative Methoden zum Konfigurieren der Ermittlung der Survivable Branch-Appliance oder des Survivable Branch-Servers:

  - Konfigurieren Sie die DHCP-Option 120 auf dem DHCP-Server (Dynamic Host Configuration Protocol) der Zweigstelle so, dass Sie auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch-Servers verweist.

  - Konfigurieren Sie die Survivable Branch-Appliance oder den Survivable Branch-Server, um auf DHCP 120-Abfragen zu reagieren.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>VoIP-Routing für Branch-Benutzer

Wir empfehlen, dass Sie eine separate VoIP-Richtlinie auf Benutzerebene für Benutzer in einer Zweigstelle erstellen. Diese Richtlinie sollte eine primäre Route umfassen, die die Survivable Branch Appliance oder das Branch Server-Gateway verwendet, und mindestens eine Sicherungs Route, die einen trunk mit einem PSTN-Gateway (Public Switched Telephone Network) am zentralen Standort verwendet. Wenn die primäre Route nicht verfügbar ist, wird stattdessen die Sicherungs Route verwendet, die mindestens ein zentrales Standort Gateway verwendet. Auf diese Weise ist die VoIP-Richtlinie des Benutzers unabhängig davon, wo ein Benutzer registriert ist, auf der Zweigstellen-Registrierungsstelle oder dem sicherungsregistrierungspool am zentralen Standort immer gültig. Dies ist eine wichtige Überlegung für Failover-Szenarien. Wenn Sie beispielsweise die Survivable Branch-Appliance umbenennen oder die Survivable Branch-Appliance neu konfigurieren müssen, um eine Verbindung mit einem sicherungsregistrierungspool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für die Dauer an den zentralen Standort verschieben. (Einzelheiten zum Umbenennen oder Neukonfigurieren einer Survivable Branch-Appliance finden Sie in [Anhang B: Verwalten einer Survivable Branch-Appliance in lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine VoIP-Richtlinien auf Benutzerebene oder Wählpläne auf Benutzerebene haben und die Benutzer auf eine andere Website umgestellt werden, gelten die VoIP-Richtlinien auf Websiteebene und die Wählpläne auf Websiteebene des zentralen Standorts standardmäßig für die Benutzer und nicht für die Website VoIP-Richtlinien und Wählpläne auf Websiteebene. Wenn die VoIP-Richtlinien auf Websiteebene und die vom sicherungsregistrierungspool verwendeten Wählpläne auf Websiteebene auch für die Benutzer der Verzweigungs Website gelten können, treten in diesem Szenario keine Anrufe auf. Wenn beispielsweise Benutzer von einer Zweigstelle, die sich in Japan befindet, in einen zentralen Standort in Redmond verschoben werden, wird ein Wählplan mit Normalisierungsregeln, der + 1425 allen siebenstelligen anrufen vorangestellt wird, wahrscheinlich nicht geeignet sein, Anrufe für diese Benutzer angemessen zu übersetzen.

<div>


> [!IMPORTANT]  
> Wenn Sie eine Zweigstellen-Backup-Route erstellen, empfehlen wir, dass Sie der Benutzerrichtlinie für Zweigniederlassungen zwei PSTN-Telefonnutzungsdatensätze hinzufügen und jedem eine separate Route zuweisen. Die erste oder primäre Route würde Anrufe an das Gateway weiterleiten, das dem SBA (Survivor Branch Appliance) oder Branch Server zugeordnet ist. die zweite oder Sicherungs-Route würde Anrufe an das Gateway an der zentralen Website weiterleiten. Bei der Weiterleitung von Anrufen versucht der SBA-oder Branch-Server alle Routen, die dem ersten PSTN-Verwendungsdaten Satz zugeordnet sind, bevor Sie den zweiten Verwendungsdaten Satz versuchen.



</div>

So stellen Sie sicher, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Branch-Gateway oder die Windows-Komponente der Survivable Branch Appliance-Website nicht verfügbar ist (Dies würde beispielsweise passieren, wenn die Survivable Branch Appliance oder Branch Gateway für die Wartung nicht zur Verfügung standen), erstellen Sie eine Failover-Route auf dem Gateway (oder arbeiten Sie mit Ihrem direkten nach innen Wähl-(DID-) Anbieter), um eingehende Anrufe an den sicherungsregistrierungspool am zentralen Standort umzuleiten. Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet. Stellen Sie sicher, dass die Route Zahlen übersetzt, um Sie dem PSTN-Gateway oder den akzeptierten Telefonnummernformaten anderer trunk-Peers zu entsprechen. Details zum Erstellen einer Failover-Route finden Sie unter [Konfigurieren einer Failover-Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Sie können auch Wählpläne auf Dienstebene für den trunk erstellen, der dem Gateway auf der Zweigstelle zugeordnet ist, um eingehende Anrufe zu normalisieren. Wenn Sie über zwei überlebensfähige Branch-Appliances an einer Zweigstelle verfügen, können Sie einen Wählplan auf Websiteebene für beide erstellen, es sei denn, es ist ein separater Service-Level-Plan erforderlich.

<div>


> [!NOTE]  
> Zum berücksichtigen des Verbrauchs von Ressourcen für die zentrale Website durch alle Zweigstellenbenutzer, die auf die zentrale Website für Anwesenheit, Konferenz oder Failover angewiesen sind, empfehlen wir, dass Sie den jeweiligen Benutzer der Zweigstelle in Betracht ziehen, als ob der Benutzer bei der zentralen Website registriert wäre. Derzeit gibt es keine Beschränkungen für die Anzahl der Benutzer von Zweigstellen, einschließlich der Benutzer, die bei einer Survivable Branch-Appliance registriert sind.



</div>

Wir empfehlen außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Benutzern der Verzweigungs Website zuzuweisen. Ausführliche Informationen finden Sie unter [Erstellen eines Wählplans in lync Server 2013](lync-server-2013-create-a-dial-plan.md) und [Erstellen der VoIP-Routing Richtlinie für Verzweigungs Benutzer in lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in der Bereitstellungsdokumentation.

<div>

## <a name="routing-extension-numbers"></a>Durchwahlnummern für die Weiterleitung

Stellen Sie beim Vorbereiten von Wählplänen und VoIP-Richtlinien für Benutzer von Zweigstellen sicher, dass Sie Normalisierungsregeln und Übersetzungsregeln einbeziehen, die mit den Zeichenfolgen und dem Zahlenformat übereinstimmen, die im Attribut msRTCSIP (oder Linien-URI)-Attribut verwendet werden, damit lync 2013-Anrufe zwischen Zweigstellen aktiviert sind. Websitebenutzer und zentrale Websitebenutzer werden ordnungsgemäß weitergeleitet, insbesondere dann, wenn Anrufe über das PSTN umgeleitet werden müssen, weil die WAN-Verbindung nicht verfügbar ist. Darüber hinaus gibt es besondere Überlegungen für gewählte Nummern, die Durchwahlnummern enthalten, und nicht nur Telefonnummern.

Normalisierungsregeln und Übersetzungen, die mit Linien-URIs übereinstimmen, die eine Durchwahlnummer enthalten, ob ausschließlich oder zusätzlich zu einer vollständigen E. 164-Telefonnummer, haben zusätzliche Anforderungen. In diesem Abschnitt werden verschiedene Beispielszenarien zum Weiterleiten von Anrufen für Linien-URIs mit einer Durchwahlnummer beschrieben.

Wenn Ihre Organisation nicht über direkte Durchwahlnummern (DID) für einzelne Benutzer verfügt und der Leitungs-URI jedes Benutzers *nur* mit einer Durchwahlnummer konfiguriert ist, können interne Benutzer eine andere Rufnummer anrufen, indem Sie nur eine Durchwahlnummer wählen. Sie müssen jedoch Normalisierungsregeln konfigurieren, die für Anrufe von einem Zweigstellenbenutzer an einen zentralen Websitebenutzer gelten können, die den Durchwahlnummern entsprechen.

In einem Szenario, in dem die WAN-Verbindung zwischen einer Verzweigungs Website und einem zentralen Standort verfügbar ist, ist es für Anrufe von Zweigstellenbenutzern an zentrale Websitebenutzer nicht erforderlich, dass die übereinstimmende Normalisierungsregel die Nummer übersetzt, da der Anruf nicht über das PSTN weitergeleitet wird. Beispiel:


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Regelname</th>
<th>Beschreibung</th>
<th>Nummernmuster</th>
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Fünfstellige Zahlen werden nicht übersetzt</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 wird nicht übersetzt</p></td>
</tr>
</tbody>
</table>


Sie müssen auch Durchwahlnummern für bestimmte Szenarien berücksichtigen, beispielsweise, wenn die WAN-Verbindung zwischen einer Verzweigungs Website und einem zentralen Standort nicht verfügbar ist und ein Anruf von einer Zweigstelle über das PSTN weitergeleitet werden muss. Wenn ein Zweigstellenbenutzer bei einem WAN-Ausfall nur einen zentralen Websitebenutzer anruft, indem er die Durchwahl des zentralen Websitebenutzers anwählt, muss eine ausgehende Übersetzungsregel vorhanden sein, mit der die vollständige Telefonnummer des zentralen Websitebenutzers hinzugefügt wird. Wenn der Linien-URI des Benutzers die vollständige Telefonnummer Ihres Unternehmens und die eindeutige Durchwahlnummer des Benutzers anstelle einer vollständigen Telefonnummer enthält, die für den Benutzer eindeutig ist, müssen Sie über eine Regel für ausgehende Übersetzungen verfügen, die stattdessen die vollständige Telefonnummer Ihrer Organisation hinzufügt. . Beispiel:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Übereinstimmungsmuster</th>
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Übersetzt fünfstellige Zahlen in die Telefonnummer und Durchwahl eines Benutzers</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550123; EXT = $1</p></td>
<td><p>10001 wird in + 14255550123; ext = 10001</p></td>
</tr>
<tr class="even">
<td><p>Übersetzt fünfstellige Zahlen in die Telefonnummer Ihrer Organisation und die Durchwahl des Benutzers.</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100 übersetzt.; ext = $1</p></td>
<td><p>10001 wird in + 14255550100 übersetzt.; ext = 10001</p></td>
</tr>
</tbody>
</table>


Wenn der trunk-Peer, der das Umleiten an das PSTN übernimmt, keine Durchwahlnummern unterstützt, muss in diesem Szenario auch die ausgehende Übersetzungsregel die Durchwahlnummer entfernen. Beispiel:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Beschreibung</th>
<th>Übereinstimmungsmuster</th>
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Entfernt die Durchwahl von Telefonnummern mit Erweiterungen</p></td>
<td><p>^\+(\d *); ext = (\d*) $</p></td>
<td><p>+$1</p></td>
<td><p>+ 14255550123; ext = 10001 wird in + 14255550123 übersetzt</p></td>
</tr>
</tbody>
</table>


Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, wenn Ihre Organisation keine DID-Nummern für einzelne Benutzer konfiguriert hat und der Leitungs-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers enthält, müssen Sie Ihre der Telefonnummern-URI der Organisation mit einer Nummer, die über das trunk-Peer-oder PSTN-Gateway auf der Zweigstelle erreichbar ist. Darüber hinaus müssen Sie den Telefonnummern-URI Ihrer Organisation so konfigurieren, dass seine eigene eindeutige Durchwahl für die Weiterleitung von Anrufen an diese Nummer hinzugefügt wird.

Informationen zu Anrufen von einem zentralen Websitebenutzer zu einem Zweigstellenbenutzer, wenn die WAN-Verbindung zwischen den Websites nicht verfügbar ist, finden Sie weiter unten in diesem Thema unter "Vorbereiten der Überlebensfähigkeit von Voicemail". Details zu Wählplänen und Normalisierungsregeln, einschließlich anderer Beispielregeln, finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation und [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) in der Bereitstellungsdokumentation. Details zu den Regeln für ausgehende Übersetzungen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md) in der Planning-Dokumentation und [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Vorbereiten der Überlebensfähigkeit von Voicemail

Exchange Unified Messaging (um) wird normalerweise nur an einem zentralen Standort und nicht an Zweigstellen installiert. Ein Anrufer sollte in der Lage sein, eine Voicemail-Nachricht zu hinterlassen, auch wenn die WAN-Verbindung zwischen der Zweigstelle und dem zentralen Standort nicht verfügbar ist. Daher erfordert die Konfiguration des Linien-URIs für die Telefonnummer der automatischen Exchange UM-Telefonzentrale, die Voicemail für Zweigstellenbenutzer bereitstellt, besondere Überlegungen, zusätzlich zu den VoIP-Richtlinien, dem Wählplan und den Normalisierungsregeln, die für diese Voicemail gelten. Anzahl.

Überlebensfähige Branch Appliances (SBAS) und überlebensfähige Verzweigungs Server sorgen für die Überlebensfähigkeit von Voicemail für Branch-Benutzer bei einem WAN-Ausfall. Wenn Sie eine Survivable Branch-Appliance oder einen Survivable Branch-Server verwenden und das WAN nicht mehr zur Verfügung steht, leitet der SBA-oder Survivable Branch-Server unbeantwortete Anrufe über das PSTN an Exchange um am zentralen Standort weiter. Mit einem SBA-oder Survivable-Branch-Server können Benutzer während eines WAN-Ausfalls auch Voicemail-Nachrichten über das PSTN abrufen. Schließlich werden bei einem WAN-Ausfall die überlebensfähige Branch-Appliance oder der Survivable Branch-Server in Warteschlangen verpasste Benachrichtigungen gesetzt und dann auf den Exchange um-Server hochgeladen, wenn das WAN wiederhergestellt wird. Stellen Sie sicher, dass Sie einen Eintrag für den FQDN des zentralen Website Pools und einen Eintrag für den FQDN des Edge-Servers in der Hosts-Datei auf dem Überlebenden Verzweigungs Server hinzufügen, um sicherzustellen, dass das neurouting von Voicemail widerstandsfähig ist. Andernfalls kann die DNS-Auflösung ein Timeout aufweisen, wenn Sie nicht über einen DNS-Server auf der Zweigstelle verfügen.

Wir empfehlen die folgenden Konfigurationen für die Überlebensfähigkeit von Voicemail für Branch Site-Benutzer:

  - Ein Microsoft Exchange-Administrator sollte die Exchange um-automatische Telefonzentrale (AA) so konfigurieren, dass nur Nachrichten akzeptiert werden. Mit dieser Konfiguration werden alle anderen generischen Funktionen, wie etwa die Übertragung an einen Benutzer oder die Übertragung an einen Operator, deaktiviert und die AA auf die Annahme von Nachrichten beschränkt. Alternativ kann der Exchange-Administrator einen generischen AA oder AA-Benutzerdefiniert verwenden, um den Anruf an einen Operator weiterzuleiten.

  - Der lync Server-Administrator sollte die AA-Telefonnummer übernehmen und diese Telefonnummer in den Einstellungen für die Voicemail-Umleitungseinstellungen für die überlebensfähige Branch-Appliance oder den Branch-Server als die Nummer der **automatischen Exchange UM-Telefonzentrale** verwenden.

  - Der lync Server-Administrator sollte die Telefonnummer für den Exchange um-Teilnehmerzugriff erhalten und diese Nummer als **Teilnehmerzugriffs** Nummer in den Einstellungen für die Voicemail-Umleitung für die Survivable Branch Appliance oder den Survivable Branch-Server verwenden.

  - Der lync Server-Administrator sollte Exchange um so konfigurieren, dass allen Verzweigungs Benutzern, die während eines WAN-Ausfalls Zugriff auf Voicemail benötigen, nur ein Wählplan zugeordnet ist.

  - Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an das Exchange Unified Messaging (um)-Voicemail-Postfach des Benutzers weitergeleitet werden, jedoch nur, wenn die auf den Anruf angewendete VoIP-Richtlinie eine eindeutige Voicemail-Telefonnummer angibt und keine Durchwahl enthält. Anzahl.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Hardware-und Software Anforderungen für die Stabilität des Zweigstellen Standorts

Die Hardware-und Softwareanforderungen variieren je nach ihrer Resilienz-Lösung.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Voraussetzungen für Survivable Branch Appliances

Die erforderliche Hardware und Software ist in der Survivable Branch-Appliance integriert. Wir empfehlen jedoch auch, dass jede Zweigstelle einen DHCP-Server bereitstellt, um Client-IP-Adressen abzurufen. Wenn die DHCP-Lease abläuft, gibt es andernfalls keine IP-Konnektivität für Clients.

Wenn sich die Enterprise-DNS-Server nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung mit Ihnen herstellen, und daher schlägt die lync Server-Ermittlung, die DNS-SRV (Service (SRV)-Ressourceneintrag verwendet, fehl. Damit Sie bei einem WAN-Ausfall ein schnelles erneutes Routing sicherstellen können, müssen DNS-Einträge auf der Zweigstelle zwischengespeichert werden. Aktivieren Sie die DNS-Zwischenspeicherung, wenn der Verzweigungs Router dies unterstützt. Oder Sie können einen DNS-Server in der Verzweigung bereitstellen. Hierbei kann es sich um einen eigenständigen Server oder eine Version der Survivable Branch-Appliance handeln, die DNS-Funktionen unterstützt. Weitere Informationen erhalten Sie von Ihrem Überlebenden Branch Appliance-Anbieter.

<div>


> [!NOTE]  
> Es ist nicht erforderlich, einen Domänencontroller an einer Zweigstelle zu haben. Die Survivable Branch-Appliance authentifiziert Clients mithilfe eines speziellen Zertifikats, das der Client als Antwort auf die Zertifikatanforderung des Clients sendet, wenn er sich anmeldet.



</div>

Lync-Clients können den lync-Server mithilfe der DHCP-Option 120 (Option SIP-Registrierungsstelle) ermitteln. Dies kann auf eine von zwei Arten konfiguriert werden:

  - Konfigurieren Sie den DHCP-Server auf der Verzweigungs Website, um auf DHCP 120-Abfragen zu antworten, die den FQDN der Registrierungsstelle auf der Survivable Branch-Appliance oder dem Überlebenden Branch-Server zurückgeben.

  - Aktivieren Sie lync Server DHCP. Wenn diese Option aktiviert ist, reagiert die lync Server-Registrierungsstelle auf DHCP-Option 120-Abfragen. Beachten Sie, dass die Registrierungsstelle nicht auf DHCP-Abfragen anders als DHCP-Optionen 120 reagiert.

Darüber hinaus sollten für größere Zweigstellen, die über mehrere Subnetze verfügen, DHCP-Relay-Agents aktiviert werden, um DHCP-Option 120-Abfragen an den DHCP-Server (Konfiguration 1) oder an die Registrierungsstelle weiterzuleiten (Konfiguration 2).

Schließlich müssen die Benutzer der Zweigstelle für Enterprise-VoIP konfiguriert und mit einem geeigneten Unified Communications-Endpunkt bereitgestellt werden.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Voraussetzungen für Überlebende Zweigstellenserver

Die Anforderungen für überlebensfähige Zweigstellenserver sind identisch mit den Anforderungen für einen Front-End-Server. Ausführliche Informationen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Planungsdokumentation.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Voraussetzungen für die vollständige Bereitstellung von lync Server Branch-Websites

Ausführliche Informationen finden Sie unter [Ermitteln der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

