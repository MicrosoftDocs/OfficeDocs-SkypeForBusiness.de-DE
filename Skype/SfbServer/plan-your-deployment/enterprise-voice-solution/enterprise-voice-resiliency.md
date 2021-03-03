---
title: Planen von Enterprise-VoIP A0 in Skype for Business Server
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
ms.assetid: b3671dcb-6a8b-4a06-84da-0c8837b35099
description: Erfahren Sie, wie Sie die Ausfallsicherheit von Sprachnachrichten in Skype for Business Server Enterprise-VoIP, sowohl an zentralen Standorten als auch an Zweigstellenstandorten unterstützen. Zu den Optionen für Zweigstellenstandorte gehört die Bereitstellung von Survivable Branch Appliances oder Survivable Branch Servers.
ms.openlocfilehash: d2b3efe36470e11d901b9b298cf955a04dd40766
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825755"
---
# <a name="plan-for-enterprise-voice-resiliency-in-skype-for-business-server"></a>Planen von Enterprise-VoIP A0 in Skype for Business Server

Erfahren Sie, wie Sie die Ausfallsicherheit von Sprachnachrichten in Skype for Business Server Enterprise-VoIP, sowohl an zentralen Standorten als auch an Zweigstellenstandorten unterstützen. Zu den Optionen für Zweigstellenstandorte gehört die Bereitstellung von Survivable Branch Appliances oder Survivable Branch Servers.

Die Ausfallsicherheit von Sprachnachrichten bezieht sich auf die Möglichkeit, dass Benutzer weiterhin Anrufe führen und empfangen können, wenn ein zentraler Standort, an dem Skype for Business Server hostet, nicht verfügbar ist, sei es durch einen Wan-Fehler (Wide Area Network) oder eine andere Ursache. Wenn ein zentraler Standort ausfällt, Enterprise-VoIP der Dienst durch ein nahtloses Failover zu einem Sicherungsstandort unterbrechungsfrei fortgesetzt werden. Im Falle eines WAN-Ausfalls müssen Zweigstellenanrufe an ein lokales PSTN-Gateway umgeleitet werden. In diesem Abschnitt wird die Planung der Ausfallsicherheit von Sprachnachrichten im Falle eines Ausfalls am zentralen Standort oder im WAN erläutert.

## <a name="central-site-resiliency"></a>Ausfallsicherheit für zentrale Standort

Immer mehr Unternehmen verfügen über mehrere Standorte, die weltweit verteilt sind. Die Verwaltung der Notrufdienste, der Zugriff auf das Helpdesk und die Möglichkeit, wichtige Geschäftsaufgaben auszuführen, wenn ein zentraler Standort außer Betrieb ist, ist für jede lösung zur Enterprise-VoIP unerlässlich. Wenn ein zentraler Standort nicht länger verfügbar ist, muss Folgendes sichergestellt werden:

- Bereitstellung von VoIP-Failover.

- Benutzer, die sich normalerweise beim Front-End-Pool am zentralen Standort registrieren, müssen sich bei einem alternativen Front-End-Pool registrieren können. Dazu können Sie mehrere DNS-SRV-Einträge erstellen, von denen jeder in einen Director- oder Front-End-Pool an jedem ihrer zentralen Standorte aufgelöst wird. Sie können die Priorität und Gewichtung der SRV-Einträge so anpassen, dass Benutzer, die von diesem zentralen Standort bedient werden, den entsprechenden Director und Front-End-Pool vor denen in anderen SRV-Einträgen erhalten.

- Eingehende und ausgehende Anrufe von Benutzern an anderen Standorten müssen an das Telefonfestnetz umgeleitet werden.

In diesem Thema wird die empfohlene Lösung zum Sicherstellen der VoIP-Ausfallsicherheit für einen zentralen Standort beschrieben.

### <a name="architecture-and-topology"></a>Architektur und Topologie

Die Planung der Ausfallsicherheit von Sprachfunktionen an einem zentralen Standort erfordert ein grundlegendes Verständnis der zentralen Rolle der Skype for Business Server-Registrierungsstelle beim Aktivieren des Sprachfailovers. Die Skype for Business Server-Registrierung ist ein Dienst, der die Clientregistrierung und -authentifizierung ermöglicht und Routingdienste bietet. Sie wird auf allen Standard Edition-Servern, Front-End-Servern, Director- oder Survivable Branch Appliances ausgeführt. Ein Registrierungsstellenpool besteht aus Registrierungsstellendiensten, die im Front-End-Pool ausgeführt werden und sich am selben Standort befindet. Ein Skype for Business-Client ermittelt den Front-End-Pool über den folgenden Ermittlungsmechanismus:

1. DNS-SRV-Eintrag

2. AutoErmittlungswebdienst

3. DHCP-Option 120

Nachdem der Skype for Business-Client eine Verbindung mit dem Front-End-Pool hergestellt hat, wird er vom Lastenausgleich an einen der Front-End-Server im Pool geleitet. Dieser Front-End-Server leitet den Client wiederum zu einer bevorzugten Registrierungsstelle im Pool um.

Jeder benutzer, der für Enterprise-VoIP aktiviert ist, wird einem bestimmten Registrierungsstellenpool zugewiesen, der zum primären Registrierungsstellenpool dieses Benutzers wird. Typischerweise verwenden Hunderte oder Tausende Benutzer an einem Standort einen einzigen primären Registrierungspool gemeinsam. Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer als Benutzer betrachten, der für den zentralen Standort registriert ist. Derzeit gibt es keine Beschränkungen für die Anzahl der Zweigstellenbenutzer, einschließlich der Benutzer, die bei einer Survivable Branch Appliance registriert sind.

Zum Gewährleisten von VoIP-Ausfallsicherheit beim Ausfall eines zentralen Standorts muss der primäre Registrierungspool über einen einzelnen designierten Sicherungsregistrierungspool verfügen, der sich an einem anderen Standort befindet. Die Sicherung kann mithilfe von Ausfallsicherheitseinstellungen des Topologie-Generators konfiguriert werden. Vorausgesetzt, dass eine ausfallsichere WAN-Leitung zwischen den beiden Standorten besteht, werden Benutzer des nicht mehr verfügbaren primären Registrierungspools automatisch an den Sicherungsregistrierungspool geleitet.

Der Such- und Registrierungsprozess des Clients umfasst die folgenden Schritte:

1. Ein Client ermittelt Skype for Business Server über DNS-SRV-Einträge. In Skype for Business Server können DNS-SRV-Einträge so konfiguriert werden, dass mehr als ein FQDN an die DNS-SRV-Abfrage zurückgegeben wird. Beispiel: Wenn das Unternehmen Contoso über drei zentrale Standorte (in Nordamerika, Europa und im asiatisch-pazifischen Raum) sowie einen Director-Pool an jedem zentralen Standort verfügt, können DNS-SRV-Einträge auf die vollqualifizierten Domänennamen der Director-Pools an jedem dieser drei Standorte verweisen. Solange der Directorpool an einem der Standorte verfügbar ist, kann der Client eine Verbindung mit dem ersten Hop von Skype for Business Server herstellen.

    > [!NOTE]
    > Die Verwendung eines Directorpools ist optional. Stattdessen kann ein Front-End-Pool verwendet werden.

2. Der Directorpool informiert den Skype for Business-Client über den primären Registrierungspool und den Sicherungsregistrierungspool des Benutzers.

3. Der Skype for Business-Client versucht, zuerst eine Verbindung mit dem primären Registrierungsstellenpool des Benutzers herzustellen. Wenn der primäre Registrierungspool verfügbar ist, wird die Registrierung akzeptiert. Wenn der primäre Registrierungsstellenpool nicht verfügbar ist, versucht der Skype for Business-Client, eine Verbindung mit dem Sicherungsregistrierungspool herzustellen. Wenn der Sicherungsregistrierungspool verfügbar ist und festgestellt hat, dass der primäre Registrierungspool des Benutzers nicht verfügbar ist (durch Erkennen eines fehlenden Takts für ein angegebenes Failoverintervall), akzeptiert der Sicherungsregistrierungspool die Registrierung des Benutzers. Nachdem die Sicherungsregistrierung erkannt hat, dass die primäre Registrierung wieder verfügbar ist, leitet der Sicherungsregistrierungspool Failoverclients an ihren primären Pool um.

### <a name="requirements-and-recommendations"></a>Anforderungen und Empfehlungen

Die folgenden Anforderungen und Empfehlungen für die Implementierung von VoIP-Ausfallsicherheit an einem zentralen Standort gelten für die meisten Organisationen:

- Die Standorte, an denen sich der primäre und der Sicherungsregistrierungspool befinden, sollten über eine ausfallsichere WAN-Leitung verbunden sein.

- Jeder zentrale Standort muss über einen Registrierungspool mit mindestens einer Registrierung verfügen.

- Jeder Registrierungsstellenpool muss einen Lastenausgleich mithilfe von DNS-Lastenausgleich, Hardwaregerät zum Lastenausgleich oder beides haben. Ausführliche Informationen zum Planen ihrer Lastenausgleichskonfiguration finden Sie unter [Lastenausgleichsanforderungen für Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md).

- Jeder Benutzer muss mithilfe des Cmdlets **"set-CsUser"** der Skype for Business Server-Verwaltungsshell oder der Skype for Business Server-Systemsteuerung einem primären Registrierungsstellenpool zugewiesen werden.

- Der primäre Registrierungspool muss über einen einzelnen Sicherungsregistrierungspool an einem anderen zentralen Standort verfügen.

- Für den primären Registrierungspool muss ein Failover auf den Sicherungsregistrierungspool konfiguriert sein. In der Standardeinstellung ist für die primäre Registrierung ein Failover auf den Sicherungsregistrierungspool nach 300 Sekunden festgelegt. Sie können dieses Intervall mithilfe des Skype for Business Server-Topologie-Generators ändern.

- Konfigurieren sie eine Failoverroute. Geben Sie beim Konfigurieren der Route ein Gateway an, das sich an einem anderen Standort befindet als das in der primären Route angegebene Gateway.

- Wenn der zentrale Standort Ihren primären Verwaltungsserver enthielt und der Standort wahrscheinlich über einen längeren Zeitraum aus ist, müssen Sie die Verwaltungstools am Sicherungsstandort neu installieren. Andernfalls können Sie keine Verwaltungseinstellungen ändern.

### <a name="dependencies"></a>Abhängigkeiten

Skype for Business Server hängt von der folgenden Infrastruktur und den folgenden Softwarekomponenten ab, um ausfallsicher zu sein:

|**Komponente** <br/> |**Funktional** <br/> |
|:-----|:-----|
|DNS  <br/> |Auflösen von SRV- und A-Einträgen für Konnektivität zwischen Servern bzw. zwischen Servern und Clients  <br/> |
|Exchange und Exchange-Webdienste  <br/> |Speicherung von Kontakten, Kalenderdaten  <br/> |
|Exchange Unified Messaging und Exchange-Webdienste  <br/> |Anrufprotokolle, Voicemailliste, Voicemail  <br/> |
|DHCP Options 120  <br/> |Wenn DNS-SRV nicht verfügbar ist, versucht der Client, DHCP Option 120 für die Suche nach der Registrierung zu verwenden. Damit dies funktioniert, muss entweder ein DHCP-Server konfiguriert oder Skype for Business Server DHCP aktiviert sein.  <br/> |

### <a name="survivable-voice-features"></a>VoIP-Funktionen mit Ausfallsicherheit

Wenn die vorstehenden Anforderungen und Empfehlungen implementiert wurden, werden die folgenden VoIP-Funktionen vom Sicherungsregistrierungspool bereitgestellt:

- Ausgehende PSTN-Anrufe

- Eingehende PSTN-Anrufe, wenn der Telefoniedienstanbieter das Failover auf einen Sicherungsstandort unterstützt

- Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden

- Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe

- Instant Messaging mit zwei Teilnehmern sowie Freigabe von Audio- und Videoinhalten zwischen Benutzern am selben Standort

- Anrufweiterleitung, gleichzeitiges Klingeln von Endgeräten, Anrufdelegierung und Teamanrufdienste (jedoch nur, wenn beide Teilnehmer für die Anrufdelegierung oder alle Teammitglieder am selben Standort konfiguriert sind).

- Vorhandene Telefone und Clients sind weiterhin funktionsfähig.

- Aufzeichnung von Kommunikationsdatensätzen (KDS)

- Authentifizierung und Autorisierung

Abhängig von ihrer Konfiguration können die folgenden VoIP-Funktionen beim Ausfall eines primären zentralen Standorts verwendet werden oder nicht:

- Hinterlassen und Abrufen von Voicemail

    Wenn Exchange UM beim Ausfall des primären zentralen Standorts verfügbar sein soll, führen Sie einen der folgenden Schritte aus:

  - Ändern Sie DNS-SRV-Einträge so, dass die Exchange UM-Server am zentralen Standort auf Exchange UM-Sicherungsserver an einem anderen Standort verweisen.

  - Konfigurieren Sie die Exchange -UM-Wähleinstellungen der einzelnen Benutzer so, dass sie Exchange -UM-Server sowohl am zentralen Standort als auch am Sicherungsstandort enthalten, die Exchange -UM-Sicherungsserver jedoch als deaktiviert festlegen. Wenn der primäre Standort nicht mehr verfügbar ist, muss der Exchange-Administrator die Exchange -UM-Server am Sicherungsstandort als aktiviert kennzeichnen.

    Wenn keine der oben genannten Lösungen möglich ist, ist Exchange UM für den Fall, dass der zentrale Standort nicht mehr verfügbar ist, nicht verfügbar.

- Alle Konferenztypen

    Ein Benutzer, der zu einem Sicherungsstandort wechselt, kann an einer Konferenz teilnehmen, die von einem Organisator erstellt oder gehostet wird, dessen Pool verfügbar ist, aber keine Konferenz in seinem eigenen primären Pool erstellen oder hosten kann, der nicht mehr verfügbar ist. Ebenso können andere Benutzer nicht an Konferenzen teilnehmen, die im primären Pool des betroffenen Benutzers gehostet werden.

Die folgenden VoIP-Funktionen können nicht verwendet werden, wenn ein primärer zentraler Standort ausfällt:

- Automatische Konferenzzentrale

- Anwesenheits- und DNS-basiertes Routing

- Aktualisieren der Einstellungen für die Anrufweiterleitung

- Reaktionsgruppendienst und Parken von Anrufen

- Bereitstellen neuer Telefone und Clients

- Adressbuchwebsuche

## <a name="branch-site-resiliency"></a>Ausfallsicherheit für Zweigstellenstandorte

Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen möchten, d. Enterprise-VoIP hohe Verfügbarkeit, haben Sie drei Möglichkeiten:

- Survivable Branch Appliance

- Survivable Branch Server

- Eine vollständige Skype for Business Server-Bereitstellung am Zweigstellenstandort

Dieses Handbuch unterstützt Sie bei der Auswertung, welche Ausfallsicherheitslösung am besten für Ihre Organisation geeignet ist. Zudem erfahren Sie, welche PSTN-Anbindung für Ihre Ausfallsicherheitslösung verwendet werden sollte. Darüber hinaus erhalten Sie Unterstützung bei der Vorbereitung auf die Bereitstellung der gewählten Lösung, indem die Voraussetzungen und andere Planungsaspekte erläutert werden.

### <a name="branch-site-resiliency-features"></a>Ausfallsicherheitsfunktionen für Zweigstellenstandorte

Wenn Sie Ausfallsicherheit für Zweigstellenstandorte bereitstellen, wenn die WAN-Verbindung eines Zweigstellenstandorts zu einem zentralen Standort ausfällt oder wenn der zentrale Standort nicht erreichbar ist, sollten die folgenden Sprachfunktionen weiterhin verfügbar sein:

- Eingehende und ausgehende PSTN-Anrufe (Public Switched Telephone Network)

- Enterprise-Anrufe zwischen Benutzern, die sich entweder am selben oder an zwei verschiedenen Standorten befinden

- Grundlegende Anrufbehandlung, einschließlich Halten, Wiederaufnahme und Übergabe

- Instant Messaging mit zwei Teilnehmern

- Anruf weiterleitung, gleichzeitiges Klingeln von Endpunkten, Anrufdelegierung und Teamanrufdienste, aber nur, wenn der Delegator und die Stellvertretung (z. B. ein Vorgesetzter und der Administrator des Managers) oder alle Teammitglieder am selben Standort konfiguriert sind

- Kommunikationsdatensätze (KDS)

- PSTN-Einwahlkonferenzen mit automatischer Konferenzzentrale

- Voicemailfunktionen, sofern Sie Einstellungen für die Voicemailumleitung konfigurieren.

- Benutzerauthentifizierung und -autorisierung

Die folgenden Funktionen sind nur verfügbar, wenn Ihre Ausfallsicherheitslösung eine umfassende Skype for Business Server-Bereitstellung am Zweigstellenstandort ist:

- IM-, Web- und A/V-Konferenzen

- Anwesenheits- und DND-basiertes Routing (Telefon soll bei eingehenden Anrufen an Ihre Durchwahlnummern mit dem Status "Nicht stören" nicht klingen)

- Aktualisieren der Einstellungen für die Anrufweiterleitung

- Reaktiongruppenanwendung und Anwendung zum Parken von Anrufen

- Bereitstellen neuer Telefone und Clients, jedoch nur, wenn active Directory Domain Services am Zweigstellenstandort vorhanden sind.

- 9-1-1 (erweitert) (E9-1-1)

    Wenn E9-1-1 bereitgestellt wird und der SIP-Trunk am zentralen Standort nicht verfügbar ist, weil die WAN-Verbindung aus ist, werden E9-1-1-Anrufe von der Survivable Branch Appliance an das lokale Zweigstellengateway geroutet. Um diese Funktion zu aktivieren, sollten die Voicerichtlinien der Zweigstellenbenutzer Anrufe an das lokale Gateway im Falle eines WAN-Ausfalls umstellen.

> [!NOTE]
> SBA (Survivable Branch Office) wird für XMPP nicht unterstützt. Benutzer, die in einer SBA-Konfiguration gespeichert sind, können keine IMs senden oder anwesenheitsinformationen mit XMPP-Kontakten sehen.

### <a name="branch-site-resiliency-solutions"></a>Ausfallsicherheitslösungen für Zweigstellenstandorte

Das Bereitstellen von Ausfallsicherheit für Zweigstellenstandorte bietet offensichtliche Vorteile. Insbesondere wenn die Verbindung zum zentralen Standort verloren geht, verfügen Zweigstellenbenutzer weiterhin über Enterprise-VoIP und Voicemail (wenn Sie Einstellungen für die Voicemailumleitung konfigurieren). Für Standorte mit weniger als 25 Benutzern ist die Implementierung einer Ausfallsicherheitslösung jedoch möglicherweise nicht ausreichend rentabel.

Wenn Sie sich zur Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte entschließen, haben Sie drei Möglichkeiten. Entscheiden Sie mithilfe der folgenden Tabelle, welche Option für Sie geeignet ist.

