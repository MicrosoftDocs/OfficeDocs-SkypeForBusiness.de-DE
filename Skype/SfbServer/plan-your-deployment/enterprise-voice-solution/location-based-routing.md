---
title: Plan für standortbasiertes Routing in Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Planung für standortbasiertes Routing in Skype for Business Server Enterprise-VoIP, einschließlich Interaktion mit gleichzeitiger Klingeln und Delegierung sowie unterstützte Szenarien für standortbasiertes Routing.
ms.openlocfilehash: fae78dcbc1aa1d92d6fe192618d9fda5001436a1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802905"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>Plan für standortbasiertes Routing in Skype for Business

Planung für standortbasiertes Routing in Skype for Business Server Enterprise-VoIP, einschließlich Interaktion mit gleichzeitiger Klingeln und Delegierung sowie unterstützte Szenarien für standortbasiertes Routing.

Standortbasiertes Routing ermöglicht das Einschränken des Routings von anrufen zwischen VoIP-Endpunkten und PSTN-Endpunkten basierend auf dem Standort der Gesprächspartner. Standortbasiertes Routing ist eine anrufverwaltungsfunktion, die steuert, wie Anrufe von Skype for Business Server weitergeleitet werden. Sie erzwingt Anruf Autorisierungsregeln, um festzulegen, ob Anrufe basierend auf dem geographischen Standort des Skype for Business-Anrufers an PBX-oder PSTN-Endpunkte weitergeleitet werden können.

Das standortbasierte Routing stellt einen neuen Regelsatz zur Verfügung, mit dem das Routing nationaler und internationaler PSTN-Anrufe modifiziert werden kann, um eine Gebührenumgehung zu verhindern. Beim standortbasierten Routing lassen sich die Regeln flexibel auf bestimmte Regionen und Gateways und sogar auf bestimmte Benutzergruppen beschränken.

Die folgenden Szenarien veranschaulichen die Haupttypen von Einschränkungen, die standortbasiertes Routing erzwingen kann:

- Ausstiegs Anrufe – standortbasiertes Routing kann ausgehende Anrufe an ein PSTN-Gateway erzwingen, das sich in derselben Region befindet, in der der Anrufer die PSTN-Maut Umgehung verhindert, wodurch Anrufe an ein PSTN-Gateway in einer anderen Region als der Aufrufer verhindert werden.

- Ingress-Anrufe – standortbasiertes Routing kann verhindern, dass eingehende PSTN-Anrufe an Skype for Business-Endpunkte abringen, wenn sich das PSTN-Gateway, das den eingehenden Anruf leitet, nicht in derselben Region wie der angerufene Skype for Business-Benutzer befindet.

- Unbekannte Regionen – standortbasiertes Routing schränkt eingehende und ausgehende PSTN-Anrufe von und zu Benutzern ein, die sich an unbestimmten Speicherorten befinden (also Remotebenutzer, die eine Verbindung mit dem Internet herstellen oder sich in unbekannten Regionen befinden).

- Internationale Regionen – standortbasiertes Routing erzwingt die Weiterleitung von ausgehenden Anrufen über internationale PSTN-Gateways, wenn ein Gateway lokal zum Standort des Benutzers nicht gefunden werden kann.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>Leitfaden für das Anwenden von Standort basiertem Routing

Standortbasiertes Routing kann je nach Situation am Endpunkt des Benutzers oder am Standort des Netzwerkstandorts des PSTN-Gateways angewendet werden. In diesem Thema finden Sie Anleitungen zur Anwendung des standortbasierten Routings.

### <a name="applying-location-based-routing-at-the-users-location"></a>Anwenden von Standort basiertem Routing am Standort des Benutzers

Standortbasiertes Routing nutzt dieselben netzwerkregionen,-Standorte und-Subnetze, wie Sie in Skype for Business Server von E9-1-1, CAC und medienumgehung definiert sind, um Anruf Weiterleitungs Einschränkungen anzuwenden, um die PSTN-Maut Umgehung zu verhindern. Der Standort eines Benutzers wird durch das IP-Subnetz der Skype for Business-Endpunkt (s) des Benutzers festgelegt, von dem die Verbindung hergestellt wird. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, von denen mehrere zu vom Administrator definierten Netzwerkbereichen zusammengefasst sind. Standortbasiertes Routing wird basierend auf der Netzwerk Website des Benutzers erzwungen.

