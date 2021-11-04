---
title: Planen des standortbasierten Routings in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planung für standortbasiertes Routing in Skype for Business Server Enterprise-VoIP, einschließlich Interaktion mit gleichzeitiges Klingeln und Delegierung sowie unterstützte Szenarien für standortbasiertes Routing.
ms.openlocfilehash: 928a44ed9484f1766013404d23b61a2cc56841d2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741972"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planen des standortbasierten Routings in Skype for Business

Planung für standortbasiertes Routing in Skype for Business Server Enterprise-VoIP, einschließlich Interaktion mit gleichzeitiges Klingeln und Delegierung sowie unterstützte Szenarien für standortbasiertes Routing.

Location-Based Routing ermöglicht es, das Routing von Anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Anrufbeteiligten einzuschränken. Location-Based Routing ist ein Anrufverwaltungsfeature, das steuert, wie Anrufe von Skype for Business Server weitergeleitet werden. Es erzwingt Anrufautorisierungsregeln, ob Anrufe basierend auf dem geografischen Standort des Skype for Business Anrufers an Nebenstellen- oder PSTN-Endpunkte weitergeleitet werden können.

Location-Based Routing führt einen neuen Satz von Regeln ein, mit denen das Routing von nationalen und internationalen PSTN-Anrufen geändert wird, um eine Gebührenumgehung zu verhindern. Location-Based Routing bietet die Flexibilität, diese Regeln auf bestimmte Regionen, bestimmte Gateways oder nur auf bestimmte Benutzergruppen zu beschränken.

Die folgenden Szenarien veranschaulichen die wichtigsten Arten von Einschränkungen, Location-Based Routing erzwingen kann:

- Egress Anrufe : Location-Based Routing kann ausgehende Anrufe erzwingen, um an ein PSTN-Gateway zu gehen, das sich in derselben Region befindet, in der sich der Anrufer befindet, um eine gebührenpflichtige PsTN-Umgehung zu verhindern. Dadurch wird verhindert, dass Anrufe an ein PSTN-Gateway in einer anderen Region als der Anrufer gesendet werden.

- Eingehende Anrufe – Location-Based Routing kann eingehende PSTN-Anrufe zum Klingeln Skype for Business Endpunkten verhindern, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleitet, nicht in derselben Region wie der angerufene Skype for Business-Benutzer befindet.

- Unbekannte Regionen – Location-Based Routing schränkt eingehende und ausgehende PSTN-Anrufe an und von Benutzern ein, die sich an unbestimmten Standorten befinden (d. h. Remotebenutzer, die über das Internet eine Verbindung herstellen oder sich in unbekannten Regionen befinden).

- Internationale Regionen – Location-Based Routing erzwingt das Routing ausgehender Anrufe über internationale PSTN-Gateways, wenn kein lokales Gateway am Standort des Benutzers gefunden werden kann.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Anleitung zum Anwenden von Location-Based Routing

Location-Based Routing kann je nach Situation am Endpunkt-Netzwerkstandort des Benutzers oder am Netzwerkstandort des PSTN-Gateways angewendet werden. Dieses Thema enthält Anleitungen dazu, wie Location-Based Routing angewendet wird.

### <a name="applying-location-based-routing-at-the-users-location"></a>Anwenden Location-Based Routing am Standort des Benutzers

Location-Based Routing nutzt die gleichen Netzwerkregionen, Standorte und Subnetze wie in Skype for Business Server definiert, die von E9-1-1, Anrufsteuerung und Medienumgehung verwendet werden, um Einschränkungen für die Anrufweiterleitung anzuwenden, um die Gebührenumgehung im öffentlichen Telefonnetz zu verhindern. Der Standort eines Benutzers wird durch das IP-Subnetz der Skype for Business Endpunkte des Benutzers bestimmt, von denen eine Verbindung hergestellt wird. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, der in vom Administrator definierte Netzwerkregionen aggregiert wird. Location-Based Routing wird basierend auf dem Netzwerkstandort des Benutzers erzwungen.

