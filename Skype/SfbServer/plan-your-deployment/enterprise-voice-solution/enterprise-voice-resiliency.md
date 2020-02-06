---
title: Plan for Enterprise Voice resiliency in Skype for Business Server
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Hier erfahren Sie, wie Sie die sprach Stabilität in Skype for Business Server Enterprise-VoIP sowohl an zentralen Websites als auch an Zweigstellen unterstützen. Zu den Optionen für die Verzweigungs Website gehören die Bereitstellung von Survivable Branch Appliances oder Survivable Branch Servern.
ms.openlocfilehash: e64ac79ef49339401c5b2d0bbb7d27140eca4296
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802945"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Plan for Enterprise Voice resiliency in Skype for Business Server

Hier erfahren Sie, wie Sie die sprach Stabilität in Skype for Business Server Enterprise-VoIP sowohl an zentralen Websites als auch an Zweigstellen unterstützen. Zu den Optionen für die Verzweigungs Website gehören die Bereitstellung von Survivable Branch Appliances oder Survivable Branch Servern.

Die sprach Stabilität bezieht sich auf die Möglichkeit von Benutzern, weiterhin Anrufe zu tätigen und zu empfangen, wenn eine zentrale Website, die Skype for Business Server hostet, nicht mehr zur Verfügung steht, ob es sich um einen WAN-Fehler (Wide Area Network) oder eine andere Ursache handelt. Wenn ein zentraler Standort ausfällt, muss der Enterprise-VoIP-Dienst durch ein nahtloses Failover zu einer Sicherungswebsite unterbrechungsfrei fortgesetzt werden. Bei einem WAN-Fehler müssen Branch Site-Aufrufe an ein lokales PSTN-Gateway umgeleitet werden. In diesem Abschnitt wird die Planung der sprach Sicherheit bei einem zentralen Standort-oder WAN-Fehler erläutert.

## <a name="central-site-resiliency"></a>Stabilität des zentralen Standorts

In zunehmendem Maße haben Unternehmen mehrere Websites, die sich auf der ganzen Welt verteilen. Die Verwaltung von Notfalldiensten, der Zugriff auf den Helpdesk und die Möglichkeit, wichtige Geschäftsaufgaben auszuführen, wenn eine zentrale Website nicht mehr zur Verfügung steht, ist für die Lösung von Enterprise-VoIP-Resilienz unerlässlich. Wenn eine zentrale Website nicht mehr verfügbar ist, müssen die folgenden Bedingungen erfüllt sein:

- Sprach-Failover muss bereitgestellt werden.

- Benutzer, die sich normalerweise beim Front-End-Pool am zentralen Standort registrieren, müssen sich mit einem alternativen Front-End-Pool registrieren können. Dies kann durch Erstellen mehrerer DNS-SRV-Einträge erfolgen, die jeweils zu einem Director-Pool oder einem Front-End-Pool in jeder ihrer zentralen Websites aufgelöst werden. Sie können die Priorität und die Gewichtung der SRV-Einträge anpassen, damit Benutzer, die von dieser zentralen Website bedient werden, den entsprechenden Director und den Front-End-Pool vor denen in anderen SRV-Einträgen erhalten.

- Anrufe an und von Benutzern, die sich an anderen Standorten befinden, müssen an das PSTN umgeleitet werden.

In diesem Thema wird die empfohlene Lösung zum Sichern der VoIP-Stabilität der zentralen Website beschrieben.

### <a name="architecture-and-topology"></a>Architektur und Topologie

Für die Planung der sprach Stabilität an einem zentralen Standort ist ein grundlegendes Verständnis der zentralen Rolle erforderlich, die von der Skype for Business Server-Registrierungsstelle bei der Aktivierung des sprach Failovers gespielt wird. Die Skype for Business Server-Registrierungsstelle ist ein Dienst, der die Clientregistrierung und-Authentifizierung ermöglicht und Routingdienste bereitstellt. Sie wird auf allen Standard Edition-Servern, Front-End-Servern, Directors oder Survivable Branch-Appliances ausgeführt. Ein Registrierungspool besteht aus Registrierungsdiensten, die im Front-End-Pool ausgeführt werden und sich am gleichen Standort befinden. Ein Skype for Business-Client erkennt den Front-End-Pool mithilfe des folgenden Ermittlungsmechanismus:

1. DNS-SRV-Eintrag

2. AutoDiscovery Web Service

3. DHCP-Option 120

Nachdem der Skype for Business-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Load Balancer an einen der Front-End-Server im Pool weitergeleitet. Dieser Front-End-Server leitet den Client wiederum an eine bevorzugte Registrierungsstelle im Pool um.

Jeder Benutzer, der für Enterprise-VoIP aktiviert ist, wird einem bestimmten Registrar-Pool zugewiesen, der zum primären Registrierungspool des Benutzers wird. An einer bestimmten Website teilen sich in der Regel Hunderte oder Tausende von Benutzern einen einzigen primären Registrierungspool. Zum berücksichtigen des Verbrauchs von Ressourcen für zentrale Websites durch alle Zweigstellenbenutzer, die auf die zentrale Website für Anwesenheit, Konferenz oder Failover angewiesen sind, empfehlen wir, dass Sie die einzelnen Verzweigungs Websitebenutzer als Benutzer berücksichtigen, die bei der zentralen Website registriert sind. Derzeit gibt es keine Beschränkungen für die Anzahl der Benutzer von Zweigstellen, einschließlich der Benutzer, die bei einer Survivable Branch-Appliance registriert sind.

Um die sprach Sicherheit bei einem zentralen Standortausfall zu gewährleisten, muss der primäre Registrierungspool über einen einzelnen dedizierten Sicherungs Registrierungs Registrierungspool an einer anderen Website verfügen. Die Sicherung kann mithilfe der Stabilitäts Einstellungen des Topologie-Generators konfiguriert werden. Unter der Voraussetzung, dass eine stabile WAN-Verbindung zwischen den beiden Websites besteht, werden Benutzer, deren primärer Registrierungspool nicht mehr verfügbar ist, automatisch an den sicherungsregistrierungspool weitergeleitet.

Die folgenden Schritte beschreiben den Client Ermittlungs-und Registrierungsprozess:

