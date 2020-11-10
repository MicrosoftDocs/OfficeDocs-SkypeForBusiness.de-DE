---
title: Direkte Weiterleitung der lokalen Medienoptimierung
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
description: Lokale Medienoptimierung für direktes Routing
appliesto:
- Microsoft Teams
ms.openlocfilehash: ebf6ca7b8b3c1bd18ffb5c00f124d90f973c4b46
ms.sourcegitcommit: aec9fcc178c227d9cfe3e2bf57d0f3bf4c318d49
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "48950789"
---
# <a name="local-media-optimization-for-direct-routing"></a>Lokale Medienoptimierung für direktes Routing

Public Switched Telephone Network (PSTN) Voice gilt als eine unternehmenskritische Anwendung mit hohen Erwartungen an die Sprachqualität. Mit der direkten Weiterleitung können Sie die Mediendatenströme steuern, um eine Vielzahl von Netzwerktopologien und lokalen Telefonie-Setups für verschiedene Unternehmen in der ganzen Welt zu ermöglichen. 

Durch die lokale Medienoptimierung für das direkte Routing können Sie die Sprachqualität verwalten, indem Sie:

-   Steuern, wie der Mediendatenverkehr zwischen den Teams-Clients und den SBCS (Customer Session Border Controllers) fließt.
-   Lokales Speichern von Medien innerhalb der Grenzen von Subnetzen des Unternehmensnetzwerks.
-   Zulassen von Medienströmen zwischen den Teams-Clients und der SBCS, selbst wenn sich die SBCS hinter Unternehmensfirewalls mit privaten IPS befinden und für Microsoft nicht direkt sichtbar sind.

Die lokale Medienoptimierung unterstützt zwei Szenarien:

- Zentralisierung aller lokalen Stämme über einen zentralisierten SBC, der mit dem Haupt-SIP-Trunk (Session Initiation Protocol) verbunden ist – Bereitstellung von Telefoniedienst für alle lokalen Niederlassungen des Unternehmens.

-   Erstellen einer virtuellen Netzwerktopologie von SBCS – wobei die SBCS in den lokalen Zweigstellen mit einem zentralen Proxy-SBC verbunden sind, der über die externe IP-Adresse für Microsoft Phone System sichtbar ist und mit ihm kommuniziert. In einer virtuellen Netzwerktopologie kommunizieren Downstream-SBCS über interne IPS und sind nicht direkt für das Telefon System sichtbar.

In diesem Artikel werden die Funktions Funktionen sowie Kundenszenarien und-Lösungen beschrieben. Details zur Konfiguration finden Sie unter [Konfigurieren der lokalen Medienoptimierung](direct-routing-media-optimization-configure.md). 

  > [!NOTE]
  > Wenn Sie Medien lokal innerhalb der Grenzen Ihres Intranets behalten möchten, wird die lokale Medienoptimierung empfohlen. Wenn Sie bereits über eine medienumgehung verfügen und nur die öffentlichen IP-Adressen Ihres SBCS verwenden, ist es nicht zwingend erforderlich, zu einer lokalen Medienoptimierung zu wechseln. Sie können die medienumgehung weiterhin verwenden. Weitere Informationen finden Sie unter [Planen der medienumgehung](direct-routing-plan-media-bypass.md).


## <a name="supported-customer-scenarios"></a>Unterstützte Kundenszenarien

In dieser Diskussion wird davon ausgegangen, dass Contoso mehrere Unternehmen auf der ganzen Welt wie folgt ausführt. (Beachten Sie, dass die Regionen Europa und APAC nur als Beispiele verwendet werden. In einem Unternehmen gibt es möglicherweise mehrere verschiedene Regionen mit ähnlichen Anforderungen.)
 
