---
title: Optimierung lokaler Medien für direktes Routing
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
description: Optimierung lokaler Medien für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a85ed89eef42abca78cfdec16a9eee398ce118c
ms.sourcegitcommit: b431fc1a1802a8177109741b7c8e91bacb8c50c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2021
ms.locfileid: "50999817"
---
# <a name="local-media-optimization-for-direct-routing"></a>Optimierung lokaler Medien für direktes Routing

Public Switched Telephone Network (PSTN)-Stimme gilt als geschäftskritische Anwendung mit hohen Erwartungen an die Sprachqualität. Mit Direct Routing können Sie den Mediendatenverkehr steuern, um eine Vielzahl von Netzwerktopologien und lokalen Telefonieinstallationen für verschiedene Unternehmen auf der ganzen Welt zu unterstützen. 

Mit der Optimierung lokaler Medien für Direct Routing können Sie die Sprachqualität verwalten, indem Sie:

-   Steuern des Mediendatenverkehrs zwischen den Teams-Clients und dem Kunden Session Border Controller (SBCs).
-   Halten Sie Medien lokal innerhalb der Grenzen von Unternehmensnetzwerksubnetzen.
-   Zulassen von Medienstreams zwischen den Teams-Clients und den SBCs auch dann, wenn sich die SBCs hinter Unternehmensfirewalls mit privaten IPs befinden und für Microsoft nicht direkt sichtbar sind.

Die Optimierung lokaler Medien unterstützt zwei Szenarien:

- Zentralisierung aller lokalen Trunks über einen zentralen SBC, der mit dem Hauptstamm des Sitzungsinitiierungsprotokolls (SIP) verbunden ist und Telefoniedienste für alle lokalen Zweigstellen des Unternehmens bietet.

-   Erstellen einer virtuellen Netzwerktopologie von SBCs, in der die SBCs in den lokalen Zweigstellen mit einem zentralen Proxy-SBC verbunden sind, der über die externe IP-Adresse für Microsoft Phone System sichtbar ist und mit dem sie kommunizieren. In einer Topologie eines virtuellen Netzwerks kommunizieren nachgeordnete SBCs über interne IPs und sind für Telefonsystem nicht direkt sichtbar.

