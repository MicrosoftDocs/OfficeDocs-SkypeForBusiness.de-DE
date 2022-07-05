---
title: Lokale Medienoptimierung für Direct Routing
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Lokale Medienoptimierung für Direct Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c33b8225f3bcde32428348e85166ff4d4463738
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616091"
---
# <a name="plan-for-local-media-optimization-for-direct-routing"></a>Planen der lokalen Medienoptimierung für Direct Routing

PSTN-VoIP (Public Switched Telephone Network) gilt als geschäftskritische Anwendung mit hohen Erwartungen an die Sprachqualität. Mit Direct Routing können Sie Mediendatenverkehrsflüsse steuern, um eine Vielzahl von Netzwerktopologien und lokalen Telefonie-Setups für verschiedene Unternehmen auf der ganzen Welt zu berücksichtigen.

Mit der lokalen Medienoptimierung für Direct Routing können Sie die Sprachqualität wie folgt verwalten:

- Steuern, wie der Mediendatenverkehr zwischen den Teams-Clients und den Session Border Controllern (SBCs) des Kunden fließt.
- Halten Sie Medien lokal innerhalb der Grenzen von Unternehmensnetzwerksubnetzen.
- Zulassen von Mediendatenströmen zwischen den Teams-Clients und den SBCs, auch wenn sich die SBCs hinter Unternehmensfirewalls mit privaten IPs befinden und nicht direkt für Microsoft sichtbar sind.

Die lokale Medienoptimierung unterstützt zwei Szenarien:

- Zentralisierung aller lokalen Trunks über einen zentralisierten SBC, der mit dem Haupttrunk des Session Initiation Protocol (SIP) verbunden ist und Telefoniedienste für alle lokalen Niederlassungen des Unternehmens bereitstellt.

- Erstellen einer virtuellen Netzwerktopologie von SBCs – wo die SBCs in den lokalen Zweigstellen mit einem zentralen Proxy-SBC verbunden sind, der für das Microsoft-Telefonsystem über seine externe IP-Adresse sichtbar ist und mit diesem kommuniziert. In einer virtuellen Netzwerktopologie kommunizieren nachgeschaltete SBCs über interne IPs und sind für das Telefonsystem nicht direkt sichtbar.

In diesem Artikel werden Featurefunktionen sowie Kundenszenarien und -lösungen beschrieben. Ausführliche Informationen zur Konfiguration finden [Sie unter Configure Local Media Optimization.For details on configuration, see Configure Local Media Optimization](direct-routing-media-optimization-configure.md).

  > [!NOTE]
  > Wenn Sie Medien lokal innerhalb der Grenzen Ihres Intranets halten möchten, wird die lokale Medienoptimierung empfohlen. Wenn Sie bereits über die Medienumgehung verfügen und nur die öffentlichen IP-Adressen Ihrer SBCs verwenden, ist es nicht zwingend erforderlich, zur lokalen Medienoptimierung zu wechseln. Sie können die Medienumgehung weiterhin verwenden. Weitere Informationen finden Sie unter [Planen der Medienumgehung](direct-routing-plan-media-bypass.md).

Informationen dazu, welche SBC-Anbieter die lokale Medienoptimierung unterstützen, finden Sie unter [Session Border Controllers Certified for Direct Routing](direct-routing-border-controllers.md).

## <a name="supported-customer-scenarios"></a>Unterstützte Kundenszenarien

Gehen Sie bei dieser Diskussion davon aus, dass Contoso wie folgt mehrere Unternehmen auf der ganzen Welt betreibt. (Beachten Sie, dass die Regionen Europa und APAC nur als Beispiele verwendet werden. Ein Unternehmen kann mehrere unterschiedliche Regionen mit ähnlichen Anforderungen haben.)

- **In Europa** hat Contoso Niederlassungen in rund 30 Ländern. Jedes Büro verfügt über eine eigene Nebenstellenanlage (Private Branch Exchange).

  Contoso wurde für alle 30 europäischen Büros die Möglichkeit angeboten, die Trunks an einem Ort zu zentralisieren – Amsterdam. Contoso stellte den SBC in Amsterdam bereit, stellte genügend Bandbreite bereit, um Anrufe über den zentralen Standort auszuführen, einen zentralen SIP-Trunk an den zentralen Standort anzugebunden und begann, alle europäischen Standorte von Amsterdam aus zu bedienen.