- **In Europa** verfügt Contoso über Niederlassungen in ungefähr 30 Ländern. Jede Niederlassung hat eine eigene private Branch Exchange (PBX). 

  Contoso wurde eine Option zum Zentralisieren der Trunks an einem einzigen Standort--Amsterdam--für alle 30 europäischen Niederlassungen angeboten. Contoso hat den SBC in Amsterdam bereitgestellt, genügend Bandbreite für die Ausführung von Anrufen über den zentralen Standort bereitgestellt, einen zentralen SIP-Stamm an den zentralisierten Standort angeschlossen und alle europäischen Standorte in Amsterdam bedient. 

- **In der Region APAC** verfügt Contoso über mehrere Niederlassungen in verschiedenen Ländern. 

  In vielen Ländern verfügt das Unternehmen weiterhin über Zeit Teilungs Multiplex (TDM)-Stämme in lokalen Niederlassungen. Die Zentralisierung der TDM-Stämme ist in der Region APAC keine Option, daher ist die Umstellung auf SIP nicht möglich. Angenommen, es gibt mehr als 50 Contoso-Zweigstellen in der Region APAC mit Hunderten von Gateways (SBCS). In diesem Szenario ist es nicht möglich, alle Gateways mit der direkten Routing Schnittstelle zu koppeln, da es keine öffentlichen IP-Adressen und/oder lokale Internet Ausbrüche gibt. Darüber hinaus verhängen einige Länder behördliche Anforderungen, die nicht erfüllt werden können, ohne dass eine lokale PSTN-Netzwerkverbindung besteht.

Basierend auf den geschäftlichen Anforderungen implementierte Contoso zwei Lösungen mit lokaler Medienoptimierung für das direkte Routing:

- **In Europa** sind alle Trunks zentralisiert, und die Medien fließen zwischen dem zentralen SBC und den Benutzern basierend auf dem Standort des Benutzers. 

  - Wenn ein Benutzer mit dem lokalen Subnetz eines Unternehmensnetzwerks verbunden ist (das heißt, der Benutzer ist intern), fließt zwischen der internen IP des zentralen SBC und dem Team-Client des Benutzers Medien. 
  
  - Wenn ein Benutzer außerhalb der Grenzen des Unternehmensnetzwerks liegt, beispielsweise wenn der Benutzer eine öffentliche drahtlose Internet Verbindung verwendet, wird der Benutzer als "extern" betrachtet. In diesem Fall fließt das Medium zwischen der externen IP des zentralen SBC und dem Teams-Client.

- **In der Region APAC** wird ein zentralisierter Proxy-SBC mit dem Microsoft Direct-Routing gekoppelt, das Medien zwischen der direkten Routingschnittstelle und den Downstream-SBCS in lokalen Zweigstellen leitet. 

  Die Downstream-SBCS in den lokalen Zweigstellen sind für die direkte Weiterleitung in APAC nicht direkt sichtbar, aber Sie werden mit dem Set-CSOnlinePSTNGateway-Cmdlet zum Erstellen einer virtuellen Netzwerktopologie in Microsoft Phone System gekoppelt. Medien bleiben immer lokal, wenn dies möglich ist. Externe Benutzer haben Medien, die zwischen dem Teams-Client und der öffentlichen IP-Adresse des Proxy-SBC fließen.


## <a name="central-sbc-with-centralized-trunks"></a>Zentrales SBC mit zentralisierten Trunks

Zum Erstellen einer Lösung, bei der PSTN-Dienste für alle lokalen Zweigstellen über einen zentralen SBC mit einem verbundenen zentralisierten SIP-Trunk bereitgestellt werden, wird vom Contoso-mandantenadministrator ein SBC (centralsbc.contoso.com) mit dem Dienst verbunden. der SBC verfügt über einen zentralen SIP-Trunk, der mit ihm verbunden ist. 

- Wenn sich ein Benutzer im internen Netzwerk des Unternehmens befindet, stellt der SBC die interne IP-Adresse des SBC für Medien zur Verfügung.

- Wenn sich ein Benutzer außerhalb des Unternehmensnetzwerks befindet, stellt der SBC die externe (öffentliche) IP-Adresse des SBC zur Verfügung.

Hinweis: alle Werte in Beispielen, Tabellen oder Diagrammen werden nur zu Illustrationszwecken dargestellt.

