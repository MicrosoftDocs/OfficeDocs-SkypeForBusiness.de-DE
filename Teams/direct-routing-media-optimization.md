---
title: Direct Routing Local Media Optimization
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
ms.openlocfilehash: aab38cb7f844764faac0e9c19bc03110adac9c10
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469667"
---
# <a name="local-media-optimization-for-direct-routing"></a>Optimierung lokaler Medien für direktes Routing

PstN-Sprache (Public Switched Telephone Network) wird als unternehmenskritische Anwendung mit hohen Erwartungen an die Sprachqualität betrachtet. Mit Direct Routing können Sie die Mediendatenverkehrsströme steuern, um eine Vielzahl von Netzwerktopologien und lokalen Telefonie-Setups für verschiedene Unternehmen auf der ganzen Welt zu unterstützen. 

Die Optimierung lokaler Medien für das direkte Routing ermöglicht ihnen die Verwaltung der Sprachqualität mit den von Ihnen verwendeten Ressourcen:

-   Steuern sie, wie der Medienverkehr zwischen den Teams und den Kunden Session Border Controller (SBCs) fließt.
-   Halten Sie Medien lokal innerhalb der Grenzen von Unternehmensnetzwerk-Subnetzen.
-   Zulassen von Medienstreams zwischen den Teams-Clients und den SBCs auch dann, wenn sich die SBCs hinter Unternehmensfirewalls mit privaten IPs befinden und für Microsoft nicht direkt sichtbar sind.

Die Optimierung lokaler Medien unterstützt zwei Szenarien:

- Zentralisierung aller lokalen Trunks über einen zentralen SBC, der mit dem SIP-Haupttelefoniedienst (Session Initiation Protocol) verbunden ist, der Telefoniedienste mit allen lokalen Zweigstellen des Unternehmens bietet.

-   Erstellen einer virtuellen Netzwerktopologie von SBCs, wobei die SBCs in den lokalen Zweigstellen mit einem zentralen Proxy-SBC verbunden sind, der für Microsoft-Telefon System über seine externe IP-Adresse sichtbar ist und mit diesem kommuniziert. In einer virtuellen Netzwerktopologie kommunizieren downstream-SBCs über interne IPs und sind für Benutzer nicht direkt Telefonsystem.

