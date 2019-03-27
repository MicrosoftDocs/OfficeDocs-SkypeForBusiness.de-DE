---
title: Plan für IPv6 in Skype for Business
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Zusammenfassung: Implementieren IPv6 vor der Installation von Skype für Business Server.'
ms.openlocfilehash: c2ac3470646c78e0a7312fb9390a712321793915
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884747"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Plan für IPv6 in Skype for Business
 
**Zusammenfassung:** Implementieren Sie vor der Installation von Skype für Business Server IPv6.
  
Skype für Business Server bietet Unterstützung für IP Version 6 (IPv6) Adressen Adressen zusammen mit Fortgesetzte Unterstützung für IP Version 4 (IPv4). 

Bei IPv4-Adressen handelt es sich um 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen. Aufgrund der steigenden Anzahl von Geräten weltweit haben die verfügbaren IPv4-Adressen zur Neige. Aus diesem Grund werden viele neue Geräte verschoben, Verwendung von IPv6-Adressen. IPv6-Adressen haben die gleiche Funktion wie IPv4-Adressen (und bieten einige zusätzliche Features), anstelle von lediglich 32 Bit werden von IPv6-Adressen jedoch 128 Bit verwendet. Dadurch steht nicht nur ein neuer Satz, sondern auch eine größere Anzahl an Adressen zur Verfügung. 

Eine typische IPv4-Adresse sieht in etwa wie folgt: 192.0.2.235, während eine IPv6-Adresse wie folgt aussieht: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. Die Änderung der Formatierung und Funktionen für Geräte, die IPv6-Adressen verwenden erfordert verschiedene Aspekte der Bereitstellung und Konfiguration Ihrer Skype für Business Server-Installation. 

Dieses Thema enthält die folgenden Abschnitte:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Wenn Sie, dass Sie IPv6-Adressen verwenden werden feststellen, finden Sie im Artikel [Konfigurieren der IP-Adresstypen in Skype für Unternehmen](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Übersicht über IP-Adresstypen
<a name="over"> </a>

Ihnen stehen drei Optionen beim Konfigurieren von IP-Adressen in Skype für Business Server. Sie können Skype für Business Server unterstützen nur IP Version 4 (IPv4), nur IP Version 6 (IPv6), konfigurieren oder eine Kombination aus beidem (als eine mit doppeltem Stack bezeichnet). Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:
  
- **Nur IPv4** IPv6 erstellt wurde, da die ganzen Welt nicht mehr genug IPv4-Adressen vorhanden ist. IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen möglicherweise kommunizieren muss, unterstützen derzeit noch nicht IPv6 und möglicherweise bleibt das auch noch eine ganze Weile so. Eine reine IPv4-Konfiguration hilft Ihnen, um sicherzustellen, dass Ihre Skype für Business Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.
    
- **Nur IPv6** Dagegen wird eine reine IPv6-Implementierung die Kommunikation mit vielen vorhandenen Geräten ausgeschlossen.
    
- **Dualer Stapel** Mit doppeltem Stack ist ein Netzwerk, in denen sowohl IPv4 als auch IPv6-Adressen aktiviert sind. Diese Konfiguration wird in Skype für Business Server unterstützt, da in den meisten Fällen der Übergang vom vollständig IPv4 in voller IPv6 mehrere Jahre dauern wird.
    
In den folgenden Abschnitten werden die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene Skype für Business Server-Features.
  
> [!NOTE]
> Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der serienmäßigen Bereitstellung nicht unterstützt. 
  
### <a name="client-registration"></a>Clientregistrierung
<a name="client"> </a>

|**Clientendpunkt-Netzwerk**|**Servernetzwerk**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dualer Stapel  <br/> |
|Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |
|Dualer Stapel  <br/> |IPv6  <br/> |
|IPv6  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>Peer-to-Peer-Client
<a name="peer"> </a>

Peer-to-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.
  
|**Clientendpunkt 1**|**Clientendpunkt 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dualer Stapel  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Konferenzen
<a name="conf"> </a>

Konferenzfunktionen beinhalten Audio/Video, Anwendungsfreigabe und Datenzusammenarbeitsanwendungen wie Whiteboards und Dateifreigabe.
  
|**Clientendpunkt-Netzwerk**|**Servernetzwerk**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dualer Stapel  <br/> |
|Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |
|Dualer Stapel  <br/> |IPv6  <br/> |
|IPv6  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>Vermittlungsserver/PSTN
<a name="med"> </a>

Skype für Business Server unterstützt keine medienumgehung für public switched Telephone Network (Telefonfestnetz PSTN) anrufen, wenn der Datenverkehr über eine IPv6-Schnittstelle ist. Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren. 
  
|**Primäre Schnittstelle 1**|**PSTN-Schnittstelle (auf dem Vermittlungsserver)**|**Einstellung für das PSTN-Gateway**|
|:-----|:-----|:-----|
|IPv4  <br/> |Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |IPv6  <br/> |
   
1. Die primäre Schnittstelle ist die Schnittstelle, mit die die Skype für Business Server-Komponenten kommuniziert.
  
### <a name="remote-user-peer-to-peer-communications"></a>Peer-to-Peer-Kommunikation mit Remotebenutzern
<a name="remote"> </a>

Peer-to-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.
  
|**Netzwerk des Remotebenutzers**|**Edgeserver (externer Edge)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Konfiguration mit Front-End-Pool und Edgepool
<a name="FE_pool"> </a>

Die folgende Tabelle zeigt die Matrix der unterstützten zwischen den Front-End-Server-Pool und der internen Edge-Server-Pool.
  
**Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)**

