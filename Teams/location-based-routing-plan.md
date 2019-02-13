---
title: Planen des standortbasierten Routings für direktes Routing
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.service: msteams
ms.reviewer: roykuntz
search.appverid: MET150
description: Erfahren Sie, wie speicherortbasierte Routing für die direkte Weiterleitung zu planen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8faf0f70b509a851b8365bea5ce4a69a57f198d1
ms.sourcegitcommit: 09c2094104ee055cb1cb047a5fab8f9fd02b123e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "29967456"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>Planen des standortbasierten Routings für direktes Routing

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>Übersicht über die Standortbasierte Weiterleitung

In einigen Ländern und Regionen ist es nicht zulässig, die den Anbieter (Public Switched Telephone Network, PSTN) zur Verringerung der Kosten für Ferngespräche aufrufende umgehen. In diesem Artikel wird beschrieben, wie mit Routing speicherortbasierte gebührenpflichtige Umgehung für Microsoft-Teams von Benutzern basierend auf ihrem geografischen Standort einschränken. Dieser Artikel gilt nur für Telefon System direkten Routing.

Hier erhalten Sie eine Übersicht über speicherortbasierte Routing und Hinweise zur einfacheren dafür zu planen. Wenn Sie sind, zum Anwenden und standortbasierte Routing aktivieren soweit, finden Sie unter:
- [Bereitstellen von Netzwerkeinstellungen für standortbasierte Routing](location-based-routing-configure-network-settings.md)
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)

Speicherortbasierte Routing ist ein Feature, mit dem Sie gebührenpflichtige Umgehung basierend auf Gruppenrichtlinien und geografischen Standort des Benutzers zum Zeitpunkt der eine eingehende oder ausgehende PSTN-Anruf einschränken kann. 

Wenn ein Benutzer Teams für standortbasierte Routing aktiviert ist, gilt Folgendes:
- Um eine ausgehende PSTN-Anruf zu tätigen, muss eines der folgenden wahr sein:
    - Endpunkt des Benutzers befindet sich in einem Netzwerkstandort, die für standortbasierte Routing- und Anrufe Ausgang über das entsprechende Gateway aktiviert ist, die für das Routing speicherortbasierte aktiviert ist. 
    - Endpunkt des Benutzers befindet sich in einem Netzwerkstandort, die nicht für standortbasierte Routing aktiviert ist und ruft Ausgang über ein Gateway, das für standortbasierte Routing nicht aktiviert ist.

    Ausgehende Anrufe sind in anderen Szenarien nicht zulässig.

- Wenn einen eingehenden PSTN-Anruf annehmen möchten, muss antwortenden Endpunkt des Benutzers am gleichen Standort Netzwerk befinden, in dem der Anruf Ingresses über das Gateway, das für das Routing speicherortbasierte aktiviert ist. In anderen Szenarien ist beispielsweise, wenn der Benutzer roaming der Aufruf ist nicht zulässig, und wird an den Benutzer Anrufweiterleitungseinstellungen (normalerweise Voicemail) weitergeleitet.
- Um einen PSTN-Anruf an einen anderen Benutzer von Teams, das Ziel übertragen muss Endpunkt des Benutzers am gleichen Standort Netzwerk wie der Benutzer befinden, die die Datenübertragung initiiert. Überträgt sind in anderen Szenarien nicht zulässig. 
- Um einen anderen Benutzer von Teams an das Telefonfestnetz zu übertragen, muss über ein befindet sich am selben Netzwerkstandort wie der anfänglichen Aufrufer speicherortbasierte Routing aktiviert Gateway der Anruf weitergeleitet werden. Überträgt sind in anderen Szenarien nicht zulässig.

Speicherortbasierte Routing verwendet die gleichen Netzwerk Region, Standort- und Subnetz Definitionen, die Skype für Business Server verwendet. Wenn gebührenpflichtige Umgehung für einen Standort eingeschränkt ist, ordnet ein Administrator jedes IP-Subnetz sowie jedes PSTN-Gateway für diesen Standort zu einem Netzwerkstandort zu. Standort des Benutzers wird durch das IP-Subnetz bestimmt, die die Endpunkte der Benutzer Teams zum Zeitpunkt der PSTN-Anruf verbunden sind. Ein Benutzer möglicherweise mehrere Teams Clients an verschiedenen Standorten befindet sich in diesem Fall erzwingt speicherortbasierte Routing des Clients routing separat je nach den Speicherort des Endpunkts. 