1. Ein Client erkennt Skype for Business Server über DNS-SRV-Einträge. In Skype for Business Server können DNS-SRV-Einträge so konfiguriert werden, dass mehr als ein FQDN an die DNS-SRV-Abfrage zurückgegeben wird. Wenn Enterprise Contoso beispielsweise über drei zentrale Standorte (Nordamerika, Europa und Asien – Pazifik) und einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die FQDNs des Director-Pools in jedem der drei Speicherorte verweisen. Solange der Director-Pool an einem der Speicherorte verfügbar ist, kann der Client eine Verbindung mit dem ersten Hop-Skype for Business-Server herstellen.

    > [!NOTE]
    > Die Verwendung eines Director-Pools ist optional. Stattdessen kann ein Front-End-Pool verwendet werden.

2. Der Director-Pool informiert den Skype for Business-Client über den primären Registrierungspool und den sicherungsregistrierungspool des Benutzers.

3. Der Skype for Business-Client versucht zunächst, eine Verbindung mit dem primären Registrierungspool des Benutzers herzustellen. Wenn der primäre Registrierungspool verfügbar ist, akzeptiert die Registrierungsstelle die Registrierung. Wenn der primäre Registrierungspool nicht verfügbar ist, versucht der Skype for Business-Client, eine Verbindung mit dem sicherungsregistrierungspool herzustellen. Wenn der sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (durch Erkennen eines fehlenden Heartbeats für ein angegebenes Failover-Intervall), akzeptiert der sicherungsregistrierungspool die Registrierung des Benutzers. Nachdem die Sicherungs Registrierungsstelle festgestellt hat, dass die primäre Registrierungsstelle wieder verfügbar ist, leitet der sicherungsregistrierungspool Failover-Clients an Ihren primären Pool um.

### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Die folgenden Voraussetzungen und Empfehlungen für die Implementierung der VoIP-Flexibilität für die zentrale Website sind für die meisten Organisationen geeignet:

- Die Websites, auf denen sich die primären und die Sicherungs registrierungspools befinden, sollten über eine stabile WAN-Verbindung verbunden sein.

- Jede zentrale Website muss einen Registrierungspool enthalten, der aus einer oder mehreren Registrierungsstellen besteht.

- Jeder Registrierungspool muss mithilfe des DNS-Lastenausgleichs, des Hardwarelastenausgleichs oder beider Lastenausgleich erfolgen. Detaillierte Informationen zum Planen Ihrer Lastenausgleichskonfiguration finden Sie unter [Lastenausgleichsanforderungen für Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Jeder Benutzer muss einem primären registrierungsstellenpool mithilfe des Cmdlets "Skype for Business Server **-Verwaltungsshell-CsUser** " oder der Skype for Business Server-Systemsteuerung zugewiesen werden.

- Der primäre Registrierungspool muss über einen einzelnen sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.

- Der primäre Registrierungspool muss so konfiguriert sein, dass ein Failover zum sicherungsregistrierungspool durchführen kann. Standardmäßig ist die primäre Registrierungsstelle so eingestellt, dass Sie nach einem Intervall von 300 Sekunden ein Failover für den sicherungsregistrierungspool durchführen kann. Sie können dieses Intervall mit dem Skype for Business Server Topology Builder ändern.

- Konfigurieren Sie eine Failover-Route. Geben Sie bei der Konfiguration der Route ein Gateway an, das sich an einem anderen Standort als dem Gateway befindet, das auf der primären Route angegeben ist.

- Wenn die zentrale Website Ihren primären Verwaltungsserver enthielt und die Website wahrscheinlich für einen längeren Zeitraum nicht mehr zur Verfügung steht, müssen Sie Ihre Verwaltungstools auf der Sicherungswebsite erneut installieren. Andernfalls können Sie keine Verwaltungseinstellungen ändern.

### <a name="dependencies"></a>Abhängigkeiten

Skype for Business Server hängt von den folgenden Infrastruktur-und Softwarekomponenten ab, um die sprach Sicherheit zu gewährleisten:

|**Komponente** <br/> |**Funktions** <br/> |
|:-----|:-----|
|DNS  <br/> |Auflösen von SRV-Einträgen und Datensätzen für Server-Server-und Server-Client-Konnektivität  <br/> |
|Exchange-und Exchange-Webdienste (EWS)  <br/> |Kontaktspeicher; Kalenderdaten  <br/> |
|Exchange Unified Messaging und Exchange-Webdienste  <br/> |Anrufprotokolle, voicemailliste, Voicemail  <br/> |
|DHCP-Optionen 120  <br/> |Wenn der DNS-SRV nicht zur Verfügung steht, versucht der Client, DHCP-Option 120 zu verwenden, um die Registrierungsstelle zu ermitteln. Damit dies funktioniert, muss entweder ein DHCP-Server konfiguriert sein, oder Skype for Business Server DHCP muss aktiviert sein.  <br/> |

### <a name="survivable-voice-features"></a>Überlebende sprach Features

Wenn die Voraussetzungen und Empfehlungen implementiert wurden, werden die folgenden Sprachfeatures vom sicherungsregistrierungspool bereitgestellt:

- Ausgehende PSTN-Anrufe

- Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter die Möglichkeit unterstützt, ein Failover zu einer Sicherungswebsite durchführen zu können

- Enterprise-Anrufe zwischen Benutzern am gleichen Standort und zwischen zwei unterschiedlichen Websites

- Einfache Anrufbehandlung, einschließlich Anruf halten, abrufen und übertragen

- Instant Messaging mit zwei Teilnehmern und Freigeben von Audio und Video zwischen Benutzern am gleichen Standort

- Anrufweiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Team Anrufdienste, aber nur, wenn beide Teilnehmer die Delegation oder alle Teammitglieder anrufen, auf der gleichen Website konfiguriert sind.

- Vorhandene Telefone und Clients funktionieren weiterhin.

- Aufzeichnung von Kommunikationsdatensätzen (KDS)

- Authentifizierung und Autorisierung

Je nachdem, wie Sie konfiguriert sind, funktionieren die folgenden Sprachfeatures möglicherweise nicht, wenn eine primäre zentrale Website nicht mehr zur Verfügung steht:

- Voicemail-Einzahlung und-Abruf

    Wenn Sie Exchange um verfügbar machen möchten, wenn der primäre zentrale Standort außer Dienst ist, müssen Sie eine der folgenden Aktionen ausführen:

  - Ändern Sie die DNS-SRV-Einträge so, dass die Exchange um-Server am zentralen Standort auf Exchange-Exchange um-Server an einem anderen Standort verweisen.

  - Konfigurieren Sie die Exchange UM-Wähleinstellungen für jeden Benutzer so, dass Exchange um-Server sowohl am zentralen Standort als auch an der Sicherungswebsite eingeschlossen werden, die Exchange um-Server jedoch als deaktiviert festlegen. Wenn der primäre Standort nicht mehr verfügbar ist, muss der Exchange-Administrator die Exchange um-Server auf der Sicherungswebsite als aktiviert kennzeichnen.

    Wenn keine der vorhergehenden Lösungen möglich ist, steht Exchange um nicht zur Verfügung, wenn die zentrale Website nicht mehr zur Verfügung steht.

- Konferenzen aller Typen

    Ein Benutzer, der ein Failover auf eine Sicherungswebsite durchgeführt hat, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist, aber keine Konferenz im eigenen primären Pool erstellen oder hosten kann, die nicht mehr verfügbar ist. Ebenso können andere Benutzer nicht an Konferenzen teilnehmen, die im primären Pool des betroffenen Benutzers gehostet werden.

Die folgenden Sprachfeatures funktionieren nicht, wenn eine primäre zentrale Website nicht mehr zur Verfügung steht:

- Automatische Telefonzentrale

- Anwesenheits-und auf den textbasierendes Routing

- Aktualisieren der Einstellungen für die Anrufweiterleitung

- Reaktionsgruppendienst und Anruf parken

- Bereitstellungneuer Telefone und Clients

- Adressbuch-Websuche

## <a name="branch-site-resiliency"></a>Stabilität des Zweigstellen Standorts

Wenn Sie eine Ausfallsicherheit für Zweigstellen, also den Enterprise-VoIP-Dienst mit hoher Verfügbarkeit, bereitstellen möchten, stehen Ihnen drei Möglichkeiten zur Verfügung:

- Survivable Branch Appliance

- Survivable Branch Server

- Eine vollständige Skype for Business Server-Bereitstellung auf der Zweigstelle

Dieser Leitfaden hilft Ihnen bei der Beurteilung, welche Stabilitäts Lösung für Ihre Organisation am besten geeignet ist und welche PSTN-Konnektivitäts-Lösung auf der Grundlage ihrer Resilienz-Lösung zu verwenden ist. Darüber hinaus können Sie die Bereitstellung der von Ihnen ausgewählten Lösung vorbereiten, indem Sie Voraussetzungen und andere Planungsüberlegungen beschreiben.

### <a name="branch-site-resiliency-features"></a>Stabilitäts Features für Zweigstellenstandorte

Wenn Sie eine Ausfallsicherheit für Zweigstellen angeben, wenn die WAN-Verbindung einer Zweigstelle zu einem zentralen Standort fehlschlägt oder wenn der zentrale Standort nicht erreichbar ist, sollten die folgenden Sprachfeatures weiterhin zur Verfügung stehen:

- Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)

