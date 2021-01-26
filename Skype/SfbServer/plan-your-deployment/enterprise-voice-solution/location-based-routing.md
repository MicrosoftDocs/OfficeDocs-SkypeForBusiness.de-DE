---
title: Planen des Location-Based routing in Skype for Business
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
description: Planung für standortbasiertes Routing in Skype for Business Server Enterprise-VoIP, einschließlich Interaktion mit gleichzeitigen Klingeln und Delegierung sowie unterstützte Szenarien für standortbasiertes Routing.
ms.openlocfilehash: 473ed77dce8edaee3b43822adcb8920027795d9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825555"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Planen des Location-Based routing in Skype for Business

Planung für standortbasiertes Routing in Skype for Business Server Enterprise-VoIP, einschließlich Interaktion mit gleichzeitigen Klingeln und Delegierung sowie unterstützte Szenarien für standortbasiertes Routing.

Location-Based Routing ermöglicht das Einschränken des Routings von Anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Anrufbesprechungen. Location-Based Routing ist eine Anrufverwaltungsfunktion, die steuert, wie Anrufe von Skype for Business Server geroutet werden. Es erzwingt Anrufautorisierungsregeln darüber, ob Anrufe basierend auf dem geografischen Standort des Skype for Business-Anrufers an PbX- oder Festnetzendpunkte geleitet werden können.

Location-Based Routing führt einen neuen Satz von Regeln ein, mit dem das Routing von nationalen und internationalen Festnetzanrufen geändert wird, um eine gebührenpflichtige Umgehung zu verhindern. Location-Based Routing bietet die Flexibilität, diese Regeln auf bestimmte Regionen, bestimmte Gateways oder nur auf bestimmte Benutzergruppen zu bereichern.

Die folgenden Szenarien veranschaulichen die wichtigsten Arten von Einschränkungen, die Location-Based Routing erzwingen kann:

- Ausgehende Anrufe: Das Location-Based Routing kann ausgehende Anrufe erzwingen, um ausgehende Anrufe an ein PSTN-Gateway zu übergehen, das sich in derselben Region wie der Anrufer befindet, um eine gebührenpflichtige Umgehung des Telefonnetz zu verhindern, wodurch verhindert wird, dass Anrufe an ein PstN-Gateway in einer anderen Region als der Anrufer abgehen.

- Eingangsanrufe– Das Location-Based Routing kann eingehende Festnetzanrufe verhindern, um Skype for Business-Endpunkte angerufen zu klingeln, wenn sich das PSTN-Gateway, das den eingehenden Anruf weiterleite, nicht in derselben Region wie der angerufene Skype for Business-Benutzer befindet.

- Unbekannte Regionen: Das Location-Based Routing schränkt ein- und ausgehende Festnetzanrufe an und von Benutzern ein, die sich an unbestimmten Standorten befinden (d. h. Remotebenutzer, die sich über das Internet verbinden oder sich in unbekannten Regionen befinden).

- Internationale RegionenLocation-Based Routing erzwingt das Routing ausgehender Anrufe über internationale PSTN-Gateways, wenn ein gateway lokal zum Standort des Benutzers nicht gefunden werden kann.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Leitfaden für die Anwendung von Location-Based Routing

Location-Based routing depending on the situation can be applied at the user's endpoint network site location or at the PSTN gateway's network site location. Dieses Thema enthält Anleitungen dazu, Location-Based A0 angewendet wird.

### <a name="applying-location-based-routing-at-the-users-location"></a>Anwenden Location-Based Routing am Standort des Benutzers

Location-Based Routing nutzt die gleichen Netzwerkregionen, Standorte und Subnetze wie in Skype for Business Server definiert, die von E9-1-1, Cac und Medienumgehung verwendet werden, um Anrufroutingeinschränkungen anzuwenden, um eine gebührenpflichtige Umgehung des Telefonnetzes zu verhindern. Der Standort eines Benutzers wird durch das IP-Subnetz der Skype for Business-Endpunkte des Benutzers bestimmt, von dem aus eine Verbindung besteht. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, der in vom Administrator definierte Netzwerkregionen aggregiert wird. Location-Based Routing wird basierend auf dem Netzwerkstandort des Benutzers erzwungen.