In diesem Artikel werden Featurefunktionen sowie Kundenszenarien und -lösungen beschrieben. Details zur Konfiguration finden Sie unter [Konfigurieren der Optimierung lokaler Medien.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Wenn Sie Medien innerhalb der Grenzen Ihres Intranets lokal halten möchten, wird die Optimierung lokaler Medien empfohlen. Wenn Sie bereits über die Medienumgehung verfügen und nur die öffentlichen IP-Adressen Ihrer SBCs verwenden, müssen Sie nicht zur Optimierung lokaler Medien wechseln. Sie können die Medienumgehung weiterhin verwenden. Weitere Informationen finden Sie unter [Planen der Medienumgehung.](direct-routing-plan-media-bypass.md)


## <a name="supported-customer-scenarios"></a>Unterstützte Kundenszenarien

Gehen Sie für diese Diskussion davon aus, dass Contoso wie folgt mehrere Unternehmen auf der ganzen Welt betreibt. (Beachten Sie, dass nur die Regionen Europa und APAC als Beispiele verwendet werden. Ein Unternehmen hat möglicherweise mehrere unterschiedliche Regionen mit ähnlichen Anforderungen.)
 
- **In Europa** verfügt Contoso über Niederlassungen in ca. 30 Ländern. Jede Niederlassung verfügt über eine eigene private Exchange (PBX). 

  Contoso bot die Möglichkeit, die Trunks an einem Ort – Amsterdam – für alle 30 europäischen Niederlassungen zu zentralisieren. Contoso hat den SBC in Amsterdam bereitgestellt, genügend Bandbreite zum Ausführen von Anrufen über den zentralen Standort bereitgestellt, einen zentralen SIP-Trunk mit dem zentralen Standort verbunden und damit begonnen, alle europäischen Standorte von Amsterdam aus zu bedient. 

- **In der Region APAC verfügt** Contoso über mehrere Niederlassungen in verschiedenen Ländern. 

  In vielen Ländern verfügt das Unternehmen weiterhin über TDM-Trunks (Time-Division Multiplexing) in lokalen Zweigstellen. Die Zentralisierung der TDM-Trunks ist in der Region APAC keine Option, daher ist ein Umstieg auf SIP nicht möglich. Angenommen, es gibt mehr als fünfzig Contoso-Zweigstellen in der Region APAC mit Hunderten von Gateways (SBCs). In diesem Szenario ist es nicht möglich, alle Gateways an die Direct-Routingschnittstelle zu koppeln, da es keine öffentlichen IP-Adressen und/oder lokalen Internet-Unterbrechungen gibt. Darüber hinaus stellen einige Länder behördliche Anforderungen, die ohne eine lokale PSTN-Netzwerkkonnektivität nicht erfüllt werden können.

Basierend auf den Geschäftsanforderungen hat Contoso zwei Lösungen mit local media optimization for Direct Routing implementiert:

- **In Europa** sind alle Trunks zentralisiert, und die Medienflüsse zwischen dem zentralen SBC und den Benutzern werden basierend auf der Benutzerposition verwendet. 

  - Wenn ein Benutzer mit dem lokalen Subnetz eines Unternehmensnetzwerks verbunden ist (d. h., der Benutzer ist intern), fließen die Medienströme zwischen der internen IP des zentralen SBC und dem Teams-Client des Benutzers. 
  
  - Wenn sich ein Benutzer außerhalb des Unternehmensnetzwerks befindet (z. B. wenn er eine öffentliche drahtlose Internetverbindung verwendet), wird der Benutzer als extern betrachtet. In diesem Fall fließen die Medien zwischen der externen IP des zentralen SBC und dem Teams Client.

- **In der Region APAC** ist ein zentraler Proxy-SBC mit Microsoft Direct Routing gekoppelt, wodurch Medien zwischen der Direct Routing-Schnittstelle und den downstream-SBCs in lokalen Zweigstellen gekoppelt werden. 

  Die downstream-SBCs in den lokalen Zweigstellen sind für Direct-Routing in APAC nicht direkt sichtbar, werden aber mit dem Set-CSOnlinePSTNGateway-Cmdlet zum Erstellen einer virtuellen Netzwerktopologie in Microsoft-Telefon System gekoppelt. Medien bleiben nach Möglichkeit immer lokal. Externe Benutzer verfügen über Medien, die zwischen dem Teams und der öffentlichen IP des Proxy-SBC fließen.


## <a name="central-sbc-with-centralized-trunks"></a>Zentraler SBC mit zentralisierten Trunks

Um eine Lösung zu erstellen, bei der PSTN-Dienste für alle lokalen Zweigstellen über einen einzigen zentralen SBC mit einem verbundenen zentralen SIP-Trunk bereitgestellt werden, paart der Contoso-Mandantenadministrator einen SBC (centralsbc.contoso.com) mit dem Dienst. SBC verfügt über einen zentralen SIP-Trunk, der mit diesem verbunden ist. 

- Wenn sich ein Benutzer im internen Netzwerk des Unternehmens befindet, stellt der SBC die interne IP des SBC für Medien zur 

- Wenn sich ein Benutzer außerhalb des Unternehmensnetzwerks befindet, stellt der SBC die externe (öffentliche) IP-Adresse des SBC zur Wird-öffentlichen IP-Adresse zur.

Hinweis: Alle Werte in Beispielen, Tabellen oder Diagrammen werden nur zur Veranschaulichung dargestellt.

Tabelle 1. Beispiel für Netzwerkparameter für SBCs 

| Ort | SBC-FQDN | Internes Subnetz | Externes NAT (Trusted IP, vertrauenswürdige IP) | Externe SBC-IP-Adresse | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Deutschland | Nicht bereitgestellt | 192.168.6.0/24 | 172.16.76.74 | Nicht bereitgestellt |  Nicht bereitgestellt |
| Frankreich | Nicht bereitgestellt | 192.168.7.0/24 | 172.16.76.75 | Nicht bereitgestellt |  Nicht bereitgestellt ||||


### <a name="internal-user"></a>Interner Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn ein Benutzer in der Home Branch-Niederlassung oder am Standort des Benutzers mit dem Unternehmensnetzwerk verbunden ist. 

Während er lokal ist, wird dem Benutzer die lokale Zweigstelle in Deutschland zugewiesen. Der Benutzer führt einen direkten Routing-Telefonanruf über Teams.

- Der Teams-Client des Benutzers kommuniziert mit Telefonsystem direkt über die REST-API, die während des Aufrufs generierten Medien fließen jedoch an die interne IP-Adresse des zentralen SBC. 

- Der SBC leitet den Fluss an das Telefonsystem und das verbundene PSTN-Netzwerk um. 

- Der zentrale SBC ist nur für Telefonsystem externe IP-Adresse sichtbar. 

Diagramm 1. Datenverkehrsfluss, wenn sich der Benutzer auf der "Homepage" mit einem zentralen SBC und einem verbundenen zentralen SIP Trunk befindet

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-1.png "Datenverkehrsfluss, wenn sich der Benutzer auf der &quot;Homepage&quot; mit zentralem SBC mit verbundenem zentralisiertem SIP Trunk befindet")


### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn ein Benutzer nicht lokal ist und nicht mit dem Unternehmensnetzwerk verbunden ist (d. h., das Gerät des Benutzers ist über ein mobiles Gerät oder ein öffentliches WLAN mit dem Internet verbunden). Der Benutzer führt einen Direkten Routing-Telefonanruf über Teams:

- Der Teams-Client des Benutzers kommuniziert mit Telefonsystem direkt über die REST-API. In diesem Fall fließen die während des Aufrufs generierten Medien jedoch an die externe IP-Adresse des zentralen SBC. 

- Der SBC leitet den Fluss an das Telefonsystem und das verbundene PSTN-Netzwerk um. 

- Der zentrale SBC ist nur für Telefonsystem externe IP-Adresse sichtbar. 

In diesem Fall ist das Verhalten ähnlich, unabhängig davon, ob der Benutzer in der Zweigstelle in Deutschland oder einer anderen Zweigstelle lokal ist. Der Benutzer wird als extern betrachtet, da er sich außerhalb der Grenzen des Unternehmensnetzwerks befindet.

Diagramm 2. Datenverkehrsfluss, wenn der Benutzer mit einem zentralen SBC und einem verbundenen zentralen SIP Trunk extern ist

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-2.png "Datenverkehrsfluss bei externem Benutzer bei zentralisiertem SBC mit verbundenem zentralem SIP Trunk")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy SBC mit verbundenen downstream-SBCs

Um eine Lösung zu erstellen, bei der PSTN-Dienste in allen lokalen Zweigstellen in der Region APAC bereitgestellt werden, in denen die Zentralisierung der TDM-Trunks keine Option ist, paart der Contoso-Administrator einen SBC (proxysbc.contoso.com), der auch Proxy-SBC genannt wird, an den Direct-Routingdienst. 

Anschließend fügt der Contoso-Administrator einige downstream-SBCs hinzu, die angeben, dass sie über die Proxy-SBC-Proxysbc.contoso.com. Downstream-SBCs verfügen nicht über öffentliche IPs, sie können jedoch Sprachrouten zugewiesen werden. In der folgenden Tabelle sind Beispiel-Netzwerkparameter und -konfiguration aufgeführt.

Wenn sich ein Benutzer in der lokalen Zweigniederlassung befindet, in der sich der Downstream-SBC befindet, fließt der Mediendatenverkehr direkt zwischen dem Benutzer und dem lokalen Downstream-SBC. Wenn sich ein Benutzer außerhalb des Büros befindet (in einem öffentlichen Internet), fließen die Medien von dem Benutzer zur öffentlichen IP des Proxy-SBC, wodurch er an die relevanten downstream-SBC(s) proxys it wird.

Tabelle 2. SBC-Beispielnetzwerkinformationen

| Ort | SBC-FQDN | Internes Subnetz | Externes NAT (Trusted IP, vertrauenswürdige IP) | Externe SBC-IP-Adresse  | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Keine |  192.168.1.5 |
| Indonesien  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Keine |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Interner Benutzer 