- Enterprise-Anrufe zwischen Benutzern am gleichen Standort und zwischen zwei unterschiedlichen Websites

- Einfache Anrufbehandlung, einschließlich Anruf halten, abrufen und übertragen

- Instant Messaging mit zwei Teilnehmern

- Anrufweiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Team Anrufdienste, aber nur, wenn der delegator und Stellvertreter (beispielsweise ein Manager und der Administrator des Managers) oder alle Teammitglieder am gleichen Standort konfiguriert sind

- Anruf Detaildatensätze (CDRs)

- PSTN-Einwahlkonferenzen mit automatischer Konferenz Automatik

- Voicemail-Funktionen, wenn Sie die Einstellungen für die Umleitung von Voicemail konfigurieren.

- Benutzerauthentifizierung und Autorisierung

Die folgenden Features stehen nur zur Verfügung, wenn Ihre Resilienz-Lösung eine umfassende Skype for Business Server-Bereitstellung auf der Zweigstelle ist:

- Chat-, Web-und A/V-Konferenzen

- Anwesenheits-und (nicht stören)-basiertes Routing (wenn Anrufe an Erweiterungen, die mit "nicht aktiviert" sind, verhindert werden)

- Aktualisieren der Einstellungen für die Anrufweiterleitung

- Anwendung für Reaktionsgruppen und Anruf parken

- Bereitstellungneuer Telefone und Clients, jedoch nur, wenn die Active Directory-Domänendienste auf der Zweigstelle vorhanden sind.

- Enhanced 9-1-1 (E9-1-1)

    Wenn E9-1-1 bereitgestellt wird und der SIP-Stamm am zentralen Standort nicht zur Verfügung steht, weil die WAN-Verbindung nicht verfügbar ist, leitet die Survivable Branch-Appliance E9-1-1-Anrufe an das lokale Verzweigung-Gateway weiter. Um dieses Feature zu aktivieren, sollten die VoIP-Richtlinien für die Zweigstellenbenutzer im Fall eines WAN-Fehlers Anrufe an das lokale Gateway weiterleiten.

> [!NOTE]
> SBA (Survivor Branch Office) wird für XMPP nicht unterstützt. Benutzer, die in einer SBA-Konfiguration verwaltet werden, können keine IMS senden oder Anwesenheitsinformationen mit XMPP-Kontakten anzeigen.

### <a name="branch-site-resiliency-solutions"></a>Stabilitäts Lösungen für Zweigstellenstandorte

Es gibt offensichtliche Vorteile für die Bereitstellung von Ausfallsicherheit für Zweigstellen in Ihrer Organisation. Insbesondere wenn Sie die Verbindung mit dem zentralen Standort verlieren, verfügen die Benutzer der Zweigstelle weiterhin über Enterprise-VoIP-Dienst und Voicemail (wenn Sie die Einstellungen für die Neukonfiguration von Voicemail konfigurieren). Bei Websites mit weniger als 25 Benutzern bietet eine Lösung für Ausfallsicherheit möglicherweise keine ausreichende Rentabilität.

Wenn Sie sich für die Bereitstellung von Ausfallsicherheit für Zweigstellen entscheiden, stehen Ihnen drei Optionen zur Verfügung. In der folgenden Tabelle können Sie die beste Option für Ihre Organisation ermitteln.

