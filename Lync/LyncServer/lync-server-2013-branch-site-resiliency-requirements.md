---
title: 'Lync Server 2013: Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten'
TOCTitle: Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412772(v=OCS.15)
ms:contentKeyID: 49294981
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen für die Ausfallsicherheit an Zweigstellenstandorten für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieses Thema unterstützt Sie bei der Vorbereitung von Benutzern im Hinblick auf die Ausfallsicherheit für Zweigstellenstandorte und für VoIP-Funktionen, und es werden die relevanten Hardware- und Softwareanforderungen angegeben.

## Vorbereiten von Zweigstellenbenutzern für die Ausfallsicherheit für Zweigstellenstandorte

Bereiten Sie Benutzer für die Ausfallsicherheit an Zweigstellenstandorten vor, indem Sie deren Registrierungspool als Survivable Branch-Anwendung (SBA) oder Survivable Branch-Server festlegen.

## Registrierungszuweisungen für Zweigstellenbenutzer

Unabhängig von der gewählten Ausfallsicherheitslösung für den Zweigstellenstandort müssen Sie jedem Benutzer eine primäre Registrierung zuweisen. Benutzer am Zweigstellenstandort sollten sich immer bei der Registrierung am Zweigstellenstandort registrieren, unabhängig davon, ob sich die Registrierung in der Survivable Branch-Anwendung, Survivable Branch-Server oder in der eigenständigen Lync Server 2013-Standard-Version bzw. in Enterprise Edition-Server befindet. Ein DNS-SRV-Ressourceneintrag ist erforderlich, damit ein Client den zugehörigen Registrierungspool ermitteln kann. Wenn die Survivable Branch-Anwendung nicht mehr verfügbar ist, ermitteln Clients am Zweigstellenstandort auf diese Weise automatisch die Sicherungsregistrierung.

Verfügt ein Zweigstellenstandort nicht über einen DNS-Server, gibt es zwei Alternativen, um die Ermittlung der Survivable Branch-Anwendung oder des Survivable Branch-Servers zu ermöglichen:

  - Konfigurieren Sie die DHCP-Option 120 auf dem DHCP-Server (Dynamic Host Configuration Protocol) der Zweigstelle, sodass sie auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch-Anwendung oder der Survivable Branch-Server zeigt.

  - Konfigurieren Sie die Survivable Branch-Anwendung oder den Survivable Branch-Server so, dass DHCP 120-Abfragen beantwortet werden.

## VoIP-Routing für Zweigstellenbenutzer

Es empfiehlt sich, eine separate VoIP-Richtlinie auf Benutzerebene für Benutzer in einer Zweigstelle zu erstellen. Diese Richtlinie sollte eine primäre Route enthalten, die die Survivable Branch-Anwendung oder das Zweigstellenserver-Gateway verwendet, und eine oder mehrere Alternativrouten, die einen Trunk mit PSTN-Gateway am zentralen Standort verwenden. Ist die primäre Route nicht verfügbar, wird stattdessen die Alternativroute verwendet, die ein oder mehrere Gateways des zentralen Standorts verwendet. Auf diese Weise ist die VoIP-Richtlinie des Benutzers immer wirksam, unabhängig davon, wo ein Benutzer registriert ist \\endash entweder bei der Zweigstellen-Registrierungsstelle oder im Sicherungs-Registrierungsstellenpool am zentralen Standort. Dies ist eine wichtige Überlegung für Failoverszenarien. Wenn Sie beispielsweise die Survivable Branch-Anwendung umbenennen oder die Survivable Branch-Anwendung neu konfigurieren müssen, um eine Verbindung zu einem Sicherungs-Registrierungsstellenpool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für diese Dauer an den zentralen Standort verschieben. (Ausführliche Informationen zum Umbenennen oder Neukonfigurieren einer Survivable Branch-Anwendung finden Sie unter [Anhang B: Verwalten einer Survivable Branch Appliance in Lync Server 2013](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md) in der Bereitstellungsdokumentation.) Wenn diese Benutzer nicht über VoIP-Richtlinien oder Wählpläne auf Benutzerebene verfügen, gelten für die Benutzer, wenn sie zu einem anderen Standort verschoben werden, standardmäßig die VoIP-Richtlinien und Wählpläne auf Standortebene des zentralen Standorts und nicht die VoIP-Richtlinien und Wählpläne auf Standortebene der Zweigstelle. In diesem Szenario können die Benutzer die Anrufe nicht durchführen, es sei denn, die VoIP-Richtlinien und Wählpläne auf Standortebene, die vom Sicherungs-Registrierungsstellenpool verwendet werden, können auch auf die Zweigstellenbenutzer angewendet werden. Angenommen, die Benutzer einer Zweigstelle in Japan werden zu einem zentralen Standort in Redmond verschoben. Dann kann ein Wählplan mit Normalisierungsregeln, die allen siebenstelligen Rufnummern +1425 voranstellen, Anrufe für diese Benutzer wahrscheinlich nicht korrekt übersetzen.


