---
title: 'Lync Server 2013: Anforderungen an die Ausfallsicherheit für Zweigstellenstandorte'
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
ms.openlocfilehash: 61ca1db13f99b13dd2a6ed148f13ab6a132ad77b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Anforderungen für Ausfallsicherheit für Zweigstellenstandorte für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-25_

Dieses Thema unterstützt Sie bei der Vorbereitung von Benutzern im Hinblick auf die Ausfallsicherheit für Zweigstellenstandorte und für VoIP-Funktionen, und es werden die relevanten Hardware- und Softwareanforderungen angegeben.

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>Vorbereiten von Zweigstellenbenutzern für die Ausfallsicherheit für Zweigstellenstandorte

Bereiten Sie Benutzer für die Ausfallsicherheit von Zweigstellenstandorten vor, indem Sie Ihren registrierungsstellenpool als Survivable Branch Appliance (SBA) oder Survivable Branch Server festlegen.

<div>

## <a name="registrar-assignments-for-branch-users"></a>Registrierungszuweisungen für Zweigstellenbenutzer

Unabhängig davon, welche ausfallsicherheitslösung für Zweigstellenstandorte Sie auswählen, müssen Sie jedem Benutzer eine primäre Registrierungsstelle zuweisen. Zweigstellenbenutzer sollten sich immer am Zweigstellenstandort bei der Registrierungsstelle registrieren, unabhängig davon, ob sich diese Registrierungsstelle im Survivable Branch Appliance, Survivable Branch Server oder eigenständigen lync Server 2013 Standard oder Enterprise Edition-Server befindet. Ein DNS-Dienst (Domain Name System)-Ressourceneintrag (SRV) ist erforderlich, damit ein Client seinen registrierungsstellenpool ermitteln kann. Wenn die Survivable Branch Appliance nicht mehr verfügbar ist, ermitteln Zweigstellenclients automatisch die Sicherungs Registrierungsstelle.

Wenn für einen Zweigstellenstandort kein DNS-Server vorhanden ist, gibt es zwei alternative Methoden zum Konfigurieren der Ermittlung der Survivable Branch Appliance oder Survivable Branch Server:

  - Konfigurieren Sie die DHCP-Option 120 auf dem DHCP-Server (Dynamic Host Configuration Protocol) der Zweigstelle so, dass Sie auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Survivable Branch Appliance oder Survivable Branch Server verweist.

  - Konfigurieren Sie die Survivable Branch Appliance oder Survivable Branch Server, um auf DHCP 120-Abfragen zu reagieren.

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>VoIP-Routing für Zweigstellenbenutzer