- **In der Region APAC** verfügt Contoso über mehrere Niederlassungen in verschiedenen Ländern.

  In vielen Ländern verfügt das Unternehmen weiterhin über TDM-Trunks (Time-Division Multiplexing) in lokalen Zweigstellen. Die Zentralisierung der TDM-Trunks ist in der APAC-Region keine Option, daher ist ein Wechsel zu SIP nicht möglich. Angenommen, es gibt mehr als 50 Contoso-Niederlassungen in der region APAC mit Hunderten von Gateways (SBCs). In diesem Szenario ist es nicht möglich, alle Gateways mit der Direct Routing-Schnittstelle zu koppeln, da keine öffentlichen IP-Adressen und/oder lokalen Internet-Breakouts vorhanden sind. Darüber hinaus stellen einige Länder gesetzliche Anforderungen, die ohne lokale PSTN-Netzwerkkonnektivität nicht erfüllt werden können.

Basierend auf ihren Geschäftsanforderungen implementierte Contoso zwei Lösungen mit der lokalen Medienoptimierung für Direct Routing:

- **In Europa** werden alle Trunks zentralisiert und medienbasiert zwischen dem zentralen SBC und den Benutzern fließen.

  - Wenn ein Benutzer mit dem lokalen Subnetz eines Unternehmensnetzwerks verbunden ist (d. h. der Benutzer ist intern), fließen die Medien zwischen der internen IP des zentralen SBC und dem Teams-Client des Benutzers.

  - Wenn sich ein Benutzer außerhalb der Grenzen des Unternehmensnetzwerks befindet , z. B. wenn der Benutzer eine öffentliche drahtlose Internetverbindung verwendet, wird der Benutzer als extern betrachtet. In diesem Fall fließen die Medien zwischen der externen IP des zentralen SBC und dem Teams-Client.

- **In der APAC-Region** wird ein zentralisierter Proxy-SBC mit Microsoft Direct Routing gekoppelt, der Medien zwischen der Direct Routing-Schnittstelle und den nachgelagerten SBCs in lokalen Zweigstellen leitet.

  Die nachgeschalteten SBCs in den lokalen Zweigstellen sind für Direct Routing in APAC nicht direkt sichtbar, werden jedoch mit dem cmdlet Set-CSOnlinePSTNGateway gekoppelt, um eine virtuelle Netzwerktopologie innerhalb von Microsoft Phone System zu erstellen. Medien bleiben nach Möglichkeit immer lokal. Externe Benutzer verfügen über Medien, die zwischen dem Teams-Client und der öffentlichen IP des Proxy-SBC fließen.

## <a name="central-sbc-with-centralized-trunks"></a>Zentraler SBC mit zentralisierten Trunks

Um eine Lösung zu erstellen, bei der PSTN-Dienste für alle lokalen Zweigstellen über einen einzigen zentralen SBC mit einem verbundenen zentralen SIP-Trunk bereitgestellt werden, paart der Contoso-Mandantenadministrator einen SBC (centralsbc.contoso.com) mit dem Dienst. der SBC verfügt über einen zentralisierten SIP-Trunk, der mit diesem verbunden ist.

- Wenn sich ein Benutzer im internen Netzwerk des Unternehmens befindet, stellt der SBC die interne IP des SBC für Medien bereit.

- Wenn sich ein Benutzer außerhalb des Unternehmensnetzwerks befindet, stellt der SBC die externe (öffentliche) IP des SBC bereit.

> [!NOTE]
> Alle Werte in Beispielen, Tabellen oder Diagrammen werden nur zu Veranschaulichungszwecken dargestellt.

Tabelle 1. Beispiel für Netzwerkparameter für SBCs

| Ort | SBC-FQDN | Internes Subnetz | Externe NAT (Vertrauenswürdige IP) | Externe SBC-IP-Adresse | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Deutschland | Nicht bereitgestellt | 192.168.6.0/24 | 172.16.76.74 | Nicht bereitgestellt |  Nicht bereitgestellt |
| Frankreich | Nicht bereitgestellt | 192.168.7.0/24 | 172.16.76.75 | Nicht bereitgestellt |  Nicht bereitgestellt |

### <a name="internal-user"></a>Interner Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn ein Benutzer mit dem Unternehmensnetzwerk in der Heimniederlassung oder am Standort des Benutzers verbunden ist.