Tabelle 1 Beispiel für Netzwerkparameter für SBCS 

| Ort | SBC-FQDN | Internes Subnetz | Externe NAT (vertrauenswürdige IP-Adresse) | Externe SBC-IP-Adresse | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Amsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Deutschland | Nicht bereitgestellt | 192.168.6.0/24 | 172.16.76.74 | Nicht bereitgestellt |  Nicht bereitgestellt |
| Frankreich | Nicht bereitgestellt | 192.168.7.0/24 | 172.16.76.75 | Nicht bereitgestellt |  Nicht bereitgestellt ||||


### <a name="internal-user"></a>Interner Benutzer

Das folgende Diagramm zeigt den Datenfluss, wenn ein Benutzer mit dem Unternehmensnetzwerk in der Home Branch Office-oder Website des Benutzers verbunden ist. 

Der Benutzer wird in der lokalen Niederlassung in Deutschland zugeteilt. Der Benutzer führt einen direkten Routing-Anruf über Teams.

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API, aber die während des Anrufs generierten Medien fließen in die interne IP-Adresse des zentralen SBC. 

- Der SBC leitet den Fluss an das Telefon System und das angeschlossene PSTN-Netzwerk um. 

- Der zentrale SBC ist nur über die externe IP-Adresse für das Telefon System sichtbar. 

Diagramm 1 Traffic-Flow, wenn sich der Benutzer auf der "Home"-Website mit einem zentralisierten SBC und einem verbundenen zentralisierten SIP-Trunk befindet

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-1.png "Traffic-Flow, wenn sich der Benutzer in der "Home"-Website befindet, mit zentralisiertem SBC mit verbundenem zentralisiertem SIP-Trunk")


### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenfluss, wenn ein Benutzer nicht lokal ist und nicht mit dem Unternehmensnetzwerk verbunden ist (das Gerät des Benutzers ist über ein mobiles Gerät oder öffentliches WLAN mit dem Internet verbunden). Der Benutzer führt einen direkten Routing-Anruf über Teams:

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API, doch in diesem Fall fließen die während des Anrufs generierten Medien in die externe IP-Adresse des zentralen SBC. 

- Der SBC leitet den Fluss an das Telefon System und das angeschlossene PSTN-Netzwerk um. 

- Der zentrale SBC ist nur über die externe IP-Adresse für das Telefon System sichtbar. 

In diesem Fall ist das Verhalten ähnlich, ob der Benutzer lokal in der Zweigstelle in Deutschland oder in einer anderen Zweigstelle ist. Der Benutzer wird als extern eingestuft, da sich der Benutzer außerhalb der Grenzen des Unternehmensnetzwerks befindet.

Diagramm 2. Datenverkehr, wenn der Benutzer extern mit einem zentralisierten SBC und mit einem verbundenen zentralisierten SIP-Trunk ist

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-2.png "Traffic-Flow, wenn der Benutzer extern ist, bei zentralisiertem SBC mit verbundenem zentralisiertem SIP-Trunk")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>Proxy-SBC mit verbundenen Downstream-SBCS

Zum Erstellen einer Lösung, bei der PSTN-Dienste in allen lokalen Zweigstellen in der Region APAC zur Verfügung gestellt werden, wo die Zentralisierung der TDM-Stämme nicht möglich ist, wird vom Contoso-Administrator ein SBC (proxysbc.contoso.com), der auch als Proxy-SBC bezeichnet wird, zum Direct Routing-Dienst hinzu gepaßt. 

Anschließend fügt der Contoso-Administrator einige Downstream-SBCS hinzu, die darauf hindeuten, dass Sie über die Proxy-SBC-proxysbc.contoso.com erreicht werden können. Downstream-SBCS haben keine öffentlichen IPS, Sie können jedoch VoIP-Routen zugewiesen werden. Die folgende Tabelle zeigt Beispiel Netzwerkparameter und-Konfiguration.

