---
title: Verwalten von Skype for Business Server 2015 mit dem SCOM Management Pack
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.'
ms.openlocfilehash: cfb48338d4022c1de7c5944f66d72e58dd8b403d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814845"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Verwalten von Skype for Business Server 2015 mit dem SCOM Management Pack
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.
  
In einer idealen Welt würden nie Probleme mit Skype for Business Server 2015 auftreten. Skype for Business Server kann jedoch durch externe Faktoren beeinflusst werden, z. B. Netzwerkabstürze und Hardwarefehler. Mithilfe von Skype for Business Server 2015 Management Packs können Sie potenzielle Probleme proaktiv identifizieren und beheben. Auf diese Weise erweitern die Skype for Business Server 2015 Management Packs die Funktionen von System Center Operations Manager.
  
Diese Informationen wurden basierend auf Version 9319.0 der Monitoring Pack für Skype for Business Server 2015-Kommunikationssoftware geschrieben.
  
## <a name="configuration-overview"></a>Übersicht über die Konfiguration

 Um Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren, müssen Sie drei Dinge tun:
  
Identifizieren und [Konfigurieren des primären Verwaltungsservers.](configure-the-primary.md) Dazu müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [Konfigurieren der Skype for Business Server-Computer, die überwacht werden.](configure-computers-to-monitor.md) Zum Überwachen eines Skype for Business Server-Computers mithilfe von System Center Operations Manager müssen Sie die System Center Operations Manager-Agent-Dateien installieren und jeden Server als Proxy konfigurieren. 
  
 Identifizieren und [Installieren und Konfigurieren von Watcher-Knoten.](watcher-nodes.md) Bei Den Watcher-Knoten handelt es sich um Computer, auf denen regelmäßig synthetische Skype for Business Server-Transaktionen ausgeführt werden– Windows PowerShell-Cmdlets, die überprüfen, ob wichtige Skype for Business Server-Komponenten, z. B. die Möglichkeit der Anmeldung am System oder der Austausch von Chatnachrichten, wie erwartet funktionieren. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager Root Management Server und Agent-Unterstützung

Die Management Packs können mit System Center Operations Manager 2007 R2 (64-Bit) (nur zu Migrationszwecken unterstützt) oder System Center Operations Manager 2012 SP1 &amp; R2 (64-Bit) oder System Center Operations Manager 2016 (64-Bit) verwendet werden. In der folgenden Tabelle sind die unterstützten Konfigurationen für die Management Packs für Skype for Business Server 2015 aufgeführt: 
  
|Konfiguration|Unterstützt?|
|:-----|:-----|
|Windows Server 2008 R2-Betriebssystem  <br/> Windows Server 2012 Betriebssystem R2  <br/> |Ja. Sowohl auf Skype for Business Server 2015-Servern als auch auf Knoten der synthetischen Transaktions-Watcher.  <br/> |
|Clusterserver  <br/> |Nicht unterstützt  <br/> |
|Agentlose Überwachung  <br/> |Nicht unterstützt  <br/> |
|Virtuelle Umgebung  <br/> |Ja.  <br/> |
|Der Domäne beigetretene Serverrollen  <br/> |Alle internen Skype for Business Server 2015-Serverrollen müssen einer Domäne beigetreten sein.  <br/> |
|Eigenständige Serverrollen  <br/> |Skype for Business Server 2015-Edgeserver müssen nicht der Domäne beigetreten sein.  <br/> |
|Topologieeinschränkungen  <br/> |Alle Serverrollen in einer Bereitstellung müssen von derselben Operations Manager-Verwaltungsgruppe überwacht werden.  <br/> |
|Watcherknoten für synthetische Transaktionen  <br/> |Die Verfügbarkeit des Überwachungsszenarios mit einem Watcher-Knoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration erforderlich). Watcherknoten müssen nicht der Domäne beigetreten sein.  <br/> |
   
In der folgenden Tabelle sind die Kapazitäts- und Betriebssystemanforderungen für einen Synthetischen Transaktions-Watcher-Knoten aufgeführt:
  
|Hardwarekomponente|Mindestanforderung|
|:-----|:-----|
|CPU  <br/> |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Vierkern, 2,33 GHz oder höher  <br/> 64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher  <br/> |
|Arbeitsspeicher  <br/> |8 GB  <br/> |
|Betriebssystem  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Netzwerk  <br/> |1 Netzwerkadapter mit 1 GBit/s  <br/> |
   
## <a name="prerequisites"></a>Voraussetzungen

Zum Ausführen eines Watcher-Knotens für synthetische Transaktionen müssen Sie zuerst Folgendes installieren:
  