In diesem Artikel werden Featurefunktionen sowie Kundenszenarien und Lösungen beschrieben. Details zur Konfiguration finden Sie unter [Konfigurieren der Optimierung lokaler Medien.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Wenn Sie medien lokal innerhalb der Grenzen Ihres Intranets bleiben möchten, wird die Optimierung lokaler Medien empfohlen. Wenn Sie bereits über die Medienumgehung verfügen und nur die öffentlichen IP-Adressen Ihrer SBCs verwenden, ist es nicht zwingend erforderlich, zur Optimierung lokaler Medien zu wechseln. Sie können die Medienumgehung weiterhin verwenden. Weitere Informationen finden Sie unter [Planen der Medienumgehung](direct-routing-plan-media-bypass.md).


## <a name="supported-customer-scenarios"></a>Unterstützte Kundenszenarien

Gehen Sie für diese Diskussion davon aus, dass Contoso wie folgt mehrere Unternehmen auf der ganzen Welt betreibt. (Beachten Sie, dass europa- und APAC-Regionen nur als Beispiele verwendet werden. Ein Unternehmen hat möglicherweise mehrere unterschiedliche Regionen mit ähnlichen Anforderungen.)
 
- **In Europa** verfügt Contoso über Niederlassungen in ca. 30 Ländern. Jedes Büro verfügt über eine eigene PbX (Private Branch Exchange). 

  Contoso wurde eine Option angeboten, um die Trunks an einem Standort – Amsterdam – für alle 30 europäischen Niederlassungen zu zentralisieren. Contoso hat den SBC in Amsterdam bereitgestellt, genügend Bandbreite zum Ausführen von Anrufen über den zentralen Standort bereitgestellt, einen zentralen SIP-Trunk mit dem zentralen Standort verbunden und mit der Bereitstellung aller europäischen Standorte von Amsterdam aus begonnen. 

- **In der Region APAC verfügt** Contoso über mehrere Niederlassungen in verschiedenen Ländern. 

  In vielen Ländern verfügt das Unternehmen noch über TNX-Trunks (Time-Division Multiplexing) in lokalen Zweigstellen. Die Zentralisierung der TDM-Trunks ist in der Region APAC keine Option, daher ist ein Umstieg auf SIP nicht möglich. Angenommen, es gibt mehr als fünfzig Contoso-Zweigstellen in der region APAC mit Hunderten von Gateways (SBCs). In diesem Szenario ist es nicht möglich, alle Gateways mit der Direct Routing-Schnittstelle zu koppeln, da es an öffentlichen IP-Adressen und/oder lokalen Internetbrüchen fehlt. Darüber hinaus stellen einige Länder gesetzliche Anforderungen, die ohne lokale PSTN-Netzwerkkonnektivität nicht erfüllt werden können.

Basierend auf ihren geschäftlichen Anforderungen implementierte Contoso zwei Lösungen mit local media optimization for Direct Routing:

- **In Europa** werden alle Trunks zentralisiert und Medienflüsse zwischen dem zentralen SBC und den Benutzern basierend auf dem Benutzerstandort. 

  - Wenn ein Benutzer mit dem lokalen Subnetz eines Unternehmensnetzwerks verbunden ist (d. h., der Benutzer ist intern), fließen Medien zwischen der internen IP des zentralen SBC und dem Teams-Client des Benutzers. 
  
  - Wenn ein Benutzer außerhalb der Grenzen des Unternehmensnetzwerks liegt , z. B. wenn der Benutzer eine öffentliche drahtlose Internetverbindung verwendet, wird der Benutzer als extern betrachtet. In diesem Fall fließen die Medien zwischen der externen IP des zentralen SBC und dem Teams-Client.

- **In der Region APAC** wird ein zentraler Proxy-SBC mit Microsoft Direct Routing gekoppelt, der Medien zwischen der Direct Routing-Schnittstelle und den nachgeordneten SBCs in lokalen Zweigstellen leitet. 

  Die nachgeordneten SBCs in den lokalen Zweigstellen sind für Direct Routing in APAC nicht direkt sichtbar, werden jedoch mithilfe des cmdlets Set-CSOnlinePSTNGateway gekoppelt, um eine virtuelle Netzwerktopologie in Microsoft Phone System zu erstellen. Medien bleiben nach Möglichkeit immer lokal. Externe Benutzer verfügen über Medien, die zwischen dem Teams-Client und der öffentlichen IP des Proxy-SBC fließen.


## <a name="central-sbc-with-centralized-trunks"></a>Zentraler SBC mit zentralen Trunks

Um eine Lösung zu erstellen, bei der #A0 für alle lokalen Zweigstellen über einen zentralen SBC mit einem angeschlossenen zentralen SIP-Trunk bereitgestellt werden, paart der Contoso-Mandantenadministrator einen SBC (centralsbc.contoso.com) mit dem Dienst. verfügt der SBC über einen zentralen SIP-Trunk. 

- Wenn sich ein Benutzer im internen Netzwerk des Unternehmens befindet, stellt der SBC die interne IP des SBC für Medien zur Verf?4bung zur Verf??4bung zur Verf 2014-2014-2012-2014-2014-2014- 

- Wenn sich ein Benutzer außerhalb des Unternehmensnetzwerks befindet, stellt der SBC die externe (öffentliche) IP des SBC zur

Hinweis: Alle Werte in Beispielen, Tabellen oder Diagrammen werden nur zur Veranschaulichung dargestellt.

Tabelle 1. Beispiel für Netzwerkparameter für SBCs 

| Ort | SBC FQDN | Internes Subnetz | Externes NAT (vertrauenswürdige IP) | Externe SBC-IP-Adresse | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Deutschland | Nicht bereitgestellt | 192.168.6.0/24 | 172.16.76.74 | Nicht bereitgestellt |  Nicht bereitgestellt |
| Frankreich | Nicht bereitgestellt | 192.168.7.0/24 | 172.16.76.75 | Nicht bereitgestellt |  Nicht bereitgestellt ||||


### <a name="internal-user"></a>Interner Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn ein Benutzer in der Heimniederlassung oder Website des Benutzers mit dem Unternehmensnetzwerk verbunden ist. 

Während er lokal ist, wird der Benutzer der lokalen Zweigstelle in Deutschland zugewiesen. Der Benutzer führt einen Direkten Routing-Telefonanruf über Teams aus.

- Der Teams-Client des Benutzers kommuniziert mit Telefonsystem direkt über die REST-API, die während des Anrufs generierten Medien fließen jedoch an die interne IP-Adresse des zentralen SBC. 

- Der SBC leitet den Fluss an Telefonsystem und das verbundene PSTN-Netzwerk weiter. 

- Der zentrale SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar. 

Diagramm 1. Datenverkehrsfluss, wenn sich der Benutzer auf der "Home"-Website mit einem zentralen SBC und einem angeschlossenen zentralen SIP Trunk befindet

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-1.png "Datenverkehrsfluss, wenn sich der Benutzer auf der "Home"-Website mit zentralem SBC mit angeschlossener zentralem SIP Trunk befindet")


### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn ein Benutzer nicht lokal ist und nicht mit dem Unternehmensnetzwerk verbunden ist (d. h., das Gerät des Benutzers ist über ein mobiles Gerät oder öffentliches WLAN mit dem Internet verbunden). Der Benutzer führt einen Direkten Routing-Telefonanruf über Teams aus:

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Dem Telefonsystem, in diesem Fall fließen die während des Anrufs generierten Medien jedoch an die externe IP-Adresse des zentralen SBC. 

- Der SBC leitet den Fluss an Telefonsystem und das verbundene PSTN-Netzwerk weiter. 

- Der zentrale SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar. 

In diesem Fall ist das Verhalten ähnlich, unabhängig davon, ob der Benutzer in der Zweigstelle in Deutschland oder in einer anderen Zweigstelle lokal ist. Der Benutzer wird als extern betrachtet, da der Benutzer außerhalb der Grenzen des Unternehmensnetzwerks liegt.

Diagramm 2. Datenverkehrsfluss, wenn der Benutzer mit einem zentralen SBC und einem angeschlossenen zentralen SIP Trunk extern ist

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-2.png "Datenverkehrsfluss, wenn der Benutzer bei zentralisiertem SBC mit angeschlossener zentralem SIP Trunk extern ist")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy-SBC mit verbundenen downstream-SBCs

Um eine Lösung zu erstellen, bei der PSTN-Dienste in allen lokalen Zweigstellen in der Region APAC bereitgestellt werden, in der die Zentralisierung der TDM-Trunks keine Option ist, paart der Contoso-Administrator einen SBC (proxysbc.contoso.com), auch proxy SBC genannt, mit dem Direct Routing-Dienst. 

Anschließend fügt der Contoso-Administrator einige nachgeordnete SBCs hinzu, die angeben, dass sie über die Proxy-SBC-Proxysbc.contoso.com. Nachgeordnete SBCs verfügen nicht über öffentliche IPs, sie können jedoch Sprachrouten zugewiesen werden. Die folgende Tabelle zeigt Beispiel für Netzwerkparameter und -konfiguration.

Wenn sich ein Benutzer in der lokalen Zweigstelle befindet, in der sich der nachgeordnete SBC befindet, fließt der Mediendatenverkehr direkt zwischen dem Benutzer und dem lokalen nachgeordneten SBC. Wenn sich ein Benutzer außerhalb des Büros (in einem öffentlichen Internet) befindet, fließen die Medien vom Benutzer zur öffentlichen IP des Proxy-SBC, wodurch er an die relevanten nachgeordneten SBC(n) übertragen wird.

Tabelle 2. Beispiel für SBC-Netzwerkinformationen

| Ort | SBC FQDN | Internes Subnetz | Externes NAT (vertrauenswürdige IP) | Externe SBC-IP-Adresse  | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Keine |  192.168.1.5 |
| Indonesien  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Keine |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Interner Benutzer 

Das folgende Diagramm zeigt den Datenverkehrsfluss auf hoher Ebene für das Szenario, wenn sich ein Benutzer im Büro in der Region APAC befindet. Der Benutzer, der einer lokalen Zweigstelle in Vietnam zugewiesen ist und sich lokal befindet, führt einen Direkten Routing-Telefonanruf über Teams durch. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Telefonsystem, während während des Anrufs generierte Medien an die interne IP-Adresse des lokalen SBC fließen.

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das verbundene lokale PSTN-Netzwerk weiter.

-  Der Proxy-SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar und leitet den Fluss vom downstream-SBC (in diesem Fall vom lokalen SBC in Vietnam) an das Telefonsystem weiter. 

- Der nachgeordnete SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern innerhalb der virtuellen Netzwerktopologie zugeordnet, die vom Contoso-Administrator beim Einrichten der Optimierung lokaler Medien definiert wird.