Während der lokalen Bereitstellung wird der Benutzer der lokalen Zweigstelle in Deutschland zugewiesen. Der Benutzer führt einen Direct Routing-Telefonanruf über Teams.

- Der Teams-Client des Benutzers kommuniziert mit dem Telefonsystem direkt über die REST-API, aber die während des Anrufs generierten Medien fließen an die interne IP-Adresse des zentralen SBC.

- Der SBC leitet den Fluss an das Telefonsystem und das verbundene PSTN-Netzwerk um.

- Der zentrale SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar.

Diagramm 1. Datenverkehrsfluss, wenn sich der Benutzer am "Startstandort" mit einem zentralen SBC und einem angeschlossenen zentralisierten SIP-Trunk befindet

![Diagramm, das die Lokale Medienoptimierung für den Datenverkehrsfluss zeigt.](media/direct-routing-media-op-1.png "Datenverkehrsfluss, wenn sich der Benutzer am &quot;Startstandort&quot; mit zentralisiertem SBC mit angeschlossenem zentralisiertem SIP-Trunk befindet")


### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn ein Benutzer nicht lokal und nicht mit dem Unternehmensnetzwerk verbunden ist (das heißt, das Gerät des Benutzers ist über ein mobiles Gerät oder öffentliches WLAN mit dem Internet verbunden). Der Benutzer führt einen Direct Routing-Telefonanruf über Teams durch:

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem, in diesem Fall werden jedoch die während des Anrufs generierten Medien an die externe IP-Adresse des zentralen SBC übermittelt.

- Der SBC leitet den Fluss an das Telefonsystem und das verbundene PSTN-Netzwerk um.

- Der zentrale SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar.

In diesem Fall ist das Verhalten ähnlich, unabhängig davon, ob sich der Benutzer lokal in der Zweigstelle in Deutschland oder in einer anderen Zweigstelle befindet. Der Benutzer wird als extern betrachtet, da sich der Benutzer außerhalb der Grenzen des Unternehmensnetzwerks befindet.

Diagramm 2. Datenverkehrsfluss, wenn der Benutzer extern mit einem zentralen SBC und einem angeschlossenen zentralisierten SIP-Trunk ist

![Diagramm zeigt die Lokale Medienoptimierung für den Datenverkehrsfluss.](media/direct-routing-media-op-2.png "Datenverkehrsfluss, wenn der Benutzer bei einem zentralen SBC mit angeschlossenem zentralisiertem SIP-Trunk extern ist")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy-SBC mit angeschlossenen nachgeschalteten SBCs

Um eine Lösung zu erstellen, bei der PSTN-Dienste in allen lokalen Niederlassungen in der Region APAC bereitgestellt werden, bei der die Zentralisierung der TDM-Trunks keine Option ist, paart der Contoso-Administrator einen SBC (proxysbc.contoso.com), auch als Proxy-SBC bezeichnet, mit dem Direct Routing-Dienst.

Anschließend fügt der Contoso-Administrator einige nachgeschaltete SBCs hinzu, die angeben, dass sie über die Proxy-SBC-proxysbc.contoso.com erreicht werden können. Nachgeschaltete SBCs verfügen nicht über öffentliche IPs, sie können jedoch VoIP-Routen zugewiesen werden. Die folgende Tabelle zeigt Beispielnetzwerkparameter und -konfiguration.

Wenn sich ein Benutzer in der lokalen Zweigstelle befindet, in der sich der nachgeschaltete SBC befindet, fließt der Mediendatenverkehr zwischen dem Benutzer und dem lokalen nachgelagerten SBC direkt. Wenn sich ein Benutzer außerhalb des Büros (in einem öffentlichen Internet) befindet, fließen die Medien vom Benutzer zur öffentlichen IP des Proxy-SBC, der ihn an die entsprechenden nachgeschalteten SBC(s) weitergibt.

Tabelle 2. Beispiel für SBC-Netzwerkinformationen

| Ort | SBC-FQDN | Internes Subnetz | Externe NAT (Vertrauenswürdige IP) | Externe SBC-IP-Adresse  | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Keine |  192.168.1.5 |
| Indonesien  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Keine |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Interner Benutzer

Das folgende Diagramm zeigt den allgemeinen Datenverkehrsfluss für das Szenario, wenn sich ein Benutzer im Büro in der APAC-Region befindet.
Der Benutzer, der einer lokalen Zweigstelle in Vietnam zugewiesen ist und lokal ist, führt einen Direct Routing-Telefonanruf über Teams durch.

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem, während der Anrufflüsse jedoch an die interne IP-Adresse des lokalen SBC generiert werden.

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das verbundene lokale PSTN-Netzwerk um.

