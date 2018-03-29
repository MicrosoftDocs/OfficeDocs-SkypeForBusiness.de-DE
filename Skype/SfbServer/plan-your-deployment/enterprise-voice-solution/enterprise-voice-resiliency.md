---
title: Planen der Ausfallsicherheit für Enterprise-VoIP in Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Erfahren Sie, wie VoIP-ausfallsicherheit für Business Server Enterprise-VoIP an zentralen Standorten und Zweigniederlassungen in Skype zu unterstützen. Branch-Site-Optionen umfassen Survivable Branch Appliances oder Survivable Branch Servern bereitstellen.
ms.openlocfilehash: a4ce7e01ef93ef7bfca2357b65b315b4be5c6781
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server-2015"></a>Planen der Ausfallsicherheit für Enterprise-VoIP in Skype for Business Server 2015
 
Erfahren Sie, wie VoIP-ausfallsicherheit für Business Server Enterprise-VoIP an zentralen Standorten und Zweigniederlassungen in Skype zu unterstützen. Branch-Site-Optionen umfassen Survivable Branch Appliances oder Survivable Branch Servern bereitstellen.
  
VoIP-ausfallsicherheit bezieht sich auf die Fähigkeit von Benutzern, machen und Empfangen von Anrufen bleiben, wenn ein zentraler Standort, dass Hosts Skype für Business Server, ob Sie über ein WAN verfügbar ist, kann (WAN) Fehler oder eine weitere Ursache Netzwerk. Wenn ein zentraler Standort ein Fehler auftritt, muss Enterprise-VoIP-Dienst ohne Unterbrechung durch nahtlose Failover auf einen weiterhin. Bei einem WAN-Ausfall müssen mit einem lokalen PSTN-Gateway Branch Site Anrufe umgeleitet werden. In diesem Abschnitt wird erläutert, Planen von VoIP-ausfallsicherheit Central-Site oder WAN-Ausfall.
  
## <a name="central-site-resiliency"></a>Ausfallsicherheit des zentralen Standorts

Unternehmen verfügen zunehmend über mehrere Standorte, die auf der ganzen Welt verteilt sind. Verwalten von Notdienste, ist der Zugriff auf Helpdesk und die Möglichkeit, wichtige geschäftliche Aufgaben durchführen, bei ein zentraler Standort ausfällt entscheidend für alle Enterprise-VoIP-ausfallsicherheitslösung. Bei ein zentraler Standort nicht mehr verfügbar ist, müssen die folgenden Bedingungen erfüllt sein:
  
- VoIP-Failover muss bereitgestellt werden.
    
- Benutzer, die normalerweise mit dem Front-End-Pool am zentralen Standort registrieren müssen eine Alternative Front-End-Pool registrieren können. Dies kann erfolgen, indem Sie Erstellen mehrerer DNS-SRV-Einträge, von denen jedes einem Director-Pool oder Front-End-Pool in den einzelnen Ihrer zentralen Standorte aufgelöst wird. Sie können die Priorität und Weights SRV-Einträge anpassen, damit die Benutzer, die von diesem zentralen Standort bereitgestellt werden den entsprechenden Director- und Front-End-Pool vor denen in anderen SRV-Einträge erhalten.
    
- Anrufe von Benutzern an anderen Standorten müssen an das Telefonfestnetz umgeleitet werden.
    
In diesem Thema wird die empfohlene Lösung zum Sichern von VoIP-ausfallsicherheit des zentralen Standorts.
  
### <a name="architecture-and-topology"></a>Architektur und Topologie

Planen von VoIP-ausfallsicherheit an einem zentralen Standort erfordert grundlegend die zentrale Rolle der Skype Business Server Registrierungsstelle VoIP-Failover zu ermöglichen. Die Skype Business Server Registrierungsstelle ist ein Dienst, der Clientregistrierung und Authentifizierung aktiviert und Routingdienste bereitstellt. Es wird auf Standard Edition-Server, Front-End-Server, Director oder Survivable Branch Appliance ausgeführt. Ein registrierungspool besteht aus der Registrierung Dienste auf den Front-End-Pool ausführen und sich am selben Standort befinden. Eine Skype für Business Client ermittelt den Front-End-Pool durch den folgenden Discovery-Mechanismus: 
  
1. DNS-SRV-Eintrag
    
2. AutoErmittlung-Webdienst 
    
3. DHCP-Option 120
    
Nachdem die Skype für Business-Client mit dem Front-End-Pool verbunden ist, wird es durch das System zum Lastenausgleich zu einem der Front-End-Servern im Pool weitergeleitet. Diesem Front-End-Server leitet wiederum den Client zum eine bevorzugte Registrierungsstelle im Pool.
  
Jeder Benutzer für Enterprise Voice aktiviert wird die primären registrierungspool des Benutzers wird einer bestimmten registrierungspool zugewiesen. An einem bestimmten Standort freigeben Hunderte oder Tausende von Benutzern in der Regel einen einzelnen primären registrierungspool. Um die Auslastung der zentralen Standort Ressourcen nach jeder Zweigstellenbenutzer berücksichtigen, die den zentralen Standort für Anwesenheitsinformationen, Konferenzen oder Failover verwenden, wird empfohlen, dass Sie jeden Branch Sitebenutzer in Betracht ziehen, als wäre der Benutzer ein Benutzer mit einem zentralen Standort registriert. Es gibt zurzeit keine Grenzwerte für die Anzahl der Benutzer des zweigstellenstandorts, einschließlich der Benutzer mit einer Survivable Branch Appliance registriert.
  
Um bei einem Ausfall des zentralen Standorts VoIP-ausfallsicherheit zu gewährleisten, muss der primäre registrierungspool einer einzelnen festgelegten sicherungsregistrierungspool an einem anderen Standort verfügen. Die Sicherung kann mithilfe des Topologie-Generator Resiliency Einstellungen konfiguriert werden. Sofern eine ausfallsichere WAN-Verbindung zwischen den beiden Standorten, werden Benutzer, deren primäre registrierungspool nicht mehr verfügbar ist, automatisch an die Sicherungsregistrierungsstellen-Pool weitergeleitet.
  
Die folgenden Schritte beschreiben den Client Discovery und Registrierung Prozess:
  