Hinweis: Abhängig vom konfigurierten Modus zur Optimierung lokaler Medien kann das Verhalten für lokale und nicht lokale Benutzer unterschiedlich sein. 

Weitere Informationen zu möglichen Modi und dem relevanten Verhalten finden Sie unter Konfigurieren der Optimierung lokaler Medien.

Diagramm 3. Datenverkehrsfluss, wenn sich der Benutzer im Heimnetzwerk mit einem Proxy-SBC und mit angeschlossenen downstream-SBCs befindet 

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-3.png "Datenverkehrsfluss bei Proxy-SBC mit angeschlossenen downstream-SBCs, wenn sich der Benutzer im Heimnetzwerk befindet")

### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn sich ein Benutzer außerhalb der Unternehmensnetzwerkgrenzen befindet. Der Benutzer ist nicht lokal (liegt nicht innerhalb der Grenzen des Unternehmensnetzwerks). Der Benutzer führt einen Direkten Routinganruf über Teams zu einer Telefonnummer in Vietnam aus. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Telefonsystem, aber die während des Anrufs generierten Medien fließen zuerst an die externe IP-Adresse des Proxy-SBC in Singapur. 

- Basierend auf Konfigurations- und [](direct-routing-media-optimization-configure.md) Sprachrichtlinien (Details finden Sie unter Konfigurieren der Optimierung lokaler Medien), leitet der Proxy-SBC den Fluss an den nachgeordneten SBC in Vietnam um. 

- Der nachgeordnete SBC in Vietnam leitet den Fluss an das verbundene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar.

-  Der nachgeordnete SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern innerhalb der Topologie des virtuellen Netzwerks zugeordnet, die vom Contoso-Administrator beim Einrichten der Optimierung lokaler Medien definiert wird. Im Beispiel wird der Benutzer als extern betrachtet, da der Benutzer außerhalb der Grenzen des Unternehmensnetzwerks liegt. 

Diagramm 4. Datenverkehrsfluss, wenn der Benutzer mit einem Proxy-SBC und mit verbundenen downstream-SBCs extern ist

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-4.png "Datenverkehrsfluss bei Proxy-SBC mit angeschlossenen downstream-SBCs, wenn der Benutzer extern ist")

## <a name="local-media-optimization-modes"></a>Lokale Medienoptimierungsmodi

Die Optimierung lokaler Medien unterstützt zwei Modi:

- **Modus 1: Umgehen Sie immer**. Wenn der Benutzer intern ist, fließen die Medien in diesem Fall unabhängig vom tatsächlichen Standort des internen Benutzers durch die interne #A0 des lokalen downstream-SBC. beispielsweise in derselben Zweigstelle, in der sich der nachgeordnete SBC befindet, oder in einer anderen Zweigstelle.  

- **Modus 2: Nur für lokale Benutzer**. In diesem Modus fließen Medien nur dann direkt an die interne IP-Adresse des lokalen downstream SBC, wenn sie vom internen Benutzer generiert werden, der sich in derselben Zweigstelle wie der nachgeordnete SBC befindet. 

Um zwischen lokalen Medienoptimierungsmodi zu unterscheiden, muss der Mandantenadministrator den Parameter -BypassMode entweder auf "Always" oder "OnlyForLocalUsers" für jeden SBC festlegen, indem er das cmdlet Set-CSonlinePSTNGateway verwendet. Weitere Informationen finden Sie unter [Konfigurieren der Optimierung lokaler Medien.](direct-routing-media-optimization-configure.md)  

 > [!NOTE]
  > Wenn Benutzer intern sind, ist eine Medienkonnektivität zwischen dem Benutzer und dem SBC über die interne IP-Adresse **erforderlich.** In diesem Fall gibt es keinen Fallback für Relays für öffentliche Verkehrsmittel für Medien, da der SBC eine interne IP für Medienkonnektivität bereitstellen wird. 

### <a name="mode-1-always-bypass"></a>Modus 1: Immer umgehen

Wenn Sie über eine gute Verbindung zwischen Zweigstellen verfügen, wird der empfohlene Modus immer umgehungsweise verwendet.
 
Angenommen, ein Unternehmen verfügt über einen zentralen SIP-Trunk in Amsterdam, der 30 Länder bedient und eine gute Verbindung zwischen allen 30 Websites und lokalen Benutzern bietet. Es gibt auch eine Zweigstelle in Deutschland, in der ein lokaler SBC bereitgestellt wird.