> [!IMPORTANT]
> Beim Erstellen einer Alternativroute für eine Zweigstelle empfiehlt es sich, der Zweigstellenbenutzerrichtlinie zwei PSTN-Verwendungsdatensätze hinzuzufügen und ihnen jeweils separate Routen zuzuweisen. Die erste, primäre Route leitet Anrufe an das der Survivable Branch-Anwendung (SBA) oder dem Zweigstellenserver zugeordnete Gateway; die zweite Route, also die Alternativroute, leitet Anrufe an das Gateway am zentralen Standort. Beim Leiten von Anrufen probiert die SBA oder der Zweigstellenserver alle dem ersten PSTN-Verwendungsdatensatz zugewiesenen Routen aus, bevor der zweite Verwendungsdatensatz verwendet wird.



Damit sichergestellt ist, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Zweigstellengateway oder die Windows-Komponente des Standorts mit der Survivable Branch-Anwendung nicht verfügbar ist (dies würde beispielsweise geschehen, wenn die Survivable Branch-Anwendung oder das Zweigstellengateway zu Wartungszwecken heruntergefahren wäre), erstellen Sie auf dem Gateway eine Failoverroute (oder erarbeiten Sie zusammen mit Ihrem DID-Anbieter (Direct Inward Dialing) eine Lösung), um eingehende Anrufe an den Sicherungs-Registrierungspool am zentralen Standort umzuleiten. Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet. Stellen Sie sicher, dass die Route Nummern so übersetzt, dass sie den zulässigen Telefonnummernformaten des PSTN-Gateways oder eines anderen Trunkpeers entspricht. Ausführliche Informationen zum Erstellen einer Failoverroute finden Sie unter [Konfigurieren einer Failoverroute in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md). Erstellen Sie außerdem Wählpläne auf Dienstebene für den Trunkt, der dem Gateway an der Zweigstelle zugeordnet ist, damit eingehende Anrufe normalisiert werden. Wenn in einer Zweigstelle zwei Survivable Branch-Anwendungen vorhanden sind, können Sie für beide einen Wählplan auf Standortebene erstellen, es sei denn, es wird für jede ein eigener Plan auf Dienstebene benötigt.


> [!NOTE]
> Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer so betrachten, als wäre er für den zentralen Standort registriert. Für die Anzahl von Zweigstellenbenutzern (einschließlich der für eine Survivable Branch-Anwendung registrierten Benutzer) gelten gegenwärtig keine Einschränkungen.



Es empfiehlt sich außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Zweigstellenbenutzern zuzuweisen. Ausführliche Informationen dazu finden Sie unter [Erstellen eines Wählplans in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) und [Erstellen einer VoIP-Routingrichtlinie für Zweigstellenbenutzer in Lync Server 2013](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md) in der Bereitstellungsdokumentation.

## Weiterleiten von Durchwahlnummern

Legen Sie beim Erstellen von Wählplänen und VoIP-Richtlinien für Zweigstellenbenutzer unbedingt Normalisierungs- und Übersetzungsregeln fest, die dem Zeichenfolgen- und Zahlenformat entsprechen, das im Attribut "msRTCSIP-line" (oder Anschluss-URI) verwendet wird, um eine ordnungsgemäße Weiterleitung von Lync 2013-Anrufen zwischen Zweigstellenbenutzern und Benutzern des zentralen Standorts sicherzustellen \\endash besonders, wenn Anrufe über das PSTN umgeleitet werden müssen, weil die WAN-Verbindung nicht verfügbar ist. Weitere besondere Überlegungen betreffen gewählte Nummern, die nur Durchwahlnummern und keine Telefonnummern enthalten.