Wenn sich ein Benutzer in der lokalen Zweigstelle befindet, in der sich der Downstream-SBC befindet, fließt der Mediendatenverkehr direkt zwischen dem Benutzer und dem lokalen Downstream-SBC. Wenn sich ein Benutzer außerhalb des Amtes befindet (in einem öffentlichen Internet), fließt das Medium vom Benutzer in die öffentliche IP des Proxy-SBC, der es an die entsprechenden Downstream-SBC (s) weiterleitet.

Tabelle 2. Beispiel-SBC-Netzwerkinformationen

| Ort | SBC-FQDN | Internes Subnetz | Externe NAT (vertrauenswürdige IP-Adresse) | Externe SBC-IP-Adresse  | Interne SBC-IP-Adresse |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Keine |  192.168.1.5 |
| Indonesien  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Keine |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Interner Benutzer 

Das folgende Diagramm zeigt den Datenverkehrs Fluss auf hoher Ebene für das Szenario, wenn sich ein Benutzer innerhalb des Büros in der Region APAC befindet. Der Benutzer, der einer lokalen Niederlassung in Vietnam zugeordnet ist und sich lokal befindet, führt einen direkten Telefonanruf über Teams. 

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API, aber während des Anrufs generierte Medien fließen in die interne IP-Adresse des lokalen SBC.

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das angeschlossene lokale PSTN-Netzwerk weiter.

-  Der Proxy-SBC ist nur über die externe IP-Adresse für das Telefonsystem sichtbar und leitet den Fluss vom Downstream-SBC (in diesem Fall dem lokalen SBC in Vietnam) an das Telefonsystem weiter. 

- Der Downstream-SBC in der lokalen Zweigstelle ist für das Telefon System nicht direkt sichtbar, wird aber innerhalb der vom Contoso-Administrator definierten virtuellen Netzwerktopologie zugeordnet, während die lokale Medienoptimierung eingerichtet wird.

Hinweis: je nach dem konfigurierten Modus für die lokale Medienoptimierung kann das Verhalten für lokale Benutzer und nicht lokale Benutzer unterschiedlich sein. 

Weitere Informationen zu den möglichen Modi und dem relevanten Verhalten finden Sie unter Konfigurieren der lokalen Medienoptimierung.

Diagramm 3 Verkehrsfluss, wenn sich der Benutzer im "Home"-Netzwerk mit einem Proxy-SBC und mit verbundenen Downstream-SBCS befindet 

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-3.png "Verkehrsfluss bei Proxy-SBC mit verbundenen Downstream-SBCS, wenn sich der Benutzer im "Home"-Netzwerk befindet")

### <a name="external-user"></a>Externer Benutzer

Das folgende Diagramm zeigt den Datenfluss, wenn sich ein Benutzer außerhalb der Unternehmensnetzwerk Grenzen befindet. Der Benutzer befindet sich nicht in einem lokal (liegt nicht innerhalb der Grenzen des Unternehmensnetzwerks). Der Benutzer führt einen direkten Routing-Anruf über Teams zu einer Telefonnummer in Vietnam. 

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API, aber die während des Anrufs generierten Medien fließen zunächst in die externe IP-Adresse des Proxy-SBC in Singapur. 

- Basierend auf Konfigurations-und VoIP-Richtlinien (siehe [Konfigurieren der lokalen Medienoptimierung](direct-routing-media-optimization-configure.md) für Details) leitet der Proxy-SBC den Fluss an den Downstream-SBC in Vietnam weiter. 

- Der Downstream-SBC in Vietnam leitet den Fluss an das angeschlossene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist nur über die externe IP-Adresse für das Telefon System sichtbar.

-  Der Downstream-SBC in der lokalen Zweigstelle ist für das Telefon System nicht direkt sichtbar, wird aber innerhalb der vom Contoso-Administrator definierten virtuellen Netzwerktopologie zugeordnet, während die lokale Medienoptimierung eingerichtet wird. Im Beispiel wird der Benutzer als extern eingestuft, da sich der Benutzer außerhalb der Grenzen des Unternehmensnetzwerks befindet. 

