---
title: Verwalten Skype for Business Server 2019 mithilfe des SCOM Management Packs
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/26/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Skype for Business Server 2019-Infrastruktur für die Arbeit mit System Center Operations Manager konfigurieren.'
ms.openlocfilehash: 2bb6e5600430cf8222d799fd42bade275d4e2f6d27fc6f6c4bfc05faad0e486d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277500"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Verwalten Skype for Business Server 2019 mithilfe des SCOM Management Packs
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Skype for Business Server 2019-Infrastruktur für die Arbeit mit System Center Operations Manager konfigurieren.
  
In einer idealen Welt treten nie Probleme mit Skype for Business Server 2019 auf. Skype for Business Server können jedoch von externen Faktoren beeinflusst werden, z. B. Netzwerkabstürzen und Hardwarefehlern. Mithilfe von Skype for Business Server 2019 Management Packs können Sie potenzielle Probleme proaktiv identifizieren und beheben. Auf diese Weise erweitern die Skype for Business Server 2019 Management Packs die Funktionen von System Center Operations Manager.
  
Diese Informationen wurden basierend auf Version 9319.0 des Monitoring Packs für Skype for Business Server 2019-Kommunikationssoftware geschrieben.
  
## <a name="configuration-overview"></a>Übersicht über die Konfiguration

 Um Ihre Skype for Business Server 2019-Infrastruktur für die Verwendung mit System Center Operations Manager zu konfigurieren, müssen Sie drei Schritte ausführen:
  
Identifizieren und [Konfigurieren des primären Verwaltungsservers.](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md) Dazu müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [konfigurieren Sie die Skype for Business Server Computer, die überwacht werden.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Um einen Skype for Business Server Computer mithilfe von System Center Operations Manager zu überwachen, müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server so konfigurieren, dass er als Proxy fungiert. 
  
 Identifizieren [und Installieren und Konfigurieren von Monitorknoten.](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md) Monitorknoten sind Computer, die in regelmäßigen Abständen Skype for Business Server synthetischen Transaktionen ausgeführt werden– Windows PowerShell Cmdlets, die überprüfen, ob Schlüssel Skype for Business Server Komponenten, z. B. die Möglichkeit, sich beim System anzumelden oder Chatnachrichten auszutauschen, erwartungsgemäß funktionieren. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager-Stammverwaltungsserver und Agent-Support

Die Management Packs können mit System Center Operations Manager 2007 R2 (64-Bit) (nur für Migrationszwecke unterstützt) oder System Center Operations Manager 2012 SP1 &amp; R2 (64-Bit) verwendet werden. In der folgenden Tabelle sind die unterstützten Konfigurationen für die Management Packs für Skype for Business Server 2019 aufgeführt: 
  
|**Konfiguration**|**Unterstützt?**|
|:-----|:-----|
|Windows Server 2008 R2-Betriebssystem  <br/> Windows Server 2012 R2-Betriebssystem  <br/> |Ja. Sowohl auf Skype for Business Server Server 2019 als auch auf Watcher-Knoten für synthetische Transaktionen.  <br/> |
|Gruppierte Server  <br/> |Nicht unterstützt  <br/> |
|Agentlose Überwachung  <br/> |Nicht unterstützt  <br/> |
|Virtuelle Umgebung  <br/> |Ja.  <br/> |
|Domänenverbundene Serverrollen  <br/> |Alle internen Serverrollen Skype for Business Server 2019 müssen in die Domäne eingebunden sein.  <br/> |
|Eigenständige Serverrollen  <br/> |Skype for Business Server 2019-Edgeserver müssen keiner Domäne angehören.  <br/> |
|Topologieeinschränkungen  <br/> |Alle Serverrollen in einer Bereitstellung müssen aus derselben Operations Manager-Verwaltungsgruppe überwacht werden.  <br/> |
|Watcher-Knoten für synthetische Transaktionen  <br/> |Die Verfügbarkeit des Überwachungsszenarios mit einem Watcher-Knoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration erforderlich). Watcher-Knoten müssen nicht in die Domäne eingebunden werden.  <br/> |
   
In der folgenden Tabelle sind die Kapazitäts- und Betriebssystemanforderungen für einen Watcher-Knoten für synthetische Transaktionen aufgeführt:
  
|**Hardwarekomponente**|**Mindestanforderung**|
|:-----|:-----|
|CPU  <br/> |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Vierkern, 2,33 GHz oder höher  <br/> 64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher  <br/> |
|Arbeitsspeicher  <br/> |8 GB  <br/> |
|Betriebssystem  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Netzwerk  <br/> |1 Netzwerkadapter bei 1 GBit/s  <br/> |
   