Location-Based Routingregeln werden pro Netzwerkstandort angewendet, was bedeutet, dass ein bestimmter Satz von Regeln auf alle Endpunkte angewendet wird, die für Location-Based Routing aktiviert sind, die sich am gleichen Netzwerkstandort befinden. Administratoren können Location-Based Routing auf Netzwerkstandorte anwenden, die dies erfordern.

VoIP-Routingrichtlinien können pro Netzwerkstandort definiert werden, um ein bestimmtes PSTN-Gateway zu definieren, das von allen Benutzern am Netzwerkstandort zum Anrufen von PSTN-Telefonnummern verwendet werden soll. Diese VoIP-Routingrichtlinien haben Vorrang vor dem von der VoIP-Richtlinie des Benutzers definierten Routing, wenn sich der Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing aktiviert ist, und verhindert das Routing von Anrufen über andere PSTN-Gateways, die für Location-Based Routing aktiviert sind. Wenn ein Skype for Business Benutzer einen PSTN-Anruf abgibt, bestimmt die VoIP-Richtlinie des Benutzers, ob der Benutzer zum Tätigen des Anrufs autorisiert werden kann. Wenn die VoIP-Richtlinie des Benutzers es dem Benutzer ermöglicht, den Anruf zu tätigen, bestimmt Location-Based Routing, von welchem PSTN-Gateway der Anruf ausgehend werden soll. Location-Based Routing legt diese Entscheidung basierend auf dem Standort des Benutzers fest.

Ein Benutzerstandort kann wie folgt kategorisiert werden:

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der für Location-Based Routing aktiviert ist, und seine DID-Nummer (Direct Inward Dial) wird an einem PSTN-Gateway am selben Netzwerkstandort (d. h. büro) beendet. Das Routing ausgehender Anrufe erfolgt über die VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Eingehende PSTN-Anrufe an den Benutzer werden an Endpunkte weitergeleitet, die sich am selben Netzwerkstandort wie das PSTN-Gateway befinden.

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich von dem Netzwerkstandort unterscheidet, an dem sich das PSTN-Gateway befindet. (d. h. der Benutzer ist zu einem anderen Unternehmensbüro gefahren). Für das Routing ausgehender Anrufe wird die VoIP-Routingrichtlinie des Netzwerkstandorts verwendet, an dem sich der Benutzer befindet. Eingehende PSTN-Anrufe an den Benutzer werden nicht an Endpunkte weitergeleitet, die sich an anderen Standorten als das PSTN-Gateway befinden, um eine Umgehung der Gebühren im öffentlichen Telefonnetz zu verhindern.

- Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der der Skype for Business Server Bereitstellung unbekannt ist, basiert das Routing ausgehender Anrufe auf der VoIP-Richtlinie, die dem Benutzer an PSTN-Gateways zugewiesen ist, die nicht an Location-Based Routingeinschränkungen gebunden sind. Eingehende PSTN-Anrufe werden nicht an Endpunkte weitergeleitet, die sich an unbekannten Netzwerkstandorten befinden, um die Umgehung der Gebühren für das Festnetz zu verhindern.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Anwenden von Location-Based Routing am Standort des PSTN-Gateways

Anrufe, die über PSTN-Gateways und Nebenstellenanlagen weitergeleitet werden, erfordern je nach Standort dieser Systeme möglicherweise Location-Based Routingeinschränkungen. Location-Based Routing kann mit granularer Genauigkeit pro Trunk aktiviert werden.

Location-Based Routing führt die folgenden Regeln ein, wenn sie für einen Trunk aktiviert sind:

- Wenn Location-Based Routing pro Trunk aktiviert ist, werden die für diesen Trunk definierten Regeln nur auf Anrufe angewendet, die über diesen Trunk weitergeleitet werden.

