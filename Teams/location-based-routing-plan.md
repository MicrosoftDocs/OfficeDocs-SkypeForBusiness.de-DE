---
title: Planen des standortbasierten Routings für direktes Routing
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Location-Based Für Direct-Routing planen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 12ff15e7bc322667464498aa166c5b0ca2066d9f82b2abf5ac15a2461f7ff504
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350907"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planen des standortbasierten Routings für direktes Routing

## <a name="overview-of-location-based-routing"></a>Übersicht über Location-Based Routing

In einigen Ländern und Regionen ist es ungesetzlich, den Anbieter des öffentlichen Telefonnetzwerks (PSTN) zu umgehen, um die Kosten für Anrufe im Ferngespräch zu senken. In diesem Artikel wird beschrieben, wie Sie Location-Based Routing verwenden, um die gebührenpflichtige Umgehung für Microsoft Teams basierend auf ihrem geografischen Standort einzuschränken. Dieser Artikel bezieht sich nur auf Telefonsystem Direct-Routing.

Hier erhalten Sie einen Überblick über Location-Based Routing und Anleitungen, die Sie bei der Planung unterstützen. Wenn Sie bereit sind, Ihr Routing anzuwenden und zu aktivierenLocation-Based finden Sie weitere Informationen unter:

- [Bereitstellen von Netzwerkeinstellungen für Location-Based Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

> [!NOTE]
> Location-Based Routing ist in Bereitstellungen mit hohen Microsoft 365 Government Community Cloud (GCC) oder DoD nicht verfügbar.

Location-Based Routing ist ein Feature, mit dem Sie die gebührenpflichtige Umgehung basierend auf der Richtlinie und dem geografischen Standort des Benutzers zum Zeitpunkt eines eingehenden oder ausgehenden PSTN-Anrufs einschränken können. Location-Based Routing soll einen Mechanismus zur Verhinderung einer gebührenfreien Umgehung bereitstellen. Es sollte nicht als Mechanismus verwendet werden, um PSTN-Anrufe dynamisch basierend auf der Position des Benutzers weiter zu routen, da unbeabsichtigte Folgen folgen können.

Wenn ein Teams für sein Routing aktiviert Location-Based, gilt Folgendes:

- Um einen ausgehenden PSTN-Anruf zu erstellen, muss eine der folgenden Bedingungen zutreffen:
    - Der Endpunkt des Benutzers befindet sich auf einer Netzwerkwebsite, die für Location-Based-Routing aktiviert ist und Anrufe über das entsprechende Gateway geleitet werden, das für das Routing Location-Based ist. 
    - Der Endpunkt des Benutzers befindet sich auf einer Netzwerkwebsite, die nicht für Location-Based-Routing und Anrufe über ein Gateway, das nicht für das Routing aktiviert ist, Location-Based ist.

    Ausgehende Anrufe sind in keinem anderen Szenario zulässig.

- Um einen eingehenden PSTN-Anruf zu empfangen, muss sich der Endpunkt für den Anrufbeantwortung des Benutzers an demselben Netzwerkstandort befinden, an dem der Anruf über das Gateway geht, das für das Routing Location-Based ist. In anderen Szenarien, z. B. wenn der Benutzer Roaming verwendet, ist der Anruf nicht zulässig und wird an die Anruf weiterleitungseinstellungen (in der Regel Voicemail) weitergeleitet.
- Um einen PSTN-Anruf an einen anderen Teams-Benutzer zu übertragen, muss sich der Endpunkt des Zielbenutzers auf derselben Netzwerkwebsite wie der Benutzer befinden, der die Übertragung initiiert. Übertragungen sind in keinem anderen Szenario zulässig. 
- Um einen anderen Teams-Benutzer an das PSTN zu übertragen, muss der Anruf über ein Location-Based Routingfähiges Gateway übertragen werden, das sich an derselben Netzwerkwebsite wie der ursprüngliche Anrufer befindet. Übertragungen sind in keinem anderen Szenario zulässig.

Location-Based Routing verwendet die gleichen Netzwerkregion-, Standort- und Subnetzdefinitionen, die Skype for Business Server verwendet. Wenn die gebührenpflichtige Umgehung für einen Standort eingeschränkt ist, ordnet ein Administrator jedes IP-Subnetz und jedes PSTN-Gateway für den jeweiligen Speicherort einem Netzwerkstandort zu. Die Position eines Benutzers wird durch das IP-Subnetz bestimmt, mit dem die Teams-Endpunkte des Benutzers zum Zeitpunkt eines PSTN-Anrufs verbunden sind. Ein Benutzer kann über mehrere Teams-Clients verfügen, die sich an unterschiedlichen Standorten befinden. In diesem Fall erzwingt Location-Based Routing das Routing jedes Clients unabhängig vom Standort seines Endpunkts. 

Wenn Sie sich mit der in diesem Artikel verwendeten Netzwerkterminologie vertraut machen möchten, lesen Sie Netzwerkeinstellungen für [Cloud-Sprachfeatures in Teams.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Anwenden Location-Based Routings

Sie müssen ein Location-Based auf Benutzer, Netzwerkwebsites und PSTN-Gateways anwenden.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Anwenden Location-Based Routing an den Benutzerstandort

Wie bereits erwähnt, Location-Based Das Routing nur für Benutzer gilt, die für Direct-Routing eingerichtet sind. Location-Based Routing gilt nicht für Benutzer, die für den Anrufplan eingerichtet sind. Benutzer müssen für Location-Based-Routing aktiviert sein, wenn sie die Einschränkung zur Umgehung der gebührenpflichtigen Umgehung erfüllen. Dies steuert die Bedingungen, unter denen sie PSTN-Anrufe und das PSTN-Gateway, das verwendet werden kann, anrufen und empfangen kann. Wenn sich ein Benutzer, der für Location-Based-Routing aktiviert ist, an einer Website befindet, die für Location-Based Routing aktiviert ist, muss er Anrufe über ein mit der Website verbundenes Location-Based Routing-aktiviertes Gateway in Verbindung mit der Website erstellen. 

Location-Based Routing ermittelt anhand der IP-Adresse des Teams-Endpunkts des Benutzers die aktuelle Position des Benutzers und wendet die Regeln entsprechend an. Die Position eines Benutzers, der für das Routing aktiviert Location-Based, kann wie folgt kategorisiert werden: 
- **Der Benutzer befindet sich an derselben Location-Based Routing aktivierten Website, die dem PSTN-Gateway zugeordnet ist, dem seine DID-Adresse zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer auf einer bekannten Netzwerkwebsite, die für Location-Based-Routing aktiviert ist, und die Did-Nummer des Benutzers mit direkt nach innen gerichteter Dial-Nummer (Direct Inward Dial, DID) wird auf einem PSTN-Gateway beendet, das sich an demselben Netzwerkstandort befindet. Beispielsweise befindet sich der Benutzer im Büro des Benutzers. 
- **Der Benutzer befindet sich an einem anderen Ort Location-Based Routing aktiviert ist und nicht mit dem PSTN-Gateway verknüpft ist, dem seine DID-Adresse zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer auf einer bekannten Netzwerkwebsite, die für Location-Based-Routing aktiviert ist, und diese Website ist nicht mit dem PSTN-Gateway verknüpft, dem die DID-Nummer des Benutzers zugewiesen ist. Der Benutzer reist beispielsweise in ein anderes Büro.  
- **Der Benutzer befindet sich an einer internen Website, die nicht für das Routing Location-Based ist.** <br>In diesem Szenario befindet sich der Benutzer auf einer bekannten internen Netzwerkwebsite, die nicht für das Routing Location-Based ist. 
- **Der Benutzer befindet sich an einer unbekannten Website.** 
    - Der Benutzer befindet sich in dem internen Netzwerk, das nicht als Netzwerkwebsite definiert ist. 
    - Der Benutzer befindet sich außerhalb des internen Netzwerks. Beispielsweise befindet sich der Benutzer zu Hause oder in einem Café im Internet. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Anwenden Location-Based Routings am Netzwerkstandort 
Netzwerkwebsites müssen für das Routing aktiviert Location-Based sein, um zu ermitteln, welche Gateways beim Roaming Location-Based Routing aktiviert sind. Wenn ein Benutzer, der für Location-Based-Routing aktiviert ist, ein Roaming zu einer Website verwendet, die für Location-Based-Routing aktiviert ist, kann nur das PSTN-Gateway, das für Location-Based-Routing an diesem Standort aktiviert ist, für ausgehende Anrufe verwendet werden. Wenn ein Benutzer, der für Location-Based-Routing aktiviert ist, ein Roaming zu einer Website verwendet, die nicht für Location-Based-Routing aktiviert ist, kann jedes Gateway, das nicht für Location-Based-Routing aktiviert ist, für ausgehende Anrufe verwendet werden.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Anwenden Location-Based Routings am PSTN-Gateway 

Gateways sind Websites zugeordnet, um zu bestimmen, wo sich ein benutzer, der für das Routing Location-Based befindet, wenn er einen PSTN-Anruf anruft oder erhält. Gateways müssen für das Location-Based-Routing aktiviert sein, um sicherzustellen, dass es unter den Einschränkungen der gebührenpflichtigen Umgehung steht und nicht von Benutzern verwendet werden kann, die nicht für das Routing Location-Based können. Das gleiche Gateway kann mehreren Websites zugeordnet sein, und es kann je nach Website so konfiguriert werden, dass es für Location-Based Routing aktiviert oder nicht für Location-Based Routing aktiviert ist.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

In diesem Abschnitt werden verschiedene Szenarien zum Einschränken der gebührenpflichtigen Umgehung mithilfe von Location-Based Routing beschrieben und verglichen, wie Anrufe für Benutzer, die nicht für Location-Based-Routing aktiviert sind, mit Benutzern, die für das Routing aktiviert sind, Location-Based werden.

- [Teams Benutzer einen ausgehenden Anruf an das PSTN ab](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams benutzer empfängt einen eingehenden Anruf aus dem PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams durch Übertragungen oder Weiterleitungen einen Anruf an einen anderen Benutzer Teams weiterleiten](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams der Benutzerübertragungen oder Weiterleitungen des Anrufs an den PSTN-Endpunkt](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Paralleles Anrufen](#simultaneous-ringing)
- [Delegierung](#delegation)

Das folgende Diagramm zeigt die Einschränkungen, die das Routing in Location-Based Szenario ermöglicht. Benutzer, Netzwerkwebsites und Gateways, die für Location-Based Routing aktiviert sind, sind von einem Rahmen umrandt. Verwenden Sie das Diagramm als Leitfaden, um zu verstehen, wie Location-Based Routing in den einzelnen Szenarien funktioniert.  

![Diagramm mit Szenarien für Location-Based Routing](media/lbr-direct-routing.png "Diagramm mit Szenarien für Location-Based Routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams Benutzer einen ausgehenden Anruf an das PSTN ab

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Routing nicht Location-Based aktiviert

Ein Benutzer, der für Location-Based-Routing nicht aktiviert ist, kann ausgehende Anrufe über ein beliebiges Gateway an einem beliebigen Ort, der nicht für Location-Based-Routing über ihre zugewiesene Voice routing-Richtlinie aktiviert ist, erstellen. Wenn ein Gateway jedoch für das Routing Location-Based aktiviert ist, kann der Benutzer keine ausgehenden Anrufe über das Gateway erstellen, auch nicht, wenn es seiner Voiceroutingrichtlinie zugewiesen ist. Wenn der Benutzer das Roaming zu einer Website verwendet, die für Location-Based-Routing aktiviert ist, kann er Anrufe nur über ihre normalen Routinggateways, die nicht für das Routing aktiviert sind, Location-Based verwenden.
 
#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter Location-Based Routing
Im Vergleich dazu ist das Routing ausgehender Anrufe für Benutzer, die für Location-Based Routing aktiviert sind, von der Netzwerkposition des Endpunkts des Benutzers betroffen. Die folgende Tabelle zeigt, Location-Based Routing sich abhängig vom Standort von Benutzer1 auf das Routing ausgehender Anrufe von Benutzer1 auswirkt. 

|Endpunktposition für Benutzer1  |Routing ausgehender Anrufe für Benutzer1  |
|---------|---------|
|Dieselbe Website, der die DID-Adresse des Benutzers zugewiesen ist, die Website ist für Location-Based (Site1) aktiviert      |Anruf, der über ein Gateway umgeschaltet wurde, das für Location-Based Routing (GW1) bei Site1 aktiviert ist, basierend auf der Sprachroutingrichtlinie des Benutzers         |
|Eine andere Website als die, der die DID-Adresse des Benutzers zugewiesen ist, ist die Website für Location-Based (Site2) aktiviert    |Anruf, der über ein Gateway umgeschaltet wurde, das für Location-Based Routing (GW2) bei Roam Site2 aktiviert ist, basierend auf der Sprachroutingrichtlinie des Benutzers        |
|Eine andere Website als die, der die DID-Adresse des Benutzers zugewiesen ist, die Website ist nicht für Location-Based (Site3) aktiviert  |Anruf, der über ein Gateway, das für Location-Based-Routing am Standort nicht aktiviert ist und nicht für Location-Based-Routing (GW3) aktiviert ist, basierend auf der Sprachroutingrichtlinie des Benutzers       |
|Unbekanntes internes Netzwerk (Standort4)    |  Anrufe über das Festnetz sind nicht zulässig       |
|Unbekanntes externes Netzwerk (Standort5)    | Anrufe über das Festnetz sind nicht zulässig        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams benutzer empfängt einen eingehenden Anruf aus dem PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Routing nicht Location-Based aktiviert

Ein Benutzer, der nicht für Location-Based-Routing aktiviert ist, kann einen eingehenden Anruf vom Gateway empfangen, der nicht für Location-Based Routing aktiviert ist, von dem aus die zugewiesenen DID-Nummernresse empfangen werden. Wenn der Benutzer das Roaming zu einer Website vorn ermöglicht, die nicht für Location-Based-Routing aktiviert ist, kann er weiterhin Anrufe über seine normalen PSTN-Gateways empfangen.
  
#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter Location-Based Routing

Im Vergleich dazu können Benutzer, die für Location-Based Routing aktiviert sind, nur eingehende Anrufe von dem PSTN-Gateway empfangen, dem ihre DID-Adresse zugewiesen ist, wenn sie sich am gleichen Standort befinden. Die folgende Tabelle zeigt, wie Benutzer1 eingehende Anrufe empfängt, wenn Benutzer1 zu verschiedenen Netzwerkstandorten wechselt. Wenn der Anruf nicht an den Endpunkt des Benutzers weitergeleitet wird, wird er zu den Anruf weiterleitungseinstellungen des Benutzers weitergeleitet, sofern die Einstellungen konfiguriert sind. In der Regel handelt es sich dabei um Voicemail.  

|Endpunktposition für Benutzer1  |Routing eingehender Anrufe an Benutzer1  |
|---------|---------|
|Dieselbe Website wie die, der die DID-Adresse des Benutzers zugewiesen ist, die Website ist für Location-Based (Site1) aktiviert   | Anrufe, die an den Endpunkt von Benutzer1 in Site1 geleitet werden        |
|Eine andere Website als die, der die DID-Adresse des Benutzers zugewiesen ist, ist die Website für Location-Based (Site2) aktiviert    | Anrufe werden nicht an Endpunkte in Site2 geleitet        |
|Eine andere Website als die, der die DID-Adresse des Benutzers zugewiesen ist, die Website ist nicht für Location-Based (Site3) aktiviert    | Anrufe, die nicht an Endpunkte in Site3 geleitet werden        |
|Unbekanntes internes Netzwerk (Standort4)   | Anrufe, die nicht an Endpunkte in Location4 geleitet werden        |
|Unbekanntes externes Netzwerk (Standort5)     | Anrufe, die nicht an Endpunkte in Location5 geleitet werden        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams durch Übertragungen oder Weiterleitungen einen Anruf an einen anderen Benutzer Teams weiterleiten

Wenn ein PSTN-Endpunkt involviert ist, analysiert Location-Based-Routing, ob ein oder beide Benutzer für Location-Based-Routing aktiviert sind, und ermittelt abhängig vom Standort beider Endpunkte, ob der Anruf weitergeleitet oder weitergeleitet werden soll. 
 
Bei der Anrufübertragung muss der initiierte Benutzer den Anruf abholen, während für die Anruf weiterleitung kein erst einmal ein Anruf beantwortet werden muss. Dies bedeutet, dass Anrufe weitergeleitet werden können, auch wenn Benutzer1 sich nicht an einem Ort befindet, an dem er eingehende Anrufe empfangen kann (siehe die Tabelle im Abschnitt Teams der Benutzer empfängt einen eingehenden Anruf aus dem [PSTN-Abschnitt)](#teams-user-receives-an-inbound-call-from-the-pstn) und Anrufe nicht übertragen werden können, wenn Benutzer1 den eingehenden Anruf nicht empfangen kann. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Routing nicht Location-Based aktiviert

Ein Benutzer, der nicht für die Location-Based-Routing aktiviert ist, kann PSTN-Anrufe an andere Benutzer, die nicht für das Routing aktiviert sind, Location-Based weiterleiten. Benutzer dürfen einen PSTN-Anruf normalerweise nicht an einen Benutzer weiterleiten, der für Location-Based-Routing aktiviert ist, da benutzer mit aktivierter Location-Based-Routing-Funktion normalerweise nur an Location-Based-fähigen Gateways für PSTN-Anrufe gemeinsam an einem anderen Standort sein dürfen. Die Ausnahme ist, wenn Location-Based Routing aktivierten Benutzer zu einer Website weiterleiten, die nicht für das Routing Location-Based ist. In diesem Szenario ist der übertragene Anruf zulässig.  

Ebenso kann ein Benutzer, der nicht für Location-Based-Routing aktiviert ist, nur einen Transfer- oder weitergeleiteten PSTN-Anruf von einem anderen Benutzer erhalten, der nicht für Location-Based ist. 

#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter Location-Based Routing

Im Allgemeinen ist das Übertragen und Weiterleiten eingehender PSTN-Anrufe von einem Gateway, das für Location-Based-Routing aktiviert ist, nur zulässig, wenn der Zielbenutzer für das Location-Based-Routing aktiviert ist und sich an demselben Standort befindet. Andernfalls sind Durch- und Weiterleitung von Anrufen nicht zulässig. 

In der folgenden Tabelle ist abhängig vom Standort des Zielbenutzers aufgeführt, ob Anrufanrufe und Anrufübertragungen zulässig sind. In dieser Tabelle initiiert Benutzer1 (auf Website1) die Übertragung oder Weiterleitung an andere Teams-Benutzer, die ebenfalls für Location-Based-Routing aktiviert sind und sich an unterschiedlichen Standorten befinden.  

|Zielbenutzerendpunktposition|Benutzer1 initiiert die Anrufübertragung |Benutzer1 initiiert die Anruf weiterleitung|
|---------|---------|---------|
|Dieselbe Netzwerkwebsite wie Eine (Benutzer2)|Zugelassen|Zugelassen|
|Verschiedene Netzwerkwebsite, Standort aktiviert für Location-Based Routing (Benutzer3)|Nicht zulässig|Nicht zulässig|
|Verschiedene Netzwerkwebsite, Website nicht aktiviert für Location-Based Routing (Benutzer4)|Nicht zulässig|Nicht zulässig|
|Unbekanntes internes Netzwerk (Benutzer5)| Nicht zulässig|Nicht zulässig|
|Unbekanntes externes Netzwerk (Benutzer6)| Nicht zulässig|Nicht zulässig|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams der Benutzerübertragungen oder Weiterleitungen des Anrufs an den PSTN-Endpunkt

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für Routing nicht Location-Based aktiviert

- Das Übertragen und Weiterleiten eines PSTN-Anrufs an eine andere PSTN-Nummer ist zulässig. 
- Bei der Übertragung und Weiterleitung eines eingehenden VOIP-Anrufs an das PSTN müssen die gebührenpflichtigen Umgehungseinschränkungen des Anrufers berücksichtigt werden. 
    - Wenn der Anrufer für das Location-Based-Routing nicht aktiviert ist, können sie an ein beliebiges PSTN-Gateway übertragen werden, das nicht für das Routing Location-Based ist.
    - Wenn der Anrufer für das Location-Based-Routing aktiviert ist, können sie nur an ein Location-Based Routing-aktiviertes Gateway übertragen werden, das sich an demselben Netzwerkstandort befindet. 

#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter Location-Based Routing

- Durch Durch übertragen und Weiterleiten eines PSTN-Anrufs an eine andere PSTN-Nummer muss das gleiche Location-Based-fähiges Gateway, zu dem der eingehende Anruf eintroffen ist, weitergeleitet werden. 
- Bei der Übertragung und Weiterleitung eines eingehenden VOIP-Anrufs an das PSTN müssen sowohl der Anrufer als auch die gebührenfreien Umgehungseinschränkungen des Benutzers berücksichtigt werden. 
    - Wenn der Anrufer für das Location-Based-Routing nicht aktiviert ist, können sie an ein beliebiges PSTN-Gateway übertragen werden, das nicht für das Routing Location-Based ist.
    - Wenn der Anrufer für das Location-Based-Routing aktiviert ist, können sie nur an ein am selben Netzwerkstandort Location-Based Routingfähiges Gateway übertragen werden.
 
Die folgende Tabelle zeigt, Location-Based sich das Routing auf das Routing eines VOIP-Anrufs von Benutzer1 an Standort1 an Benutzer an unterschiedlichen Standorten auswirkt, die den Anruf an einen PSTN-Endpunkt durchstellen oder weiterleiten.  

|Benutzer initiiert Anrufübertragung oder Weiterleitung  |Übertragen in das PSTN  |Weiterleiten an PSTN  |
|---------|---------|---------|
|Gleiche Netzwerkwebsite, Website für Location-Based Routing aktiviert (Benutzer2)   |Die Anrufübertragung kann nur über das routingfähige Location-Based Gateway1 an Standort1, basierend auf der Voice Routingrichtlinie von Benutzer2, geroutet werden.         |Die Anruf weiterleiten kann nur über das Location-Based Routing aktiviertes Gateway1 an Standort1, basierend auf der Voice Routingrichtlinie von Benutzer2         |
|Verschiedene Netzwerkwebsite, Standort aktiviert für Location-Based Routing (Benutzer3)    |Die Anrufübertragung kann basierend auf der Voice Routing-Richtlinie von Benutzer3 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.         |Die Anruf weiterleiten kann nur über Location-Based Routing aktiviertes Gateway1 an Standort1, basierend auf der Voice Routing-Richtlinie von Benutzer3         |
|Verschiedene Netzwerkwebsite, Website nicht aktiviert für Location-Based Routing (Benutzer4)    |Die Anrufübertragung kann basierend auf der Voice Routing-Richtlinie von Benutzer4 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.         |Die Anruf weiterleiten kann nur über Location-Based Routing aktiviertes Gateway1 an Standort1, basierend auf der Voice Routing-Richtlinie von Benutzer4         |
|Unbekanntes internes Netzwerk (Benutzer5)     |Die Anrufübertragung kann basierend auf der Voice Routing-Richtlinie von Benutzer5 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.         |Die Anruf weiterleiten kann nur über Location-Based Routing aktiviertes Gateway1 an Standort1, basierend auf der Voice Routing-Richtlinie von Benutzer5         |
|Unbekanntes externes Netzwerk (Benutzer6)   |Die Anrufübertragung kann basierend auf der Voice Routing-Richtlinie von Benutzer6 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.        |Die Anruf weiterleiten kann nur über Location-Based Routing aktiviertes Gateway1 an Standort1, basierend auf der Voice Routing-Richtlinie von Benutzer6         |

### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn ein Benutzer, der für Location-Based-Routing einen Anruf empfängt und gleichzeitiges Klingeln aktiviert ist, analysiert Location-Based Routing die Position der anrufenden Partei und die Endpunkte der angerufenen Parteien, um zu bestimmen, ob der Anruf geleitet werden soll. Das gleichzeitige Klingeln folgt Location-Based Regeln wie Anrufübertragungen und Weiterleitungen. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Gleichzeitiges Klingeln für einen Teams Benutzer

Die folgende Tabelle zeigt, Location-Based Routing gleichzeitiges Klingeln bei verschiedenen Benutzern für einen eingehenden PSTN-Anruf für Benutzer1 zulässt.

|Zielbenutzerendpunktposition|Gleichzeitiges Klingeln  |
|---------|---------|
|Dieselbe Netzwerkwebsite wie Eine (Benutzer2)   |Zugelassen         |
|Verschiedene für das Routing aktivierte Netzwerkwebsites mit Location-Based (Benutzer3)   |Nicht zulässig         |
|Für das Routing von Netzwerkwebsites nicht aktiviertes Location-Based (Benutzer4)   |Nicht zulässig        |
|Unbekanntes internes Netzwerk (Benutzer5)    | Nicht zulässig        |
|Unbekanntes externes Netzwerk (Benutzer6)    |Nicht zulässig        |
|Zielbenutzer ist eine PSTN-Nummer.    |Der Anruf kann basierend auf der Voice routing policy von Benutzer1 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Gleichzeitiges Klingeln an einem PSTN-Endpunkt

Die folgende Tabelle zeigt Location-Based Routingverhalten für einen eingehenden VOIP-Anruf von Benutzer1 an Standort1 zu Benutzern an unterschiedlichen Standorten, bei dem gleichzeitiges Anrufen auf eine PSTN-Nummer festgelegt ist. 

|Ort des so genannten Benutzerendpunkts  |Gleichzeitiges Ringziel ist PSTN-Endpunkt |
|---------|---------|
|Gleiche Netzwerkwebsite, Website für Location-Based Routing aktiviert (Benutzer2)    |Anrufe können nur über das Routinggateway1 Location-Based Standort1, basierend auf der Voiceroutingrichtlinie von Benutzer2, geroutet werden       |
|Unterschiedliche Netzwerkwebsite, die für Location-Based Routing aktiviert ist (Benutzer3)    |Der Anruf kann basierend auf der Voice Routing-Richtlinie von Benutzer3 nur über Location-Based Routinggateway1 an Standort1 geroutet werden.        |
|Unterschiedliche Netzwerkwebsite, die nicht für die Location-Based aktiviert ist (Benutzer4)    |Anruf kann nur basierend auf der Voice Routing-Richtlinie von Benutzer4 über Location-Based Routinggateway1 an Ort1 geroutet werden         |
|Unbekanntes internes Netzwerk (Benutzer5)    |Anruf kann nur über das Routinggateway1 Location-Based Standort1 routing, basierend auf der Voice Routing-Richtlinie von Benutzer5         |
|Unbekanntes externes Netzwerk (Benutzer6)   |Anrufe können nur über das Routinggateway1 Location-Based Standort1, basierend auf der Voiceroutingrichtlinie von Benutzer6, geroutet werden.         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Eingehende Anrufe über die Sprach-App (automatische Telefonzentrale Anrufwarteschleife)

Eingehende PSTN-Anrufe von einem Location-Based Routing-aktivierten Gateway dürfen eine Verbindung mit einer automatischen Telefon attendant oder Anrufwarteschleife herstellen. Benutzer, die für Location-Based Routing aktiviert sind, können eingehende Anrufübertragungen von diesen Anwendungen nur empfangen, wenn sie sich an demselben Standort befinden, von dem der eingehende PSTN-Anruf stammt. 
 
Anruf weiterleiten und gleichzeitiges Klingeln bei Benutzern und PSTN ist für Sprach-App-Übertragungen zulässig. Das Abschließen des Aufrufs an das Ziel unterliegt den gleichen Regeln, Location-Based weiter oben aufgeführt sind.  
 
Weiterleitung an Voicemail ist ebenfalls zulässig.  

### <a name="delegation"></a>Delegierung

Ein Teams kann Stellvertretung auswählen, die in ihrem Namen Anrufe erstellen und empfangen kann. Delegierungsfunktionen in Teams sind von der Location-Based wie folgt betroffen: 
- Für ausgehende Anrufe von einer Location-Based Routing-aktivierten Stellvertretung im Auftrag eines Delegators gelten die gleichen Regeln. Die Anrufrouting-Richtlinie basiert auf der Anrufautorisierungsrichtlinie, der Sprachroutingrichtlinie und dem Standort der Stellvertretung. Weitere Informationen finden Sie unter Teams [einen ausgehenden Anruf bei der PSTN-Datei.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Für eingehende PSTN-Anrufe an einen Delegator gelten für Stellvertretung die gleichen Location-Based-Routingregeln, die für die Anrufleitung oder für gleichzeitiges Klingeln bei anderen Benutzern gelten. Weitere Informationen finden Sie unter Teams durch Übertragungen oder Weiterleitungen eines [Anrufs](#teams-user-transfers-or-forwards-call-to-another-teams-user)an einen anderen Teams-Benutzer, [](#simultaneous-ringing)Teams-Benutzerübertragungen oder -Weiterleitungen -Anruf an den [PSTN-Endpunkt](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)und Gleichzeitiges Klingeln. Wenn ein Stellvertreter einen PSTN-Endpunkt als Ziel für gleichzeitiges Anrufen legt, wird die Voiceroutingrichtlinie des Stellvertretungs verwendet, um den Anruf an das PSTN weiter zu weiterleiten. 
- Für Delegierung wird empfohlen, dass sich der Delegator und die zugehörigen Stellvertretung auf derselben Netzwerkwebsite befinden. 

## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Änderungen von einer lokalen Bereitstellung Location-Based Routingbereitstellung

Die Voiceroutingrichtlinie für Netzwerkwebsites wird nicht mehr verwendet. Stattdessen verwenden wir die Voice Routing-Richtlinie des Benutzers. Dies bedeutet, dass die Sprachroutingrichtlinie die Gateways der Serverwebsites enthalten muss, damit Benutzer das Roamen zu anderen Websites zulassen können. 

### <a name="technical-considerations-for-location-based-routing"></a>Technische Überlegungen zum standortbasierten Routing

IPv4- und IPv6-Subnetze werden unterstützt, aber IPv6 hat Vorrang, wenn auf eine Übereinstimmung überprüft wird.

### <a name="client-support-for-location-based-routing"></a>Clientunterstützung für Location-Based Routing

Die folgenden Teams Clients werden unterstützt:
- Teams-Desktopclients (Windows und Mac)
- Teams mobilen Clients (iOS und Android)
- Teams IP-Telefone

Der Teams Webclient und Skype for Business-Clients werden nicht unterstützt.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Location-Based Routing gilt nicht für die folgenden Interaktionstypen. Location-Based Routing wird nicht erzwungen, wenn Teams Endpunkte in den folgenden Szenarien mit PSTN-Endpunkten interagieren: 
- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen 
- Ein lokales Skype for Business oder ein Skype for Business Online-Benutzer ruft einen Teams an  

### <a name="location-based-routing-for-conferencing"></a>Location-Based Routing für Konferenzen

Einem Location-Based bei einem PSTN-Anruf ist es nicht gestattet, eine Konferenz mit einem anderen Benutzer oder einer PSTN-Nummer zu starten. Verbindungen mit automatischen Telefonkonferenzen oder Anrufwarteschleifen sind zulässig. Wenn der Benutzer über eine Konferenzlizenz verfügt, muss er eine Konferenz mit den entsprechenden Benutzern starten und das PSTN über die Konferenzbrücke anrufen, um eine Telefonkonferenz zu beginnen.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Anforderung zur Medienumgehung für Location-Based Routing

Wenn Sie Ihr Routing in Location-Based bereitstellen, ist es eine Voraussetzung, dass Sie auch die Medienumgehung konfigurieren. Weitere Informationen finden Sie unter Planen der [Medienumgehung mit Direct-Routing](direct-routing-plan-media-bypass.md) und Optimierung lokaler [Medien für Direct-Routing.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Direct Voice over IP (VoIP) darf in Indien nicht mit Telefoniegeräten bereitgestellt werden.

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie [zu Konfigurieren von Netzwerkeinstellungen für Location-Based Routing.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Verwandte Themen

- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
