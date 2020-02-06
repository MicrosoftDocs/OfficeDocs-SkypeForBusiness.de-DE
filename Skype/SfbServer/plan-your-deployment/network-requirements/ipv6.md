---
title: Plan für IPv6 in Skype for Business
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
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 'Zusammenfassung: Implementieren Sie IPv6, bevor Sie Skype for Business Server installieren.'
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802075"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>Plan für IPv6 in Skype for Business
 
**Zusammenfassung:** Implementieren Sie IPv6, bevor Sie Skype for Business Server installieren.
  
Skype for Business Server bietet Unterstützung für IP Version 6 (IPv6)-Adressen sowie fortgesetzte Unterstützung von IP Version 4 (IPv4)-Adressen. 

Bei IPv4-Adressen handelt es sich um 32-Bit-Adressen, die einem Computer die Kommunikation über das Internet ermöglichen. Aufgrund der weltweit steigenden Anzahl von Geräten sind die verfügbaren IPv4-Adressen nicht mehr verfügbar. Aus diesem Grund werden viele neue Geräte in die Verwendung von IPv6-Adressen verschoben. IPv6-Adressen haben die gleiche Funktion wie IPv4-Adressen (und bieten einige zusätzliche Features), anstelle von lediglich 32 Bit werden von IPv6-Adressen jedoch 128 Bit verwendet. Dadurch steht nicht nur ein neuer Satz, sondern auch eine größere Anzahl an Adressen zur Verfügung. 

Eine typische IPv4-Adresse sieht ungefähr wie folgt aus: 192.0.2.235, wohingegen eine IPv6-Adresse wie folgt aussieht: 2001:0db8:85a3:0000:0000:8a2e: 0370:7334. Die Änderung der Formatierung und Funktionalität für Geräte, die IPv6-Adressen verwenden, erfordert in Ihrer Skype for Business Server-Installation verschiedene Überlegungen zur Bereitstellung und Konfiguration. 

Dieses Thema enthält die folgenden Abschnitte:
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
Wenn Sie feststellen, dass Sie IPv6-Adressen verwenden, lesen Sie den Artikel [Konfigurieren von IP-Adresstypen in Skype for Business](ip-address-types.md) .
  
## <a name="overview-of-ip-address-types"></a>Übersicht über IP-Adresstypen
<a name="over"> </a>

Sie haben drei Optionen, wenn Sie in Skype for Business Server IP-Adressen konfigurieren. Sie können Skype for Business Server so konfigurieren, dass nur IP Version 4 (IPv4), nur IP Version 6 (IPv6) oder eine Kombination aus beidem (als dualer Stack bezeichnet) unterstützt wird. Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:
  
- **Nur IPv4** IPv6 wurde erstellt, weil die IPv4-Adressen für die Welt nicht mehr funktionieren. IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen möglicherweise kommunizieren muss, unterstützen derzeit noch nicht IPv6 und möglicherweise bleibt das auch noch eine ganze Weile so. Eine nur-IPv4-Konfiguration hilft, sicherzustellen, dass Ihre Skype for Business Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.
    
- **Nur IPv6** Umgekehrt schließt eine vollständige IPv6-Implementierung die Kommunikation mit vielen vorhandenen Geräten aus.
    
- **Dual-Stack** Dual Stack ist ein Netzwerk, in dem sowohl IPv4-als auch IPv6-Adressen aktiviert sind. Diese Konfiguration wird in Skype for Business Server unterstützt, da in den meisten Fällen der Übergang von Full-IPv4 zu Full-IPv6 mehrere Jahre in Anspruch nehmen wird.
    
In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene Funktionen von Skype for Business Server erläutert.
  
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

Skype for Business Server unterstützt keine medienumgehung für PSTN-Anrufe (Public Switched Telephone Network), wenn der Datenverkehr über eine IPv6-Schnittstelle erfolgt. Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren. 
  
|**Primäre Schnittstelle 1**|**PSTN-Schnittstelle (auf dem Vermittlungsserver)**|**Einstellung für das PSTN-Gateway**|
|:-----|:-----|:-----|
|IPv4  <br/> |Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |IPv4  <br/> |
|Dualer Stapel  <br/> |Dualer Stapel  <br/> |IPv6  <br/> |
   
1. Die primäre Schnittstelle ist die Schnittstelle, die mit den Skype for Business Server-Komponenten kommuniziert.
  
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

Die folgende Tabelle zeigt die Support Matrix zwischen dem Front-End-Serverpool und dem internen Edge-Serverpool.
  
**Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)**

||**Edgepool: IPv4** <br/> |**Edgepool: Dualer Stapel** <br/> |**Edgepool: IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Front-End-Pool: IPv4** <br/> |Ja   <br/> |Ja  <br/> |Nein  <br/> |
|**Front-End-Pool: Dualer Stapel** <br/> |Ja   <br/> |Ja  <br/> |Nein  <br/> |
|**Front-End-Pool: IPv6** <br/> |Nein  <br/> |Nein  <br/> |Ja\*  <br/> |
   
\*Verwenden Sie diese Kombination nur in einer Lab-Umgebung.
  
Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.
  
**Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)**

