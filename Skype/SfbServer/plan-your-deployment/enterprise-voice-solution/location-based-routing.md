---
title: Planen des standortbasierten Routings in Skype for Business 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/7/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: Planen von Standortbasierte Weiterleitung im Skype für Business Server Enterprise-VoIP, einschließlich der Interaktion mit Gleichzeitiges Klingeln und Delegierung und unterstützte Szenarios für die Standortbasierte Weiterleitung.
ms.openlocfilehash: 224bae32037ea474dc376e653db5b3d644c859ee
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-location-based-routing-in-skype-for-business-2015"></a>Planen des standortbasierten Routings in Skype for Business 2015
 
Planen von Standortbasierte Weiterleitung im Skype für Business Server Enterprise-VoIP, einschließlich der Interaktion mit Gleichzeitiges Klingeln und Delegierung und unterstützte Szenarios für die Standortbasierte Weiterleitung.
  
Speicherortbasierte Routing ermöglicht das routing von Anrufen zwischen VoIP-Endpunkten und PSTN-Endgeräten basierend auf den Speicherort der Parteien in den Anruf zu beschränken. Speicherortbasierte Routing ist eine Anruf-Management-Funktion, die steuert, wie Anrufe von Skype für Business Server weitergeleitet werden. Sie erzwingt Anruf Autorisierungsregeln auf gibt an, ob Anrufe zu PBX- oder PSTN-Endpunkten, die basierend auf der Skype für geografischen Standort des Anrufers Business weitergeleitet werden können.
  
Das standortbasierte Routing stellt einen neuen Regelsatz zur Verfügung, mit dem das Routing nationaler und internationaler PSTN-Anrufe modifiziert werden kann, um eine Gebührenumgehung zu verhindern. Beim standortbasierten Routing lassen sich die Regeln flexibel auf bestimmte Regionen und Gateways und sogar auf bestimmte Benutzergruppen beschränken.
  
Die folgenden Szenarien veranschaulichen die wichtigsten Typen von Einschränkungen, die Routing speicherortbasierte erzwingen kann:
  
- Ausgang Anrufe - kann Routing speicherortbasierte erzwingen ausgehende Anrufe, die mit einem PSTN-Gateway egress, die sich im selben Bereich als, in dem der Aufrufer wird ein PSTN gebührenpflichtige umgehen, vermieden wird verhindert, dass Anrufe an eine PSTN-Gateway befindet sich in einer anderen Region wie der Aufrufer egress befindet.
    
- Eingehende Anrufe - kann speicherortbasierte Routing zu verhindern, dass eingehende PSTN-Anrufe, Skype für Business-Endpunkte angerufen, das PSTN-Gateway den eingehenden Anruf routing befindet sich nicht im selben Bereich als die gewählte Skype für Geschäftsbenutzer.
    
- Unbekannte Regionen - legt eine Beschränkung auf Standortbasierte Routing eingehender und ausgehender PSTN-Anrufe zu und von Benutzern, die sich in einer unbestimmten Speicherorte (d. h. Remotebenutzer eine Verbindung über das Internet oder befindet sich im unbekannte Regionen) befinden.
    
- Internationale Regionen - erzwingt Routing Standortbasierte Weiterleitung der ausgehenden Anrufe über internationale PSTN-Gateways, wenn ein Gateway lokalen auf den Standort des Benutzers nicht gefunden werden kann.
    
## <a name="guidance-for-where-to-apply-location-based-routing"></a>Leitfaden für standortbasierte Routing übernehmen

Speicherortbasierte Routing je nach Situation kann am Standort des Benutzers Endpunkt Netzwerkspeicherort oder an das PSTN-Gateway Netzwerkspeicherort Website angewendet werden. Dieses Thema enthält Anleitungen auf Standortbasierte Routing angewendet wird.
  
### <a name="applying-location-based-routing-at-the-users-location"></a>Anwenden von speicherortbasierte Routing am Standort des Benutzers

Standortbasierte Weiterleitung nutzt die gleichen Netzwerk-Regionen, Standorten und Subnetzen gemäß Definition in Skype für Business-Servers, der vom E9-1-1, umgehen CAC und Medienumgehung anzuwendende Anruf routing Einschränkungen PSTN Gebühren zu vermeiden. Standort des Benutzers wird durch das IP-Subnetz des Benutzers Skype bestimmt, für die Business-Endpunkte von verbunden sind. Jedes IP-Subnetz ist einem Netzwerkstandort zugeordnet, von denen mehrere zu vom Administrator definierten Netzwerkbereichen zusammengefasst sind. Speicherortbasierte Routing wird basierend auf den Benutzer Netzwerkstandort erzwungen.
  