Der SBC in Deutschland kann im Modus "Immer umgehen" konfiguriert werden. Benutzer stellen unabhängig von ihrem Standort eine direkte Verbindung mit dem SBC über die interne #A0 des SBC (z. B. von Frankreich nach Deutschland, siehe nachstehendes Diagramm) dar.

Im Folgenden werden zwei Szenarien beschrieben:

- Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der in der Online-Voiceroutingrichtlinie definierte SBC.

- Szenario 2. Der Benutzer und die Gateways befinden sich auf verschiedenen Websites.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der in der Online-Voiceroutingrichtlinie definierte SBC.

Der SBC in Amsterdam ist als Proxy-SBC für einen lokalen nachgeordneten SBC in Deutschland konfiguriert. Der Benutzer befindet sich in Deutschland im selben Subnetz wie das Unternehmensnetzwerk des lokalen SBC. Beide SBCs (Proxy und Downstream) sind für den Modus "Immer umgehen" konfiguriert. Die Richtlinien für das Online-Voicerouting geben an, dass bei Anrufen innerhalb Von Deutschland (mit Vorwahl +49) an den lokalen SBC in Deutschland geroutet werden soll. Alle anderen Anrufe – und für den Fall, dass die SBC in Deutschland fehlschlägt, Anrufe in Deutschland – sollten an den Proxy-SBC in Amsterdam weitergeroutet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 3. Beispielkonfiguration für Szenario 1

| Physische Position des Benutzers | Benutzer anruft eine Nummer | Online-Voiceroutingrichtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Deutschland | +49 1 437 2800 | Priorität 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Priorität 2: .* – proxysbc.contoso.com| DEsbc.contoso.com – Immer umgehen <br>proxysbc.contoso.com – Immer umgehen | Teams User <-> DEsbc.contoso.com |

Das folgende Diagramm zeigt den Datenverkehr auf hoher Ebene für den internen Benutzer in Deutschland, der über Teams einen Direkten Routing-Telefonanruf an die Nummer in Deutschland führt. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Dem Telefonsystem. 

- Die während des Anrufs generierten Medien fließen an die interne IP-Adresse des lokalen SBC. 

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Amsterdam und an das verbundene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar und leitet den Fluss vom downstream-SBC (in diesem Fall dem lokalen SBC in Deutschland) an Das Telefonsystem weiter. 

- Der nachgeordnete SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern innerhalb der virtuellen Netzwerktopologie zugeordnet, die vom Contoso-Administrator beim Einrichten der Optimierung lokaler Medien definiert wird.


Diagramm 5.  Datenverkehrsfluss im Modus "Immer umgehen", und der Benutzer befindet sich auf der "Home"-Website.

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-5.png "Datenverkehrsfluss mit dem Modus "Immer umgehen", und der Benutzer befindet sich auf der "Home"-Website.")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2: Benutzer und Gateways befinden sich auf verschiedenen Websites

Der SBC in Amsterdam ist als Proxy-SBC für einen lokalen nachgeordneten SBC in Deutschland konfiguriert. Beide SBCs (Proxy und Downstream) sind für den Modus "Immer umgehen" konfiguriert. Der interne Benutzer in Frankreich, der sich in der lokalen Zweigstelle befindet, führt einen Direkten Routing-Anruf nach Deutschland durch. Die Richtlinien für das Online-Voicerouting legen fest, dass Anrufe nach Deutschland (mit Vorwahl +49) an den lokalen SBC in Deutschland weiterleitiert werden sollen. Alle anderen Anrufe – und, falls der SBC in Deutschland fehlschlägt, alle Anrufe in Deutschland – sollten an den Proxy-SBC in Amsterdam weitergeroutet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 4. Beispielkonfiguration für Szenario 2

| Physische Position des Benutzers | Benutzer anruft eine Nummer | Online-Voiceroutingrichtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Frankreich | +49 1 437 2800 | Priorität 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Priorität 2: .* – proxysbc.contoso.com |  DEsbc.contoso.com – Immer proxysbc.contoso.com umgehen – Immer umgehen | Teams User <– > DEsbc.contoso.com  |