Wenn für einige der in diesem Artikel verwendeten Netzwerk Terminologie vertraut erhalten möchten, finden Sie unter [Routing speicherortbasierte Terminologie](location-based-routing-terminology.md).

## <a name="apply-location-based-routing"></a>Standortbasierte Weiterleitung anwenden

Sie müssen Benutzer, Netzwerkstandorten und PSTN-Gateways speicherortbasierte Routing zuweisen.  

### <a name="apply-location-based-routing-at-the-user-location"></a>Speicherortbasierte Routing an der Position Benutzer anwenden

Wie bereits erwähnt, gilt speicherortbasierte Routing nur für Benutzer, die für die direkte Weiterleitung eingerichtet sind. Speicherortbasierte Routing gilt nicht für Benutzer, die für das Planen von Aufrufen eingerichtet sind. Benutzer müssen für standortbasierte Routing aktiviert sein, wenn sie unter gebührenpflichtige Umgehung Einschränkung, sind die steuert die Bedingungen, in denen sie tätigen und Empfangen von PSTN-Anrufe und das PSTN-Gateway, das verwendet werden können. Wenn ein Benutzer, der für das Routing speicherortbasierte aktiviert ist an einem Standort, die für das Routing speicherortbasierte aktiviert ist befindet, muss der Benutzer Anrufe über ein speicherortbasierte Routing aktiviert Gateway mit der Website verbunden tätigen. 

Speicherortbasierte Routing funktioniert, indem aktuellen Standort des Benutzers basierend auf der IP-Adresse des Benutzers Teams Endpunkt und wendet die Regeln entsprechend anpassen. Der Speicherort eines Benutzers für standortbasierte Routing aktiviert ist, kann auf folgende Weise unterteilt werden: 
- **Der Benutzer befindet sich am selben Speicherort-basierte Routing aktiviert Standort, der PSTN-Gateway zugeordnet ist, wo ihre DID zugewiesen ist.**<br>In diesem Szenario wird der Benutzer in einem bekannten Netzwerkstandort gespeichert, der für die standortbasierte Routing- und des Benutzers (Direct Inward Dial DIALING) Anzahl auf ein PSTN-Gateway beendet wird, die in den gleichen Netzwerkstandort ist aktiviert ist. Beispielsweise ist der Benutzer ihre Büro. 
- **Der Benutzer befindet sich an einem anderen Speicherort-basierte Routing aktiviert Standort nicht, PSTN-Gateway zugeordnet ist, die, wo ihre DID zugewiesen ist.**<br>In diesem Szenario befindet sich des Benutzers in einem bekannten Netzwerkstandort, der für das Routing speicherortbasierte aktiviert ist, und diese Website nicht das PSTN-Gateway zugeordnet, denen der Benutzer DID-Nummer zugewiesen. Beispielsweise wird der Benutzer zu einer anderen Office übermittelt.  
- **Der Benutzer befindet sich auf eine interne Website, die für das Routing speicherortbasierte nicht aktiviert ist.** <br>In diesem Szenario ist der Benutzer in einer bekannten internen Netzwerk-Website gespeichert, der für standortbasierte Routing nicht aktiviert ist. 
- **Der Benutzer befindet sich an einem unbekannten Standort.** 
    - Der Benutzer befindet sich innerhalb des internen Netzwerks, die nicht als einem Netzwerkstandort definiert ist. 
    - Der Benutzer befindet sich außerhalb des internen Netzwerks. Beispielsweise ist der Benutzer im Internet zu Hause oder in einem Café. 

