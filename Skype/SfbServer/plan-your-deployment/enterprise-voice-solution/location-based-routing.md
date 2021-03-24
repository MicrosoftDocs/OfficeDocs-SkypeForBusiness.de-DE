---
title: Planen Location-Based Routing in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planen des standortbasierten Routings in Skype for Business Server Enterprise-VoIP, einschließlich der Interaktion mit gleichzeitigen Klingeln und Delegierung sowie unterstützten Szenarien für standortbasiertes Routing.
ms.openlocfilehash: 99a76d3cda40bb1fdc71bdffc7f6c896c96c5cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101481"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planen Location-Based Routing in Skype for Business

Planen des standortbasierten Routings in Skype for Business Server Enterprise-VoIP, einschließlich der Interaktion mit gleichzeitigen Klingeln und Delegierung sowie unterstützten Szenarien für standortbasiertes Routing.

Location-Based Routing ermöglicht es, das Routing von Anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Parteien im Anruf einzuschränken. Location-Based Routing ist ein Anrufverwaltungsfeature, das steuert, wie Anrufe von Skype for Business Server geroutet werden. Es erzwingt Anrufautorisierungsregeln, ob Anrufe basierend auf dem geografischen Standort des Skype for Business-Anrufers an PbX- oder PSTN-Endpunkte geleitet werden können.

Location-Based Routing führt einen neuen Satz von Regeln ein, mit dem das Routing von nationalen und internationalen PSTN-Anrufen geändert wird, um eine Gebührenumgehung zu verhindern. Location-Based Routing bietet die Flexibilität, diese Regeln nur auf bestimmte Regionen, bestimmte Gateways oder bestimmte Benutzergruppen zu deggnen.

In den folgenden Szenarien werden die wichtigsten Arten von Einschränkungen veranschaulicht, Location-Based Routing erzwingen kann:

- Ausgehende Anrufe – Location-Based Routing kann ausgehende Anrufe erzwingen, um ausgehende Anrufe an ein PSTN-Gateway zu übergehen, das sich in derselben Region befindet, in der sich der Anrufer befindet, um die Gebührenumgehung von PSTN zu verhindern, wodurch verhindert wird, dass Anrufe an ein PSTN-Gateway in einer anderen Region als der Anrufer gesendet werden.

- Ausgehende Anrufe – Location-Based Routing kann eingehende PSTN-Anrufe verhindern, um Skype for Business-Endpunkte anzuringen, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleite, nicht in derselben Region wie der skype for Business-Benutzer befindet.

- Unbekannte Regionen – Location-Based Routing schränkt eingehende und ausgehende PSTN-Anrufe an und von Benutzern ein, die sich an unbestimmten Orten befinden (d. h. Remotebenutzer, die eine Verbindung über das Internet herstellen oder sich in unbekannten Regionen befinden).

- Internationale Regionen – Location-Based Routing erzwingt das Routing ausgehender Anrufe über internationale PSTN-Gateways, wenn ein lokales Gateway zum Standort des Benutzers nicht gefunden werden kann.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Leitfaden für die Anwendung Location-Based Routing

Location-Based Routing kann je nach Situation am Endpunktnetzwerkstandort des Benutzers oder am Netzwerkstandort des PSTN-Gateways angewendet werden. Dieses Thema enthält Anleitungen dazu, Location-Based Routing angewendet wird.

### <a name="applying-location-based-routing-at-the-users-location"></a>Anwenden Location-Based Routing am Standort des Benutzers

Location-Based Routing nutzt dieselben Netzwerkregionen, Standorte und Subnetze wie in Skype for Business Server definiert, die von E9-1-1, CAC und Medienumgehung verwendet werden, um Anrufroutingeinschränkungen anzuwenden, um die Umgehung der Gebührenumgehung von PstN zu verhindern. Der Standort eines Benutzers wird durch das IP-Subnetz der Skype for Business-Endpunkte des Benutzers bestimmt, von dem aus eine Verbindung besteht. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, der in vom Administrator definierte Netzwerkregionen aggregiert wird. Location-Based Routing wird basierend auf dem Netzwerkstandort des Benutzers erzwungen.

Location-Based Routingregeln werden pro Netzwerkstandort angewendet, d. h. ein bestimmtes Regelset wird auf alle Endpunkte angewendet, die für Location-Based Routing aktiviert sind, die sich am gleichen Netzwerkstandort befinden. Administratoren können Location-Based Routing auf Netzwerkstandorte anwenden, die dies erfordern.