Standortbasierte Routingregeln werden pro Netzwerk Website angewendet, was bedeutet, dass ein bestimmter Satz von Regeln auf alle Endpunkte angewendet wird, die für standortbasiertes Routing aktiviert sind, die sich innerhalb desselben Netzwerkstandorts befinden. Administratoren können das standortbasierte Routing auf Netzwerkstandorte anwenden, die dies erfordern.

Richtlinien für das VoIP-Routing können auf Grundlage von Netzwerkstandorten definiert werden, um ein bestimmtes Gateway in das öffentliche Telefonnetz zu definieren, das dann von allen Benutzern, die sich am gleichen Netzwerkstandort befinden, für Verbindungen mit Rufnummern im öffentlichen Telefonnetz verwendet werden muss. Solche VoIP-Routing Richtlinien haben Vorrang vor dem Routing, das durch die VoIP-Richtlinie des Benutzers definiert wird, wenn sich der Benutzer in einer Netzwerk Website befindet, die für standortbasiertes Routing aktiviert ist, und dadurch das Routing von Anrufen über andere PSTN-Gateways verhindert, die für Standortbasiertes Routing Wenn ein Skype for Business-Benutzer einen PSTN-Anruf einrichtet, bestimmt die VoIP-Richtlinie des Benutzers, ob der Nutzer autorisiert werden kann, den Anruf zu tätigen. Wenn die VoIP-Richtlinie des Benutzers es dem Benutzer ermöglicht, den Anruf zu tätigen, bestimmt standortbasiertes Routing, von welchem PSTN-Gateway der Anruf ausgehen soll. Standortbasiertes Routing macht diese Ermittlung auf Grundlage des Standorts des Benutzers.

Der Standort eines Benutzers kann auf folgende Weise kategorisiert werden:

- Der Benutzer befindet sich in einer bekannten Netzwerk Website, die für standortbasiertes Routing aktiviert ist, und seine DID-Nummer (Direktwahl) wird auf einem PSTN-Gateway beendet, das sich auf demselben Netzwerkstandort befindet (also Office). Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Aus dem öffentlichen Telefonnetz für den Benutzer eingehende Anrufe werden an Endpunkte geroutet, die sich am gleichen Netzwerkstandort wie das Gateway in das öffentliche Telefonnetz befinden.

- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich von dem Netzwerkstandort unterscheidet, an dem sich das Gateway in das öffentliche Telefonnetz befindet (d. h., der Benutzer ist zu einem anderen Unternehmensstandort gereist). Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Für den Benutzer aus dem öffentlichen Telefonnetz eingehende Anrufe werden nicht an Endpunkte geroutet, die sich an anderen Standorten befinden als das Gateway in das öffentliche Telefonnetz, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.

- Wenn sich ein Benutzer in einer Netzwerk Website befindet, die der Skype for Business Server-Bereitstellung unbekannt ist, basiert das Routing von ausgehenden Anrufen auf der VoIP-Richtlinie, die dem Benutzer für PSTN-Gateways zugewiesen ist, die nicht an standortbasierte Routing Einschränkungen gebunden sind. Eingehende Anrufe aus dem öffentlichen Telefonnetz werden nicht an Endpunkte geroutet, die sich an unbekannten Netzwerkstandorten befinden, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Anwenden von Standort basiertem Routing am Standort des PSTN-Gateways

Für Anrufe, die über PSTN-Gateways und PBX-Anlagen geroutet werden, können abhängig vom Standort solcher Systeme standortbasierte Routing Einschränkungen erforderlich sein. Standortbasiertes Routing kann bei der Granularität pro trunk-Basis aktiviert werden.

Standortbasiertes Routing führt die folgenden Regelsätze ein, wenn Sie in einem Trunk aktiviert sind:

- Wenn standortbasiertes Routing pro trunk aktiviert ist, werden die Regeln, die für diesen Stamm definiert sind, nur auf Anrufe angewendet, die durch diesen Trunk geleitet werden.

- Um zu verhindern, dass PSTN-Mautgebühren für Anrufe von einer Netzwerk Website abweichen, die sich auf der Netzwerk Website befinden, auf der sich das PSTN-Gateway befindet, führt das ortsbasierte Routing die Zuordnung einer Netzwerk Website zu einem bestimmten Stamm ein. Dadurch wird die Netzwerk Website definiert, die das Weiterleiten von Anrufen an einen bestimmten trunk ermöglicht.

Trunks kann auf zwei Arten für standortbasiertes Routing aktiviert werden:

- Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das Telefonfestnetz weiterleitet. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endgeräte weitergeleitet, die sich am selben Netzwerkstandort befinden wie der Trunk.

- Der trunk ist für einen Vermittlungs Server-Peer definiert, der keine Anrufe an das PSTN abgibt und Dienste für Benutzer mit älteren Telefonen an statischen Speicherorten (also Telefonanlagen) abruft. Für diese spezielle Konfiguration wird für alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, angenommen, dass sie vom selben Netzwerkstandort kommen wie der Trunk. Anrufe von PBX-Benutzern haben die gleiche standortbasierte Routing Erzwingung wie Skype for Business-Benutzer, die sich am gleichen Netzwerkstandort wie der Stamm befinden. Wenn zwei PBX-Anlagen, die sich auf separaten Netzwerkstandorten befinden, über Skype for Business Server verbunden sind, ermöglicht standortbasiertes Routing die Weiterleitung von einem PBX-Endpunkt in einer Netzwerk Website zu einem anderen PBX-Endpunkt auf der anderen Netzwerk Website. Dieses Szenario wird nicht durch standortbasiertes Routing blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise wie ein Skype for Business-Benutzer am gleichen Standort können Endpunkte, die mit einem Vermittlungsserver-Peer mit dieser Konfiguration verbunden sind, Anrufe an und von anderen Vermittlungsserver-Peers tätigen oder empfangen, die keine Anrufe an t weiterleiten. o das PSTN (also ein Endpunkt, der mit einer anderen Telefonanlage verbunden ist), unabhängig von der Netzwerk Website, der der Vermittlungs Server-Peer zugeordnet ist. Alle eingehenden Anrufe, ausgehenden Anrufe, Anruf Übertragungen und Anrufweiterleitung mit PSTN-Endpunkten unterliegen dem standortbasierten Routing, um nur PSTN-Gateways zu verwenden, die als lokal für diesen Vermittlungs Server-Peer definiert sind.

## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

Beim standortbasierten Routing werden die folgenden allgemeinen Regeln auf das Routing von Anrufen in den folgenden Szenarios angewendet.

### <a name="outgoing-calls"></a>Ausgehende Anrufe

Das Routing von ausgehenden Anrufen von Benutzern, die für standortbasierte Routings aktiviert sind, ist vom Netzwerkspeicherort des Endpunkts des Benutzers betroffen. Die folgende Tabelle zeigt, wie sich der standortbasierte Routing auf das Routing von ausgehenden Anrufen auswirkt, abhängig von der Position des Endpunkts des Anrufers.

**Der Anrufer tätigt einen ausgehenden Anruf in das öffentliche Telefonnetz**

||**Der Benutzerendpunkt befindet sich an einem Netzwerkstandort, der für standortbasiertes Routing aktiviert ist**|**Der Benutzerendpunkt befindet sich an einem unbekannten Netzwerkstandort oder einem Standort, der nicht für standortbasiertes Routing aktiviert ist**|
|:-----|:-----|:-----|
|Autorisierung ausgehender Anrufe  <br/> |Anruf ist basierend auf der VoIP-Richtlinie des Benutzers autorisiert  <br/> |Anruf ist basierend auf der VoIP-Richtlinie des Benutzers autorisiert  <br/> |
|Routing ausgehender Anrufe  <br/> |Der Anruf wird entsprechend der VoIP-Routing Richtlinie der Netzwerk Website weitergeleitet.  <br/> |Der Anruf wird entsprechend der VoIP-Richtlinie des Benutzers und nur über Trunks geroutet, die für standortbasiertes Routing nicht aktiviert sind (sofern verfügbar).  <br/> |

### <a name="incoming-calls"></a>Eingehende Anrufe

Die Weiterleitung eingehender Anrufe an Benutzer, die für standortbasierte Routings aktiviert sind, hängt von der Position des Endpunkts des Benutzers ab. Die Weiterleitung eingehender Anrufe ist auf die folgende Weise betroffen. Wenn ein Benutzer einen eingehenden Anruf an einem Endpunkt hat, der sich in einer standortbasierten Routing fähigen Netzwerk Website befindet, und sich der Endpunkt am gleichen Netzwerkstandort wie das PSTN-Gateway befindet, wird der Anruf weitergeleitet. Wenn ein Benutzer einen eingehenden Anruf an einem Endpunkt hat, der sich in einer standortbasierten Routing fähigen Netzwerk Website befindet, und sich der Endpunkt an einem anderen Netzwerkstandort als dem PSTN-Gateway befindet, wird der Anruf nicht weitergeleitet. Wenn ein Benutzer keine Endpunkte an derselben Netzwerk Website wie das PSTN-Gateway hat, von dem der eingehende Anruf stammt, wird der eingehende Anruf direkt an die Voicemail des Benutzers weitergeleitet, und eine Benachrichtigung über verpasste Anrufe wird an den angerufenen Teilnehmer gesendet.

Die Einstellungen für die Anrufweiterleitung eines Benutzers, der für standortbasiertes Routing aktiviert ist, werden weiterhin erzwungen, die weitergeleiteten Anrufe unterliegen jedoch standortbasierten Routing Einschränkungen des Benutzers.

Die folgende Tabelle zeigt, wie sich der standortbasierte Routing auf das Routing von eingehenden Anrufen auswirkt, abhängig von der Position des Endpunkts des aufgerufenen. Die Netzwerk Website des PSTN-Gateways ist für standortbasiertes Routing aktiviert, und das ortsbasierte Routing ermöglicht nur das Routing von PSTN-Anrufen an Endpunkte innerhalb desselben Netzwerkstandorts.

**Angerufener empfängt einen eingehenden Anruf aus dem Telefonfestnetz (PSTN)**

||**Endpunkt des angerufenen, der sich am gleichen Netzwerkstandort wie das PSTN-Gateway befindet**|**Der Endpunkt des angerufenen, der sich nicht am gleichen Netzwerkstandort wie das PSTN-Gateway befindet**|**Endpunkt des angerufenen, der sich in einer unbekannten Netzwerk Website befindet oder für standortbasiertes Routing nicht aktiviert ist**|
|:-----|:-----|:-----|:-----|
|Routing eines eingehenden Telefonfestnetzanrufs  <br/> |Der eingehende Anruf wird an die Endpunkte des anrufenden weitergeleitet  <br/> |Der eingehende Anruf wird nicht an die Endpunkte des anrufenden weitergeleitet  <br/> |Der eingehende Anruf wird nicht an die Endpunkte des anrufenden weitergeleitet  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>Durchstellung und Weiterleitung von Anrufen

Wenn ein PSTN-Endpunkt beteiligt ist, analysiert standortbasiertes Routing die Position des Endpunkts der Calle und den Endpunkt, an den der Anruf übertragen oder weitergeleitet wird (d. h. Übertragung/Forward-Ziel). Standortbasiertes Routing bestimmt, ob der Anruf je nach Position beider Endpunkte übertragen oder weitergeleitet werden soll.

Die folgende Tabelle zeigt das Szenario eines Skype for Business-Benutzers in einem Anruf mit einem PSTN-Endpunkt, und der Skype for Business-Benutzer übergibt den Anruf an einen anderen Skype for Business-Benutzer. Je nach dem Standort des Netzwerkstandorts des Endpunkts des Empfängers wirkt sich der standortbasierte Routing auf das Routing der Anrufweiterleitung oder der Weiterleitung aus.

**Einleitung der Anrufdurchstellung oder -weiterleitung**

|**Benutzer, der die Durchstellung oder Weiterleitung des Anrufs einleitet**|**Der Zielendpunkt befindet sich am gleichen Netzwerkstandort wie der Benutzer, der die Anrufdurchstellung oder -weiterleitung einleitet**|**Der Zielendpunkt befindet sich an einem anderen Netzwerkstandort als der Benutzer, der die Anrufdurchstellung oder -weiterleitung einleitet**|**Der Zielendpunkt ist auf der unbekannten Netzwerk Website oder Netzwerk Website nicht für standortbasiertes Routing aktiviert.**|
|:-----|:-----|:-----|:-----|
|Skype for Business-Benutzer  <br/> |Anrufweiterleitung oder -durchstellung ist erlaubt  <br/> |Anrufweiterleitung oder -durchstellung ist nicht erlaubt  <br/> |Anrufweiterleitung oder -durchstellung ist nicht erlaubt  <br/> |

Beispiel: ein Skype for Business-Benutzer in einem Anruf mit einem PSTN-Endpunkt übergibt den Anruf an einen anderen Skype for Business-Benutzer, der sich auf derselben Netzwerk Website befindet. In diesem Fall ist die Durchstellung des Anrufs erlaubt.

Die folgende Tabelle zeigt das Szenario eines Skype for Business-Benutzers in einem Anruf mit einem anderen Skype for Business-Benutzer, und einer der Benutzer übergibt den Anruf an einen PSTN-Endpunkt. Die Tabelle zeigt im Detail, wie sich das standortbasierte Routing abhängig vom Standort des Benutzers, an den der Anruf durchgestellt werden soll, auf den Anruf auswirkt.

**Anrufdurchstellung oder -weiterleitung an einen Endpunkt im öffentlichen Telefonnetz**

|**Zielendpunkt für die Anrufdurchstellung oder -weiterleitung**|**Skype for Business-Benutzer auf derselben Netzwerk Website**|**Skype for Business-Benutzer in verschiedenen Netzwerk Websites**|**Ein oder beide Skype for Business-Benutzer in einer unbekannten Netzwerk Website oder Netzwerk Website sind für standortbasiertes Routing nicht aktiviert**|
|:-----|:-----|:-----|:-----|
|Endpunkt im öffentlichen Telefonnetz  <br/> |Anrufweiterleitung oder-Übertragung, die von der Website-VoIP-Routing Richtlinie des übertragenen Benutzers zugelassen wird  <br/> |Anrufweiterleitung oder-Übertragung, die von der Website-VoIP-Routing Richtlinie des übertragenen Benutzers zugelassen wird  <br/> |Anrufweiterleitung oder Übertragung durch die VoIP-Richtlinie des übertragenen Benutzers nur über Trunks, die für standortbasiertes Routing nicht aktiviert sind  <br/> |

Beispiel: ein Skype for Business-Benutzer in einem Anruf mit einem anderen Skype for Business-Benutzer, der sich am gleichen Netzwerkstandort befindet, überträgt den Anruf an einen PSTN-Endpunkt, und die Anrufübertragung ist zulässig.

### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn der angerufene Teilnehmer das gleichzeitige Klingeln aktiviert hat, analysiert standortbasiertes Routing den Standort des anrufenden und die Endpunkte der angerufenen Parteien, um zu ermitteln, ob der Anruf weitergeleitet werden soll.

Die folgende Tabelle zeigt einen Benutzer, für den paralleles Anrufen konfiguriert ist, und das Ziel des parallelen Anrufs ist ein Benutzer am gleichen oder einem unbekannten Netzwerkstandort.

****

|**Eingehender Anruf aus dem öffentlichen Telefonnetz für**|**Am gleichen Netzwerkstandort wie der Angerufene**|**An einem anderen Netzwerkstandort als der Angerufene**|**Befindet sich auf der unbekannten Netzwerk Website oder ist für standortbasiertes Routing nicht aktiviert**|
|:-----|:-----|:-----|:-----|
|Skype for Business-Benutzer  <br/> |Paralleles Anrufen zugelassen  <br/> |Paralleles Anrufen nicht zugelassen  <br/> |Paralleles Anrufen nicht zugelassen  <br/> |