-  Der Proxy-SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar und leitet den Fluss vom nachgeschalteten SBC (in diesem Fall dem lokalen SBC in Vietnam) an das Telefonsystem weiter.

- Der nachgeschaltete SBC in der lokalen Zweigstelle ist für das Telefonsystem nicht direkt sichtbar, sondern wird innerhalb der topologie des virtuellen Netzwerks zugeordnet, die vom Contoso-Administrator beim Einrichten der lokalen Medienoptimierung definiert wird.

> [!NOTE]
> Das Verhalten kann für lokale Benutzer und nicht lokale Benutzer je nach konfiguriertem Modus für die lokale Medienoptimierung unterschiedlich sein.

Weitere Informationen zu möglichen Modi und relevantem Verhalten finden Sie unter Configure Local Media Optimization.

Diagramm 3. Datenverkehrsfluss, wenn sich der Benutzer im Heimnetzwerk mit einem Proxy-SBC und mit angeschlossenen nachgeschalteten SBCs befindet

![Diagramm, das erneut die Optimierung des Datenverkehrsflusses für lokale Medien zeigt.](media/direct-routing-media-op-3.png "Traffic flow in case of proxy SBC with connected downstream SBCs when user is in the \"home\" network")

### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn sich ein Benutzer außerhalb der Unternehmensnetzwerkgrenzen befindet. Der Benutzer ist nicht lokal (nicht innerhalb der Grenzen des Unternehmensnetzwerks). Der Benutzer führt einen Direct Routing-Telefonanruf über Teams an eine Telefonnummer in Vietnam.

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem, die während des Anrufs generierten Medien fließen jedoch zuerst an die externe IP-Adresse des Proxy-SBC in Singapur.

- Basierend auf Konfigurations- und VoIP-Richtlinien (details finden [Sie unter Konfigurieren der lokalen Medienoptimierung](direct-routing-media-optimization-configure.md) ) leitet der Proxy-SBC den Fluss an den nachgelagerten SBC in Vietnam um.

- Der nachgeschaltete SBC in Vietnam leitet den Fluss an das verbundene lokale PSTN-Netzwerk um.

- Der Proxy-SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar.

-  Der nachgeschaltete SBC in der lokalen Zweigstelle ist für das Telefonsystem nicht direkt sichtbar, sondern innerhalb der topologischen Virtuellen Netzwerkverbindung zugeordnet, die vom Contoso-Administrator beim Einrichten der lokalen Medienoptimierung definiert wird. In diesem Beispiel wird der Benutzer als extern betrachtet, da sich der Benutzer außerhalb der Grenzen des Unternehmensnetzwerks befindet.

Diagramm 4. Datenverkehrsfluss, wenn der Benutzer extern mit einem Proxy-SBC und mit verbundenen nachgeschalteten SBCs ist

![Das Diagramm zeigt erneut die Optimierung des Datenverkehrsflusses für lokale Medien.](media/direct-routing-media-op-4.png "Datenverkehrsfluss bei Proxy-SBC mit verbundenen nachgeschalteten SBCs, wenn der Benutzer extern ist")

## <a name="local-media-optimization-modes"></a>Lokale Medienoptimierungsmodi

Die lokale Medienoptimierung unterstützt zwei Modi:

- **Modus 1: Immer umgehen**. Wenn der Benutzer intern ist, fließen die Medien in diesem Fall unabhängig vom tatsächlichen Standort des internen Benutzers durch die interne IP-Adresse des lokalen downstream SBC. beispielsweise innerhalb derselben Zweigstelle, in der sich der nachgeschaltete SBC befindet, oder in einer anderen Zweigstelle.

- **Modus 2: Nur für lokale Benutzer**. In diesem Modus fließen Medien nur dann direkt an die interne IP-Adresse des lokalen downstream SBC, wenn sie vom internen Benutzer generiert werden, der sich in derselben Zweigstelle wie der nachgeschaltete SBC befindet.