|**Wenn Sie...**|**Wir empfehlen die Verwendung einer...**|
|:-----|:-----|
|Hosten Sie zwischen 25 und 1000 Benutzern an ihrer Zweigstelle, und wenn die Kapitalrendite keine vollständige Bereitstellung unterstützt oder wenn die lokale administrative Unterstützung nicht verfügbar ist  <br/> |Survivable Branch Appliance  <br/> Die Survivable Branch-Appliance ist ein branchenüblicher Blade-Server mit einer Skype for Business Server-Registrierungsstelle und einem Vermittlungsserver, die unter Windows Server 2008 R2 ausgeführt werden. Die Survivable Branch-Appliance enthält auch ein PSTN-Gateway (Public Switched Telephone Network). Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im SBA-Qualifizierungs-/-Zertifizierungsprogramm) bieten eine durchgehende PSTN-Verbindung im Fall eines WAN-Fehlers, doch dieser Ansatz bietet keine belastbaren Anwesenheits-und Konferenzfunktionen, da diese Features von Front-End-Servern am zentralen Standort abhängen.  <br/> Details zu Überlebenden Branch-Appliances finden Sie weiter unten in diesem Thema unter "Survival Branch Appliance Details".  <br/> **Hinweis:** Wenn Sie sich entscheiden, auch einen SIP-Trunk für Ihre Survivable Branch-Appliance zu verwenden, wenden Sie sich an den Anbieter von Survivable Branch Appliance, um zu erfahren, welcher Dienstanbieter für Ihre Organisation am besten geeignet ist. <br/> |
|Hosten zwischen 1000-und 2000-Benutzern an ihrer Zweigstelle, keine robuste WAN-Verbindung und geschulte Skype for Business Server-Administratoren verfügbar  <br/> |Überlebensfähiger Branch-Server oder zwei überlebensfähige Branch-Appliances.  <br/> Der Survivable Branch Server ist eine Windows Server-Besprechung, auf die die Hardwareanforderungen für die Skype for Business Server-Registrierungs-und Mediationsserver-Software installiert sind. Sie muss mit einem PSTN-Gateway oder einem SIP-Trunk an einen Telefondienstanbieter angeschlossen werden.  <br/> Ausführliche Informationen zu Überlebenden Verzweigungs Servern finden Sie weiter unten in diesem Thema unter "Survivable Branch Serverdetails".  <br/> |
|Wenn Sie zusätzlich zu den Sprachfeatures für bis zu 5000-Benutzer Anwesenheits-und Konferenzfeatures benötigen und die Skype for Business Server-Administratoren geschult sind  <br/> |Bereitstellen als zentrale Website mit einem Standard Edition-Server und nicht als Verzweigungs Website  <br/> Eine umfassende Skype for Business Server-Bereitstellung bietet eine durchgehende PSTN-Verbindung sowie eine zuverlässige Anwesenheits-und Konferenzfunktion bei einem WAN-Fehler.  <br/> |

#### <a name="resiliency-topologies"></a>Stabilitäts Topologien

Die folgende Abbildung zeigt die empfohlenen Topologien für die Ausfallsicherheit von Zweigstellen.

**Stabilitäts Optionen für Zweigstellenstandorte**

![Optionen für die Widerstandsfähigkeit der sprach Verzweigung](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Details zu Survivable Branch Appliances

Die Survivable Branch-Appliance von Skype for Business Server umfasst die folgenden Komponenten:

- Eine Registrierungsstelle für Benutzerauthentifizierung, Registrierung und Anrufweiterleitung

- Ein Vermittlungs Server für die Verarbeitung der Signalübertragung zwischen der Registrierungsstelle und einem PSTN-Gateway

- Ein PSTN-Gateway zum Weiterleiten von Anrufen an das PSTN als Fall Back Transport bei einem WAN-Ausfall

- SQL Server Express für den lokalen Benutzerdatenspeicher

Die Survivable Branch-Appliance umfasst außerdem PSTN-Stämme, analoge Anschlüsse und einen Ethernet-Adapter.

Wenn die WAN-Verbindung der Zweigstelle zu einem zentralen Standort nicht mehr zur Verfügung steht, werden Benutzer der internen Verzweigung weiterhin bei der überlebensfähigen Branch Appliance-Registrierungsstelle registriert und erhalten unterbrechungsfreien Sprachdienst mithilfe der Survivable Branch Appliance-Verbindung. ins Festnetz. Zweigstellenbenutzer, die eine Verbindung von zu Hause aus oder aus anderen Remotestandorten herstellen, können sich bei einem Registrierungsstellen Server an einem zentralen Standort registrieren, wenn die WAN-Verbindung zur Zweigstelle nicht verfügbar ist. Diese Benutzer verfügen über eine vollständige Unified Communications-Funktion, mit der Ausnahme, dass eingehende Anrufe an die Zweigstelle an die Voicemail weitergesendet werden. Wenn die WAN-Verbindung verfügbar wird, sollte die vollständige Funktionalität für Benutzer der Verzweigungs Website wiederhergestellt werden. Weder das Failover auf die Survivable Branch-Appliance noch die Wiederherstellung des Diensts erfordert das vorhanden sein eines IT-Administrators.

Skype for Business Server unterstützt bis zu zwei Survivable-Branch-Appliances an einer Zweigstelle.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Übersicht über Survivable Branch Appliance-Bereitstellung

Die Survivable Branch Appliance wird von Herstellern von Originalgeräten in Partnerschaft mit Microsoft hergestellt und in deren Auftrag von Wert Schöpfungs Händlern bereitgestellt. Diese Bereitstellung sollte erst erfolgen, nachdem Skype for Business Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit der Zweigstelle vorhanden ist und die Benutzer von Zweigstellenbenutzern für Enterprise-VoIP aktiviert sind.

Ausführliche Informationen zu diesen Phasen finden Sie unter Bereitstelleneiner überlebensfähigen [Branch-Appliance oder eines Überlebenden Servers](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) in der Bereitstellungsdokumentation.

|**Phase**|**Schritte**|**Benutzerrechte**|
|:-----|:-----|:-----|
|Einrichten von Active Directory-Domänendiensten für die Survivable Branch Appliance  <br/> |**Auf der zentralen Website:** <br/>  Erstellen Sie ein Domänenbenutzerkonto (oder eine Unternehmensidentität) für den Techniker, der die Survivable Branch-Appliance auf der Zweigstelle installieren und aktivieren wird. <br/>  Erstellen Sie ein Computerkonto (mit dem entsprechenden vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN)) für Survivable Branch Appliance in den Active Directory-Domänendiensten. <br/>  Erstellen und veröffentlichen Sie im Topologie-Generator die Survivable Branch-Appliance. <br/> |Das Techniker Benutzerkonto muss ein Mitglied von RTCUniversalSBATechnicians sein. Die Survivable Branch-Appliance muss zur RTCSBAUniversalServices-Gruppe gehören, die automatisch erfolgt, wenn Sie den Topology Builder verwenden.  <br/> |
|Installieren Sie die Survivable Branch-Appliance, und aktivieren Sie Sie.  <br/> |**Auf der Zweigstelle:** <br/>  Verbinden Sie die Survivable Branch-Appliance mit einem Ethernet-Port und einem PSTN-Anschluss. <br/>  Starten Sie die Survivable Branch-Appliance. <br/>  Nehmen Sie an der Überlebenden Branch-Appliance mit dem Domänenbenutzerkonto Teil, das für die Survivable Branch-Appliance am zentralen Standort erstellt wurde. Legen Sie den FQDN und die IP-Adresse so ein, dass er dem FQDN entspricht, der im Computerkonto erstellt wurde. <br/>  Konfigurieren Sie die Survivable Branch-Appliance mithilfe der OEM-Benutzeroberfläche. <br/>  Testen Sie die PSTN-Konnektivität. <br/> |Das Techniker Benutzerkonto muss ein Mitglied von RTCUniversalSBATechnicians sein.  <br/> |