### <a name="apply-location-based-routing-at-the-network-site"></a>Speicherortbasierte Routing unter den Netzwerkstandort anwenden 
Netzwerkstandorte müssen für standortbasierte Routing, um festzustellen, welche Gateways speicherortbasierte Routing aktivierten Benutzer weitergeleitet, beim roaming aktiviert sein. Wenn ein Benutzer, der für das Routing speicherortbasierte aktiviert ist für einen Standort, die für das Routing speicherortbasierte aktiviert ist wechselt, kann nur das PSTN-Gateway, das für das Routing an diesem Standort speicherortbasierte aktiviert ist für ausgehende Anrufe verwendet werden. Wenn ein Benutzer, der für das Routing speicherortbasierte aktiviert ist, eine Website, die für das Routing speicherortbasierte nicht aktiviert ist wechselt, kann alle Gateways, die nicht für standortbasierte Routing aktiviert ist für ausgehende Anrufe verwendet werden.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>Anwenden von speicherortbasierte Routing an das PSTN-gateway 

Gateways werden Websites, um zu bestimmen, wo ein Benutzer, der für das Routing speicherortbasierte aktiviert ist befinden kann beim tätigen oder eines Anrufs PSTN annehmen zugeordnet. Gateways müssen aktiviert sein, für das Routing speicherortbasierte, um sicherzustellen, dass es unter gebührenpflichtige Umgehung der Einschränkungen ist und kann nicht verwendet werden, durch die Benutzer, die für das Routing speicherortbasierte nicht aktiviert ist. Dieses Gateway kann an mehreren Standorten zugeordnet werden und können so konfiguriert, dass für standortbasierte Routing aktiviert werden soll oder nicht für standortbasierte Routing, abhängig von der Website aktiviert. 

## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

Dieser Abschnitt beschreibt verschiedene Szenarien für das Einschränken gebührenpflichtige Umgehung mithilfe von speicherortbasierte Routing und vergleicht wie Anrufe für Benutzer weitergeleitet werden, die für das Routing speicherortbasierte mit Benutzern nicht aktiviert sind, die für das Routing speicherortbasierte aktiviert sind.