Speicherortbasierte Routing Regeln werden angewendet, auf einer pro Network-Website, d. h., die ein bestimmten Satz von Regeln an alle Endpunkte für standortbasierte Routing aktiviert angewendet wird, die sich innerhalb der gleichen Website Netzwerk befinden. Administratoren können das standortbasierte Routing auf Netzwerkstandorte anwenden, die dies erfordern.
  
Richtlinien für das VoIP-Routing können auf Grundlage von Netzwerkstandorten definiert werden, um ein bestimmtes Gateway in das öffentliche Telefonnetz zu definieren, das dann von allen Benutzern, die sich am gleichen Netzwerkstandort befinden, für Verbindungen mit Rufnummern im öffentlichen Telefonnetz verwendet werden muss. Diese VoIP-Routingrichtlinien zurückgegeben, haben Vorrang vor der Weiterleitung von VoIP-Richtlinie des Benutzers definiert werden, wenn der Benutzer sich in einem Netzwerkstandort für standortbasierte Routing aktiviert befindet, und es wird verhindert, dass das routing von Anrufen über andere PSTN-Gateways, die für aktiviert sind Standortbasierte Weiterleitung. Wenn eine Skype für Geschäftsbenutzer einen PSTN-Anruf tätigt, bestimmt VoIP-Richtlinie des Benutzers an, ob der Benutzer autorisiert werden kann, um den Anruf zu tätigen. Wenn der Benutzer VoIP-Richtlinie der Benutzer den Anruf zu tätigen kann, bestimmt speicherortbasierte Routing welche PSTN-Gateway der Anruf von egress sollten. Speicherortbasierte Routing wird dies basierend auf den Standort des Benutzers zu bestimmen.
  
Der Standort eines Benutzers kann auf folgende Weise kategorisiert werden:
  
- Der Benutzer befindet sich in einem bekannten Netzwerkstandort für standortbasierte Routing aktiviert, und seine DID (Direct Inward Dial) Zahl, die auf ein PSTN-Gateway im gleichen Netzwerkstandort (d. h. Office) platziert wird beendet. Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Aus dem öffentlichen Telefonnetz für den Benutzer eingehende Anrufe werden an Endpunkte geroutet, die sich am gleichen Netzwerkstandort wie das Gateway in das öffentliche Telefonnetz befinden.
    
- Der Benutzer befindet sich an einem bekannten Netzwerkstandort, der sich von dem Netzwerkstandort unterscheidet, an dem sich das Gateway in das öffentliche Telefonnetz befindet (d. h., der Benutzer ist zu einem anderen Unternehmensstandort gereist). Das Routing ausgehender Anrufe erfolgt anhand der VoIP-Routingrichtlinie des Netzwerkstandorts, an dem sich der Benutzer befindet. Für den Benutzer aus dem öffentlichen Telefonnetz eingehende Anrufe werden nicht an Endpunkte geroutet, die sich an anderen Standorten befinden als das Gateway in das öffentliche Telefonnetz, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden.
    
- Wenn ein Benutzer in einem Netzwerkstandort befindet, der Skype für Business Server-Bereitstellung nicht bekannt ist, wird das routing von ausgehenden Anrufen auf die VoIP-Richtlinie für den Benutzer zu PSTN-Gateways nicht gebunden speicherortbasierte Routing Einschränkungen zugewiesen basieren. Eingehende Anrufe aus dem öffentlichen Telefonnetz werden nicht an Endpunkte geroutet, die sich an unbekannten Netzwerkstandorten befinden, um das Umgehen von Gebühren im öffentlichen Telefonnetz zu vermeiden. 
    
### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>Anwenden von speicherortbasierte Routing an das PSTN-Gateway-Standort

Anrufe über PSTN-Gateways weitergeleitet und Nebenstellenanlagen möglicherweise speicherortbasierte Routing Einschränkungen je nach den Speicherort dieser Systeme erforderlich. Speicherortbasierte Routing kann mit der Granularität für einzelne pro Trunks aktiviert werden.
  
Speicherortbasierte Routing stellt den folgenden Satz von Regeln für einen Trunk aktiviert:
  
- Wenn speicherortbasierte Routing für einzelne pro Trunk aktiviert ist, definieren die Regeln auf, denen nur für Anrufe über dieses Trunk geleitet Trunk angewendet wird.
    
- Um zu verhindern, dass PSTN Gebühren umgehen, wenn Anrufe von einem anderen Netzwerkstandort, die stammen, den Netzwerkstandort, in dem das PSTN-Gateway befindet, führt speicherortbasierte Routing die Zuordnung von einem Netzwerkstandort an einen bestimmten Trunk. Definiert den Netzwerkstandort, der Anrufe an einen bestimmten Trunk weitergeleitet werden kann.
    
Trunks können für standortbasierte Routing auf zwei Arten aktiviert werden:
  
- Der Trunk ist für ein PSTN-Gateway definiert, das Anrufe an das Telefonfestnetz weiterleitet. Eingehende Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, werden nur an Endgeräte weitergeleitet, die sich am selben Netzwerkstandort befinden wie der Trunk.
    
- Der Trunk ist für einen Vermittlungsserver Peer definiert, die Anrufe an die Benutzer über das FESTNETZ oder Dienste mit bisherigen Telefone in eine statische Speicherorte (d. h. PBX-Telefone) egress nicht. Für diese spezielle Konfiguration wird für alle eingehenden Anrufe, die von einem Trunk dieses Typs weitergeleitet werden, angenommen, dass sie vom selben Netzwerkstandort kommen wie der Trunk. Anrufe von Benutzern der Nebenstellenanlage müssen die gleiche speicherortbasierte Routing Erzwingung als Skype für Unternehmensbenutzer, die in den gleichen Netzwerkstandort als den Trunk befinden. Wenn zwei befindet sich in separaten Netzwerkstandorten PBX-Systemen über Skype für Business Server verbunden sind, kann speicherortbasierte Routing, nämlich von einem PBX-Endpunkt in einem Netzwerkstandort zu einem anderen PBX-Endpunkt in den anderen Netzwerkstandort routing. In diesem Szenario werden von speicherortbasierte Routing nicht blockiert. Zusätzlich zu diesem Szenario und auf ähnliche Weise als einen Skype für Benutzer am selben Speicherort Business werden Endpunkte für einen Vermittlungsserver Peer mit dieser Konfiguration verbunden können tätigen oder Entgegennehmen von Anrufen an und von anderen Peer Vermittlungsserver, die nicht, die Anrufe t weiterleiten o das Telefonfestnetz (d. h. einen Endpunkt zu einer anderen Nebenstellenanlage verbunden) unabhängig von den Netzwerkstandort, der Vermittlungsserver Peers zugeordnet ist. Alle eingehenden Anrufe, ausgehende Anrufe Übertragungen aufrufen, und rufen Sie Weiterleitungen-büroumzüge PSTN-Endgeräten, unterliegen Speicherort basiertes Routing PSTN-Gateways verwenden, die eine solche Peer Mediation Server lokal definiert sind.
    
## <a name="scenarios-for-location-based-routing"></a>Szenarien für das standortbasierte Routing

Beim standortbasierten Routing werden die folgenden allgemeinen Regeln auf das Routing von Anrufen in den folgenden Szenarios angewendet.
  
### <a name="outgoing-calls"></a>Ausgehende Anrufe

Das routing ausgehender Anrufe von Benutzern für standortbasierte Routing aktiviert ist, hängt vom Netzwerkspeicherort des Endpunkts des Benutzers betroffen. Die folgende Tabelle veranschaulicht die standortbasierte Routing wirkt sich auf das routing von ausgehenden Anrufen je nach den Speicherort des Endpunkts des Anrufers. 
  
**Platzieren einen ausgehenden Anruf an das Telefonfestnetz Anrufer**

||**Benutzer-Endpunkt befindet sich in einem Netzwerkstandort für standortbasierte Routing aktiviert**|**Benutzer-Endpunkt befindet sich im Netzwerkstandort unbekannt oder für standortbasierte Routing nicht aktiviert.**|
|:-----|:-----|:-----|
|Autorisierung ausgehender Anrufe  <br/> |Anruf ist autorisiert basierend auf VoIP-Richtlinie des Benutzers  <br/> |Anruf ist autorisiert basierend auf VoIP-Richtlinie des Benutzers  <br/> |
|Routing ausgehender Anrufe  <br/> |Anruf wird entsprechend den Netzwerkstandort VoIP-Routingrichtlinie geleitet.  <br/> |Anruf wird gemäß den VoIP-Richtlinie des Benutzers und nur über Trunks nicht aktiviert für standortbasierte Routing (sofern verfügbar) weitergeleitet.  <br/> |
   
### <a name="incoming-calls"></a>Eingehende Anrufe

Das routing von eingehenden Anrufe an Benutzer, die für standortbasierte Routing aktiviert, hängt von der Position des Endpunkts des Benutzers ab. Das routing von eingehenden Anrufen ist auf folgende Weise betroffen. Verfügt ein Benutzer ein eingehenden Anrufs an einen Endpunkt befindet sich in einer speicherortbasierte Routing aktiviert Netzwerkstandort, und der Endpunkt befindet sich in demselben Netzwerkstandort wie das PSTN-Gateway, der Anruf weitergeleitet werden. Verfügt ein Benutzer ein eingehenden Anrufs an einen Endpunkt befindet sich in einer speicherortbasierte Routing aktiviert Netzwerkstandort, und der Endpunkt befindet sich in einem anderen Netzwerkstandort als das PSTN-Gateway, der Anruf nicht weitergeleitet. Wenn ein Benutzer keine Endpunkte befindet sich im gleichen Netzwerkstandort als das PSTN-Gateway hat aus, auf dem, der eingehende Anruf getätigt wird, der eingehende Anruf direkt an die der Benutzer Voicemail weitergeleitet werden und eine Benachrichtigung über verpasste Anrufe an den angerufenen gesendet.
  
Die Anrufweiterleitungseinstellungen eines Benutzers, der für das Routing speicherortbasierte aktiviert ist weiterhin erzwungen werden, jedoch Weiterleiten von Anrufen unterliegen speicherortbasierte Routing Einschränkungen des Benutzers.
  
Die folgende Tabelle veranschaulicht die standortbasierte Routing wirkt sich auf das routing von eingehenden Anrufen je nach den Speicherort des Endpunkts des angerufenen. Der Netzwerkstandort des PSTN-Gateways für standortbasierte Routing aktiviert ist, und standortbasierte nur Routing ermöglicht das routing von PSTN-Anrufe an Endpunkten innerhalb der gleichen Network-Website.
  
**Angerufenen empfangen einen eingehenden Anruf über das PSTN**

||**Endpunkt des angerufenen befindet sich im gleichen Netzwerkstandort als PSTN-gateway**|**Endpunkt des angerufenen befindet sich nicht im gleichen Netzwerkstandort als PSTN-gateway**|**Endpunkt des angerufenen befindet sich im Netzwerkstandort unbekannt oder für standortbasierte Routing nicht aktiviert.**|
|:-----|:-----|:-----|:-----|
|Routing eines eingehenden Telefonfestnetzanrufs  <br/> |Eingehender Anruf wird an die Endpunkte des angerufenen weitergeleitet.  <br/> |Eingehender Anruf wird nicht an die Endpunkte des angerufenen weitergeleitet.  <br/> |Eingehender Anruf wird nicht an die Endpunkte des angerufenen weitergeleitet.  <br/> |
   
### <a name="call-transfers-and-call-forwarding"></a>Durchstellung und Weiterleitung von Anrufen

Wenn ein PSTN-Endpunkt beteiligt ist, analysiert speicherortbasierte Routing den Speicherort der Calle Endpunkt und den Endpunkt, in dem der Anruf weitergeleitet oder an (d. h. Übertragung/Forward Ziel) weitergeleitet werden. Speicherortbasierte Routing bestimmt, ob der Anruf weitergeleitet oder je nach den Speicherort der beide Endpunkte weitergeleitet werden soll.
  
Die folgende Tabelle veranschaulicht das Szenario, einen Skype für Geschäftsbenutzer im Gespräch mit einem PSTN-Endpunkt, und die Skype für Geschäftsbenutzer überträgt den Anruf an eine andere Skype für Geschäftsbenutzer. Abhängig von der Website Netzwerkspeicherort des Endpunkts des Übernehmers wirkt sich auf Standortbasierte Routing, routing, der den Anruf weiterleiten oder weiterleiten.
  