- Um zu verhindern, dass gebührenpflichtige PsTN-Anrufe von einem Netzwerkstandort stammen, der sich vom Netzwerkstandort unterscheidet, an dem sich das PSTN-Gateway befindet, führt Location-Based Routing die Zuordnung eines Netzwerkstandorts zu einem bestimmten Trunk ein. Dadurch wird der Netzwerkstandort definiert, an dem Anrufe an einen bestimmten Trunk weitergeleitet werden können.

Trunks können für Location-Based Routing auf zwei Arten aktiviert werden:

- Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das PSTN übergibt. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endpunkte weitergeleitet, die sich am selben Netzwerkstandort wie der Trunk befinden.

- Der Trunk ist für einen Vermittlungsserverpeer definiert, der keine Anrufe an das Telefonfestnetz und Benutzer von Diensten mit älteren Telefonen an statischen Standorten (z. B. Nebenstellentelefone) ausgibt. Für diese spezielle Konfiguration werden alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, als vom selben Netzwerkstandort wie der Trunk ausgehend betrachtet. Anrufe von Pbx-Benutzern haben die gleiche Location-Based Routingerzwingung wie Skype for Business Benutzer, die sich am selben Netzwerkstandort wie der Trunk befinden. Wenn zwei Pbx-Systeme, die sich an separaten Netzwerkstandorten befinden, über Skype for Business Server verbunden sind, ermöglicht Location-Based Routing das Routing von einem NEBENSTELLEN-Endpunkt an einem Netzwerkstandort zu einem anderen NEBENSTELLEN-Endpunkt am anderen Netzwerkstandort. Dieses Szenario wird nicht durch Location-Based Routing blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein Skype for Business Benutzer am selben Standort können Endpunkte, die mit einem Vermittlungsserverpeer mit dieser Konfiguration verbunden sind, Anrufe an und von einem anderen Vermittlungsserverpeer tätigen oder empfangen, die keine Anrufe an das Festnetz weiterleiten (d. h. einen Endpunkt, der mit einer anderen Nebenstellenanlage verbunden ist), unabhängig vom Netzwerkstandort, dem der Vermittlungsserverpeer zugeordnet ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anrufübertragungen und Anrufweiterleitungen, an denen PSTN-Endpunkte beteiligt sind, unterliegen dem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die als lokal für einen solchen Vermittlungsserverpeer definiert sind.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für Location-Based Routing

Location-Based Routing wendet die folgenden allgemeinen Regeln beim Weiterleiten von Anrufen in den folgenden Szenarien an.

### <a name="outgoing-calls"></a>Ausgehende Anrufe

Das Routing ausgehender Anrufe von Benutzern, die für Location-Based Routing aktiviert sind, wird vom Netzwerkstandort des Endpunkts des Benutzers beeinflusst. Die folgende Tabelle zeigt, wie sich Location-Based Routing abhängig vom Standort des Endpunkts des Anrufers auf das Routing ausgehender Anrufe auswirkt.

**Anrufer, der einen ausgehenden Anruf an das PSTN abgibt**

|&nbsp;|Benutzerendpunkt an einem Netzwerkstandort, der für Location-Based Routing aktiviert ist|Benutzerendpunkt, der sich an einem unbekannten Netzwerkstandort befindet oder nicht für Location-Based Routing aktiviert ist|
|:-----|:-----|:-----|
|Autorisierung ausgehender Anrufe   |Der Anruf ist basierend auf der VoIP-Richtlinie des Benutzers autorisiert.   |Der Anruf ist basierend auf der VoIP-Richtlinie des Benutzers autorisiert.   |
|Routing von ausgehenden Anrufen   |Der Anruf wird gemäß der VoIP-Routingrichtlinie des Netzwerkstandorts weitergeleitet.   |Der Anruf wird gemäß der VoIP-Richtlinie des Benutzers weitergeleitet und nur über Trunks, die nicht für Location-Based Routing aktiviert sind (sofern verfügbar).   |

### <a name="incoming-calls"></a>Eingehende Anrufe