Location-Based Routingregeln werden pro Netzwerkstandort angewendet, d. h., ein festgelegter Satz von Regeln wird auf alle Endpunkte angewendet, die für Location-Based Routing aktiviert sind, die sich am selben Netzwerkstandort befinden. Administratoren können das Location-Based auf Netzwerkstandorte anwenden, die dies erfordern.

Richtlinien für das Voicerouting können pro Netzwerkstandort definiert werden, um ein bestimmtes PSTN-Gateway zu definieren, das von allen Benutzern am Netzwerkstandort zum Anrufen von Festnetznummern verwendet werden soll. Solche Richtlinien für das Voicerouting haben Vorrang vor dem Routing, das von der Benutzer-Voice-Richtlinie definiert wird, wenn sich der Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing aktiviert ist, und verhindert das Routing von Anrufen über andere PSTN-Gateways, die für Location-Based Routing aktiviert sind. Wenn ein Skype for Business-Benutzer einen Festnetzanruf abnetzt, bestimmt die Sprachrichtlinie des Benutzers, ob der Benutzer autorisiert werden kann, den Anruf zu führen. Wenn die Sprachrichtlinie des Benutzers es dem Benutzer ermöglicht, den Anruf zu platzieren, bestimmt Location-Based Routing, von welchem PSTN-Gateway der Anruf abgangen soll. Location-Based routing macht diese Bestimmung basierend auf dem Standort des Benutzers.

Ein Benutzerstandort kann auf folgende Weise kategorisiert werden:

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der für das Location-Based Routing aktiviert ist, und seine DID (Direct Inward Dial)-Nummer endet an einem PSTN-Gateway, das sich am selben Netzwerkstandort (d. h. im Büro) befindet. Das Routing ausgehender Anrufe wird über die Voiceroutingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet, verwendet. Eingehende Festnetzanrufe an den Benutzer werden an Endpunkte geleitet, die sich am gleichen Netzwerkstandort wie das PSTN-Gateway befinden.

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich nicht am Netzwerkstandort befindet, an dem sich das PSTN-Gateway befindet. (d. h. der Benutzer ist zu einem anderen Unternehmensbüro reist). Das Routing ausgehender Anrufe wird mithilfe der Voiceroutingrichtlinie des Netzwerkstandorts verwendet, an dem sich der Benutzer befindet. Eingehende Festnetzanrufe an den Benutzer werden nicht an Endpunkte geleitet, die sich an anderen Standorten befinden als das PSTN-Gateway, um eine Gebührenumgehung im öffentlichen Telefonnetz zu verhindern.

- Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der für die Skype for Business Server-Bereitstellung nicht bekannt ist, basiert das Routing ausgehender Anrufe auf der Dem Benutzer zugewiesenen Voicerichtlinie an PSTN-Gateways, die nicht an Location-Based Routingeinschränkungen gebunden sind. Eingehende Festnetzanrufe werden nicht an Endpunkte geleitet, die sich an unbekannten Netzwerkstandorten befinden, um eine Gebührenumgehung im öffentlichen Telefonnetz zu verhindern.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Anwenden Location-Based A0 am Standort des PSTN-Gateways

Anrufe, die über PSTN-Gateways und Nebenstellenanlagen geroutet werden, erfordern möglicherweise Location-Based Routingeinschränkungen, je nach Standort dieser Systeme. Location-Based routing can be enabled at the granularity on a trunk basis.

Location-Based Routing führt die folgenden Regeln ein, wenn diese für einen Trunk aktiviert sind:

- Wenn Location-Based Routing pro Trunk aktiviert ist, werden die für den Trunk definierten Regeln nur auf Anrufe angewendet, die über den Trunk geroutet werden.

- Um die Umgehung von Gebühren im öffentlichen Telefonnetz zu verhindern, wenn Anrufe von einem anderen Netzwerkstandort als dem Netzwerkstandort stammen, an dem sich das PSTN-Gateway befindet, führt Location-Based Routing die Zuordnung eines Netzwerkstandorts zu einem bestimmten Trunk ein. Dadurch wird der Netzwerkstandort definiert, über den Anrufe an einen bestimmten Trunk geroutet werden können.

Trunks können auf zwei Arten für Location-Based A0 aktiviert werden:

- Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das Telefonnetz weiterf?sselt. Eingehende Anrufe, die von einem Trunk dieses Typs geroutet werden, werden nur an Endpunkte geleitet, die sich am gleichen Netzwerkstandort wie der Trunk befinden.