Das folgende Diagramm zeigt den Datenverkehr auf hoher Ebene für das Szenario, in dem sich ein Benutzer im Büro in der Region APAC befindet. Der Benutzer, der einer lokalen Zweigniederlassung in Vietnam zugewiesen ist und lokal ist, führt einen direkten Routing-Telefonanruf über Teams. 

- Der Teams-Client des Benutzers kommuniziert direkt über die REST-API mit Telefonsystem, während während des Aufrufs generierte Medien an die interne IP-Adresse des lokalen SBC fließen.

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das verbundene lokale PSTN-Netzwerk um.

-  Der Proxy-SBC ist nur Telefonsystem externen IP-Adresse sichtbar und leitet den Fluss vom downstream-SBC (in diesem Fall der lokale SBC in Vietnam) an Telefonsystem. 

- Der downstream-SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern innerhalb der virtuellen Netzwerktopologie zugeordnet, die vom Contoso-Administrator beim Einrichten der Optimierung für lokale Medien definiert wird.

Hinweis: Je nach konfigurierter Optimierungsmodus für lokale Medien kann das Verhalten für lokale Benutzer und nicht lokale Benutzer unterschiedlich sein. 

Weitere Informationen zu möglichen Modi und relevantem Verhalten finden Sie unter Konfigurieren der Optimierung lokaler Medien.

Diagramm 3. Datenverkehrsfluss, wenn sich der Benutzer im "Heimnetzwerk" mit einem Proxy-SBC und verbundenen downstream-SBCs befindet 

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-3.png "Datenverkehrsfluss bei Proxy-SBC mit verbundenen downstream-SBCs, wenn sich der Benutzer im Heimnetzwerk befindet")

### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenverkehrsfluss, wenn sich ein Benutzer außerhalb der Grenzen des Unternehmensnetzwerks befindet. Der Benutzer ist nicht lokal (befindet sich nicht innerhalb der Grenzen des Unternehmensnetzwerks). Der Benutzer führt einen direkten Routing-Telefonanruf Teams eine Telefonnummer in Vietnam durch. 

- Der Teams-Client des Benutzers kommuniziert mit Telefonsystem direkt über die REST-API, aber die während des Aufrufs generierten Medien fließen zuerst an die externe IP-Adresse des Proxy-SBC in Singapur. 

- Basierend auf Konfigurations- und Sprachrichtlinien (Details finden Sie unter Konfigurieren der lokalen [Medienoptimierung),](direct-routing-media-optimization-configure.md) leitet der Proxy-SBC den Fluss an den Downstream-SBC in Vietnam weiter. 

- Der Downstream-SBC in Vietnam leitet den Fluss an das verbundene lokale PSTN-Netzwerk um. 

- Der Proxy-SBC ist nur für Telefonsystem externe IP-Adresse sichtbar.

-  Der downstream-SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern wird innerhalb der virtuellen Netzwerktopologie zugeordnet, die vom Contoso-Administrator beim Einrichten der Optimierung für lokale Medien definiert wird. In diesem Beispiel wird der Benutzer als extern betrachtet, da er sich außerhalb der Grenzen des Unternehmensnetzwerks befindet. 

Diagramm 4. Datenverkehrsfluss, wenn der Benutzer mit einem Proxy-SBC und verbundenen downstream-SBCs extern ist

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-4.png "Datenverkehrsfluss bei Proxy-SBC mit verbundenen downstream-SBCs, wenn der Benutzer extern ist")

## <a name="local-media-optimization-modes"></a>Modi zur Optimierung lokaler Medien

Die Optimierung lokaler Medien unterstützt zwei Modi:

- **Modus 1: Umgehen Sie immer**. In diesem Fall fließt das Medium, wenn es sich um einen internen Benutzer handelt, durch die interne IP-Adresse des lokalen Downstream-SBC, unabhängig vom tatsächlichen Standort des internen Benutzers. Beispielsweise in derselben Zweigstelle, in der sich der downstream-SBC befindet, oder in einer anderen Zweigstelle.  