Die folgende Abbildung zeigt den Datenverkehr auf hoher Ebene, wenn der interne deutsche Benutzer, der sich in Frankreich befindet, einen Direkten Routing-Telefonanruf über Teams an die Nummer in Deutschland führt. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Dem Telefonsystem.

- Die während des Anrufs generierten Medien fließen direkt an die interne IP-Adresse des SBC in Deutschland. 

- Der SBC in Deutschland leitet den Fluss an den Proxy-SBC in Amsterdam und an das verbundene lokale PSTN-Netzwerk weiter. 

Diagramm 6.  Datenverkehrsfluss im Modus "Immer umgehen", und der Benutzer befindet sich nicht auf der "Home"-Website, sondern im internen Netzwerk.

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-6.png "Datenverkehrsfluss im Modus "Immer umgehen", und der Benutzer befindet sich nicht auf der "Home"-Website, sondern im internen Netzwerk.")

### <a name="mode-2-only-for-local-users"></a>Modus 2: Nur für lokale Benutzer

Wenn es schlechte Verbindungen zwischen lokalen Zweigstellen, aber gute Verbindungen zwischen jeder lokalen Zweigstelle und einer regionalen Niederlassung gibt, wird der empfohlene Modus "Nur für lokale Benutzer" verwendet.

Gehen Sie beispielsweise in der Region APAC davon aus, dass Contoso über mehrere Niederlassungen in verschiedenen Ländern verfügt. In vielen Ländern ist ein Umstieg auf SIP nicht möglich, da das Unternehmen in vielen lokalen Zweigstellen weiterhin über T TDM-Trunks verfügt. Die Zentralisierung der TDM-Trunks ist in der Region APAC keine Option. Darüber hinaus gibt es mehr als fünfzig Contoso-Zweigstellen in der gesamten Region APAC mit Hunderten von Gateways (SBCs). 

Um eine Lösung zu erstellen, bei der PSTN-Dienste in allen lokalen Zweigstellen in der Region APAC bereitgestellt werden, in der die Zentralisierung der TDM-Trunks keine Option ist, paart der Contoso-Administrator einen regionalen SBC in Singapur als Proxy-SBC mit dem Direct Routing-Dienst. Die direkte Verbindung zwischen den lokalen Zweigstellen ist nicht gut, aber es gibt eine gute Verbindung zwischen jeder lokalen Zweigstelle und dem regionalen SBC in Singapur. Für den regionalen SBC wählt der Administrator den Modus "Immer umgehen", und für die lokalen nachgeordneten SBCs wählt der Administrator den Modus "Nur für lokale Benutzer".

Im Folgenden werden zwei Szenarien beschrieben:

- Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der in der Online-Voiceroutingrichtlinie definierte SBC.

- Szenario 2. Benutzer und Gateways befinden sich auf verschiedenen Websites

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der in der Online-Voiceroutingrichtlinie definierte SBC.

Angenommen, der SBC in Singapur ist als Proxy-SBC für die lokalen nachgeordneten SBCs in Vietnam und Indonesien konfiguriert. Der Benutzer befindet sich in Vietnam an demselben Ort wie der lokale SBC. Die Richtlinien für das Online-Voicerouting legen fest, dass Anrufe in Vietnam (mit Vorwahl +84) an den lokalen SBC in Vietnam weiterleitet werden sollen. Alle anderen Anrufe – und, wenn der SBC in Vietnam fehlschlägt, Anrufe in Vietnam – sollten an den Proxy-SBC in Singapur weitergeroutet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 5. Beispielkonfiguration für den Modus "Nur für lokale Benutzer" Szenario 1

| Physische Position des Benutzers | Benutzer anruft eine Nummer | Online-Voiceroutingrichtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Priorität 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Priorität 2: .* – proxysbc.contoso.com | VNsbc.contoso.com – Nur für lokale Benutzer <br> proxysbc.contoso.com – Immer umgehen | Teams User <-> VNsbc.contoso.com |

In der folgenden Abbildung führt ein Benutzer, der der lokalen Zweigstelle in Vietnam zugewiesen ist, lokal einen Direkten Routing-Telefonanruf über Teams durch. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Dem Telefonsystem. 

- Während des Anrufs generierte Medien fließen an die interne IP-Adresse des lokalen SBC. 

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das verbundene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar und leitet den Fluss vom downstream-SBC (in diesem Fall vom lokalen SBC in Vietnam) an das Telefonsystem weiter. 