- Der Trunk ist für einen Vermittlungsserver-Peer definiert, der keine Anrufe an das PstN abruft und Benutzer mit älteren Telefonen an einem statischen Standort (z. B. Nebenstellentelefone) unterstützt. Für diese spezielle Konfiguration werden alle eingehenden Anrufe, die von einem Trunk dieses Typs geroutet werden, als vom selben Netzwerkstandort wie der Trunk stammend betrachtet. Anrufe von Nebenstellenanlagenbenutzern haben dieselbe Erzwingung Location-Based Routing wie Skype for Business-Benutzer, die sich am gleichen Netzwerkstandort wie der Trunk befinden. Wenn zwei Nebenstellenanlagen an separaten Netzwerkstandorten über Skype for Business Server verbunden sind, ermöglicht das Location-Based Routing das Routing von einem PbX-Endpunkt an einem Netzwerkstandort an einen anderen PbX-Endpunkt am anderen Netzwerkstandort. Dieses Szenario wird nicht durch das Location-Based blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein Skype for Business-Benutzer am gleichen Standort können Endpunkte, die mit einem Vermittlungsserver-Peer verbunden sind, mit dieser Konfiguration Anrufe an und von anderen Vermittlungsserver-Peers, die keine Anrufe an das Telefonnetz (d. h. einen Endpunkt, der mit einer anderen Nebenstellenanlage verbunden ist) unabhängig vom Netzwerkstandort, dem der Vermittlungsserver-Peer zugeordnet ist, senden oder empfangen. Alle eingehenden Anrufe, ausgehenden Anrufe, Anrufübertragungen und Anrufanrufanrufe, an denen endpunkte im öffentlichen Telefonnetz beteiligt sind, unterliegen dem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die für einen solchen Vermittlungsserver-Peer als lokal definiert sind.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für Location-Based Routing

Location-Based Routing wendet die folgenden allgemeinen Regeln beim Weiterleiten von Anrufen in den folgenden Szenarien an.

### <a name="outgoing-calls"></a>Ausgehende Anrufe

Das Routing ausgehender Anrufe von Benutzern, die Location-Based Routing aktiviert sind, wird vom Netzwerkstandort des Endpunkts des Benutzers beeinflusst. Die folgende Tabelle zeigt, Location-Based Routing das Routing ausgehender Anrufe abhängig vom Standort des Endpunkts des Anrufers beeinflusst.

**Anrufer, der einen ausgehenden Anruf an das Telefonnetz (PSTN) abnetzt**

||**Benutzerendpunkt an einem Netzwerkstandort, der für das Location-Based ist**|**Benutzerendpunkt befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für Location-Based aktiviert**|
|:-----|:-----|:-----|
|Autorisierung ausgehender Anrufe  <br/> |Der Anruf wird basierend auf der Sprachrichtlinie des Benutzers autorisiert.  <br/> |Der Anruf wird basierend auf der Sprachrichtlinie des Benutzers autorisiert.  <br/> |
|Routing ausgehender Anrufe  <br/> |Der Anruf wird gemäß der Voiceroutingrichtlinie des Netzwerkstandorts geroutet.  <br/> |Der Anruf wird gemäß der Benutzer-Voice-Richtlinie und nur über Trunks geroutet, die nicht für Location-Based sind (sofern verfügbar)  <br/> |

### <a name="incoming-calls"></a>Eingehende Anrufe

Das Routing eingehender Anrufe an Benutzer, die Location-Based Routing aktiviert sind, hängt vom Standort des Endpunkts des Benutzers ab. Das Routing eingehender Anrufe wird wie folgt beeinflusst. Wenn ein Benutzer einen eingehenden Anruf an einen Endpunkt hat, der sich an einem Location-Based Routing-fähigen Netzwerkstandort befindet und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf geroutet. Wenn ein Benutzer über einen eingehenden Anruf an einen Endpunkt verfügt, der sich an einem Location-Based Routing-fähigen Netzwerkstandort befindet und sich der Endpunkt an einem anderen Netzwerkstandort befindet als das PSTN-Gateway, wird der Anruf nicht geroutet. Wenn ein Benutzer keine Endpunkte am gleichen Netzwerkstandort wie das PSTN-Gateway hat, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers geleitet, und eine Benachrichtigung über verpasste Anrufe wird an den angerufenen Parteien gesendet.