1. Ein Client ermittelt Skype für Business Server über DNS-SRV-Einträge. In Skype für Business Server können DNS-SRV-Einträge konfiguriert werden, um mehr als einen FQDN der DNS-SRV-Abfrage zurückgegeben. Wenn Enterprise Contoso drei zentralen Standorten (Nordamerika, Europa und Asien-Pazifik) und einen directorpool auf jeder zentrale Standort hat, können DNS-SRV-Einträge auf den Director-Pool FQDNs in jeder der drei Speicherorte verweisen. Als Director-Pools in einem der Speicherorte verfügbar ist, kann der Client zum ersten Hop Skype für Business Server verbinden.
    
    > [!NOTE]
    > Verwenden einen Director-Pool ist optional. Ein Front-End-Pool kann stattdessen verwendet werden. 
  
2. Der Director-Pool informiert den Skype für Business-Client über primären registrierungspool des Benutzers und Sicherungsregistrierungsstellen-Pool.
    
3. Die Skype für Business-Client versucht für die Verbindung des Benutzers primären registrierungspool zuerst. Wenn der primäre registrierungspool verfügbar ist, akzeptiert die Registrierung die Registrierung. Wenn der primäre registrierungspool nicht verfügbar ist, versucht der Skype für Business-Client zur sicherungsregistrierungspool Verbindung. Wenn sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass die primären registrierungspool des Benutzers nicht verfügbar ist (durch Erkennen fehlender Heartbeat für eine angegebene Failover-Intervall) akzeptiert der sicherungsregistrierungspool Registrierung des Benutzers. Nachdem Sicherungsregistrierung erkennt, dass die primäre Registrierungsstelle wieder verfügbar ist, wird sicherungsregistrierungspool Failover-Clients auf ihren primären Pool umleiten.
    
### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Die folgenden Anforderungen und Empfehlungen für die Implementierung von VoIP-ausfallsicherheit des zentralen Standorts sind für die meisten Organisationen geeignet:
  
- Die Websites, in denen die primäre und der sicherungsregistrierungspool befinden, sollte über eine ausfallsichere WAN-Leitung verbunden sein.
    
- Jeder zentrale Standort muss über einen registrierungspool bestehend aus mindestens Registrierungsstellen enthalten.
    
- Für jeden registrierungspool muss mit Lastenausgleich mithilfe von DNS-Lastenausgleich, Hardwaregeräte zum Lastenausgleich oder beides sein. Ausführliche Informationen zur Planung der Konfigurations zum Netzwerklastenausgleich finden Sie unter [Lastenausgleich Anforderungen für Skype für Unternehmen zu laden](../../plan-your-deployment/network-requirements/load-balancing.md).
    
- Jeder Benutzer muss unter Verwendung von entweder die Skype für Business Server-Verwaltungsshell-Cmdlet " **Set-CsUser** " oder der Skype Business Server-Systemsteuerung einem primären registrierungspool zugewiesen werden.
    
- Der primäre registrierungspool muss über einen einzelnen sicherungsregistrierungspool an einem anderen zentralen Standort verfügen. 
    
- Der primäre registrierungspool muss konfiguriert sein, um ein Failover auf den Registrierungsstellen-Sicherungspool. Standardmäßig ist die primäre Registrierungsstelle sicherungsregistrierungspool nach ein Intervall von 300 Sekunden Failover zu festgelegt. Sie können dieses Intervall ändern, mit der Skype für Business Server-Topologie-Generator.
    
- Konfigurieren einer failoverroute. Wenn Sie die Route konfigurieren, geben Sie ein Gateway, die sich an einem anderen Standort vom Gateway in der primären Route angegeben.
    
- Wenn am zentrale Standort, die Ihren primären Verwaltungsserver enthalten sind und die Website ist wahrscheinlich für einen längeren Zeitraum ausfallen, müssen Sie die Verwaltungstools am Standort backup neu installieren. andernfalls, Sie kann nicht zum Ändern einer Einstellung Management werden.
    
### <a name="dependencies"></a>Abhängigkeiten

Skype für Business Server hängt von den folgenden Infrastruktur- und Softwarekomponenten Komponenten VoIP-ausfallsicherheit zu gewährleisten:
  
|||
|:-----|:-----|
|**Komponente** <br/> |**Funktionale** <br/> |
|DNS  <br/> |Beheben von SRV-Einträge und A-Einträgen für Server-zu-Server und Server-Client-Konnektivität  <br/> |
|Exchange- und Exchange-Webdienste (EWS)  <br/> |Speicherung von Kontakten; Kalenderdaten  <br/> |
|Exchange Unified Messaging und Exchange-Webdienste  <br/> |Rufen Sie Protokolle, Voicemail, Voicemail  <br/> |
|DHCP-Optionen 120  <br/> |Wenn Sie DNS-SRV nicht verfügbar ist, versucht der Client DHCP-Option 120 verwenden, um die Registrierung zu ermitteln. Dies funktioniert muss ein DHCP-Server konfiguriert werden oder Skype für Business Server DHCP aktiviert sein.  <br/> |
   
### <a name="survivable-voice-features"></a>Survivable VoIP-Funktionen

Wenn die vorstehenden Anforderungen und Empfehlungen implementiert wurden, werden die folgenden VoIP-Funktionen vom sicherungsregistrierungspool bereitgestellt werden:
  
- Ausgehende PSTN-Anrufe
    
- Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter die Möglichkeit zum Failover auf einen unterstützt
    
- Enterprise-Anrufe zwischen Benutzern am selben Standort und zwischen zwei verschiedenen Standorten
    
- Grundlegende Anrufbehandlung, einschließlich halten, Wiederaufnahme und Übergabe
    
- Zwei Teilnehmern instant messaging und Freigabe, Audio- und Videoinhalten zwischen Benutzern am selben Standort
    
- Anrufweiterleitung, Gleichzeitiges Klingeln von Endgeräten, anrufdelegierung und teamanrufdienste, aber nur, wenn beide Teilnehmer für die anrufdelegierung oder alle Teammitglieder am selben Standort konfiguriert sind.
    
- Vorhandene Telefone und Clients weiterhin funktionsfähig.
    
- Aufzeichnung von Kommunikationsdatensätzen (KDS)
    
- Authentifizierung und Autorisierung
    
Abhängig von ihrer Konfiguration sind die folgenden VoIP-Funktionen können oder funktionieren nicht, wenn ein primärer zentraler Standort ausfällt:
  