Um zwischen Modi für die lokale Medienoptimierung zu unterscheiden, muss der Mandantenadministrator den Parameter "-BypassMode" für jeden SBC entweder auf "Always" oder "OnlyForLocalUsers" festlegen, indem er das cmdlet Set-CSonlinePSTNGateway verwendet. Weitere Informationen finden [Sie unter Configure Local Media Optimization](direct-routing-media-optimization-configure.md).

> [!NOTE]
> Wenn Benutzer intern sind, ist eine Medienkonnektivität zwischen dem Benutzer und dem SBC über die interne IP-Adresse **erforderlich**. In diesem Fall gibt es keinen Fallback auf Relays für den öffentlichen Verkehr für Medien, da der SBC eine interne IP für die Medienkonnektivität bereitstellt.

### <a name="mode-1-always-bypass"></a>Modus 1: Immer umgehen

Wenn Sie über eine gute Verbindung zwischen Zweigstellen verfügen, ist der empfohlene Modus "Immer umgehen".

Angenommen, ein Unternehmen verfügt über einen zentralen SIP-Trunk in Amsterdam, der 30 Länder bedient und eine gute Konnektivität zwischen allen 30 Standorten und lokalen Benutzern hat. Es gibt auch eine Niederlassung in Deutschland, in der ein lokaler SBC bereitgestellt wird.

Der SBC in Deutschland kann im Modus "Immer umgehen" konfiguriert werden. Benutzer stellen unabhängig von ihrem Standort eine direkte Verbindung mit dem SBC über die interne IP-Adresse des SBC her (z. B. von Frankreich nach Deutschland; siehe nachstehende Abbildung).

Im Folgenden werden zwei Szenarien beschrieben:

- Szenario 1. Der Benutzer befindet sich am selben Ort wie der in der Online-VoIP-Routingrichtlinie definierte SBC.

- Szenario 2. Der Benutzer und die Gateways befinden sich an verschiedenen Standorten.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Szenario 1. Der Benutzer befindet sich am selben Speicherort wie der in der Online-VoIP-Routingrichtlinie definierte SBC.

Der SBC in Amsterdam ist als Proxy-SBC für einen lokalen downstream SBC in Deutschland konfiguriert. Der Benutzer befindet sich in Deutschland im selben Subnetz wie das Unternehmensnetzwerk des lokalen SBC. Sowohl SBCs (Proxy als auch Downstream) sind für den Modus "Immer umgehen" konfiguriert. Online-VoIP-Routingrichtlinien geben an, dass sie bei Anrufen innerhalb Deutschlands (mit Vorwahl +49) an den lokalen SBC in Deutschland weitergeleitet werden sollen. Alle anderen Anrufe - und falls der SBC in Deutschland fehlschlägt, Anrufe in Deutschland - sollten an den Proxy-SBC in Amsterdam weitergeleitet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst.

Tabelle 3. Beispielkonfiguration für Szenario 1

| Physischer Standort des Benutzers | Der Benutzer ruft eine Nummer an | Online-VoIP-Routingrichtlinie | Für SBC konfigurierter Modus | Medienfluss |
|:------------|:-------|:-------|:-------|:-------|
| Deutschland | +49 1 437 2800 | Priorität 1: ^\+49(\d{8})$ -DEsbc.contoso.com<br>Priorität 2: .* - proxysbc.contoso.com| DEsbc.contoso.com – Immer umgehen <br>proxysbc.contoso.com – Immer umgehen | Teams-Benutzer <–> DEsbc.contoso.com |

Das folgende Diagramm zeigt den allgemeinen Datenverkehrsfluss für den internen Benutzer in Deutschland, der einen Direct Routing-Telefonanruf über Teams an die Nummer in Deutschland führt.

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem.

- Die während des Anrufs generierten Medien fließen an die interne IP-Adresse des lokalen SBC.

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Amsterdam und an das verbundene lokale PSTN-Netzwerk um.

- Der Proxy-SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar und leitet den Fluss vom nachgeschalteten SBC (in diesem Fall dem lokalen SBC in Deutschland) an das Telefonsystem weiter.

- Der nachgeschaltete SBC in der lokalen Zweigstelle ist für das Telefonsystem nicht direkt sichtbar, sondern wird innerhalb der topologie des virtuellen Netzwerks zugeordnet, die vom Contoso-Administrator beim Einrichten der lokalen Medienoptimierung definiert wird.


Diagramm 5.  Datenverkehrsfluss mit dem Modus "Immer umgehen", und der Benutzer befindet sich auf der "Startseite"