Diagramm 4 Datenfluss, wenn der Benutzer extern mit einem Proxy-SBC und mit verbundenen Downstream-SBCS

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-4.png "Datenfluss bei Proxy-SBC mit verbundenen Downstream-SBCS, wenn der Benutzer extern ist")

## <a name="local-media-optimization-modes"></a>Lokale Medien Optimierungs Modi

Die lokale Medienoptimierung unterstützt zwei Modi:

- **Modus 1: immer umgehen**. In diesem Fall werden die Medien, wenn der Benutzer intern ist, durch die interne IP-Adresse des lokalen Downstream-SBC durchlaufen, unabhängig von der tatsächlichen Position des internen Benutzers. beispielsweise in derselben Zweigstelle, in der sich der Downstream-SBC befindet, oder in einer anderen Zweigstelle.

- **Modus 2: nur für lokale Benutzer**. In diesem Modus fließen Medien nur dann direkt zur internen IP-Adresse des lokalen Downstream-SBC, wenn Sie von dem internen Benutzer in derselben Zweigstelle wie dem Downstream-SBC generiert wurden. 

Um zwischen den Modi für die lokale Medienoptimierung zu unterscheiden, muss der mandantenadministrator den-BypassMode-Parameter für jeden SBC mit dem Set-CSonlinePSTNGateway-Cmdlet auf "Always" oder "OnlyForLocalUsers" setzen. Weitere Informationen finden Sie unter [Konfigurieren der lokalen Medienoptimierung](direct-routing-media-optimization-configure.md).  

### <a name="mode-1-always-bypass"></a>Modus 1: immer umgehen

Wenn Sie eine gute Verbindung zwischen Zweigstellen haben, ist der empfohlene Modus immer Bypass.

Angenommen, ein Unternehmen verfügt über einen zentralisierten SIP-Trunk in Amsterdam, der 30 Ländern dient und eine gute Konnektivität zwischen allen 30 Websites und lokalen Benutzern bietet. Es gibt auch eine Niederlassung in Deutschland, in der ein lokaler SBC bereitgestellt wird.

Der SBC in Deutschland kann im Modus "immer umgehen" konfiguriert werden. Benutzer können unabhängig von Ihrem Standort direkt über die interne IP-Adresse des SBC eine Verbindung mit dem SBC herstellen (beispielsweise von Frankreich nach Deutschland; siehe Abbildung unten als Referenz).

Im folgenden werden zwei Szenarien beschrieben:

- Szenario 1 Der Benutzer befindet sich am gleichen Speicherort wie der SBC, der in der Online-VoIP-Routing Richtlinie definiert ist.

- Szenario 2. Benutzer und Gateways sind an verschiedenen Standorten.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Szenario 1 Der Benutzer befindet sich am gleichen Speicherort wie der SBC, der in der Online-VoIP-Routing Richtlinie definiert ist.

Der SBC in Amsterdam ist so konfiguriert, dass er ein Proxy-SBC für einen lokalen Downstream-SBC in Deutschland ist. Der Benutzer befindet sich in Deutschland im gleichen Subnetz wie das Unternehmensnetzwerk des lokalen SBC. Sowohl SBCS (Proxy als auch Downstream) sind für den immer-Bypass-Modus konfiguriert. Online-VoIP-Routing Richtlinien legen fest, dass Sie im Falle von Anrufen innerhalb Deutschlands (mit Vorwahl + 49) an den lokalen SBC in Deutschland weitergeleitet werden sollen. Alle anderen Anrufe--und für den Fall, dass der SBC in Deutschland scheitert, Anrufe in Deutschland--sollten an den Proxy SBC in Amsterdam weitergeleitet werden. Die folgende Tabelle enthält eine Zusammenfassung der Beispielkonfiguration. 

Tabelle 3. Beispielkonfiguration für Szenario 1

| Physischer Standort des Benutzers | Der Benutzer führt einen Anruf an eine Nummer. | Online-VoIP-Routing Richtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Deutschland | + 49 1 437 2800 | Priorität 1: ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com<br>Priorität 2:. *-proxysbc.contoso.com| DEsbc.contoso.com – immer umgehen <br>proxysbc.contoso.com – immer umgehen | Teams User < – > DEsbc.contoso.com |