Voiceroutingrichtlinien können pro Netzwerkstandort definiert werden, um ein bestimmtes PSTN-Gateway zu definieren, das von allen Benutzern am Netzwerkstandort zum Anrufen von PSTN-Telefonnummern verwendet werden soll. Solche Voiceroutingrichtlinien haben Vorrang vor dem Routing, das durch die Sprachrichtlinie des Benutzers definiert wird, wenn sich der Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing aktiviert ist, und verhindert das Routing von Anrufen über andere PSTN-Gateways, die für Location-Based Routing aktiviert sind. Wenn ein Skype for Business-Benutzer einen PSTN-Anruf abstellen, bestimmt die Sprachrichtlinie des Benutzers, ob der Benutzer autorisiert werden kann, den Anruf zu führen. Wenn die Sprachrichtlinie des Benutzers dem Benutzer das Platzieren des Anrufs zulässt, bestimmt Location-Based Routing, von welchem PSTN-Gateway der Anruf abziehen soll. Location-Based Routing wird diese Bestimmung basierend auf dem Standort des Benutzers bestimmt.

Ein Benutzerspeicherort kann auf folgende Weise kategorisiert werden:

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der für Location-Based Routing aktiviert ist, und seine DID(Direct Inward Dial)-Nummer wird an einem PSTN-Gateway beendet, das am gleichen Netzwerkstandort (z. B. office) platziert ist. Das Routing ausgehender Anrufe wird über die Voiceroutingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet, verwendet. Eingehende PSTN-Anrufe an den Benutzer werden an Endpunkte geleitet, die sich am gleichen Netzwerkstandort wie das PSTN-Gateway befinden.

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich nicht am Netzwerkstandort befindet, an dem sich das PSTN-Gateway befindet. (d. h. der Benutzer ist in ein anderes Unternehmensbüro 2014 2014 2014 2014 2014 20 Das Routing ausgehender Anrufe verwendet die Voiceroutingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Eingehende PSTN-Anrufe an den Benutzer werden nicht an Endpunkte geleitet, die sich an unterschiedlichen Standorten als das PSTN-Gateway befinden, um die Umgehung von PSTN-Gebühren zu verhindern.

- Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der der Skype for Business Server-Bereitstellung nicht bekannt ist, basiert das Routing ausgehender Anrufe auf der Voicerichtlinie, die dem Benutzer an PSTN-Gateways zugewiesen ist, die nicht an Location-Based Routingeinschränkungen gebunden sind. Eingehende PSTN-Anrufe werden nicht an Endpunkte geleitet, die sich an unbekannten Netzwerkstandorten befinden, um die Umgehung der Gebührenumgehung durch PSTN zu verhindern.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Anwenden Location-Based Routing am Standort des PSTN-Gateways

Anrufe, die über PSTN-Gateways und Nebenstellenanlagen geroutet werden, erfordern möglicherweise Location-Based Routingeinschränkungen abhängig vom Standort dieser Systeme. Location-Based Routing kann in der Granularität pro Trunk aktiviert werden.

Location-Based Routing führt die folgenden Regeln ein, wenn sie für einen Trunk aktiviert sind:

- Wenn Location-Based Routing pro Trunk aktiviert ist, werden die Regeln, die für den Trunk definiert werden, nur auf Anrufe angewendet, die über den Trunk geroutet werden.

- Um zu verhindern, dass Anrufe von einem Netzwerkstandort stammen, der sich vom Netzwerkstandort, an dem sich das PSTN-Gateway befindet, abstammt, führt Location-Based Routing die Zuordnung eines Netzwerkstandorts zu einem bestimmten Trunk ein. Dadurch wird der Netzwerkstandort definiert, über den Anrufe an einen bestimmten Trunk geroutet werden können.

Trunks können für das Location-Based auf zwei Arten aktiviert werden:

- Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das PSTN überfresst. Eingehende Anrufe, die von einem Trunk dieses Typs geleitet werden, werden nur an Endpunkte geleitet, die sich am gleichen Netzwerkstandort wie der Trunk befinden.

- Der Trunk ist für einen Vermittlungsserver-Peer definiert, der keine Anrufe an das PSTN abfing und Benutzer mit älteren Telefonen an einem statischen Speicherort (z. B. NEBENSTELLENtelefone) unterstützt. Für diese spezielle Konfiguration werden alle eingehenden Anrufe, die von einem Trunk dieses Typs geroutet werden, als vom gleichen Netzwerkstandort wie der Trunk betrachtet. Anrufe von Nebenstellenanlagenbenutzern verfügen über die Location-Based Routingdurchsetzung wie Skype for Business-Benutzer, die sich am gleichen Netzwerkstandort wie der Trunk befinden. Wenn zwei Nebenstellenanlagen an separaten Netzwerkstandorten über Skype for Business Server verbunden sind, ermöglicht Location-Based Routing das Routing von einem PbX-Endpunkt an einem Netzwerkstandort zu einem anderen PbX-Endpunkt am anderen Netzwerkstandort. Dieses Szenario wird nicht durch das Routing Location-Based blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein Skype for Business-Benutzer am gleichen Standort können Endpunkte, die mit einem Vermittlungsserver-Peer mit dieser Konfiguration verbunden sind, Anrufe an und von einem anderen Vermittlungsserver-Peer senden oder empfangen, die Anrufe an das PSTN (d. h. einen endpunkt, der mit einer anderen Nebenstellenanlage verbunden ist) unabhängig vom Netzwerkstandort, dem der Vermittlungsserver-Peer zugeordnet ist, nicht weiter geleitet werden. Alle eingehenden Anrufe, ausgehenden Anrufe, Anrufübertragungen und Anrufanleitungen, die PSTN-Endpunkte verwenden, unterliegen dem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die für einen solchen Vermittlungsserver-Peer als lokal definiert sind.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für Location-Based Routing

Location-Based Routing wendet die folgenden allgemeinen Regeln beim Routing von Anrufen in den folgenden Szenarien an.

### <a name="outgoing-calls"></a>Ausgehende Anrufe

Das Routing ausgehender Anrufe von Benutzern, die Location-Based Routing aktiviert sind, wird vom Netzwerkspeicherort des Endpunkts des Benutzers beeinflusst. Die folgende Tabelle veranschaulicht, Location-Based Routing sich auf das Routing ausgehender Anrufe in Abhängigkeit vom Standort des Endpunkts des Anrufers auswirkt.

**Anrufer, der einen ausgehenden Anruf an das PSTN abstellen**

||**Benutzerendpunkt an einem Netzwerkstandort, der für das Routing Location-Based ist**|**Benutzerendpunkt an unbekanntem Netzwerkstandort oder nicht für das Routing Location-Based aktiviert**|
|:-----|:-----|:-----|
|Autorisierung ausgehender Anrufe  <br/> |Anruf wird basierend auf der Sprachrichtlinie des Benutzers autorisiert  <br/> |Anruf wird basierend auf der Sprachrichtlinie des Benutzers autorisiert  <br/> |
|Routing ausgehender Anrufe  <br/> |Der Anruf wird gemäß der Voiceroutingrichtlinie des Netzwerkstandorts geroutet.  <br/> |Der Anruf wird gemäß der Sprachrichtlinie des Benutzers und nur über Trunks geroutet, die nicht für Location-Based Routing aktiviert sind (sofern verfügbar)  <br/> |

### <a name="incoming-calls"></a>Eingehende Anrufe

Das Routing eingehender Anrufe an Benutzer, die für Location-Based Routing aktiviert sind, hängt vom Speicherort des Endpunkts des Benutzers ab. Das Routing eingehender Anrufe ist auf folgende Weise betroffen. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt an einem Location-Based Routing aktivierten Netzwerkstandort hat und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf geleitet. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt an einem Location-Based Routing aktivierten Netzwerkstandort hat und sich der Endpunkt an einem anderen Netzwerkstandort als dem PSTN-Gateway befindet, wird der Anruf nicht geleitet. Wenn ein Benutzer keine Endpunkte am gleichen Netzwerkstandort wie das PSTN-Gateway hat, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers geleitet, und eine Benachrichtigung über verpasste Anrufe wird an die angerufene Partei gesendet.

Die Anrufleitungseinstellungen eines Benutzers, der für Location-Based Routing aktiviert ist, werden weiterhin erzwungen, weitergeleitete Anrufe unterliegen jedoch den Location-Based Routingeinschränkungen des Benutzers.

Die folgende Tabelle veranschaulicht, Location-Based Routing sich auf das Routing eingehender Anrufe in Abhängigkeit vom Standort des Endpunkts des Anrufers auswirkt. Der Netzwerkstandort des PSTN-Gateways ist für Location-Based Routing aktiviert, und Location-Based Routing ermöglicht nur das Routing von PSTN-Anrufen an Endpunkte innerhalb desselben Netzwerkstandorts.

**Anrufer, der einen eingehenden Anruf vom PSTN empfängt**

||**Endpunkt des Anrufers am gleichen Netzwerkstandort wie das PSTN-Gateway**|**Endpunkt des Anrufers, der sich nicht am gleichen Netzwerkstandort wie das PSTN-Gateway befindet**|**Endpunkt des Anrufers, der sich an einem unbekannten Netzwerkstandort befindet oder nicht für das Routing Location-Based ist**|
|:-----|:-----|:-----|:-----|
|Routing eingehender PSTN-Anrufe  <br/> |Eingehender Anruf wird an die Endpunkte des Anrufers geleitet  <br/> |Eingehender Anruf wird nicht an die Endpunkte des Anrufers geleitet  <br/> |Eingehender Anruf wird nicht an die Endpunkte des Anrufers geleitet  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Anrufübertragungen und Anrufübermittlung

Wenn ein PSTN-Endpunkt beteiligt ist, analysiert Location-Based Routing den Standort des Endpunkts des Anrufs und den Endpunkt, an den der Anruf weitergeleitet oder weitergeleitet wird (d. h. Transfer-/Weiterleitungsziel). Location-Based Routing bestimmt, ob der Anruf in Abhängigkeit vom Standort beider Endpunkte übertragen oder weitergeleitet werden soll.

Die folgende Tabelle veranschaulicht das Szenario eines Skype for Business-Benutzers in einem Anruf mit einem PSTN-Endpunkt, und der Skype for Business-Benutzer überträgt den Anruf an einen anderen Skype for Business-Benutzer. Abhängig vom Standort des Netzwerkstandorts des Endpunkts des Übertragungsendpunkts wirkt sich Location-Based Routing auf das Routing der Anrufübertragung oder Weiterleitung aus.

**Initiieren der Anrufübertragung oder Weiterleitung**

|**Benutzer, der die Anrufübertragung/Weiterleitung initiiert**|**Zielendpunkt befindet sich an demselben Netzwerkstandort wie der Benutzer, der die Anrufübertragung oder Weiterleitung initiiert**|**Zielendpunkt befindet sich an unterschiedlichen Netzwerkstandorten als Benutzer, der die Anrufübertragung oder Weiterleitung initiiert**|**Zielendpunkt befindet sich an unbekanntem Netzwerkstandort oder Netzwerkstandort, der nicht für das Routing Location-Based ist**|
|:-----|:-----|:-----|:-----|
|Skype for Business-Benutzer  <br/> |Anrufanruf oder Übertragung ist zulässig  <br/> |Anrufanruf oder -übertragung ist nicht zulässig  <br/> |Anrufanruf oder -übertragung ist nicht zulässig  <br/> |

Beispiel: Ein Skype for Business-Benutzer in einem Anruf mit einem PSTN-Endpunkt überträgt den Anruf an einen anderen Skype for Business-Benutzer, der sich am gleichen Netzwerkstandort befindet. In diesem Fall ist die Anrufübertragung zulässig.

Die folgende Tabelle veranschaulicht das Szenario eines Skype for Business-Benutzers bei einem Anruf mit einem anderen Skype for Business-Benutzer, und einer der Benutzer überträgt den Anruf an einen PSTN-Endpunkt. Je nach Standort des Benutzers, an den der Anruf übertragen wird, wird in der Tabelle Location-Based Routing des Anrufs aufgeführt.

**Anrufübertragung oder Weiterleitung an den PSTN-Endpunkt**

|**Ziel des Anrufübertragungs-/Weiterleitungsendpunkts**|**Skype for Business-Benutzer am gleichen Netzwerkstandort**|**Skype for Business-Benutzer an verschiedenen Netzwerkstandorten**|**Ein oder beide Skype for Business-Benutzer an unbekanntem Netzwerkstandort oder Netzwerkstandort, der nicht für das Routing Location-Based ist**|
|:-----|:-----|:-----|:-----|
|PSTN-Endpunkt  <br/> |Anrufanleitung oder Übertragung durch die Standort-Voiceroutingrichtlinie des übertragenen Benutzers zulässig  <br/> |Anrufanleitung oder Übertragung durch die Standort-Voiceroutingrichtlinie des übertragenen Benutzers zulässig  <br/> |Anrufanleitung oder Übertragung durch die Voicerichtlinie des übertragenen Benutzers nur über Trunks zulässig, die nicht für die Weiterleitung Location-Based sind  <br/> |

Beispiel: Ein Skype for Business-Benutzer in einem Anruf mit einem anderen Skype for Business-Benutzer, der sich am gleichen Netzwerkstandort befindet, überträgt den Anruf an einen PSTN-Endpunkt, und die Anrufübertragung ist zulässig.

### <a name="simultaneous-ringing"></a>Gleichzeitiges Klingeln

Wenn das gleichzeitige Klingeln der angerufenen Partei aktiviert ist, analysiert Location-Based Routing den Standort der anrufenden Partei und die Endpunkte der angerufenen Parteien, um zu bestimmen, ob der Anruf geleitet werden soll.

Die folgende Tabelle zeigt einen Benutzer, der mit gleichzeitigen Klingeln konfiguriert ist, und das gleichzeitige Klingeln ist ein Benutzer am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort.

****

|**Eingehender PSTN-Anruf für**|**Befindet sich am gleichen Netzwerkstandort wie der Anrufer**|**Befindet sich an einem anderen Netzwerkstandort als der Anrufer**|**Befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für das Routing Location-Based aktiviert**|
|:-----|:-----|:-----|:-----|
|Skype for Business-Benutzer  <br/> |Gleichzeitiges Klingeln zulässig  <br/> |Gleichzeitiges Klingeln nicht zulässig  <br/> |Gleichzeitiges Klingeln nicht zulässig  <br/> |

In der folgenden Tabelle ist ein Anruf eines Skype for Business-Benutzers (d. h. eines Skype for Business-Anrufers) am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder von einem unbekannten Netzwerkstandort dargestellt. Der Anrufer verfügt über einen PSTN-Endpunkt (d. h. ein Mobiltelefon), der als gleichzeitiges Ringziel konfiguriert ist. In diesem Szenario bestimmt Location-Based Routing, ob der Anruf an das gleichzeitige Klingelziel (d. h. das Mobiltelefon) des Anrufer weiterleitbar sein soll oder nicht.

****

|**Gleichzeitiges Ringziel**|**Befindet sich am gleichen Netzwerkstandort wie der Anrufer**|**Befindet sich an einem anderen Netzwerkstandort als der Anrufer**|**Befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für das Routing Location-Based aktiviert**|
|:-----|:-----|:-----|:-----|
|PSTN-Endpunkt  <br/> |Gleichzeitiges Klingeln über die Standort-Voiceroutingrichtlinie des Anrufers zulässig  <br/> |Gleichzeitiges Klingeln über die Standort-Voiceroutingrichtlinie des Anrufers zulässig  <br/> |Gleichzeitiges Klingeln über die Voicerichtlinie des Anrufers an Trunks zulässig, die nicht für das Routing Location-Based sind  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Kumulatives Update 4 für Skype for Business

Mit kumulativem Update 4 sehen Sie Folgendes:

- Location-Based Routing wird weiterhin über Voice Policy aktiviert, einschließlich Skype for Business Mobile-Clients.

- Das Anrufverhalten für Skype for Business Mobile-Clients basiert darauf, ob sie für Location-Based Routing und den kommunizierenden Client aktiviert sind. Dies ist statisch ausgelegt, es kann jedoch in bestimmten Situationen eine Anstrengung geben, einen Skype for Business Mobile-Client einem lokalen PSTN-Gateway zuzuordnen und bestimmte Verhaltensweisen wie eine Eskalation zu ermöglichen.

- Unabhängig von Ihrem Betriebssystem sollte Ihr Skype for Business Mobile-Client die gleiche Funktionalität haben.

In der folgenden Tabelle werden Einige der Szenarien nach kumulativem Update 4 beschrieben:

|**Standortbasierter Routingbenutzer**|**Andere Partei**|**Aktion**|**Ergebnis**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile empfängt einen eingehenden PSTN-Anruf.  <br/> |Der Anruf wird über "Anruf über Arbeit" (CvW) und nicht über VoIP geroutet.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile macht einen ausgehenden PSTN-Anruf.  <br/> |Der Anruf wird über CvW und nicht über VoIP geroutet.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile befindet sich in einem PSTN-Anruf. Skype for Business Mobile eskaliert dann den Anruf an einen anderen Benutzer oder Kontakt.  <br/> |Der Anruf wird über VoIP geroutet, wenn der Benutzer oder Kontakt lokal an das PSTN-Gateway-Leg ist.  <br/> Wenn sich der Benutzer oder Kontakt remote vom PSTN-Gateway-Leg befindet, wird der Anruf über CvW geroutet.  <br/> Wenn der Zielbenutzer nicht über das PSTN erreichbar ist, schlägt der Anruf fehl.  <br/> Wenn es sich bei dem Zielkontakt um automatische Telefonzentrale (CaA) handelt, wird der Anruf blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> |Ein Skype for Business Mobile initiiert einen Sprachanruf an einen anderen Skype for Business-Client oder Partnerbenutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> | Ein Skype for Business-Client oder Partnerbenutzer initiiert einen Sprachanruf an einen Skype for Business Mobile-Location-Based Routingbenutzer. <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> |Ein Skype for Business-Client oder Ein Verbundbenutzer wird an einen Skype for Business Mobile-Benutzer in einem VoIP-Anruf ausgeführt. Beide Parteien eskalieren zu einem zusätzlichen Skype for Business- oder Verbundbenutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbundbenutzer wird bei einem Skype for Business Mobile-Location-Based anruft. Eine Skype for Business Mobile-Partei eskaliert an einen PSTN-Benutzer.  <br/> |Der Anruf wird blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbundbenutzer ist in einem Location-Based an einen Skype for Business Mobile Location-Based Routing-Benutzer; Eine der beiden Parteien eskaliert zu einem CAA-Kontakt.  <br/> |Der eskalierte Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbundbenutzer ist bei einem VoIP-Anruf an einen Skype for Business Mobile Location-Based Routingbenutzer, und der Verbundbenutzer eskaliert an einen PSTN-Benutzer.  <br/> |Die Eskalation ist basierend auf dem Location-Based des Verbundbenutzers zulässig oder nicht zulässig. Die Anwendung des Skype for Business Mobile Location-Based Routingbenutzers nimmt keine Aktion vor.  <br/> |

### <a name="delegation"></a>Delegierung

Die Delegierungsfunktionen in Skype for Business sind von Location-Based Routing betroffen:

- Wenn eine Stellvertretung, die für Location-Based Routing aktiviert ist, einen Anruf im Auftrag eines Managers abgesetzt hat, wird die Voicerichtlinie des Stellvertreters verwendet, um den Anruf zu autorisieren, und die Standort-Voiceroutingrichtlinie des Stellvertreters wird zum Weiterleiten des Anrufs verwendet.

- Für eingehende PSTN-Anrufe an einen Vorgesetzten gelten dieselben Regeln, die für die Anrufleitung oder gleichzeitiges Klingeln gelten, wie in den Themen Anrufübertragungen und Weiterleitung und Gleichzeitiges Klingeln beschrieben.

- Wenn ein Stellvertreter einen PSTN-Endpunkt als gleichzeitiges Ringziel fest legt, wird für einen eingehenden Anruf an den Vorgesetzten die Voiceroutingrichtlinie des Standorts verwendet, der dem eingehenden Trunk zugeordnet ist, um den Anruf an den PSTN-Endpunkt des Stellvertreters weiterzuleiten.

- Für die Delegierung wird empfohlen, dass sich der Manager und seine zugehörigen Stellvertreter in der Regel am gleichen Netzwerkstandort befinden.

## <a name="other-planning-considerations"></a>Andere Planungsüberlegungen

Bei der planung Location-Based Routing sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.

### <a name="disaster-recovery"></a>Notfallwiederherstellung

Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen normaler Vorgänge im primären Pool bleibt Location-Based Routing während eines Notfall- und Wiederherstellungsverfahrens immer erzwungen.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Das Konfigurieren Location-Based Routing wirkt sich auf die Planung der Bereitstellung der Gateways aus, die Ihren Survivable Branch Appliances zugeordnet sind. Das Ihrem SBA zugeordnete Gateway muss sich am gleichen Netzwerkstandort wie Ihre Survivable Branch Appliance befinden. Andernfalls ist es Benutzern, die in Ihrer Survivable Branch Appliance zu Hause sind, nicht gestattet, ausgehende Anrufe zu platzieren, wenn Location-Based Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch Appliance und dem zentralen Standort nicht mehr besteht, werden Location-Based Routingeinschränkungen erzwungen.

## <a name="client-and-server-support-for-location-based-routing"></a>Client- und Serverunterstützung für Location-Based Routing

Location-Based Routing wird von Skype for Business Server erzwungen. Skype for Business Server kann die Netzwerkstandorte identifizieren, an denen Benutzer über das Unternehmensnetzwerk eine Verbindung herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, gilt ihr Standort als unbekannt.

### <a name="server-support"></a>Serverunterstützung

Location-Based Routing erfordert, dass Skype for Business Server oder Lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt wird. Wenn diese Versionen des Servers nicht installiert sind, können standortbasierte Routingeinschränkungen nicht vollständig erzwungen werden.

In der folgenden Tabelle wird die Kombination von Serverrollen und -versionen aufgeführt, die für das Routing Location-Based werden.

****

|**Poolversion**|**Version des Vermittlungsservers**|**Unterstützt**|
|:-----|:-----|:-----|
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 Februar 2013  <br/> |Kumulatives Update für Skype for Business Server oder Lync Server 2013 Februar 2013  <br/> |ja  <br/> |
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 Februar 2013  <br/> |Lync Server 2013  <br/> |nein  <br/> |
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 Februar 2013  <br/> |Lync Server 2010  <br/> |nein  <br/> |
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 Februar 2013  <br/> |Office Communications Server 2007 R2  <br/> |nein  <br/> |
|Lync Server 2013  <br/> |Beliebiger Wert  <br/> |nein  <br/> |
|Lync Server 2010  <br/> |Beliebiger Wert  <br/> |nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Beliebiger Wert  <br/> |nein  <br/> |

### <a name="client-support"></a>Clientunterstützung

In der folgenden Tabelle sind die Clients aufgeführt, die Location-Based routing unterstützt werden.

****

|**Clienttyp**|**Unterstützt**|**Details**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |ja  <br/> ||
|Lync 2013  <br/> |ja  <br/> ||
|Lync 2010  <br/> |ja  <br/> ||
|Office Communicator 2007 R2  <br/> |nein  <br/> ||
|Lync Phone Edition  <br/> |ja  <br/> ||
|Lync Attendant  <br/> |ja  <br/> ||
|Lync for Windows 8  <br/> |nein  <br/> ||
|Lync Mobile 2013  <br/> |nein  <br/> |VoIP muss für Lync Mobile 2013-Clients deaktiviert sein, wenn sie von Benutzern mit aktivierter Location-Based werden.  <br/> |
|Lync Mobile 2010  <br/> |ja  <br/> ||

> [!NOTE]
> Um VoIP für Skype for Business-Clients zu deaktivieren, weisen Sie eine Mobilitätsrichtlinie mit der Einstellung IP Audio/Video zu, die für alle Benutzer deaktiviert ist, die für das Routing Location-Based sind. Weitere Informationen zur Mobilitätsrichtlinie finden Sie unter [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funktionen, die vom Routing nicht Location-Based werden

Location-Based Routing gilt nicht für die folgenden Arten von Interaktionen. Location-Based Routing wird nicht erzwungen, wenn Skype for Business-Endpunkte mit PSTN-Endpunkten interagieren, die diese Funktionen verwenden.

- PSTN-Einwahl bei Konferenzen

- Eingehende und ausgehende PSTN-Anrufe über die Reaktionsgruppe

- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen

- Eingehende PSTN-Anrufe an den Ansagedienst

- Eingehende PSTN-Anrufe, die über die Gruppenanrufannahme abgerufen werden

Zum Erzwingen Location-Based Routingregeln für die Arten von Interaktionen in der folgenden Liste müssen Sie das routing for conferencing Location-Based aktivieren:

- PSTN-Einwahl von Konferenzen

- Eskalationen von Peer-zu-Peer-Audiounterhaltungen zu Konferenzen mit PSTN-Endpunkten

- Beratungsübertragungen mit PSTN-Endpunkten

Informationen zum Location-Based Routing für Konferenzen finden Sie unter [Location-Based Routing for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing).