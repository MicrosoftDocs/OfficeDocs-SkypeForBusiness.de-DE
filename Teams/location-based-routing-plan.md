---
title: Planen des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: Erfahren Sie, wie Sie standortbasiertes Routing für das direkte Routing planen.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f72360f4462a64e357d58489aa70203bf10c532
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326642"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planen des standortbasierten Routings für direktes Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Übersicht über standortbasiertes Routing

In einigen Ländern und Regionen ist es illegal, den PSTN-Anbieter (Public Switched Telephone Network) zu umgehen, um die Kosten für Ferngespräche zu verringern. In diesem Artikel wird beschrieben, wie Sie mithilfe von Standort basiertem Routing die Gebühren Umgehung für Microsoft Teams-Benutzer auf der Grundlage ihres geografischen Standorts einschränken. Dieser Artikel bezieht sich nur auf das direkte Routing von Telefonsystemen.

Hier erhalten Sie einen Überblick über standortbasiertes Routing und Anleitungen, die Ihnen bei der Planung helfen. Wenn Sie bereit sind, standortbasiertes Routing zu übernehmen und zu aktivieren, lesen Sie:
- [Bereitstellen von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

Standortbasiertes Routing ist eine Funktion, mit der Sie die Gebühren Umgehung auf der Grundlage der Richtlinie und des geografischen Standorts des Benutzers zum Zeitpunkt eines eingehenden oder ausgehenden PSTN-Anrufs einschränken können. 

Wenn ein Team Benutzer für standortbasiertes Routing aktiviert ist, gilt Folgendes:
- Um einen ausgehenden PSTN-Anruf zu führen, muss eine der folgenden Bedingungen erfüllt sein:
    - Der Endpunkt des Benutzers befindet sich in einer Netzwerk Website, die für standortbasiertes Routing aktiviert ist, und ruft den Ausgang über das entsprechende Gateway auf, das für standortbasiertes Routing aktiviert ist. 
    - Der Endpunkt des Benutzers befindet sich an einer Netzwerk Website, die für standortbasiertes Routing nicht aktiviert ist, und ruft den Ausstieg über ein Gateway auf, das für standortbasiertes Routing nicht aktiviert ist.

    Ausgehende Anrufe sind in einem anderen Szenario nicht zulässig.

- Um einen eingehenden PSTN-Anruf zu empfangen, muss sich der Antwortendpunkt des Benutzers an derselben Netzwerk Website befinden, an der der Anruf durch das Gateway erfolgt, das für standortbasiertes Routing aktiviert ist. In einem anderen Szenario, beispielsweise wenn der Benutzer Roaming durchführt, ist der Anruf nicht zulässig und wird an die Einstellungen für die Anrufweiterleitung des Benutzers (in der Regel Voicemail) weitergeleitet.
- Um einen PSTN-Anruf an einen anderen Teams-Benutzer zu übertragen, muss sich der Endpunkt des Zielbenutzers an derselben Netzwerk Website befinden wie der Benutzer, der die Übertragung initiiert. Übertragungen sind in einem anderen Szenario nicht zulässig. 
- Um einen anderen Teams-Benutzer an das PSTN zu übertragen, muss der Anruf über ein standortbasiertes Routing aktiviertes Gateway erfolgen, das sich am gleichen Netzwerkstandort befindet wie der ursprüngliche Anrufer. Übertragungen sind in einem anderen Szenario nicht zulässig.

Standortbasiertes Routing verwendet die gleichen netzwerkregion-, Website-und Subnetz-Definitionen, die Skype for Business Server verwendet. Wenn die Gebühren Umgehung für einen Standort eingeschränkt ist, ordnet ein Administrator jedes IP-Subnetz und jedes PSTN-Gateway für diesen Standort einer Netzwerk Website zu. Der Standort eines Benutzers wird durch das IP-Subnetz bestimmt, mit dem die Endpunkte des Benutzers verbunden sind, zum Zeitpunkt eines PSTN-Anrufs. Ein Benutzer kann mehrere Teams-Clients an verschiedenen Standorten haben, wobei standortbasiertes Routing die einzelnen Client-Routings je nach Standort des Endpunkts separat erzwingt. 

Wenn Sie sich mit einigen der in diesem Artikel verwendeten Netzwerkterminologie vertraut machen möchten, lesen Sie [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>Anwenden von Standort basiertem Routing

Sie müssen standortbasiertes Routing auf Benutzer, Netzwerk Websites und PSTN-Gateways anwenden.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Anwenden des standortbasierten Routings am Benutzerstandort

Wie bereits erwähnt, gilt standortbasiertes Routing nur für Benutzer, die für die direkte Weiterleitung eingerichtet sind. Standortbasiertes Routing gilt nicht für Benutzer, die für einen Anrufplan eingerichtet sind. Benutzer müssen für standortbasiertes Routing aktiviert sein, wenn Sie unter der Maut Umgehungs Beschränkung sind, die die Bedingungen steuert, unter denen Sie PSTN-Anrufe tätigen können, und das PSTN-Gateway, das verwendet werden kann. Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, sich auf einer Website befindet, die für standortbasiertes Routing aktiviert ist, muss der Benutzer Anrufe über ein standortbasiertes Routing aktiviertes Gateway führen, das mit der Website verbunden ist. 

Standortbasiertes Routing durch Ermitteln des aktuellen Standorts des Benutzers basierend auf der IP-Adresse des Teams-Endpunkts des Benutzers und Anwenden der Regeln entsprechend. Der Standort eines Benutzers, der für standortbasiertes Routing aktiviert ist, kann wie folgt kategorisiert werden: 
- **Der Benutzer befindet sich an der gleichen standortbasierten Routing fähigen Website, die dem PSTN-Gateway zugeordnet ist, in dem dessen did zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer in einer bekannten Netzwerk Website, die für standortbasiertes Routing aktiviert ist, und die direkte Durchwahlnummer (DID) des Benutzers wird auf einem PSTN-Gateway beendet, das sich auf derselben Netzwerk Website befindet. Der Benutzer befindet sich beispielsweise in seinem Büro. 
- **Der Benutzer befindet sich an einer anderen standortbasierten Routing fähigen Website, die nicht mit dem PSTN-Gateway verknüpft ist, in dem Ihre did zugewiesen ist.**<br>In diesem Szenario befindet sich der Benutzer in einer bekannten Netzwerk Website, die für standortbasiertes Routing aktiviert ist, und diese Website ist nicht mit dem PSTN-Gateway verknüpft, in dem die DID-Nummer des Benutzers zugewiesen wurde. So reist der Benutzer beispielsweise in ein anderes Office.  
- **Der Benutzer befindet sich an einer internen Website, die für standortbasiertes Routing nicht aktiviert ist.** <br>In diesem Szenario befindet sich der Benutzer in einer bekannten internen Netzwerk Website, die für standortbasiertes Routing nicht aktiviert ist. 
- **Der Benutzer befindet sich an einer unbekannten Website.** 
    - Der Benutzer befindet sich im internen Netzwerk, das nicht als Netzwerk Website definiert ist. 
    - Der Benutzer befindet sich außerhalb des internen Netzwerks. So befindet sich der Benutzer beispielsweise im Internet zu Hause oder in einem Coffee-Shop. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Anwenden von Standort basiertem Routing auf der Netzwerk Website 
Netzwerk Websites müssen für standortbasiertes Routing aktiviert sein, damit Sie ermitteln können, welche Gateways beim Roaming standortbasierte routingfähige Benutzer weiterleiten. Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, zu einer Website wechselt, die für standortbasiertes Routing aktiviert ist, kann nur das PSTN-Gateway, das für standortbasiertes Routing an diesem Standort aktiviert ist, für ausgehende Anrufe verwendet werden. Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, zu einer Website wechselt, die nicht für standortbasiertes Routing aktiviert ist, kann ein Gateway, das für standortbasiertes Routing nicht aktiviert ist, für ausgehende Anrufe verwendet werden.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Anwenden von Standort basiertem Routing auf dem PSTN-Gateway 

Gateways werden Websites zugeordnet, um festzustellen, wo ein Benutzer, der für standortbasiertes Routing aktiviert ist, beim vornehmen oder empfangen eines PSTN-Anrufs gefunden werden kann. Gateways müssen für standortbasiertes Routing aktiviert sein, um sicherzustellen, dass die gebührenpflichtigen Umgehungs Einschränkungen gelten und nicht von Benutzern verwendet werden können, die für standortbasiertes Routing nicht aktiviert sind. Das gleiche Gateway ist möglicherweise mehreren Websites zugeordnet und kann je nach Standort so konfiguriert werden, dass es für standortbasiertes Routing aktiviert oder nicht für standortbasiertes Routing aktiviert ist.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

In diesem Abschnitt werden verschiedene Szenarien für die Einschränkung der Maut Umgehung mithilfe von Standort basiertem Routing beschrieben, und es wird verglichen, wie Anrufe für Benutzer weitergeleitet werden, die nicht für standortbasiertes Routing mit Benutzern aktiviert sind, die für standortbasiertes Routing aktiviert sind.

- [Teams-Benutzer platziert einen ausgehenden Anruf an das PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams-Benutzer erhält einen eingehenden Anruf vom PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams Nutzer Übertragungen oder Weiterleitung von Anrufen an einen anderen Teams-Nutzer](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams, die den Anruf an den PSTN-Endpunkt übertragen oder weiterleiten](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Paralleles Anrufen](#simultaneous-ringing)
- [Delegierung](#delegation)

Das folgende Diagramm zeigt die Einschränkungen, die in jedem Szenario durch standortbasiertes Routing aktiviert sind. Benutzer, Netzwerk Websites und Gateways, die für standortbasierte Routings aktiviert sind, haben einen Rahmen um Sie herum. Verwenden Sie das Diagramm als Leitfaden, damit Sie verstehen, wie standortbasiertes Routing in jedem Szenario funktioniert.  

![Diagramm mit Szenarien für standortbasiertes Routing](media/lbr-direct-routing.png "Diagramm mit Szenarien für standortbasiertes Routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams-Benutzer platziert einen ausgehenden Anruf an das PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing nicht aktiviert

Ein Benutzer, der für standortbasiertes Routing nicht aktiviert ist, kann ausgehende Anrufe über ein beliebiges Gateway an einer beliebigen Website führen, die nicht für standortbasiertes Routing über die zugewiesene VoIP-Routing Richtlinie aktiviert ist. Wenn ein Gateway aber für standortbasiertes Routing aktiviert ist, kann der Benutzer keine ausgehenden Anrufe über das Gateway tätigen, auch wenn es seiner VoIP-Routing Richtlinie zugewiesen ist. Wenn der Benutzer zu einer Website wechselt, die für standortbasiertes Routing aktiviert ist, können Sie nur Anrufe über Ihre normalen Routing Gateways führen, die für standortbasiertes Routing nicht aktiviert sind.
 
#### <a name="user-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing aktiviert
Im Vergleich dazu ist das Routing von ausgehenden Anrufen für Benutzer, die für standortbasierte Routings aktiviert sind, vom Netzwerkspeicherort des Endpunkts des Benutzers betroffen. In der folgenden Tabelle wird gezeigt, wie sich der standortbasierte Routing abhängig vom Standort von Benutzer1 auf das Routing von ausgehenden Anrufen von Benutzer1 auswirkt. 

|Benutzer1-Endpunkt Standort  |Routing von ausgehenden Anrufen für Benutzer1  |
|---------|---------|
|Dieselbe Website, auf der der Benutzer die did-Funktion zugewiesen hat, Website für standortbasiertes Routing (site1)      |Anrufweiterleitung über Gateway, das für standortbasiertes Routing (GW1) unter site1 basierend auf der VoIP-Routing Richtlinie des Benutzers aktiviert ist         |
|Andere Website als die, für die der Benutzer die Funktion zugewiesen hat, Website für standortbasiertes Routing (site2)    |Anrufweiterleitung über Gateway, das für standortbasiertes Routing (GW2) auf Roaming-site2 aktiviert ist, basierend auf der VoIP-Routing Richtlinie des Benutzers        |
|Andere Website als die, für die der Benutzer die Funktion zugewiesen hat, Website nicht aktiviert für standortbasiertes Routing (Site3)  |Anrufweiterleitung über Gateway, das nicht für standortbasiertes Routing an einer Website aktiviert ist, die nicht für standortbasiertes Routing (GW3) aktiviert ist, basierend auf der VoIP-Routing Richtlinie des Benutzers       |
|Unbekanntes internes Netzwerk (Location4)    |  PSTN-Anrufe sind nicht zulässig       |
|Unbekanntes externes Netzwerk (Location5)    | PSTN-Anrufe sind nicht zulässig        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams-Benutzer erhält einen eingehenden Anruf vom PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing nicht aktiviert

Ein Benutzer, der für standortbasiertes Routing nicht aktiviert ist, kann einen eingehenden Anruf vom Gateway empfangen, das für standortbasiertes Routing nicht aktiviert ist, von dem die zugewiesene DID-Nummer eintritt. Wenn der Benutzer zu einer Website wechselt, die für standortbasiertes Routing nicht aktiviert ist, können Sie weiterhin Anrufe über Ihre normalen PSTN-Gateways empfangen.
  
#### <a name="user-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing aktiviert

Im Vergleich dazu können Benutzer, die für standortbasiertes Routing aktiviert sind, nur eingehende Anrufe vom PSTN-Gateway empfangen, dem Ihre did-Funktion zugewiesen ist, wenn Sie sich am gleichen Standort befinden. In der folgenden Tabelle wird gezeigt, wie Benutzer1 eingehende Anrufe empfängt, wenn Benutzer1 an verschiedene Netzwerkspeicherorte wechselt. Wenn der Anruf nicht an den Endpunkt des Benutzers weitergeleitet wird, wechselt er zu den Einstellungen für die Anrufweiterleitung des Benutzers, wenn die Einstellungen konfiguriert sind. In der Regel ist dies Voicemail.  

|Benutzer1-Endpunkt Standort  |Weiterleiten von eingehenden Anrufen an Benutzer1  |
|---------|---------|
|Dieselbe Website wie in der der Benutzer zugewiesen wurde, Website aktiviert für standortbasiertes Routing (site1)   | An von Benutzer1-Endpunkt in site1 weitergeleitete Anrufe        |
|Andere Website als die, für die der Benutzer die Funktion zugewiesen hat, Website für standortbasiertes Routing (site2)    | Anrufe, die nicht an Endpunkte in site2 weitergeleitet werden        |
|Andere Website als die, für die der Benutzer die Funktion zugewiesen hat, Website nicht aktiviert für standortbasiertes Routing (Site3)    | Anrufe, die nicht an Endpunkte in Site3 weitergeleitet werden        |
|Unbekanntes internes Netzwerk (Location4)   | Anrufe, die nicht an Endpunkte in Location4 weitergeleitet werden        |
|Unbekanntes externes Netzwerk (Location5)     | Anrufe, die nicht an Endpunkte in Location5 weitergeleitet werden        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams Nutzer Übertragungen oder Weiterleitung von Anrufen an einen anderen Teams-Nutzer

Wenn es sich um einen PSTN-Endpunkt handelt, analysiert standortbasiertes Routing, ob ein oder beide Benutzer für standortbasiertes Routing aktiviert sind, und bestimmt, ob der Anruf je nach Position beider Endpunkte übertragen oder weitergeleitet werden soll. 
 
Für die Anrufübertragung muss der initiierende Benutzer den Anruf annehmen, während die Anrufweiterleitung nicht erfordert, dass der erste Anruf beantwortet wird. Das bedeutet, dass Anrufe weitergeleitet werden können, auch wenn Benutzer1 nicht an einem Ort ist, um eingehende Anrufe zu empfangen (siehe Tabelle in den Teams, der [Benutzer einen eingehenden Anruf vom PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) -Abschnitt erhält), und Anrufe können nicht übertragen werden, wenn Benutzer1 den eingehenden Anruf nicht empfangen kann. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing nicht aktiviert

Ein Benutzer, der für standortbasiertes Routing nicht aktiviert ist, kann PSTN-Anrufe an andere Benutzer übertragen oder weiterleiten, die nicht für standortbasiertes Routing aktiviert sind. Der Benutzer ist in der Regel nicht berechtigt, einen PSTN-Anruf an einen Benutzer zu übertragen oder weiterzuleiten, der für standortbasiertes Routing aktiviert ist, da standortbasierte Routing aktivierte Benutzer in der Regel nur an standortbasierten routingfähigen Gateways für PSTN-Anrufe teilnehmen dürfen. Die Ausnahme ist, wenn ein standortbasierter Routing Benutzer zu einer Website wechselt, die für standortbasiertes Routing nicht aktiviert ist. In diesem Szenario ist der übertragene Anruf zulässig.  

Ein Benutzer, der für standortbasiertes Routing nicht aktiviert ist, kann auch nur einen PSTN-Anruf von einem anderen Benutzer empfangen, der für standortbasiertes Routing nicht aktiviert ist. 

#### <a name="user-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing aktiviert

Im Allgemeinen ist das übertragen und Weiterleiten von eingehenden PSTN-Anrufen von einem Gateway, das für standortbasiertes Routing aktiviert ist, nur zulässig, wenn der Zielbenutzer für standortbasiertes Routing aktiviert ist und sich am gleichen Standort befindet. Andernfalls ist das übertragen und Weiterleiten von Anrufen nicht zulässig. 

In der folgenden Tabelle wird gezeigt, ob Anrufweiterleitung und Anruf Übertragungen je nach Standort des Zielbenutzers zulässig sind. In dieser Tabelle initiiert Benutzer1, die sich in site1 befindet, die Übertragung oder Weiterleitung an andere Teams-Benutzer, die ebenfalls für standortbasiertes Routing aktiviert sind und sich an verschiedenen Speicherorten befinden.  

|Speicherort des Zielbenutzer Endpunkts|Benutzer1 initiiert Anrufübertragung |Benutzer1 initiiert Anrufweiterleitung|
|---------|---------|---------|
|Gleiche Netzwerk Website wie Initiator (User2)|Zulässig|Zulässig|
|Unterschiedliche Netzwerk Website, Standort für standortbasiertes Routing (user3) aktiviert|Nicht zulässig|Nicht zulässig|
|Unterschiedliche Netzwerk Website, Website nicht aktiviert für standortbasiertes Routing (benutzer4)|Nicht zulässig|Nicht zulässig|
|Unbekanntes internes Netzwerk (User5)| Nicht zulässig|Nicht zulässig|
|Unbekanntes externes Netzwerk (Benutzer6)| Nicht zulässig|Nicht zulässig|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams, die den Anruf an den PSTN-Endpunkt übertragen oder weiterleiten

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing nicht aktiviert

- Das übertragen und Weiterleiten eines PSTN-Anrufs an eine andere PSTN-Nummer ist zulässig. 
- Beim übertragen und Weiterleiten eines eingehenden VoIP-Anrufs an das PSTN müssen die Einschränkungen für die Gebühren Umgehung des Anrufers berücksichtigt werden. 
    - Wenn der Anrufer nicht für standortbasiertes Routing aktiviert ist, kann er an ein beliebiges PSTN-Gateway übertragen werden, das für standortbasiertes Routing nicht aktiviert ist.
    - Wenn der Anrufer für standortbasiertes Routing aktiviert ist, kann er nur an ein standortbasiertes Routing aktiviertes Gateway übertragen werden, das sich am gleichen Netzwerkstandort befindet. 

#### <a name="user-enabled-for-location-based-routing"></a>Benutzer für standortbasiertes Routing aktiviert

- Übertragen und Weiterleiten eines PSTN-Anrufs an eine andere PSTN-Nummer muss das gleiche standortbasierte Routing aktiviert sein, auf dem der eingehende Anruf eingegangen ist. 
- Beim übertragen und Weiterleiten eines eingehenden VoIP-Anrufs an das PSTN müssen sowohl der Anrufer als auch die Gebühren Umgehungs Einschränkungen des Benutzers beachtet werden. 
    - Wenn der Anrufer nicht für standortbasiertes Routing aktiviert ist, kann er an ein beliebiges PSTN-Gateway übertragen werden, das für standortbasiertes Routing nicht aktiviert ist.
    - Wenn der Anrufer für standortbasiertes Routing aktiviert ist, kann er nur an ein standortbasiertes routingfähiges Gateway übertragen werden, das sich am gleichen Netzwerkstandort befindet.
 
Die folgende Tabelle zeigt, wie sich der standortbasierte Routing auf das Routing eines VoIP-Anrufs von Benutzer1 bei site1 an Benutzer an verschiedenen Speicherorten auswirkt, die den Anruf an einen PSTN-Endpunkt übertragen oder weiterleiten.  

|Benutzer initiiert Anrufübertragung oder Weiterleitung  |In PSTN übertragen  |Weiterleiten an PSTN  |
|---------|---------|---------|
|Gleiche Netzwerk Website, Standort aktiviert für standortbasiertes Routing (User2)   |Die Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der Benutzer2-VoIP-Routing Richtlinie, geroutet werden.         |Anrufweiterleitung kann nur durch standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der Benutzer2-VoIP-Routing Richtlinie, weitergeleitet werden.         |
|Unterschiedliche Netzwerk Website, Standort für standortbasiertes Routing (user3) aktiviert    |Die Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User3's-VoIP-Routing Richtlinie, geroutet werden.         |Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User3's-VoIP-Routing Richtlinie, geroutet werden.         |
|Unterschiedliche Netzwerk Website, Website nicht aktiviert für standortbasiertes Routing (benutzer4)    |Die Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User4's-VoIP-Routing Richtlinie, geroutet werden.         |Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User4's-VoIP-Routing Richtlinie, geroutet werden.         |
|Unbekanntes internes Netzwerk (User5)     |Die Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User5's-VoIP-Routing Richtlinie, geroutet werden.         |Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User5's-VoIP-Routing Richtlinie, geroutet werden.         |
|Unbekanntes externes Netzwerk (Benutzer6)   |Die Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User6's-VoIP-Routing Richtlinie, geroutet werden.        |Anrufweiterleitung kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der User6's-VoIP-Routing Richtlinie, geroutet werden.         |

### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, einen Anruf erhält und die gleichzeitige Klingel Funktion aktiviert ist, analysiert standortbasiertes Routing den Standort des anrufenden Teilnehmers und die Endpunkte der angerufenen Parteien, um zu ermitteln, ob der Anruf weitergeleitet werden soll. Das gleichzeitige Klingeln folgt denselben standortbasierten Regeln wie Anruf Übertragungen und Weiterleitungen. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Gleichzeitiges Klingeln für einen anderen Teams-Benutzer

In der folgenden Tabelle wird gezeigt, ob das ortsbasierte Routing das gleichzeitige Klingeln verschiedener Benutzer für einen eingehenden PSTN-Anruf für Benutzer1 ermöglicht.

|Speicherort des Zielbenutzer Endpunkts|Simultaner Ring  |
|---------|---------|
|Gleiche Netzwerk Website wie Initiator (User2)   |Zulässig         |
|Unterschiedliche Roaming-Netzwerk Website für standortbasiertes Routing aktiviert (user3)   |Nicht zulässig         |
|Roaming-Netzwerk Website nicht für standortbasiertes Routing aktiviert (benutzer4)   |Nicht zulässig        |
|Unbekanntes internes Netzwerk (User5)    | Nicht zulässig        |
|Unbekanntes externes Netzwerk (Benutzer6)    |Nicht zulässig        |
|Zielbenutzer ist eine PSTN-Nummer    |Der Anruf kann nur über standortbasierte Routing aktivierte Gateway1 bei site1, basierend auf der von Benutzer1-VoIP-Routing Richtlinie, geroutet werden.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Gleichzeitiges Klingeln an einem PSTN-Endpunkt

Die folgende Tabelle zeigt das standortbasierte Routing Verhalten für einen eingehenden VoIP-Anruf von Benutzer1, der sich in site1 befindet, für Benutzer an verschiedenen Speicherorten, wobei der gleichzeitige Ring auf eine PSTN-Nummer festgelegt ist. 

|Als Speicherort für Benutzer Endpunkt bezeichnet  |Das Ziel für das gleichzeitige Klingeln ist PSTN-Endpunkt |
|---------|---------|
|Gleiche Netzwerk Website, Standort aktiviert für standortbasiertes Routing (User2)    |Der Anruf kann nur durch standortbasierte Routing-Gateway1 bei site1, basierend auf der Benutzer2-VoIP-Routing Richtlinie, geroutet werden.       |
|Für standortbasiertes Routing (user3) ist eine andere Netzwerk Website aktiviert    |Der Anruf kann nur durch standortbasierte Routing-Gateway1 bei site1, basierend auf der User3's-VoIP-Routing Richtlinie, geroutet werden.        |
|Unterschiedliche Netzwerk Website für standortbasiertes Routing (benutzer4) nicht aktiviert    |Der Anruf kann nur durch standortbasierte Routing-Gateway1 bei site1, basierend auf der User4's-VoIP-Routing Richtlinie, geroutet werden.         |
|Unbekanntes internes Netzwerk (User5)    |Der Anruf kann nur durch standortbasierte Routing-Gateway1 bei site1, basierend auf der User5's-VoIP-Routing Richtlinie, geroutet werden.         |
|Unbekanntes externes Netzwerk (Benutzer6)   |Der Anruf kann nur durch standortbasierte Routing-Gateway1 bei site1, basierend auf der User6's-VoIP-Routing Richtlinie, geroutet werden.         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Eingehende Anrufe über die sprach-app (automatische Telefonzentrale oder Anrufwarteschlange)

Eingehende PSTN-Anrufe von einem standortbasierten Routing fähigen Gateway können mit einer automatischen Telefonzentrale oder einer Anrufwarteschlange verbunden werden. Benutzer, die für standortbasiertes Routing aktiviert sind, können nur eingehende Anruf Übertragungen von diesen Anwendungen empfangen, wenn Sie sich am gleichen Standort befinden, von dem der eingehende PSTN-Anruf stammt. 
 
Anrufweiterleitung und gleichzeitiges Klingeln an Benutzer und PSTN sind für sprach-App-Transfers zulässig. Das Abschließen des Anrufs an das Ziel unterliegt denselben standortbasierten Routing Regeln, die zuvor aufgeführt sind.  
 
Die Weiterleitung an Voicemail ist ebenfalls gestattet.  

### <a name="delegation"></a>Delegierung

Benutzer von Teams können Stellvertretungen auswählen, die in Ihrem Auftrag Anrufe tätigen und empfangen können. Die Delegierungsfunktionen in Teams sind vom standortbasierten Routing wie folgt betroffen: 
- Für ausgehende Anrufe von einem standortbasierten Routing fähigen Stellvertreter im Auftrag eines delegierenden gelten die gleichen Regeln. Das Anrufrouting basiert auf den Richtlinien für die Anruf Autorisierung der Stellvertretung, der VoIP-Routing Richtlinie und dem Standort. Weitere Informationen finden Sie unter [Teams-Benutzer platziert einen ausgehenden Anruf an das PSTN](#teams-user-places-an-outbound-call-to-the-pstn). 
- Für eingehende PSTN-Anrufe an einen Teilnehmer gelten die gleichen standortbasierten Routing Regeln, die für die Anrufweiterleitung gelten, oder gleichzeitiges Anrufen an andere Benutzer, auch für Stellvertretungen. Weitere Informationen finden Sie unter [Teams-Benutzer Transfers oder Weiterleiten eines Anrufs an einen anderen Teams-Benutzer](#teams-user-transfers-or-forwards-call-to-another-teams-user), [Teams, die den Anruf an den PSTN-Endpunkt weiterleiten oder ihn anrufen](#teams-user-transfers-or-forwards-call-to-pstn-endpoint), und [Gleichzeitiges Klingeln](#simultaneous-ringing). Wenn ein Stellvertreter einen PSTN-Endpunkt als Ziel für das gleichzeitige Klingeln festlegt, wird die VoIP-Routing Richtlinie der Stellvertretung verwendet, um den Anruf an das PSTN weiterzuleiten. 
- Für die Delegierung empfiehlt es sich, dass sich der delegator und die zugehörigen Stellvertretungen auf derselben Netzwerk Website befinden. 

## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Änderungen an einer lokalen standortbasierten Routing Bereitstellung

Die VoIP-Routing Richtlinie für Netzwerkstandorte wird nicht mehr verwendet. Stattdessen verwenden wir die VoIP-Routing Richtlinie des Benutzers. Das bedeutet, dass die VoIP-Routing Richtlinie die Gateways der Roaming-Websites enthalten muss, damit Benutzer zu anderen Websites wechseln können. 

### <a name="technical-considerations-for-location-based-routing"></a>Technische Überlegungen zum standortbasierten Routing

IPv4-und IPv6-Subnetze werden unterstützt, aber IPv6 hat Vorrang beim Überprüfen auf eine Übereinstimmung.

### <a name="client-support-for-location-based-routing"></a>Client Unterstützung für standortbasiertes Routing

Die folgenden Teams-Clients werden unterstützt:
- Teams-Desktop Clients (Windows und Mac)
- Teams Mobile Clients (IOS und Android)
- IP-Telefone für Teams

Die Microsoft Teams-WebClient-und Skype for Business-Clients werden nicht unterstützt.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Standortbasiertes Routing gilt nicht für die folgenden Arten von Interaktionen. Standortbasiertes Routing wird nicht erzwungen, wenn die Endpunkte von Teams mit PSTN-Endpunkten in den folgenden Szenarien interagieren: 
- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen 
- Ein lokales Skype for Business-Benutzer oder ein Skype for Business Online-Benutzer ruft einen Teams-Nutzer an.  

### <a name="location-based-routing-for-conferencing"></a>Orts basiertes Routing für Konferenzen

Ein standortbasierter Routing aktivierter Benutzer für einen PSTN-Anruf ist nicht berechtigt, eine Konferenz mit einem anderen Benutzer oder einer anderen PSTN-Nummer zu starten. Das Herstellen einer Verbindung mit automatischen Telefonzentralen oder Anrufwarteschlangen ist zulässig. Wenn der Benutzer eine Konferenz Lizenz hat, muss der Benutzer eine Konferenz mit den entsprechenden Benutzern starten und das PSTN über die Konferenzbrücke anrufen, um einen Konferenzanruf zu starten.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>Medien Umgehungs Anforderung für standortbasiertes Routing

Wenn Sie ein standortbasiertes Routing in Indien bereitstellen, müssen Sie auch die medienumgehung konfigurieren. Weitere Informationen finden Sie unter [Planen der medienumgehung mit direktem Routing](direct-routing-plan-media-bypass.md) und [lokaler Medienoptimierung für das direkte Routing](direct-routing-media-optimization.md).

## <a name="next-steps"></a>Nächste Schritte

Wechseln Sie zu [Konfigurieren von Netzwerkeinstellungen für standortbasiertes Routing](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>Verwandte Themen

- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Netzwerkeinstellungen für Cloud-Sprachfeatures in Teams](cloud-voice-network-settings.md)
