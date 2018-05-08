---
title: Direkte SIP-Verbindungen in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Direkte SIP-Verbindungen werden zwischen Skype für Business Server und sowohl PSTN-Gateways und IP-PBX-Ressource in Enterprise-VoIP unterstützt.
ms.openlocfilehash: c9dca75a7b1c7ac8fa60bafc5b7a2c2fa7b51490
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="direct-sip-connections-in-skype-for-business-server-2015"></a>Direkte SIP-Verbindungen in Skype for Business Server 2015
 
Direkte SIP-Verbindungen werden zwischen Skype für Business Server und sowohl PSTN-Gateways und IP-PBX-Ressource in Enterprise-VoIP unterstützt.
  
Sie können direkte SIP-Verbindungen Verbindung Skype für Business Server mit einer der folgenden verwenden:
  
- IP-Nebenstellenanlage 
    
- PSTN-Gateway
    
Zur Implementierung einer direkten SIP-Verbindung führen Sie grundsätzlich dieselben Bereitstellungsschritte aus wie bei der Implementierung eines SIP-Trunks. In beiden Fällen implementieren Sie die Verbindung mithilfe der externen Schnittstelle eines Vermittlungsservers. Der einzige Unterschied besteht darin, dass Sie SIP-Trunks mit einer externen Entität (z. B. einem ITSP-Gateway) verbinden, während direkte SIP-Verbindungen eine Verbindung mit einer internen Entität im lokalen Netzwerk herstellen, z. B. einer IP-Nebenstellenanlage oder einem PSTN-Gateway (Public Switched Telephone Network).
  
## <a name="direct-sip-deployment-options"></a>Optionen für Bereitstellungen mit direkten SIP-Verbindungen

### <a name="skype-for-business-server-stand-alone"></a>Eigenständige Skype for Business Server-Bereitstellung
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Wenn Ihre Organisation eine der in diesem Abschnitt beschriebenen Bereitstellungen verwendet, können Sie als einzige telefonielösung für eine Organisation ganz oder teilweise Skype für Business Server verwenden. In diesem Abschnitt werden die folgenden Bereitstellungen ausführlich beschrieben:
  
- **Inkrementelle Bereitstellung:** Diese Option wird davon ausgegangen, dass Sie über eine vorhandene Infrastruktur mit private Branch Exchange, (Nebenstellenanlage PBX) verfügen, und Sie Enterprise Voice schrittweise für kleinere Gruppen oder Teams innerhalb Ihrer Organisation einführen möchten.
    
- **Nur VoIP-Bereitstellung:** dieser Option wird davon ausgegangen, dass Sie beabsichtigen, Bereitstellung von Enterprise-VoIP an einem Standort, die keine herkömmliche Telefonieinfrastruktur vorhanden ist.
    
#### <a name="incremental-deployment"></a>Inkrementelle Bereitstellung

Inkrementelle Bereitstellung Skype für Business Server ist die einzige telefonielösung für einzelne Teams oder Abteilungen, während die übrigen Benutzer in einer Organisation weiterhin eine Nebenstellenanlage verwenden. Diese inkrementelle Bereitstellungsstrategie bietet eine Möglichkeit, die IP-Telefonie anhand kontrollierter Pilotprogramme in Ihrem Unternehmen einzuführen. Arbeitsgruppen, deren Kommunikation sind die Anforderungen am besten von Microsoft Unified Communications bedient, werden in Enterprise-VoIP, verschoben, während andere Benutzer auf die vorhandene Nebenstellenanlage bleiben. Zusätzliche Arbeitsgruppen können bei Bedarf zu Enterprise-VoIP migriert werden.
  