Es wird empfohlen, eine separate VoIP-Richtlinie auf Benutzerebene für Benutzer an einem Zweigstellenstandort zu erstellen. Diese Richtlinie sollte eine primäre Route umfassen, die das Survivable Branch Appliance-oder Zweigstellenserver Gateway verwendet, sowie eine oder mehrere Sicherungs Routen, die einen trunk mit einem PSTN-Gateway (Public Switched Telephone Network) am zentralen Standort verwenden. Wenn die primäre Route nicht verfügbar ist, wird stattdessen die Sicherungs Route verwendet, die ein oder mehrere zentrale Standort Gateways verwendet. Auf diese Weise ist die VoIP-Richtlinie des Benutzers unabhängig davon, wo ein Benutzer registriert ist, auf der Zweigstellen Registrierungsstelle oder dem sicherungsregistrierungspool am zentralen Standort immer gültig. Dies ist eine wichtige Überlegung bei Failover-Szenarien. Wenn Sie beispielsweise die Survivable Branch Appliance umbenennen oder die Survivable Branch Appliance neu konfigurieren müssen, um eine Verbindung mit einem sicherungsregistrierungspool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für die Dauer an den zentralen Standort verlagern. (Ausführliche Informationen zum Umbenennen oder Neukonfigurieren eines Survivable Branch Appliance finden Sie in [Anhang B: Verwalten eines Survivable Branch Appliance in lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine VoIP-Richtlinien auf Benutzerebene oder Wählpläne auf Benutzerebene haben und die Benutzer an einen anderen Standort verschoben werden, gelten die VoIP-Richtlinien auf Standortebene und die Wähleinstellungen auf Standortebene des zentralen Standorts standardmäßig für die Benutzer, statt auf Standortebene-VoIP-Richtlinien und Wähleinstellungen. Wenn die VoIP-Richtlinien auf Standortebene und die Wählpläne auf Standortebene, die vom sicherungsregistrierungspool verwendet werden, auch auf die Benutzer der Zweigstellenstandorte angewendet werden können, tritt in diesem Szenario ein Fehler auf. Wenn beispielsweise Benutzer von einem Zweigstellenstandort in Japan an einen zentralen Standort in Redmond verschoben werden, ist es unwahrscheinlich, dass ein Wählplan mit Normalisierungsregeln, der + 1425 allen 7-stelligen anrufen anbietet, Anrufe für diese Benutzer nicht ordnungsgemäß übersetzt.

<div>


> [!IMPORTANT]  
> Beim Erstellen einer Alternativroute für eine Zweigstelle empfiehlt es sich, der Zweigstellenbenutzerrichtlinie zwei PSTN-Verwendungsdatensätze hinzuzufügen und ihnen jeweils separate Routen zuzuweisen. Die erste oder primäre Route würde Anrufe an das Gateway weiterleiten, das dem Survivable Branch Appliance (SBA) oder dem Zweigstellenserver zugeordnet ist; die zweite oder gesicherte Route würde Anrufe an das Gateway am zentralen Standort weiterleiten. Beim Leiten von Anrufen probiert die SBA oder der Zweigstellenserver alle dem ersten PSTN-Verwendungsdatensatz zugewiesenen Routen aus, bevor der zweite Verwendungsdatensatz verwendet wird.



</div>

Um sicherzustellen, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Zweigstellen Gateway oder die Windows-Komponente des Survivable Branch Appliance-Standorts nicht verfügbar ist (beispielsweise wenn der Survivable Branch Appliance oder die Verzweigung Gateway für die Wartung nicht zur Verfügung stand), erstellen Sie eine Failover-Route auf dem Gateway (oder arbeiten Sie mit Ihrem Direct Inward Dialing (DID)-Anbieter), um eingehende Anrufe an den sicherungsregistrierungspool am zentralen Standort umzuleiten. Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet. Stellen Sie sicher, dass die Route Nummern so übersetzt, dass sie den zulässigen Telefonnummernformaten des PSTN-Gateways oder eines anderen Trunkpeers entspricht. Ausführliche Informationen zum Erstellen einer Failover-Route finden Sie unter [Configuring a Failover Route in lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Erstellen Sie außerdem Wählpläne auf Dienstebene für den Trunkt, der dem Gateway an der Zweigstelle zugeordnet ist, damit eingehende Anrufe normalisiert werden. Wenn Sie zwei Survivable Branch Appliances an einem Zweigstellenstandort haben, können Sie einen Wählplan auf Standortebene für beide erstellen, es sei denn, es ist ein separater Service Level-Plan für jeden erforderlich.

<div>


> [!NOTE]  
> Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer so betrachten, als wäre er für den zentralen Standort registriert. Derzeit gibt es keine Beschränkungen für die Anzahl der Zweigstellenbenutzer, einschließlich der Benutzer, die mit einem Survivable Branch Appliance registriert sind.



</div>

Es empfiehlt sich außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Zweigstellenbenutzern zuzuweisen. Ausführliche Informationen finden Sie unter [Erstellen von Wähleinstellungen in lync Server 2013](lync-server-2013-create-a-dial-plan.md) und [Erstellen der VoIP-Routing Richtlinie für Zweigstellenbenutzer in lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in der Bereitstellungsdokumentation.

<div>

## <a name="routing-extension-numbers"></a>Weiterleiten von Durchwahlnummern

Bei der Vorbereitung von Wähleinstellungen und VoIP-Richtlinien für Zweigstellenbenutzer müssen Sie die Normalisierungsregeln und Übersetzungsregeln einbeziehen, die mit den Zeichenfolgen und dem Zahlenformat übereinstimmen, die im msRTCSIP-Linien Attribut (oder dem Linien-URI) verwendet werden, sodass lync 2013 Anrufe zwischen Verzweigung aktiviert sind. Websitebenutzer und Benutzer des zentralen Standorts werden ordnungsgemäß weitergeleitet, insbesondere dann, wenn Anrufe über das PSTN umgeleitet werden müssen, da die WAN-Verbindung nicht verfügbar ist. Weitere besondere Überlegungen betreffen gewählte Nummern, die nur Durchwahlnummern und keine Telefonnummern enthalten.

Besondere Voraussetzungen gelten für Normalisierungs- und Übersetzungsregeln, die Anschluss-URIs entsprechen, die eine Durchwahlnummer enthalten – sei es ausschließlich oder zusätzlich zu einer vollständigen E.164-Telefonnummer. In diesem Abschnitt werden einige Beispielszenarien zur Weiterleitung von Anrufen für Anschluss-URIs mit einer Durchwahlnummer beschrieben.

Wenn in Ihrer Organisation keine DID-Telefonnummern (Direct Inward Dial) für die einzelnen Benutzer konfiguriert sind und der Anschluss-URI für jeden Benutzer *nur* mit einer Durchwahlnummer konfiguriert ist, können interne Benutzer sich gegenseitig anrufen, indem Sie einfach nur eine Durchwahlnummer wählen. Allerdings müssen Sie Normalisierungsregeln konfigurieren, die für Anrufe eines Zweigstellenbenutzers an einen Benutzer am zentralen Standort gelten können, die mit den Durchwahlnummern übereinstimmen.

In einem Szenario, in dem die WAN-Verbindung zwischen einer Zweigstelle und einem zentralen Standort verfügbar ist, muss für Anrufe von Zweigstellenbenutzern an Benutzer am zentralen Standort nicht die Nummer durch eine entsprechende Normalisierungsregel übersetzt werden, da der Anruf nicht über das PSTN weitergeleitet wird. Ein Beispiel:


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
<th>Translation</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Fünfstellige Nummern werden nicht übersetzt</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 wird nicht übersetzt</p></td>
</tr>
</tbody>
</table>


Sie müssen auch Durchwahlnummern für besondere Szenarien mit einbeziehen, bei denen z. B. die WAN-Verbindung zwischen einer Zweigstelle und dem zentralen Standort nicht verfügbar ist und ein Anruf von einer Zweigstelle über das Festnetz weitergeleitet werden muss. Während eines WAN-Ausfalls wird, wenn ein Zweigstellenbenutzer einen Benutzer am zentralen Standort anruft, indem er nur dessen Durchwahlnummer wählt, eine ausgehende Übersetzungsregel benötigt, die die vollständige Telefonnummer des Benutzers am zentralen Standort hinzufügt. Wenn der Anschluss-URI die vollständige Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers anstelle einer vollständigen eindeutigen Telefonnummer für den Benutzer enthält, benötigen Sie eine ausgehende Übersetzungsregel, die stattdessen die vollständige Telefonnummer Ihrer Organisation hinzufügt. Beispiel:


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
<th>Vergleichsmuster</th>
<th>Translation</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Übersetzt fünfstellige Nummern in die Telefon- und Durchwahlnummer eines Benutzers</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550123; EXT = $1</p></td>
<td><p>10001 wird in +14255550123;ext=10001 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>Übersetzt fünfstellige Nummern in die Telefonnummer Ihrer Organisation und die Durchwahlnummer eines Benutzers</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+ 14255550100 übersetzt; EXT = $1</p></td>
<td><p>10001 wird in +14255550100;ext=10001 übersetzt</p></td>
</tr>
</tbody>
</table>


In diesem Szenario muss die ausgehende Übersetzungsregel, wenn der Trunkpeer, der die Rückumleitung an das Festnetz abwickelt, keine Durchwahlnummern unterstützt, auch die Durchwahlnummer entfernen. Beispiel:


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
<th>Vergleichsmuster</th>
<th>Translation</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Entfernt die Durchwahl von Telefonnummern mit Durchwahlnummern</p></td>
<td><p>^\+(\d *); ext = (\d*) $</p></td>
<td><p>+ $1</p></td>
<td><p>+14255550123;ext=10001 wird in +14255550123 übersetzt</p></td>
</tr>
</tbody>
</table>


Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, gilt Folgendes: Wenn in Ihrer Organisation keine DID-Nummern für einzelne Benutzer konfiguriert sind und der Anschluss-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des jeweiligen Benutzers enthält, müssen Sie den Anschluss-URI der Telefonnummer Ihrer Organisation mit einer Nummer konfigurieren, die vom Trunkpeer oder vom PSTN-Gateway am Zweigstellenstandort erreicht werden kann. Außerdem müssen Sie den Anschluss-URI der Telefonnummer Ihrer Organisation so konfigurieren, dass er eine eigene, eindeutige Durchwahlnummer für die Weiterleitung von Anrufen zu dieser Nummer enthält.

Einzelheiten zu Anrufen von einem Benutzer am zentralen Standort zu einem Zweigstellenbenutzer bei nicht verfügbarer WAN-Verbindung zwischen den Standorten finden Sie im Abschnitt "Vorbereiten der Ausfallsicherheit für VoIP-Funktionen" weiter unten in diesem Thema. Ausführliche Informationen zu Wählplänen und Normalisierungsregeln, einschließlich anderer Beispielregeln, finden Sie unter [Wählpläne und Normalisierungsregeln in lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation und [Konfigurieren von Wählplänen in lync Server 2013](lync-server-2013-configuring-dial-plans.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zu Regeln für ausgehende Übersetzungen finden Sie unter [Übersetzungsregeln in lync Server 2013](lync-server-2013-translation-rules.md) in der Planungsdokumentation und [Definieren von Übersetzungsregeln in lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>Vorbereiten der Ausfallsicherheit für VoIP-Funktionen

Exchange Unified Messaging (um) wird normalerweise nur an einem zentralen Standort und nicht an Zweigstellenstandorten installiert. Ein Anrufer sollte auch dann eine Voicemailnachricht hinterlassen können, wenn die WAN-Verbindung zwischen Zweigstelle und zentralem Standort nicht verfügbar ist. Daher erfordert das Konfigurieren des Leitungs-URI für die Exchange um Telefonnummer für die automatische Telefonzentrale, die Voicemail für Zweigstellenbenutzer bereitstellt, zusätzlich zu den für diese Voicemail geltenden VoIP-Richtlinien, Wähleinstellungen und Normalisierungsregeln besondere Überlegungen. Anzahl.

Survivable Branch Appliances (SBAS) und Survivable Branch Server bieten Filial Benutzern während eines WAN-Ausfalls eine Überlebensfähigkeit von Voicemail. Wenn Sie beispielsweise eine Survivable Branch Appliance oder Survivable Branch Server verwenden und das WAN nicht mehr verfügbar ist, leitet das SBA oder Survivable Branch Server unbeantwortete Anrufe über das PSTN an Exchange um am zentralen Standort weiter. Mit einem SBA oder Survivable Branch Server können Benutzer während eines WAN-Ausfalls auch Voicemail-Nachrichten über das PSTN abrufen. Schließlich werden bei einem WAN-Ausfall die Survivable Branch Appliance oder Survivable Branch Server in Warteschlangen verpasste Benachrichtigungen gesendet und dann auf den Exchange um Server hochzuladen, wenn das WAN wiederhergestellt wird. Um sicherzustellen, dass das Voicemail-neurouting widerstandsfähig ist, müssen Sie einen Eintrag für den FQDN des zentralen Website Pools und einen Eintrag für den Edgeserver FQDN der Hosts-Datei auf dem Survivable Branch Server hinzufügen. Andernfalls kann es bei der DNS-Auflösung zu einem Timeout kommen, wenn an der Zweigstelle kein DNS-Server vorhanden ist.

Für die Bereitstellung ausfallsicherer VoIP-Funktionen für Zweigstellenbenutzer werden die folgenden Konfigurationen empfohlen:

  - Ein Microsoft Exchange Administrator sollte Exchange um automatische Telefonzentrale (AA) so konfigurieren, dass nur Nachrichten akzeptiert werden. Durch diese Konfiguration wird jede andere allgemeine Funktionalität deaktiviert, beispielsweise das Durchstellen an einen Benutzer oder an einen Agent, und beschränkt die automatische Telefonzentrale auf die Annahme von Nachrichten. Alternativ dazu kann der Exchange-Administrator auch eine allgemeine automatische Telefonzentrale oder eine benutzerdefinierte automatische Telefonzentrale zum Routen des Anrufs an einen Agent verwenden.

  - Der lync Server Administrator sollte die AA-Telefonnummer übernehmen und diese Telefonnummer als **automatische Telefonzentrale für die Exchange um** -Telefonzentrale in den Einstellungen für die Voicemail-Umleitung für den Survivable Branch Appliance-oder Zweigstellen Server verwenden.

  - Der lync Server Administrator sollte die Telefonnummer des Exchange um Teilnehmerzugriffs erhalten und diese Nummer als **Teilnehmerzugriffs** Nummer in den Einstellungen für die Voicemail-Umleitung für die Survivable Branch Appliance oder Survivable Branch Server verwenden.

  - Der lync Server Administrator sollte Exchange um so konfigurieren, dass nur ein Wählplan allen Zweigstellenbenutzern zugeordnet ist, die während eines WAN-Ausfalls auf Voicemail zugreifen müssen.

  - Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an den Exchange Unified Messaging (UM)-Sprachposteingang des Benutzers umgeleitet werden, jedoch nur, wenn die auf den Anruf angewendete VoIP-Richtlinie eine Voicemailtelefonnummer angibt, die eindeutig ist und keine Durchwahlnummer enthält.

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Hardware- und Softwareanforderungen für die Ausfallsicherheit am Zweigstellenstandort

Die Hardware- und Softwareanforderungen variieren je nach Ausfallsicherheitslösung.

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>Anforderungen für Survivable Branch Appliances

Die erforderliche Hardware und Software ist in den Survivable Branch Appliance integriert. Es wird jedoch auch empfohlen, dass jeder Zweigstellenstandort einen DHCP-Server bereitstellt, um Client-IP-Adressen zu erhalten. Andernfalls kann es sein, dass Clients keine IP-Konnektivität haben, wenn die DHCP-Lease abläuft.

Wenn sich die Enterprise-DNS-Server nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung mit diesen herstellen, und daher schlägt lync Server Erkennung, die DNS-SRV (Service (SRV)-Ressourceneintrag verwendet) fehl. Damit eine sofortige Umleitung während eines WAN-Ausfalls gewährleistet ist, müssen DNS-Einträge am Zweigstellenstandort zwischengespeichert werden. Wenn der Zweigstellenrouter die DNS-Zwischenspeicherung unterstützt, aktivieren Sie sie. Sie können auch einen DNS-Server in der Zweigstelle bereitstellen. Hierbei kann es sich um einen eigenständigen Server oder eine Version der Survivable Branch Appliance handeln, die DNS-Funktionen unterstützt. Weitere Informationen erhalten Sie von Ihrem Survivable Branch Appliance Anbieter.

<div>


> [!NOTE]  
> Es ist nicht erforderlich, an jedem Zweigstellenstandort einen Domänencontroller zu verwenden. Das Survivable Branch Appliance authentifiziert Clients mithilfe eines speziellen Zertifikats, das den Client als Antwort auf die Zertifikatanforderung des Clients sendet, wenn er sich anmeldet.



</div>

Lync-Clients können die lync Server mithilfe der DHCP-Option 120 (SIP-Registrierungsoption) ermitteln. Dies ist mit einer von zwei Konfigurationen möglich:

  - Konfigurieren Sie den DHCP-Server am Zweigstellenstandort so, dass er auf DHCP 120-Abfragen antwortet, die den FQDN der Registrierungsstelle auf dem Survivable Branch Appliance oder Survivable Branch Server zurückgeben.

  - Aktivieren Sie lync Server DHCP. Wenn dieser aktiviert ist, antwortet die lync Server Registrierungsstelle auf DHCP-Option 120-Abfragen. Beachten Sie, dass die Registrierung nicht auf andere DHCP-Abfragen als DHCP-Option 120 reagiert.

Zusätzlich sollten für größere Zweigstellenstandorte mit mehreren Subnetzen DHCP-Relay-Agents aktiviert werden, um Abfragen der DHCP-Option 120 an den DHCP Server (Konfiguration 1) oder die Registrierung (Konfiguration 2) weiterzuleiten.

Schließlich müssen Zweigstellenbenutzer für Enterprise-VoIP konfiguriert und mit einem entsprechenden Unified Communications-Endpunkt eingerichtet werden.

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>Anforderungen für Survivable Branch Server

Die Anforderungen für Survivable Branch Server entsprechen den Anforderungen für ein Front-End-Server. Ausführliche Informationen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Planungsdokumentation.

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>Anforderungen für vollständige Lync Server-Bereitstellungen am Zweigstellenstandort

Ausführliche Informationen finden Sie unter [bestimmen der Infrastrukturanforderungen für lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