Das Routing eingehender Anrufe an Benutzer, die für Location-Based Routing aktiviert sind, hängt vom Standort des Endpunkts des Benutzers ab. Das Routing eingehender Anrufe wird wie folgt beeinflusst. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem Location-Based Routing-aktivierten Netzwerkstandort befindet und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf weitergeleitet. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem Location-Based Routing-aktivierten Netzwerkstandort befindet und sich der Endpunkt an einem anderen Netzwerkstandort als das PSTN-Gateway befindet, wird der Anruf nicht weitergeleitet. Wenn sich ein Benutzer nicht am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers weitergeleitet, und eine Benachrichtigung über verpasste Anrufe wird an die angerufene Partei gesendet.

Die Anrufweiterleitungseinstellungen eines Benutzers, der für Location-Based Routing aktiviert ist, werden weiterhin erzwungen. Weitergeleitete Anrufe unterliegen jedoch Location-Based Routingeinschränkungen des Benutzers.

In der folgenden Tabelle wird veranschaulicht, wie sich Location-Based Routing abhängig vom Standort des Endpunkts des Angerufenen auf das Routing eingehender Anrufe auswirkt. Der Netzwerkstandort des PSTN-Gateways ist für Location-Based Routing aktiviert, und Location-Based Routing erlaubt nur das Routing von PSTN-Anrufen an Endpunkte am gleichen Netzwerkstandort.

**Anrufer, der einen eingehenden Anruf aus dem PSTN empfängt**

|&nbsp;|Der Endpunkt des Angerufenen befindet sich am selben Netzwerkstandort wie das PSTN-Gateway|Der Endpunkt des Angerufenen befindet sich nicht am selben Netzwerkstandort wie das PSTN-Gateway|Endpunkt des Angerufenen, der sich an einem unbekannten Netzwerkstandort befindet oder nicht für Location-Based Routing aktiviert ist|
|:-----|:-----|:-----|:-----|
|Routing eines eingehenden PSTN-Anrufs   |Eingehender Anruf wird an die Endpunkte des Angerufenen weitergeleitet   |Eingehender Anruf wird nicht an die Endpunkte des Angerufenen weitergeleitet   |Eingehender Anruf wird nicht an die Endpunkte des Angerufenen weitergeleitet   |

### <a name="call-transfers-and-call-forwarding"></a>Anrufweiterleitung und Anrufweiterleitung

Wenn ein PSTN-Endpunkt beteiligt ist, analysiert Location-Based Routing den Standort des Endpunkts des Anrufers und den Endpunkt, an den der Anruf weitergeleitet oder weitergeleitet wird (d. h. Das Übertragungs-/Weiterleitungsziel). Location-Based Routing bestimmt, ob der Anruf je nach Standort beider Endpunkte weitergeleitet oder weitergeleitet werden soll.

Die folgende Tabelle veranschaulicht das Szenario eines Skype for Business Benutzers in einem Anruf mit einem PSTN-Endpunkt, und der Skype for Business Benutzer überträgt den Anruf an einen anderen Skype for Business Benutzer. Abhängig vom Netzwerkstandort des Endpunkts des Übertragungsempfängers wirkt sich Location-Based Routing auf das Routing der Anrufweiterleitung oder -weiterleitung aus.

**Initiieren der Anrufübertragung oder -weiterleitung**

|Benutzer, der die Anrufweiterleitung initiiert|Der Zielendpunkt befindet sich am selben Netzwerkstandort wie der Benutzer, der die Anrufübertragung oder -weiterleitung initiiert.|Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als Benutzer, der die Anrufübertragung oder -weiterleitung initiiert.|Der Zielendpunkt befindet sich an einem unbekannten Netzwerkstandort oder Netzwerkstandort, der nicht für Location-Based Routing aktiviert ist
|:-----|:-----|:-----|:-----|
|Skype for Business Benutzer   |Anrufweiterleitung oder -übertragung ist zulässig   |Anrufweiterleitung oder -übertragung ist nicht zulässig   |Anrufweiterleitung oder -übertragung ist nicht zulässig   |