Das folgende Diagramm zeigt den hohen Datenverkehrs Fluss für den internen Nutzer in Deutschland, der einen direkten Telefonanruf über Teams an die Nummer in Deutschland durchführt. 

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API. 

- Die während des Anrufs generierten Medien fließen in die interne IP-Adresse des lokalen SBC. 

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Amsterdam und an das angeschlossene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist nur über die externe IP-Adresse für das Telefonsystem sichtbar und leitet den Fluss vom Downstream-SBC (in diesem Fall dem lokalen SBC in Deutschland) an das Telefonsystem weiter. 

- Der Downstream-SBC in der lokalen Zweigstelle ist für das Telefon System nicht direkt sichtbar, wird aber innerhalb der vom Contoso-Administrator definierten virtuellen Netzwerktopologie zugeordnet, während die lokale Medienoptimierung eingerichtet wird.


Diagramm 5  Traffic-Flow mit "Always Bypass"-Modus und der Benutzer befindet sich auf der "Home"-Website

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-5.png "Traffic-Flow mit "Always Bypass"-Modus und Nutzer befindet sich auf der "Home"-Website")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2: Benutzer und Gateways sind an verschiedenen Standorten

Der SBC in Amsterdam ist so konfiguriert, dass er ein Proxy-SBC für einen lokalen Downstream-SBC in Deutschland ist. Sowohl SBCS (Proxy als auch Downstream) sind für den immer-Bypass-Modus konfiguriert. Der interne Benutzer in Frankreich, der sich in der lokalen Niederlassung befindet, führt einen direkten Anruf nach Deutschland. Online-VoIP-Routing Richtlinien legen fest, dass Anrufe nach Deutschland (mit Vorwahl + 49) an den lokalen SBC in Deutschland weitergeleitet werden sollen. Alle anderen Anrufe--und für den Fall, dass der SBC in Deutschland ausfällt, sollten alle Anrufe in Deutschland--an den Proxy SBC in Amsterdam weitergeleitet werden. Die folgende Tabelle enthält eine Zusammenfassung der Beispielkonfiguration. 

Tabelle 4. Beispielkonfiguration für Szenario 2

| Physischer Standort des Benutzers | Der Benutzer führt einen Anruf an eine Nummer. | Online-VoIP-Routing Richtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Frankreich | + 49 1 437 2800 | Priorität 1: ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com <br>Priorität 2:. *-proxysbc.contoso.com |  DEsbc.contoso.com – immer Bypass-proxysbc.contoso.com – immer umschalten | Teams User < – > DEsbc.contoso.com  |

Das folgende Diagramm zeigt den Datenverkehrs Fluss auf hoher Ebene, wenn der interne deutsche Nutzer in Frankreich einen direkten Routing-Anruf über Teams an die Nummer in Deutschland durchführt. 

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API.

- Die während des Anrufs generierten Medien fließen direkt an den SBC in Deutschlands interner IP-Adresse. 

- Der SBC in Deutschland leitet den Fluss an den Proxy SBC in Amsterdam und an das angeschlossene lokale PSTN-Netzwerk weiter. 

Abbildung 6.  Verkehrsfluss mit "Always Bypass"-Modus, und der Benutzer befindet sich nicht auf der "Home"-Website, sondern im internen Netzwerk

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-6.png "Traffic-Flow mit "Always Bypass"-Modus und Benutzer befindet sich nicht auf der "Home"-Website, sondern im internen Netzwerk")

### <a name="mode-2-only-for-local-users"></a>Modus 2: nur für lokale Benutzer

Wenn es schlechte Verbindungen zwischen lokalen Zweigstellen gibt, aber gute Verbindungen zwischen jeder lokalen Zweigstelle und einem regionalen Büro bestehen, lautet der empfohlene Modus "nur für lokale Benutzer".