- Der nachgeordnete SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern innerhalb der Topologie des virtuellen Netzwerks zugeordnet.

Diagramm 7. Datenverkehrsfluss im Modus "Nur für lokale Benutzer", und der Benutzer befindet sich auf der "Home"-Website.

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-7.png "Datenverkehrsfluss mit dem Modus "Nur für lokale Benutzer", und der Benutzer befindet sich auf der "Home"-Website.")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2. Benutzer und Gateways befinden sich auf verschiedenen Websites

Angenommen, der SBC in Singapur ist als Proxy-SBC für die lokalen nachgeordneten SBCs in Vietnam und Indonesien konfiguriert. Der interne Benutzer in Indonesien, der sich in der lokalen Zweigstelle befindet, führt einen Direkten Routing-Anruf nach Vietnam durch. Die Online-Voice-Routingrichtlinien legen fest, dass Anrufe nach Vietnam (mit Vorwahl +84) an den lokalen SBC in Vietnam weiterleitet werden sollen. Alle anderen Anrufe – und für den Fall, dass der SBC in Vietnam fehlschlägt, Anrufe nach Vietnam – sollten an den Proxy-SBC in Singapur weitergeroutet werden. Der Proxy-SBC in Singapur ist auf den Modus "Immer umgehen" festgelegt, und der lokale SBC in Vietnam ist auf "Nur für lokale Benutzer" festgelegt. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 6. Benutzerkonfiguration

| Physische Position des Benutzers | Benutzer anruft eine Nummer | Online-Voiceroutingrichtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesien | +84 4 3926 3000 | Priorität 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Priorität 2: .* – proxysbc.contoso.com |VNsbc.contoso.com – Nur für lokale Benutzer <br> proxysbc.contoso.com – Immer umgehen | Teams User <-> proxysbc.contoso.com <-> VNsbc.contoso.com |


In der folgenden Abbildung führt der interne Benutzer, der lokal in der indonesischen Niederlassung ist, einen Direkten Routinganruf über Teams zu einer Nummer in Vietnam durch. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Dem Telefonsystem.

- Medien, die während des Anrufs generiert werden, fließen zuerst an die interne IP-Adresse des Proxys. 

- Der Proxy-SBC in Singapur leitet den Fluss an die interne IP-Adresse des nachgeordneten SBC in Vietnam und an Telefonsystem weiter. 

- Der downstream SBC in Vietnam leitet den Fluss an das verbundene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist für Telefonsystem nur über die externe IP-Adresse sichtbar.

- Die nachgeordneten SBCs in lokalen Zweigstellen sind für Telefonsystem nicht direkt sichtbar, sondern innerhalb der Topologie des virtuellen Netzwerks zugeordnet.

Diagramm 8.  Datenverkehrsfluss im Modus "Nur für lokale Benutzer", und der Benutzer befindet sich nicht auf der Homepage, sondern im internen Netzwerk.

![Diagramm zur Optimierung des Datenverkehrsflusses (Local Media Optimization)](media/direct-routing-media-op-8.png "Der Datenverkehrsfluss im Modus "Nur für lokale Benutzer" befindet sich nicht auf der "Homepage", sondern im internen Netzwerk.")

## <a name="known-issues"></a>Bekannte Probleme

Im Folgenden finden Sie eine Liste der bekannten Probleme, die derzeit in der Optimierung lokaler Medien auftreten. Microsoft arbeitet an der Lösung dieser Probleme.

| Problem | Problemumgehung |
| :--- | :--- |
| Der Teams-Client wird nicht als **intern identifiziert,** wenn die öffentliche IP des Teams-Clients mit der vertrauenswürdigen IP-Liste des Kunden entspricht. | Die Optimierung lokaler Medien setzt voraus, dass das Teams-Clientsubnetz einem mandantenkonfigurierten [Netzwerksubnetz entspricht.](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| Anrufeskalation führt zu verworfenen Anrufen, wenn der Teams-Client als intern identifiziert wird.| Deaktivieren Sie die Optimierung lokaler Medien auf dem Direct Routing SBC.|
| Anrufeskalation von 1 bis 1 Anruf zwischen internen Kunden zum Mehrteileranruf mit externem Kunden/Ressource führt zu verworfenen Anrufen | Es wird an einem Fix in Bearbeitung ausgeführt. Alternativ können Sie die Optimierung lokaler Medien auf dem Direct Routing SBC deaktivieren.|