Beispiel: Ein Skype for Business Benutzer in einem Anruf mit einem PSTN-Endpunkt überträgt den Anruf an einen anderen Skype for Business Benutzer, der sich am selben Netzwerkstandort befindet. In diesem Fall ist die Anrufübertragung zulässig.

Die folgende Tabelle veranschaulicht das Szenario eines Skype for Business Benutzers in einem Anruf mit einem anderen Skype for Business Benutzer, und einer der Benutzer überträgt den Anruf an einen PSTN-Endpunkt. Abhängig vom Standort des Benutzers, an den der Anruf weitergeleitet wird, wird in der Tabelle beschrieben, wie sich Location-Based Routing auf den Anruf auswirkt.

**Anrufweiterleitung oder -weiterleitung an PSTN-Endpunkt**

|Endpunktziel für Anrufübertragung/-weiterleitung|Skype for Business Benutzer am selben Netzwerkstandort|Skype for Business Von Benutzern an unterschiedlichen Netzwerkstandorten|Ein oder beide Skype for Business Benutzer an einem unbekannten Netzwerkstandort oder Netzwerkstandort, der nicht für Location-Based Routing aktiviert ist|
|:-----|:-----|:-----|:-----|
|PSTN-Endpunkt   |Anrufweiterleitung oder -übertragung, die von der VoIP-Routingrichtlinie des übertragenen Benutzers zugelassen ist   |Anrufweiterleitung oder -übertragung, die von der VoIP-Routingrichtlinie des übertragenen Benutzers zugelassen ist   |Anrufweiterleitung oder -übertragung, die von der VoIP-Richtlinie des übertragenen Benutzers nur über Trunks zulässig ist, die nicht für Location-Based Routing aktiviert sind   |

Beispiel: Ein Skype for Business Benutzer in einem Anruf mit einem anderen Skype for Business Benutzer, der sich am selben Netzwerkstandort befindet, überträgt den Anruf an einen PSTN-Endpunkt, und die Anrufübertragung ist zulässig.

### <a name="simultaneous-ringing"></a>Gleichzeitiges Klingeln

Wenn das gleichzeitige Klingeln für die angerufene Partei aktiviert ist, analysiert Location-Based Routing den Standort der anrufenden Partei und die Endpunkte der angerufenen Parteien, um zu bestimmen, ob der Anruf weitergeleitet werden soll.

Die folgende Tabelle zeigt einen Benutzer, der mit gleichzeitigem Klingeln konfiguriert ist, und das Ziel für das gleichzeitige Klingeln ist ein Benutzer am selben Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort.

****

|Eingehender PSTN-Anruf für|Befindet sich am gleichen Netzwerkstandort wie der Angerufene.|Befindet sich an einem anderen Netzwerkstandort als der Angerufene|Befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für Location-Based Routing aktiviert|
|:-----|:-----|:-----|:-----|
|Skype for Business Benutzer   |Gleichzeitiges Klingeln zulässig   |Gleichzeitiges Klingeln nicht zulässig   |Gleichzeitiges Klingeln nicht zulässig   |

Die folgende Tabelle zeigt einen Anruf von einem Skype for Business Benutzer (d. h. Skype for Business Anrufer) am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder von einem unbekannten Netzwerkstandort aus. Der Angerufene verfügt über einen PSTN-Endpunkt (d. h. ein Mobiltelefon), der als Ziel für gleichzeitiges Klingeln konfiguriert ist. In diesem Szenario bestimmt Location-Based Routing, ob der Anruf an das Ziel des gleichzeitigen Anrufs (z. B. das Mobiltelefon) des Angerufenen weitergeleitet werden soll oder nicht.

****