- Voicemails zu hinterlassen und Abrufen 
    
    Verfügbarmachen von Exchange UM beim Ausfall des primären zentralen Standorts ist werden soll, müssen Sie einen der folgenden Schritte ausführen:
    
  - Ändern Sie die DNS-SRV-Einträge so, dass Exchange UM-Server am zentralen Standort auf Exchange um-Sicherungsserver an einem anderen Standort verweisen.
    
  - Konfigurieren des Benutzers Exchange UM-Wählplan Exchange UM-Server am zentralen Standort und die Sicherungswebsite enthalten, jedoch festlegen, die Exchange um-Sicherungsserver deaktiviert. Wenn der primäre Standort ausfällt, muss der Exchange-Administrator die Exchange UM-Server am Standort backup markieren als aktiviert.
    
    Wenn keines der oben genannten Lösungen möglich ist, klicken Sie dann stehen Exchange UM nicht zur Verfügung Ausfall des zentralen Standorts nicht verfügbar.
    
- Alle konferenztypen
    
    Ein Failover, auf einen ausgeführt wurde Benutzer kann nicht an einer Konferenz teilnehmen, die erstellt oder von Organisator, deren Pool verfügbar ist, gehostet wird, aber erstellen oder hosten eine Konferenz auf ein eigenes primären Pool, der nicht mehr verfügbar ist. In ähnlicher Weise andere Benutzer können nicht zur Konferenzteilnahme, die im primären Pool des betroffenen Benutzers gehostet werden.
    
Die folgenden VoIP-Features funktionieren nicht, wenn ein primärer zentraler Standort ausfällt:
  
- Automatische Konferenzzentrale
    
- Anwesenheits- und DND-basiertes routing
    
- Aktualisieren der Einstellungen für die anrufweiterleitung
    
- Reaktionsgruppendienst und Parken von Anrufen
    
- Bereitstellen neuer Telefone und clients
    
- Adressbuchwebsuche
    
## <a name="branch-site-resiliency"></a>Zweigstellenstandorte

Wenn Sie Zweigstellenstandorte bereitstellen möchten, müssen d. h., hohe Verfügbarkeit Enterprise Voice-Dienst Sie drei Optionen für die auf diese Weise:
  
- Survivable Branch Appliance
    
- Survivable Branch Server
    
- Eine vollständige Skype für Business Server-Bereitstellung am Zweigstellenstandort 
    
In diesem Handbuch helfen Ihnen beim Bewerten, welche ausfallsicherheitslösung am besten für Ihre Organisation und, basierend auf Ihrer ausfallsicherheitslösung, welche PSTN-Anbindung Lösung verwendet wird. Sie helfen Ihnen beim Vorbereiten der Bereitstellung der Lösung, die Sie auswählen, dass Voraussetzungen und anderen planungsüberlegungen beschrieben.
  
### <a name="branch-site-resiliency-features"></a>Branch Site Resiliency features

Wenn Sie Zweigstellenstandorte, bereitstellen, wenn einer Zweigniederlassung WAN-Verbindung mit einem zentralen Standort ausfällt oder des zentralen Standorts nicht erreichbar ist, sollten die folgenden VoIP-Funktionen weiterhin verfügbar sein:
  
- Eingehende und ausgehende public switched Telephone Network (PSTN) anrufen
    
- Enterprise-Anrufe zwischen Benutzern am selben Standort und zwischen zwei verschiedenen Standorten
    
- Grundlegende Anrufbehandlung, einschließlich halten, Wiederaufnahme und Übergabe
    
- Zwei Teilnehmern instant messaging
    
- Anrufweiterleitung, Gleichzeitiges Klingeln von Endgeräten, anrufdelegierung und teamanrufdienste, aber nur, wenn Stellvertreters und Delegat (beispielsweise ein Manager und den Manager Administrator) oder alle Teammitglieder am selben Standort konfiguriert sind
    
- Kommunikationsdatensätze (KDS)
    
- PSTN-einwahlkonferenzen mit automatischer Konferenzzentrale
    
- VoIP-e-Mail-Funktionen, wenn Sie voicemailumleitungseinstellungen konfigurieren.
    
- Benutzerauthentifizierung und-Autorisierung
    
Die folgenden Features wird nur bei Ihrer ausfallsicherheitslösung um eine umfassende Skype für Business Server-Bereitstellung am Zweigstellenstandort handelt:
  
- IM-, Web- und A / V-Konferenzen
    
- Anwesenheits- und DND nicht stören-basiertes routing (wobei Anrufe verhindert Klingeln von Erweiterungen, die klingen)
    
- Aktualisieren der Einstellungen für die anrufweiterleitung
    
- Reaktionsgruppenanwendung und anrufparkanwendung
    
- Bereitstellung neuer Telefone und Clients, jedoch nur, wenn Active Directory Domain Services vorhanden ist am Zweigstellenstandort.
    
- Erweiterte E9-1-1 (E9-1-1)
    
    E9-1-1 bereitgestellt wird, und der SIP-Trunk am zentralen Standort ist nicht verfügbar, da die WAN-Verbindung vorhanden ist, leitet der Survivable Branch Appliance E9-1-1-Anrufen an das Gateway Zweigstelle. Um dieses Feature aktivieren, sollten VoIP-Richtlinien den Zweigstellenstandort Benutzer Anrufen an das lokale Gateway bei einem WAN-Ausfall leiten.
    
> [!NOTE]
> SBA (survivable Branch Office) ist für XMPP nicht unterstützt. Benutzer, die in einer SBA verwaltet Konfigurationen zum Senden von Sofortnachrichten oder finden Sie unter Anwesenheit mit XMPP-Kontakten nicht möglich. 
  
### <a name="branch-site-resiliency-solutions"></a>Branch Site Resiliency solutions

Es gibt offensichtliche Vorteile auf Zweigstellenstandorte in Ihrer Organisation bereitstellen. Insbesondere wenn Sie die Verbindung zum zentralen Standort verlieren, weiterhin Zweigstellenbenutzer Enterprise-VoIP-Dienst und Voice Mail haben (Wenn Sie den voicemailumleitungseinstellungen konfigurieren). Jedoch kann für Websites mit weniger als 25 Benutzer, eine ausfallsicherheitslösung nicht ausreichend wieder Rendite angeben. 
  
Wenn Sie Zweigstellenstandorte bereitstellen möchten, müssen Sie drei Optionen zur Verfügung. In der folgenden Tabelle können Sie bestimmen, die beste Option für Ihre Organisation helfen.
  