## <a name="prerequisites"></a>Voraussetzungen

Um einen Watcher-Knoten für synthetische Transaktionen auszuführen, müssen Sie zuerst Folgendes installieren:
  
- System Center Operations Manager-Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server wichtigsten Installationsdateien (OcsCore.msi) und Unified Communications Managed API (UCMA) (Versionen müssen mit der Skype for Business Server WatcherNode.msi Version übereinstimmen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Monitoring Pack

Das Monitoring Pack für Skype for Business Server 2019 enthält die folgenden Dateien:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu in Skype for Business Server 2019 Management Packs.

- Änderungen im Update vom **[September 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Bei einigen Warnungen wurden Sonderzeichen entfernt. In einigen Fällen beeinträchtigen Sonderzeichen die Benachrichtigungsfunktion des SCOM-Befehlskanals.

- **Automatische Ermittlung für die Clientanmeldung** Clientanwendungen, die sich bei Skype for Business Server 2019 anmelden, ermitteln häufig automatisch den Server für die Anmeldung. Synthetische Transaktionen unterstützen jetzt die Überprüfung, dass die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Benutzerdefinierte Ausführungsintervalle für synthetische Transaktionen** Zur Vereinfachung des Einrichtungsprozesses von Watcher-Knoten können synthetische Transaktionen Benutzerkonten freigeben. Dadurch wird die Häufigkeit verlangsamt, mit der die Tests ausgeführt werden, während die Tests serialisiert werden, um Konflikte zu vermeiden. Standardmäßig werden synthetische Transaktionen alle 15 Minuten ausgeführt, um sicherzustellen, dass alle Tests über genügend Zeit zum Ausführen verfügen. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden möchten, können jetzt auch das Ausführungsintervall reduzieren.
    
- **Synthetische Transaktion für Video-Interoperabilitätsdienste** Kunden, die von Lösungen anderer Anbieter zu Skype for Business Server 2019 migrieren, möchten häufig weiterhin die Videotelekonferenzgeräte (Video Teleconferencing Devices, VTCs) von diesen anderen Anbietern verwenden. Video Interop Server ist eine neue Skype for Business Server 2019-Serverrolle, mit der Kunden weiterhin Cisco-VTCs in ihren Konferenzräumen verwenden können, indem sie eine Verbindung mit Cisco CUCM über einen Video-SIP-Trunk herstellen. Dieses Feature fügt auch eine synthetische Transaktion hinzu, um zu überprüfen, ob der Video-Interoperabilitätsserver aktiv ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Anwendungsfreigabekonferenzen** Die End-to-End-Szenarioüberprüfung für Anwendungsfreigabekonferenzen wird jetzt unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachungsszenarien

Das Skype for Business Server 2019 Management Pack nutzt eine Vielzahl von Features, mit denen Sie Probleme erkennen und diagnostizieren können. Diese Features bieten einen Einblick in die Integrität einer Skype for Business Server 2019-Umgebung in Echtzeit.
  
|**Überwachungsszenario**|**Beschreibung**|
|:-----|:-----|
|Synthetische Transaktionen  <br/> | Windows PowerShell Cmdlets, um eine hohe Verfügbarkeit von Szenarien wie Anmeldung, Anwesenheit, Chat und Konferenzen für Benutzer zu testen und sicherzustellen. <br/> Die synthetischen Transaktionen können von jedem geografischen Standort aus ausgeführt werden, einschließlich innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen.  <br/> Wenn eine synthetische Transaktion fehlschlägt, werden HTML-Protokolle erstellt, um die genaue Art des Fehlers zu ermitteln. Dazu gehören das Verständnis, welche Aktion fehlgeschlagen ist, die Latenz der einzelnen Aktionen, die zum Ausführen des Tests verwendete Befehlszeile und der spezifische Fehler, der aufgetreten ist.  <br/> |
|Warnungen zur Anruf zuverlässigkeit  <br/> |Von Skype for Business Server 2019-Servern geschriebene Kommunikationsdatensätze (KDS) geben an, ob Benutzer eine Verbindung mit einem Anruf herstellen können oder warum ein Anruf beendet wird. Anrufzuverlässigkeitswarnungen fragen die KDS-Datenbank ab, um Warnungen zu erstellen, die angeben, wenn bei einer hohen Anzahl von Benutzern Konnektivitätsprobleme bei Peer-to-Peer-Anrufen oder grundlegenden Konferenzfunktionen auftreten.  <br/> Die Szenarioabdeckung umfasst Audioanrufe, Peer-to-Peer-Chatnachrichten und andere Konferenzfunktionen.  <br/> |
|Warnungen zur Medienqualität  <br/> |Datenbankabfragen mit QoE-Berichten (Quality of Experience), die von Skype for Business Server 2019-Clients am Ende jedes Anrufs veröffentlicht wurden. Diese Abfragen erzeugen Warnungen, die Szenarien anheften, in denen Die Medienqualität bei Anrufen und Konferenzen am wahrscheinlichsten beeinträchtigt wird. Die Daten basieren auf wichtigen Metriken, z. B. Paketlatenz und -verlust, die direkt zur Qualität der Benutzererfahrung beitragen.  <br/> |
|Warnungen zur Komponentenintegrität  <br/> |Einzelne Serverkomponenten lösen Warnungen über Ereignisprotokolle und Leistungsindikatoren aus, um Fehlerbedingungen anzugeben, die sich erheblich auf Benutzerszenarien auswirken können. Diese Warnungen weisen auf eine Vielzahl von Bedingungen hin, z. B. nicht ausgeführte Dienste, hohe Fehlerraten, hohe Nachrichtenlatenz oder Konnektivitätsprobleme.  <br/> |
|Überwachung der Abhängigkeitsintegrität  <br/> |Skype for Business Server kann aus verschiedenen externen Gründen fehlschlagen. Das Management Pack überwacht und sammelt Daten für kritische externe Abhängigkeiten, die auf schwerwiegende Probleme hinweisen können. Diese Abhängigkeiten umfassen die Verfügbarkeit von Internetinformationsdienste (IIS) und die CPU von Servern, die für Skype for Business Server verwendet werden.  <br/> |
   
### <a name="alert-prioritization"></a>Priorisierung von Warnungen

Warnungen werden in die folgenden Kategorien unterteilt: 
  
 **Warnungen mit hoher Priorität:** Diese Warnungen weisen auf Bedingungen hin, die zu Dienstausfällen für große Benutzergruppen führen und sofortige Maßnahmen erfordern. Ausfälle, die von synthetischen Transaktionen und Offlinediensten (z. B. Skype for Business Server Audio-/Videokonferenzen) erkannt werden, gelten als Warnungen mit hoher Priorität. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype for Business Server 2019 verfügt über integrierte Hochverfügbarkeitsfunktionen für diese Situationen, z. B. mehrere Front-End-Server hinter Lastenausgleichsservern.
  
 **Warnungen mit mittlerer Priorität:** Diese Warnungen deuten auf Bedingungen hin, die sich auf eine Teilmenge von Benutzern auswirken, oder weisen auf Probleme bei der Anrufqualität hin, z. B. Komponentenfehler, Latenz beim Anrufaufbau oder niedrigere Audioqualität bei Anrufen. Warnungen in dieser Kategorie sind zustandsbehaftet (d. h. die Art der Warnung ändert sich basierend auf dem Status der Netzwerkverbindung.) Wenn z. B. die Zeiten für die Anruferstellung auf Latenz hindeuten, dann aber zu einem normalen Schwellenwert zurückkehren, würde diese Warnung mit mittlerer Priorität automatisch in System Center Operations Manager aufgelöst werden, und Administratoren müssten keine Maßnahmen ergreifen. Warnungen, die nicht automatisch aufgelöst werden können, werden in der Regel am selben Geschäftstag von Administratoren behoben.
  
 **Weitere Warnungen:** Diese Warnungen werden von Komponenten generiert, die sich auf einen bestimmten Benutzer oder eine Teilmenge von Benutzern auswirken können. Eine typische Warnung wäre beispielsweise, dass der Adressbuchdienst den Active Directory® Domain Services (AD DS)-Eintrag für den Benutzer nicht analysieren konnte: testuser@contoso.com. Administratoren können diese Warnungen jederzeit beheben, wenn Zeit verfügbar ist.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype for Business Server 2019 Management Packs bieten eine höhere Abdeckung für Warnungen durch synthetische Transaktionen. Synthetische Transaktionen sind Windows PowerShell Cmdlets, die in das Operations Manager Management Pack integriert sind, um End-to-End-Benutzerszenarien zu testen. Wenn Sie einen Server zum Ausführen synthetischer Transaktionen festlegen, werden diese Cmdlets in regelmäßigen Abständen vom Management Pack ausgelöst. Fehler aufgrund einer synthetischen Transaktion generieren eine zustandsbehaftete Warnung. Im Folgenden werden synthetische Transaktionen für Skype for Business Server 2019 unterstützt:
  
**Unterstützte synthetische Transaktionen für Registrierung, Anwesenheit und Kontakte**

||||
|:-----|:-----|:-----|
|1  <br/> |Registrierung (Benutzeranmeldung)  <br/> |Verfügbarer Lync Server 2010 und höher  <br/> |
|2  <br/> |Adressbuchdienst (Dateidownload)  <br/> |Verfügbarer Lync Server 2010 und höher  <br/> |
|3  <br/> |Adressbuchwebabfrage  <br/> |Verfügbarer Lync Server 2010 und höher  <br/> |
|4   <br/> |Anwesenheit  <br/> |Verfügbarer Lync Server 2010 und höher  <br/> |
|5   <br/> |Einheitlicher Kontaktspeicher  <br/> |Verfügbarer Lync Server 2013 und höher  <br/> |
   
**Unterstützte synthetische Transaktionen für Peer-to-Peer-Dienste**

||||
|:-----|:-----|:-----|
|6   <br/> |Peer-to-Peer-Chat  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|7   <br/> |Peer-to-Peer-Audiovideo  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|8   <br/> |MCX-Peer-zu-Peer-Chatnachricht (mobil)  <br/> |Verfügbar in der Version vom September 2011 von Lync Server 2010 bis Skype for Business 2019  <br/> |
 
> [!NOTE]
> MCX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.
  
**Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat**

||||
|:-----|:-----|:-----|
|9   <br/> |Audio/Video-Konferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|10   <br/> |Datenkonferenzen  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|11  <br/> |Chatkonferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|12   <br/> | Beständiger Chat <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|13  <br/> |Teilnehmen an Startprogramm (geplante Besprechungen)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|14   <br/> |Einwahlkonferenzen  <br/> |Ab Skype for Business Server 2015 verfügbar <br/> |
|15  <br/> |Konferenzen zur Anwendungsfreigabe  <br/> |Ab Skype for Business Server 2015 verfügbar <br/> |
|16   <br/> |UCWA-Konferenz (Webbesprechung)  <br/> |Ab Skype for Business Server 2015 verfügbar <br/> |
   
**Unterstützte synthetische Transaktionen für Netzwerk- und Partnerabhängigkeiten**

||||
|:-----|:-----|:-----|
|17   <br/> |AV-Edgekonnektivität  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|18   <br/> |AV Edge Connectivity Exchange Unified Message Connectivity (Voicemail)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|19  <br/> |PSTN-Peer-to-Peer-Anruf  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|20  <br/> |XMPP-Chat (Partnerverbund)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
| 21  <br/> |Video-Interoperabilitätsserver  <br/> |Ab Skype for Business Server 2015 verfügbar  <br/> |
   
## <a name="how-health-rolls-up"></a>Roll-up für Integrität

In der folgenden Tabelle sind die Integritätszustände von Objekten dargestellt, die vom Skype for Business Server Monitoring Pack verwendet werden.
  
|**Management Pack-Objekt**|**Beschreibung**|
|:-----|:-----|
|Skype for Business Server Einsatz  <br/> |Stellt die Bereitstellung von Skype for Business Server 2019 in der Organisation dar.  <br/> |
|Skype for Business Server Website  <br/> |Stellt unterschiedliche geografische Standorte dar, an denen Dienste bereitgestellt werden.  <br/> |
|Skype for Business Server Pool  <br/> |Ein Pool (innerhalb eines Standorts), der Benutzern Kommunikationsdienste wie Chat und Konferenzen bereitstellt. Gilt für Front-End-Pools, Edgepools und Directorpools, auch wenn sich nur ein einzelner Computer in einem bestimmten Pool befindet.  <br/> |
|Skype for Business Server Rolle  <br/> |Eine Serverrolle, die Skype for Business Server Dienst hostet.  <br/> |
|Skype for Business Server Service  <br/> |Stellt eine Funktionalität dar, die auf einem bestimmten Computer bereitgestellt wird (z. B. Benutzerdienst auf fp01.contoso.com).  <br/> |
|Skype for Business Server Komponente  <br/> |Eine Komponente des Diensts (z. B. ist die Adressbuchdownloadkomponente Teil des Webdiensts).  <br/> |
|Skype for Business Server Poolüberwachung  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Pool ausgeführt werden.  <br/> |
|Skype for Business Server Registrar Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Registrierungsstellenpool ausgeführt werden.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Benutzerdienstpool ausgeführt werden.  <br/> |
|Skype for Business Server VoIP-Poolüberwachung  <br/> |Eine Instanz synthetischer Transaktionen, die für einen VoIP-Pool ausgeführt werden.  <br/> |
|Skype for Business Server Portüberwachung  <br/> |Eine Instanz von Portüberprüfungen, die für einen Pool ausgeführt werden.  <br/> |
|Watcher für einfache URLs  <br/> |Führt HTTPS-Untersuchung der konfigurierten einfachen URLs in einer Bereitstellung aus.  <br/> |
   
![SCOM-Rollup](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Ein Skype for Business Server Pool kann mehrere einzelne Skype for Business Server Systeme enthalten (mit mehr als einer Skype for Business Server Rolle, Skype for Business Server Dienst und Skype for Business Server Komponente). Daher ist der Ausfall eines einzelnen Servers oder einer Komponente weniger wichtig für den Gesamtzustand des Skype for Business Server Pools, da andere Server im selben Pool den Anwendungsdienst für den Client bereitstellen können. Die Integrität wird auf prozentualer Ebene für den Skype for Business Server-Pool rollt. 
  
Der Skype for Business Server Pool watcher führt synthetische Transaktionen für einen Skype for Business Server Pool aus. Durch aufeinander folgende Fehler einer oder mehrerer synthetischer Transaktionen (ein Prozess, der als aufeinander folgendes Abrufintervall bezeichnet wird) wird der kritische Integritätsstatus auf Poolebene (die schlechteste aller synthetischen Transaktionen) wie im folgenden Diagramm dargestellt. 
  
![Aufeinanderfolgende Abfragen des SCOM-Rollups](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Operations Manager speichert standardmäßig alle Anpassungen, z. B. Außerkraftsetzungen im Standardverwaltungspaket. Als bewährte Methode sollten Sie ein separates Management Pack für jedes versiegelte Management Pack erstellen, das Sie anpassen möchten. 
  
Wenn Sie ein Management Pack zum Speichern benutzerdefinierter Einstellungen für ein versiegeltes Management Pack erstellen, empfehlen wir, das neue Management Pack entsprechend zu benennen, z. B. "Skype for Business Server 2019-Anpassungen".
  
Das Erstellen eines neuen Management Packs zum Speichern von Anpassungen der einzelnen versiegelten Management Packs erleichtert das Exportieren der Anpassungen aus einer Testumgebung in eine Produktionsumgebung. Dies erleichtert auch das Löschen eines Management Packs, da Sie alle Abhängigkeiten löschen müssen, bevor Sie ein Management Pack löschen können. Wenn Anpassungen für alle Management Packs im Standardverwaltungspaket gespeichert werden und Sie ein einzelnes Management Pack löschen müssen, müssen Sie zuerst das Default Management Pack löschen, das auch Anpassungen an anderen Management Packs löscht. 
  
## <a name="links"></a>Links

Die folgenden Links verbinden Sie mit Informationen zu allgemeinen Aufgaben, die System Center 2012 Monitoring Packs zugeordnet sind:
  
- [Management Pack-Lebenszyklus](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [Importieren eines Management Packs in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [So überschreiben Sie eine Regel oder einen Monitor](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [So erstellen Sie ein Konto ausführen in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [Verwalten von "Als Konten und Profile ausführen"](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [So exportieren Sie ein Operations Manager Management Pack](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [So entfernen Sie ein Operations Manager Management Pack](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
Die folgenden Links verbinden Sie mit Informationen zu allgemeinen Aufgaben, die System Center 2007 Monitoring Packs zugeordnet sind:
  
- [Verwalten des Management Pack-Lebenszyklus](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [Importieren eines Management Packs in Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [Überwachen mithilfe von Außerkraftsetzungen](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [So erstellen Sie eine Ausführung als Konto in Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [So ändern Sie eine vorhandene Ausführung als Profil](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [Exportieren von Management Pack-Anpassungen](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [So entfernen Sie ein Management Pack](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
Fragen zu Operations Manager und Überwachungspaketen finden Sie im [Community-Forum System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Eine hilfreiche Ressource ist der [Blog System Center Operations Manager-Entfesselung,](https://opsmgrunleashed.wordpress.com/) der Beiträge "Nach Beispiel" für bestimmte Überwachungspakete enthält.
  
Weitere Informationen zu Operations Manager finden Sie in den folgenden Blogs: 
  
- [Operations Manager Team Blog](https://blogs.technet.com/momteam/default.aspx)
    
- [OpsMgr-Blog von Kevin Holman](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Gedanken zu OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog von "Unterzung Bile"](https://rburri.wordpress.com/)
    
- [Verwaltungsbereich von BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Alle Informationen und Inhalte auf Nicht-Microsoft-Websites werden vom Besitzer oder den Benutzern der Website bereitgestellt. Microsoft übernimmt keine garantiernden, ausdrücklichen, konkludenten oder gesetzlichen Garantien hinsichtlich der Informationen auf dieser Website. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2019-Verwaltungstools](../management-tools-2019.md)