|Ziel für gleichzeitiges Klingeln|Befindet sich am gleichen Netzwerkstandort wie der Angerufene.|Befindet sich an einem anderen Netzwerkstandort als der Angerufene|Befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für Location-Based Routing aktiviert|
|:-----|:-----|:-----|:-----|
|PSTN-Endpunkt   |Gleichzeitiges Klingeln über die VoIP-Routingrichtlinie des Anrufers   |Gleichzeitiges Klingeln über die VoIP-Routingrichtlinie des Anrufers   |Gleichzeitiges Klingeln über die VoIP-Richtlinie des Anrufers für Trunks zulässig, die nicht für Location-Based Routing aktiviert sind   |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business Kumulatives Update 4

Mit kumulativem Update 4 sehen Sie Folgendes:

- Location-Based Routing wird weiterhin über voIP-Richtlinie aktiviert, einschließlich Skype for Business Mobile-Clients.

- Das Anrufverhalten für Skype for Business Mobile-Clients basiert darauf, ob sie für Location-Based Routing und den kommunizierenden Client aktiviert sind. Dies ist so konzipiert, dass es statisch ist, aber in bestimmten Situationen kann versucht werden, einen Skype for Business Mobile-Client einem lokalen PSTN-Gateway zuzuordnen und bestimmte Verhaltensweisen zuzulassen, z. B. eine Eskalation

- Unabhängig von Ihrem Betriebssystem sollte Ihr Skype for Business Mobile-Client die gleiche Funktionalität haben.

Die folgende Tabelle führt Sie durch einige der Szenarien nach dem kumulativen Update 4:

|Location-Based Routingbenutzer|Andere Partei|Aktion|Result|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobil   |Telefonfestnetz (Public Switched Telephone Network, PSTN)   |Skype for Business Mobile empfängt einen eingehenden PSTN-Anruf.   |Der Anruf wird über "Anruf über Arbeit" (Call via Work, CvW) und nicht über VoIP weitergeleitet.   |
|Skype for Business Mobil   |Telefonfestnetz (Public Switched Telephone Network, PSTN)   |Skype for Business Mobile führt einen ausgehenden PSTN-Anruf durch.   |Der Anruf wird über CvW und nicht über VoIP weitergeleitet.   |
|Skype for Business Mobil   |Telefonfestnetz (Public Switched Telephone Network, PSTN)   |Skype for Business Mobile befindet sich in einem PSTN-Anruf. Skype for Business Mobile eskaliert den Anruf dann an einen anderen Benutzer oder Kontakt.   |Der Anruf wird über VoIP weitergeleitet, wenn sich der Benutzer oder Kontakt lokal im PSTN-Gateway befindet.  <br/> Wenn sich der Benutzer oder Kontakt remote vom PSTN-Gateway befindet, wird der Anruf über CvW weitergeleitet.  <br/> Wenn der Zielbenutzer über das PSTN nicht erreichbar ist, schlägt der Anruf fehl.  <br/> Wenn der Zielkontakt eine automatische Telefonzentrale (Conference Auto Attendant, CAA) ist, wird der Anruf blockiert.   |
|Skype for Business Mobil   |Skype for Business Client- oder Verbundbenutzer   |Ein Skype for Business Mobile initiiert einen Sprachanruf an einen anderen Skype for Business Client- oder Verbundbenutzer.   |Der Anruf wird über VoIP abgeschlossen.   |
|Skype for Business Mobil   |Skype for Business Client- oder Verbundbenutzer   | Ein Skype for Business Client- oder Verbundbenutzer initiiert einen Sprachanruf an einen Benutzer Skype for Business Mobile Location-Based Routing.  |Der Anruf wird über VoIP abgeschlossen.   |
|Skype for Business Mobil   |Skype for Business Client- oder Verbundbenutzer   |Ein Skype for Business Client- oder Verbundbenutzer befindet sich in einem VoIP-Anruf an einen Skype for Business Mobile-Benutzer. Beide Parteien eskalieren an einen zusätzlichen Skype for Business oder Verbundbenutzer.   |Der Anruf wird über VoIP abgeschlossen.   |
|Skype for Business Mobil   |Partnerbenutzer   |Ein Verbundbenutzer hat einen Sprachanruf an einen Benutzer Skype for Business Mobile Location-Based Routing; eine Skype for Business Mobile-Partei wird an einen PSTN-Benutzer eskaliert.   |Der Anruf wird blockiert.   |
|Skype for Business Mobil   |Partnerbenutzer   |Ein Verbundbenutzer hat einen VoIP-Anruf an einen Benutzer Skype for Business Mobile Location-Based Routing; Beide Parteien eskalieren an einen CAA-Kontakt.   |Der eskalierte Anruf wird mit einer entsprechenden Fehlermeldung blockiert.   |
|Skype for Business Mobil   |Partnerbenutzer   |Ein Verbundbenutzer hat einen VoIP-Anruf an einen Benutzer Skype for Business Mobile Location-Based Routing, und der Verbundbenutzer wird an einen PSTN-Benutzer eskaliert.   |Die Eskalation ist basierend auf dem Location-Based Routing des Verbundbenutzers zulässig oder nicht zulässig. Die Anwendung des Skype for Business Mobile Location-Based Routing-Benutzers wird keine Aktion ausgeführt.   |