Die Anrufanleitungseinstellungen eines Benutzers, der für Location-Based Routing aktiviert ist, werden weiterhin erzwungen, weitergeleitete Anrufe unterliegen jedoch den Location-Based Routingeinschränkungen des Benutzers.

Die folgende Tabelle zeigt, Location-Based Routing das Routing eingehender Anrufe abhängig vom Standort des Endpunkts des Anrufers beeinflusst. Der Netzwerkstandort des PSTN-Gateways ist für Location-Based Routing aktiviert, und Location-Based Routing lässt nur das Routing von Festnetzanrufen an Endpunkte innerhalb desselben Netzwerkstandorts zu.

**Anrufer, der einen eingehenden Anruf aus dem Telefonnetz empfängt**

||**Endpunkt des Anrufers am selben Netzwerkstandort wie das PSTN-Gateway**|**Endpunkt des Anrufers, der sich nicht am gleichen Netzwerkstandort wie das GATEWAY des Telefonnetzes befindet**|**Endpunkt des Anrufers, der sich an einem unbekannten Netzwerkstandort befindet oder nicht für Location-Based aktiviert ist**|
|:-----|:-----|:-----|:-----|
|Routing eingehender Festnetzanrufe  <br/> |Eingehender Anruf wird an die Endpunkte des Ansprechers geleitet  <br/> |Eingehender Anruf wird nicht an die Endpunkte des Anrufers geleitet  <br/> |Eingehender Anruf wird nicht an die Endpunkte des Anrufers geleitet  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Anrufübertragungen und Anrufanrufanrufe

Wenn ein Endpunkt im öffentlichen Telefonnetz beteiligt ist, analysiert Location-Based Routing den Standort des Endpunkts des Anrufers und den Endpunkt, an den der Anruf weitergeleitet oder weitergeleitet wird (d. h. Transfer-/Weiterleitungsziel). Location-Based Routing bestimmt, ob der Anruf je nach Standort beider Endpunkte weitergeleitet oder weitergeleitet werden soll.

Die folgende Tabelle veranschaulicht das Szenario eines Skype for Business-Benutzers in einem Anruf mit einem PSTN-Endpunkt, und der Skype for Business-Benutzer überträgt den Anruf an einen anderen Skype for Business-Benutzer. Abhängig vom Netzwerkstandort des Endpunkts des Übertragungsendpunkts wirkt sich Location-Based Routing auf das Routing der Anrufüberleitung oder Weiterleitung aus.

**Initiieren der Anrufüberführung oder Weiterleitung**

|**Benutzer, der die Anrufüberführung/Weiterleitung initiiert**|**Der Zielendpunkt befindet sich an demselben Netzwerkstandort wie der Benutzer, der die Anrufübertragung oder -weiterleitung initiiert.**|**Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als Benutzer, der die Anrufübertragung oder -weiterleitung initiiert.**|**Der Zielendpunkt befindet sich an einem unbekannten Netzwerkstandort oder netzwerkstandort, der nicht für das Location-Based ist**|
|:-----|:-----|:-----|:-----|
|Skype for Business-Benutzer  <br/> |Anruf weiterleiten oder weiterleiten ist zulässig  <br/> |Anruf weiterleiten oder weiterleiten ist nicht zulässig  <br/> |Anruf weiterleiten oder weiterleiten ist nicht zulässig  <br/> |

Beispiel: Ein Skype for Business-Benutzer in einem Anruf mit einem Endpunkt im Telefonnetz überträgt den Anruf an einen anderen Skype for Business-Benutzer, der sich am gleichen Netzwerkstandort befindet. In diesem Fall ist die Anrufüberführung zulässig.

Die folgende Tabelle veranschaulicht das Szenario eines Skype for Business-Benutzers bei einem Anruf mit einem anderen Skype for Business-Benutzer, und einer der Benutzer überträgt den Anruf an einen PSTN-Endpunkt. In Abhängigkeit vom Standort des Benutzers, an den der Anruf durch den Anruf übermittelt wird, wird in der Tabelle aufgeführt, wie sich Location-Based Routing auf den Anruf auswirkt.

**Anrufübergang oder Weiterleitung an den ENDPUNKT PSTN**