Die inkrementelle Bereitstellung wird empfohlen, wenn Sie über eindeutig definierte Benutzergruppen verfügen, die gemeinsame Kommunikationsanforderungen aufweisen und für eine zentrale Verwaltung geeignet sind. Außerdem ist diese Option für Teams oder Abteilungen effektiv, die geografisch weit verteilt sind, sodass deutliche Einsparungen bei den Kosten für Ferngespräche erzielt werden können. Diese Option ist hilfreich für die Bildung virtueller Teams, deren Mitglieder möglicherweise weltweit verteilt sind. Sie können solche Teams gemäß wechselnden Unternehmensanforderungen schnell zusammenstellen, ändern oder auflösen.
  
Die folgende Abbildung zeigt die allgemeine Topologie für die Bereitstellung von Enterprise-VoIP hinter einer Nebenstellenanlage. Diese Topologie wird für die inkrementelle Bereitstellung empfohlen.
  
**Inkrementelle Bereitstellung**

![Abteilungsbezogene Migrationsoption (Diagramm)](../../media/Fig28_Departmental_migration_option.jpg)
  
> [!NOTE]
> Wenn Sie Ihre Skype für Business Server-Bereitstellung mit einem zertifizierten direkte SIP-Partner herstellen, ist ein Gateway public switched Telephone Network, (PSTN) zwischen dem Vermittlungsserver und der Nebenstellenanlage nicht erforderlich. Eine Liste mit zertifizierten direkte SIP-Partnern finden Sie auf der [Microsoft Unified Communications Open Interoperability Program](https://go.microsoft.com/fwlink/p/?linkId=203309). 
  
> [!NOTE]
> Für den in dieser Abbildung gezeigten Medienpfad wurde die Medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie sich entscheiden, um die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungsserver weitergeleitet. 
  
In dieser Topologie werden ausgewählte Abteilungen oder Arbeitsgruppen für Enterprise Voice aktiviert. Die VoIP-Arbeitsgruppe wird über ein PSTN-Gateway mit der Nebenstellenanlage verbunden. Benutzer, die für Remotemitarbeiter, einschließlich Enterprise-VoIP aktiviert sind die Kommunikation über das IP-Netzwerk. Anrufe von Enterprise-VoIP-Benutzern mit dem PSTN und Kollegen, die nicht für Enterprise Voice aktiviert sind, werden über das entsprechende PSTN-Gateway weitergeleitet. Anrufe von Kollegen, die sich immer noch das PBX-System befinden oder von Anrufern auf das Telefonfestnetz werden an das PSTN-Gateway weitergeleitet, die die Aufrufe von Skype für das routing für Business Server weiterleitet.
  
Es gibt zwei Empfohlene Konfigurationen für die Verbindung von Enterprise-VoIP mit einer vorhandenen PBX-Infrastruktur für die Interoperabilität: Enterprise-VoIP hinter der Nebenstellenanlage und Enterprise-VoIP vor der Nebenstellenanlage.
  
#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise-VoIP hinter der Nebenstellenanlage

Bei der Bereitstellung von Enterprise-VoIP hinter der Nebenstellenanlage erreichen der Nebenstellenanlage, die Anrufe bei Benutzern von Enterprise-VoIP-Routen für ein PSTN-Gateway und PBX-Benutzern mit der Nebenstellenanlage Ruft alle Anrufe über das PSTN. 
  
#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise-VoIP vor der Nebenstellenanlage

Das PSTN-Gateway leitet Anrufe für Enterprise-VoIP-Benutzern, Skype Business Server auch für Anrufe für PBX-Benutzer mit der Nebenstellenanlage Problembehandlungsprozesse alle Anrufe, bei der Bereitstellung von Enterprise-VoIP vor der Nebenstellenanlage. Anrufe an das Telefonfestnetz von Benutzern für Enterprise-VoIP und einer Nebenstellenanlage werden über das IP-Netzwerk an das kosteneffizienteste PSTN-Gateway weitergeleitet. In der folgenden Tabelle werden die Vor- und Nachteile dieser Konfiguration dargestellt.
  
**Vor- und Nachteile der Bereitstellung von Enterprise-VoIP vor einer Nebenstellenanlage**

|**Vorteile**|**Nachteile**|
|:-----|:-----|
|Die Nebenstellenanlage bedient weiterhin die Benutzer für Enterprise-VoIP nicht aktiviert.  <br/> |Die vorhandenen Gateways unterstützen möglicherweise die gewünschten Funktionen oder Kapazitäten nicht.  <br/> |
|Die Nebenstellenanlage steuert alle älteren Geräte.  <br/> |Erfordert einen Trunk aus Gateway zur Nebenstellenanlage und dem Gateway an den Vermittlungsserver. Möglicherweise benötigen Sie weitere Trunks vom Dienstanbieter.  <br/> |
|Enterprise-VoIP-Benutzer behalten Ihre Rufnummern.  <br/> | <br/> |
   
#### <a name="voip-only-deployment"></a>Reine VoIP-Bereitstellung

Enterprise-VoIP bietet neue Unternehmen sowie neue Websites in Office für vorhandene Unternehmen die Möglichkeit, eine voll funktionsfähige VoIP-Lösung implementieren, ohne Gedanken PBX-Integration müssen oder dass die umfangreiche Bereitstellung und Wartung Kosten für eine IP-PBX-Infrastruktur. Diese Lösung unterstützt sowohl Mitarbeiter am Standort als auch Remotemitarbeiter.
  
In dieser Bereitstellung werden die Anrufe über das IP-Netzwerk weitergeleitet. Anrufe an das Festnetz werden an das entsprechende PSTN-Gateway weitergeleitet. Skype für Geschäftskunden und Lync Phone Edition dienen als Softphone. Die Remoteanrufsteuerung ist nicht verfügbar und nicht erforderlich, da keine Nebenstellentelefone für Benutzer gesteuert werden müssen. Voicemail und automatische Telefonzentrale sind optional über von Exchange Unified Messaging (UM) verfügbar.
  
> [!NOTE]
> Zusätzlich zur Netzwerkinfrastruktur, die zur Unterstützung von Skype für Business Server erforderlich ist, können eine nur-VoIP-Bereitstellung ein kleines, qualifiziertes Gateway zur Unterstützung von Fax- und analogen Geräten. 
  
In der folgenden Abbildung wird eine typische Topologie für eine reine VoIP-Bereitstellung dargestellt.
  
**Ausschließliche VoIP-Bereitstellung**

![Greenfidle-Bereitstellungsoption](../../media/Fig29_Greenfield_deployment_option.jpg)
  
> [!NOTE]
> Für den in dieser Abbildung gezeigten Medienpfad wurde die Medienumgehung aktiviert (empfohlene Konfiguration). Wenn Sie sich entscheiden, um die medienumgehung zu deaktivieren, wird der Medienpfad über den Vermittlungsserver weitergeleitet. 
  
## <a name="pstn-gateway-deployment-options"></a>Bereitstellungsoptionen für PSTN-Gateways

### <a name="pstn-gateways"></a>PSTN-Gateways

Gateways Public switched Telephone Network (Telefonfestnetz PSTN) werden von Drittanbietern Hardwarekomponenten, die Signale und Medien zwischen der Enterprise-VoIP-Infrastruktur und dem Telefonfestnetz weder direkt noch über Verbindung mit SIP-Trunks übersetzen. In beiden Topologien stellt das Gateway den Endpunkt für das Telefonfestnetz dar. Das Gateway wird in einem eigenen Subnetz isoliert und mit dem Unternehmensnetzwerk über den Vermittlungsserver verbunden ist.
  
In einem Unternehmen mit mehreren Standorten wird üblicherweise mindestens ein Gateway pro Standort bereitgestellt. Zweigniederlassungen können an das Telefonfestnetz über ein Gateway oder über eine Survivable Branch Appliance, die mit dem Gateway und Server in einem Feld kombiniert verbinden. Wenn Zweigniederlassungen ein Gateway verwendet werden, sind eine Registrierung und den Vermittlungsserver klicken Sie auf Website erforderlich, es sei denn, die WAN-Verbindung ausfallsicher ist. Mindestens einen Vermittlungsserver, die Front-End-Server verbunden sind, können Anrufe für die eine oder mehrere Gateways an jedem Standort weitergeleitet. Es wird empfohlen, dass die Registrierung, Vermittlungsserver und -Gateway erforderlich auf Website als eine Survivable Branch Appliance bereitgestellt werden.
  
Bestimmen der Anzahl, Größe und Position des PSTN-Gateways ist möglicherweise die wichtigste und teuerste Entscheidung, die Sie bei der Planung Ihrer Enterprise-VoIP-Infrastruktur treffen müssen. 
  
Sie müssen folgende wichtige Fragen bedenken. Keine dieser Fragen kann unabhängig von den anderen beantwortet werden.
  
- Wie viele PSTN-Gateways sind erforderlich? Die Antwort richtet sich nach der Anzahl von Benutzern, der erwarteten Anzahl gleichzeitiger Anrufe (Datenverkehr) und der Anzahl von Standorten (jeder Standort benötigt ein Gateway).
    
- Wie groß sollen die Gateways sein? Die Antwort richtet sich nach der Anzahl von Benutzern am Standort und dem zu erwartenden Datenverkehr.
    
- Wo sollen sich die Gateways befinden? Die Antwort richtet sich zum Teil nach der Topologie und zum Teil nach der geografischen Verteilung Ihrer Organisation.
    
 Sie sollten auch die Optionen für die Gatewaytopologie berücksichtigen (weitere Informationen hierzu finden Sie im Abschnitt „Gatewaytopologien“ weiter unten in diesem Thema).
  
#### <a name="mn-trunk-support"></a>M:N-Trunkunterstützung

Der Vermittlungsserver können Anrufe über mehrere Gateways, Session Border Controller (SBCs) von bereitgestellten Internet Telefoniedienstanbieter, oder eine Kombination aus beidem weiterleiten. Darüber hinaus können mehrere Vermittlungsserver im Pool mit mehreren Gateways interagieren. Die logische Route zwischen einem Vermittlungsserver und einem Gateway definiert wird einen Trunk aufgerufen. Wenn ein interner Benutzer einen PSTN-Anruf tätigt, wählt ausgehende Routinglogik auf den Front-End-Pool welche Trunk über alle möglichen Kombinationen weitergeleitet, die für das routing von bestimmten Aufruf verfügbar sein können. Mit der DNS-Lastenausgleich, wenn ein Aufruf fehlschlägt, ein Gateway aufgrund eines Problems mit einem bestimmten Vermittlungsserver im Pool erreicht wird der Anruf an einen anderen Mediation Server im Pool wiederholt. 
  
Ausführliche Informationen zur Planung für mehrere Gateways finden Sie unter [m: n-Trunk in Skype für Business Server 2015](m-n-trunk.md).
  
Ausführliche Informationen zu anderen Verbesserungen beim Ausgangsrouting finden Sie unter [Call Routes](http://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).
  
#### <a name="gateway-topologies"></a>Gatewaytopologien

Halten Sie sich bei Ihren Überlegungen zu den grundlegenden Fragen zur Gatewaybereitstellung an die folgenden Schritte:
  
1. Zählen Sie die Standorte, an denen Sie PSTN-Konnektivität mit Enterprise-VoIP bereitstellen möchten.
    
2. Schätzen Sie den zu erwartenden Datenverkehr für jeden Standort (Anzahl der Benutzer und durchschnittliche Anzahl der Anrufe pro Stunde und Benutzer).
    
3. Stellen Sie mindestens ein Gateway an jedem Standort bereit, um den zu erwartenden Datenverkehr zu verarbeiten.
    
In dieser Topologie werden alle Anrufe zwischen Mitarbeitern an den einzelnen Standorten sowie zwischen den Standorten über Ihr Intranet weitergeleitet. Anrufe in das Telefonfestnetz werden über das IP-Unternehmensnetzwerk an die Gateways weitergeleitet, die dem Standort der Zielrufnummern am nächsten sind. Wie sollte die Bereitstellung jedoch aussehen, wenn Ihre Organisation Dutzende, Hunderte oder sogar Tausende von Standorten unterstützt, die über mehrere Kontinente verteilt sind – was beispielsweise bei vielen Finanzinstituten und anderen großen Unternehmen der Fall ist? In solchen Fällen ist es nicht empfehlenswert, an jedem Standort ein separates Gateway bereitzustellen.
  
Um dieses Problem zu beheben, lieber viele große Unternehmen ein oder mehrere große Telefonie zentralen Standorten bereitstellen.
  
In dieser Topologie werden mehrere große Gateways für die vorherzusehende benutzerauslastung ausreichend an jedem zentralen Standort bereitgestellt. Alle Anrufe an Benutzer im Unternehmen werden durch den Telefondienstanbieter der Firma an einen zentralen Standort weitergeleitet. Routinglogik am zentralen Standort bestimmt, ob der Anruf über das Intranet oder an das PSTN weitergeleitet werden sollen.
  
#### <a name="gateway-location"></a>Gatewaystandort

Auch der Gatewaystandort bestimmt möglicherweise, welche Typen von Gateways Sie auswählen und wie Sie diese konfigurieren können. Es gibt Dutzende von PSTN-Protokollen, von denen jedoch keines weltweiter Standard ist. Wenn sich alle Ihre Gateways in einem einzigen Land bzw. einer einzigen Region befinden, stellt dies kein Problem dar. Wenn Sie jedoch Gateways in mehreren Ländern/Regionen platzieren, muss jedes Gateway gemäß den dort verwendeten PSTN-Standards konfiguriert werden. Außerdem sind Gateways, die beispielsweise für den Betrieb in Kanada zertifiziert sind, in Indien, Brasilien oder der Europäischen Union möglicherweise nicht zertifiziert.
  
#### <a name="gateway-size-and-number"></a>Größe und Anzahl von Gateways

Die Größe der PSTN-Gateways, deren Bereitstellung für die meisten Organisationen in Betracht kommt, liegt im Bereich von 2 bis 960 Ports. (Es gibt sogar größere Gateways, aber diese werden hauptsächlich von telefonanbietern verwendet.) Wenn Sie die Anzahl von Ports schätzen, den Ihre Organisation erforderlich sind, verwenden Sie die folgenden Richtlinien:
  
- Wenn in Ihrer Organisation wenig telefoniert wird (ein PSTN-Anruf pro Benutzer und Stunde), sollten Sie einen Port für jeweils 15 Benutzer zuordnen. Wenn beispielsweise 20 Benutzer vorhanden sind, benötigen Sie ein Gateway mit zwei Ports.
    
- Wenn in Ihrer Organisation mäßig viel telefoniert wird (zwei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 10 Benutzer zuordnen. Wenn beispielsweise 100 Benutzer vorhanden sind, benötigen Sie insgesamt 10 Ports, die Sie auf einem oder auf mehreren Gateways zuordnen können.
    
- Wenn in Ihrer Organisation viel telefoniert wird (mindestens drei PSTN-Anrufe pro Benutzer und Stunde), sollten Sie einen Port für jeweils 5 Benutzer zuordnen. Wenn beispielsweise 47.000 Benutzer vorhanden sind, benötigen Sie insgesamt 9.400 Ports, die Sie auf mindestens 10 großen Gateways zuordnen sollten.
    
- Zusätzliche Ports können erworben werden, wenn die Benutzeranzahl oder der Umfang des Datenverkehrs in Ihrer Organisation steigt.
    
Für jede zu unterstützende Benutzeranzahl können Sie entweder wenige größere Gateways oder mehrere kleine bereitstellen. Prinzipiell werden für jede Organisation mindestens zwei Gateways empfohlen, um die Verfügbarkeit sicherzustellen, falls ein Gateway ausfällt. 
  
Jeder PSTN-Gateway, die Sie bereitstellen, benötigen Sie mindestens einen zugehörigen Vermittlungsserver.
  