### <a name="delegation"></a>Delegierung

Die Delegierungsfunktionen in Skype for Business werden durch Location-Based Routing auf folgende Weise beeinflusst:

- Wenn eine Stellvertretung für Location-Based Routing einen Anruf im Auftrag eines Vorgesetzten tätigt, wird die VoIP-Richtlinie der Stellvertretung verwendet, um den Anruf zu autorisieren, und die VoIP-Routingrichtlinie des Delegaten wird zum Weiterleiten des Anrufs verwendet.

- Für eingehende PSTN-Anrufe an einen Vorgesetzten gelten die gleichen Regeln für die Anrufweiterleitung oder das gleichzeitige Klingeln, wie in den Themen "Anrufweiterleitung und -weiterleitung" und "Gleichzeitiges Klingeln" beschrieben.

- Wenn ein Delegat einen PSTN-Endpunkt als Ziel für gleichzeitiges Klingeln für einen eingehenden Anruf an den Vorgesetzten festlegt, wird die VoIP-Routingrichtlinie des Standorts, der dem eingehenden Trunk zugeordnet ist, verwendet, um den Anruf an den PSTN-Endpunkt des Delegaten weiterzuleiten.

- Für die Delegierung wird empfohlen, dass sich der Vorgesetzte und seine zugeordneten Stellvertreter in der Regel am gleichen Netzwerkstandort befinden.

## <a name="other-planning-considerations"></a>Weitere Planungsüberlegungen

Bei der Planung Location-Based Routing sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.

### <a name="disaster-recovery"></a>Notfallwiederherstellung

Während eines Failovers vom primären Pool zu einem Sicherungspool und beim Wiederherstellen des normalen Betriebs im primären Pool bleibt Location-Based Routing während eines Notfall- und Wiederherstellungsvorgangs jederzeit erzwungen.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Das Konfigurieren Location-Based Routing wirkt sich auf die Planung der Bereitstellung der Gateways aus, die Ihren Survivable Branch Appliances zugeordnet sind. Das Ihrem SBA zugeordnete Gateway muss sich am gleichen Netzwerkstandort wie Ihre Survivable Branch Appliance befinden. andernfalls können Benutzer, die in Ihrer Survivable Branch Appliance verwaltet werden, keine ausgehenden Anrufe tätigen, wenn Location-Based Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch Appliance und dem zentralen Standort ausfällt, bleiben Location-Based Routingeinschränkungen erzwungen.

## <a name="client-and-server-support-for-location-based-routing"></a>Client- und Serverunterstützung für Location-Based Routing