|**Ziel des Anrufübergangs/Weiterleitungsendpunkts**|**Skype for Business-Benutzer am gleichen Netzwerkstandort**|**Skype for Business-Benutzer an unterschiedlichen Netzwerkstandorten**|**Ein oder beide Skype for Business-Benutzer an einem unbekannten Netzwerkstandort oder Netzwerkstandort, der nicht für das routingfähige Location-Based ist**|
|:-----|:-----|:-----|:-----|
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Durch die Standort-Voice-Routing-Richtlinie des übertragenen Benutzers zugelassene Anrufanleitung oder -übertragung  <br/> |Durch die Standort-Voice-Routing-Richtlinie des übertragenen Benutzers zugelassene Anrufanleitung oder -übertragung  <br/> |Anrufanleitung oder -übertragung, die von der Sprachrichtlinie des übertragenen Benutzers nur über Trunks zulässig ist, die nicht für das Routing Location-Based sind  <br/> |

Beispiel: Ein Skype for Business-Benutzer bei einem Anruf mit einem anderen Skype for Business-Benutzer, der sich am gleichen Netzwerkstandort befindet, überträgt den Anruf an einen PSTN-Endpunkt, und die Anrufüberweisung ist zulässig.

### <a name="simultaneous-ringing"></a>Gleichzeitiges Klingeln

Wenn für den angerufenen Parteien gleichzeitiges Klingeln aktiviert ist, analysiert Location-Based Routing den Standort des Anrufenden und die Endpunkte der angerufenen Parteien, um festzustellen, ob der Anruf geroutet werden soll.

Die folgende Tabelle zeigt einen Benutzer, der mit gleichzeitigen Klingeln konfiguriert ist, und das Ziel für gleichzeitiges Klingeln ist ein Benutzer am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort.

****

|**Eingehender Festnetzanruf für**|**Sich am gleichen Netzwerkstandort wie der Ankrufer befinden**|**Befindet sich an einem anderen Netzwerkstandort als der Ankrufer**|**Befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für Location-Based aktiviert**|
|:-----|:-----|:-----|:-----|
|Skype for Business-Benutzer  <br/> |Gleichzeitiges Klingeln zulässig  <br/> |Gleichzeitiges Klingeln nicht zulässig  <br/> |Gleichzeitiges Klingeln nicht zulässig  <br/> |

Die folgende Tabelle zeigt einen Anruf von einem Skype for Business-Benutzer (d. h. Skype for Business-Anrufer) am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder von einem unbekannten Netzwerkstandort aus. Der Anrufee verfügt über einen PSTN-Endpunkt (z. B. Mobiltelefon), der als gleichzeitiges Klingelziel konfiguriert ist. In diesem Szenario bestimmt das Location-Based Routing, ob der Anruf an das gleichzeitige Klingelziel (d. h. das Mobiltelefon) des Ansprechten geroutet werden soll oder nicht.

****

|**Ziel für gleichzeitiges Klingeln**|**Sich am gleichen Netzwerkstandort wie der Ankrufer befinden**|**Befindet sich an einem anderen Netzwerkstandort als der Ankrufer**|**Befindet sich an einem unbekannten Netzwerkstandort oder ist nicht für Location-Based aktiviert**|
|:-----|:-----|:-----|:-----|
|Endpunkt des öffentlichen Telefonnetz (PSTN)  <br/> |Gleichzeitiges Klingeln über die Standort-Voice-Routing-Richtlinie des Anrufers zulässig  <br/> |Gleichzeitiges Klingeln über die Standort-Voice-Routing-Richtlinie des Anrufers zulässig  <br/> |Gleichzeitiges Klingeln über die Sprachrichtlinie des Anrufers für Trunks zulässig, die nicht für Location-Based sind  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Kumulatives Update 4 für Skype for Business

Mit dem kumulativen Update 4 sehen Sie Folgendes:

- Location-Based A0 wird weiterhin über die Voicerichtlinie aktiviert, einschließlich Skype for Business Mobile-Clients.

- Das Anrufverhalten für Skype for Business Mobile-Clients basiert darauf, ob sie für Location-Based Routing aktiviert sind, und auf dem kommunizierenden Client. Dies ist als statisch konzipiert, aber in bestimmten Situationen besteht möglicherweise der Versuch, einen Skype for Business Mobile-Client einem lokalen PSTN-Gateway zuzuordnen und bestimmte Verhaltensweisen zu erlauben, z. B. eine Eskalation.

- Unabhängig von Ihrem Betriebssystem sollte Ihr Skype for Business Mobile-Client über die gleiche Funktionalität verfügen.

In der folgenden Tabelle werden einige der Szenarien nach dem kumulativen Update 4 beschrieben:

|**Standortbasierter Routingbenutzer**|**Andere Partei**|**Aktion**|**Result**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile empfängt einen eingehenden PSTN-Anruf.  <br/> |Der Anruf wird über "Anruf über Arbeit" (Call via Work, CvW) und nicht über VoIP geroutet.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile nimmt einen ausgehenden Festnetzanruf vor.  <br/> |Der Anruf wird über CvW und nicht über VoIP geroutet.  <br/> |
|Skype for Business Mobile  <br/> |PSTN  <br/> |Skype for Business Mobile ist in einem Festnetzanruf. Skype for Business Mobile eskaliert dann den Anruf an einen anderen Benutzer oder Kontakt.  <br/> |Der Anruf wird über VoIP geroutet, wenn sich der Benutzer oder Kontakt lokal am Abschnitt des PSTN-Gateways befindet.  <br/> Wenn sich der Benutzer oder Kontakt remote vom Abschnitt des PSTN-Gateways befindet, wird der Anruf über CvW geroutet.  <br/> Wenn der Zielbenutzer nicht über das TELEFON erreichbar ist, schlägt der Anruf fehl.  <br/> Wenn es sich bei dem Zielkontakt um eine automatische Telefonzentrale handelt, wird der Anruf blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Partnerbenutzer  <br/> |Ein Skype for Business Mobile initiiert einen Sprachanruf an einen anderen Skype for Business-Client oder Partnerbenutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Partnerbenutzer  <br/> | Ein Skype for Business-Client oder Partnerbenutzer initiiert einen Sprachanruf an einen Skype for Business Mobile Location-Based Routing-Benutzer. <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Partnerbenutzer  <br/> |Ein Skype for Business-Client- oder Partnerbenutzer hat einen VoIP-Anruf an einen Skype for Business Mobile-Benutzer. Beide Parteien eskalieren an einen zusätzlichen Skype for Business- oder Partnerbenutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbundbenutzer ist bei einem Skype for Business Mobile Location-Based Location-Based per Sprachanruf; Eine Skype for Business Mobile-Partei eskaliert an einen PSTN-Benutzer.  <br/> |Der Anruf wird blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Partnerbenutzer hat einen Location-Based an einen Skype for Business Mobile Location-Based Routing-Benutzer; Beide Parteien eskalieren an einen CAA-Kontakt.  <br/> |Der eskalierte Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Partnerbenutzer hat einen VoIP-Anruf an einen Skype for Business Mobile Location-Based Routing-Benutzer, und der Partnerbenutzer eskaliert an einen PSTN-Benutzer.  <br/> |Die Eskalation wird basierend auf dem Location-Based des Partnerbenutzers zugelassen oder nicht zugelassen. Die Anwendung des Skype for Business Mobile Location-Based Routing-Benutzers wird nicht aktiv.  <br/> |

### <a name="delegation"></a>Delegierung

Die Delegierungsfunktionen in Skype for Business sind von Location-Based Routing betroffen:

- Wenn eine für Location-Based Routing aktivierte Stellvertretung einen Anruf im Auftrag eines Vorgesetzten abgesetzt, wird die Voicerichtlinie der Stellvertretung verwendet, um den Anruf zu autorisieren, und die Standort-Voice-Routing-Richtlinie der Stellvertretung wird zum Weiterleiten des Anrufs verwendet.

- Für eingehende Festnetzanrufe an einen Vorgesetzten gelten die gleichen Regeln, die für die Anrufanleitung oder gleichzeitiges Klingeln gelten, wie in den Themen "Anrufüberleitung und Weiterleitung und gleichzeitiges Klingeln" beschrieben.

- Wenn ein Stellvertreter einen Endpunkt für das Telefonnetz als Ziel für gleichzeitiges Klingeln legt, wird für einen eingehenden Anruf an den Vorgesetzten die Voiceroutingrichtlinie des Standorts verwendet, der dem eingehenden Trunk zugeordnet ist, um den Anruf an den Endpunkt des Stellvertretungs-PSTN weiterzuverleitung.

- Für die Delegierung wird empfohlen, dass sich der Manager und seine zugeordneten Stellvertretung in der Regel am gleichen Netzwerkstandort befinden.