Die folgende Tabelle zeigt einen Anruf von einem Skype for Business-Benutzer (also Skype for Business-Anrufer) an derselben Netzwerk Website, an einer anderen Netzwerk Website oder an einer unbekannten Netzwerk Website. Der Angerufene hat einen Endpunkt im öffentlichen Telefonfestnetz (z. B. ein Mobiltelefon), der als Ziel für paralleles Anrufen konfiguriert ist. In diesem Szenario bestimmt standortbasiertes Routing, ob der Anruf an das Ziel für das gleichzeitige Klingeln (also das Mobiltelefon) des angerufenen weitergeleitet werden soll.

****

|**Ziel für paralleles Anrufen**|**Am gleichen Netzwerkstandort wie der Angerufene**|**An einem anderen Netzwerkstandort als der Angerufene**|**Befindet sich auf der unbekannten Netzwerk Website oder ist für standortbasiertes Routing nicht aktiviert**|
|:-----|:-----|:-----|:-----|
|Endpunkt im öffentlichen Telefonnetz  <br/> |Gleichzeitiges Klingeln über die VoIP-Routing Richtlinie des Anrufers erlaubt  <br/> |Gleichzeitiges Klingeln über die VoIP-Routing Richtlinie des Anrufers erlaubt  <br/> |Gleichzeitiges Klingeln über die VoIP-Richtlinie des Anrufers an Trunks, die für standortbasiertes Routing nicht aktiviert sind  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business, kumulatives Update 4

Mit dem kumulativen Update 4 geschieht Folgendes:

- Standortbasiertes Routing wird weiterhin über VoIP-Richtlinien aktiviert, einschließlich Skype for Business-mobilen Clients.

- Das Anrufverhalten für mobile Skype for Business-Clients hängt davon ab, ob Sie für standortbasiertes Routing und den kommunizierenden Client aktiviert sind. Dies sollte statisch sein, aber in bestimmten Situationen besteht die Möglichkeit, dass ein Skype for Business Mobile-Client einem lokalen PSTN-Gateway zugeordnet wird und bestimmte Verhaltensweisen wie zum Beispiel eine Eskalation zugelassen werden.

- Ihr Skype for Business Mobile-Client sollte unabhängig vom Betriebssystem die gleichen Funktionen aufweisen.

In der folgenden Tabelle werden Sie durch einige der nach dem kumulativen Update 4 geltenden Szenarien geführt:

|**Standortbasierter Routing Benutzer**|**Andere Teilnehmer**|**Aktion**|**Ergebnis**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype for Business Mobile erhält einen eingehenden PSTN-Anruf.  <br/> |Der Anruf wird über „Geschäftlich anrufen“ (Call via Work, CvW) und nicht über VoIP weitergeleitet.  <br/> |
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype for Business Mobile führt einen ausgehenden PSTN-Anruf.  <br/> |Der Anruf wird über CvW und nicht über VoIP weitergeleitet.  <br/> |
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype for Business Mobile ist in einem PSTN-Anruf. Skype for Business Mobile eskaliert den Anruf dann an einen anderen Nutzer oder Kontakt.  <br/> |Wenn es sich um einen Benutzer oder Kontakt handelt, der für den PSTN-Gateway-Abschnitt lokal ist, wird der Anruf über VoIP weitergeleitet.  <br/> Wenn es sich um einen Remotebenutzer oder -kontakt (aus der Perspektive des PSTN-Gateways) handelt, wird der Anruf über „Geschäftlich anrufen“ weitergeleitet.  <br/> Wenn der Zielbenutzer über das PSTN nicht erreichbar ist, schlägt der Anruf fehl.  <br/> Wenn es sich bei dem Zielkontakt um eine automatische Konferenztelefonzentrale (Conference Auto Attendant, CAA) handelt, wird der Anruf blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> |Ein Skype for Business-Mobiltelefon initiiert einen Sprachanruf an einen anderen Skype for Business-Client oder einen Verbund Nutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> | Ein Skype for Business-Client oder ein Verbundbenutzer initiiert einen Sprachanruf an einen mobilen standortbasierten Skype for Business-Routing Benutzer. <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype for Business-Client oder Verbundbenutzer  <br/> |Ein Skype for Business-Client oder ein Verbundbenutzer befindet sich in einem VoIP-Anruf an einen mobilen Skype for Business-Benutzer. Jede Partei eskaliert zu einem zusätzlichen Skype for Business-oder Federated-Nutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Föderationsbenutzer ist bei einem Skype for Business-standortbasierten Routing Benutzer auf Sprachanruf angewiesen. eine Skype for Business-Mobil Partei eskaliert zu einem PSTN-Benutzer.  <br/> |Der Anruf wird blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbundbenutzer befindet sich in einem VoIP-Anruf an einem mobilen standortbasierten Skype for Business-Routing Benutzer; Jede Partei eskaliert zu einem CAA-Kontakt.  <br/> |Der eskalierte Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbundbenutzer befindet sich in einem VoIP-Anruf an einem mobilen standortbasierten Skype for Business-Routing Benutzer, und der Verbundbenutzer eskaliert zu einem PSTN-Benutzer.  <br/> |Die Eskalation wird basierend auf dem standortbasierten Routing des Verbundbenutzers zugelassen oder nicht zulässig. Die Anwendung Skype for Business Mobile Location-Based Routing-Benutzer unternimmt keine Aktionen.  <br/> |