Nehmen Sie beispielsweise in der Region APAC an, dass Contoso mehrere Niederlassungen in verschiedenen Ländern hat. Für viele Länder ist die Umstellung auf SIP nicht möglich, da das Unternehmen weiterhin TDM-Stämme in vielen lokalen Niederlassungen hat. Die Zentralisierung der TDM-Stämme ist in der Region APAC keine Option. Darüber hinaus gibt es mehr als 50 Contoso-Niederlassungen in der Region APAC mit Hunderten von Gateways (SBCS). 

Zum Erstellen einer Lösung, bei der PSTN-Dienste in allen lokalen Zweigstellen in der Region APAC bereitgestellt werden, in denen die Zentralisierung der TDM-Stämme nicht möglich ist, gibt der Contoso-Administrator einen regionalen SBC in Singapur als Proxy-SBC für den Direct Routing-Dienst aus. Die direkte Verbindung zwischen den lokalen Niederlassungen ist nicht gut, aber es besteht eine gute Verbindung zwischen jeder lokalen Zweigstelle und dem regionalen SBC in Singapur. Für den regionalen SBC wählt der Administrator den Modus "immer umgehen" und für den lokalen Downstream-SBCS den Administrator "nur für lokale Benutzer" aus.

Im folgenden werden zwei Szenarien beschrieben:

- Szenario 1 Der Benutzer befindet sich am gleichen Speicherort wie der SBC, der in der Online-VoIP-Routing Richtlinie definiert ist.

- Szenario 2. Benutzer und Gateways sind an verschiedenen Standorten

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Szenario 1 Der Benutzer befindet sich am gleichen Speicherort wie der SBC, der in der Online-VoIP-Routing Richtlinie definiert ist.

Davon ausgehen, dass der SBC in Singapur als Proxy-SBC für die lokale Downstream-SBCS in Vietnam und Indonesien konfiguriert ist. Der Benutzer befindet sich in Vietnam am selben Ort wie der lokale SBC. Online-VoIP-Routing Richtlinien geben an, dass Anrufe in Vietnam (mit Ortsvorwahl + 84) an den lokalen SBC in Vietnam weitergeleitet werden sollen. Alle anderen Anrufe--und, wenn der SBC in Vietnam scheitert, Anrufe in Vietnam--sollten an den Proxy SBC in Singapur weitergeleitet werden. Die folgende Tabelle enthält eine Zusammenfassung der Beispielkonfiguration. 

Tabelle 5. Beispielkonfiguration für den Modus "nur für lokale Benutzer" Szenario 1

| Physischer Standort des Benutzers | Der Benutzer führt einen Anruf an eine Nummer. | Online-VoIP-Routing Richtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 | Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br>Priorität 2:. *-proxysbc.contoso.com | VNsbc.contoso.com – nur für lokale Benutzer <br> proxysbc.contoso.com – immer umgehen | Teams User < – > VNsbc.contoso.com |

In der folgenden Abbildung führt ein Benutzer, der der lokalen Niederlassung in Vietnam zugewiesen ist, während er sich lokal befindet, einen direkten Routing Anruf über Teams durch. 

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API. 

- Während des Anrufs generierte Medien fließen in die interne IP-Adresse des lokalen SBC. 

- Der lokale SBC leitet den Fluss an den Proxy-SBC in Singapur und an das angeschlossene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist nur über die externe IP-Adresse für das Telefonsystem sichtbar und leitet den Fluss vom Downstream-SBC (in diesem Fall dem lokalen SBC in Vietnam) an das Telefonsystem weiter. 

- Der Downstream-SBC in der lokalen Zweigstelle ist für das Telefon System nicht direkt sichtbar, wird aber innerhalb der virtuellen Netzwerktopologie zugeordnet.

Abbildung 7. Verkehrsfluss mit dem Modus "nur für lokale Benutzer" und der Benutzer befindet sich auf der "Home"-Website

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-7.png "Verkehrsfluss mit dem Modus "nur für lokale Benutzer" und der Benutzer befindet sich auf der "Home"-Website")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Szenario 2. Benutzer und Gateways sind an verschiedenen Standorten