#### <a name="survivable-branch-server-details"></a>Informationen zu Überlebenden Verzweigungs Servern

Erstellen Sie im Topologie-Generator die Verzweigungs Website, fügen Sie den Überlebenden Verzweigungs Server zu dieser Website hinzu, und führen Sie dann den Skype for Business Server-Bereitstellungs-Assistenten auf dem Computer aus, auf dem Sie die Rolle installieren möchten.

### <a name="branch-site-resiliency-requirements"></a>Anforderungen an die Elastizität der Zweigstelle

In diesem Thema finden Sie Informationen dazu, wie Sie Benutzer auf die Ausfallsicherheit von Zweigstellen und Voicemail vorbereiten sowie die entsprechenden Hardware-und Softwareanforderungen angeben.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Vorbereiten von Verzweigungs Benutzern für die Stabilität des Zweig Standorts

Bereiten Sie die Benutzer auf die Ausfallsicherheit von Zweigstellen vor, indem Sie deren Registrierungspool als Survivable Branch Appliance (SBA) oder Survivable Branch Server festlegen.

#### <a name="registrar-assignments-for-branch-users"></a>Registrierungsstellen Zuweisungen für Verzweigungs Benutzer

Unabhängig davon, welche Lösung für eine Zweigstellen-Ausfallsicherheit Sie wählen, müssen Sie jedem Benutzer eine primäre Registrierungsstelle zuweisen. Benutzer von Verzweigungs Websites sollten sich immer bei der Registrierungsstelle an der Zweigstelle anmelden, und zwar unabhängig davon, ob sich die Registrierungsstelle in der Survivable Branch-Appliance, dem Überlebenden Branch-Server oder einer eigenständigen Skype for Business Server-Standard-oder Enterprise-Edition befindet. Server. Ein DNS-Service-Ressourceneintrag (Domain Name System) ist erforderlich, damit ein Client seinen Registrierungspool ermitteln kann. Wenn die Survivable Branch-Appliance nicht mehr zur Verfügung steht, finden die Zweigstellenclients automatisch die Sicherungs Registrierungsstelle.

Wenn eine Verzweigungs Website nicht über einen DNS-Server verfügt, gibt es zwei alternative Methoden zum Konfigurieren der Ermittlung der Survivable Branch-Appliance oder des Survivable Branch-Servers:

- Konfigurieren Sie die DHCP-Option 120 auf dem DHCP-Server (Dynamic Host Configuration Protocol) der Zweigstelle so, dass Sie auf den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) der Survivable Branch Appliance oder des Survivable Branch-Servers verweist.

- Konfigurieren Sie die Survivable Branch-Appliance oder den Survivable Branch-Server, um auf DHCP 120-Abfragen zu reagieren.

#### <a name="voice-routing-for-branch-users"></a>VoIP-Routing für Branch-Benutzer

