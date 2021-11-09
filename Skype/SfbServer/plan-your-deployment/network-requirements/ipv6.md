---
title: Planen von IPv6 in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Zusammenfassung: Implementieren Sie IPv6, bevor Sie Skype for Business Server installieren.'
ms.openlocfilehash: 21fa37d187f32c9b679a49a3b8181b1a5e2732d1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849748"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Planen von IPv6 in Skype for Business
 
**Zusammenfassung:** Implementieren Sie IPv6, bevor Sie Skype for Business Server installieren.
  
Skype for Business Server umfasst Unterstützung für IP-Adressen der Version 6 (IPv6) sowie die fortlaufende Unterstützung von IP-Adressen der Version 4 (IPv4). 

IPv4-Adressen sind 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen. Aufgrund der zunehmenden Anzahl von Geräten weltweit sind die verfügbaren IPv4-Adressen abgelaufen. Aus diesem Grund werden viele neue Geräte auf die Verwendung von IPv6-Adressen umgezogen. IPv6-Adressen führen die gleiche Funktion wie IPv4-Adressen aus (mit einigen zusätzlichen Features), aber anstatt nur 32-Bit-Adressen verwenden IPv6-Adressen 128-Bit. Dies bietet nicht nur eine neue Gruppe von Adressen, sondern auch eine viel größere Anzahl von Adressen. 

Eine typische IPv4-Adresse sieht etwa wie folgt aus: 192.0.2.235, während eine IPv6-Adresse wie folgt aussieht: 2001:0db8:85a3:0000:0000:8a2e:0370:7334. Die Änderung der Formatierung und Funktionalität für Geräte, die IPv6-Adressen verwenden, erfordert verschiedene Bereitstellungs- und Konfigurationsaspekte in Ihrer Skype for Business Server Installation. 

Dieses Thema umfasst die folgenden Abschnitte:
  