- [Teams Benutzer tätigt einen ausgehenden Anruf an das Telefonfestnetz](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams Benutzer erhält einen eingehenden Anruf über das PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams Benutzer überträgt oder leitet Anruf an einen anderen Benutzer von Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams Benutzer überträgt oder leitet Anrufe an PSTN-Endpunkt](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [Paralleles Anrufen](#simultaneous-ringing)
- [Delegierung](#delegation)

Das folgende Diagramm zeigt die Einschränkungen durch standortbasierte Routing in jedem Szenario aktiviert. Haben einen Rahmen Benutzer, Netzwerkstandorten und Gateways, die für das Routing speicherortbasierte aktiviert sind. Verwenden Sie das Diagramm als Leitfaden zur einfacheren standortbasierte Routing in jedem Szenario verstanden haben.  

![Diagramm zeigt die Szenarien für standortbasierte Routing] (media/lbr-direct-routing.png "Diagramm zeigt die Szenarien für standortbasierte Routing")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams Benutzer tätigt einen ausgehenden Anruf an das Telefonfestnetz

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer, die für das Routing speicherortbasierte nicht aktiviert

Ein Benutzer, der für das Routing speicherortbasierte nicht aktiviert ist kann stellen Sie ausgehende Anrufe mit Gateway an jedem beliebigen Standort, die für standortbasierte Routing über ihre zugewiesenen VoIP-routing-Richtlinie nicht aktiviert ist. Jedoch, wenn ein Gateway für standortbasierte Routing aktiviert ist, der Benutzer ausgehende Anrufe über das Gateway nicht möglich, auch wenn sie ihre VoIP-routing-Richtlinie zugewiesen wurde. Wenn der Benutzer auf einer Website, die für das Routing speicherortbasierte aktiviert ist wechselt, können sie nur Anrufe über ihre normalen routing Gateways vornehmen, die für das Routing speicherortbasierte nicht aktiviert ist.
 
#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter speicherortbasierte Routing
Im Vergleich ist das routing von ausgehenden Anrufen für Benutzer, die für das Routing speicherortbasierte aktiviert sind die Netzwerkadresse der Endpunkt des Benutzers betroffen. Die folgende Tabelle zeigt die standortbasierte Routing wirkt sich auf das routing von ausgehenden Anrufen User1, je nach Standort User1. 

|Benutzer1 Endpunktposition  |Weiterleiten von ausgehenden Anrufen nach ' User1 '  |
|---------|---------|
|Gleicher, wo des Benutzers DID zugewiesen ist, Standort für standortbasierte Routing (Site1) aktiviert      |Rufen Sie über das Gateway, das für standortbasierte Routing (GW1), am Site1 aktiviert ist, basierend auf VoIP-Routingrichtlinie des Benutzers weitergeleitet         |
|Anderen Standort als, wo des Benutzers DID zugewiesen ist, aktiviert die Website für standortbasierte Routing (Site2)    |Anruf weitergeleitet über Gateway, das für standortbasierte Routing (GW2) unter Roaming Site2, aktiviert wird basierend auf VoIP-Routingrichtlinie des Benutzers        |
|Anderen Standort als, in dem des Benutzers DID zugewiesen wird, wird nicht aktiviert für standortbasierte Routing (Site3) Website  |Rufen Sie über das Gateway, das nicht für standortbasierte Routing auf der Website aktiviert ist, die nicht für standortbasierte Routing (GW3), basierend auf VoIP-Routingrichtlinie des Benutzers aktiviert hat weitergeleitet       |
|Unbekannte internen Netzwerk (Location4)    |  Öffentliche Telefonnetz nicht zulässig       |
|Unbekannte externes Netzwerk (Location5)    | Öffentliche Telefonnetz nicht zulässig        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams Benutzer erhält einen eingehenden Anruf über das PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer, die für das Routing speicherortbasierte nicht aktiviert

Ein Benutzer, der für das Routing speicherortbasierte nicht aktiviert ist, kann einen eingehenden Anruf vom Gateway empfangen, die nicht für standortbasierte Routing aktiviert ist, von dem der zugeordneten Ingresses Zahl. Wenn der Benutzer auf einer Website, die für das Routing speicherortbasierte nicht aktiviert ist wechselt, können sie weiterhin Anrufe über ihre normalen PSTN-Gateways empfangen.
  
#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter speicherortbasierte Routing

Im Vergleich können für standortbasierte Routing aktivierte Benutzer nur eingehende Anrufe vom PSTN-Gateway erhalten, denen Ihre DID zugewiesen ist, wenn diese sich am selben Standort befinden. In der folgenden Tabelle wird veranschaulicht, wie User1 eingehende Anrufe empfängt, wenn User1 zu verschiedenen Arten von Netzwerkadressen wechselt. Wenn der Anruf an den Endpunkt des Benutzers weitergeleitet nicht zur Verfügung, geht es zur des Benutzers Anrufweiterleitungseinstellungen, wenn die Einstellungen konfiguriert sind. In der Regel ist dies Voicemail.  

|Benutzer1 Endpunktposition  |Routing von eingehenden Anrufen an User1  |
|---------|---------|
|Selben Standort befinden wie in dem DID des Benutzers zugewiesen wird, Website für standortbasierte Routing (Site1) aktiviert.   | An der Benutzer1s Endpunkt in Site1 weitergeleitete Anrufe        |
|Anderen Standort als, wo des Benutzers DID zugewiesen ist, aktiviert die Website für standortbasierte Routing (Site2)    | Nicht an Endpunkten in Site2 weitergeleitete Anrufe        |
|Anderen Standort als, in dem des Benutzers DID zugewiesen wird, wird nicht aktiviert für standortbasierte Routing (Site3) Website    | Nicht an Endpunkten in Site3 weitergeleitete Anrufe        |
|Unbekannte internen Netzwerk (Location4)   | Nicht an Endpunkten in Location4 weitergeleitete Anrufe        |
|Unbekannte externes Netzwerk (Location5)     | Nicht an Endpunkten in Location5 weitergeleitete Anrufe        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams Benutzer überträgt oder leitet Anruf an einen anderen Benutzer von Teams

Wenn ein PSTN-Endpunkt beteiligt ist, Routing speicherortbasierte analysiert, ob eine oder beide Benutzer für das Routing speicherortbasierte aktiviert sind und bestimmt, ob der Anruf weitergeleitet oder je nach den Speicherort der beide Endpunkte weitergeleitet werden soll. 
 
Anruf weiterleiten erfordert auslösenden Benutzer, um den Anruf zu übernehmen, während die anrufweiterleitung den anfänglichen Anruf beantwortet werden keine erforderlich sind. Dies bedeutet, dass Anrufe weitergeleitet werden können, selbst wenn nicht User1 am ein Speicherort zum Empfangen von eingehenden Anrufen (siehe Tabelle im Abschnitt [Teams Benutzer erhält einen eingehenden Anruf aus dem Telefonfestnetz](#teams-user-receives-an-inbound-call-from-the-pstn) ) und Anrufe können nicht übertragen werden, wenn User1 den eingehenden Anruf empfangen kann. 

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer, die für das Routing speicherortbasierte nicht aktiviert

Ein Benutzer, der für das Routing speicherortbasierte nicht aktiviert ist, kann übertragen oder forward PSTN-Anrufe an andere Benutzer, die für das Routing speicherortbasierte nicht aktiviert ist. Der Benutzer in der Regel nicht kann zum Übertragen von oder vorwärts PSTN-Anruf an einen Benutzer, die für das Routing speicherortbasierte aktiviert ist, weil speicherortbasierte Routing Benutzer aktiviert in der Regel nur dürfen am Gateways für PSTN speicherortbasierte Routing aktiviert werden Anrufe. Die Ausnahme ist, wenn ein Routing speicherortbasierte Benutzer wechselt zu einer Website, die nicht für standortbasierte Routing aktiviert ist aktiviert. In diesem Szenario wird die übertragenen Anrufs zugelassen.  

Ebenso ein Benutzer, der für das Routing speicherortbasierte nicht aktiviert ist kann nur eine Übertragung empfangen oder weitergeleitet PSTN-Anruf von einem anderen Benutzer, die für das Routing speicherortbasierte nicht aktiviert ist. 

#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter speicherortbasierte Routing

Im Allgemeinen ist durchstellen und Weiterleiten eingehender PSTN-Anrufe von einem Gateway, das für das Routing speicherortbasierte aktiviert ist nur zulässig, wenn die Zielbenutzer für standortbasierte Routing aktiviert ist und am selben Standort befindet. Andernfalls ist durchstellen und Weiterleiten von Anrufen nicht zulässig. 

In der folgenden Tabelle wird beschrieben, ob Anruf weiterleiten und Anruf Übertragungen je nach dem Ort des Zielbenutzers zulässig sind. In dieser Tabelle initiiert User1, befindet sich im Site1, die Übertragung oder Weiterleiten an andere Benutzer Teams, die auch für standortbasierte Routing aktiviert sind und Personen an verschiedenen Standorten sind.  

|Zielspeicherort Benutzer-Endpunkt|Benutzer1 initiiert Anruf weiterleiten |Benutzer1 initiiert Anruf weiterleiten|
|---------|---------|---------|
|Gleiche Netzwerkstandort als Initiator (Benutzer2)|Zulässig|Zulässig|
|Verschiedene Netzwerkstandort Standort für standortbasierte Routing (User3) aktiviert|Nicht zulässig|Nicht zulässig|
|Verschiedene Netzwerkstandort Standort für standortbasierte Routing (User4) nicht aktiviert.|Nicht zulässig|Nicht zulässig|
|Unbekannte internen Netzwerk (User5)| Nicht zulässig|Nicht zulässig|
|Unbekannte externes Netzwerk (User6)| Nicht zulässig|Nicht zulässig|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams Benutzer überträgt oder leitet Anrufe an PSTN-Endpunkt

#### <a name="user-not-enabled-for-location-based-routing"></a>Benutzer, die für das Routing speicherortbasierte nicht aktiviert

- Übertragen und Weiterleiten von PSTN-Anruf an eine andere PSTN-Nummer ist zulässig. 
- Durchstellen und Weiterleiten eines eingehenden VOIP-Anrufs an das Telefonfestnetz müssen des Anrufers gebührenpflichtige Umgehung der Einschränkungen beachtet. 
    - Wenn der Aufrufer für standortbasierte Routing nicht aktiviert ist, können sie auf alle PSTN-Gateway übertragen werden, die für das Routing speicherortbasierte nicht aktiviert ist.
    - Wenn der Aufrufer für standortbasierte Routing aktiviert ist, können sie nur mit einem speicherortbasierte Routing aktiviert Gateway befindet sich am selben Netzwerkstandort übertragen werden. 

#### <a name="user-enabled-for-location-based-routing"></a>Benutzer mit aktivierter speicherortbasierte Routing

- Durchstellen und Weiterleiten eingehender eine PSTN an eine andere PSTN-Nummer heraus, die auf der eingehende Anruf eingegangen speicherortbasierte Routing aktiviert dieses Gateway weitergeleitet werden muss. 
- Durchstellen und Weiterleiten eines eingehenden VOIP Anruf an das Telefonfestnetz muss sowohl den Aufrufer berücksichtigt und gewählte Benutzer gebührenpflichtige umgehen Einschränkungen. 
    - Wenn der Aufrufer für standortbasierte Routing nicht aktiviert ist, können sie auf alle PSTN-Gateway übertragen werden, die für das Routing speicherortbasierte nicht aktiviert ist.
    - Wenn der Aufrufer für standortbasierte Routing aktiviert ist, können sie nur werden übertragen werden mit einem speicherortbasierte Routing aktiviert Gateway befindet sich am selben Netzwerkstandort.
 
Die folgende Tabelle zeigt die standortbasierte Routing wirkt sich auf das routing von einen VOIP-Anruf von Benutzer1 unter Site1 für Benutzer in unterschiedlichen Standorten, die übertragen oder den Anruf an einen PSTN-Endpunkt weiterzuleiten.  

|Anruf weiterleiten oder Weiterleiten Benutzer initiieren  |Weiterleiten an PSTN  |Weiterleiten an PSTN  |
|---------|---------|---------|
|Gleiche Netzwerkstandort Standort für standortbasierte Routing (Benutzer2) aktiviert   |Anruf, dass die Übertragung nur über speicherortbasierte Routing weitergeleitet werden kann aktiviert Gateway1 unter Site1, basierend auf der Benutzer2s VoIP-routing-Richtlinie         |Anruf weiterleiten kann nur über speicherortbasierte Routing geleitet aktiviert Gateway1 unter Site1, basierend auf der Benutzer2s VoIP-routing-Richtlinie         |
|Verschiedene Netzwerkstandort Standort für standortbasierte Routing (User3) aktiviert    |Anruf, dass die Übertragung nur über speicherortbasierte Routing weitergeleitet werden kann aktiviert Gateway1 unter Site1, basierend auf User3s VoIP-routing-Richtlinie         |Anruf weiterleiten kann nur über speicherortbasierte Routing geleitet werden Gateway1 unter Site1, basierend auf User3s VoIP-routing-Richtlinie aktiviert         |
|Verschiedene Netzwerkstandort Standort für standortbasierte Routing (User4) nicht aktiviert.    |Anruf, dass die Übertragung nur über speicherortbasierte Routing weitergeleitet werden kann aktiviert Gateway1 unter Site1, basierend auf User4s VoIP-routing-Richtlinie         |Anruf weiterleiten kann nur über speicherortbasierte Routing geleitet werden Gateway1 unter Site1, basierend auf User4s VoIP-routing-Richtlinie aktiviert         |
|Unbekannte internen Netzwerk (User5)     |Anruf, dass die Übertragung nur über speicherortbasierte Routing weitergeleitet werden kann aktiviert Gateway1 unter Site1, basierend auf User5s VoIP-routing-Richtlinie         |Anruf weiterleiten kann nur über speicherortbasierte Routing geleitet werden Gateway1 unter Site1, basierend auf User5s VoIP-routing-Richtlinie aktiviert         |
|Unbekannte externes Netzwerk (User6)   |Anruf, dass die Übertragung nur über speicherortbasierte Routing weitergeleitet werden kann aktiviert Gateway1 unter Site1, basierend auf User6s VoIP-routing-Richtlinie        |Anruf weiterleiten kann nur über speicherortbasierte Routing geleitet werden Gateway1 unter Site1, basierend auf User6s VoIP-routing-Richtlinie aktiviert         |

### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn ein Benutzer, die für standortbasierte Routing aktiviert ist, eines Anrufs erhält und Gleichzeitiges Klingeln aktiviert hat, analysiert speicherortbasierte Routing an dem Standort des Anrufers sowie die Endpunkte der gewählte Parteien um festzustellen, ob der Anruf weitergeleitet werden sollen. Gleichzeitiges Klingeln folgt dieselben Regeln speicherortbasierte Anruf überträgt und weiterleitet. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>Gleichzeitiges Klingeln für einen anderen Benutzer von Teams

In der folgenden Tabelle wird beschrieben, ob Routing speicherortbasierte Gleichzeitiges Klingeln auf unterschiedliche Benutzer für einen eingehenden Anruf PSTN für User1 ermöglicht.

|Zielspeicherort Benutzer-Endpunkt|Gleichzeitiges Klingeln  |
|---------|---------|
|Gleiche Netzwerkstandort als Initiator (Benutzer2)   |Zulässig         |
|Verschiedene servergespeicherten Netzwerkstandort für standortbasierte Routing (User3) aktiviert   |Nicht zulässig         |
|Servergespeicherten Netzwerkstandort für standortbasierte Routing (User4) nicht aktiviert.   |Nicht zulässig        |
|Unbekannte internen Netzwerk (User5)    | Nicht zulässig        |
|Unbekannte externes Netzwerk (User6)    |Nicht zulässig        |
|Zielbenutzer ist eine PSTN-Nummer    |Anruf kann nur über speicherortbasierte Routing geleitet werden Gateway1 unter Site1, basierend auf der Benutzer1s VoIP-routing-Richtlinie aktiviert      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>Gleichzeitiges Klingeln zu einem PSTN-Endpunkt

Die folgende Tabelle zeigt speicherortbasierte Routing Verhalten für einen eingehenden Anruf VOIP von User1 befindet sich unter Site1 für Benutzer in unterschiedlichen Standorten mit Gleichzeitiges Klingeln auf eine PSTN-Nummer festgelegt. 

|Endpunktposition gewählte Benutzer  |Gleichzeitiges Klingeln Ziel ist PSTN-Endpunkt |
|---------|---------|
|Gleiche Netzwerkstandort Standort für standortbasierte Routing (Benutzer2) aktiviert    |Anrufe können werden nur weitergeleitet werden über speicherortbasierte Routing Gateway1 unter Site1, basierend auf VoIP-Routingrichtlinie von Benutzer2       |
|Verschiedene Netzwerkstandort für standortbasierte Routing (User3) aktiviert    |Anruf kann nur über speicherortbasierte Routing Gateway1 unter Site1, basierend auf VoIP-Routingrichtlinie des User3 weitergeleitet werden        |
|Verschiedene Netzwerkstandort für standortbasierte Routing (User4) nicht aktiviert.    |Anruf kann nur über speicherortbasierte Routing Gateway1 unter Site1, basierend auf VoIP-Routingrichtlinie des User4 weitergeleitet werden         |
|Unbekannte internen Netzwerk (User5)    |Anruf kann nur über speicherortbasierte Routing Gateway1 unter Site1, basierend auf User5s VoIP-Routingrichtlinie weitergeleitet werden         |
|Unbekannte externes Netzwerk (User6)   |Anruf kann nur über speicherortbasierte Routing Gateway1 unter Site1, basierend auf User6s VoIP-Routingrichtlinie weitergeleitet werden         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>Eingehende Anrufe über VoIP-app (automatische Telefonzentrale oder rufen Sie Warteschlange)

Eingehende PSTN-Anrufe von einem Gateway speicherortbasierte Routing aktiviert eine automatische Telefonzentrale oder ein Anruf Warteschlange herstellen dürfen. Speicherortbasierte Routing-fähigen Benutzer können nur eingehenden Anruf Übermittlung einer Anwendung erhalten, wenn diese sich am selben Standort befinden, die eingehende PSTN-Anruf stammt. 
 
Die anrufweiterleitung und Gleichzeitiges Klingeln zu Benutzern und PSTN ist für VoIP-app-Übermittlung zulässig. Beenden den Anruf an das Ziel unterliegt den gleichen speicherortbasierte Routing-Regeln, die zuvor aufgeführten ab.  
 
Weiterleitung an die Voicemail ist ebenfalls zulässig.  

### <a name="delegation"></a>Delegierung

Ein Benutzer Teams kann Delegaten auswählen, tätigen und Entgegennehmen von Anrufen in ihrem Auftrag kann. Delegierungsfunktionen in Teams sind wie folgt von speicherortbasierte Routing betroffen: 
- Für ausgehende Anrufe von einem Speicherort-basierte Routing aktiviert Delegaten im Namen einer Person gelten dieselben Regeln. Anrufrouting basiert auf der Stellvertretung Anruf Autorisierungsrichtlinie, VoIP-Routingrichtlinie und Ort. Weitere Informationen finden Sie unter [Teams Benutzer einen ausgehenden Anruf an das Telefonfestnetz platziert](#teams-user-places-an-outbound-call-to-the-pstn). 
- Für eingehende PSTN-Anrufe an eine Person dieselben speicherortbasierte Routing Regeln, die gelten für die anrufweiterleitung oder Gleichzeitiges Anrufen an andere Benutzer gelten auch für Stellvertretungen. Weitere Informationen finden Sie unter [Teams Benutzer überträgt oder leitet Anruf an einen anderen Benutzer von Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user), [Teams Benutzer überträgt oder leitet Anrufe an PSTN-Endpunkt](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)und [Gleichzeitiges Klingeln](#simultaneous-ringing). Wenn ein Stellvertreter einen PSTN-Endpunkt als Ziel Gleichzeitiges Klingeln festlegt, wird die VoIP-Routingrichtlinie des Delegaten den Anruf an das PSTN weitergeleitet. 
- Für die Delegierung empfiehlt es sich, dass die Delegator und die entsprechenden Delegaten im gleichen Netzwerkstandort befinden. 

## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>Änderungen aus einer lokalen speicherortbasierte Routing-Bereitstellung

Netzwerk-Website, VoIP-routing-Richtlinie wird nicht mehr verwendet. In diesem Fall verwenden wir VoIP-Routingrichtlinie des Benutzers. Das heißt, damit Benutzer auf andere Standorte zugreifen können, die VoIP-routing-Richtlinie die Gateways servergespeicherten Websites umfassen muss. 

### <a name="technical-considerations-for-location-based-routing"></a>Technische Überlegungen zum standortbasierten Routing

IPv4 und IPv6-Subnetze werden unterstützt, IPv6 hat jedoch Vorrang vor, wenn für eine Übereinstimmung überprüfen. Unterstützung für IPv6 ist derzeit in Arbeit und wird durch allgemeine Verfügbarkeit (GA) für das Routing speicherortbasierte verfügbar sein. 

### <a name="client-support-for-location-based-routing"></a>Client-Unterstützung für standortbasierte Routing

Die folgenden Teams Clients werden unterstützt:
- Teams Desktopclients (Windows und Mac)
- Teams mobilen Clients (iOS und Android)
- Teams IP-Telefone

Die WebClient-Teams und Skype für Business Clients werden nicht unterstützt.

### <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Speicherortbasierte Routing gilt nicht für die folgenden Typen von Interaktionen. Speicherortbasierte Routing wird nicht erzwungen, wenn der Interaktion von Teams Endpunkten mit PSTN-Endpunkten in den folgenden Szenarien: 
- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen 
- Eine lokale Skype für Geschäftsbenutzer oder einen Skype für Business Online-Benutzer Ruft einen Teams Benutzer  

### <a name="location-based-routing-for-conferencing"></a>Standortbasierte Weiterleitung für Konferenzen

Ein speicherortbasierte Routing aktiviert Benutzer auf eine PSTN-Anruf ist nicht zulässig zum Starten einer Konferenz mit einem anderen Benutzer oder eine PSTN-Nummer. Herstellen einer Verbindung mit der automatischen Telefonzentralen oder Anruf Warteschlangen ist zulässig. Wenn der Benutzer eine Live Meeting-Lizenz verfügt, muss der Benutzer Starten einer Konferenz mit den entsprechenden Benutzern und rufen Sie das PSTN über die Konferenzbrücke zum Starten einer Telefonkonferenz.  

## <a name="next-steps"></a>Nächste Schritte
Wechseln Sie zur [Netzwerkeinstellungen für standortbasierte Routing konfigurieren](location-based-routing-configure-network-settings.md).

### <a name="related-topics"></a>Verwandte Themen
- [Aktivieren des standortbasierten Routings für direktes Routing](location-based-routing-enable.md)
- [Terminologie für das standortbasierte Routing](location-based-routing-terminology.md)