||**Edgepool (Externer Edge): IPv4** <br/> |**Edgepool (Externer Edge): Dualer Stapel** <br/> |**Edgepool (Externer Edge): IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**Edgepool (Interner Edge): IPv4** <br/> |Ja  <br/> |Ja  <br/> |Nein  <br/> |
|**Edgepool (Interner Edge): Dualer Stapel** <br/> |Nein  <br/> |Ja  <br/> |Nein  <br/> |
|**Edgepool (Interner Edge): IPv6** <br/> |Nein  <br/> |Nein  <br/> |Ja\*  <br/> |
   
\*Verwenden Sie diese Kombination nur in einer Lab-Umgebung.
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>Erweiterte Unterstützung für Enterprise-VoIP für IPv6
<a name="Ent_V"> </a>

Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E911-Notrufdienste oder Medienumgehung beinhalten, können nur mit IPv4 oder als Implementierung mit dualem Stapel konfiguriert werden. Endpunkte, die nur IPv6 verwenden, haben diese Funktionen nicht.
  
> [!NOTE]
> In einer Dual-Stacked-Bereitstellung, auch wenn ein Skype for Business Server-Client eine Verbindung mit einem Skype for Business-Server mithilfe von IPv6 herstellt, ist Skype for Business Server bemüht, eine geeignete IPv4-Adresse zuzuordnen, um E9-1-1 zu unterstützen. 
  
Der standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.
  
Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden. 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>Andere Skype for Business Server-Feature-Unterstützung für IPv6
<a name="Ent_V"> </a>

Zusätzlich zu den zuvor erwähnten Features und Komponenten unterstützt Skype for Business Server IPv6 für die folgenden Features:
  
- **Beständiger Chat**
    
    Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators. Details zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation zum Bereitstellen des beständigen Chats.
    
- **QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen (KDS)**
    
    In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.
    
## <a name="technical-requirements-for-ipv6"></a>Technische Anforderungen für IPv6
<a name="tech"> </a>

Wenn Sie die Konfiguration von Skype for Business Server für IPv6 planen, sollten Sie die folgenden Voraussetzungen berücksichtigen:
  
- Wenn Sie IPv6-Adressen mit Skype for Business Server verwenden möchten, müssen Sie DNS-Einträge (Domain Name System) für Datensätze erstellen, die erkannt und in eine IPv6-Adresse aufgelöst werden müssen. IPv6-DNS verwendet Host-AAAA-Einträge (vier „A“). Falls Sie sowohl IPv4 als auch IPv6 in Ihrer Bereitstellung verwenden, empfiehlt es sich, sowohl Host-A-Einträge für IPv4 als auch Host-AAAA-Einträge für IPv6 zu konfigurieren und zu verwalten. Selbst wenn Sie Ihre Bereitstellung vollständig auf IPv6 umstellen, benötigen Sie möglicherweise weiterhin IPv4-DNS-Hosteinträge für externe Benutzer, die noch IPv4 verwenden.
    
    Sie können IPv6-DNS-Hosteinträge bereitstellen, bevor Sie mit der Verwendung von IPv6 beginnen. Falls der Client oder Server IPv6 nicht verwendet, wird nicht auf den Eintrag verwiesen. Umstellungstechnologien bestimmen anhand von Konfiguration und Richtlinien, welcher Eintrag verwendet werden soll.
    
- Jede IPv6-Adresse hat einen Adressbereich. Die drei Bereiche, die Sie für die IPv6-Adressierung verwenden können, sind IPv6-globale Adressen (ähnlich wie öffentliche IPv4-Adressen), eindeutige IPv6-lokale Adressen (ähnlich den privaten IPv4-Adressbereichen) und IPv6-Link-Local-Adressen (ähnlich wie automatische private IP-Adressen in Windows Server für IPv4). Alle Server innerhalb eines Pools sollten IPv6-Adressen mit dem gleichen Adressbereich aufweisen. 
    
> [!IMPORTANT]
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internet Anbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows-Serverebene und auf der Skype for Business-Serverebene zuweisen, wie erwartet funktionieren. Zusätzliche Informationen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas. 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>Überlegungen zu Migration und Koexistenz für IPv6
<a name="migration"> </a>

IP Version 6 (IPv6) wird in lync Server 2010 oder Office Communications Server nicht unterstützt. Für Pilot Zwecke können Sie die Koexistenz von lync Server 2010 und Skype for Business Server Dual-Stack testen. Wir empfehlen, dass alle Pools für einen bestimmten zentralen Standort auf Skype for Business Server aktualisiert werden, bevor Sie IPv6 (Dual-Stack-Netzwerk) für einen der Pools aktivieren. Wenn Sie einen Pool nur für IPv6 konfigurieren müssen, wird empfohlen, dass Sie einen Nur-IPv6-Pool in Ihrer Testumgebung zum Testen einrichten.
  
Die folgenden Szenarien werden bei der Migration und Koexistenz unterstützt:
  
- Skype for Business Server-, lync Server 2013-und lync Server 2010-Pools im IPv4-Modus, die mit Skype for Business Server im Dual-Stack-Modus vorhanden sind.
    
- Skype for Business-Server Pool im reinen IPv6-Modus, wenn der reine IPv6-Pool isoliert ist.
    
## <a name="see-also"></a>Siehe auch
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[IP Version 6-Adressierungs Architektur](https://tools.ietf.org/html/rfc4291)
  
[Globales IPv6-Unicast-Adress Format](https://tools.ietf.org/html/rfc3587)
  
[Eindeutige lokale IPv6-Unicast-Adressen](https://tools.ietf.org/html/rfc4193)