- [Übersicht über IP-Adresstypen](ipv6.md#over)
    
- [Technische Anforderungen für IPv6](ipv6.md#tech)
    
- [Überlegungen zu Migration und Koexistenz für IPv6](ipv6.md#migration)
    
Wenn Sie feststellen, dass Sie IPv6-Adressen verwenden werden, lesen Sie den Artikel zum Konfigurieren von [IP-Adresstypen in Skype for Business](ip-address-types.md) Artikel.
  
## <a name="overview-of-ip-address-types"></a>Übersicht über IP-Adresstypen
<a name="over"> </a>

Sie haben drei Optionen beim Konfigurieren von IP-Adressen in Skype for Business Server. Sie können Skype for Business Server so konfigurieren, dass nur IP-Version 4 (IPv4), nur IP-Version 6 (IPv6) oder eine Kombination aus beiden (als dualer Stapel bezeichnet) unterstützt wird. Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:
  
- **Nur IPv4** IPv6 wurde erstellt, da in der Welt keine IPv4-Adressen mehr vorhanden sind. IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen kommunizieren muss, unterstützen vielleicht derzeit noch nicht IPv6, und möglicherweise bleibt das auch noch eine ganze Weile so. Eine IPv4-only-Konfiguration trägt dazu bei, sicherzustellen, dass Ihre Skype for Business Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.
    
- **Nur IPv6** Im Gegensatz dazu schließt eine vollständige IPv6-Implementierung die Kommunikation mit vielen vorhandenen Geräten aus.
    
- **Dualer Stapel** Der duale Stapel ist ein Netzwerk, in dem sowohl IPv4- als auch IPv6-Adressen aktiviert sind. Diese Konfiguration wird in Skype for Business Server unterstützt, da in den meisten Fällen der Übergang von full-IPv4 zu full-IPv6 mehrere Jahre dauern wird.
    
In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene Skype for Business Server Features beschrieben.
  
> [!NOTE]
> Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der Produktionsbereitstellung nicht unterstützt. 
  
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
   
### <a name="peer-to-peer-client"></a>Peer-zu-Peer-Client
<a name="peer"> </a>

Peer-zu-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.
  
|**Clientendpunkt 1**|**Clientendpunkt 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |Dualer Stapel  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>Konferenzen
<a name="conf"> </a>

Konferenzen umfassen Audio-/Video-, Anwendungsfreigabe- und Datenzusammenarbeitsanwendungen wie Whiteboarding und Dateifreigabe.
  
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

Skype for Business Server unterstützt keine Medienumgehung für PSTN-Anrufe (Public Switched Telephone Network), wenn der Datenverkehr über eine IPv6-Schnittstelle erfolgt. Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren. 
  
|**Primäre Schnittstelle 1**|**PSTN-Schnittstelle (auf dem Vermittlungsserver)**|**Einstellung für das PSTN-Gateway**|
|:-----|:-----|:-----|
|IPv4  <br/> |Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |IPv6  <br/> |
   
1. Die primäre Schnittstelle ist die Schnittstelle, die mit den Skype for Business Server-Komponenten kommuniziert.
  
### <a name="remote-user-peer-to-peer-communications"></a>Peer-zu-Peer-Kommunikation mit Remotebenutzern
<a name="remote"> </a>

Peer-zu-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.
  
|**Netzwerk des Remotebenutzers**|**Edgeserver (externer Edge)**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |Dualer Stapel  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>Konfiguration mit Front-End-Pool und Edgepool
<a name="FE_pool"> </a>

Die folgende Tabelle zeigt die Unterstützungsmatrix zwischen dem Front-End-Serverpool und dem internen Edgeserverpool.
  
**Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)**

||**Edgepool: IPv4** <br/> |**Edgepool: Dualer Stapel** <br/> |**Edgepool: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Front-End-Pool: IPv4** <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|**Front-End-Pool: Dualer Stapel** <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|**Front-End-Pool: IPv6** <br/> |Nein  <br/> |Nein  <br/> |Ja\*  <br/> |
   
\* Verwenden Sie diese Kombination nur in einer Laborumgebung.
  
Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.
  
**Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)**

||**Edgepool (externer Edge): IPv4** <br/> |**Edgepool (Externer Edge): Dualer Stapel** <br/> |**Edgepool (Externer Edge): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Edgepool (interner Edge): IPv4** <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|**Edgepool (interner Edge): Dualer Stapel** <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|**Edgepool (interner Edge): IPv6** <br/> |Nein  <br/> |Nein  <br/> |Ja\*  <br/> |
   
\* Verwenden Sie diese Kombination nur in einer Laborumgebung.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Erweiterte Unterstützung für Enterprise-VoIP für IPv6
<a name="Ent_V"> </a>

Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E9-1-1-Notrufdienste oder Medienumgehung beinhalten, müssen als Implementierung nur mit IPv4 oder als Dualer-Stapel-Implementierung konfiguriert werden. Endpunkte, die nur IPv6 verwenden, können keine dieser Features verwenden.
  
> [!NOTE]
> Auch wenn ein Skype for Business Server-Client mithilfe von IPv6 eine Verbindung mit einem Skype for Business Server herstellt, unternehmen Skype for Business Server in einer Bereitstellung mithilfe von IPv6 die besten Anstrengungen, um eine entsprechende IPv4-Adresse zur Unterstützung von E9-1-1 zuzuordnen. 
  
Der Standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.
  
Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Weitere Skype for Business Server-Featureunterstützung für IPv6
<a name="Ent_V"> </a>

Zusätzlich zu den oben erwähnten Features und Komponenten unterstützt Skype for Business Server IPv6 für die folgenden Features:
  
- **Beständiger Chat**
    
    Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators. Ausführliche Informationen zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation zum Bereitstellen des Servers für beständigen Chat.
    
- **QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen**
    
    In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.
    
## <a name="technical-requirements-for-ipv6"></a>Technische Anforderungen für IPv6
<a name="tech"> </a>

Wenn Sie beabsichtigen, Skype for Business Server für IPv6 zu konfigurieren, berücksichtigen Sie die folgenden Anforderungen:
  
- Um IPv6-Adressen mit Skype for Business Server zu verwenden, müssen Sie DNS-Einträge (Domain Name System) für Datensätze erstellen, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen. IPv6-DNS verwendet Host-AAAA-Einträge (Quad-A). Wenn Sie in Ihrer Bereitstellung sowohl IPv4 als auch IPv6 verwenden, empfiehlt es sich, sowohl Host-A-Einträge für IPv4 als auch Host-AAAA-Einträge für IPv6 zu konfigurieren und zu verwalten. Auch wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die weiterhin IPv4 verwenden.
    
    Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen. Wenn der Client oder Server IPv6 nicht verwendet, wird nicht auf den Datensatz verwiesen. Übergangstechnologien treffen basierend auf der Konfiguration und Richtlinien der Übergangstechnologie die Entscheidung darüber, welche Aufzeichnung verwendet werden soll.
    
- Jede IPv6-Adresse hat einen Bereich. Die drei Bereiche, die Sie für die IPv6-Adressierung verwenden können, sind globale IPv6-Adressen (ähnlich wie öffentliche IPv4-Adressen), IPv6 eindeutige lokale Adressen (ähnlich den privaten IPv4-Adressbereichen) und IPv6-Adressen mit lokaler Verknüpfung (ähnlich wie automatische private IP-Adressen in Windows Server für IPv4). Alle Server in einem Pool sollten IPv6-Adressen mit demselben Bereich aufweisen. 
    
> [!IMPORTANT]
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internetanbieter, um sicherzustellen, dass die Adressen, die Sie auf Windows Serverebene und auf Skype for Business Server Ebene zuweisen, wie erwartet funktionieren. Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie unter den Links am Ende dieses Themas. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Überlegungen zu Migration und Koexistenz für IPv6
<a name="migration"> </a>

IP-Version 6 (IPv6) wird auf Lync Server 2010 oder Office Communications Server nicht unterstützt. Zu Pilotzwecken können Sie Lync Server 2010 und Skype for Business Server Koexistenz mit dualen Stapeln testen. Es wird empfohlen, dass alle Pools für einen bestimmten zentralen Standort auf Skype for Business Server aktualisiert werden, bevor Sie IPv6 (Dual-Stack-Netzwerk) für einen der Pools aktivieren. Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Pool nur mit IPv6 in Ihrer Testumgebung zum Testen einrichten.
  
Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:
  
- Skype for Business Server-, Lync Server 2013- und Lync Server 2010-Pools im IPv4-Modus, koexistierend mit Skype for Business Server im Dualstapelmodus.
    
- Skype for Business Server Pool im IPv6-Modus, wenn der reine IPv6-Pool isoliert ist.
    
## <a name="see-also"></a>Siehe auch
<a name="migration"> </a>

[Konfigurieren von IP-Adresstypen in Skype for Business](ip-address-types.md)

[IP-Version 6– Adressierungsarchitektur](https://tools.ietf.org/html/rfc4291)
  
[Globales IPv6-Unicast-Adressformat](https://tools.ietf.org/html/rfc3587)
  
[Eindeutige lokale IPv6-Unicastadressen](https://tools.ietf.org/html/rfc4193)