Wir empfehlen, dass Sie eine separate VoIP-Richtlinie auf Benutzerebene für Benutzer in einer Zweigstelle erstellen. Diese Richtlinie sollte eine primäre Route umfassen, die die Survivable Branch Appliance oder das Branch Server-Gateway verwendet, und mindestens eine Sicherungs Route, die einen trunk mit einem PSTN-Gateway (Public Switched Telephone Network) am zentralen Standort verwendet. Wenn die primäre Route nicht verfügbar ist, wird stattdessen die Sicherungs Route verwendet, die mindestens ein zentrales Standort Gateway verwendet. Auf diese Weise ist die VoIP-Richtlinie des Benutzers unabhängig davon, wo ein Benutzer registriert ist, auf der Zweigstellen-Registrierungsstelle oder dem sicherungsregistrierungspool am zentralen Standort immer gültig. Dies ist eine wichtige Überlegung für Failover-Szenarien. Wenn Sie beispielsweise die Survivable Branch-Appliance umbenennen oder die Survivable Branch-Appliance neu konfigurieren müssen, um eine Verbindung mit einem sicherungsregistrierungspool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für die Dauer an den zentralen Standort verschieben. (Einzelheiten zum Umbenennen oder Neukonfigurieren einer Survivable Branch-Appliance finden Sie in [Anhang B: Verwalten einer Survivable Branch-Appliance](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine VoIP-Richtlinien auf Benutzerebene oder Wählpläne auf Benutzerebene haben und die Benutzer auf eine andere Website umgestellt werden, gelten die VoIP-Richtlinien auf Websiteebene und die Wählpläne auf Websiteebene des zentralen Standorts standardmäßig für die Benutzer und nicht für die Website VoIP-Richtlinien und Wählpläne auf Websiteebene. Wenn die VoIP-Richtlinien auf Websiteebene und die vom sicherungsregistrierungspool verwendeten Wählpläne auf Websiteebene auch für die Benutzer der Verzweigungs Website gelten können, treten in diesem Szenario keine Anrufe auf. Wenn beispielsweise Benutzer von einer Zweigstelle, die sich in Japan befindet, in einen zentralen Standort in Redmond verschoben werden, wird ein Wählplan mit Normalisierungsregeln, der + 1425 allen siebenstelligen anrufen vorangestellt wird, wahrscheinlich nicht geeignet sein, Anrufe für diese Benutzer angemessen zu übersetzen.

> [!IMPORTANT]
> Wenn Sie eine Zweigstellen-Backup-Route erstellen, empfehlen wir, dass Sie der Benutzerrichtlinie für Zweigniederlassungen zwei PSTN-Telefonnutzungsdatensätze hinzufügen und jedem eine separate Route zuweisen. Die erste oder primäre Route würde Anrufe an das Gateway weiterleiten, das dem SBA (Survivor Branch Appliance) oder Branch Server zugeordnet ist. die zweite oder Sicherungs-Route würde Anrufe an das Gateway an der zentralen Website weiterleiten. Bei der Weiterleitung von Anrufen versucht der SBA-oder Branch-Server alle Routen, die dem ersten PSTN-Verwendungsdaten Satz zugeordnet sind, bevor Sie den zweiten Verwendungsdaten Satz versuchen.

So stellen Sie sicher, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Branch-Gateway oder die Windows-Komponente der Survivable Branch Appliance-Website nicht verfügbar ist (Dies würde beispielsweise passieren, wenn die Survivable Branch Appliance oder Branch Gateway für die Wartung nicht zur Verfügung standen), erstellen Sie eine Failover-Route auf dem Gateway (oder arbeiten Sie mit Ihrem direkten nach innen Wähl-(DID-) Anbieter), um eingehende Anrufe an den sicherungsregistrierungspool am zentralen Standort umzuleiten. Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet. Stellen Sie sicher, dass die Route Zahlen übersetzt, um Sie dem PSTN-Gateway oder den akzeptierten Telefonnummernformaten anderer trunk-Peers zu entsprechen. Details zum Erstellen einer Failover-Route finden Sie unter [Konfigurieren einer Failover-Route](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Sie können auch Wählpläne auf Dienstebene für den trunk erstellen, der dem Gateway auf der Zweigstelle zugeordnet ist, um eingehende Anrufe zu normalisieren. Wenn Sie über zwei überlebensfähige Branch-Appliances an einer Zweigstelle verfügen, können Sie einen Wählplan auf Websiteebene für beide erstellen, es sei denn, es ist ein separater Service-Level-Plan erforderlich.

> [!NOTE]
> Zum berücksichtigen des Verbrauchs von Ressourcen für die zentrale Website durch alle Zweigstellenbenutzer, die auf die zentrale Website für Anwesenheit, Konferenz oder Failover angewiesen sind, empfehlen wir, dass Sie den jeweiligen Benutzer der Zweigstelle in Betracht ziehen, als ob der Benutzer bei der zentralen Website registriert wäre. Derzeit gibt es keine Beschränkungen für die Anzahl der Benutzer von Zweigstellen, einschließlich der Benutzer, die bei einer Survivable Branch-Appliance registriert sind.

Wir empfehlen außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Benutzern der Verzweigungs Website zuzuweisen. Ausführliche Informationen finden Sie unter [erstellen oder Ändern eines Wählplans in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) und [Erstellen der VoIP-Routing Richtlinie für Verzweigungs Benutzer](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) in der Bereitstellungsdokumentation.

#### <a name="routing-extension-numbers"></a>Durchwahlnummern für die Weiterleitung

Stellen Sie beim Vorbereiten von Wählplänen und VoIP-Richtlinien für Benutzer von Zweigstellen sicher, dass Sie Normalisierungsregeln und Übersetzungsregeln einbeziehen, die den Zeichenfolgen und dem Zahlenformat entsprechen, die im Attribut msRTCSIP (oder Linien-URI)-Attribut verwendet werden, damit Skype for Business-Anrufe aktiviert sind. zwischen den Benutzern der Verzweigungs Website und der zentralen Website werden Benutzer ordnungsgemäß weitergeleitet, insbesondere dann, wenn Anrufe über das PSTN umgeleitet werden müssen, weil die WAN-Verbindung nicht verfügbar ist. Darüber hinaus gibt es besondere Überlegungen für gewählte Nummern, die Durchwahlnummern enthalten, und nicht nur Telefonnummern.

Normalisierungsregeln und Übersetzungen, die mit Linien-URIs übereinstimmen, die eine Durchwahlnummer enthalten, ob ausschließlich oder zusätzlich zu einer vollständigen E. 164-Telefonnummer, haben zusätzliche Anforderungen. In diesem Abschnitt werden verschiedene Beispielszenarien zum Weiterleiten von Anrufen für Linien-URIs mit einer Durchwahlnummer beschrieben.

Wenn Ihre Organisation nicht über direkte Durchwahlnummern (DID) für einzelne Benutzer verfügt und der Leitungs-URI jedes Benutzers nur mit einer Durchwahlnummer konfiguriert ist, können interne Benutzer eine andere Rufnummer anrufen, indem Sie nur eine Durchwahlnummer wählen. Sie müssen jedoch Normalisierungsregeln konfigurieren, die für Anrufe von einem Zweigstellenbenutzer an einen zentralen Websitebenutzer gelten können, die den Durchwahlnummern entsprechen.

In einem Szenario, in dem die WAN-Verbindung zwischen einer Verzweigungs Website und einem zentralen Standort verfügbar ist, ist es für Anrufe von Zweigstellenbenutzern an zentrale Websitebenutzer nicht erforderlich, dass die übereinstimmende Normalisierungsregel die Nummer übersetzt, da der Anruf nicht über das PSTN weitergeleitet wird. Beispiel:

|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Fünfstellige Zahlen werden nicht übersetzt  <br/> |^ (\d{5}) $  <br/> |$1  <br/> |10001 wird nicht übersetzt  <br/> |

Sie müssen auch Durchwahlnummern für bestimmte Szenarien berücksichtigen, beispielsweise, wenn die WAN-Verbindung zwischen einer Verzweigungs Website und einem zentralen Standort nicht verfügbar ist und ein Anruf von einer Zweigstelle über das PSTN weitergeleitet werden muss. Wenn ein Zweigstellenbenutzer bei einem WAN-Ausfall nur einen zentralen Websitebenutzer anruft, indem er die Durchwahl des zentralen Websitebenutzers anwählt, muss eine ausgehende Übersetzungsregel vorhanden sein, mit der die vollständige Telefonnummer des zentralen Websitebenutzers hinzugefügt wird. Wenn der Linien-URI des Benutzers die vollständige Telefonnummer Ihres Unternehmens und die eindeutige Durchwahlnummer des Benutzers anstelle einer vollständigen Telefonnummer enthält, die für den Benutzer eindeutig ist, müssen Sie über eine Regel für ausgehende Übersetzungen verfügen, die stattdessen die vollständige Telefonnummer Ihrer Organisation hinzufügt. . Beispiel:

|**Beschreibung**|**Übereinstimmungsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Übersetzt fünfstellige Zahlen in die Telefonnummer und Durchwahl eines Benutzers  <br/> |^ (\d{5}) $  <br/> |+ 14255550123; EXT = $1  <br/> |10001 wird in + 14255550123; ext = 10001  <br/> |
|Übersetzt fünfstellige Zahlen in die Telefonnummer Ihrer Organisation und die Durchwahl des Benutzers.  <br/> |^ (\d{5}) $  <br/> |+ 14255550100 übersetzt.; ext = $1  <br/> |10001 wird in + 14255550100 übersetzt.; ext = 10001  <br/> |

Wenn der trunk-Peer, der das Umleiten an das PSTN übernimmt, keine Durchwahlnummern unterstützt, muss in diesem Szenario auch die ausgehende Übersetzungsregel die Durchwahlnummer entfernen. Beispiel:

|**Beschreibung**|**Übereinstimmungsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Entfernt die Durchwahl von Telefonnummern mit Erweiterungen  <br/> |^\+(\d\*); ext = (\d\*) $  <br/> |+$1  <br/> |+ 14255550123; ext = 10001 wird in + 14255550123 übersetzt  <br/> |

Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, wenn Ihre Organisation keine DID-Nummern für einzelne Benutzer konfiguriert hat und der Leitungs-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers enthält, müssen Sie Ihre der Telefonnummern-URI der Organisation mit einer Nummer, die über das trunk-Peer-oder PSTN-Gateway auf der Zweigstelle erreichbar ist. Darüber hinaus müssen Sie den Telefonnummern-URI Ihrer Organisation so konfigurieren, dass seine eigene eindeutige Durchwahl für die Weiterleitung von Anrufen an diese Nummer hinzugefügt wird.

#### <a name="preparing-for-voice-mail-survivability"></a>Vorbereiten der Überlebensfähigkeit von Voicemail

Exchange Unified Messaging (um) wird normalerweise nur an einem zentralen Standort und nicht an Zweigstellen installiert. Ein Anrufer sollte in der Lage sein, eine Voicemail-Nachricht zu hinterlassen, auch wenn die WAN-Verbindung zwischen der Zweigstelle und dem zentralen Standort nicht verfügbar ist. Daher erfordert die Konfiguration des Linien-URIs für die Telefonnummer der automatischen Exchange UM-Telefonzentrale, die Voicemail für Zweigstellenbenutzer bereitstellt, besondere Überlegungen, zusätzlich zu den VoIP-Richtlinien, dem Wählplan und den Normalisierungsregeln, die für diese Voicemail gelten. Anzahl.

Überlebensfähige Branch Appliances (SBAS) und überlebensfähige Verzweigungs Server sorgen für die Überlebensfähigkeit von Voicemail für Branch-Benutzer bei einem WAN-Ausfall. Wenn Sie eine Survivable Branch-Appliance oder einen Survivable Branch-Server verwenden und das WAN nicht mehr zur Verfügung steht, leitet der SBA-oder Survivable Branch-Server unbeantwortete Anrufe über das PSTN an Exchange um am zentralen Standort weiter. Mit einem SBA-oder Survivable-Branch-Server können Benutzer während eines WAN-Ausfalls auch Voicemail-Nachrichten über das PSTN abrufen. Schließlich werden bei einem WAN-Ausfall die überlebensfähige Branch-Appliance oder der Survivable Branch-Server in Warteschlangen verpasste Benachrichtigungen gesetzt und dann auf den Exchange um-Server hochgeladen, wenn das WAN wiederhergestellt wird. Stellen Sie sicher, dass Sie einen Eintrag für den FQDN des zentralen Website Pools und einen Eintrag für den FQDN des Edge-Servers in der Hosts-Datei auf dem Überlebenden Verzweigungs Server hinzufügen, um sicherzustellen, dass das neurouting von Voicemail widerstandsfähig ist. Andernfalls kann die DNS-Auflösung ein Timeout aufweisen, wenn Sie nicht über einen DNS-Server auf der Zweigstelle verfügen.

Wir empfehlen die folgenden Konfigurationen für die Überlebensfähigkeit von Voicemail für Branch Site-Benutzer:

- Ein Microsoft Exchange-Administrator sollte die Exchange um-automatische Telefonzentrale (AA) so konfigurieren, dass nur Nachrichten akzeptiert werden. Mit dieser Konfiguration werden alle anderen generischen Funktionen, wie etwa die Übertragung an einen Benutzer oder die Übertragung an einen Operator, deaktiviert und die AA auf die Annahme von Nachrichten beschränkt. Alternativ kann der Exchange-Administrator einen generischen AA oder AA-Benutzerdefiniert verwenden, um den Anruf an einen Operator weiterzuleiten.

- Der Skype for Business Server-Administrator sollte die AA-Telefonnummer übernehmen und diese Telefonnummer in den Einstellungen für die Voicemail-Umleitungseinstellungen für die Survivable Branch-Appliance oder den Branch-Server als die Nummer der **automatischen Exchange UM-Telefonzentrale** verwenden.

- Der Skype for Business Server-Administrator sollte die Telefonnummer für den Exchange um-Teilnehmerzugriff erhalten und diese Nummer als **Teilnehmerzugriffs** Nummer in den Einstellungen für die Voicemail-Umleitung für die Survivable Branch Appliance oder den Survivable Branch-Server verwenden.

- Der Skype for Business Server-Administrator sollte Exchange um so konfigurieren, dass nur ein Wählplan allen Verzweigungs Benutzern zugeordnet ist, die bei einem WAN-Ausfall Zugriff auf Voicemail benötigen.

- Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an das Exchange Unified Messaging (um)-Voicemail-Postfach des Benutzers weitergeleitet werden, jedoch nur, wenn die auf den Anruf angewendete VoIP-Richtlinie eine eindeutige Voicemail-Telefonnummer angibt und keine Durchwahl enthält. Anzahl.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Hardware-und Software Anforderungen für die Stabilität des Zweigstellen Standorts

Die Hardware-und Softwareanforderungen variieren je nach ihrer Resilienz-Lösung.

#### <a name="requirements-for-survivable-branch-appliances"></a>Voraussetzungen für Survivable Branch Appliances

Die erforderliche Hardware und Software ist in der Survivable Branch-Appliance integriert. Wir empfehlen jedoch auch, dass jede Zweigstelle einen DHCP-Server bereitstellt, um Client-IP-Adressen abzurufen. Wenn die DHCP-Lease abläuft, gibt es andernfalls keine IP-Konnektivität für Clients.

Wenn sich die Enterprise-DNS-Server nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung mit Ihnen herstellen, und daher schlägt die Skype for Business Server-Ermittlung, die DNS-SRV (Service (SRV)-Ressourceneintrag verwendet) fehl. Damit Sie bei einem WAN-Ausfall ein schnelles erneutes Routing sicherstellen können, müssen DNS-Einträge auf der Zweigstelle zwischengespeichert werden. Aktivieren Sie die DNS-Zwischenspeicherung, wenn der Verzweigungs Router dies unterstützt. Oder Sie können einen DNS-Server in der Verzweigung bereitstellen. Hierbei kann es sich um einen eigenständigen Server oder eine Version der Survivable Branch-Appliance handeln, die DNS-Funktionen unterstützt. Weitere Informationen erhalten Sie von Ihrem Überlebenden Branch Appliance-Anbieter.

> [!NOTE]
> Es ist nicht erforderlich, einen Domänencontroller an einer Zweigstelle zu haben. Die Survivable Branch-Appliance authentifiziert Clients mithilfe eines speziellen Zertifikats, das der Client als Antwort auf die Zertifikatanforderung des Clients sendet, wenn er sich anmeldet.

Skype for Business-Clients können den Skype for Business-Server mithilfe der DHCP-Option 120 (SIP-Registrar-Option) entdecken. Dies kann auf eine von zwei Arten konfiguriert werden:

- Konfigurieren Sie den DHCP-Server auf der Verzweigungs Website, um auf DHCP 120-Abfragen zu antworten, die den FQDN der Registrierungsstelle auf der Survivable Branch-Appliance oder dem Überlebenden Branch-Server zurückgeben.

- Aktivieren Sie Skype for Business Server DHCP. Wenn diese Option aktiviert ist, reagiert die Skype for Business Server-Registrierungsstelle auf DHCP-Option 120-Abfragen. Beachten Sie, dass die Registrierungsstelle nicht auf DHCP-Abfragen anders als DHCP-Optionen 120 reagiert.

Darüber hinaus sollten für größere Zweigstellen, die über mehrere Subnetze verfügen, DHCP-Relay-Agents aktiviert werden, um DHCP-Option 120-Abfragen an den DHCP-Server (Konfiguration 1) oder an die Registrierungsstelle weiterzuleiten (Konfiguration 2).

Schließlich müssen die Benutzer der Zweigstelle für Enterprise-VoIP konfiguriert und mit einem geeigneten Unified Communications-Endpunkt bereitgestellt werden.

#### <a name="requirements-for-survivable-branch-servers"></a>Voraussetzungen für Überlebende Zweigstellenserver

Die Anforderungen für überlebensfähige Zweigstellenserver sind identisch mit den Anforderungen für einen Front-End-Server. Weitere Einzelheiten finden Sie in [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Voraussetzungen für die vollständige Bereitstellung von Skype for Business Server-Zweigstellen

Ausführliche Informationen finden Sie unter [Server Anforderungen für Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) in der Planungsdokumentation.

### <a name="example-configuring-a-failover-route"></a>Beispiel: Konfigurieren einer Failover-Route

 Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failover-Route für die Verwendung definieren kann, wenn der Dallas-GW1 für die Wartung ausgefallen ist oder anderweitig nicht verfügbar ist. Die folgenden Tabellen veranschaulichen die erforderliche Konfigurationsänderung.

**Tabelle 1 Benutzerrichtlinien**

|**Benutzerrichtlinie**|**Telefonnutzung**|
|:-----|:-----|
|Standardanrufrichtlinie  <br/> |Local  <br/> GlobalPSTNHopoff  <br/> |
|Lokale Redmond-Richtlinie  <br/> |RedmondLocal  <br/> |
|Dallas-Anrufrichtlinie  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabelle 2. Routen**


| **Routenname**             | **Nummernmuster** | **Telefonnutzung**         | **Stamm**                                 | **Gateway**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Lokale Redmond-Route  <br/> | ^\+1 (425           | 206                     | 253) (\d{7}) $  <br/>                       | Local  <br/> RedmondLocal  <br/>                |
| Lokale Route für Dallas  <br/>  | ^\+1 (972           | 214                     | 469) (\d{7}) $  <br/>                       | Local  <br/>                                    |
| Universelle Route  <br/>     | ^\+? (\d\*) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Rot-GW1  <br/> Rot-GW2  <br/> Dallas-GW1  <br/> |
| Route für Dallas-Benutzer  <br/>  | ^\+? (\d\*) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

In Tabelle 1 wird nach der DallasUsers-Telefonnutzung in der Dallas-Anrufrichtlinie eine Telefonverwendung von GlobalPSTNHopoff hinzugefügt. Dies ermöglicht es anrufen mit der Dallas-Anrufrichtlinie, Routen zu verwenden, die für die GlobalPSTNHopoff-Telefonverwendung konfiguriert sind, wenn eine Route für die DallasUsers-Telefonnutzung nicht verfügbar ist.