### <a name="delegation"></a>Delegierung

Die Delegierungsfunktionen in Skype for Business sind von Standort basiertem Routing wie folgt betroffen:

- Wenn eine für standortbasierte Weiterleitung aktivierte Stellvertretung einen Anruf im Auftrag eines Managers anbietet, wird die VoIP-Richtlinie des Stellvertreters verwendet, um den Anruf zu genehmigen, und die VoIP-Routing Richtlinie des Stellvertreters wird zum Weiterleiten des Anrufs verwendet.

- Für eingehende Anrufe aus dem öffentlichen Telefonnetz für einen Vorgesetzten gelten die gleichen Regeln wie für Anrufweiterleitung oder paralleles Anrufen, wie in den Themen zur Anrufweiterleitung und -durchstellung bzw. zum parallelen Anrufen beschrieben.

- Wenn eine Stellvertretung einen PSTN-Endpunkt als gleichzeitiges Klingel Ziel festlegt, wird für einen eingehenden Anruf an den Manager die VoIP-Routing Richtlinie der Website verwendet, die dem eingehenden Stamm zugeordnet ist, um den Anruf an den PSTN-Endpunkt der Stellvertretung weiterzuleiten.

- Für die Delegierung empfiehlt es sich, dass sich der Manager und die zugehörigen Stellvertretungen normalerweise auf derselben Netzwerk Website befinden.

## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

Bei der Planung von Standort basiertem Routing sollten Sie die Auswirkungen auf die folgenden Szenarien berücksichtigen.

### <a name="disaster-recovery"></a>Notfallwiederherstellung

Während eines Failovers vom primären Pool zu einem Sicherungspool sowie beim Wiederherstellen von normalen Vorgängen für den primären Pool bleibt das standortbasierte Routing während eines Disaster-und Wiederherstellungsverfahrens zu allen Zeiten erzwungen.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Die Konfiguration des standortbasierten Routings wirkt sich auf die Planung aus, in der Sie die Gateways bereitstellen, die ihren überlebenden Branch-Appliances zugeordnet sind. Das Gateway, das mit Ihrem SBA verbunden ist, muss sich im selben Netzwerkstandort wie Ihre Survivable Branch-Appliance befinden. Andernfalls ist es Benutzern, die auf Ihrer Survivable Branch-Appliance verwaltet werden, nicht möglich, ausgehende Anrufe zu tätigen, wenn standortbasiertes Routing konfiguriert ist. Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch-Appliance und dem zentralen Standort ausgefallen ist, bleiben standortbasierte Routing Einschränkungen erzwungen.

## <a name="client-and-server-support-for-location-based-routing"></a>Client- und Serverunterstützung für standortbasiertes Routing

Standortbasiertes Routing wird von Skype for Business Server erzwungen. Skype for Business Server kann die Netzwerk Websites identifizieren, über die Benutzer im Unternehmensnetzwerk eine Verbindung herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, werden deren Positionen als unbekannt angesehen.