||**Edgepool: IPv4** <br/> |**Edgepool: Dualer Stapel** <br/> |**Edgepool: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Front-End-Pool: IPv4** <br/> |Ja   <br/> |Ja  <br/> |Nein  <br/> |
|**Front-End-Pool: Dualer Stapel** <br/> |Ja   <br/> |Ja  <br/> |Nein  <br/> |
|**Front-End-Pool: IPv6** <br/> |Nein  <br/> |Nein  <br/> |Ja\*  <br/> |
   
\*Verwenden Sie diese Kombination nur in einer laborumgebung.
  
Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.
  
**Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)**

||**Edgepool (Externer Edge): IPv4** <br/> |**Edgepool (Externer Edge): Dualer Stapel** <br/> |**Edgepool (Externer Edge): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Edgepool (Interner Edge): IPv4** <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|**Edgepool (Interner Edge): Dualer Stapel** <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|**Edgepool (Interner Edge): IPv6** <br/> |Nein  <br/> |Nein  <br/> |Ja\*  <br/> |
   
\*Verwenden Sie diese Kombination nur in einer laborumgebung.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Erweiterte Unterstützung für Enterprise-VoIP für IPv6
<a name="Ent_V"> </a>

Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E911-Notrufdienste oder Medienumgehung beinhalten, können nur mit IPv4 oder als Implementierung mit dualem Stapel konfiguriert werden. Endpunkte, die nur IPv6 verwenden, haben diese Funktionen nicht.
  
> [!NOTE]
> In einer Bereitstellung dualer-Stapel stellen Skype für Business Server, auch wenn eine Skype für Business Server-Client an einen Skype für Business Server stellt eine Verbindung über IPv6 bemüht, eine geeignete IPv4-Adresse zur Unterstützung der E9-1-1 zuordnen. 
  
Standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.
  
Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Andere Skype für Business Serverunterstützung für IPv6
<a name="Ent_V"> </a>

Zusätzlich zu den Features und Komponenten, die weiter oben erwähnten unterstützt Skype für Business Server IPv6 für die folgenden Features:
  
- **Beständiger Chat**
    
    Sie Konfigurieren von IPv6 für beständigen Chat mithilfe des Topologie-Generator. Ausführliche Informationen zum Konfigurieren von Persistent Chat finden Sie unter Deploying Persistent Chat Server-Dokumentation.
    
- **QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen (KDS)**
    
    In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.
    
## <a name="technical-requirements-for-ipv6"></a>Technische Anforderungen für IPv6
<a name="tech"> </a>

Wenn Sie Skype für Business Server für IPv6 konfigurieren möchten, sollten beachten Sie Folgendes:
  
- Um IPv6-Adressen mit Skype für Business Server verwenden, müssen Sie Domain Name System (DNS) Einträge für Datensätze erstellen, der ermittelt und in eine IPv6-Adresse aufgelöst werden muss. IPv6-DNS verwendet Host-AAAA-Einträge (vier „A“). Falls Sie sowohl IPv4 als auch IPv6 in Ihrer Bereitstellung verwenden, empfiehlt es sich, sowohl Host-A-Einträge für IPv4 als auch Host-AAAA-Einträge für IPv6 zu konfigurieren und zu verwalten. Selbst wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die noch IPv4 verwenden.
    
    Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen. Falls der Client oder Server IPv6 nicht verwendet, wird nicht auf den Eintrag verwiesen. Umstellungstechnologien bestimmen anhand von Konfiguration und Richtlinien, welcher Eintrag verwendet werden soll.
    
- Jede IPv6-Adresse hat einen Adressbereich. Die drei Bereiche, die Sie für IPv6-Adressen verwenden können sind globalen IPv6-Adressen (analog zu öffentliche IPv4-Adressen), IPv6 eindeutige lokalen Adressen (ähnlich wie die private Adressbereiche IPv4) und IPv6-Link-Local-Adressen (analog zu automatische private IP-Adressen in WindowsServer für IPv4). Alle Server innerhalb eines Pools sollten IPv6-Adressen mit dem gleichen Adressbereich aufweisen. 
    
> [!IMPORTANT]
> IPv6 ist ein komplexes Thema und erfordert sorgfältige Planung mit Teammitgliedern Netzwerke und Ihren Internetanbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server-Ebene und auf die Skype für Business Server Ebene zuweisen wie erwartet funktionieren. Zusätzliche Informationen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Überlegungen zu Migration und Koexistenz für IPv6
<a name="migration"> </a>

IP Version 6 (IPv6) wird auf Lync Server 2010 oder Office Communications Server nicht unterstützt. Aus Gründen der Pilotphase können Sie Lync Server 2010 und Skype Business Server dualen Koexistenz testen. Es wird empfohlen, alle Pools für einen bestimmten zentralen Standort auf wurden Skype für Business Server aktualisiert vor dem Aktivieren von IPv6 (Dual-Stack Network) für alle Pools. Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Nur-IPv6-Pool in Ihrer Testumgebung zum Testen einrichten.
  
Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:
  
- Skype für Business Server, Lync Server 2013 und Lync Server 2010-Pools im IPv4-Modus, gemeinsame Verwendung mit Skype für Business Server im dualen Modus.
    
- Skype für Business Server-Pool im nur-IPv6-Modus, wenn der reine IPv6-Pool in Silos zusammengefasst wird.
    
## <a name="see-also"></a>Siehe auch
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[Reagieren auf IP Version 6-Architektur](https://tools.ietf.org/html/rfc4291)
  
[Format der IPv6-globale Unicast-Adresse](https://tools.ietf.org/html/rfc3587)
  
[Eindeutige lokale IPv6-Unicast-Adressen](https://tools.ietf.org/html/rfc4193)