|**Wenn Sie...**|**Empfehlung**|
|:-----|:-----|
|Host mit 25 bis 1.000 Benutzern am Zweigstellenstandort, wobei eine vollständige Bereitstellung nicht rentabel ist oder kein administrativer Support zur Verfügung steht  <br/> |Survivable Branch Appliance  <br/> Die Survivable Branch Appliance ist ein Branchenstandard-Blade-Server mit einer Skype for Business Server-Registrierungsstelle und einem Vermittlungsserver, der auf Windows Server 2008 R2. Die Survivable Branch Appliance enthält auch ein PstN-Gateway( Public Switched Telephone Network). Qualifizierte Drittanbietergeräte (entwickelt von Microsoft-Partnern im Programm zur SBA-Qualifizierung/-Zertifizierung) bieten bei einem WAN-Ausfall eine dauerhafte PSTN-Verbindung (Public Switched Telephone Network, Telefonfestnetz), es werden jedoch keine ausfallsicheren Anwesenheits- und Konferenzfeatures bereitgestellt, da diese Features von den Front-End-Servern am zentralen Standort abhängen.  <br/> Weitere Informationen zu Survivable Branch Appliances finden Sie unter "Survivable Branch Appliance Details" weiter später in diesem Thema.  <br/> **Hinweis:** Wenn Sie auch einen SIP-Trunk mit Ihrer Survivable Branch Appliance verwenden möchten, wenden Sie sich an Ihren Survivable Branch Appliance-Hersteller, um zu erfahren, welcher Dienstanbieter für Ihre Organisation am besten ist. <br/> |
|Hosten von 1.000 bis 2.000 Benutzern an Ihrem Zweigstellenstandort, fehlende ausfallsichere WAN-Verbindung und geschulte Skype for Business Server-Administratoren  <br/> |Survivable Branch Server oder zwei Survivable Branch Appliances.  <br/> Der Survivable Branch Server ist ein Windows Server, der die angegebenen Hardwareanforderungen erfüllt, auf dem skype for Business Server-Registrierungs- und Vermittlungsserversoftware installiert ist. Der Server muss entweder über ein PSTN-Gateway oder einen SIP-Trunk mit einem Telefoniedienstanbieter verbunden sein.  <br/> Weitere Informationen zu Survivable Branch Servers finden Sie unter "Survivable Branch Server Details" weiter später in diesem Thema.  <br/> |
|Wenn Sie Anwesenheits- und Konferenzfunktionen zusätzlich zu den Sprachfunktionen für bis zu 5.000 Benutzer benötigen und geschulte Skype for Business Server-Administratoren zur Verfügung stehen  <br/> |Führen Sie statt einer Zweigstellenbereitstellung eine Bereitstellung als zentraler Standort mit einem Standard Edition-Server durch.  <br/> Eine vollständige Skype for Business Server-Bereitstellung bietet eine kontinuierliche PSTN-Verbindung sowie ausfallsichere Anwesenheits- und Konferenzvorgänge im Falle eines WAN-Ausfalls.  <br/> |

#### <a name="resiliency-topologies"></a>Topologien zur Bereitstellung von Ausfallsicherheit

Die folgende Abbildung zeigt die empfohlenen Topologien zum Gewährleisten von Ausfallsicherheit für einen Zweigstellenstandort.

**Optionen für die Bereitstellung von Ausfallsicherheit für Zweigstellenstandorte**

![Optionen zur Ausfallsicherheit von Voice Branch](../../media/Plan_OCS_Voice_BranchResiliencyOptions.jpg)

#### <a name="survivable-branch-appliance-details"></a>Details zur Survivable Branch Appliance

Die Skype for Business Server Survivable Branch Appliance umfasst die folgenden Komponenten:

- Einen Registrierungsserver für Benutzerauthentifizierung, Registrierung und Anrufrouting

- Einen Vermittlungsserver für die Signalverarbeitung zwischen der Registrierung und einem PSTN-Gateway

- Ein PSTN-Gateway zum Routen von Anrufen an das Telefonfestnetz als Fallback bei WAN-Ausfällen

- SQL Server Express zur Speicherung lokaler Benutzerdaten

Die Survivable Branch Appliance umfasst außerdem PSTN-Trunks, analoge Ports und einen Ethernet-Adapter.

Wenn die WAN-Verbindung des Zweigstellenstandorts zu einem zentralen Standort nicht mehr verfügbar ist, werden interne Zweigstellenbenutzer weiterhin bei der Survivable Branch Appliance Registrar registriert und erhalten einen unterbrechungsfreien Sprachdienst mithilfe der Survivable Branch Appliance-Verbindung mit dem PSTN. Zweigstellenbenutzer, die von zu Hause oder von Remotestandorten aus eine Verbindung herstellen, können sich beim Registrierungsserver am zentralen Standort registrieren, wenn die WAN-Leitung zum Zweigstellenstandort nicht verfügbar ist. Diese Benutzer haben Zugriff auf die vollständige Unified Communications-Funktionalität (UM), mit der Ausnahme, dass eingehende Anrufe am Zweigstellenstandort an das Voicemailsystem übermittelt werden. Wenn die WAN-Verbindung wieder verfügbar ist, sollte für Benutzer am Zweigstellenstandort automatisch die vollständige Funktionalität wiederhergestellt werden. Weder das Failover zur Survivable Branch Appliance noch die Wiederherstellung des Diensts erfordert das Vorhandensein eines IT-Administrators.

Skype for Business Server unterstützt bis zu zwei Survivable Branch Appliances an einem Zweigstellenstandort.

#### <a name="survivable-branch-appliance-deployment-overview"></a>Übersicht über die Bereitstellung einer Survivable Branch Appliance

Die Survivable Branch Appliance wird von Originalgeräteherstellern in Zusammenarbeit mit Microsoft hergestellt und in ihrem Namen von Händlern mit Mehrwert bereitgestellt. Diese Bereitstellung sollte erst erfolgen, nachdem Skype for Business Server am zentralen Standort bereitgestellt wurde, eine WAN-Verbindung mit dem Zweigstellenstandort besteht und Zweigstellenbenutzer für die Enterprise-VoIP.