**Ausgehender Anruf weiterleiten oder weiterleiten**

|**Benutzer, die den Anruf initiieren Übertragung/weiterleiten**|**Zielendpunkt befindet sich in demselben Netzwerkstandort als Benutzer initiieren Anruf weiterleiten "oder" weiterleiten**|**Zielendpunkt ist in verschiedenen Netzwerkstandort als Benutzer initiieren Anruf weiterleiten "oder" weiterleiten**|**Zielendpunkt ist unbekannt Netzwerk oder Netzwerkstandort nicht für standortbasierte Routing aktiviert**|
|:-----|:-----|:-----|:-----|
|Skype für Geschäftsbenutzer  <br/> |Anrufweiterleitung oder -durchstellung ist erlaubt  <br/> |Anrufweiterleitung oder -durchstellung ist nicht erlaubt  <br/> |Anrufweiterleitung oder -durchstellung ist nicht erlaubt  <br/> |
   
Beispiel: ein Skype für Geschäftsbenutzer im Gespräch mit einem PSTN-Endpunkt überträgt den Anruf an eine andere Skype für Business-Benutzer, die in der gleichen Network-Website ist. In diesem Fall ist die Durchstellung des Anrufs erlaubt. 
  
Die folgende Tabelle veranschaulicht das Szenario, einen Skype für Geschäftsbenutzer im Gespräch mit einem anderen Skype für Geschäftsbenutzer und einer der Benutzer den Anruf an einen PSTN-Endpunkt überträgt. Die Tabelle zeigt im Detail, wie sich das standortbasierte Routing abhängig vom Standort des Benutzers, an den der Anruf durchgestellt werden soll, auf den Anruf auswirkt.
  
**Anruf weiterleiten oder Weiterleiten an PSTN-Endpunkt**

|**Rufen Sie die Übertragung/Forward Endpunkt Ziel**|**Skype für Unternehmensbenutzer in demselben Netzwerkstandort**|**Skype für Unternehmensbenutzer in verschiedenen Netzwerkstandorten**|**Eine oder beide Skype für Unternehmensbenutzer in unbekannte Netzwerkstandort oder Netzwerkstandort für standortbasierte Routing nicht aktiviert.**|
|:-----|:-----|:-----|:-----|
|Endpunkt im öffentlichen Telefonnetz  <br/> |Anruf weiterleiten oder Übertragung von der übertragenen Benutzer Website VoIP-Routingrichtlinie zulässig  <br/> |Anruf weiterleiten oder Übertragung von der übertragenen Benutzer Website VoIP-Routingrichtlinie zulässig  <br/> |Anruf weiterleiten oder Übertragung von VoIP-Richtlinie der übertragenen Benutzer nur über Trunks zulässig für standortbasierte Routing nicht aktiviert  <br/> |
   
Beispiel: ein Skype für Geschäftsbenutzer im Gespräch mit einem anderen Skype für Business-Benutzer, die in den gleichen Netzwerkstandort ist überträgt den Anruf an einen PSTN-Endpunkt und die Weiterleitung des Anrufs ist zulässig. 
  
### <a name="simultaneous-ringing"></a>Paralleles Anrufen

Wenn der angerufene Gleichzeitiges Klingeln aktiviert hat, analysiert speicherortbasierte Routing dem Standort des Anrufers sowie die Endpunkte der gewählte Parteien um festzustellen, ob der Anruf weitergeleitet werden sollen.
  
Die folgende Tabelle zeigt einen Benutzer, für den paralleles Anrufen konfiguriert ist, und das Ziel des parallelen Anrufs ist ein Benutzer am gleichen oder einem unbekannten Netzwerkstandort. 
  
****

|**Für eingehende PSTN-Anruf**|**Befindet sich am gleichen Standort Netzwerk als des angerufenen**|**Befindet sich in unterschiedlichen Netzwerkstandort als des angerufenen**|**Befindet sich im Netzwerkstandort unbekannt oder für standortbasierte Routing nicht aktiviert.**|
|:-----|:-----|:-----|:-----|
|Skype für Geschäftsbenutzer  <br/> |Paralleles Anrufen zugelassen  <br/> |Paralleles Anrufen nicht zugelassen  <br/> |Paralleles Anrufen nicht zugelassen  <br/> |
   
