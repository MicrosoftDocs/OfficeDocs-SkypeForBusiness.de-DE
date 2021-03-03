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
description: Erfahren Sie, wie Sie Location-Based Routing für direktes Routing planen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822925"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planen des standortbasierten Routings für direktes Routing

## <a name="overview-of-location-based-routing"></a>Übersicht über Location-Based Routing

In einigen Ländern und Regionen ist es ungesetzlich, den Anbieter des öffentlichen Telefonnetzwerks (PSTN) zu umgehen, um die Kosten für Ferngespräche zu senken. In diesem Artikel wird beschrieben, wie Sie Location-Based Routing verwenden, um die gebührenpflichtige Umgehung für Microsoft Teams-Benutzer basierend auf ihrem geografischen Standort einzuschränken. Dieser Artikel bezieht sich nur auf das direkte Routing des Telefonsystems.

Hier erhalten Sie eine Übersicht über das Location-Based und Anleitungen, die Sie bei der Planung unterstützen. Wenn Sie bereit sind, das Routing anzuwenden und Location-Based zu aktivieren, lesen Sie:

- [Bereitstellen von Netzwerkeinstellungen für Location-Based Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

> [!NOTE]
> Location-Based Routing ist in Bereitstellungen mit dem High- oder DoD-Speicher der Microsoft 365 Government Community Cloud (GCC) nicht verfügbar.

Location-Based Routing ist ein Feature, mit dem Sie die gebührenpflichtige Umgehung basierend auf einer Richtlinie und dem geografischen Standort des Benutzers zum Zeitpunkt eines eingehenden oder ausgehenden FESTNETZanrufs einschränken können. Location-Based routing is intended to provide a mechanism to prevent toll bypass. Es sollte nicht als Mechanismus zum dynamischen Routen von Festnetzanrufen basierend auf dem Standort des Benutzers verwendet werden, da sich dies unter Umständen durch unbeabsichtigte Folgen ausdingen kann.

Wenn ein Teambenutzer für das Routing Location-Based aktiviert ist, gilt Folgendes:

- Um einen ausgehenden Festnetzanruf zu erstellen, muss einer der folgenden Bedingungen zutreffen:
    - Der Endpunkt des Benutzers befindet sich auf einer Netzwerkwebsite, die für Location-Based Routing und Anrufe über das entsprechende Gateway aktiviert ist, das für das Routing Location-Based ist. 
    - Der Endpunkt des Benutzers befindet sich auf einer Netzwerkwebsite, die nicht für Location-Based Routing und Anrufe über ein Gateway aktiviert ist, das nicht für das Routing Location-Based ist.

    Ausgehende Anrufe sind in keinem anderen Szenario zulässig.

- Für den Empfang eines eingehenden PSTN-Anrufs muss sich der Endpunkt für die Anrufbeantwortung des Benutzers an derselben Netzwerkwebsite befinden, an der der Anruf über das Gateway geht, das für das Routing Location-Based ist. In anderen Szenarien, z. B. wenn der Benutzer roamingt, ist der Anruf nicht zulässig und wird an die Anruf weiterleitungseinstellungen des Benutzers (normalerweise Voicemail) weitergeleitet.
- Um einen Anruf über das Festnetz an einen anderen Teambenutzer zu übertragen, muss sich der Endpunkt des Zielbenutzers auf derselben Netzwerkwebsite wie der Benutzer befinden, der die Übertragung initiiert. Übertragungen sind in keinem anderen Szenario zulässig. 
- Um einen anderen Benutzer von Teams in das PSTN zu übertragen, muss der Anruf über ein Location-Based Routingfähiges Gateway übertragen werden, das sich an derselben Netzwerkwebsite wie der ursprüngliche Anrufer befindet. Übertragungen sind in keinem anderen Szenario zulässig.

Location-Based Routing verwendet die gleichen Definitionen für Netzwerkregion, Standort und Subnetz wie Skype for Business Server. Wenn die gebührenpflichtige Umgehung für einen Standort eingeschränkt ist, ordnet ein Administrator jedes IP-Subnetz und jedes PSTN-Gateway für den jeweiligen Standort einem Netzwerkstandort zu. Die Position eines Benutzers wird durch das IP-Subnetz bestimmt, mit dem die Teams-Endpunkte des Benutzers zum Zeitpunkt eines Festnetzanrufs verbunden sind. Ein Benutzer kann über mehrere Teams-Clients verfügen, die sich auf unterschiedlichen Websites befinden. In diesem Fall erzwingt Location-Based Routing das Routing jedes Clients abhängig vom Standort des jeweiligen Endpunkts. 

Informationen zu einigen der in diesem Artikel verwendeten Netzwerkterminologie finden Sie unter ["Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams".](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>Anwenden Location-Based Routing

Sie müssen das Location-Based an Benutzer, Netzwerkwebsites und PSTN-Gateways anwenden.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Anwenden Location-Based Routing am Benutzerstandort

Wie bereits erwähnt, Location-Based Routing nur für Benutzer gelten, die für das direkte Routing eingerichtet sind. Location-Based Routing gilt nicht für Benutzer, die für einen Anrufplan eingerichtet sind. Benutzer müssen für das Routing Location-Based aktiviert sein, wenn sie die Umgehungsbeschränkung für die gebührenpflichtige Umgehung erfüllen und damit die Bedingungen steuert, unter denen sie ANRUFE über das Festnetz und das PSTN-Gateway, das verwendet werden kann, anrufen und empfangen können. Wenn sich ein Benutzer, der für Location-Based Routing aktiviert ist, an einem Standort befindet, der für das Location-Based-Routing aktiviert ist, muss der Benutzer anrufe über ein Location-Based Routing-fähiges Gateway, das mit dem Standort verbunden ist, anrufen. 

Location-Based Routing funktioniert, indem die aktuelle Position des Benutzers anhand der IP-Adresse des Teams-Endpunkts des Benutzers ermittelt und die Regeln entsprechend angewendet werden. Der Standort eines Benutzers, der für das Routing Location-Based, kann wie folgt kategorisiert werden: 
- **Der Benutzer befindet sich an derselben Location-Based Routing-aktivierten Website, die dem PSTN-Gateway zugeordnet ist, dem die zugehörige Funktion zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer auf einer bekannten Netzwerkwebsite, die für Location-Based Routing aktiviert ist, und die Direktwahlnummer (Direct Inward Dial, DID) des Benutzers endet auf einem PSTN-Gateway, das sich an demselben Netzwerkstandort befindet. Beispielsweise befindet sich der Benutzer im Büro. 
- **Der Benutzer befindet sich an einer anderen Location-Based Routing-aktivierten Website, die nicht mit dem PSTN-Gateway verknüpft ist, dem die funktional zugeordnet ist.**<br>In diesem Szenario befindet sich der Benutzer auf einer bekannten Netzwerkwebsite, die für das Routing von Location-Based aktiviert ist, und diese Website ist nicht mit dem PSTN-Gateway verknüpft, dem die DID-Nummer des Benutzers zugewiesen ist. Der Benutzer reist z. B. in ein anderes Büro.  
- **Der Benutzer befindet sich an einer internen Website, die nicht für das Routing Location-Based ist.** <br>In diesem Szenario befindet sich der Benutzer auf einer bekannten internen Netzwerkwebsite, die nicht für das Routing Location-Based ist. 
- **Der Benutzer befindet sich an einer unbekannten Website.** 
    - Der Benutzer befindet sich in dem internen Netzwerk, das nicht als Netzwerkwebsite definiert ist. 
    - Der Benutzer befindet sich außerhalb des internen Netzwerks. Beispielsweise befindet sich der Benutzer zu Hause oder in einem Café im Internet. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Anwenden Location-Based Routing am Netzwerkstandort 
Netzwerkwebsites müssen für das Routing aktiviert Location-Based, um zu bestimmen, welche Gateways beim Roaming routingfähige Location-Based Routing aktiviert sind. Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, ein Roaming zu einer Website verwendet, die für das Location-Based-Routing aktiviert ist, kann nur das PSTN-Gateway, das für Location-Based Routing an diesem Standort aktiviert ist, für ausgehende Anrufe verwendet werden. Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, ein Roaming zu einer Website verwendet, die für Location-Based Routing nicht aktiviert ist, kann jedes Gateway, das nicht für Location-Based Routing aktiviert ist, für ausgehende Anrufe verwendet werden.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Anwenden Location-Based Routing über das PSTN-Gateway 

Gateways sind Websites zugeordnet, um zu bestimmen, wo sich ein Benutzer befinden kann, der für das Location-Based Routing aktiviert ist, wenn er einen Festnetzanruf anruft oder erhält. Gateways müssen für das Routing Location-Based sein, um sicherzustellen, dass es unter den Einschränkungen für die umgehungspflichtige Umgehung steht und nicht von Benutzern verwendet werden kann, die nicht für das Routing Location-Based können. Dasselbe Gateway kann mehreren Websites zugeordnet sein, und je nach Website kann es so konfiguriert werden, dass es für Location-Based Routing aktiviert oder nicht für Location-Based Routing aktiviert ist.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

In diesem Abschnitt werden verschiedene Szenarien für das Einschränken der gebührenpflichtigen Umgehung mithilfe von Location-Based Routing beschrieben und die Weiterleitung von Anrufen für Benutzer verglichen, die nicht für Location-Based Routing mit Benutzern aktiviert sind, die für das Routing Location-Based sind.

- [Der Benutzer von Teams setzt einen ausgehenden Anruf an das PSTN ab.](#teams-user-places-an-outbound-call-to-the-pstn)
- [Der Benutzer von Teams empfängt einen eingehenden Anruf aus dem PSTN.](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams User transfers or forwards call to another Teams user](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams User transfers or forwards call to PSTN endpoint](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Paralleles Anrufen](#simultaneous-ringing)
- [Delegierung](#delegation)

Das folgende Diagramm zeigt die Einschränkungen, die durch das Routing Location-Based Szenario aktiviert sind. Benutzer, Netzwerkwebsites und Gateways, die für das Routing Location-Based, verfügen über einen Rahmen um sie. Verwenden Sie das Diagramm als Leitfaden, um zu verstehen, wie Location-Based Routing in den einzelnen Szenarien funktioniert.  

![Diagramm mit Szenarien für Location-Based Routing](media/lbr-direct-routing.png "Diagramm mit Szenarien für Location-Based Routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Der Benutzer von Teams setzt einen ausgehenden Anruf an das PSTN ab.

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer ist für das Routing Location-Based aktiviert

Ein Benutzer, der nicht für Location-Based-Routing aktiviert ist, kann ausgehende Anrufe über ein beliebiges Gateway an einem beliebigen Standort, der nicht für das Routing Location-Based über die zugewiesene Voiceroutingrichtlinie aktiviert ist, erstellen. Wenn ein Gateway jedoch für das Routing Location-Based aktiviert ist, kann der Benutzer ausgehende Anrufe nicht über das Gateway abgehen, auch nicht, wenn es seiner Sprachroutingrichtlinie zugewiesen ist. Wenn der Benutzer ein Roaming zu einer Website durchleitt, die für das Routing von Location-Based aktiviert ist, kann er nur über seine normalen Routinggateways Anrufe erstellen, die nicht für das Routing Location-Based sind.
 
#### <a name="user-enabled-for-location-based-routing"></a>Für das Routing Location-Based Benutzer aktiviert
Im Vergleich dazu ist das Routing ausgehender Anrufe für Benutzer, die für das Routing Location-Based von der Netzwerkposition des Endpunkts des Benutzers betroffen. Die folgende Tabelle zeigt, Location-Based routing sich abhängig vom Standort von Benutzer1 auf das Routing ausgehender Anrufe von Benutzer1 auswirkt. 

|Position des Benutzer1-Endpunkts  |Routing ausgehender Anrufe für Benutzer1  |
|---------|---------|
|Dieselbe Website, der die did-Website des Benutzers zugewiesen ist, für die Location-Based (Site1) aktiviert      |Anruf, der über ein Gateway geroutet wird, das für Location-Based Routing (GW1) an Standort1 aktiviert ist, basierend auf der Sprachroutingrichtlinie des Benutzers         |
|Anders als die Website, der die DID des Benutzers zugewiesen ist, aktivierte Website für Location-Based Routing (Site2)    |Anruf, der über ein Gateway geroutet wird, das für Location-Based Routing (GW2) am Roam Site2 aktiviert ist, basierend auf der Sprachroutingrichtlinie des Benutzers        |
|Eine andere Website als die Website, der die did-Funktion des Benutzers zugewiesen ist, die Website ist nicht für das Routing Location-Based (Site3) aktiviert  |Anruf, der über ein Gateway geroutet wird, das nicht für Location-Based Routing an einem Standort aktiviert ist, der nicht für Location-Based Routing (GW3) aktiviert ist, basierend auf der Sprachroutingrichtlinie des Benutzers       |
|Unbekanntes internes Netzwerk (Standort4)    |  Anrufe über das Festnetz sind nicht zulässig       |
|Unbekanntes externes Netzwerk (Standort5)    | Anrufe über das Festnetz sind nicht zulässig        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Der Benutzer von Teams empfängt einen eingehenden Anruf aus dem PSTN.

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer ist für das Routing Location-Based aktiviert

Ein Benutzer, der nicht für Location-Based Routing aktiviert ist, kann einen eingehenden Anruf vom Gateway empfangen, der nicht für Location-Based Routing aktiviert ist, von dem die zugewiesenen Nummern der Anderen empfangen werden. Wenn der Benutzer das Roaming zu einer Website anleitt, die nicht für das Routing Location-Based ist, kann er weiterhin Anrufe über seine normalen PSTN-Gateways empfangen.
  
#### <a name="user-enabled-for-location-based-routing"></a>Für das Routing Location-Based Benutzer aktiviert

Im Vergleich dazu können Benutzer, die für Location-Based Routing aktiviert sind, nur eingehende Anrufe vom PSTN-Gateway empfangen, dem ihre DID-Funktion zugewiesen ist, wenn sie sich am selben Standort befinden. Die folgende Tabelle zeigt, wie Benutzer1 eingehende Anrufe empfängt, wenn Benutzer1 zu verschiedenen Netzwerkstandorten wechselt. Wenn der Anruf nicht an den Endpunkt des Benutzers weitergeleitet wird, wird er zu den Anruf weiterleitungseinstellungen des Benutzers weitergeleitet, sofern die Einstellungen konfiguriert sind. In der Regel handelt es sich dabei um Voicemail.  

|Position des Benutzer1-Endpunkts  |Routing eingehender Anrufe an Benutzer1  |
|---------|---------|
|Dieselbe Website wie die Website, der die did-Website des Benutzers zugewiesen ist, aktiviert für Location-Based Routing (Site1)   | Anrufe, die an den Endpunkt von Benutzer1 in Site1 geleitet werden        |
|Anders als die Website, der die DID des Benutzers zugewiesen ist, aktivierte Website für Location-Based Routing (Site2)    | Anrufe, die nicht an Endpunkte in Site2 geleitet werden        |
|Eine andere Website als die Website, der die did-Funktion des Benutzers zugewiesen ist, die Website ist nicht für das Routing Location-Based (Site3) aktiviert    | Anrufe, die nicht an Endpunkte in Site3 geleitet werden        |
|Unbekanntes internes Netzwerk (Standort4)   | Anrufe, die nicht an Endpunkte in Location4 geleitet werden        |
|Unbekanntes externes Netzwerk (Standort5)     | Anrufe, die nicht an Endpunkte in Location5 geleitet werden        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams User transfers or forwards call to another Teams user

Wenn ein PSTN-Endpunkt involviert ist, analysiert Location-Based Routing, ob ein oder beide Benutzer für Location-Based Routing aktiviert sind, und bestimmt, ob der Anruf je nach Standort der beiden Endpunkte weitergeleitet oder weitergeleitet werden soll. 
 
Bei der Anrufübertragung muss der initiierte Benutzer den Anruf ablösen, während für die Anruf weiterleitung nicht der erste Anruf beantwortet werden muss. Dies bedeutet, dass Anrufe weitergeleitet werden können, auch wenn Sich Benutzer1 nicht an einem Ort befindet, an dem er eingehende Anrufe empfangen kann (siehe die Tabelle im [Abschnitt "Teams-Benutzer](#teams-user-receives-an-inbound-call-from-the-pstn) empfängt einen eingehenden Anruf aus dem PSTN-Abschnitt) und Anrufe nicht übertragen werden können, wenn Benutzer1 den eingehenden Anruf nicht empfangen kann. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer ist für das Routing Location-Based aktiviert

Ein Benutzer, der nicht für das Routing Location-Based kann ANRUFE über das Festnetz an andere Benutzer weiterleiten, die nicht für das Routing Location-Based sind. Der Benutzer darf normalerweise einen Anruf über das Festnetz nicht an einen Benutzer weiterleiten, der für Location-Based Routing aktiviert ist, da Location-Based Routing-aktivierte Benutzer im Allgemeinen nur an Location-Based Routing-fähigen Gateways für Anrufe über das Festnetz gemeinsam an einem anderen Standort sein dürfen. Die Ausnahme ist, wenn Location-Based Routing aktivierten Benutzer zu einer Website weiterleite, die nicht für das Routing Location-Based ist. In diesem Szenario ist der übertragene Anruf zulässig.  

Ebenso kann ein Benutzer, der nicht für Location-Based Routing aktiviert ist, nur eine Übertragung oder einen weitergeleiteten Festnetzanruf von einem anderen Benutzer erhalten, der nicht für das Routing Location-Based ist. 

#### <a name="user-enabled-for-location-based-routing"></a>Für das Routing Location-Based Benutzer aktiviert

Im Allgemeinen ist das Übertragen und Weiterleiten eingehender PSTN-Anrufe von einem Gateway, das für Location-Based Routing aktiviert ist, nur zulässig, wenn der Zielbenutzer für das Routing von Location-Based aktiviert ist und sich an demselben Standort befindet. Andernfalls sind Das Übertragen und Weiterleiten von Anrufen nicht zulässig. 

Die folgende Tabelle zeigt, ob Anrufanrufe und Anrufübertragungen je nach Standort des Zielbenutzers zulässig sind. In dieser Tabelle initiiert "Benutzer1" auf "Website1" die Übertragung oder Weiterleitung an andere Teams-Benutzer, die ebenfalls für Location-Based Routing aktiviert sind und sich an unterschiedlichen Standorten befinden.  

|Zielpunkt des Benutzerendpunkts|Benutzer1 initiiert die Anrufübertragung |Benutzer1 initiiert die Anruf weiterleiten|
|---------|---------|---------|
|Dieselbe Netzwerkwebsite wie Inn (Benutzer2)|Zulässig|Zulässig|
|Verschiedene Netzwerkwebsite, Website für Location-Based Routing aktiviert (Benutzer3)|Nicht zulässig|Nicht zulässig|
|Unterschiedliche Netzwerkwebsite, Website nicht für Location-Based Routing aktiviert (Benutzer4)|Nicht zulässig|Nicht zulässig|
|Unbekanntes internes Netzwerk (Benutzer5)| Nicht zulässig|Nicht zulässig|
|Unbekanntes externes Netzwerk (Benutzer6)| Nicht zulässig|Nicht zulässig|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams User transfers or forwards call to PSTN endpoint

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer ist für das Routing Location-Based aktiviert

- Das Übertragen und Weiterleiten eines Anrufs über das Festnetz an eine andere Rufnummer ist zulässig. 
- Durch Die Übertragung und Weiterleitung eines eingehenden VOIP-Anrufs an das PSTN müssen die einschränkungen der gebührenpflichtigen Umgehung des Anrufers berücksichtigt werden. 
    - Wenn der Anrufer für das Routing Location-Based aktiviert ist, kann er an ein beliebiges PSTN-Gateway übertragen werden, das nicht für das Routing Location-Based ist.
    - Wenn der Anrufer für das Routing Location-Based aktiviert ist, kann er nur an ein Location-Based Routing-aktiviertes Gateway übertragen werden, das sich an demselben Netzwerkstandort befindet. 

#### <a name="user-enabled-for-location-based-routing"></a>Für das Routing Location-Based Benutzer aktiviert

- Durch die Übertragung und Weiterleitung eines eingehenden Anrufs an eine andere Rufnummer im öffentlichen Telefonnetz muss dasselbe routingfähige Location-Based-fähiges Gateway, bei dem der eingehende Anruf eintroffen ist. 
- Bei der Übertragung und Weiterleitung eines eingehenden VOIP-Anrufs an das PSTN müssen sowohl der Anrufer als auch die angerufenen Einschränkungen der gebührenpflichtigen Umgehung berücksichtigt werden. 
    - Wenn der Anrufer für das Routing Location-Based aktiviert ist, kann er an ein beliebiges PSTN-Gateway übertragen werden, das nicht für das Routing Location-Based ist.
    - Wenn der Anrufer für das Routing Location-Based ist, kann er nur an ein Location-Based Routing-aktiviertes Gateway übertragen werden, das sich an demselben Netzwerkstandort befindet.
 
Die folgende Tabelle zeigt, wie sich Location-Based Routing auf das Routing eines VOIP-Anrufs von Benutzer1 an Standort1 an Benutzer an unterschiedlichen Standorten auswirkt, die den Anruf an einen PSTN-Endpunkt durchstellen oder weiterleiten.  

|Benutzer initiiert Anrufübertragung oder Weiterleitung  |Übertragen in das PSTN  |Weiterleiten an PSTN  |
|---------|---------|---------|
|Dieselbe Netzwerkwebsite, Website für Location-Based Routing aktiviert (Benutzer2)   |Die Anrufübertragung kann basierend auf der Voiceroutingrichtlinie von Benutzer2 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.         |Die Weiterleitung kann basierend auf der Voiceroutingrichtlinie von Benutzer2 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |
|Verschiedene Netzwerkwebsite, Website für Location-Based Routing aktiviert (Benutzer3)    |Die Anrufübertragung kann basierend auf der Voiceroutingrichtlinie von Benutzer3 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.         |Die Weiterleitung kann basierend auf der Voiceroutingrichtlinie von Benutzer3 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |
|Unterschiedliche Netzwerkwebsite, Website nicht für Location-Based Routing aktiviert (Benutzer4)    |Die Anrufübertragung kann basierend auf der Voiceroutingrichtlinie von Benutzer4 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.         |Die Weiterleitung kann basierend auf der Sprachroutingrichtlinie von Benutzer4 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |
|Unbekanntes internes Netzwerk (Benutzer5)     |Die Anrufübertragung kann basierend auf der Voiceroutingrichtlinie von Benutzer5 nur über Location-Based Routing aktiviertes Gateway1 an "Standort1" geroutet werden.         |Die Weiterleitung kann basierend auf der Voiceroutingrichtlinie von Benutzer5 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |
|Unbekanntes externes Netzwerk (Benutzer6)   |Die Anrufübertragung kann basierend auf der Voiceroutingrichtlinie von Benutzer6 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 geroutet werden.        |Die Weiterleitung kann basierend auf der Voiceroutingrichtlinie von Benutzer6 nur über Location-Based Routing aktiviertes Gateway1 an Standort1 weitergeleitet werden.         |

### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn ein Benutzer, der für Location-Based Routing aktiviert ist, einen Anruf empfängt und gleichzeitiges Klingeln aktiviert ist, analysiert Location-Based Routing die Position der anrufenden Partei und die Endpunkte der angerufenen Parteien, um zu bestimmen, ob der Anruf geleitet werden soll. Für das gleichzeitige Klingeln gelten die gleichen Location-Based wie für Anrufübertragungen und Weiterleitungen. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Gleichzeitiges Klingeln für einen anderen Teams-Benutzer

In der folgenden Tabelle ist Location-Based, ob das Routing das gleichzeitige Klingeln bei verschiedenen Benutzern für einen eingehenden Festnetzanruf für Benutzer1 zulässt.

|Zielpunkt des Benutzerendpunkts|Gleichzeitiges Klingeln  |
|---------|---------|
|Dieselbe Netzwerkwebsite wie Inn (Benutzer2)   |Zulässig         |
|Unterschiedliche für das Routing aktivierte Location-Based (Benutzer3)   |Nicht zulässig         |
|Roamierte Netzwerkwebsite, die nicht für Location-Based aktiviert ist (Benutzer4)   |Nicht zulässig        |
|Unbekanntes internes Netzwerk (Benutzer5)    | Nicht zulässig        |
|Unbekanntes externes Netzwerk (Benutzer6)    |Nicht zulässig        |
|Zielbenutzer ist eine PSTN-Nummer.    |Der Anruf kann nur über das routingfähige Location-Based Gateway1 an Standort1, basierend auf der Voiceroutingrichtlinie von Benutzer1, geroutet werden.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Gleichzeitiges Klingeln an einem PSTN-Endpunkt

Die folgende Tabelle zeigt Location-Based Routingverhalten für einen eingehenden VOIP-Anruf von "Benutzer1" an Standort1 für Benutzer an unterschiedlichen Standorten, bei dem gleichzeitiges Anrufen auf eine Festnetznummer festgelegt ist. 

|So genannte Position des Benutzerendpunkts  |Gleichzeitiges Rufziel ist der PSTN-Endpunkt. |
|---------|---------|
|Dieselbe Netzwerkwebsite, Website für Location-Based Routing aktiviert (Benutzer2)    |Der Anruf kann basierend auf der Voiceroutingrichtlinie von Benutzer2 nur über Location-Based Routinggateway1 an Standort1 geroutet werden.       |
|Unterschiedliche Netzwerkwebsite, die für Location-Based Routing aktiviert ist (Benutzer3)    |Der Anruf kann nur über Location-Based Routinggateway1 an Standort1 geroutet werden, basierend auf der Sprachroutingrichtlinie von Benutzer3.        |
|Unterschiedliche Netzwerkwebsite, die nicht für die Location-Based aktiviert ist (Benutzer4)    |Anrufe können nur über Location-Based Routinggateway1 an Standort1 weiterleiten, basierend auf der Sprachroutingrichtlinie von Benutzer4         |
|Unbekanntes internes Netzwerk (Benutzer5)    |Der Anruf kann basierend auf der Voiceroutingrichtlinie von Benutzer5 nur über Location-Based Routinggateway1 an Standort1 geroutet werden.         |
|Unbekanntes externes Netzwerk (Benutzer6)   |Der Anruf kann nur über Location-Based Routinggateway1 an Standort1 weiterleiten, basierend auf der Voiceroutingrichtlinie von Benutzer6         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Eingehende Anrufe über die Sprach-App (automatische Telefonzentrale oder Anrufwarteschleife)

Eingehende PstN-Anrufe von einem Location-Based Routing-aktivierten Gateways dürfen eine Verbindung mit einer automatischen Telefonwarteschlange oder Anrufwarteschleife herstellen. Benutzer, die für Location-Based A0 aktiviert sind, können eingehende Anrufübertragungen von diesen Anwendungen nur empfangen, wenn sie sich an demselben Standort befinden, von dem der eingehende Festnetzanruf stammt. 
 
Anrufanrufe und gleichzeitiges Klingeln an Benutzer und PSTN sind für Voice-App-Übertragungen zulässig. Das Abschließen des Anrufs an das Ziel unterliegt den oben Location-Based Routingregeln.  
 
Weiterleitung an Voicemail ist ebenfalls zulässig.  

### <a name="delegation"></a>Delegierung

Ein Teambenutzer kann Stellvertretung auswählen, die in ihrem Namen Anrufe erstellen und empfangen kann. Delegierungsfunktionen in Teams sind von der Location-Based wie folgt betroffen: 
- Für ausgehende Anrufe von einer Location-Based routingfähigen Stellvertretung im Auftrag eines Delegators gelten die gleichen Regeln. Die Anrufrouting basiert auf der Anrufautorisierungsrichtlinie, der Sprachroutingrichtlinie und dem Standort der Stellvertretung. Weitere Informationen finden Sie unter [Teams-Benutzer, die ausgehende Anrufe an das PSTN abstellen.](#teams-user-places-an-outbound-call-to-the-pstn) 
- Bei eingehenden Anrufen über das Festnetz an einen Delegator gelten für Stellvertretung die gleichen Location-Based-Routingregeln, die für die Anruf weiterleitung oder für gleichzeitiges Klingeln bei anderen Benutzern gelten. Weitere Informationen finden [](#teams-user-transfers-or-forwards-call-to-another-teams-user)Sie unter "Teams-Benutzerübertragungen" oder "Weiterleitungen" an einen anderen Teams-Benutzer, Anruf durch Teams-Benutzerübertragungen oder -Weiterleitungen an den [PSTN-Endpunkt](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)und gleichzeitiges [Klingeln.](#simultaneous-ringing) Wenn eine Stellvertretung einen PstN-Endpunkt als Ziel für gleichzeitiges Anrufen fest legt, wird die Sprachroutingrichtlinie der Stellvertretung verwendet, um den Anruf an das PSTN weiter zu weiterleiten. 
- Für delegierung wird empfohlen, dass sich der Delegator und die zugehörigen Stellvertretung auf derselben Netzwerkwebsite befinden. 

## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Änderungen von einer lokalen Bereitstellung Location-Based Routingbereitstellung

Die Voiceroutingrichtlinie für eine Netzwerkwebsite wird nicht mehr verwendet. Stattdessen verwenden wir die Sprachroutingrichtlinie des Benutzers. Dies bedeutet, dass die Sprachroutingrichtlinie die Gateways der ge roamten Websites enthalten muss, um Benutzern das Roamen zu anderen Websites zu ermöglichen. 

### <a name="technical-considerations-for-location-based-routing"></a>Technische Überlegungen zum standortbasierten Routing

IPv4- und IPv6-Subnetze werden unterstützt, IPv6 hat jedoch Beim Überprüfen auf eine Übereinstimmung Vorrang.

### <a name="client-support-for-location-based-routing"></a>Clientunterstützung für Location-Based Routing

Die folgenden Teams-Clients werden unterstützt:
- Desktopclients für Teams (Windows und Mac)
- Mobile Teams-Clients (iOS und Android)
- Teams-IP-Telefone

Der Webclient von Teams und Skype for Business werden nicht unterstützt.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Location-Based Routing gilt nicht für die folgenden Interaktionstypen. Location-Based Routing wird nicht erzwungen, wenn Teams-Endpunkte in den folgenden Szenarien mit DEN PSTN-Endpunkten interagieren: 
- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen 
- Ein lokales Skype for Business-Benutzer oder ein Skype for Business Online-Benutzer ruft einen Teambenutzer an.  

### <a name="location-based-routing-for-conferencing"></a>Location-Based Routing für Konferenzen

Einem Location-Based Routing aktivierter Benutzer bei einem Anruf über das Festnetz ist es nicht gestattet, eine Konferenz mit einem anderen Benutzer oder einer Anderen Rufnummer über das Festnetz zu starten. Das Herstellen einer Verbindung mit automatischen Telefonkonferenzen oder Anrufwarteschleifen ist zulässig. Wenn der Benutzer über eine Konferenzlizenz verfügt, muss er eine Konferenz mit den relevanten Benutzern beginnen und das PSTN über die Konferenzbrücke anrufen, um eine Telefonkonferenz zu starten.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Anforderung zur Medienumgehung für Location-Based Routing

Wenn Sie das Routing Location-Based in Indien bereitstellen, ist es erforderlich, auch die Medienumgehung zu konfigurieren. Weitere Informationen finden Sie unter "Planen der [Medienumgehung mit Direct Routing"](direct-routing-plan-media-bypass.md) und der Optimierung lokaler [Medien für das direkte Routing.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>Direct Voice over IP (VoIP)

Direct Voice over IP (VoIP) darf in Indien nicht mit Telefoniegeräten bereitgestellt werden.

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie [zu "Konfigurieren von Netzwerkeinstellungen für Location-Based Routing".](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>Verwandte Themen

- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