! [Ein Diagramm, das die Optimierung des Datenverkehrsflusses für lokale Medien zeigt.] (Medien/direct-routing-media-op-5.png "Datenverkehrsfluss mit "Immer umgehen"-Modus und Benutzer befindet sich auf der Startseite")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2: Benutzer und Gateways befinden sich an verschiedenen Standorten

Der SBC in Amsterdam ist als Proxy-SBC für einen lokalen downstream SBC in Deutschland konfiguriert. Sowohl SBCs (Proxy als auch Downstream) sind für den Modus "Immer umgehen" konfiguriert. Der interne Benutzer in Frankreich, der sich in der lokalen Zweigstelle befindet, führt einen Direct Routing-Anruf nach Deutschland durch. Online-VoIP-Routingrichtlinien geben an, dass Anrufe nach Deutschland (mit Vorwahl +49) an den lokalen SBC in Deutschland weitergeleitet werden sollen. Alle anderen Anrufe - und falls der SBC in Deutschland fehlschlägt, alle Anrufe in Deutschland - sollten an den Proxy-SBC in Amsterdam weitergeleitet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst.

Tabelle 4. Beispielkonfiguration für Szenario 2

| Physischer Standort des Benutzers | Der Benutzer ruft eine Nummer an | Online-VoIP-Routingrichtlinie | Für SBC konfigurierter Modus | Medienfluss |
|:------------|:-------|:-------|:-------|:-------|
| Frankreich | +49 1 437 2800 | Priorität 1: ^\+49(\d{8})$ -DEsbc.contoso.com <br>Priorität 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com – Immer umgehen proxysbc.contoso.com – Immer umgehen | Teams-Benutzer <– > DEsbc.contoso.com  |

Das folgende Diagramm zeigt den allgemeinen Datenverkehrsfluss, wenn der interne deutsche Benutzer mit Sitz in Frankreich einen Direct Routing-Telefonanruf über Teams an die Nummer in Deutschland führt.

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem.

- Die während des Anrufs generierten Medien fließen direkt an den SBC in der internen IP-Adresse Deutschlands.

- Der SBC in Deutschland leitet den Fluss an den Proxy-SBC in Amsterdam und an das verbundene lokale PSTN-Netzwerk um.

Diagramm 6.  Datenverkehrsfluss mit dem Modus "Immer umgehen" und der Benutzer befindet sich nicht auf der "Startseite", sondern im internen Netzwerk.

! [Ein Diagramm zeigt die Optimierung des Datenverkehrsflusses für lokale Medien.] (Medien/direct-routing-media-op-6.png "Datenverkehrsfluss mit Dem Modus "Immer umgehen" und der Benutzer befindet sich nicht an der "Startseite", sondern im internen Netzwerk")

### <a name="mode-2-only-for-local-users"></a>Modus 2: Nur für lokale Benutzer

Wenn es schlechte Verbindungen zwischen lokalen Zweigstellen, aber gute Verbindungen zwischen jeder lokalen Zweigstelle und regional office gibt, ist der empfohlene Modus "Nur für lokale Benutzer".

Gehen Sie beispielsweise in der Region APAC davon aus, dass Contoso über mehrere Niederlassungen in verschiedenen Ländern verfügt. In vielen Ländern ist ein Umstieg auf SIP nicht möglich, da das Unternehmen noch immer TDM-Trunks in vielen lokalen Niederlassungen hat. Die Zentralisierung der TDM-Trunks ist in der Region APAC keine Option. Darüber hinaus gibt es mehr als 50 Contoso-Niederlassungen in der region APAC mit Hunderten von Gateways (SBCs).

Um eine Lösung zu erstellen, bei der PSTN-Dienste in allen lokalen Niederlassungen in der Region APAC bereitgestellt werden, bei der die Zentralisierung der TDM-Trunks keine Option ist, paart der Contoso-Administrator einen regionalen SBC in Singapur als Proxy-SBC mit dem Direct Routing-Dienst. Die direkte Verbindung zwischen den lokalen Niederlassungen ist nicht gut, aber es besteht eine gute Verbindung zwischen jeder lokalen Zweigstelle und dem regionalen SBC in Singapur. Für den regionalen SBC wählt der Administrator den Modus "Immer umgehen" aus, und für die lokalen nachgeschalteten SBCs wählt der Administrator den Modus "Nur für lokale Benutzer" aus.

Im Folgenden werden zwei Szenarien beschrieben:

- Szenario 1. Der Benutzer befindet sich am selben Speicherort wie der in der Online-VoIP-Routingrichtlinie definierte SBC.

- Szenario 2. Der Benutzer und die Gateways befinden sich an verschiedenen Standorten.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Szenario 1. Der Benutzer befindet sich am selben Speicherort wie der in der Online-VoIP-Routingrichtlinie definierte SBC.

Angenommen, der SBC in Singapur ist als Proxy-SBC für die lokalen nachgeschalteten SBCs in Vietnam und Indonesien konfiguriert. Der Benutzer befindet sich in Vietnam an demselben Ort wie der lokale SBC. Online-VoIP-Routingrichtlinien geben an, dass Anrufe in Vietnam (mit Vorwahl +84) an den lokalen SBC in Vietnam weitergeleitet werden sollen. Alle anderen Anrufe - und wenn der SBC in Vietnam fehlschlägt, Anrufe in Vietnam - sollten an den Proxy-SBC in Singapur weitergeleitet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst.

Tabelle 5. Beispielkonfiguration für den Modus "Nur für lokale Benutzer" Szenario 1

| Physischer Standort des Benutzers | Der Benutzer ruft eine Nummer an | Online-VoIP-Routingrichtlinie | Für SBC konfigurierter Modus | Medienfluss |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Priorität 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br>Priorität 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – Nur für lokale Benutzer <br> proxysbc.contoso.com – Immer umgehen | Teams-Benutzer <–> VNsbc.contoso.com |

Im folgenden Diagramm führt ein Benutzer, der der lokalen Zweigstelle in Vietnam zugewiesen ist, vor Ort einen Direct Routing-Telefonanruf über Teams.

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem.

- Medien, die während des Anrufs generiert werden, werden an die interne IP-Adresse des lokalen SBC weitergeleitet.

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das verbundene lokale PSTN-Netzwerk um.

- Der Proxy-SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar und leitet den Fluss vom nachgeschalteten SBC (in diesem Fall dem lokalen SBC in Vietnam) an das Telefonsystem weiter.

- Der nachgeschaltete SBC in der lokalen Zweigstelle ist für das Telefonsystem nicht direkt sichtbar, wird aber in der topologischen Virtuellen Netzwerkgruppe zugeordnet.

Diagramm 7. Datenverkehrsfluss mit dem Modus "Nur für lokale Benutzer", und der Benutzer befindet sich auf der "Startseite"

! [Ein weiteres Diagramm, das die Optimierung des Datenverkehrsflusses für lokale Medien zeigt.] (Medien/direct-routing-media-op-7.png "Datenverkehrsfluss mit dem Modus "Nur für lokale Benutzer", und der Benutzer befindet sich auf der Startseite")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2. Der Benutzer und die Gateways befinden sich an verschiedenen Standorten.

Angenommen, der SBC in Singapur ist als Proxy-SBC für die lokalen nachgeschalteten SBCs in Vietnam und Indonesien konfiguriert. Der interne Benutzer in Indonesien, der sich in der lokalen Zweigstelle befindet, führt einen Direct Routing-Anruf nach Vietnam durch. Online-VoIP-Routingrichtlinien geben an, dass Anrufe nach Vietnam (mit Vorwahl +84) an den lokalen SBC in Vietnam weitergeleitet werden sollen. Alle anderen Anrufe - und im Falle eines Ausfalls des SBC in Vietnam - sollten an den Proxy-SBC in Singapur weitergeleitet werden. Der Proxy-SBC in Singapur ist auf den Modus "Immer umgehen" und der lokale SBC in Vietnam auf "Nur für lokale Benutzer" festgelegt. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst.

Tabelle 6. Benutzerkonfiguration

| Physischer Standort des Benutzers | Der Benutzer ruft eine Nummer an | Online-VoIP-Routingrichtlinie | Für SBC konfigurierter Modus | Medienfluss |
|:------------|:-------|:-------|:-------|:-------|
| Indonesien | +84 4 3926 3000 | Priorität 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Priorität 2: .* - proxysbc.contoso.com |VNsbc.contoso.com – Nur für lokale Benutzer <br> proxysbc.contoso.com – Immer umgehen | Teams-Benutzer <–> proxysbc.contoso.com <–> VNsbc.contoso.com |