- **Modus 2: Nur für lokale Benutzer.** In diesem Modus werden Medien nur dann direkt zur internen IP-Adresse des lokalen Downstream-SBC fließen, wenn sie vom internen Benutzer generiert werden, der sich in derselben Zweigstelle wie der Downstream-SBC befindet. 

Um zwischen lokalen Medienoptimierungsmodi zu unterscheiden, muss der Mandantenadministrator den Parameter "-BypassMode" mithilfe des Set-CSonlinePSTNGateway-Cmdlets entweder auf "Always" oder "OnlyForLocalUsers" festlegen. Weitere Informationen finden Sie unter [Konfigurieren der Optimierung lokaler Medien.](direct-routing-media-optimization-configure.md)  

 > [!NOTE]
  > Bei internen Benutzern ist eine Medienkonnektivität zwischen dem Benutzer und dem SBC über die interne IP-Adresse **erforderlich.** In diesem Fall gibt es keinen Fallback für Relays für den öffentlichen Transport für Medien, da der SBC eine interne IP für Die Medienkonnektivität stellt. 

### <a name="mode-1-always-bypass"></a>Modus 1: Immer umgehen

Wenn Sie über eine gute Verbindung zwischen Zweigstellen verfügen, ist der empfohlene Modus Immer Umgehen.
 
Angenommen, ein Unternehmen verfügt über einen zentralen SIP-Trunk in Amsterdam, der 30 Länder und eine gute Verbindung zwischen allen 30 Standorten und lokalen Benutzern bietet. Es gibt auch einen Zweig in Deutschland, in dem ein lokaler SBC bereitgestellt wird.

Der SBC in Deutschland kann im Modus "Always bypass" konfiguriert werden. Benutzer stellen unabhängig von ihrem Standort eine direkte Verbindung mit dem SBC über die interne IP-Adresse des SBC (z. B. von Frankreich nach Deutschland; siehe die nachstehende Abbildung) zur Verfügung.

Im Folgenden werden zwei Szenarien beschrieben:

- Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der SBC, der in der Online-Voiceroutingrichtlinie definiert ist.

- Szenario 2. Der Benutzer und die Gateways befinden sich auf unterschiedlichen Websites.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der SBC, der in der Online-Voiceroutingrichtlinie definiert ist.

Der SBC in Amsterdam ist als Proxy-SBC für einen lokalen Downstream-SBC in Deutschland konfiguriert. Der Benutzer befindet sich in Deutschland im selben Subnetz wie das Unternehmensnetzwerk des lokalen SBC. Sowohl SBCs (Proxy als auch Downstream) sind für den Always Bypass-Modus konfiguriert. Die Richtlinien für das Online-Voicerouting legen fest, dass Bei Anrufen innerhalb Von Deutschland (mit der Ortswahl +49) diese an den lokalen SBC in Deutschland geroutet werden sollen. Alle anderen Aufrufe – und für den Fall, dass SBC in Deutschland fehlschlägt, -Aufrufe in Deutschland sollten an den Proxy-SBC in Amsterdam geroutet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 3. Beispielkonfiguration für Szenario 1

| Physischer Standort des Benutzers | Der Benutzer anruft eine Nummer. | Online Voice Routing Policy | Für SBC konfigurierter Modus | Medien Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Deutschland | +49 1 437 2800 | Priorität 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Priorität 2: .* - proxysbc.contoso.com| DEsbc.contoso.com – Immer umgehen <br>proxysbc.contoso.com – Immer umgehen | Teams Benutzer <-> DEsbc.contoso.com |

Das folgende Diagramm zeigt den Datenverkehrsfluss auf hoher Ebene für den internen Benutzer in Deutschland, der einen Direkten Routing-Telefonanruf über Teams zu der Nummer in Deutschland führt. 

- Der Teams des Benutzers kommuniziert mit dem Telefonsystem direkt über die REST-API. 

- Die während des Anrufs generierten Medien fließen an die interne IP-Adresse des lokalen SBC. 

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Amsterdam und an das verbundene lokale PSTN-Netzwerk um. 

- Der Proxy-SBC ist nur Telefonsystem der externen IP-Adresse sichtbar und leitet den Fluss vom downstream-SBC (in diesem Fall dem lokalen SBC in Deutschland) an Telefonsystem. 