Besondere Voraussetzungen gelten für Normalisierungs- und Übersetzungsregeln, die Anschluss-URIs entsprechen, die eine Durchwahlnummer enthalten - sei es ausschließlich oder zusätzlich zu einer vollständigen E.164-Telefonnummer. In diesem Abschnitt werden einige Beispielszenarien zur Weiterleitung von Anrufen für Anschluss-URIs mit einer Durchwahlnummer beschrieben.

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
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>Fünfstellige Nummern werden nicht übersetzt</p></td>
<td><p>^(\d{5})$</p></td>
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
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Übersetzt fünfstellige Nummern in die Telefon- und Durchwahlnummer eines Benutzers</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550123;ext=$1</p></td>
<td><p>10001 wird in +14255550123;ext=10001 übersetzt</p></td>
</tr>
<tr class="even">
<td><p>Übersetzt fünfstellige Nummern in die Telefonnummer Ihrer Organisation und die Durchwahlnummer eines Benutzers</p></td>
<td><p>^(\d{5})$</p></td>
<td><p>+14255550100;ext=$1</p></td>
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
<th>Übersetzung</th>
<th>Beispiel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Entfernt die Durchwahl von Telefonnummern mit Durchwahlnummern</p></td>
<td><p>^\+(\d*);ext=(\d*)$</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 wird in +14255550123 übersetzt</p></td>
</tr>
</tbody>
</table>


Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, gilt Folgendes: Wenn in Ihrer Organisation keine DID-Nummern für einzelne Benutzer konfiguriert sind und der Anschluss-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des jeweiligen Benutzers enthält, müssen Sie den Anschluss-URI der Telefonnummer Ihrer Organisation mit einer Nummer konfigurieren, die vom Trunkpeer oder vom PSTN-Gateway am Zweigstellenstandort erreicht werden kann. Außerdem müssen Sie den Anschluss-URI der Telefonnummer Ihrer Organisation so konfigurieren, dass er eine eigene, eindeutige Durchwahlnummer für die Weiterleitung von Anrufen zu dieser Nummer enthält.

