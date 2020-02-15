---
title: Verwalten von Skype for Business Server 2015 mithilfe des SCOM Management Packs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Verwendung mit System Center Operations Manager konfigurieren.'
ms.openlocfilehash: 06297ba7e0ab70e7046fc2f3db189275cc90f9d4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42005940"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Verwalten von Skype for Business Server 2015 mithilfe des SCOM Management Packs
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.
  
In einer idealen Welt würden Probleme mit Skype for Business Server 2015 nie auftreten. Allerdings können Skype for Business Server von externen Faktoren betroffen sein, beispielsweise von Netzwerk abstürzen und Hardwarefehlern. Mithilfe Skype for Business Server 2015 Management Packs können Sie potenzielle Probleme proaktiv identifizieren und beheben. Auf diese Weise erweitern die Skype for Business Server 2015 Management Packs die Funktionen von System Center Operations Manager.
  
Diese Informationen wurden auf der Grundlage der Version 9319,0 des Monitoring Packs für Skype for Business Server 2015 Kommunikationssoftware geschrieben.
  
## <a name="configuration-overview"></a>Übersicht über die Konfiguration

 Zum Konfigurieren Ihrer Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager müssen Sie drei Schritte ausführen:
  
Identifizieren und [Konfigurieren des primären Verwaltungsservers](configure-the-primary.md) Hierzu müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [Konfigurieren Sie die Skype for Business Server Computer, die überwacht werden sollen](configure-computers-to-monitor.md). Zum Überwachen eines Skype for Business Server Computers mithilfe von System Center Operations Manager müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server so konfigurieren, dass er als Proxy fungiert. 
  
 Identifizieren und [Installieren und konfigurieren Sie Watcher-Knoten](watcher-nodes.md). Watcher-Knoten sind Computer, die regelmäßig Skype for Business Server synthetischen Transaktionen ausgeführt werden – Windows PowerShell Cmdlets, die überprüfen, ob die Schlüssel Skype for Business Server Komponenten, beispielsweise die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum sofortigen Austausch Nachrichten funktionieren wie erwartet. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager-Stamm Verwaltungs Server und Agent-Unterstützung

Die Management Packs können mit System Center Operations Manager 2007 R2 (64-Bit) oder System Center Operations Manager 2012 SP1 &amp; R2 (64-Bit) oder System Center Operations Manager 2016 (64-Bit) (nur für Migrationszwecke) verwendet werden. In der folgenden Tabelle sind die unterstützten Konfigurationen für die Management Packs für Skype for Business Server 2015 aufgeführt: 
  
|Konfiguration|Unterstützt?|
|:-----|:-----|
|Windows Server 2008 R2-Betriebssystem  <br/> Windows Server 2012 R2-Betriebssystem  <br/> |Ja. Sowohl auf Skype for Business Server 2015-Servern als auch auf synthetischen Transaktionsmonitor Knoten.  <br/> |
|Gruppierte Server  <br/> |Nicht unterstützt  <br/> |
|Überwachung ohne Agents  <br/> |Nicht unterstützt  <br/> |
|Virtuelle Umgebung  <br/> |Ja.  <br/> |
|Domänen verbundene Serverrollen  <br/> |Alle internen Skype for Business Server 2015-Server Rollen müssen einem Domänenbeitritt unterliegen.  <br/> |
|Eigenständige Serverrollen  <br/> |Skype for Business Server 2015 Edgeserver müssen nicht der Domäne beigetreten sein.  <br/> |
|Topologie-Einschränkungen  <br/> |Alle Serverrollen in einer Bereitstellung müssen von der gleichen Operations Manager-Verwaltungsgruppe überwacht werden.  <br/> |
|Knoten für synthetische Transaktionen Watcher  <br/> |Die Überwachung der Szenario-Verfügbarkeit mit einem Watcher-Knoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration erforderlich). Watcher-Knoten müssen nicht der Domäne beigetreten sein.  <br/> |
   
In der folgenden Tabelle sind die Kapazitäts-und Betriebssystemanforderungen für einen Monitor Knoten für synthetische Transaktionen aufgeführt:
  