Die folgende Tabelle veranschaulicht einen Anruf von einem Skype für Geschäftsbenutzer (d. h. Skype für Anrufer Business) in der gleichen Network-Website in einer anderen Netzwerk-Website oder aus einem unbekannten Netzwerkstandort an. Der Angerufene hat einen Endpunkt im öffentlichen Telefonfestnetz (z. B. ein Mobiltelefon), der als Ziel für paralleles Anrufen konfiguriert ist. In diesem Szenario wird speicherortbasierte Routing bestimmen, ob der Anruf an das Ziel des Gleichzeitiges Klingeln (d. h. Mobilnummer) des angerufenen weitergeleitet werden sollen.
  
****

|**Gleichzeitiges Klingeln Ziel**|**Befindet sich am gleichen Standort Netzwerk als des angerufenen**|**Befindet sich in unterschiedlichen Netzwerkstandort als des angerufenen**|**Befindet sich im Netzwerkstandort unbekannt oder für standortbasierte Routing nicht aktiviert.**|
|:-----|:-----|:-----|:-----|
|Endpunkt im öffentlichen Telefonnetz  <br/> |Gleichzeitiges Klingeln passieren des Anrufers Website VoIP-routing-Richtlinie  <br/> |Gleichzeitiges Klingeln passieren des Anrufers Website VoIP-routing-Richtlinie  <br/> |Gleichzeitiges Klingeln passieren des Anrufers VoIP-Richtlinie auf Trunks für standortbasierte Routing nicht aktiviert.  <br/> |
   
### <a name="skype-for-business-cumulative-update-4"></a>Skype for Business, kumulatives Update 4

Mit dem kumulativen Update 4 geschieht Folgendes:
  
- Speicherortbasierte Routing weiterhin über VoIP-Richtlinie, einschließlich Skype für Business-Mobile-Clients aktiviert werden soll.
    
- Das aufrufende Verhalten für Skype für Business-Mobile-Clients basiert auf gibt an, ob sie für standortbasierte Routing- und die kommunizierenden Client aktiviert sind. Dies sollte statisch sein, aber in bestimmten Situationen besteht die Möglichkeit, dass ein Skype for Business Mobile-Client einem lokalen PSTN-Gateway zugeordnet wird und bestimmte Verhaltensweisen wie zum Beispiel eine Eskalation zugelassen werden.
    
- Ihr Skype for Business Mobile-Client sollte unabhängig vom Betriebssystem die gleichen Funktionen aufweisen.
    
In der folgenden Tabelle werden Sie durch einige der nach dem kumulativen Update 4 geltenden Szenarien geführt:
  
|**Standortbasierte Weiterleitung Benutzer**|**Andere Partei**|**Aktion**|**Ergebnis**|
|:-----|:-----|:-----|:-----|
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype für Mobile Business erhält einen eingehenden PSTN-Anruf.  <br/> |Der Anruf wird über „Geschäftlich anrufen“ (Call via Work, CvW) und nicht über VoIP weitergeleitet.  <br/> |
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype für Mobile Business macht einen ausgehenden PSTN-Anruf.  <br/> |Der Anruf wird über CvW und nicht über VoIP weitergeleitet.  <br/> |
|Skype for Business Mobile  <br/> |Telefonfestnetz (PSTN)  <br/> |Skype for Business Mobile ist in einem PSTN-Anruf. Skype für Mobile Business eskaliert klicken Sie dann den Anruf an einen anderen Benutzer oder Kontakt.  <br/> |Wenn es sich um einen Benutzer oder Kontakt handelt, der für den PSTN-Gateway-Abschnitt lokal ist, wird der Anruf über VoIP weitergeleitet.  <br/> Wenn es sich um einen Remotebenutzer oder -kontakt (aus der Perspektive des PSTN-Gateways) handelt, wird der Anruf über „Geschäftlich anrufen“ weitergeleitet.  <br/> Wenn der Zielbenutzer über das PSTN nicht erreichbar ist, schlägt der Anruf fehl.  <br/> Wenn es sich bei dem Zielkontakt um eine automatische Konferenztelefonzentrale (Conference Auto Attendant, CAA) handelt, wird der Anruf blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Skype für Business-Client oder verbundene Benutzer  <br/> |Eine Skype für Mobile Business initiiert einen Anruf an einen anderen Skype für Business-Client oder Federated User.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype für Business-Client oder verbundene Benutzer  <br/> | Eine Skype für Business-Client oder verbundene Benutzer initiiert einen VoIP-Anruf an einen Skype für Benutzer Business Mobile Location-Based Routing. <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Skype für Business-Client oder verbundene Benutzer  <br/> |Eine Skype Business-Client oder eines Benutzers Federated ist auf einen VoIP-Anruf an einen Skype für Business mobiler Benutzer. Kommunikationspartner eskaliert, eine zusätzliche Skype für Business oder Verbundpartner Benutzer.  <br/> |Der Anruf wird über VoIP abgeschlossen.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Verbund gehörenden Benutzer ist auf VoIP-Anruf an einen Skype für Benutzer Business Mobile Location-Based Routing. eine Skype für Mobile Business Partei eskaliert an PSTN-Benutzer.  <br/> |Der Anruf wird blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Benutzer Federated ist auf einen VoIP-Anruf an einen Skype für Benutzer Business Mobile Location-Based Routing. Kommunikationspartner eskaliert an einen Kontakt CAA.  <br/> |Der eskalierte Anruf wird mit einer entsprechenden Fehlermeldung blockiert.  <br/> |
|Skype for Business Mobile  <br/> |Partnerbenutzer  <br/> |Ein Benutzer Federated ist auf einen VoIP-Anruf an einen Skype für Benutzer Business Mobile Location-Based Routing, und der Benutzer Federated eskaliert an PSTN-Benutzer.  <br/> |Die Ausweitung zugelassen oder nicht zugelassen werden basierend auf Standortbasierte Routing des Benutzers Federated. Die Skype für Routing Business Mobile Location-Based Anwendung des Benutzers durchführen keine Aktionen.  <br/> |
   