Location-Based Routing wird von Skype for Business Server erzwungen. Skype for Business Server können die Netzwerkstandorte identifizieren, an denen Benutzer innerhalb des Unternehmensnetzwerks eine Verbindung herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, wird ihr Standort als unbekannt betrachtet.

### <a name="server-support"></a>Serverunterstützung

Location-Based Routing erfordert, dass Skype for Business Server oder Lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition Servern in einer bestimmten Topologie bereitgestellt wird. Wenn diese Versionen des Servers nicht installiert sind, können standortbasierte Routingeinschränkungen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrollen und -versionen aufgeführt, die für Location-Based Routing unterstützt werden.

****

|Poolversion|Version des Vermittlungsservers|Unterstützt|
|:-----|:-----|:-----|
|kumulatives Update Skype for Business Server oder Lync Server 2013 Februar 2013   |kumulatives Update Skype for Business Server oder Lync Server 2013 Februar 2013   |ja   |
|kumulatives Update Skype for Business Server oder Lync Server 2013 Februar 2013   |Lync Server 2013   |Nein   |
|kumulatives Update Skype for Business Server oder Lync Server 2013 Februar 2013   |Lync Server 2010   |Nein   |
|kumulatives Update Skype for Business Server oder Lync Server 2013 Februar 2013   |Office Communications Server 2007 R2   |Nein   |
|Lync Server 2013   |Beliebiger Wert   |Nein   |
|Lync Server 2010   |Beliebiger Wert   |Nein   |
|Office Communications Server 2007 R2   |Beliebiger Wert   |Nein   |

### <a name="client-support"></a>Clientunterstützung

In der folgenden Tabelle sind die Clients aufgeführt, die Location-Based Routing unterstützt.

****

|Clienttyp|Unterstützt|Details|
|:-----|:-----|:-----|
|Skype for Business   |ja   ||
|Lync 2013   |ja   ||
|Lync 2010   |ja   ||
|Office Communicator 2007 R2   |Nein   ||
|Lync Phone Edition   |ja   ||
|Lync-Telefonzentrale   |ja   ||
|Lync für Windows 8   |Nein   ||
|Lync Mobile 2013   |Nein   |VoIP muss für Lync Mobile 2013-Clients deaktiviert sein, wenn es von Benutzern mit aktivierter Location-Based Routing verwendet wird.   |
|Lync Mobile 2010   |ja   ||

> [!NOTE]
> Um VoIP für Skype for Business Clients zu deaktivieren, weisen Sie eine Mobilitätsrichtlinie mit der Einstellung IP Audio/Video zu, die für alle Benutzer deaktiviert ist, die für Location-Based Routing aktiviert sind. Weitere Informationen zur Mobilitätsrichtlinie finden Sie unter [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Vom Location-Based Routing nicht unterstützte Funktionen

Location-Based Routing gilt nicht für die folgenden Arten von Interaktionen. Location-Based Routing wird nicht erzwungen, wenn Skype for Business Endpunkte mit PSTN-Endpunkten mit diesen Funktionen interagieren.

- PSTN-Einwahl in Konferenzen

- Ein- und ausgehende PSTN-Anrufe über Reaktionsgruppen

- Parken oder Abrufen von PSTN-Anrufen über das Parken von Anrufen

- Eingehende PSTN-Anrufe an den Ankündigungsdienst

- Eingehende PSTN-Anrufe, die über die Gruppenanrufannahme abgerufen werden

Um Location-Based Routingregeln für die Arten von Interaktionen in der folgenden Liste zu erzwingen, müssen Sie Location-Based Routing für Konferenzen aktivieren:

- PSTN-Ausgehende Anrufe von Konferenzen

- Eskalationen von Peer-zu-Peer-Audiounterhaltungen zu Konferenzen mit PSTN-Endpunkten

- Beratungsübertragungen, an denen PSTN-Endpunkte beteiligt sind

Informationen zum Aktivieren Location-Based Routing für Konferenzen finden Sie unter ["Standortbasiertes Routing für Konferenzen".](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)