Im folgenden Diagramm führt der interne Benutzer vor Ort in der indonesischen Niederlassung einen Direct Routing-Telefonanruf über Teams an eine Nummer in Vietnam.

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit dem Telefonsystem.

- Medien, die während des Anrufflusses zuerst an die interne IP-Adresse des Proxy-SBC generiert wurden.

- Der Proxy-SBC in Singapur leitet den Fluss an die interne IP-Adresse des nachgelagerten SBC in Vietnam und an das Telefonsystem um.

- Der downstream SBC in Vietnam leitet den Fluss an das verbundene lokale PSTN-Netzwerk weiter.

- Der Proxy-SBC ist für das Telefonsystem nur über die externe IP-Adresse sichtbar.

- Die nachgeschalteten SBCs in lokalen Zweigstellen sind für das Telefonsystem nicht direkt sichtbar, werden aber innerhalb der virtuellen Netzwerktopologie zugeordnet.The downstream SBCs in local branch offices are not visible to Phone System directly but are mapped within the virtual network topology.

Diagramm 8.  Datenverkehrsfluss mit dem Modus "Nur für lokale Benutzer", und der Benutzer befindet sich nicht auf der "Startseite", sondern im internen Netzwerk.

! [Ein weiteres Diagramm zeigt die Optimierung des Datenverkehrsflusses für lokale Medien.] (Medien/direct-routing-media-op-8.png "Datenverkehrsfluss mit dem Modus "Nur für lokale Benutzer", der Benutzer befindet sich nicht an der "Startseite", sondern im internen Netzwerk")

## <a name="known-issues"></a>Bekannte Probleme

Es folgt eine Liste bekannter Probleme, die derzeit in der lokalen Medienoptimierung vorhanden sind. Microsoft arbeitet daran, diese Probleme zu beheben.

| Problem | Problemumgehung |
| :--- | :--- |
| Der Teams-Client wird nicht als **intern** identifiziert, wenn der Teams-Client mit der Liste der vertrauenswürdigen IP-Adressen des Kunden übereinstimmt. | Die lokale Medienoptimierung erfordert, dass das Teams-Clientsubnetz einem mandantenkonfigurierten [Netzwerksubnetz](/powershell/module/skype/new-cstenantnetworksubnet) entspricht.|
| Anrufeskalationen führen zu abgebrochenen Anrufen, wenn der Teams-Client als intern identifiziert wird.| Deaktivieren Sie die lokale Medienoptimierung auf dem Direct Routing-SBC.|
| Anrufeskalationen von 1 bis 1 Anruf zwischen internen Kunden und Anrufen mit mehreren Teilnehmern mit externen Kunden/Ressourcen führen zu abgebrochenen Anrufen. | Arbeiten Sie in Bearbeitung an einem Fix. Deaktivieren Sie alternativ die lokale Medienoptimierung auf dem Direct Routing-SBC.|
| Der Teams-Benutzer hält den Anruf in der Warteschleife. Musik wird am PSTN-Ende wiedergegeben, und die lokale Medienoptimierung funktioniert. Der Teams-Benutzer setzt den Anruf fort. Der Aufruf des PSTN wird fortgesetzt, die lokale Medienoptimierung funktioniert jedoch nicht, und der Anruf wird über den Zentralen SBC (Proxy) fortgesetzt. | Wenn ein Benutzer einen Anruf parkt, um Wartemusik (MoH) zu initiieren, wird er von 1:1 auf einen Anruf mit mehreren Teilnehmern vom Anrufcontroller eskaliert, um den Mediencontroller und Medienprozessor (als AVMCU-Mixer) aufzurufen, über den MoH einen Benutzer erreicht, der in den Haltebereich gesetzt wurde. Die Deeskalation auf einen 1:1-Anruf nach dem Fortsetzen des Anrufs erfolgt niemals gemäß Entwurf. Deaktivieren Sie die lokale Medienoptimierung auf dem Direct Routing-SBC.|
|Während ein Anruf für einige Sekunden eingerichtet wird, hört der Benutzer möglicherweise Stille.| Aufgrund der Komplexität der Architektur der lokalen Medienoptimierung kann dies in einigen Fällen auftreten.|
|VoIP-Apps (z. B. automatische Telefonzentrale, Anrufwarteschleife) funktionieren nicht.| LMO unterstützt keine VoIP-Apps, da sie sich in der Cloud befinden und externe Konnektivität erfordern. Vorerst keine Problemumgehung.|