|Hardwarekomponente|Mindestanforderung|
|:-----|:-----|
|CPU  <br/> |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Quad-Core, 2,33 GHz oder höher  <br/> 64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher  <br/> |
|Arbeitsspeicher  <br/> |8 GB  <br/> |
|Betriebssystem  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Netzwerk  <br/> |1 Netzwerkadapter mit 1 Gbit/s  <br/> |
   
## <a name="prerequisites"></a>Voraussetzungen

Um einen Monitor Knoten für synthetische Transaktionen auszuführen, müssen Sie zunächst Folgendes installieren:
  
- System Center Operations Manager-Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server Core-Installationsdateien (OcsCore. msi) und Unified Communications Managed API (UCMA) (Versionen müssen mit der Skype for Business Server WatcherNode. MSI-Version übereinstimmen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Überwachungspaket

Das Monitoring Pack für Skype for Business Server 2015 umfasst die folgenden Dateien:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode. msi
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu in Skype for Business Server 2015 Management Packs.

- **Änderungen im [September 2019-Update](https://www.microsoft.com/en-in/download/details.aspx?id=47364) ** Für einige Warnungen wurden Sonderzeichen entfernt. In einigen Fällen stören Sonderzeichen die Benachrichtigungsfunktion für das SCOM-Befehlskanal Programm.

- **Automatische Ermittlung für die Client Anmeldung** Client Anwendungen, die sich bei Skype for Business Server 2015 anmelden, ermitteln häufig automatisch den Server zur Anmeldung bei. Synthetische Transaktionen unterstützen jetzt die Überprüfung, dass die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Benutzerdefinierte Lauf Intervalle für synthetische Transaktionen** Um den Setup-Prozess von Watcher-Knoten zu vereinfachen, können synthetische Transaktionen Benutzerkonten freigeben. Dadurch wird die Häufigkeit verringert, mit der die Tests ausgeführt werden, wenn die Tests serialisiert werden, um Konflikte zu vermeiden. Standardmäßig werden synthetische Transaktionen alle 15 Minuten ausgeführt, um sicherzustellen, dass alle Tests Zeit zum Ausführen haben. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden möchten, können nun auch das Lauf Intervall reduzieren.
    
- **Synthetische Transaktion für Video Interoperabilitätsdienste** Kunden, die von anderen Anbieter Lösungen zu Skype for Business Server 2015 migrieren, möchten häufig die Video Teleconferencing-Geräte (VTCs) von diesen anderen Anbietern weiter verwenden. Bei Video Interop Server handelt es sich um eine neue Skype for Business Server 2015-Serverrolle, mit der Kunden Cisco VTCs weiterhin in ihren Konferenzräumen verwenden können, indem Sie über einen Video-SIP-Trunk eine Verbindung mit Cisco CUCM herstellen. Dieses Feature fügt außerdem eine synthetische Transaktion hinzu, um sicherzustellen, dass der Video-Interop-Server aktiviert ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Anwendungsfreigabe Konferenzen** Die End-to-End-Szenario-Validierung für Anwendungsfreigabe Konferenzen wird nun unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachungsszenarien

Das Skype for Business Server 2015 Management Pack nutzt eine Vielzahl von Funktionen, die Sie bei der Erkennung und Diagnose von Problemen unterstützen. Diese Features ermöglichen einen Echtzeiteinblick in die Integrität einer Skype for Business Server 2015 Umgebung.
  
|Überwachungsszenario|Beschreibung|
|:-----|:-----|
|Synthetische Transaktionen  <br/> | Windows PowerShell Cmdlets zum Testen und zur Sicherstellung der hohen Verfügbarkeit von Szenarien wie anmelden, Anwesenheitsinformationen, Chatnachrichten und Konferenzen für Benutzer. <br/> Die synthetischen Transaktionen können von jedem geografischen Standort aus ausgeführt werden, einschließlich innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen.  <br/> Wenn eine synthetische Transaktion fehlschlägt, werden HTML-Protokoll s erstellt, um die genaue Art des Fehlers zu ermitteln. Dazu gehört das Verständnis der fehlgeschlagenen Aktion, der Wartezeit der einzelnen Aktionen, der Befehlszeile, die zum Ausführen des Tests verwendet wurde, und des jeweiligen aufgetretenen Fehlers.  <br/> |
|Warnungen zur Anruf Zuverlässigkeit  <br/> |Call Detail Records (CDRs), die von Skype for Business Server 2015 Servern geschrieben wurden, geben an, ob Benutzer in der Lage sind, eine Verbindung mit einem Anruf herzustellen oder warum ein Anruf beendet wird. Warnungen zur Anruf Zuverlässigkeit Abfrage der KDS-Datenbank, um Warnungen zu erstellen, die angeben, wann eine hohe Anzahl von Benutzern Verbindungsprobleme für Peer-zu-Peer-Anrufe oder grundlegende Konferenzfunktionen aufweist.  <br/> Die Szenario-Abdeckung umfasst Audioanrufe, Peer-zu-Peer-Chatnachrichten (Instant Messaging) und andere Konferenzfunktionen.  <br/> |
|Benachrichtigungen zur Medienqualität  <br/> |Datenbankabfragen, die sich die QoE-Berichte (Quality of Experience) ansehen, die am Ende jedes Anrufs von Skype for Business Server 2015 Clients veröffentlicht werden. Diese Abfragen erzeugen Warnungen, in denen Szenarien ermittelt werden, in denen Benutzer bei Anrufen und Konferenzen am ehesten eine beeinträchtigte Medienqualität erleben. Die Daten basieren auf wichtigen Metriken wie Paket Wartezeit und Verlust, die direkt zur Qualität der Benutzerfreundlichkeit beitragen.  <br/> |
|Komponenten Integritätswarnungen  <br/> |Einzelne Server Komponenten lösen Warnungen über Ereignisprotokolle und Leistungsindikatoren aus, um Fehlerbedingungen anzuzeigen, die sich möglicherweise erheblich auf Benutzerszenarien auswirken. Diese Warnungen deuten auf eine Vielzahl von Bedingungen hin, beispielsweise nicht laufende Dienste, hohe Ausfallraten, hohe Nachrichten Wartezeit oder Verbindungsprobleme.  <br/> |
|Überwachung der Abhängigkeits Integrität  <br/> |Für Skype for Business Server kann aus einer Vielzahl von externen Gründen ein Fehler auftreten. Das Management Pack überwacht und sammelt Daten für wichtige externe Abhängigkeiten, die auf schwerwiegende Probleme hindeuten können. Diese Abhängigkeiten umfassen Internet Information Services (IIS) Verfügbarkeit und die CPU-Auslastung von Servern, die für Skype for Business Server verwendet werden.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Priorisierung von Warnungen

Warnungen werden in die folgenden Kategorien unterteilt: 
  
 **Warnungen mit hoher Priorität:** Diese Warnungen weisen auf Bedingungen hin, die zu Dienstausfällen für große Benutzergruppen führen und sofortiges Handeln erfordern. Ausfällen, die von synthetischen Transaktionen und Offline Diensten (wie Skype for Business Server Audio/Video Konferenzen) erkannt werden, werden als Warnungen mit hoher Priorität qualifiziert. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype for Business Server 2015 verfügt über integrierte Features für hohe Verfügbarkeit in diesen Situationen, beispielsweise mehrere Front-End-Server hinter Lastenausgleichssystemen.
  
 **Warnungen mittlerer Priorität:** Diese Warnungen zeigen Bedingungen an, die sich auf eine Teilmenge von Benutzern auswirken oder Probleme in der Anrufqualität anzeigen (beispielsweise Komponentenfehler, Wartezeit in einer Anrufeinrichtung oder niedrigere Audioqualität bei Anrufen). Warnungen in dieser Kategorie sind Stateful (das heißt, die Art der Warnung ändert sich basierend auf dem Status der Netzwerkverbindung.) Wenn beispielsweise die Anruf Erstellungszeiten auf Wartezeit hindeuten, aber dann zu einem normalen Schwellenwert zurückkehren, würde diese Warnung mit mittlerer Priorität automatisch in System Center Operations Manager aufgelöst, und Administratoren müssten keine Maßnahmen ergreifen. Warnungen, die nicht automatisch aufgelöst werden können, werden in der Regel von Administratoren am gleichen Werktag adressiert.
  
 **Andere Warnungen:** Diese Warnungen werden von Komponenten generiert, die sich möglicherweise auf einen bestimmten Benutzer oder eine Teilmenge von Benutzern auswirken. Eine typische Warnung wäre beispielsweise, dass der Adressbuchdienst den Active Directory-Domänendienste Eintrag (AD DS) für Benutzer: testuser@contoso.com nicht analysieren konnte. Administratoren können diese Benachrichtigungen immer dann adressieren, wenn Ihnen Zeit zur Verfügung steht.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype for Business Server 2015 Management Packs bieten erhöhte Abdeckung für Warnungen über synthetische Transaktionen. Synthetische Transaktionen sind Windows PowerShell Cmdlets, die in das Operations Manager Management Pack integriert sind, um End-to-End-Benutzerszenarien zu testen. Wenn Sie einen Server für die Ausführung synthetischer Transaktionen festlegen, werden diese Cmdlets regelmäßig vom Management Pack ausgelöst. Fehler, die sich aus einer synthetischen Transaktion ergeben, generieren eine statusbehaftete Warnung. Hier werden synthetische Transaktionen für Skype for Business Server 2015 unterstützt:
  


|Unterstützte synthetische Transaktionen für Registrierung, Anwesenheit und Kontakte|||
|:-----|:-----|:-----|
|1   <br/> |Registrierung (Benutzeranmeldung)  <br/> |Verfügbar lync Server 2010 und darüber hinaus  <br/> |
|2   <br/> |Adressbuchdienst (Dateidownload)  <br/> |Verfügbar lync Server 2010 und darüber hinaus  <br/> |
|3   <br/> |Adressbuchwebabfrage  <br/> |Verfügbar lync Server 2010 und darüber hinaus  <br/> |
|4   <br/> |Anwesenheit  <br/> |Verfügbar lync Server 2010 und darüber hinaus  <br/> |
|5   <br/> |Einheitlicher Kontaktspeicher  <br/> |Verfügbar lync Server 2013 und darüber hinaus  <br/> |
||||   

|Unterstützte synthetische Transaktionen für Peer-to-Peer-Dienste|||
|:-----|:-----|:-----|
|6   <br/> |Peer-zu-Peer-Chatnachrichten  <br/> |Verfügbar in lync Server 2010 und darüber hinaus  <br/> |
|7   <br/> |Peer-to-Peer-Audio-Video  <br/> |Verfügbar in lync Server 2010 und darüber hinaus  <br/> |
|8   <br/> |MCX Peer-to-Peer-Sofortnachricht (mobil)  <br/> |Verfügbar in der September 2011-Version von lync Server 2010 Skype for Business 2015  <br/> |
 
> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle aktuellen Skype for Business mobilen Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit älteren Clients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.


|Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat|||
|:-----|:-----|:-----|
|9   <br/> |Audio-Video Konferenzen  <br/> |Verfügbar in lync Server 2010 und darüber hinaus  <br/> |
|10   <br/> |Datenkonferenzen  <br/> |Verfügbar in lync Server 2013 und darüber hinaus  <br/> |
|11  <br/> |Sofortnachrichtenkonferenzen  <br/> |Verfügbar in lync Server 2010 und darüber hinaus  <br/> |
|12  <br/> | Beständiger Chat <br/> |Verfügbar in lync Server 2013 und darüber hinaus  <br/> |
|13  <br/> |Join Launcher (geplante Besprechungen)  <br/> |Verfügbar in lync Server 2013 und darüber hinaus  <br/> |
|14   <br/> |Einwahlkonferenzen  <br/> |Neu in Skype for Business Server 2015  <br/> |
|15   <br/> |Anwendungsfreigabe Konferenzen  <br/> |Neu in Skype for Business Server 2015  <br/> |
|16   <br/> |UCWA-Konferenz (webbesprechungs Beitritt)  <br/> |Neu in Skype for Business Server 2015  <br/> |
||||

|Unterstützte synthetische Transaktionen für Netzwerk-und Partner Abhängigkeiten|||
|:-----|:-----|:-----|
|17   <br/> |AV-Edge-Konnektivität  <br/> |Verfügbar in lync Server 2013 und darüber hinaus  <br/> |
|18   <br/> |Exchange Unified Message Connectivity (Voicemail) für AV-Edge-Konnektivität  <br/> |Verfügbar in lync Server 2013 und darüber hinaus  <br/> |
|19  <br/> |PSTN-Peer-zu-Peer-Anruf  <br/> |Verfügbar in lync Server 2010 und darüber hinaus  <br/> |
|20  <br/> |XMPP-Sofortnachrichten (Verbund)  <br/> |Verfügbar in lync Server 2013 und Skype for Business 2015  <br/> |
|21  <br/> |Video-Interop-Server  <br/> |Neu in Skype for Business Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>Rollup der Integrität

In der folgenden Tabelle sind die Integritätsstatus von Objekten dargestellt, die das Skype for Business Server-Überwachungspaket enthält.
  
|Management Pack-Objekt|Beschreibung|
|:-----|:-----|
|Skype for Business Server-Bereitstellung  <br/> |Stellt die Bereitstellung von Skype for Business Server 2015 in der Organisation dar.  <br/> |
|Skype for Business Server Website  <br/> |Stellt verschiedene geographische Standorte dar, an denen Dienste bereitgestellt werden.  <br/> |
|Skype for Business Server Pool  <br/> |Ein Pool (innerhalb eines Standorts), der den Benutzern Kommunikationsdienste wie Chatnachrichten und Konferenzen zur Verfügung stellt. Gilt für Front-End-Pools, Edge-Pools und Director-Pools, auch wenn es nur einen einzelnen Computer in einem bestimmten Pool gibt.  <br/> |
|Skype for Business Server Rolle  <br/> |Eine Serverrolle, die Skype for Business Server-Dienst hostet.  <br/> |
|Skype for Business Server Dienst  <br/> |Stellt eine auf einem bestimmten Computer bereitgestellte Funktionalität dar (beispielsweise Benutzer Dienst auf fp01.contoso.com).  <br/> |
|Skype for Business Server Komponente  <br/> |Eine Komponente des Diensts (beispielsweise ist die Adressbuch-Download Komponente Bestandteil des Webdiensts).  <br/> |
|Skype for Business Server Pool Monitor  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Pool ausgeführt werden.  <br/> |
|Skype for Business Server Registrar Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen registrierungsstellenpool ausgeführt werden.  <br/> |
|Skype for Business Server Pool Monitor für Benutzer Dienste  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Benutzer Dienste-Pool ausgeführt werden.  <br/> |
|Skype for Business Server sprach Pool Monitor  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen VoIP-Pool ausgeführt werden.  <br/> |
|Skype for Business Server Port Watcher  <br/> |Eine Instanz der Port Überprüfung, die für einen Pool durchgeführt wird.  <br/> |
|Einfacher URL-Watcher  <br/> |Führt HTTPS-Sondierung der konfigurierten einfachen URLs in einer Bereitstellung aus.  <br/> |
   
![SCOM-Rollup](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Ein Skype for Business Server Pool kann mehrere einzelne Skype for Business Server Systeme enthalten (mit mehr als einer Skype for Business Server Rolle, Skype for Business Server Dienst und Skype for Business Server Komponente). Daher ist der Ausfall eines einzelnen Servers oder einer Komponente für den Gesamtzustand des Skype for Business Server Pools unwichtiger, da andere Server im selben Pool dem Client den Anwendungsdienst bereitstellen können. Die Integrität wird auf einer Prozent Ebene auf den Skype for Business Server Pool hoch gerollt. 
  
Der Skype for Business Server Pool Monitor führt synthetische Transaktionen für einen Skype for Business Server-Pool aus. Aufeinander folgender Fehler bei einer oder mehreren synthetischen Transaktionen (ein Prozess, der als Aufeinanderfolgendes Abrufintervall bezeichnet wird) rollt den kritischen Integritätsstatus auf die Poolebene (am schlechtesten einer synthetischen Transaktion), wie im folgenden Diagramm dargestellt. 
  
![SCOM-Rollup aufeinanderfolgender Abruf](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Standardmäßig speichert Operations Manager alle Anpassungen, beispielsweise Außerkraftsetzungen, im Standard-Management Pack. Als bewährte Methode sollten Sie ein separates Management Pack für jedes versiegelte Management Pack erstellen, das Sie anpassen möchten. 
  
Wenn Sie ein Management Pack zum Speichern angepasster Einstellungen für ein versiegeltes Management Pack erstellen, wird empfohlen, das neue Management Pack entsprechend zu benennen, beispielsweise "Skype for Business Server 2015 Anpassungen". 
  
Durch das Erstellen eines neuen Management Packs zum Speichern von Anpassungen jedes versiegelten Management Packs wird das Exportieren der Anpassungen aus einer Testumgebung in eine Produktionsumgebung vereinfacht. Dadurch wird auch das Löschen eines Management Packs vereinfacht, da Sie alle Abhängigkeiten löschen müssen, bevor Sie ein Management Pack löschen können. Wenn Anpassungen für alle Management Packs im Standard-Management Pack gespeichert werden und Sie ein einzelnes Management Pack löschen müssen, müssen Sie zuerst das Standard Management Pack löschen, das auch Anpassungen für andere Management Packs löscht. 
  
## <a name="links"></a>Links

Die folgenden Links stellen eine Verbindung zu Informationen zu allgemeinen Aufgaben her, die mit System Center 2012-Überwachungs Paketen verbunden sind:
  
- [Management Pack-Lebenszyklus](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Importieren eines Management Packs in Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [Vorgehensweise außer Kraft setzen einer Regel oder eines Monitors](https://technet.microsoft.com/library/hh212869.aspx)
    
- [Vorgehensweise Erstellen eines Ausführ Unterkontos in Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Verwalten von Ausführ als Konten und Profilen](https://technet.microsoft.com/library/hh212714.aspx)
    
- [Exportieren eines Operations Manager Management Packs](https://technet.microsoft.com/library/hh320149.aspx)
    
- [Entfernen eines Operations Manager Management Packs](https://technet.microsoft.com/library/hh230746.aspx)
    
Die folgenden Links stellen eine Verbindung zu Informationen zu allgemeinen Aufgaben her, die mit System Center 2007-Überwachungs Paketen verbunden sind:
  
- [Verwalten des Management Pack-Lebenszyklus](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Importieren eines Management Packs in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Überwachen der Verwendung von Außerkraftsetzungen](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Vorgehensweise Erstellen eines Ausführ Operations Manager 2007 Kontos](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Vorgehensweise ändern eines vorhandenen ausführbaren Profils](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Exportieren von Management Pack-Anpassungen](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Vorgehensweise Entfernen eines Management Packs](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Fragen zu Operations Manager und Überwachungs Paketen finden Sie im [System Center Operations Manager-Community-Forum](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Eine hilfreiche Ressource ist der Blog " [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) ", der "durch ein Beispiel"-Beiträge für bestimmte Monitoring Packs enthält.
  
Weitere Informationen zu Operations Manager finden Sie in den folgenden Blogs: 
  
- [Team-Blog für Operations Manager](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holmans Opsmgr-Blog](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Überlegungen zu OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog von Raphael Burri](https://rburri.wordpress.com/)
    
- [BWren-Verwaltungsbereich](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Alle Informationen und Inhalte auf nicht-Microsoft-Websites werden vom Besitzer oder von den Benutzern der Website bereitgestellt. Microsoft leistet keine ausdrücklichen, impliziten oder gesetzlichen Garantien hinsichtlich der Informationen auf dieser Website. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015 Verwaltungs Tools](../../management-tools/management-tools.md)