### <a name="delegation"></a>Delegierung

Die Delegierungsfunktionen in Skype für Unternehmen unterliegen speicherortbasierte Routing auf folgende Weise:
  
- Wenn eine Stellvertretung für standortbasierte Routing Orte ein Anrufs im Namen eines Managers aktiviert, wird der Stellvertretung VoIP-Richtlinie verwendet, um den Anruf und der Stellvertretung Website VoIP, den routing-Richtlinie verwendet wird, um den Anruf weiterleiten zu autorisieren
    
- Für eingehende Anrufe aus dem öffentlichen Telefonnetz für einen Vorgesetzten gelten die gleichen Regeln wie für Anrufweiterleitung oder paralleles Anrufen, wie in den Themen zur Anrufweiterleitung und -durchstellung bzw. zum parallelen Anrufen beschrieben.
    
- Wenn ein Stellvertreter einen PSTN-Endpunkt als Ziel für einen eingehenden Anruf an den Manager Gleichzeitiges Klingeln festgelegt wird die VoIP-Routingrichtlinie der Website, die die eingehenden Trunk zugeordnet ist zum Weiterleiten des Anrufs der Stellvertretung PSTN-Endpunkt verwendet werden.
    
- Für die Delegierung hat empfohlen, dass der Manager und seine zugeordneten Stellvertretungen in der Regel am gleichen Standort Netzwerk befinden.
    
## <a name="other-planning-considerations"></a>Andere Planungsentscheidungen

Bei der Planung der speicherortbasierte Routing, sollten Sie die Auswirkung auf die folgenden Szenarien.
  
### <a name="disaster-recovery"></a>Notfallwiederherstellung

Bei einem Failover vom primären Pool zu einem Sicherungspool sowie wie beim Wiederherstellen der normale Vorgänge in den primären Pool speicherortbasierte Routing erzwungene überhaupt bleibt jederzeit während einer Prozedur Disaster Recovery und Wiederherstellung.
  
### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

Konfigurieren von speicherortbasierte Routing wirkt sich auf die Planung der, in der die Ihrer Survivable Branch Appliances zugeordnete Gateways bereitgestellt. Das Gateway, das der SBA zugeordnet ist, muss am gleichen Standort Netzwerk als Ihrer Survivable Branch Appliance befinden. Anderenfalls verwalteten Benutzer in Ihrer Survivable Branch Appliance wird die ausgehende Anrufe tätigen, wenn speicherortbasierte Routing konfiguriert ist nicht zugelassen werden. Wenn die WAN-Verbindung zwischen Ihrer Survivable Branch Appliance und am zentralen Standort ausgefallen ist, bleibt die speicherortbasierte Routing Einschränkungen erzwungene.
  