- Der downstream-SBC in der lokalen Zweigstelle ist für Telefonsystem nicht direkt sichtbar, sondern innerhalb der virtuellen Netzwerktopologie zugeordnet, die vom Contoso-Administrator beim Einrichten der Optimierung für lokale Medien definiert wird.


Diagramm 5.  Datenverkehrsfluss mit "Always Bypass"-Modus, und der Benutzer befindet sich auf der "Startseite"-Website

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-5.png "Datenverkehrsfluss mit &quot;Always Bypass&quot;-Modus und Benutzer befinden sich auf der &quot;Startseite&quot;-Website")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2: Benutzer und Gateways befinden sich auf unterschiedlichen Websites

Der SBC in Amsterdam ist als Proxy-SBC für einen lokalen Downstream-SBC in Deutschland konfiguriert. Sowohl SBCs (Proxy als auch Downstream) sind für den Always Bypass-Modus konfiguriert. Der interne Benutzer in Frankreich, der sich in der lokalen Zweigstelle befindet, führt einen Direct Routing-Anruf nach Deutschland durch. Die Richtlinien für das Online-Voicerouting legen fest, dass Anrufe nach Deutschland (mit der Vorwahl +49) an den lokalen SBC in Deutschland geroutet werden sollen. Alle anderen Aufrufe – und für den Fall, dass SBC in Deutschland fehlschlägt, alle Aufrufe in Deutschland – sollten an den Proxy-SBC in Amsterdam geroutet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 4. Beispielkonfiguration für Szenario 2

| Physischer Standort des Benutzers | Der Benutzer anruft eine Nummer. | Online Voice Routing Policy | Für SBC konfigurierter Modus | Medien Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Frankreich | +49 1 437 2800 | Priorität 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Priorität 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com – Immer umgehen proxysbc.contoso.com – Immer umgehen | Teams Benutzer < – > DEsbc.contoso.com  |

Das folgende Diagramm zeigt den Datenverkehr auf hoher Ebene, wenn der interne deutsche Benutzer, der sich in Frankreich befindet, einen direkten Routing-Telefonanruf über Teams zu der Nummer in Deutschland führt. 

- Der Teams des Benutzers kommuniziert mit dem Telefonsystem direkt über die REST-API.

- Die während des Anrufs generierten Medien fließen direkt an die interne IP-Adresse von SBC in Deutschland. 

- Der SBC in Deutschland leitet den Fluss an den Proxy-SBC in Amsterdam und an das verbundene lokale PSTN-Netzwerk um. 

Diagramm 6.  Datenverkehrsfluss im Modus "Immer umgehen", und der Benutzer befindet sich nicht auf der Startseite, sondern im internen Netzwerk

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-6.png "Der Datenverkehrsfluss mit dem Modus &quot;Immer umgehen&quot;, und der Benutzer befindet sich nicht auf der Startseite, sondern im internen Netzwerk.")

### <a name="mode-2-only-for-local-users"></a>Modus 2: Nur für lokale Benutzer

Wenn es schlechte Verbindungen zwischen lokalen Zweigstellen, aber gute Verbindungen zwischen den einzelnen lokalen Zweigniederlassungen und regionalen Niederlassungen gibt, dann ist der empfohlene Modus "Nur für lokale Benutzer".

Nehmen wir beispielsweise an, dass Contoso in der Region APAC mehrere Niederlassungen in verschiedenen Ländern hat. In vielen Ländern ist ein Umstieg auf SIP nicht möglich, da das Unternehmen weiterhin über TDM-Trunks in vielen lokalen Zweigstellen verfügt. Die Zentralisierung der TDM-Trunks ist in der Region APAC keine Option. Darüber hinaus gibt es mehr als fünfzig Contoso-Zweigstellen in der Region APAC mit Hunderten von Gateways (SBCs). 