Ausführliche Informationen zu diesen Phasen finden Sie unter [Deploying a Survivable Branch Appliance or Server](https://technet.microsoft.com/library/cb780c14-dc5f-41ba-8092-f20ae905bd16.aspx) in der Bereitstellungsdokumentation.

|**Phase**|**Schritte**|**Benutzerrechte**|
|:-----|:-----|:-----|
|Einrichten von Active Directory Domain Services für die Survivable Branch Appliance  <br/> |**Am zentralen Standort:** <br/>  Erstellen Sie ein Domänenbenutzerkonto (oder eine Unternehmensidentität) für den Techniker, der die Survivable Branch Appliance am Zweigstellenstandort installiert und aktiviert. <br/>  Erstellen Sie ein Computerkonto (mit dem entsprechenden vollqualifizierten Domänennamen)) für survivable Branch Appliance in Active Directory Domain Services. <br/>  Erstellen und veröffentlichen Sie im Topologie-Generator die Survivable Branch Appliance. <br/> |Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe "RTCUniversalSBATechnicians" sein. Die Survivable Branch Appliance muss der Gruppe "RTCSBAUniversalServices" angehören, was automatisch geschieht, wenn Sie den Topologie-Generator verwenden.  <br/> |
|Installieren und aktivieren Sie die Survivable Branch Appliance.  <br/> |**Am Zweigstellenstandort:** <br/>  Verbinden Sie die Survivable Branch Appliance mit einem Ethernet- und einem PSTN-Port. <br/>  Starten Sie die Survivable Branch Appliance. <br/>  Verbinden Sie die Survivable Branch Appliance mit der Domäne mithilfe des Domänenbenutzerkontos, das für die Survivable Branch Appliance am zentralen Standort erstellt wurde. Legen Sie FQDN und IP-Adresse auf den FQDN fest, den Sie im Computerkonto erstellt haben. <br/>  Konfigurieren Sie die Survivable Branch Appliance über die OEM-Benutzeroberfläche. <br/>  Testen Sie die PSTN-Anbindung. <br/> |Das Benutzerkonto für den Techniker muss Mitglied in der Gruppe "RTCUniversalSBATechnicians" sein.  <br/> |

#### <a name="survivable-branch-server-details"></a>Details zum Survivable Branch Server

Erstellen Sie im Topologie-Generator den Zweigstellenstandort, fügen Sie den Survivable Branch Server zu diesem Standort hinzu, und führen Sie dann den Skype for Business Server-Bereitstellungs-Assistenten auf dem Computer aus, auf dem Sie die Rolle installieren möchten.

### <a name="branch-site-resiliency-requirements"></a>Anforderungen an die Ausfallsicherheit von Zweigstellenstandorten

Dieses Thema unterstützt Sie bei der Vorbereitung von Benutzern im Hinblick auf die Ausfallsicherheit für Zweigstellenstandorte und für VoIP-Funktionen, und es werden die relevanten Hardware- und Softwareanforderungen angegeben.

#### <a name="preparing-branch-users-for-branch-site-resiliency"></a>Vorbereiten von Zweigstellenbenutzern für die Ausfallsicherheit für Zweigstellenstandorte

Bereiten Sie die Benutzer auf ausfallsicherheit für Zweigstellenstandorte vor, indem Sie ihren Registrierungsstellenpool als Survivable Branch Appliance (SBA) oder Survivable Branch Server festlegen.

#### <a name="registrar-assignments-for-branch-users"></a>Registrierungszuweisungen für Zweigstellenbenutzer

Unabhängig davon, welche Ausfallsicherheitslösung für Zweigstellenstandorte Sie auswählen, müssen Sie jedem Benutzer eine primäre Registrierung zuweisen. Zweigstellenbenutzer sollten sich immer bei der Registrierung am Zweigstellenstandort registrieren, unabhängig davon, ob sich diese Registrierung auf dem Survivable Branch Appliance-, Survivable Branch Server- oder eigenständigen Skype for Business Server Standard- oder Enterprise Edition-Server befindet. Ein Ressourcendatensatz für den Domänennamensystemdienst (DOMAIN Name System, SRV) ist erforderlich, damit ein Client seinen Registrierungsstellenpool ermitteln kann. Wenn die Survivable Branch Appliance nicht mehr verfügbar ist, ermitteln Zweigstellenclients auf diese Weise automatisch die Sicherungsregistrierungsstelle.

Wenn ein Zweigstellenstandort nicht über einen DNS-Server verfügt, gibt es zwei alternative Möglichkeiten zum Konfigurieren der Ermittlung der Survivable Branch Appliance oder des Survivable Branch Servers:

- Konfigurieren Sie die DHCP-Option 120 auf dem Dynamic Host Configuration Protocol (DHCP)-Server des Zweigstellenstandorts, um auf den vollqualifizierten Domänennamen (FQDN) der Survivable Branch Appliance oder des Survivable Branch Servers zu verweisen.

- Konfigurieren Sie die Survivable Branch Appliance oder den Survivable Branch Server so, dass sie auf DHCP 120-Abfragen reagiert.

#### <a name="voice-routing-for-branch-users"></a>VoIP-Routing für Zweigstellenbenutzer

