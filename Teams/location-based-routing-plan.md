---
title: Planen des standortbasierten Routings für direktes Routing
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Erfahren Sie, wie Sie Location-Based Routing für Teams Telefon Direct Routing planen.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6361e9454f6df301c0fbf1c91e39158115f2300
ms.sourcegitcommit: 3beef904411a9d5787a73678464003a868630649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2022
ms.locfileid: "64817796"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planen des standortbasierten Routings für direktes Routing

In einigen Ländern und Regionen ist es illegal, den Anbieter von Telefonfestnetzen (Public Switched Telephone Network, PSTN) zu umgehen, um die Anrufkosten für Ferngespräche zu senken. 

In diesem Artikel wird beschrieben, was Sie wissen müssen, um Location-Based Routing zu verwenden, um die gebührenpflichtige Umgehung für Microsoft Teams Benutzer basierend auf ihrem geografischen Standort einzuschränken. Dieser Artikel gilt nur für Direct Routing. Location-Based Routing gilt nicht für Anrufpläne oder Telefonieanbieter.

Wenn Sie bereit sind, Location-Based Routing zu aktivieren, lesen Sie:

- [Konfigurieren der Netzwerkeinstellungen für das standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Bereitstellen von Netzwerkeinstellungen für Location-Based Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

> [!NOTE]
> Sie sollten Location-Based Routing nicht verwenden, um PSTN-Anrufe dynamisch basierend auf dem Standort des Benutzers weiterzuleiten. Dies kann zu unbeabsichtigten Ergebnissen führen.

## <a name="overview"></a>Übersicht

mit Location-Based Routing können Sie die gebührenpflichtige Umgehung für einen Benutzer basierend auf der Richtlinie und dem geografischen Standort des Benutzers zum Zeitpunkt eines eingehenden oder ausgehenden PSTN-Anrufs einschränken. 

Location-Based Routing verwendet die Netzwerktopologie, die Sie für Netzwerkregion, Standort und Subnetz definieren. Wenn die gebührenpflichtige Umgehung für einen Standort eingeschränkt ist, ordnen Sie jedes IP-Subnetz und jedes PSTN-Gateway für diesen Standort einem Netzwerkstandort zu. 

Zum Zeitpunkt eines PSTN-Anrufs wird der Standort eines Benutzers durch das IP-Subnetz bestimmt, mit dem die Teams Endpunkte des Benutzers verbunden sind. Wenn ein Benutzer mehrere Teams Clients an unterschiedlichen Standorten hat, erzwingt Location-Based Routing das Routing jedes Clients separat je nach Standort der Teams Endpunkte.

Weitere Informationen zu Netzwerkeinstellungen finden Sie [unter Netzwerkeinstellungen für Cloud voice features in Teams](cloud-voice-network-settings.md).

In diesem Artikel wird davon ausgegangen, dass sich ein Netzwerkstandort in einem der folgenden Zustände befinden kann:

- **Aktiviert** – Ein Standort, der mithilfe von Mandantennetzwerksubnetzen und -standorten konfiguriert und für Location-Based Routing aktiviert ist.

- **Nicht aktiviert** – Ein Standort, der mit mandantenbasierten Netzwerksubnetzen und Standorten konfiguriert wurde, aber nicht für Location-Based Routing aktiviert ist.

- **Unbekannt** – Ein Standort, der nicht mithilfe von Mandantennetzwerksubnetzen und -standorten konfiguriert wurde. In der Regel sind solche Websites entweder intern im Unternehmensnetzwerk, aber nicht designbedingt nicht konfiguriert oder extern zum Unternehmensnetzwerk. In jedem Fall sind diese Websites nicht für Location-Based Routing aktiviert. 

### <a name="toll-bypass-evaluation-and-outcome"></a>Bewertung und Ergebnis der Gebührenumgehung

Wenn Location-Based Routing verwendet wird, wird ein Anruf zwischen einem Teams Benutzer und dem PSTN ausgewertet, um festzustellen, ob die gebührenpflichtige Umgehung eingeschränkt ist. Abhängig von den Ergebnissen wird der Anruf abgeschlossen oder nicht abgeschlossen. 

Wenn ein Benutzer für Location-Based Routing aktiviert ist und sich der Benutzer an einem Standort befindet, an dem Location-Based Routingeinschränkungen gelten, ist die gebührenpflichtige Umgehung für diesen Benutzer eingeschränkt. Teams anhand der folgenden Informationen ermitteln, ob die gebührenpflichtige Umgehung eingeschränkt ist: 

- Gibt an, ob der Teams Benutzer für Location-Based Routing aktiviert ist, wie in der Teams Anrufrichtlinie des Benutzers definiert.

- Die Teams Standort des Endpunktnetzwerks des Benutzers und ob der Standort für Location-Based Routing aktiviert oder nicht aktiviert ist.

- Der Standort des Netzwerkstandorts des PSTN-Gateways, das vom Anruf verwendet wird.

- Gibt an, ob das vom Anruf verwendete PSTN-Gateway für Location-Based Routing aktiviert wurde.

- Bei Übertragungsszenarien basiert die Route des PSTN-Anrufs auf den Routingeinstellungen der Person, die den Anruf übergibt, und auf den Location-Based Routingeinstellungen des Teams Benutzers, an den der Anruf weitergeleitet wird.  

- Für Konferenz- und Gruppenanrufszenarien, unabhängig davon, ob ein Teams Benutzer, für den die gebührenpflichtige Umgehung eingeschränkt ist, Teil des Anrufs ist oder war.

Wenn ein Anruf nicht abgeschlossen werden kann, wird der Teams Benutzer wie folgt benachrichtigt:

- Bei ausgehenden PSTN-Anrufen wird die folgende Meldung im Anruffenster angezeigt: Anruf aufgrund der Einstellungen Ihrer Organisation nicht zulässig.

- Bei eingehenden PSTN-Anrufen wird der Anruf basierend auf den anrufbeantworteten Einstellungen Teams Benutzers weitergeleitet, in der Regel an Voicemail. Wenn für den Teams Benutzer keine Einstellungen für unbeantwortete Anrufe konfiguriert sind, wird die Verbindung getrennt.

## <a name="apply-location-based-routing"></a>Anwenden Location-Based Routings

Sie müssen Location-Based Routing auf Folgendes anwenden:

- [Benutzer](#apply-location-based-routing-at-the-user-location)
- [Netzwerkstandorte](#apply-location-based-routing-at-the-network-site)
- [PSTN-Gateways](#apply-location-based-routing-at-the-pstn-gateway)

Beachten Sie die folgenden bewährten Methoden:

- Das dem Gateway zugeordnete PSTN-Gateway und der Netzwerkstandort müssen beide für Location-Based Routing aktiviert sein.

- Um Anrufe über ein PSTN-Gateway zu tätigen, das für Location-Based Routing aktiviert ist, müssen Benutzer auch für Location-Based Routing aktiviert sein.

- Damit Benutzer, die für Location-Based Routing aktiviert sind, ausgehende PSTN-Anrufe von einem unbekannten Netzwerkstandort tätigen können, muss Folgendes zutreffen:

  - Der Anruf muss von einem PSTN-Gateway ausgehend werden, das für Location-Based Routing aktiviert ist.
  - Das PSTN-Gateway muss mit dem Flag "GatewayLbrEnabledUserOverride" konfiguriert werden, das auf "True" festgelegt ist.


### <a name="apply-location-based-routing-at-the-user-location"></a>Anwenden Location-Based Routing am Benutzerstandort

Die Einschränkung der Gebührenumgehung steuert die Bedingungen, unter denen ein Benutzer PSTN-Anrufe tätigen und empfangen kann, und das PSTN-Gateway, das verwendet werden kann. 

Wenn ein Benutzer unter der Einschränkung der gebührenpflichtigen Umgehung steht, muss dieser Benutzer für Location-Based Routing aktiviert sein. Wenn sich der aktivierte Benutzer an einem Standort befindet, der für Location-Based Routing aktiviert ist, muss der Benutzer Anrufe über ein Gateway tätigen, das sowohl mit dem Standort verbunden als auch für Location-Based Routing aktiviert ist. 

Location-Based Routing funktioniert, indem der aktuelle Standort des Benutzers basierend auf der IP-Adresse des Teams Endpunkts des Benutzers ermittelt wird und die Regeln entsprechend angewendet werden. Der Speicherort eines Benutzers, der für Location-Based Routing aktiviert ist, kann wie folgt kategorisiert werden: 

- **Der Benutzer befindet sich an demselben Location-Based Routing-aktivierten Standort, der dem PSTN-Gateway zugeordnet ist, dem die DID zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer an einem konfigurierten Netzwerkstandort, der für Location-Based Routing aktiviert ist, und die DID-Nummer (Direct Inward Dial) des Benutzers wird auf einem PSTN-Gateway beendet, das sich am gleichen Netzwerkstandort befindet. Beispielsweise befindet sich der Benutzer in seiner Niederlassung. 

- **Der Benutzer befindet sich an einem anderen Location-Based Routing-aktivierten Standort, der nicht dem PSTN-Gateway zugeordnet ist, dem die DID zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer an einem konfigurierten Netzwerkstandort, der für Location-Based Routing aktiviert ist, und dieser Standort ist nicht dem PSTN-Gateway zugeordnet, dem die DID-Nummer des Benutzers zugewiesen ist. Beispielsweise reist der Benutzer in ein anderes Büro.  

- **Der Benutzer befindet sich an einem internen Standort, der nicht für Location-Based Routing aktiviert ist.** <br>In diesem Szenario befindet sich der Benutzer an einem konfigurierten Netzwerkstandort, der nicht für Location-Based Routing aktiviert ist. 

- **Der Benutzer befindet sich an einem unbekannten Standort.** 
    - Der Benutzer befindet sich innerhalb des internen Netzwerks, das nicht als Netzwerkstandort definiert ist. 
    - Der Benutzer befindet sich außerhalb des internen Netzwerks. So befindet sich der Benutzer beispielsweise zu Hause oder in einem Café im Internet. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Anwenden von Location-Based Routing am Netzwerkstandort 

Wenn Benutzer, die für Location-Based Routing aktiviert sind, Roaming verwenden, können Netzwerkstandorte, die für Location-Based Routing aktiviert sind, ermitteln, welche Gateways verwendet werden sollen. Zum Beispiel: 

- Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, zu einem Standort roamingt, der für Location-Based Routing aktiviert ist, kann nur das PSTN-Gateway, das für Location-Based Routing an diesem Standort aktiviert ist, für ausgehende Anrufe verwendet werden. 

- Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, zu einem Standort roamingt, der nicht für Location-Based Routing aktiviert ist, kann jedes Gateway, das nicht für Location-Based Routing aktiviert ist, für ausgehende Anrufe verwendet werden.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Anwenden von Location-Based Routing am PSTN-Gateway  

Um Location-Based Routing am PSTN-Gateway anzuwenden, müssen Sie die folgenden Schritte ausführen:

- Aktivieren Sie das Gateway für Location-Based Routing. (Die Gateways müssen für Location-Based Routing aktiviert sein, um sicherzustellen, dass sie nicht von Benutzern verwendet werden können, die nicht für Location-Based Routing aktiviert sind.)

- Weisen Sie dem Gateway einen Netzwerkstandort zu.

Das System ermittelt dann, ob ein bestimmter Benutzer an einem bestimmten Standort das Gateway verwenden darf. 

Wenn Sie gatewayLbrEnabledUserOverride auf "True" festlegen, können standortbasiertes Routing aktivierte Benutzer an unbekannten Standorten (z. B. Benutzer, die zu Hause arbeiten) ausgehende PSTN-Anrufe tätigen.


## <a name="restriction-rules"></a>Einschränkungsregeln

Einschränkungsregeln hängen davon ab, ob ein Teams Benutzer für Location-Based Routing aktiviert ist oder nicht.

### <a name="user-is-enabled-for-location-based-routing"></a>Der Benutzer ist für Location-Based Routing aktiviert.

Wenn ein Benutzer für Location-Based Routing aktiviert ist, gilt Folgendes:

- **Um einen ausgehenden PSTN-Anruf zu tätigen**, muss eine der folgenden Bedingungen erfüllt sein:

  - Der Endpunkt des Benutzers befindet sich an einem Standort, der für Location-Based Routing aktiviert ist, und ruft den Ausgang über ein PSTN-Gateway ab, das für Location-Based Routing am selben Standort aktiviert ist.  

  - Der Endpunkt des Benutzers befindet sich an einem unbekannten Standort und ruft den Ausgang über ein PSTN-Gateway ab, das für Location-Based Routing aktiviert ist. Das PSTN-Gateway ist mit dem GatewayLbrEnabledUserOverride-Parameter auf True konfiguriert.

  - Der Endpunkt des Benutzers befindet sich an einem Standort, der nicht für Location-Based Routing aktiviert ist, und ruft den Ausgang über ein PSTN-Gateway ab, das nicht für Location-Based Routing aktiviert ist.

- **Um einen eingehenden PSTN-Anruf zu empfangen**, muss eine der folgenden Bedingungen erfüllt sein: 

   - Der Endpunkt, über den der Benutzer antwortet, und das PSTN-Gateway, über das der Anruf einläuft, müssen sich am selben Standort befinden, der für Location-Based Routing aktiviert ist. Das PSTN-Gateway muss für Location-Based Routing aktiviert sein.

   - Der Antwortendpunkt des Benutzers und das PSTN-Gateway, über das der Anruf einläuft, müssen sich am selben Standort befinden, der nicht für Location-Based Routing aktiviert ist. Das PSTN-Gateway darf nicht für Location-Based Routing aktiviert sein.  (Dieses Szenario umfasst das erneute Weiterleiten des eingehenden PSTN-Anrufs an ein anderes PSTN-Gateway als das, das normalerweise für eingehende Anrufe an die Telefonnummer des Benutzers verwendet wird.)

   - In jedem anderen Szenario, z. B. beim Roaming des Benutzers, ist der Anruf nicht zulässig und wird an die Einstellungen für die Anrufweiterleitung (in der Regel Voicemail) des Benutzers weitergeleitet.  
   
- Beachten Sie für **einen 1:1-Teams VoIP-Anruf und die Übertragung an das PSTN** Folgendes:

  - Das Routing des Anrufs – d. h. welches PSTN-Gateway den Anruf ausgehend hat – basiert auf den Routingeinstellungen des Benutzers, der den Anruf übergibt.

  - Ob die Übertragung zulässig ist, hängt von folgenden Bedingungen ab:
  
    - Die Location-Based Routingeinstellungen des Benutzers, der den weitergeleiteten Anruf empfängt.
    - Der Standort des Endpunktnetzwerks.
    - Gibt an, ob der Speicherort für Location-Based Routing aktiviert ist.

    Die Übertragung ist zulässig, wenn der Benutzer, der den weitergeleiteten Anruf empfängt, diesen PSTN-Anruf am aktuellen Standort mit demselben PSTN-Gateway tätigen kann.

- **Für einen eingehenden oder ausgehenden PSTN-Anruf und die Übertragung an einen anderen Teams Benutzer** hängt davon ab, ob die Übertragung zulässig ist:

   - Die Routingeinstellungen des Benutzers, der den weitergeleiteten Anruf empfängt. 
   - Der Standort des Endpunktnetzwerks.
   - Gibt an, ob der Speicherort für Location-Based Routing aktiviert ist.

   Die Übertragung ist zulässig, wenn die Person, die den durchgestellten Anruf empfängt, diesen PSTN-Anruf an ihrem aktuellen Standort mithilfe des PSTN-Gateways tätigen oder empfangen kann, das vom laufenden PSTN-Anruf verwendet wird.


### <a name="user-is-not-enabled-for-location-based-routing"></a>Der Benutzer ist für Location-Based Routing nicht aktiviert.

Wenn ein Teams Benutzer nicht für Location-Based Routing aktiviert ist, müssen alle Anrufe an und von diesem Benutzer über ein PSTN-Gateway geleitet werden, das nicht für Location-Based Routing aktiviert ist. Ein eingehender Anruf an einen solchen Benutzer, der über ein PSTN-Gateway weitergeleitet wird, das für Location-Based Routing aktiviert ist, wird an die Einstellungen für die unbeantwortete Anrufweiterleitung (in der Regel Voicemail) des Benutzers weitergeleitet.

### <a name="decision-flows-for-inbound-and-outbound-calls"></a>Entscheidungsflüsse für eingehende und ausgehende Anrufe

Die folgenden Diagramme zeigen die Entscheidungsflüsse für eingehende und ausgehende Anrufe.

**Eingehende Anrufe**

![Diagramm mit LBR für eingehende Anrufe](media/lbr-routing-inbound1.png "Diagramm mit Szenarien für Location-Based Routing")

**Ausgehende Anrufe**

![Diagramm mit LBR für ausgehende Anrufe](media/lbr-routing-outbound1.png "Diagramm mit Szenarien für Location-Based Routing")


## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

In diesem Abschnitt werden verschiedene Szenarien zum Einschränken der gebührenpflichtigen Umgehung mithilfe von Location-Based Routing beschrieben. Die Szenarien vergleichen die Weiterleitung von Anrufen für Benutzer, die nicht für Location-Based Routing aktiviert sind, mit Benutzern, die für Location-Based Routing aktiviert sind.

- [Teams Benutzer gibt einen ausgehenden Anruf an das PSTN ab](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams Benutzer erhält einen eingehenden Anruf vom PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams Benutzer überträgt oder leitet einen Anruf an einen anderen Teams Benutzer weiter.](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams Benutzer überträgt oder leitet Anrufe an den PSTN-Endpunkt weiter](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Paralleles Anrufen](#simultaneous-ringing)
- [Delegierung](#delegation)

Das folgende Diagramm zeigt die Einschränkungen, die durch Location-Based Routing in jedem Szenario aktiviert sind. Benutzer, Netzwerkstandorte und Gateways, die für Location-Based Routing aktiviert sind, haben einen Rahmen um sie herum. Verwenden Sie das Diagramm als Leitfaden, um zu verstehen, wie Location-Based Routing in jedem Szenario funktioniert.  

![Diagramm mit Szenarien für Location-Based Routing.](media/lbr-direct-routing.png "Diagramm mit Szenarien für Location-Based Routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams Benutzer gibt einen ausgehenden Anruf an das PSTN ab

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Location-Based Routing nicht aktiviert

Ein Benutzer, der nicht für Location-Based Routing aktiviert ist, kann ausgehende Anrufe über ein beliebiges Gateway an einem beliebigen Standort tätigen, der nicht über die zugewiesene VoIP-Routingrichtlinie für Location-Based Routing aktiviert ist. Wenn ein Gateway jedoch für Location-Based Routing aktiviert ist, kann der Benutzer keine ausgehenden Anrufe über das Gateway tätigen, auch wenn es seiner VoIP-Routingrichtlinie zugewiesen ist. Wenn der Benutzer zu einem Standort roamingt, der für Location-Based Routing aktiviert ist, kann er nur Anrufe über seine normalen Routinggateways tätigen, die nicht für Location-Based Routing aktiviert sind.
 
#### <a name="user-enabled-for-location-based-routing"></a>Für Location-Based Routing aktivierter Benutzer

Im Vergleich dazu wird das Routing ausgehender Anrufe für Benutzer, die für Location-Based Routing aktiviert sind, vom Netzwerkstandort des Endpunkts des Benutzers beeinflusst. Die folgende Tabelle zeigt, wie sich Location-Based Routing abhängig vom Standort von User1 auf das Routing ausgehender Anrufe von User1 auswirkt. 

|Speicherort des Benutzer1-Endpunkts  |Routing ausgehender Anrufe für User1  |
|---------|---------|
|Dieselbe Website, der die DID des Benutzers zugewiesen ist, standortfähig für Location-Based Routing (Site1)      |Anruf, der über ein Gateway weitergeleitet wird, das für Location-Based Routing (GW1) bei Site1 aktiviert ist, basierend auf der VoIP-Routingrichtlinie des Benutzers         |
|Andere Website als die Stelle, an der die DID des Benutzers zugewiesen ist, Standort, der für Location-Based Routing aktiviert ist (Standort2)    |Anruf, der über ein Gateway weitergeleitet wird, das für Location-Based Routing (GW2) am Roamingstandort2 aktiviert ist, basierend auf der VoIP-Routingrichtlinie des Benutzers        |
|Andere Website als die DID des Benutzers, Website nicht für Location-Based Routing aktiviert (Site3)  |Anruf, der über ein Gateway weitergeleitet wird, das nicht für Location-Based Routing an einem Standort aktiviert ist, der nicht für Location-Based Routing (GW3) aktiviert ist, basierend auf der VoIP-Routingrichtlinie des Benutzers       |
|Unbekanntes internes Netzwerk (Standort4)    |  PSTN-Anrufe sind nicht zulässig, es sei denn, gatewayLbrEnabledUserOverride ist auf "True" festgelegt.       |
|Unbekanntes externes Netzwerk (Standort5)    | PSTN-Anrufe sind nicht zulässig, es sei denn, gatewayLbrEnabledUserOverride ist auf "True" festgelegt.       |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams Benutzer erhält einen eingehenden Anruf vom PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Location-Based Routing nicht aktiviert

Ein Benutzer, der nicht für Location-Based Routing aktiviert ist, kann einen eingehenden Anruf vom Gateway empfangen, der nicht für Location-Based Routing aktiviert ist, von dem die zugewiesene DID-Nummer eintrifft. Wenn der Benutzer zu einem Standort roamingt, der nicht für Location-Based Routing aktiviert ist, kann er weiterhin Anrufe über seine normalen PSTN-Gateways empfangen.
  
#### <a name="user-enabled-for-location-based-routing"></a>Für Location-Based Routing aktivierter Benutzer

Im Vergleich dazu können Benutzer, die für Location-Based Routing aktiviert sind, nur eingehende Anrufe vom PSTN-Gateway empfangen, dem ihre DID zugewiesen ist, wenn sie sich am selben Standort befinden. Die folgende Tabelle zeigt, wie User1 eingehende Anrufe empfängt, wenn User1 zu verschiedenen Netzwerkstandorten wechselt. Wenn der Anruf nicht an den Endpunkt des Benutzers weitergeleitet wird, wird er an die Unbeantworteten Anrufweiterleitungseinstellungen des Benutzers weitergeleitet, wenn die Einstellungen konfiguriert sind. In der Regel werden Anrufe an Voicemail weitergeleitet.  

|Speicherort des Benutzer1-Endpunkts  |Routing eingehender Anrufe an Benutzer1  |
|---------|---------|
|Dieselbe Website wie die Did-Funktion des Benutzers, Die Website ist für Location-Based Routing aktiviert (Standort1)   | Anrufe, die an den Endpunkt von User1 in Site1 weitergeleitet werden        |
|Andere Website als die Stelle, an der die DID des Benutzers zugewiesen ist, Standort, der für Location-Based Routing aktiviert ist (Standort2)    | Anrufe, die nicht an Endpunkte in Site2 weitergeleitet werden        |
|Andere Website als die DID des Benutzers, Website nicht für Location-Based Routing aktiviert (Site3)    | Anrufe, die nicht an Endpunkte in Site3 weitergeleitet werden        |
|Unbekanntes internes Netzwerk (Standort4)   | Anrufe, die nicht an Endpunkte in Position 4 weitergeleitet werden        |
|Unbekanntes externes Netzwerk (Standort5)     | Anrufe, die nicht an Endpunkte in Standort 5 weitergeleitet werden        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams Benutzer überträgt oder leitet einen Anruf an einen anderen Teams Benutzer weiter.

Wenn ein PSTN-Endpunkt beteiligt ist, analysiert Location-Based Routing, ob ein oder beide Benutzer für Location-Based Routing aktiviert sind, und bestimmt, ob der Anruf je nach Standort beider Endpunkte übertragen oder weitergeleitet werden soll. 
 
Die Anrufweiterleitung erfordert, dass der initiierende Benutzer den Anruf entgegennimmt, während die Anrufweiterleitung nicht erfordert, dass der erste Anruf angenommen wird. Anrufe können weitergeleitet werden, auch wenn Sich Benutzer1 nicht an einem Ort zum Empfangen eingehender Anrufe befindet (siehe die Tabelle in der [Teams Benutzer erhält einen eingehenden Anruf aus dem PSTN-Abschnitt](#teams-user-receives-an-inbound-call-from-the-pstn)) und Anrufe nicht durchgestellt werden können, wenn Benutzer1 den eingehenden Anruf nicht empfangen kann. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Location-Based Routing nicht aktiviert

Ein Benutzer, der nicht für Location-Based Routing aktiviert ist, kann PSTN-Anrufe an andere Benutzer weiterleiten, die nicht für Location-Based Routing aktiviert sind. Benutzer, die für Location-Based Routing aktiviert sind, befinden sich in der Regel gemeinsam an Location-Based Routing-aktivierten Gateways für PSTN-Anrufe. Benutzer, die nicht aktiviert sind, dürfen daher keinen PSTN-Anruf an einen Benutzer weiterleiten, der für Location-Based Routing aktiviert ist. Die Ausnahme ist, wenn ein benutzer mit Location-Based Routing ein Roaming zu einer Website durchläuft, die nicht für Location-Based Routing aktiviert ist. In diesem Szenario ist der durchgestellte Anruf zulässig.  

Ebenso kann ein Benutzer, der nicht für Location-Based Routing aktiviert ist, nur eine Übertragung oder einen weitergeleiteten PSTN-Anruf von einem anderen Benutzer erhalten, der nicht für Location-Based Routing aktiviert ist. 

#### <a name="user-enabled-for-location-based-routing"></a>Für Location-Based Routing aktivierter Benutzer

Das Übertragen und Weiterleiten eingehender PSTN-Anrufe von einem Gateway, das für Location-Based Routing aktiviert ist, ist nur zulässig, wenn der Zielbenutzer für Location-Based Routing aktiviert ist und sich am selben Standort befindet. Andernfalls ist das Durch- und Weiterleiten von Anrufen nicht zulässig. 

Die folgende Tabelle zeigt, ob Anrufweiterleitung und Anrufweiterleitung je nach Standort des Zielbenutzers zulässig sind. In dieser Tabelle initiiert Benutzer1, der sich in Site1 befindet, die Übertragung oder Weiterleitung an andere Teams Benutzer, die auch für Location-Based Routing aktiviert sind und sich an verschiedenen Standorten befinden.  

|Zielbenutzerendpunktspeicherort|User1 initiiert anrufweiterleitung |Benutzer1 initiiert anrufweiterleitung|
|---------|---------|---------|
|Gleicher Netzwerkstandort wie Initiator (User2)|Erlaubt|Erlaubt|
|Anderer Netzwerkstandort, Standort für Location-Based Routing aktiviert (Benutzer3)|Nicht zulässig|Nicht zulässig|
|Anderer Netzwerkstandort, Standort für Location-Based Routing nicht aktiviert (Benutzer4)|Nicht zulässig|Nicht zulässig|
|Unbekanntes internes Netzwerk (Benutzer5)| Nicht zulässig|Nicht zulässig|
|Unbekanntes externes Netzwerk (User6)| Nicht zulässig|Nicht zulässig|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams Benutzer überträgt oder leitet Anrufe an den PSTN-Endpunkt weiter

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Location-Based Routing nicht aktiviert

- Das Übertragen und Weiterleiten eines PSTN-Anrufs an eine andere PSTN-Nummer ist zulässig. 

- Beim Übertragen und Weiterleiten eines eingehenden VOIP-Anrufs an das PSTN müssen die Einschränkungen für die gebührenpflichtige Umgehung des Anrufers berücksichtigt werden. 

    - Wenn der Anrufer nicht für Location-Based Routing aktiviert ist, kann er an jedes PSTN-Gateway übertragen werden, das nicht für Location-Based Routing aktiviert ist.
    - Wenn der Anrufer für Location-Based Routing aktiviert ist, kann er nur an ein gateway mit aktiviertem Location-Based Routing übertragen werden, das sich am selben Netzwerkstandort befindet. 

#### <a name="user-enabled-for-location-based-routing"></a>Für Location-Based Routing aktivierter Benutzer

- Das Übertragen und Weiterleiten eingehender PSTN-Anrufe an eine andere PSTN-Nummer muss an dieselbe Location-Based Routing-aktivierten Gateway weitergeleitet werden, an das der eingehende Anruf eingegangen ist.

- Die Übertragung und Weiterleitung eines eingehenden VOIP-Anrufs an das PSTN muss sowohl den Anrufer als auch die Einschränkungen für die gebührenpflichtige Umgehung des Benutzers berücksichtigen. 

    - Wenn der Anrufer nicht für Location-Based Routing aktiviert ist, kann er an jedes PSTN-Gateway übertragen werden, das nicht für Location-Based Routing aktiviert ist.

    - Wenn der Anrufer für Location-Based Routing aktiviert ist, kann er nur an ein Location-Based Routing-aktiviertes Gateway übertragen werden, das sich am selben Netzwerkstandort befindet.
 
Die folgende Tabelle zeigt, wie sich Location-Based Routing auf das Routing eines VOIP-Anrufs von User1 an Standort1 an Benutzer an verschiedenen Standorten auswirkt, die den Anruf an einen PSTN-Endpunkt weiterleiten oder weiterleiten.  

|Benutzer initiiert Anrufdurchstellung oder Weiterleitung  |Übertragung in das PSTN  |Weiterleiten an das PSTN  |
|---------|---------|---------|
|Gleicher Netzwerkstandort, Standort für Location-Based Routing aktiviert (Benutzer2)   |Anrufweiterleitung kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User2         |Anrufweiterleitung kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User2         |
|Anderer Netzwerkstandort, Standort für Location-Based Routing aktiviert (Benutzer3)    |Anrufweiterleitung kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User3         |Die Anrufweiterleitung kann basierend auf der VoIP-Routingrichtlinie von User3 nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |
|Anderer Netzwerkstandort, Standort für Location-Based Routing nicht aktiviert (Benutzer4)    |Anrufweiterleitung kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User4         |Die Anrufweiterleitung kann basierend auf der VoIP-Routingrichtlinie von User4 nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |
|Unbekanntes internes Netzwerk (Benutzer5)     |Anrufweiterleitung kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User5         |Die Anrufweiterleitung kann basierend auf der VoIP-Routingrichtlinie von User5 nur über Location-Based Routing-aktiviertes Gateway1 bei Site1 weitergeleitet werden.         |
|Unbekanntes externes Netzwerk (User6)   |Anrufweiterleitung kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User6        |Die Anrufweiterleitung kann basierend auf der VoIP-Routingrichtlinie von User6 nur über Location-Based Routing-aktiviertes Gateway1 bei Site1 weitergeleitet werden.         |

### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, einen Anruf empfängt und gleichzeitiges Klingeln aktiviert ist, analysiert Location-Based Routing den Standort des Anrufers und die Endpunkte der aufgerufenen Parteien, um zu bestimmen, ob der Anruf weitergeleitet werden soll. Gleichzeitiges Klingeln folgt den gleichen Location-Based Regeln wie Anrufübertragungen und Weiterleitungen. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Gleichzeitiges Klingeln für einen anderen Teams Benutzer

Die folgende Tabelle zeigt, ob Location-Based Routing gleichzeitiges Klingeln an verschiedene Benutzer für einen eingehenden PSTN-Anruf für User1 zulässt.

|Zielbenutzerendpunktspeicherort|Gleichzeitiges Klingeln  |
|---------|---------|
|Gleicher Netzwerkstandort wie Initiator (User2)   |Erlaubt         |
|Unterschiedlicher roamingfähiger Netzwerkstandort für Location-Based Routing aktiviert (Benutzer3)   |Nicht zulässig         |
|Roamed network site not enabled for Location-Based Routing (User4)   |Nicht zulässig        |
|Unbekanntes internes Netzwerk (Benutzer5)    | Nicht zulässig        |
|Unbekanntes externes Netzwerk (User6)    |Nicht zulässig        |
|Zielbenutzer ist eine PSTN-Nummer    |Der Anruf kann nur über Location-Based Routing-aktiviertes Gateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User1.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Gleichzeitiges Klingeln an einem PSTN-Endpunkt

Die folgende Tabelle zeigt Location-Based Routingverhalten für einen eingehenden VoIP-Anruf von User1, der sich am Standort1 befindet, an Benutzer an unterschiedlichen Standorten mit gleichzeitigem Klingeln auf eine PSTN-Nummer festgelegt. 

|So genannte Position des Benutzerendpunkts  |Ziel für gleichzeitigen Ring ist PSTN-Endpunkt |
|---------|---------|
|Gleicher Netzwerkstandort, Standort für Location-Based Routing aktiviert (Benutzer2)    |Anruf kann nur über Location-Based Routinggateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User2       |
|Für Location-Based Routing aktivierter anderer Netzwerkstandort (Benutzer3)    |Anruf kann nur über Location-Based Routinggateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User3        |
|Unterschiedlicher Netzwerkstandort für Location-Based Routing nicht aktiviert (Benutzer4)    |Anruf kann nur über Location-Based Routinggateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User4         |
|Unbekanntes internes Netzwerk (Benutzer5)    |Anruf kann nur über Location-Based Routinggateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User5         |
|Unbekanntes externes Netzwerk (User6)   |Anruf kann nur über Location-Based Routinggateway1 an Standort1 weitergeleitet werden, basierend auf der VoIP-Routingrichtlinie von User6         |

#### <a name="inbound-calls-through-voice-apps-auto-attendant-or-call-queue"></a>Eingehende Anrufe über VoIP-Apps (automatische Telefonzentrale oder Anrufwarteschleife)

Eingehende PSTN-Anrufe von einem Location-Based Routing-aktivierten Gateways dürfen eine Verbindung mit einer automatischen Telefonzentrale oder Anrufwarteschleife herstellen. 

Benutzer, die für Location-Based Routing aktiviert sind, werden unterstützt, um eingehende Anrufübertragungen für diese Anwendungen zu empfangen, wenn sie sich am selben Standort befinden, von dem der eingehende PSTN-Anruf stammt.
 
Anrufweiterleitung und gleichzeitiges Klingeln an Benutzer und PSTN sind für VoIP-App-Übertragungen zulässig. Das Abschließen des Anrufs an das Ziel unterliegt den gleichen Location-Based zuvor aufgeführten Routingregeln.  
 
Die Weiterleitung an Voicemail ist ebenfalls zulässig.  

### <a name="delegation"></a>Delegierung

Ein Teams Benutzer kann Stellvertretungen auswählen, die Anrufe in ihrem Namen tätigen und empfangen können. Delegierungsfunktionen in Teams sind wie folgt von Location-Based Routing betroffen: 

- Für ausgehende Anrufe von einer Location-Based Routing-aktivierten Stellvertretung im Namen eines Delegators gelten die gleichen Regeln. Das Anrufrouting basiert auf der Anrufautorisierungsrichtlinie, der VoIP-Routingrichtlinie und dem Standort des Stellvertreters. Weitere Informationen finden Sie [unter Teams Benutzer einen ausgehenden Anruf an das PSTN durchführt](#teams-user-places-an-outbound-call-to-the-pstn). 

- Für eingehende PSTN-Anrufe an einen Delegator gelten dieselben Location-Based Routingregeln, die für die Anrufweiterleitung oder gleichzeitiges Anrufen an andere Benutzer gelten, auch für Stellvertretungen. Weitere Informationen finden Sie [unter Teams Benutzer Anrufe an einen anderen Teams Benutzer überträgt oder weiterleitet](#teams-user-transfers-or-forwards-call-to-another-teams-user), [Teams Benutzer Anrufe an den PSTN-Endpunkt überträgt oder weiterleitet](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) und [gleichzeitig klingelt](#simultaneous-ringing). Wenn ein Delegat einen PSTN-Endpunkt als Ziel für gleichzeitiges Anrufen festlegt, wird die VoIP-Routingrichtlinie des Delegaten verwendet, um den Anruf an das PSTN weiterzuleiten. 

- Für die Delegierung empfiehlt Microsoft, dass sich der Delegator und die zugehörigen Stellvertretungen am selben Netzwerkstandort befinden. 

## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Änderungen aus einer lokalen Location-Based Routingbereitstellung

Die VoIP-Routingrichtlinie für Netzwerkstandorte wird nicht mehr verwendet. Stattdessen verwenden wir die VoIP-Routingrichtlinie des Benutzers. Um Benutzern das Roaming zu anderen Websites zu ermöglichen, muss die VoIP-Routingrichtlinie die Gateways der Roamingwebsites enthalten. 

### <a name="technical-considerations-for-location-based-routing"></a>Technische Überlegungen zum standortbasierten Routing

IPv4- und IPv6-Subnetze werden unterstützt, IPv6 hat jedoch Vorrang bei der Suche nach einer Übereinstimmung.

### <a name="client-support-for-location-based-routing"></a>Clientunterstützung für Location-Based Routing

Die folgenden Teams Clients werden unterstützt:
- Teams Desktopclients (Windows und Mac)
- Teams mobile Clients (iOS und Android)
- Teams IP-Telefone

Der Teams-Webclient und Skype for Business-Clients werden nicht unterstützt.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Location-Based Routing gilt nicht für die folgenden Arten von Interaktionen. Location-Based Routing wird nicht erzwungen, wenn Teams Endpunkte in den folgenden Szenarien mit PSTN-Endpunkten interagieren: 

- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen 

- Ein lokaler Skype for Business Benutzer oder ein Skype for Business Onlinebenutzer ruft einen Teams Benutzer auf.  

### <a name="location-based-routing-for-conferencing"></a>Location-Based Routing für Konferenzen

Ein Location-Based Routing-aktivierter Benutzer bei einem PSTN-Anruf darf keine Konferenz mit einem anderen Benutzer oder einer anderen PSTN-Nummer starten. Eine Verbindung mit automatischen Telefonzentralen oder Anrufwarteschleifen ist zulässig.

Wenn der Benutzer über eine Audiokonferenzlizenz verfügt, muss der Benutzer eine Konferenz mit den relevanten Benutzern starten und das PSTN über die Konferenzbrücke anrufen, um eine Telefonkonferenz zu starten.

In einer Telefonkonferenz, die von einem Benutzer ohne Audiokonferenzlizenz gestartet wurde, ist das Hinzufügen von PSTN-Teilnehmern nicht zulässig, wenn mindestens ein benutzer mit aktiviertem Location-Based Routing in der Telefonkonferenz vorhanden ist oder war. Wenn mindestens ein PSTN-Teilnehmer an einer solchen Telefonkonferenz teilnimmt oder war, bevor teilnehmer mit aktiviertem Location-Based Routing zur Teilnahme am Anruf eingeladen wurden, können solche Location-Based Routing-aktivierte Teilnehmer dem Anruf nicht hinzugefügt werden.

Wenn der benutzer mit aktivierter Location-Based Routing an der Telefonkonferenz von einem internen Standort aus beitritt, der nicht für Location-Based Routing aktiviert ist, werden die Einschränkungen im vorstehenden Absatz nicht erzwungen. 

On-network conferencing for Audio Conferencing must NOT be deployed with any telephony equipment in India.


### <a name="media-bypass-requirement-for-location-based-routing"></a>Medienumgehungsanforderung für Location-Based Routing

Wenn Sie Location-Based Routing in Indien bereitstellen, ist es erforderlich, auch die Medienumgehung zu konfigurieren. Weitere Informationen finden Sie unter [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md) and [Local Media Optimization for Direct Routing](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Direct Voice over IP (VoIP) darf nicht mit Telefoniegeräten in Indien bereitgestellt werden.


## <a name="related-articles"></a>Verwandte Artikel

- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Netzwerkeinstellungen für Cloud voice features in Teams](cloud-voice-network-settings.md)