Einzelheiten zu Anrufen von einem Benutzer am zentralen Standort zu einem Zweigstellenbenutzer bei nicht verfügbarer WAN-Verbindung zwischen den Standorten finden Sie im Abschnitt "Vorbereiten der Ausfallsicherheit für VoIP-Funktionen" weiter unten in diesem Thema. Ausführliche Informationen zu Wählplänen und Normalisierungsregeln sowie weitere Beispielregeln finden Sie unter [Wählpläne und Normalisierungsregeln in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in der Planungsdokumentation und unter [Konfigurieren von Wählplänen in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) in der Bereitstellungsdokumentation. Ausführliche Informationen zu ausgehenden Übersetzungsregeln finden Sie unter [Übersetzungsregeln in Lync Server 2013](lync-server-2013-translation-rules.md) in der Planungsdokumentation und unter [Definieren von Übersetzungsregeln in Lync Server 2013](lync-server-2013-defining-translation-rules.md) in der Bereitstellungsdokumentation.

## Vorbereiten der Ausfallsicherheit für VoIP-Funktionen

Exchange Unified Messaging (UM) wird in der Regel am zentralen Standort und nicht an Zweigstellen installiert. Ein Anrufer sollte auch dann eine Voicemailnachricht hinterlassen können, wenn die WAN-Verbindung zwischen Zweigstelle und zentralem Standort nicht verfügbar ist. Infolgedessen erfordert die Konfiguration des Anschluss-URIs für die Exchange UM-Rufnummer der automatischen Telefonzentrale, die Voicemailfunktionen für Zweigstellenbenutzer bereitstellt, neben der VoIP-Richtlinie, dem Wählplan und den Normalisierungsregeln, die für diese Voicemailnummer gelten, besondere Überlegungen.

Survivable Branch-Anwendungen (SBAs) und Survivable Branch-Server bieten Ausfallsicherheit für VoIP-Funktionen für Zweigstellenbenutzer während eines WAN-Ausfalls. Das heißt, wenn Sie eine Survivable Branch-Anwendung oder einen Survivable Branch-Server verwenden, leitet die SBA oder der Survivable Branch-Server nicht beantwortete Anrufe bei einem WAN-Ausfall über das Festnetz an Exchange UM am zentralen Standort um. Mit einer SBA oder einem Survivable Branch-Server können die Benutzer außerdem während eines WAN-Ausfalls Voicemailnachrichten über das Festnetz abrufen. Zudem platziert die Survivable Branch-Anwendung oder der Survivable Branch-Server Benachrichtigungen über entgangene Anrufe in einer Warteschleife und lädt sie dann auf den Exchange UM-Server hoch, sobald das WAN wiederhergestellt ist. Damit die Umleitung von Voicemailnachrichten ausfallsicher ist, fügen Sie der Hostdatei des Survivable Branch-Servers unbedingt einen Eintrag für den FQDN des Pools am zentralen Standort und einen Eintrag für den FQDN des Edgeservers hinzu. Andernfalls kann es bei der DNS-Auflösung zu einem Timeout kommen, wenn an der Zweigstelle kein DNS-Server vorhanden ist.

Für die Bereitstellung ausfallsicherer VoIP-Funktionen für Zweigstellenbenutzer werden die folgenden Konfigurationen empfohlen:

  - Ein Microsoft Exchange-Administrator sollte die automatische Exchange UM-Telefonzentrale so konfigurieren, dass nur Nachrichten angenommen werden. Durch diese Konfiguration wird jede andere allgemeine Funktionalität deaktiviert, beispielsweise das Durchstellen an einen Benutzer oder an einen Agent, und beschränkt die automatische Telefonzentrale auf die Annahme von Nachrichten. Alternativ dazu kann der Exchange-Administrator auch eine allgemeine automatische Telefonzentrale oder eine benutzerdefinierte automatische Telefonzentrale zum Routen des Anrufs an einen Agent verwenden.

  - Der Lync Server-Administrator sollte die Rufnummer der automatischen Telefonzentrale als Rufnummer für **Automatische Exchange UM-Telefonzentrale** in den Voicemailumleitungseinstellungen für die Survivable Branch-Anwendung oder den Zweigstellenserver verwenden.

  - Der Lync Server-Administrator sollte die Exchange UM-Rufnummer für den Teilnehmerzugriff erhalten und diese als Rufnummer für den **Teilnehmerzugriff** in den Voicemailumleitungseinstellungen für die Survivable Branch-Anwendung oder den Survivable Branch-Server verwenden.

  - Der Lync Server-Administrator sollte Exchange UM so konfigurieren, dass nur ein Satz mit Wähleinstellungen allen Zweigstellenbenutzern zugeordnet wird, die während eines WAN-Ausfalls auf die Voicemail zugreifen müssen.

  - Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an den Exchange Unified Messaging (UM)-Sprachposteingang des Benutzers umgeleitet werden, jedoch nur, wenn die auf den Anruf angewendete VoIP-Richtlinie eine Voicemailtelefonnummer angibt, die eindeutig ist und keine Durchwahlnummer enthält.

## Hardware- und Softwareanforderungen für die Ausfallsicherheit am Zweigstellenstandort

Die Hardware- und Softwareanforderungen variieren je nach Ausfallsicherheitslösung.

## Anforderungen für Survivable Branch Appliances

Die erforderliche Hardware und Software sind in der Survivable Branch-Anwendung integriert. Es wird jedoch außerdem empfohlen, an jedem Zweigstellenstandort einen DHCP-Server zum Abrufen von Client-IP-Adressen bereitzustellen. Andernfalls steht den Clients bei Ablauf der DHCP-Lease keine IP-Konnektivität zur Verfügung.

Wenn die DNS-Server des Unternehmens sich nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung zu diesen herstellen, daher tritt bei der Lync Server-Ermittlung, die DNS SRV (Ressourceneintrag für Dienste) verwendet, ein Fehler auf. Damit eine sofortige Umleitung während eines WAN-Ausfalls gewährleistet ist, müssen DNS-Einträge am Zweigstellenstandort zwischengespeichert werden. Wenn der Zweigstellenrouter die DNS-Zwischenspeicherung unterstützt, aktivieren Sie sie. Sie können auch einen DNS-Server in der Zweigstelle bereitstellen. Dies kann ein eigenständiger Server oder eine Version der Survivable Branch-Anwendung sein, die DNS-Funktionen unterstützt. Ausführliche Informationen erhalten Sie beim Anbieter der Survivable Branch-Anwendung.


> [!NOTE]
> Es ist nicht erforderlich, an jedem Zweigstellenstandort einen Domänencontroller zu verwenden. Die Survivable Branch-Anwendung authentifiziert Clients über ein spezielles Zertifikat, das dem Client als Antwort auf seine Zertifikatanforderung bei der Anmeldung gesendet wird.



Lync-Clients können den Lync Server über die DHCP-Option 120 (SIP-Registrierungsoption) ermitteln. Dies ist mit einer von zwei Konfigurationen möglich:

  - Konfigurieren Sie den DHCP-Server am Zweigstellenstandort für die Antwort auf DHCP 120-Abfragen, welche den FQDN der Registrierung auf der Survivable Branch-Anwendung oder dem Survivable Branch-Server zurückgeben.

  - Aktivieren Sie Lync Server DHCP. Wenn DHCP aktiviert ist, reagiert die Lync Server-Registrierung auf Abfragen der DHCP-Option 120. Beachten Sie, dass die Registrierung nicht auf andere DHCP-Abfragen als DHCP-Option 120 reagiert.

Zusätzlich sollten für größere Zweigstellenstandorte mit mehreren Subnetzen DHCP-Relay-Agents aktiviert werden, um Abfragen der DHCP-Option 120 an den DHCP Server (Konfiguration 1) oder die Registrierung (Konfiguration 2) weiterzuleiten.

Schließlich müssen die Benutzer des Zweigstellenstandorts für Enterprise-VoIP konfiguriert und mit einem geeigneten Unified Communications-Endpunkt ausgestattet werden.

## Anforderungen für Survivable Branch Server

Die Anforderungen für Survivable Branch-Server sind identisch mit den Anforderungen für eine Front-End-Server. Ausführliche Informationen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Planungsdokumentation.

## Anforderungen für vollständige Lync Server-Bereitstellungen am Zweigstellenstandort

Ausführliche Informationen finden Sie unter [Ermitteln Ihrer Infrastrukturanforderungen für Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in der Planungsdokumentation.