Davon ausgehen, dass der SBC in Singapur als Proxy-SBC für die lokale Downstream-SBCS in Vietnam und Indonesien konfiguriert ist. Der interne Benutzer in Indonesien, der sich in der lokalen Zweigstelle befindet, führt einen direkten Anruf nach Vietnam. Online-VoIP-Routing Richtlinien geben an, dass Anrufe nach Vietnam (mit Ortsvorwahl + 84) an den lokalen SBC in Vietnam weitergeleitet werden sollen. Alle anderen Anrufe--und, falls der SBC in Vietnam scheitert, Anrufe nach Vietnam--sollten an den Proxy SBC in Singapur weitergeleitet werden. Der Proxy-SBC in Singapur ist auf "Always Bypass"-Modus eingestellt, und der lokale SBC in Vietnam ist auf "nur für den lokalen Benutzermodus" eingestellt. Die folgende Tabelle enthält eine Zusammenfassung der Beispielkonfiguration. 

Tabelle 6. Benutzerkonfiguration

| Physischer Standort des Benutzers | Der Benutzer führt einen Anruf an eine Nummer. | Online-VoIP-Routing Richtlinie | Für SBC konfigurierter Modus | Medienfluss | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesien | + 84 4 3926 3000 | Priorität 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Priorität 2:. *-proxysbc.contoso.com |VNsbc.contoso.com – nur für lokale Benutzer <br> proxysbc.contoso.com – immer umgehen | Teams User < – > proxysbc.contoso.com < – > VNsbc.contoso.com |


Im folgenden Diagramm führt der interne Benutzer, während er sich lokal in der indonesischen Niederlassung befindet, einen direkten Routing-Anruf über Teams zu einer Nummer in Vietnam durch. 

- Der Team-Client des Benutzers kommuniziert mit dem Telefon System direkt über die restliche API.

- Während des Anrufs generierte Medien werden zuerst an die interne IP-Adresse des Proxy-SBC übertragen. 

- Der Proxy-SBC in Singapur leitet den Fluss an die interne IP-Adresse des Downstream-SBC in Vietnam und an das Telefon System weiter. 

- Der Downstream-SBC in Vietnam leitet den Fluss an das angeschlossene lokale PSTN-Netzwerk weiter. 

- Der Proxy-SBC ist nur über die externe IP-Adresse für das Telefon System sichtbar.

- Die Downstream-SBCS in lokalen Zweigstellen sind für das Telefon System nicht direkt sichtbar, werden aber innerhalb der virtuellen Netzwerktopologie zugeordnet.

Abbildung 8.  Verkehrsfluss mit dem Modus "nur für lokale Benutzer", und der Benutzer befindet sich nicht auf der "Home"-Website, sondern im internen Netzwerk

![Diagramm mit Datenverkehrs Fluss-Optimierung für lokale Medien](media/direct-routing-media-op-8.png "Verkehrsfluss mit dem Modus "nur für lokale Benutzer" befindet sich der Benutzer nicht auf der "Home"-Website, sondern im internen Netzwerk")

## <a name="known-issues"></a>Bekannte Probleme

Im folgenden finden Sie eine Liste der bekannten Probleme, die derzeit in der lokalen Medienoptimierung vorhanden sind. Microsoft arbeitet an der Behebung dieser Probleme.

| Problem | Workaround |
| :--- | :--- |
| Teams-Client wird nicht als " **intern** " erkannt, wenn die öffentliche IP-Adresse des Teams-Clients der vertrauenswürdigen IP-Liste des Kunden entspricht. | Für die lokale Medienoptimierung muss das Team-Client-Subnetz einem vom Mandanten konfigurierten [Netzwerk-Subnetz](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) entsprechen.|
| Anruf Eskalationen führen zu verworfenen anrufen, wenn der Team-Client als "intern" erkannt wird.| Deaktivieren Sie die lokale Medienoptimierung für das Direct Routing-SBC.|