## <a name="other-planning-considerations"></a>Weitere Planungsüberlegungen

Bei der Planung Location-Based Routing sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.

### <a name="disaster-recovery"></a>Notfallwiederherstellung

Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen des normalen Betriebs im primären Pool bleibt das Location-Based Routing während eines Notfall- und Wiederherstellungsverfahrens jederzeit erzwungen.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Die Konfiguration Location-Based Routing wirkt sich auf die Planung der Bereitstellung der Gateways aus, die Ihren Survivable Branch Appliances zugeordnet sind. Das Ihrem SBA zugeordnete Gateway muss sich am gleichen Netzwerkstandort wie Ihre Survivable Branch Appliance befinden. Andernfalls dürfen Benutzer, die in Ihrer Survivable Branch Appliance zu Hause sind, keine ausgehenden Anrufe mehr abstellen, Location-Based Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch Appliance und dem zentralen Standort aus ist, Location-Based Routingeinschränkungen weiterhin erzwungen.

## <a name="client-and-server-support-for-location-based-routing"></a>Client- und Serverunterstützung für Location-Based Routing

Location-Based Routing wird von Skype for Business Server erzwungen. Skype for Business Server kann die Netzwerkstandorte identifizieren, an denen Benutzer eine Verbindung von innerhalb des Unternehmensnetzwerks herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, gilt ihr Standort als unbekannt.

### <a name="server-support"></a>Serverunterstützung

Location-Based routing requires that Skype for Business Server or Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology. Wenn diese Versionen des Servers nicht installiert sind, können standortbasierte Routingeinschränkungen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination aus Serverrollen und Versionen aufgeführt, die für das Location-Based werden.

****

|**Poolversion**|**Vermittlungsserverversion**|**Unterstützt**|
|:-----|:-----|:-----|
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 vom Februar 2013  <br/> |Kumulatives Update für Skype for Business Server oder Lync Server 2013 vom Februar 2013  <br/> |ja  <br/> |
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 vom Februar 2013  <br/> |Lync Server 2013  <br/> |nein  <br/> |
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 vom Februar 2013  <br/> |Lync Server 2010  <br/> |nein  <br/> |
|Kumulatives Update für Skype for Business Server oder Lync Server 2013 vom Februar 2013  <br/> |Office Communications Server 2007 R2  <br/> |nein  <br/> |
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
|Lync Mobile 2013  <br/> |nein  <br/> |VoIP muss für Lync Mobile 2013-Clients deaktiviert werden, wenn es von Benutzern mit aktivierter Location-Based verwendet wird.  <br/> |
|Lync Mobile 2010  <br/> |ja  <br/> ||

> [!NOTE]
> Um VoIP für Skype for Business-Clients zu deaktivieren, weisen Sie eine Mobilitätsrichtlinie mit der Einstellung "IP-Audio/Video" zu, die für alle Benutzer deaktiviert ist, die für das Location-Based sind. Weitere Informationen zur Mobilitätsrichtlinie finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Funktionen, die vom Location-Based nicht unterstützt werden

Location-Based Routing gilt nicht für die folgenden Arten von Interaktionen. Location-Based Routing wird nicht erzwungen, wenn Skype for Business-Endpunkte mit Endpunkten im öffentlichen Telefonnetz interagieren, die diese Funktionen verwenden.

- PSTN-Einwahl in Konferenzen

- Eingehende und ausgehende Festnetzanrufe über Reaktionsgruppe

- Parken oder Abrufen von Anrufen im öffentlichen Telefonnetz über das Parken von Anrufen

- Eingehende Festnetzanrufe an den Ankündigungsdienst

- Eingehende PSTN-Anrufe, die über die Gruppenanrufannahme abgerufen werden

Zum Erzwingen Location-Based Routingregeln für die Arten von Interaktionen in der folgenden Liste müssen Sie das Location-Based für Konferenzen aktivieren:

- PSTN-Einwahl aus Konferenzen

- Eskalationen von Peer-zu-Peer-Audiounterhaltungen zu Konferenzen mit PSTN-Endpunkten

- Mit Öffentlichen Telefonnetzen (PSTN)-Endpunkte

Informationen zum Location-Based routing for Conferencing finden Sie unter ["Standortbasiertes Routing für Konferenzen".](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)