Es wird empfohlen, eine separate VoIP-Richtlinie (Voice over Internet Protocol) auf Benutzerebene für Benutzer an einem Zweigstellenstandort zu erstellen. Diese Richtlinie sollte eine primäre Route umfassen, die die Survivable Branch Appliance oder das Zweigstellenservergateway verwendet, sowie eine oder mehrere Sicherungsrouten, die einen Trunk mit einem PstN-Gateway (Public Switched Telephone Network) am zentralen Standort verwenden. Wenn die primäre Route nicht verfügbar ist, wird stattdessen die Sicherungsroute verwendet, die ein oder mehrere Gateways für den zentralen Standort verwendet. Auf diese Weise ist die VoIP-Richtlinie des Benutzers immer wirksam, unabhängig davon, wo ein Benutzer registriert ist – in der Zweigstellenregistrierungsstelle oder im Sicherungsregistrierungspool am zentralen Standort. Dies ist eine wichtige Überlegung für Failoverszenarien. Wenn Sie beispielsweise die Survivable Branch Appliance umbenennen oder die Survivable Branch Appliance neu konfigurieren müssen, um eine Verbindung mit einem Sicherungsregistrierungspool am zentralen Standort herzustellen, müssen Sie die Zweigstellenbenutzer für die Dauer an den zentralen Standort verschieben. (Ausführliche Informationen zum Umbenennen oder Neukonfigurieren einer Survivable Branch Appliance finden Sie in Anhang [B: Managing a Survivable Branch Appliance](https://technet.microsoft.com/library/2ec9d505-6d39-491c-9524-8cf36866b855.aspx) in der Bereitstellungsdokumentation.) Wenn diese Benutzer keine Benutzerrichtlinien oder Wählpläne auf Benutzerebene haben, gelten beim Umstellen der Benutzer an einen anderen Standort standardmäßig die VoIP-Richtlinien auf Standortebene und Wählpläne auf Standortebene des zentralen Standorts für die Benutzer und nicht für die VoIP-Richtlinien und Wählpläne auf Zweigstellenstandortebene. In diesem Szenario können die vom Sicherungsregistrierungsstellenpool verwendeten VoIP-Richtlinien und Wählpläne auf Standortebene nicht auch für die Zweigstellenbenutzer gelten, wenn ihre Anrufe fehlschlagen. Wenn beispielsweise Benutzer von einem Zweigstellenstandort in Japan an einen zentralen Standort in Redmond verschoben werden, ist es unwahrscheinlich, dass ein Wählplan mit Normalisierungsregeln, die +1425 allen siebenstelligen Anrufen voranstellen, Anrufe für diese Benutzer entsprechend übersetzt.

> [!IMPORTANT]
> Beim Erstellen einer Alternativroute für eine Zweigstelle empfiehlt es sich, der Zweigstellenbenutzerrichtlinie zwei PSTN-Verwendungsdatensätze hinzuzufügen und ihnen jeweils separate Routen zuzuweisen. Die erste oder primäre Route leitet Anrufe an das Gateway weiter, das der Survivable Branch Appliance (SBA) oder dem Zweigstellenserver zugeordnet ist. Die zweite Oder Sicherung leitet Anrufe an das Gateway am zentralen Standort weiter. Beim Leiten von Anrufen probiert die SBA oder der Zweigstellenserver alle dem ersten PSTN-Verwendungsdatensatz zugewiesenen Routen aus, bevor der zweite Verwendungsdatensatz verwendet wird.

Um sicherzustellen, dass eingehende Anrufe an Zweigstellenbenutzer diese Benutzer erreichen, wenn das Zweigstellengateway oder die Windows-Komponente des Survivable Branch Appliance-Standorts nicht verfügbar ist (z. B. wenn die Survivable Branch Appliance oder das Zweigstellengateway zur Wartung ausfallen), erstellen Sie eine Failoverroute für das Gateway (oder arbeiten Sie mit Ihrem Direct Inward Dialing (DID)-Anbieter zusammen, um eingehende Anrufe an den Sicherungsregistrierungsstellenpool am zentralen Standort umzuleiten. Von dort aus werden die Anrufe über die WAN-Verbindung an Zweigstellenbenutzer weitergeleitet. Stellen Sie sicher, dass die Route Nummern übersetzt, damit sie den akzeptierten Telefonnummernformaten des PSTN-Gateways oder eines anderen Trunk-Peers entsprechen. Ausführliche Informationen zum Erstellen einer Failoverroute finden Sie unter [Configuring a Failover Route](https://technet.microsoft.com/library/76e48df4-3b78-4fb7-b1f7-c1e604b81bad.aspx). Erstellen Sie außerdem Wählpläne auf Dienstebene für den Trunkt, der dem Gateway an der Zweigstelle zugeordnet ist, damit eingehende Anrufe normalisiert werden. Wenn Sie über zwei Survivable Branch Appliances an einem Zweigstellenstandort verfügen, können Sie einen Wählplan auf Standortebene für beide erstellen, es sei denn, es ist ein separater Servicelevelplan erforderlich.

> [!NOTE]
> Um den Verbrauch der Ressourcen eines zentralen Standorts durch Zweigstellenbenutzer zu ermitteln, die für Anwesenheits-, Konferenz- oder Failoverfunktionen vom zentralen Standort abhängen, sollten Sie jeden Zweigstellenbenutzer so betrachten, als wäre er für den zentralen Standort registriert. Derzeit gibt es keine Beschränkungen für die Anzahl der Zweigstellenbenutzer, einschließlich der Benutzer, die bei einer Survivable Branch Appliance registriert sind.

Es empfiehlt sich außerdem, einen Wählplan und eine VoIP-Richtlinie auf Benutzerebene zu erstellen und diese dann den Zweigstellenbenutzern zuzuweisen. Ausführliche Informationen finden Sie unter "Erstellen oder Ändern eines Wählplans [in Skype for Business Server"](../../deploy/deploy-enterprise-voice/dial-plans.md) und "Erstellen der [VoIP-Routingrichtlinie](https://technet.microsoft.com/library/10deca9f-f870-4a42-b25d-e4fc53108658.aspx) für Zweigstellenbenutzer" in der Bereitstellungsdokumentation.

#### <a name="routing-extension-numbers"></a>Weiterleiten von Durchwahlnummern

Achten Sie bei der Vorbereitung von Wählplänen und -richtlinien für Zweigstellenbenutzer darauf, Normalisierungsregeln und Übersetzungsregeln zu verwenden, die den Zeichenfolgen und dem Nummernformat im Attribut "msRTCSIP-line" (oder "Line URI") entsprechen, damit Skype for Business-Anrufe, die zwischen Zweigstellenbenutzern und Benutzern am zentralen Standort aktiviert sind, ordnungsgemäß geroutet werden, insbesondere dann, wenn Anrufe über das PstN umgeleitet werden müssen, da die WAN-Verbindung nicht verfügbar ist. Weitere besondere Überlegungen betreffen gewählte Nummern, die nur Durchwahlnummern und keine Telefonnummern enthalten.

Besondere Voraussetzungen gelten für Normalisierungs- und Übersetzungsregeln, die Anschluss-URIs entsprechen, die eine Durchwahlnummer enthalten – sei es ausschließlich oder zusätzlich zu einer vollständigen E.164-Telefonnummer. In diesem Abschnitt werden einige Beispielszenarien zur Weiterleitung von Anrufen für Anschluss-URIs mit einer Durchwahlnummer beschrieben.

Wenn in Ihrer Organisation keine DID-Telefonnummern (Direct Inward Dial) für die einzelnen Benutzer konfiguriert sind und der Anschluss-URI für jeden Benutzer nur mit einer Durchwahlnummer konfiguriert ist, können interne Benutzer sich gegenseitig anrufen, indem Sie einfach nur eine Durchwahlnummer wählen. Allerdings müssen Sie Normalisierungsregeln konfigurieren, die für Anrufe eines Zweigstellenbenutzers an einen Benutzer am zentralen Standort gelten können, die mit den Durchwahlnummern übereinstimmen.

In einem Szenario, in dem die WAN-Verbindung zwischen einer Zweigstelle und einem zentralen Standort verfügbar ist, muss für Anrufe von Zweigstellenbenutzern an Benutzer am zentralen Standort nicht die Nummer durch eine entsprechende Normalisierungsregel übersetzt werden, da der Anruf nicht über das PSTN weitergeleitet wird. Ein Beispiel:

|**Regelname**|**Beschreibung**|**Nummernmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|:-----|
|5digitExtensions  <br/> |Fünfstellige Nummern werden nicht übersetzt  <br/> |^(\d{5})$  <br/> |$1  <br/> |10001 wird nicht übersetzt  <br/> |

Sie müssen auch Durchwahlnummern für besondere Szenarien mit einbeziehen, bei denen z. B. die WAN-Verbindung zwischen einer Zweigstelle und dem zentralen Standort nicht verfügbar ist und ein Anruf von einer Zweigstelle über das Festnetz weitergeleitet werden muss. Wenn ein Benutzer eines Zweigstellenstandorts während eines WAN-Ausfalls einen Benutzer des zentralen Standorts nur durch Wählen der Durchwahl des Benutzers des zentralen Standorts anruft, müssen Sie über eine ausgehende Übersetzungsregel verfügen, die die vollständige Telefonnummer des Benutzers des zentralen Standorts hinzufügt. Wenn der Leitungs-URI eines Benutzers die vollständige Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers anstelle einer vollständigen, für den Benutzer eindeutigen Telefonnummer enthält, müssen Sie über eine ausgehende Übersetzungsregel verfügen, die stattdessen die vollständige Telefonnummer Ihrer Organisation hinzufügt. Beispiel:

|**Beschreibung**|**Vergleichsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Übersetzt fünfstellige Nummern in die Telefonnummer und Durchwahlnummer eines Benutzers.  <br/> |^(\d{5})$  <br/> |+14255550123;ext=$1  <br/> |10001 wird in +14255550123;ext=10001 übersetzt  <br/> |
|Übersetzt fünfstellige Nummern in die Telefonnummer Ihrer Organisation und die Durchwahl eines Benutzers.  <br/> |^(\d{5})$  <br/> |+14255550100;ext=$1  <br/> |10001 wird in +14255550100;ext=10001 übersetzt  <br/> |

In diesem Szenario muss die ausgehende Übersetzungsregel, wenn der Trunkpeer, der die Rückumleitung an das Festnetz abwickelt, keine Durchwahlnummern unterstützt, auch die Durchwahlnummer entfernen. Beispiel:

|**Beschreibung**|**Vergleichsmuster**|**Übersetzung**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Entfernt die Durchwahl von Telefonnummern mit Durchwahlnummern  <br/> |^\+(\d \* ); ext=(\d \* )$  <br/> |+$1  <br/> |+14255550123;ext=10001 wird in +14255550123 übersetzt  <br/> |

Unabhängig davon, ob eine WAN-Verbindung verfügbar ist, wenn in Ihrer Organisation keine DID-Nummern für einzelne Benutzer konfiguriert sind und der Leitungs-URI für einen Benutzer die Telefonnummer Ihrer Organisation und die eindeutige Durchwahlnummer des Benutzers enthält, müssen Sie den Leitungs-URI der Telefonnummer Ihrer Organisation mit einer Nummer konfigurieren, die vom Trunk-Peer oder vom PstN-Gateway am Zweigstellenstandort erreichbar ist. Außerdem müssen Sie den Leitungs-URI ihrer Organisation so konfigurieren, dass er eine eigene eindeutige Durchwahlnummer für Anrufe enthält, die an diese Nummer geroutet werden.

#### <a name="preparing-for-voice-mail-survivability"></a>Vorbereiten der Ausfallsicherheit für VoIP-Funktionen

Exchange Unified Messaging (UM) wird in der Regel nur an einem zentralen Standort und nicht an Zweigstellenstandorten installiert. Ein Anrufer sollte auch dann eine Voicemailnachricht hinterlassen können, wenn die WAN-Verbindung zwischen Zweigstelle und zentralem Standort nicht verfügbar ist. Das Konfigurieren des Leitungs-URI für die Exchange UM automatische Telefonzentrale-Telefonnummer, die Voicemail für Zweigstellenbenutzer bietet, erfordert daher zusätzlich zu den für diese Voicemailnummer geltenden Voicemailrichtlinien, Wählplan- und Normalisierungsregeln besondere Überlegungen.

Survivable Branch Appliances (SBAs) und Survivable Branch Servers bieten ausfallenden Voicemail für Zweigstellenbenutzer während eines WAN-Ausfalls. Wenn Sie eine Survivable Branch Appliance oder einen Survivable Branch Server verwenden und das WAN nicht mehr verfügbar ist, leitet der SBA- oder Survivable Branch Server nicht beantwortete Anrufe über das Telefonnetz an Exchange UM am zentralen Standort um. Mit einem SBA- oder Survivable Branch Server können Benutzer voicemailnachrichten auch während eines WAN-Ausfalls über das PSTN abrufen. Schließlich stellt die Survivable Branch Appliance oder der Survivable Branch Server bei einem Ausfall des WAN Benachrichtigungen über verpasste Anrufe in die Warteschlange und lädt sie dann auf den Exchange -UM-Server hoch, wenn das WAN wiederhergestellt wird. Um sicherzustellen, dass die Voicemailumleitung ausfallsicher ist, müssen Sie einen Eintrag für den FQDN des zentralen Standortpools und einen Eintrag für den Edgeserver-FQDN zur Hostdatei auf dem Survivable Branch Server hinzufügen. Andernfalls kann es bei der DNS-Auflösung zu einem Timeout kommen, wenn an der Zweigstelle kein DNS-Server vorhanden ist.

Für die Bereitstellung ausfallsicherer VoIP-Funktionen für Zweigstellenbenutzer werden die folgenden Konfigurationen empfohlen:

- Ein Microsoft Exchange-Administrator sollte Exchange UM automatische Telefonzentrale (AA) so konfigurieren, dass nur Nachrichten akzeptiert werden. Durch diese Konfiguration wird jede andere allgemeine Funktionalität deaktiviert, beispielsweise das Durchstellen an einen Benutzer oder an einen Agent, und beschränkt die automatische Telefonzentrale auf die Annahme von Nachrichten. Alternativ dazu kann der Exchange-Administrator auch eine allgemeine automatische Telefonzentrale oder eine benutzerdefinierte automatische Telefonzentrale zum Routen des Anrufs an einen Agent verwenden.

- Der Skype for Business Server-Administrator sollte die AA-Telefonnummer verwenden und diese Telefonnummer als nummer der automatischen **Exchange-Um-Telefonleitung** in den Voicemailumleitungseinstellungen für die Survivable Branch Appliance oder den Zweigstellenserver verwenden.

- Der Skype for Business Server-Administrator sollte die Exchange UM-Teilnehmerzugriffstelefonnummer erhalten und diese Nummer als Teilnehmerzugriffsnummer in den Voicemailumleitungseinstellungen für die Survivable Branch Appliance oder den Survivable Branch Server verwenden. 

- Der Skype for Business Server-Administrator sollte Exchange UM so konfigurieren, dass allen Zweigstellenbenutzern, die während eines Wan-Ausfalls Zugriff auf Voicemail benötigen, nur ein Wählplan zugeordnet ist.

- Wenn die WAN-Verbindung nicht verfügbar ist, können Anrufe an Zweigstellenbenutzer an das Exchange Unified Messaging (UM)-Sprachpostfach des Benutzers geroutet werden, jedoch nur, wenn die auf den Anruf angewendete Sprachrichtlinie eine eindeutige Voicemailtelefonnummer angibt, die keine Durchwahlnummer enthält.

#### <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>Hardware- und Softwareanforderungen für die Ausfallsicherheit am Zweigstellenstandort

Die Hardware- und Softwareanforderungen variieren je nach Ausfallsicherheitslösung.

#### <a name="requirements-for-survivable-branch-appliances"></a>Anforderungen für Survivable Branch Appliances

Erforderliche Hardware und Software ist in die Survivable Branch Appliance integrierte. Es wird jedoch auch empfohlen, dass jeder Zweigstellenstandort einen #A0 zum Abrufen von Client-IP-Adressen bereitstellen. Andernfalls verfügen Clients nach Ablauf der DHCP-Lease nicht über IP-Konnektivität.

Wenn sich die Enterprise-DNS-Server nur an zentralen Standorten befinden, können Zweigstellenbenutzer während eines WAN-Ausfalls keine Verbindung mit ihnen herstellen, und daher kann die Skype for Business Server-Ermittlung, die den DNS-SRV (Service-SRV)-Ressourcendatensatz verwendet, fehlschlagen. Damit eine sofortige Umleitung während eines WAN-Ausfalls gewährleistet ist, müssen DNS-Einträge am Zweigstellenstandort zwischengespeichert werden. Wenn der Zweigstellenrouter die DNS-Zwischenspeicherung unterstützt, aktivieren Sie sie. Sie können auch einen DNS-Server in der Zweigstelle bereitstellen. Dies kann ein eigenständiger Server oder eine Version der Survivable Branch Appliance sein, die die DNS-Funktionen unterstützt. Weitere Informationen erhalten Sie von Ihrem Survivable Branch Appliance-Anbieter.

> [!NOTE]
> Es ist nicht erforderlich, an jedem Zweigstellenstandort einen Domänencontroller zu verwenden. Die Survivable Branch Appliance authentifiziert Clients mithilfe eines speziellen Zertifikats, das sie als Reaktion auf die Zertifikatanforderung des Clients sendet, wenn sie sich anmeldet.

Skype for Business clients can discover the Skype for Business Server by using DHCP Option 120 (SIP Registrar Option). Dies ist mit einer von zwei Konfigurationen möglich:

- Konfigurieren Sie den DHCP-Server am Zweigstellenstandort so, dass er auf DHCP 120-Abfragen antwortet, die den FQDN der Registrierungsstelle auf der Survivable Branch Appliance oder dem Survivable Branch Server zurückgeben.

- Aktivieren Sie Skype for Business Server DHCP. Wenn diese Option aktiviert ist, antwortet die Skype for Business Server-Registrierungsstelle auf DHCP-Option 120-Abfragen. Beachten Sie, dass die Registrierung nicht auf andere DHCP-Abfragen als DHCP-Option 120 reagiert.

Zusätzlich sollten für größere Zweigstellenstandorte mit mehreren Subnetzen DHCP-Relay-Agents aktiviert werden, um Abfragen der DHCP-Option 120 an den DHCP Server (Konfiguration 1) oder die Registrierung (Konfiguration 2) weiterzuleiten.

Schließlich müssen Zweigstellenbenutzer für die Enterprise-VoIP konfiguriert und mit einem geeigneten Unified Communications-Endpunkt bereitgestellt werden.

#### <a name="requirements-for-survivable-branch-servers"></a>Anforderungen für Survivable Branch Server

Die Anforderungen für Survivable Branch Server sind mit den Anforderungen für einen Front-End-Server identisch. Weitere Informationen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015".](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)

#### <a name="requirements-for-full-scale-skype-for-business-server-branch-site-deployments"></a>Anforderungen für Full-Scale Skype for Business Server Branch-Site Bereitstellungen

Ausführliche Informationen finden Sie unter ["Serveranforderungen für Skype for Business Server 2015"](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) in der Planungsdokumentation.

### <a name="example-configuring-a-failover-route"></a>Beispiel: Konfigurieren einer Failoverroute

 Im folgenden Beispiel wird gezeigt, wie ein Administrator eine Failoverroute definieren kann, die bei geplanten Wartungsausfällen oder anderen Ausfällen des Gateways „Dallas-GW1“ verwendet wird. In den folgenden Tabellen wird die erforderliche Konfigurationsänderung beschrieben.

**Tabelle 1. Benutzerrichtlinie**

|**Benutzerrichtlinie**|**Telefonverwendung**|
|:-----|:-----|
|Standardanrufrichtlinie  <br/> |Lokal  <br/> GlobalPSTNHopoff  <br/> |
|Richtlinie für Ortsgespräche am Standort Redmond  <br/> |RedmondLocal  <br/> |
|Anrufrichtlinie für Dallas  <br/> |DallasUsers  <br/> GlobalPSTNHopoff  <br/> |

**Tabelle 2. Routen**


| **Name der Route**             | **Nummernmuster** | **Telefonverwendung**         | **Trunk**                                 | **Gateway**                                     |
|:---------------------------|:-------------------|:------------------------|:------------------------------------------|:------------------------------------------------|
| Route für Ortsgespräche am Standort Redmond  <br/> | ^\+1(425           | 206                     | 253)(\d {7} )$  <br/>                       | Lokal  <br/> RedmondLocal  <br/>                |
| Route für Ortsgespräche am Standort Dallas  <br/>  | ^\+1(972           | 214                     | 469)(\d {7} )$  <br/>                       | Lokal  <br/>                                    |
| Universalroute  <br/>     | ^\+? (\d \* ) $  <br/> | GlobalPSTNHopoff  <br/> | Trunk1  <br/> Trunk2  <br/> Trunk3  <br/> | Red-GW1  <br/> Red-GW2  <br/> Dallas-GW1  <br/> |
| Route für Benutzer in Dallas  <br/>  | ^\+? (\d \* ) $  <br/> | DallasUsers  <br/>      | Trunk3  <br/>                             | Dallas-GW1  <br/>                               |

In Tabelle 1 wird die Telefonverwendung „GlobalPSTNHopoff“ nach der Telefonverwendung „DallasUsers“ zur Anrufrichtlinie für Dallas hinzugefügt. Daher können für Anrufe, für die die Anrufrichtlinie für Dallas gilt, Routen verwendet werden, die für „GlobalPSTNHopoff“ konfiguriert sind, wenn eine Route für die Telefonverwendung „DallasUsers“ nicht verfügbar ist.