|**Wenn Sie...**|**Wir empfehlen die Verwendung einer...**|
|:-----|:-----|
|Host mit 25 bis 1.000 Benutzern am Zweigstellenstandort und Rendite eine vollständige Bereitstellung nicht unterstützt, oder wenn lokale administrative Unterstützung ist nicht verfügbar  <br/> |Survivable Branch Appliance  <br/> Der Survivable Branch Appliance ist ein Branchenstandard Blade-Server mit einer Skype Business Server Registrierungsstelle und Vermittlungsserver, die auf Windows Server 2008 R2 ausgeführt. Der Survivable Branch Appliance enthält auch ein Gateway public switched Telephone Network, (PSTN). Qualifizierte Drittanbieter-Geräte (Entwicklung von Microsoft-Partnern in der Survivable Branch Appliance (SBA) Qualifikation/Zertifizierungsprogramm) bieten eine dauerhafte PSTN-Verbindung bei einem WAN-Ausfall, jedoch dieser Ansatz bietet keine ausfallsichere Anwesenheit und Konferenzen, da diese Features von Front-End-Server am zentralen Standort abhängen.  <br/> Ausführliche Informationen zu Survivable Branch Appliances finden Sie unter "Survivable Branch Appliance Details" weiter unten in diesem Thema.  <br/> **Hinweis:** Wenn Sie beschließen, auch einen SIP-Trunk mit Ihrer Survivable Branch Appliance, wenden Sie sich an den Hersteller Ihres Survivable Branch Appliance, um Informationen zu den Dienstanbieter für Ihre Organisation am besten geeignet ist. <br/> |
|Host mit 1.000 bis 2.000 Benutzern am Zweigstellenstandort, keine ausfallsichere WAN-Verbindung und geschulte Skype für Business Server-Administratoren sind verfügbar  <br/> |Survivable Branch Server oder zwei Survivable Branch Appliances.  <br/> Die Survivable Branch Server ist ein Windows Server meeting angegebenen Hardware-, der Skype für Business Server Registrierung und Vermittlungsserver-Software installiert wurde. Sie müssen mit einem PSTN-Gateway oder einen SIP-Trunk mit einem Telefon-Dienstanbieter verbinden.  <br/> Ausführliche Informationen zu Survivable Branch Servern finden Sie unter "Survivable Branch Server Details" weiter unten in diesem Thema.  <br/> |
|Wenn Sie Features Anwesenheit und Konferenzen in benötigen zusätzlich zu VoIP-Funktionen für bis zu 5.000 Benutzer, und geschulte Skype für Business Server-Administratoren sind verfügbar  <br/> |Bereitstellen Sie als zentraler Standort mit einem Standard Edition-Server und nicht als einem Zweigstellenstandort.  <br/> Eine umfassende Skype für Business Server-Bereitstellung bietet eine dauerhafte PSTN-Verbindung und ausfallsichere Anwesenheits- und Konferenzfunktionen bei einem WAN-Ausfall.  <br/> |
   
#### <a name="resiliency-topologies"></a>Resiliency Topologien

Die folgende Abbildung zeigt die empfohlenen Topologien für Zweigstellenstandorte.
  
**Optionen für die Website**

![VoIP-Zweig: Ausfallsicherheitsoptionen](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)
  
#### <a name="survivable-branch-appliance-details"></a>Survivable Branch Appliance-Details

Die Skype für Business Server Survivable Branch Appliance umfasst die folgenden Komponenten:
  
- Einen Registrierungsserver für Benutzerauthentifizierung, Registrierung und Anrufrouting
    
- Einen Vermittlungsserver für die signalverarbeitung zwischen der Registrierung und einem PSTN-gateway
    
- Ein PSTN-Gateway für die Weiterleitung von Anrufen an das Telefonfestnetz als fallback bei WAN-Ausfällen
    
- SQL Server Express zur Speicherung lokaler Benutzerdaten
    
Der Survivable Branch Appliance umfasst außerdem PSTN-Trunks, analoge Ports und einen Ethernet-Adapter. 
  
Wenn die Zweigniederlassung WAN-Verbindung mit einem zentralen Standort nicht mehr verfügbar ist, fahren Sie interne Zweigstellenbenutzer mit Survivable Branch Appliance-Registrierung registriert werden, und erhalten einen VoIP-Dienst mithilfe der Survivable Branch Appliance-Verbindungs an das Telefonfestnetz. Zweigniederlassung, die Benutzer, die von privaten oder anderen Remotestandorten herstellen mit einem Registrar-Server an einem zentralen Standort zu registrieren werden, wenn die WAN-, um die Zweigniederlassung Verbindung können ist nicht verfügbar. Diese Benutzer müssen vollständige unified Communications-Funktionalität, mit einer Ausnahme, die eingehende Anrufe an die Zweigniederlassung an Voicemail umgeleitet werden. Wenn die WAN-Verbindung verfügbar ist, sollten Benutzer an Zweigniederlassungen unterbrechungsfreie voller Funktionsumfang wiederhergestellt werden. Weder das Failover auf der Survivable Branch Appliance noch die Wiederherstellung eines Diensts erfordert das Vorhandensein von IT-Administrator.
  
Skype für Business Server unterstützt bis zu zwei Survivable Branch Appliance am Zweigstellenstandort. 
  
#### <a name="survivable-branch-appliance-deployment-overview"></a>Übersicht über die Survivable Branch Appliance-Bereitstellung

Der Survivable Branch Appliance ist von Originalgeräteherstellern in Zusammenarbeit mit Microsoft hergestellt und in ihrem Auftrag von Mehrwert Einzelhandelsunternehmen bereitgestellt. Nur nach dem Skype für Business Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit den Zweigstellenstandort vorhanden ist und Benutzer des zweigstellenstandorts für Enterprise Voice aktiviert sind, sollten diese Bereitstellung auftreten.
  