## <a name="client-and-server-support-for-location-based-routing"></a>Client- und Serverunterstützung für standortbasiertes Routing

Speicherortbasierte Routing wird vom Skype für Business Server erzwungen. Skype für Business Server kann die Netzwerk-Websites identifizieren, in dem Benutzer von innerhalb des Unternehmensnetzwerks eine Verbindung herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, werden deren Positionen als unbekannt angesehen.
  
### <a name="server-support"></a>Serverunterstützung

Speicherortbasierte Routing erfordert, dass Skype für Business Server oder Lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition-Server in einer gegebenen Topologie bereitgestellt wird. Wenn diese Versionen des Servers nicht installiert sind, können nicht vollständig standortbasierte Routing Einschränkungen erzwungen werden.
  
Die folgende Tabelle zeigt die Kombination von Serverrollen und Versionen, die für das Routing speicherortbasierte unterstützt wird.
  
****

|**Poolversion**|**Mediation Server-version**|**Unterstützt**|
|:-----|:-----|:-----|
|Skype für Business Server oder für Lync Server 2013 für Februar 2013 kumulative Update  <br/> |Skype für Business Server oder für Lync Server 2013 für Februar 2013 kumulative Update  <br/> |ja  <br/> |
|Skype für Business Server oder für Lync Server 2013 für Februar 2013 kumulative Update  <br/> |Lync Server 2013  <br/> |nein  <br/> |
|Skype für Business Server oder für Lync Server 2013 für Februar 2013 kumulative Update  <br/> |Lync Server 2010  <br/> |nein  <br/> |
|Skype für Business Server oder für Lync Server 2013 für Februar 2013 kumulative Update  <br/> |Office Communications Server 2007 R2  <br/> |nein  <br/> |
|Lync Server 2013  <br/> |Beliebig  <br/> |nein  <br/> |
|Lync Server 2010  <br/> |Beliebig  <br/> |nein  <br/> |
|Office Communications Server 2007 R2  <br/> |Beliebig  <br/> |nein  <br/> |
   
### <a name="client-support"></a>Clientunterstützung

Die folgende Tabelle zeigt die Clients, die standortbasierte Routing unterstützt.
  
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
|Lync Mobile 2013  <br/> |nein  <br/> |VoIP muss für Lync Mobile 2013-Clients bei Verwendung von Benutzern mit speicherortbasierte Routing aktiviert deaktiviert werden.  <br/> |
|Lync Mobile 2010  <br/> |ja  <br/> ||
   
> [!NOTE]
> Um VoIP für Skype für Business-Clients zu deaktivieren, weisen Sie eine mobilitätsrichtlinie mit der Einstellung der IP-Audio/Video, für alle Benutzer aktiviert für standortbasierte Routing deaktiviert. Weitere Informationen zu mobilitätsrichtlinie finden Sie unter [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps). 
  
## <a name="capabilities-not-supported-by-location-based-routing"></a>Vom standortbasierten Routing nicht unterstützte Funktionen

Speicherortbasierte Routing gilt nicht für die folgenden Arten von Aktivitäten. Speicherortbasierte Routing wird nicht erzwungen, wenn Skype für Business-Endpunkte interagieren mit PSTN-Endpunkten, die diese Funktionen verwenden.
  
- PSTN-Einwahl bei Konferenzen
    
- Eingehende und ausgehende PSTN-Anrufe über die Reaktionsgruppe
    
- Parken von Anrufen oder Abrufen von PSTN-Anrufen über das Parken von Anrufen
    
- Eingehende PSTN-Anrufe an den Ankündigungsdienst
    
- Eingehende PSTN-Anrufe, die über die Gruppenanrufannahme abgerufen werden
    
Zum Erzwingen der Regeln für die Typen von Aktivitäten in der folgenden Liste Routing speicherortbasierte müssen Sie standortbasierte Routing für Konferenzen aktivieren:
  
- PSTN-Einwahl von Konferenzen
    
- Eskalationen von Peer-zu-Peer-Audiounterhaltungen in Konferenzen unter Beteiligung von PSTN-Endpunkten 
    
- Anrufdurchstellung nach Rücksprache unter Beteiligung von PSTN-Endpunkten
    
Um speicherortbasierte Routing für Konferenzen zu aktivieren, finden Sie unter [speicherortbasierte Routing für Konferenzen](http://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx).
  