### <a name="server-support"></a>Serverunterstützung

Standortbasiertes Routing setzt voraus, dass Skype for Business Server oder lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt wird. Wenn diese Versionen des Servers nicht installiert sind, können standortbasierte Routing Einschränkungen nicht vollständig erzwungen werden.

In der folgenden Tabelle wird die Kombination aus Serverrollen und Versionen aufgeführt, die für standortbasiertes Routing unterstützt werden.

****

|**Poolversion**|**Mediation Server-Version**|**Unterstützt**|
|:-----|:-----|:-----|
|Kumulatives Update für Skype for Business Server oder lync Server 2013 Februar 2013  <br/> |Kumulatives Update für Skype for Business Server oder lync Server 2013 Februar 2013  <br/> |ja  <br/> |
|Kumulatives Update für Skype for Business Server oder lync Server 2013 Februar 2013  <br/> |Lync Server 2013  <br/> |nein  <br/> |
|Kumulatives Update für Skype for Business Server oder lync Server 2013 Februar 2013  <br/> |Lync Server 2010  <br/> |nein  <br/> |
|Kumulatives Update für Skype for Business Server oder lync Server 2013 Februar 2013  <br/> |Office Communications Server 2007 R2  <br/> |nein  <br/> |
|Lync Server 2013  <br/> |Beliebig  <br/> |nein  <br/> |
|Lync Server 2010  <br/> |Beliebig  <br/> |nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Beliebig  <br/> |nein  <br/> |

### <a name="client-support"></a>Clientunterstützung

In der folgenden Tabelle sind die Clients aufgeführt, die vom standortbasierten Routing unterstützt werden.

****

|**Clienttyp**|**Unterstützt**|**Details**|
|:-----|:-----|:-----|
|Skype for Business  <br/> |ja  <br/> ||
|Lync 2013  <br/> |ja  <br/> ||
|Lync 2010  <br/> |ja  <br/> ||
|Office Communicator 2007 R2  <br/> |nein  <br/> ||
|Lync Phone Edition  <br/> |ja  <br/> ||
|Lync Attendant  <br/> |ja  <br/> ||
|Lync für Windows 8  <br/> |nein  <br/> ||
|Lync Mobile 2013  <br/> |nein  <br/> |VoIP muss für lync Mobile 2013-Clients deaktiviert sein, wenn Sie von Benutzern mit aktiviertem Standort basiertem Routing verwendet werden.  <br/> |
|Lync Mobile 2010  <br/> |ja  <br/> ||

> [!NOTE]
> Um VoIP für Skype for Business-Clients zu deaktivieren, weisen Sie der Einstellung "IP Audio/Video" eine Mobilitätsrichtlinie zu, die für alle Benutzer deaktiviert ist, die für standortbasiertes Routing aktiviert sind. Ausführlichere Informationen zu Mobilitätsrichtlinien finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).

## <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Standortbasiertes Routing gilt nicht für die folgenden Arten von Interaktionen. Standortbasiertes Routing wird nicht erzwungen, wenn Skype for Business-Endpunkte mithilfe dieser Funktionen mit PSTN-Endpunkten interagieren.

- PSTN-Einwahl bei Konferenzen

- Eingehende und ausgehende PSTN-Anrufe über die Reaktionsgruppe

- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen

- Eingehende PSTN-Anrufe an den Ankündigungsdienst

- Eingehende PSTN-Anrufe, die über die Gruppenanrufannahme abgerufen werden

Wenn Sie Standortbasierte Routingregeln für die Typen von Interaktionen in der folgenden Liste erzwingen möchten, müssen Sie standortbasiertes Routing für Konferenzen aktivieren:

- PSTN-Einwahl von Konferenzen

- Eskalationen von Peer-zu-Peer-Audiounterhaltungen in Konferenzen unter Beteiligung von PSTN-Endpunkten

- Anrufdurchstellung nach Rücksprache unter Beteiligung von PSTN-Endpunkten

Informationen zum Aktivieren des standortbasierten Routings für Konferenzen finden Sie unter [standortbasiertes Routing für Konferenzen](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).