Um eine Lösung zu erstellen, bei der PSTN-Dienste in allen lokalen Zweigstellen in der Region APAC bereitgestellt werden, in denen die Zentralisierung der TDM-Trunks keine Option ist, paart der Contoso-Administrator einen regionalen SBC in Singapur als Proxy-SBC mit dem Direct-Routingdienst. Die direkte Verbindung zwischen den lokalen Zweigstellen ist nicht gut, aber es gibt eine gute Verbindung zwischen jeder lokalen Zweigstelle und dem regionalen SBC in Singapur. Für den regionalen SBC entscheidet sich der Administrator für den Modus "Always Bypass", und für die lokalen downstream-SBCs wählt der Administrator den Modus "Nur für lokale Benutzer".

Im Folgenden werden zwei Szenarien beschrieben:

- Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der SBC, der in der Online-Voiceroutingrichtlinie definiert ist.

- Szenario 2. Benutzer und Gateways befinden sich auf unterschiedlichen Websites

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Szenario 1. Der Benutzer befindet sich an demselben Speicherort wie der SBC, der in der Online-Voiceroutingrichtlinie definiert ist.

Angenommen, SBC in Singapur ist als Proxy-SBC für die lokalen downstream-SBCs in Vietnam und Indonesien konfiguriert. Der Benutzer befindet sich in Vietnam am selben Ort wie der lokale SBC. Die Richtlinien für das Online-Voicerouting legen fest, dass Anrufe in Vietnam (mit der Vorwahl +84) an den lokalen SBC in Vietnam geroutet werden sollen. Alle anderen Aufrufe – und, wenn der SBC in Vietnam fehlschlägt, Aufrufe in Vietnam – sollten an den Proxy-SBC in Singapur geroutet werden. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 5. Beispielkonfiguration für den Modus "Nur für lokale Benutzer" Szenario 1

| Physischer Standort des Benutzers | Der Benutzer anruft eine Nummer. | Online Voice Routing Policy | Für SBC konfigurierter Modus | Medien Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Priorität 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Priorität 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – nur für lokale Benutzer <br> proxysbc.contoso.com – Immer umgehen | Teams Benutzer <-> VNsbc.contoso.com |

In the following diagram, a user assigned to the local branch office in Vietnam, while on premises, makes a Direct Routing phone call through Teams. 

- Der Teams des Benutzers kommuniziert mit dem Telefonsystem direkt über die REST-API. 

- Während des Anrufs generierte Medien fließen an die interne IP-Adresse des lokalen SBC. 

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das verbundene lokale PSTN-Netzwerk um. 

- Der Proxy-SBC ist nur Telefonsystem der externen IP-Adresse sichtbar und leitet den Fluss vom downstream-SBC (in diesem Fall dem lokalen SBC in Vietnam) an Telefonsystem. 

- Der downstream-SBC in der lokalen Zweigniederlassung ist für Benutzer Telefonsystem sichtbar, wird aber in der virtuellen Netzwerktopologie zugeordnet.

Diagramm 7. Datenverkehrsfluss mit dem Modus "Nur für lokale Benutzer", und der Benutzer befindet sich auf der "Startseite"-Website

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-7.png "Datenverkehrsfluss mit Dem Modus &quot;Nur für lokale Benutzer&quot;, und der Benutzer befindet sich auf der &quot;Startseite&quot;-Website")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2. Benutzer und Gateways befinden sich auf unterschiedlichen Websites

Angenommen, SBC in Singapur ist als Proxy-SBC für die lokalen downstream-SBCs in Vietnam und Indonesien konfiguriert. Der interne Benutzer in Indonesien, der sich in der lokalen Zweigstelle befindet, führt einen direkten Routinganruf nach Vietnam durch. Die Richtlinien für das Online-Voicerouting legen fest, dass Anrufe nach Vietnam (mit der Vorwahl +84) an den lokalen SBC in Vietnam geroutet werden sollen. Alle anderen Aufrufe – und für den Fall, dass der SBC in Vietnam fehlschlägt, Aufrufe an Vietnam – sollten an den Proxy-SBC in Singapur geroutet werden. Der Proxy-SBC in Singapur ist auf "Always Bypass"-Modus festgelegt, und der lokale SBC in Vietnam ist auf "Nur für lokale Benutzer" festgelegt. In der folgenden Tabelle ist die Beispielkonfiguration zusammengefasst. 

Tabelle 6. Benutzerkonfiguration