Ausführliche Informationen zu diesen Phasen finden Sie unter [Bereitstellen einer Survivable Branch Appliance oder einen Server](http://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) in der Bereitstellungsdokumentation.
  
|**Phase**|**Schritte**|**Benutzerrechte**|
|:-----|:-----|:-----|
|Einrichten von Active Directory-Domänendienste für die Survivable Branch Appliance  <br/> |**Am zentralen Standort:** <br/>  Erstellen Sie ein Domänenbenutzerkonto (oder Unternehmensidentität) für den Techniker, installieren und Aktivieren der Survivable Branch Appliance am Zweigstellenstandort wird. <br/>  Erstellen Sie ein Computerkonto (mit den entsprechenden vollqualifizierten Domänennamen (FQDN)) für Survivable Branch Appliance in Active Directory-Domänendienste. <br/>  Erstellen und Veröffentlichen der Survivable Branch Appliance, im Topologie-Generator. <br/> |Das Benutzerkonto für den Techniker muss Mitglied der RTCUniversalSBATechnicians. Der Survivable Branch Appliance müssen der Gruppe RTCSBAUniversalServices gehören, die automatisch erfolgt, wenn Sie den Topologie-Generator verwenden.  <br/> |
|Installieren und Aktivieren der Survivable Branch Appliance.  <br/> |**Am Zweigstellenstandort:** <br/>  Verbinden Sie die Survivable Branch Appliance mit einem Ethernet-Port und die PSTN-Port. <br/>  Starten Sie die Survivable Branch Appliance. <br/>  Fügen Sie der Survivable Branch Appliance zur Domäne, verwenden das Domänenbenutzerkonto, das für die Survivable Branch Appliance am zentralen Standort erstellt. Legen Sie den FQDN und IP-Adresse mit dem FQDN übereinstimmen, die in das Computerkonto erstellt. <br/>  Konfigurieren der Survivable Branch Appliance mithilfe der OEM-Benutzeroberfläche an. <br/>  PSTN-Anbindung zu testen. <br/> |Das Benutzerkonto für den Techniker muss Mitglied der RTCUniversalSBATechnicians.  <br/> |
   
#### <a name="survivable-branch-server-details"></a>Details zur Survivable Branch Server

Im Topologie-Generator fügen Sie den Zweigstellenstandort erstellen den Survivable Branch Server in dieser Website hinzu, und führen Sie die Skype für Business Server-Bereitstellungs-Assistenten auf dem Computer, auf dem Sie die Rolle installieren möchten.
  
### <a name="branch-site-resiliency-requirements"></a>Branch Site Resiliency requirements

Dieses Thema hilft Ihnen beim Vorbereiten der Benutzer für Zweigstellenstandorte und ausfallsichere VoIP-Funktionen und gibt auch die entsprechenden Hardware und Software-Anforderungen an.
  
#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Vorbereiten von Zweigstellenbenutzern für Zweigstellenstandorte

Bereiten Sie Benutzer für Zweigstellenstandorte, indem Sie deren registrierungspool als Survivable Branch Appliance (SBA) oder einen Survivable Branch Server festlegen.
  
#### <a name="registrar-assignments-for-branch-users"></a>Registrierungszuweisungen für Zweigstellenbenutzer

Unabhängig davon welche Branch-Site Resiliency Lösung Sie auswählen, müssen Sie jedem Benutzer eine primäre Registrierungsstelle zuzuweisen. Zweigstellenbenutzer sollte immer mit dem Registrar am Zweigstellenstandort, unabhängig davon, ob diese Registrierung in der Survivable Branch Appliance, Survivable Branch Server oder eigenständigen Skype für Business Server Standard oder Enterprise Edition befindet sich registrieren Server. Ein Ressourceneintrag für Domain Name System (DNS) Service (SRV) ist erforderlich, damit ein Client seine Registrar-Pools ermitteln kann. Wenn der Survivable Branch Appliance nicht mehr verfügbar ist, ist dies wie Branch Site Clients Sicherungsregistrierung automatisch erkennen.
  
Wenn ein Zweigstellenstandort nicht über einen DNS-Server verfügt, gibt es zwei Alternativen zur Ermittlung der Survivable Branch Appliance oder einen Survivable Branch Server konfigurieren:
  
- Konfigurieren von DHCP-Option 120 auf den Zweigstellenstandort Dynamic Host Configuration Protocol (DHCP) Server So zeigen Sie auf den vollqualifizierten Domänennamen (FQDN) der Survivable Branch Appliance oder einen Survivable Branch Server.
    
- Konfigurieren Sie die Survivable Branch Appliance oder Survivable Branch Server, um auf DHCP 120-Abfragen zu reagieren.
    
#### <a name="voice-routing-for-branch-users"></a>VoIP-Routing für Zweigstellenbenutzer

Es wird empfohlen, dass Sie einen separaten auf Benutzerebene Voice over Internet Protocol (VoIP) Richtlinie für Benutzer an einem Zweigstellenstandort erstellen. Diese Richtlinie sollte enthalten eine primäre Route, die der Survivable Branch Appliance oder eine Filiale Server Gateway verwendet, und eine oder mehrere backup-Routen, die einen Trunk mit einem Gateway public switched Telephone Network (Telefonfestnetz PSTN) am zentralen Standort verwenden. Wenn die primäre Route nicht verfügbar ist, wird die Sicherung Route, die mindestens einen zentralen Standort Gateways verwendet stattdessen verwendet. Auf diese Weise unabhängig davon, in dem ein Benutzer registriert ist, auf den Zweigstellenstandort Registrierung oder die Sicherungsregistrierungsstellen-Pool am zentralen Standort – VoIP-Richtlinie des Benutzers ist immer aktiviert. Dies ist ein wichtiger Aspekt für Failover-Szenarien. Angenommen, wenn Sie zum Umbenennen der Survivable Branch Appliance oder Neukonfigurieren der Survivable Branch Appliance zu einer Sicherung Registrar-Pool am zentralen Standort herstellen müssen, müssen Sie Benutzer des zweigstellenstandorts am zentralen Standort für die Dauer verschieben. (Ausführliche Informationen zum Umbenennen oder einen Survivable Branch Appliance Neukonfiguration finden Sie unter [Anhang B: Verwalten einer Survivable Branch Appliance](http://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine VoIP-Richtlinien auf Benutzerebene oder Benutzerebene-Wählpläne, wenn die Benutzer in einer anderen Website verschoben werden, auf Standortebene die VoIP-Richtlinien auf Standort- und auf Standortebene wählen, die Pläne von am zentralen Standort auf die Benutzer in der Standardeinstellung, anstatt den Zweigstellenstandort anwenden VoIP Richtlinien und Dial Plans. In diesem Szenario können Sie es sei denn, die auf Standortebene VoIP-Richtlinien und Standort-Wählpläne von verwendet sicherungsregistrierungspool kann auch auf die Zweigstellenbenutzer anwenden, die Aufrufe fehl. Beispielsweise wenn Benutzer aus einer Zweigniederlassung befindet sich im Japan mit einem zentralen Standort in Redmond verschoben werden, ist ein Wählplan mit Normalisierungsregeln, die + 1425 alle 7 Ziffer Anrufe voranstellen entsprechend Übersetzen von Anrufen für diesen Benutzer wahrscheinlich nicht.
  
> [!IMPORTANT]
> Wenn Sie eine Branch Office backup Route erstellen, wird empfohlen, dass Sie die Branch Office Benutzerrichtlinie zwei PSTN-telefonverwendungsdatensätze hinzu, und weisen Sie separate Routen zu jedem Befehl die EINGABETASTE. Die erste oder primären, leitet Route Aufrufe an das Gateway der Survivable Branch Appliance (SBA) oder Branch Server zugeordnet; die zweite oder Sicherung, leitet Route Aufrufe an das Gateway am zentralen Standort. In Umleiten von Anrufen, versucht der SBA oder eine Filiale Server alle Routen der erste PSTN-Datensatz zugewiesen sind, bevor Sie versuchen, des zweiten Datensatzes. 
  
Um sicherzustellen, dass eingehende Anrufe an Benutzer des zweigstellenstandorts diese Benutzer erreichen werden, wenn das Gateway Branch oder die Windows-Komponente der Survivable Branch Appliance-Website nicht verfügbar ist (die würde beispielsweise eintreten, wenn die Survivable Branch Appliance oder Zweigniederlassung Gateway wurden nach unten für die Wartung), eine failoverroute auf dem Gateway (oder die Arbeit mit Ihrem Anbieter (Direct Inward Dialing, DIALING)) zum Umleiten von eingehender Anrufen an die Sicherungsregistrierungsstellen-Pool am zentralen Standort erstellen. Von dort, die die Anrufe weitergeleitet werden, über das WAN Link zu Zweigstellenbenutzer. Stellen Sie sicher, dass die Route Rufnummern zur Einhaltung der PSTN-Gateway oder anderen trunkpeer akzeptierte rufnummernformate übersetzt. Ausführliche Informationen zum Erstellen einer failoverroute finden Sie unter [Konfigurieren einer Failoverroute](http://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Erstellen Sie auch Servicelevel Wähleinstellungen für den Trunk zugeordnet das Gateway am Zweigstellenstandort eingehende Anrufe normalisiert werden sollen. Wenn Sie zwei Survivable Branch Appliances an einem Zweigstellenstandort verfügen, können Sie einen Wählplan auf Websiteebene für beide erstellen, es sei denn, die ein separater Servicelevel Plan für die einzelnen erforderlich ist.
  
> [!NOTE]
> Um die Auslastung der zentralen Standort Ressourcen nach jeder Zweigstellenbenutzer berücksichtigen, die den zentralen Standort für Anwesenheitsinformationen, Konferenzen oder Failover verwenden, wird empfohlen, dass Sie jeden Branch Sitebenutzer in Betracht ziehen, als wäre der Benutzer mit einem zentralen Standort registriert wurden. Es gibt zurzeit keine Grenzwerte für die Anzahl der Benutzer des zweigstellenstandorts, einschließlich der Benutzer mit einer Survivable Branch Appliance registriert. 
  
Außerdem wird empfohlen, dass Sie eine auf Benutzerebene Dial Plan und VoIP-Richtlinie zu erstellen, und weisen Sie es dann Zweigstellenbenutzer. Weitere Informationen hierzu finden Sie unter [Erstellen oder Ändern von Wähleinstellungen in Skype für Business Server 2015](../../deploy/deploy-enterprise-voice/dial-plans.md) und [VoIP-Routingrichtlinie für Zweigstellenbenutzer erstellen](http://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) in der Bereitstellungsdokumentation.
  
#### <a name="routing-extension-numbers"></a>Weiterleiten von Durchwahlnummern

Bei der Vorbereitung von Wähleinstellungen und VoIP-Richtlinien für Benutzer des zweigstellenstandorts, unbedingt Normalisierungsregeln und Übersetzungsregeln, die die Zeichenfolgen und Zahlenformat verwendet, in der MsRTCSIP-Line (oder Anschluss-URI) entsprechen-Attributs, sodass Skype für geschäftliche Anrufe aktiviert zwischen Zweigstellenbenutzer und zentralen Standort Benutzer weitergeleitet werden ordnungsgemäß – insbesondere wenn Anrufe müssen werden umgeleitet, über das Telefonfestnetz, da die WAN-Verbindung nicht verfügbar ist. Darüber hinaus stehen besondere Aspekte bei gewählter Nummern, die Durchwahlnummern, lieber Telefonnummern enthalten.
  
Haben zusätzliche Anforderungen Normalisierungsregeln und Übersetzungen Regeln, die Zeile URIs entsprechen, die eine Durchwahlnummer, ob ausschließlich oder zusätzlich zu einer vollständigen e. 164-Telefonnummer enthalten. In diesem Abschnitt werden einige Beispielszenarien für das Anrufrouting für Zeile URIs mit einer Durchwahlnummer beschrieben.
  
Wenn Ihre Organisation keinen (Direct Inward Dial, DIALING) Rufnummern für einzelne Benutzer konfiguriert und den Anschluss-URI der einzelnen Benutzer mit nur einer Durchwahlnummer konfiguriert ist, können interne Benutzer voneinander aufrufen, indem nur einer Durchwahlnummer wählen. Sie müssen jedoch Normalisierungsregeln, die Anrufe von einem Branch Sitebenutzer zu einem zentralen Standort Benutzer anwenden können konfigurieren, die die Durchwahlnummern entsprechen.
  
In einem Szenario, in dem die WAN-Verbindung zwischen einer Zweigstelle und einem zentralen Standort, ist verfügbar, Anrufe von Zweigstellenbenutzer zum zentralen Standort Benutzer keine erfordern, dass die übereinstimmenden Normalisierungsregel die Nummer übersetzt wird, da der Anruf nicht wird über das PSTN weitergeleitet. Beispiel:
  
|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |5-Ziffern werden nicht übersetzt werden.  <br/> |^ (\d{5})$  <br/> |$1  <br/> |10001 wird nicht übersetzt.  <br/> |
   
Sie müssen auch Durchwahlnummern für bestimmte Szenarien erfüllen, z. B., wenn die WAN-Verbindung zwischen einer Zweigstelle und dem zentralen Standort ist nicht verfügbar und ein Anruf von einem Zweigstellenstandort über das Telefonfestnetz weitergeleitet werden muss. Während eines WAN-Ausfalls Falls ein Websitebenutzer Branch zentralen Standort Benutzer anrufen, nur durch wählen den zentralen Standort des Benutzers Erweiterung, müssen Sie eine ausgehende übersetzungsregel verfügen, die vollständige Telefonnummer des Benutzers, der den zentralen Standort hinzufügt. Wenn Anschluss-URI des Benutzers enthält die vollständige Telefonnummer Ihrer Organisation und eindeutige Durchwahlnummer des Benutzers, anstatt eine vollständige Telefonnummer ein, die für den Benutzer eindeutig ist, muss eine ausgehende übersetzungsregel sein, die vollständige Telefonnummer Ihrer Organisation stattdessen hinzufügt . Beispiel:
  
|**Beschreibung**|**Übereinstimmendes Muster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Übersetzt 5-stellige Nummern in Telefonnummer und die Erweiterung eines Benutzers  <br/> |^ (\d{5})$  <br/> |+ 14255550123; Ext = $1  <br/> |10001 wird übersetzt in + 14255550123; Ext = 10001 übersetzt  <br/> |
|Übersetzt 5-stellige Nummern in Ihrer Organisation Telefon- und Durchwahlnummer eines Benutzers  <br/> |^ (\d{5})$  <br/> |+ 14255550100; Ext = $1  <br/> |10001 wird in + 14255550100; übersetzt Ext = 10001 übersetzt  <br/> |
   
In diesem Szenario Wenn der trunkpeer, der die Weiterleitung an das Telefonfestnetz behandelt Durchwahlnummern, nicht unterstützt muss die ausgehende übersetzungsrichtlinie auch die Durchwahlnummer entfernen. Beispiel:
  
|**Beschreibung**|**Übereinstimmendes Muster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Entfernt die Durchwahl von Telefonnummern mit Durchwahlnummern  <br/> |^\+(\d\*); ext=(\d\*)$  <br/> |+$1  <br/> |+ 14255550123; Ext = 10001 wird in + 14255550123 übersetzt  <br/> |
   
Unabhängig davon, ob eine WAN-Verbindung ist verfügbar, wenn Ihre Organisation keinen DID-Nummern, die für einzelne Benutzer konfiguriert den Anschluss-URI für einen Benutzer enthält Telefonnummer Ihrer Organisation und eindeutige Durchwahlnummer des Benutzers, und Sie müssen Konfigurieren Ihrer Organisation Anzahl Telefonleitung URI mit einer Nummer, die durch den trunkpeer oder PSTN-Gateway am Zweigstellenstandort erreichbar ist. Sie müssen auch Ihrer Organisation Anzahl Telefonleitung URI eine eigene eindeutige-Erweiterung für Anrufe an diese Nummer weitergeleitet werden sollen konfigurieren.
  
#### <a name="preparing-for-voice-mail-survivability"></a>Vorbereiten der ausfallsichere VoIP-Funktionen

Exchange Unified Messaging (UM) ist in der Regel nur an einem zentralen Standort und nicht auf Zweigniederlassungen installiert. Ein Anrufer sollten in der Lage, eine Nachricht hinterlassen, auch wenn die WAN-Verbindung zwischen Zweigstelle und dem zentralen Standort ist nicht verfügbar. Dementsprechend, erfordert besondere Aspekte, zusätzlich zu den VoIP-Richtlinie für Planung und Normalisierungsregeln gelten, Voicemail wählen die Konfiguration der Anschluss-URI für die Exchange UM-Telefonzentrale Telefonnummer, die für Zweigstellenbenutzer Voicemail bereitstellt Anzahl.
  
Survivable Branch Appliances (SBAs) und Survivable Branch Server bieten ausfallsichere VoIP-Funktionen für Zweigstellenbenutzer während eines WAN-Ausfalls. Insbesondere leitet Sie verwenden eine Survivable Branch Appliance oder Survivable Branch Server- und das WAN zur Verfügung steht, der SBA oder einen Survivable Branch Server nicht beantwortete Anrufe über das Telefonfestnetz an Exchange UM am zentralen Standort. Mit einem SBA oder einen Survivable Branch Server können Benutzer auch Voicemailnachrichten über das Telefonfestnetz während eines WAN-Ausfalls abrufen. Schließlich während eines WAN-Ausfalls der Survivable Branch Appliance oder einen Survivable Branch Server Warteschlangen Benachrichtigungen über verpasste Anrufe und hochgeladen, auf dem Exchange UM-Server, wenn das WAN wiederhergestellt wird. Um sicherzustellen, dass voicemailumleitung ausfallsicher ist, achten Sie darauf, dass Sie einen Eintrag für den zentralen Standort Pool-FQDN und einen Eintrag für den Edge-Server-FQDN der Hostdatei auf dem Survivable Branch Server hinzufügen. Anderenfalls DNS-Auflösung kann Timeout, wenn Sie nicht über einen DNS-Server am Zweigstellenstandort verfügen.
  
Es wird empfohlen, die folgenden Konfigurationen für ausfallsichere VoIP-Funktionen für Zweigstellenbenutzer: 
  
- Microsoft Exchange-Administrator sollte Exchange UM Auto Attendant Annahme von Nachrichten nur konfiguriert. Diese Konfiguration deaktiviert alle anderen generischen Funktionen wie Übertragung auf einen Benutzer oder Übertragung auf einen Operator und AA zum Akzeptieren von Nachrichten nur beschränkt. Alternativ können Sie mit der Exchange-Administrator eine generische AA oder eine automatische Telefonzentrale angepasst, um den Anruf an einen Operator weiterleiten verwenden.
    
- Die Skype für Business Server-Administrator sollte übernehmen die Rufnummer der automatischen Telefonzentrale und der angegebenen Telefonnummer an als Rufnummer für den **Exchange um-Telefonzentrale** in den voicemailumleitungseinstellungen für die Survivable Branch Appliance oder Branch Server verwenden.
    
- Die Skype für Business Server-Administrator sollte Rufnummer für die Exchange UM-Teilnehmerzugriff erhalten und diese Nummer verwenden, als die Anzahl der **Abonnentenzugriff** in den voicemailumleitungseinstellungen für die Survivable Branch Appliance oder einen Survivable Branch Server .
    
- Die Skype für Business Server-Administrator sollte Exchange UM konfigurieren, so dass nur eine Wähleinstellungen allen Zweigstellenbenutzern zugeordnet wird, die während eines WAN-Ausfalls auf Voicemail zugreifen.
    
- Wenn die WAN-Verbindung nicht verfügbar ist, Anrufe an Benutzer des zweigstellenstandorts an das Postfach des Benutzers Exchange Unified Messaging (UM) Voicemail weitergeleitet werden können, aber nur, wenn der Aufruf die VoIP-Richtlinie zugewiesen gibt eine Voice Mail unter der Telefonnummer, die ist eindeutig und enthält keine Erweiterung Anzahl.
    
#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Hardware- und Softwareanforderungen für Zweigstellenstandorte

Hardware-und softwareanforderungen variieren je nach ausfallsicherheitslösung.
  
#### <a name="requirements-for-survivable-branch-appliances"></a>Anforderungen für Survivable Branch Appliances

Erforderliche Hardware und Software ist in der Survivable Branch Appliance integriert. Jedoch wird empfohlen, dass jede Zweigniederlassung Client IP-Adressen für DHCP-Server bereitstellen; andernfalls, wenn die DHCP-Lease abläuft, Clients nicht keine IP-Verbindung haben.
  
Die Enterprise-DNS-Server nur in der zentralen Standorten befinden, Zweigstellenbenutzer können keine während eines WAN-Ausfalls herstellen, und daher Skype für die Ermittlung Business Server, die DNS-SRV (Service (SRV)-Ressourceneintrag) wird verwendet, schlägt fehl. Um während eines WAN-Ausfalls Prompt Weiterleitung zu gewährleisten, müssen die DNS-Einträge am Zweigstellenstandort zwischengespeichert werden sollen. Wenn Router der Zweigstelle unterstützt, aktivieren Sie DNS-Cache. Alternativ können Sie einen DNS-Server am Zweigstellenstandort bereitstellen. Dies kann sein, einen eigenständigen Server oder eine Version von der Survivable Branch Appliance, die DNS-Funktionen unterstützt. Weitere Informationen hierzu wenden Sie sich an Ihren Anbieter Survivable Branch Appliance.
  
> [!NOTE]
> Es ist nicht erforderlich, einen Domänencontroller an einem Zweigstellenstandort haben. Der Survivable Branch Appliance authentifiziert Clients mit einem speziellen Zertifikat, das er des Clients als Antwort auf die Clientanforderung Zertifikat sendet, wenn er sich anmeldet. 
  
Skype für Unternehmenskunden kann das Skype für Business Server erkennen, mithilfe von DHCP-Option 120 (SIP-Registrierung Option). Dies kann auf zwei Arten konfiguriert werden:
  
- Konfigurieren Sie den DHCP-Server am Zweigstellenstandort so Antworten Sie auf DHCP 120-Abfragen, die den FQDN der Registrierung auf dem Survivable Branch Appliance oder einen Survivable Branch Server zurückgeben.
    
- Skype für Business Server DHCP aktivieren. Wenn dies aktiviert ist, reagiert der Skype Business Server Registrierungsstelle für DHCP-Option 120-Abfragen. Beachten Sie, dass die Registrierung nicht auf DHCP-Abfragen als DHCP-Optionen 120 reagiert.
    
Zusätzlich sollten für größere Zweigstellenstandorte, die mehreren Subnetzen, DHCP-Relay-Agents zum Weiterleiten DHCP-Option 120-Abfragen an den DHCP-Server (Konfiguration 1) oder die Registrierung (Konfiguration 2) aktiviert.
  
Schließlich müssen Benutzer des zweigstellenstandorts für Enterprise Voice konfiguriert und bereitgestellt, die mit einem geeigneten unified Communications-Endpunkt.
  
#### <a name="requirements-for-survivable-branch-servers"></a>Anforderungen für Survivable Branch Server

Die Anforderungen für Survivable Branch Server stimmen die Anforderungen für einen Front-End-Server. Weitere Informationen hierzu finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).
  
#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Anforderungen für vollständige Skype für Business Server-Branch-Site-Bereitstellungen

Weitere Informationen hierzu finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) in der Planungsdokumentation.
  
### <a name="example-configuring-a-failover-route"></a>Beispiel: Konfigurieren einer failoverroute

 Das folgende Beispiel zeigt, wie ein Administrator für die Verwendung eine failoverroute definieren kann, wenn die Dallas-GW1 für Wartungsarbeiten heruntergefahren wurde oder anderweitig nicht verfügbar ist. In den folgenden Tabellen werden die erforderliche konfigurationsänderung veranschaulicht.
  
**In Tabelle 1. Benutzerrichtlinie**

|**Benutzerrichtlinie**|**Telefonverwendung**|
|:-----|:-----|
|Standardanrufrichtlinie  <br/> |Lokal  <br/> "Globalpstnhopoff"  <br/> |
|Richtlinie für Ortsgespräche Redmond  <br/> |RedmondLocal  <br/> |
|Anrufrichtlinie für Dallas  <br/> |DallasUsers  <br/> "Globalpstnhopoff"  <br/> |
   
**In Tabelle 2. Routen**

|**Name der Route**|**Nummernmuster**|**Telefonverwendung**|**Trunk**|**Gateway**|
|:-----|:-----|:-----|:-----|:-----|
|Route für Ortsgespräche Redmond  <br/> |^\+1 (425|206|253)(\d{7})$  <br/> |Lokal  <br/> RedmondLocal  <br/> |Trunk1  <br/> Trunk2  <br/> |Red-GW1  <br/> Red-GW2  <br/> |
|Route für Ortsgespräche Dallas  <br/> |^\+1 (972|214|469)(\d{7})$  <br/> |Lokal  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
|Universalroute  <br/> |^\+?(\d\*)$  <br/> |"Globalpstnhopoff"  <br/> |Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> |Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
|Route für Dallas Benutzer  <br/> |^\+?(\d\*)$  <br/> |DallasUsers  <br/> |Trunk3  <br/> |Dallas-GW1  <br/> |
   
In Tabelle 1 wird die Telefonverwendung "globalpstnhopoff" nach der Telefonverwendung Auslastung in Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe die anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für die Telefonverwendung globalpstnhopoff konfiguriert sind, wenn eine Route für die Telefonverwendung nicht verfügbar ist.
  