- System Center Operations Manager Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server Core Installation Files (OcsCore.msi) und Unified Communications Managed API (UCMA) (Versionen müssen mit der Skype for Business Server WatcherNode.msi übereinstimmen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Monitoring Pack

Das Monitoring Pack für Skype for Business Server 2015 enthält die folgenden Dateien:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu in Skype for Business Server 2015 Management Packs.

- **Änderungen im [Update vom September 2019](https://www.microsoft.com/en-in/download/details.aspx?id=47364)** Bei einigen Warnungen wurden Sonderzeichen entfernt. In einigen Fällen stören Sonderzeichen die Benachrichtigungsfunktion des SCOM-Befehlskanals.

- **Automatische Ermittlung für die Client-Anmeldung** Clientanwendungen, die sich bei Skype for Business Server 2015 anmelden, ermitteln häufig automatisch den Server für die Anmeldung. Synthetische Transaktionen unterstützen jetzt die Überprüfung, ob die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Angepasste Ausführungsintervalle für synthetische Transaktionen** Zur Vereinfachung des Einrichtungsprozesses von Watcher Nodes können synthetische Transaktionen Benutzerkonten gemeinsam verwenden. Dies verlangsamt die Häufigkeit, mit der die Tests ausgeführt werden, wenn die Tests serialisiert werden, um Konflikte zu vermeiden. Synthetische Transaktionen werden standardmäßig alle 15 Minuten ausgeführt, um sicherzustellen, dass alle Tests Zeit zum Ausführen haben. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden möchten, können jetzt auch das Ausführungsintervall reduzieren.
    
- **Synthetische Transaktion der Video-Inop-Dienste** Kunden, die von Lösungen anderer Anbieter zu Skype for Business Server 2015 migrieren, möchten häufig weiterhin die Videotelekonferenzgeräte (VTCs) dieser anderen Anbieter verwenden. Video Interop Server ist eine neue Skype for Business Server 2015-Serverrolle, mit der Kunden weiterhin Cisco VTCs in ihren Konferenzräumen verwenden können, indem sie über einen Video-SIP-Trunk eine Verbindung mit Cisco CUCM herstellen. Dieses Feature fügt außerdem eine synthetische Transaktion hinzu, um zu überprüfen, ob der Video-Interop-Server verfügbar ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Anwendungsfreigabekonferenzen** Die End-to-End-Szenarioüberprüfung für Anwendungsfreigabekonferenzen wird jetzt unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachungsszenarien

Das Skype for Business Server 2015 Management Pack nutzt eine Vielzahl von Funktionen, mit deren Hilfe Sie Probleme erkennen und diagnostizieren können. Diese Features bieten einen Einblick in die Integrität einer Skype for Business Server 2015-Umgebung in Echtzeit.
  
|Überwachungsszenario|Beschreibung|
|:-----|:-----|
|Synthetische Transaktionen  <br/> | Windows PowerShell cmdlets zum Testen und Sicherstellen der hohen Verfügbarkeit von Szenarien wie Anmeldung, Anwesenheit, Telefonkonferenzen und Konferenzen für Benutzer. <br/> Die synthetischen Transaktionen können von jedem geografischen Standort aus ausgeführt werden, auch innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen.  <br/> Wenn bei einer synthetischen Transaktion ein Fehler auftritt, werden HTML-Protokolle erstellt, um die genaue Art des Fehlers zu ermitteln. Dazu gehört das Verständnis, welche Aktion fehlgeschlagen ist, die Wartezeit der einzelnen Aktionen, die zum Ausführen des Tests verwendete Befehlszeile und der spezifische aufgetretene Fehler.  <br/> |
|Warnungen zur Anrufzuverlässigkeit  <br/> |Von Skype for Business Server 2015-Servern verfasste Anrufdetaildatensätze (Call Detail Records, CDRs) geben an, ob Benutzer eine Verbindung mit einem Anruf herstellen können oder warum ein Anruf beendet wird. Warnungen zur Anrufzuverlässigkeit fragen die Datenbank für die Anrufzuverlässigkeit ab, um Warnungen zu erzeugen, die angeben, ob bei einer hohen Anzahl von Benutzern Verbindungsprobleme bei Peer-zu-Peer-Anrufen oder bei grundlegenden Konferenzfunktionen auftreten.  <br/> Die Szenarioabdeckung umfasst Audioanrufe, Peer-zu-Peer-Sofortnachrichten und andere Konferenzfunktionen.  <br/> |
|Warnungen zur Medienqualität  <br/> |Datenbankabfragen, die quality of experience (QoE)-Berichte anzeigen, die von Skype for Business Server 2015-Clients am Ende jedes Anrufs veröffentlicht werden. Diese Abfragen erzeugen Warnungen, die Szenarien heften, in denen die Medienqualität bei Anrufen und Konferenzen am wahrscheinlichsten beeinträchtigt wird. Die Daten bauen auf wichtigen Metriken wie Paketlatenz und -verlust auf, die direkt zur Qualität der Benutzerfreundlichkeit beitragen.  <br/> |
|Integritätswarnungen für Komponenten  <br/> |Einzelne Serverkomponenten auslösen Warnungen über Ereignisprotokolle und Leistungsindikatoren, um Fehlerbedingungen anzugeben, die sich erheblich auf Benutzerszenarien auswirken können. Diese Warnungen weisen auf eine Vielzahl von Bedingungen hin, z. B. nicht ausgeführte Dienste, hohe Fehlerraten, hohe Nachrichtenlatenz oder Konnektivitätsprobleme.  <br/> |
|Überwachung des Abhängigkeitszustands  <br/> |Skype for Business Server kann aus einer Vielzahl von externen Gründen fehlschlagen. Das Management Pack überwacht und sammelt Daten für kritische externe Abhängigkeiten, die auf schwerwiegende Probleme hinweisen können. Diese Abhängigkeiten umfassen die Verfügbarkeit der Internetinformationsdienste (IiS) und die CPU von Servern, die für Skype for Business Server verwendet werden.  <br/> |
|||
   
### <a name="alert-prioritization"></a>Warnungs priorisierung

Warnungen werden in die folgenden Kategorien unterteilt: 
  
 **Warnungen mit hoher Priorität:** Diese Warnungen weisen auf Bedingungen hin, die Dienstausfälle für große Benutzergruppen verursachen und sofortige Maßnahmen erfordern. Ausfälle, die von synthetischen Transaktionen und Offlinediensten (z. B. Skype for Business Server Audio/Video Conferencing) erkannt werden, gelten als Warnungen mit hoher Priorität. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype for Business Server 2015 verfügt über integrierte Hochverfügbarkeitsfunktionen für diese Situationen, z. B. mehrere Front-End-Server hinter Lastenausgleichssettern.
  
 **Warnungen mit mittlerer Priorität:** Diese Warnungen weisen auf Bedingungen hin, die sich auf eine Teilmenge von Benutzern auswirken oder auf Probleme in der Anrufqualität hinweisen, z. B. Komponentenfehler, Wartezeit bei der Anrufeinrichtung oder niedrigere Audioqualität bei Anrufen. Warnungen in dieser Kategorie sind statusreich (d. h. die Art der Warnung ändert sich basierend auf dem Status der Netzwerkverbindung).) Wenn z. B. die Zeiten für die Anrufereinrichtung die Latenz angeben, aber dann zu einem normalen Schwellenwert zurückkehren, würde diese Warnung mit mittlerer Priorität automatisch in System Center Operations Manager aufgelöst, und Administratoren müssten keine Maßnahmen ergreifen. Warnungen, die nicht automatisch aufgelöst werden können, werden in der Regel am selben Arbeitstag von Administratoren adressiert.
  
 **Weitere Warnungen:** Diese Warnungen werden von Komponenten generiert, die sich auf einen bestimmten Benutzer oder eine Teilmenge von Benutzern auswirken können. Eine typische Warnung wäre beispielsweise, dass der Adressbuchdienst den Active Directory® Domain Services (AD DS)-Eintrag für den Benutzer nicht analysieren konnte: testuser@contoso.com. Administratoren können diese Warnungen immer dann adressiert werden, wenn ihnen Zeit zur Verfügung steht.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype for Business Server 2015 Management Packs bieten eine höhere Abdeckung für Warnungen durch synthetische Transaktionen. Synthetische Transaktionen sind Windows PowerShell in das Operations Manager Management Pack integrierte Cmdlets, um End-to-End-Benutzerszenarien zu testen. Wenn Sie einen Server zum Ausführen synthetischer Transaktionen festlegen, werden diese Cmdlets regelmäßig vom Management Pack ausgelöst. Fehler, die sich aus einer synthetischen Transaktion ergeben, generieren eine Statuswarnung. Hier sind unterstützte synthetische Transaktionen für Skype for Business Server 2015:
  


|Unterstützte synthetische Transaktionen für Registrierung, Anwesenheit und Kontakte|||
|:-----|:-----|:-----|
|1   <br/> |Registrierung (Benutzeranmeldung)  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|2   <br/> |Adressbuchdienst (Dateidownload)  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|3   <br/> |Adressbuchwebabfrage  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|4   <br/> |Anwesenheit  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|5   <br/> |Einheitlicher Kontaktspeicher  <br/> |Verfügbarer Lync Server 2013 und darüber hinaus  <br/> |
||||   

|Unterstützte synthetische Transaktionen für Peer-to-Peer-Dienste|||
|:-----|:-----|:-----|
|6   <br/> |Peer-to-Peer-Sofortnachrichten  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|7   <br/> |Peer-to-Peer-Audiovideo  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|8   <br/> |MCX Peer-to-Peer Instant Message (mobil)  <br/> |Verfügbar in der September 2011-Version von Lync Server 2010 für Skype for Business 2015  <br/> |
 
> [!NOTE]
> Die McX (Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits unified Communications Web API (UCWA), um Chat, Anwesenheit und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.


|Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat|||
|:-----|:-----|:-----|
|9   <br/> |Audio/Video-Konferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|10   <br/> |Datenkonferenzen  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|11   <br/> |Chatkonferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|12   <br/> | Beständiger Chat <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|13   <br/> |Teilnehmen Startprogramm Besprechungen (geplante Besprechungen)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|14   <br/> |Einwahlkonferenzen  <br/> |Neu in Skype for Business Server 2015  <br/> |
|15   <br/> |Konferenz zur Anwendungsfreigabe  <br/> |Neu in Skype for Business Server 2015  <br/> |
|16   <br/> |UCWA Conference (Web Meeting Join)  <br/> |Neu in Skype for Business Server 2015  <br/> |
||||

|Unterstützte synthetische Transaktionen für Netzwerk- und Partnerabhängigkeiten|||
|:-----|:-----|:-----|
|17   <br/> |AV-Edge-Konnektivität  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|18   <br/> |AV Edge Connectivity Exchange Unified Message Connectivity (Voicemail)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|19  <br/> |PSTN Peer-to-Peer-Anruf  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|20  <br/> |XMPP Instant Messaging (Verbund)  <br/> |Verfügbar in Lync Server 2013 und Skype for Business 2015  <br/> |
| 21  <br/> |Video-Interoperabilitätsserver  <br/> |Neu in Skype for Business Server 2015  <br/> |
||||
   
## <a name="how-health-rolls-up"></a>So wird integritätsroll up

In der folgenden Tabelle sind die Integritätszustände von Objekten des Skype for Business Server Monitoring Packs aufgeführt.
  
|Management Pack (Objekt)|Beschreibung|
|:-----|:-----|
|Skype for Business Server Deployment  <br/> |Stellt die Bereitstellung von Skype for Business Server 2015 in der Organisation dar.  <br/> |
|Skype for Business Server Site  <br/> |Stellt verschiedene geografische Standorte dar, an denen Dienste bereitgestellt werden.  <br/> |
|Skype for Business Server Pool  <br/> |Ein Pool (innerhalb eines Standorts), der Kommunikationsdienste wie Chat und Konferenzen für Benutzer bietet. Gilt für Front-End-Pools, Edgepools und Director-Pools, auch wenn nur ein einzelner Computer in einem bestimmten Pool vorhanden ist.  <br/> |
|Skype for Business -Serverrolle  <br/> |Eine Serverrolle, die den Skype for Business Server Service hostet.  <br/> |
|Skype for Business Server Service  <br/> |Stellt eine Auf einem bestimmten Computer bereitgestellte Funktionalität dar (z. B. benutzerdienst auf fp01.contoso.com).  <br/> |
|Skype for Business Server Component  <br/> |Eine Komponente des Diensts (z. B. ist die Komponente "Adressbuchdownload" Teil des Webdiensts).  <br/> |
|Skype for Business Server Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Pool ausgeführt werden.  <br/> |
|Skype for Business Server Registrar Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Registrierungsstellenpool ausgeführt werden.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Benutzerdienstepool ausgeführt werden.  <br/> |
|Skype for Business Server Voice Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen einzigen Sprachpool ausgeführt werden.  <br/> |
|Skype for Business Server Port Watcher  <br/> |Eine Instanz von Portüberprüfungen, die für einen Pool ausgeführt werden.  <br/> |
|Watcher für einfache URLs  <br/> |Führt eine HTTPS-Probe der konfigurierten einfachen URLs in einer Bereitstellung durch.  <br/> |
   
![SCOM Rollup](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Ein Skype for Business Server-Pool kann mehrere einzelne Skype for Business Server-Systeme (mit mehr als einer Skype for Business Server-Rolle, einem Skype for Business Server-Dienst und einer Skype for Business Server-Komponente) enthalten. Daher ist der Ausfall eines einzelnen Servers oder einer Einzelnen Komponente weniger wichtig für die Allgemeine Integrität des Skype for Business Server-Pools, da andere Server im gleichen Pool den Anwendungsdienst für den Client bereitstellen können. Die Integrität wird in prozentualer Ebene in den Skype for Business Server-Pool rollups. 
  
Der Skype for Business Server-Pool-Watcher führt synthetische Transaktionen für einen Skype for Business Server-Pool aus. Aufeinanderfolgende Fehler bei einer oder mehreren synthetischen Transaktionen (ein Prozess, der als aufeinander folgendes Abrufintervall bezeichnet wird) führen ein Rollup des kritischen Integritätszustands auf Poolebene durch (am schlechtesten aller synthetischen Transaktionen), wie im folgenden Diagramm dargestellt. 
  
![Aufeinander folgende Abrufe des SCOM-Rollups](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Standardmäßig speichert Operations Manager alle Anpassungen, z. B. Außerkraftsetzungen, im Standardverwaltungspaket. Als bewährte Methode sollten Sie ein separates Management Pack für jedes versiegelte Management Pack erstellen, das Sie anpassen möchten. 
  
Wenn Sie ein Management Pack zum Speichern benutzerdefinierter Einstellungen für ein versiegeltes Management Pack erstellen, wird empfohlen, das neue Management Pack entsprechend zu benennen, z. B. "Skype for Business Server 2015 Customizations". 
  
Das Erstellen eines neuen Management Packs zum Speichern von Anpassungen jedes versiegelten Management Packs erleichtert das Exportieren der Anpassungen aus einer Testumgebung in eine Produktionsumgebung. Dies erleichtert auch das Löschen eines Management Packs, da Sie alle Abhängigkeiten löschen müssen, bevor Sie ein Management Pack löschen können. Wenn Anpassungen für alle Management Packs im Standardverwaltungspaket gespeichert werden und Sie ein einzelnes Management Pack löschen müssen, müssen Sie zuerst das Standardverwaltungspaket löschen, das auch Anpassungen an anderen Management Packs löscht. 
  
## <a name="links"></a>Links

Die folgenden Links verbinden Sie mit Informationen zu allgemeinen Aufgaben, die System Center 2012 Monitoring Packs zugeordnet sind:
  
- [Lebenszyklus des Management Packs](https://technet.microsoft.com/library/hh212732.aspx)
    
- [Importieren eines Management Packs in Operations Manager 2012](https://technet.microsoft.com/library/hh212691.aspx)
    
- [So überschreiben Sie eine Regel oder einen Monitor](https://technet.microsoft.com/library/hh212869.aspx)
    
- [So erstellen Sie ein "Als Konto ausführen" in Operations Manager 2012](https://technet.microsoft.com/library/hh321655.aspx)
    
- [Verwalten von "Als Konten und Profile ausführen"](https://technet.microsoft.com/library/hh212714.aspx)
    
- [So exportieren Sie ein Operations Manager Management Pack](https://technet.microsoft.com/library/hh320149.aspx)
    
- [So entfernen Sie ein Operations Manager Management Pack](https://technet.microsoft.com/library/hh230746.aspx)
    
Die folgenden Links verbinden Sie mit Informationen zu allgemeinen Aufgaben, die System Center 2007 Monitoring Packs zugeordnet sind:
  
- [Verwalten des Management Pack-Lebenszyklus](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [So importieren Sie ein Management Pack in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [So überwachen Sie die Verwendung von Außerkraftsetzungen](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [So erstellen Sie ein "Als Konto ausführen" in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [So ändern Sie eine vorhandene Ausführung als Profil](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [So exportieren Sie Management Pack-Anpassungen](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [So entfernen Sie ein Management Pack](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Fragen zu Operations Manager und Monitoring Packs finden Sie im Communityforum für [System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Eine nützliche Ressource ist der Blog "Entfesselt" von [System Center Operations Manager,](https://opsmgrunleashed.wordpress.com/) der "By Example"-Beiträge für bestimmte Monitoring Packs enthält.
  
Weitere Informationen zu Operations Manager finden Sie in den folgenden Blogs: 
  
- [Operations Manager Team Blog](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holmans Blog "OpsMgr"](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Gedanken zu OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog von "Desser"](https://rburri.wordpress.com/)
    
- [Verwaltungsbereich von BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Alle Informationen und Inhalte auf Nicht-Microsoft-Websites werden vom Besitzer oder den Benutzern der Website bereitgestellt. Microsoft übersennet keine ausdrücklichen, impliziten oder gesetzlichen Gewährleistungen für die Informationen auf dieser Website. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015-Verwaltungstools](../../management-tools/management-tools.md)