| Physischer Standort des Benutzers | Der Benutzer anruft eine Nummer. | Online Voice Routing Policy | Für SBC konfigurierter Modus | Medien Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesien | +84 4 3926 3000 | Priorität 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Priorität 2: .* - proxysbc.contoso.com |VNsbc.contoso.com – nur für lokale Benutzer <br> proxysbc.contoso.com – Immer umgehen | Teams Benutzer <-> proxysbc.contoso.com <-> VNsbc.contoso.com |


Im folgenden Diagramm führt der interne Benutzer, der in der indonesischen Zweigstelle lokal ist, einen direkten Routing-Telefonanruf über Teams zu einer Nummer in Vietnam durch. 

- Der Teams des Benutzers kommuniziert mit dem Telefonsystem direkt über die REST-API.

- Während des Anrufs generierte Medien fließen zuerst an die interne IP-Adresse des Proxy-SBC. 

- Der Proxy-SBC in Singapur leitet den Fluss an die interne IP-Adresse des downstream SBC in Vietnam und an Telefonsystem. 

- Der Downstream-SBC in Vietnam leitet den Fluss an das verbundene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist nur für Telefonsystem externe IP-Adresse sichtbar.

- Die downstream-SBCs in lokalen Zweigstellen sind für Benutzer Telefonsystem sichtbar, werden aber in der virtuellen Netzwerktopologie zugeordnet.

Diagramm 8.  Datenverkehrsfluss im Modus "Nur für lokale Benutzer", und der Benutzer befindet sich nicht auf der Startseite, sondern im internen Netzwerk

![Diagramm mit Anzeige des Datenverkehrsflusses zur Optimierung lokaler Medien](media/direct-routing-media-op-8.png "Datenverkehrsfluss mit dem Modus &quot;Nur für lokale Benutzer&quot;, der Benutzer befindet sich nicht auf der &quot;Homepage&quot;, sondern im internen Netzwerk")

## <a name="known-issues"></a>Bekannte Probleme

Im Folgenden finden Sie eine Liste der bekannten Probleme, die derzeit bei der Optimierung lokaler Medien auftreten. Microsoft arbeitet an diesen Problemen.

| Problem | Problemumgehung |
| :--- | :--- |
| Teams Client wird nicht als **intern** identifiziert, wenn Teams öffentliche IP-Adresse des Kunden der Liste Vertrauenswürdige IP des Kunden entspricht. | Die Optimierung lokaler Medien setzt voraus, dass Teams Client-Subnetz einem vom Mandanten konfigurierten [Netzwerksubnetz-Subnetz entspricht.](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| Anrufskalation führt zu Gesprächsanrufen, wenn Teams-Client als intern identifiziert wird.| Deaktivieren Sie die Optimierung lokaler Medien auf dem Direct-Routing-SBC.|
| Anrufskalation von 1 bis 1 Anruf zwischen internen Kunden zum Mehrteileranruf mit externen Kunden/Ressourcen führt zu abgelegten Anrufen | Es wird noch an einer Lösung gearbeitt. Deaktivieren Sie alternativ die Optimierung lokaler Medien auf dem Direct-Routing-SBC.|
| Teams Der Benutzer hält den Anruf. Musik auf dem PSTN-Ende ab, und die Optimierung lokaler Medien funktioniert. Der Teams benutzer setzt den Anruf fort. Der Aufruf von PSTN wird fortgesetzt, aber die Optimierung der lokalen Medien funktioniert nicht, und der Aufruf wird über zentrale SBC (Proxy) fortgesetzt. | Wenn ein Benutzer einen Anruf startet, um Musik im Warteschleifen-Speicher (MoH) zu initiieren, wird er von 1:1 zu einem Anruf mit mehrerenPartys durch den Anrufcontroller eskaliert, um media controller and media processor (als AVMCU-Mixer dienen) aufzurufen, über den MoH einen benutzer erreicht, der im Halteraum war. Die Deeskalierung auf einen 1:1-Anruf nach dem Fortsetzen des Anrufs erfolgt nicht wie je nach Entwurf. Deaktivieren Sie die Optimierung lokaler Medien auf dem Direct-Routing-SBC.|
