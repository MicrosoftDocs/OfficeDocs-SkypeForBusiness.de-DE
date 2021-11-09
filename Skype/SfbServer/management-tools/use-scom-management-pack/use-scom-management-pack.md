---
title: Verwalten von Skype for Business Server 2015 mithilfe des SCOM Management Packs
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Arbeit mit System Center Operations Manager konfigurieren.'
ms.openlocfilehash: 4fb6d0c900285b473012d5f9051f25c8c30320f6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836287"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Verwalten von Skype for Business Server 2015 mithilfe des SCOM Management Packs
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für System Center Operations Manager konfigurieren.
  
In einer idealen Welt treten nie Probleme mit Skype for Business Server 2015 auf. Skype for Business Server können jedoch von externen Faktoren betroffen sein, z. B. Netzwerkabstürzen und Hardwarefehlern. Mithilfe Skype for Business Server 2015 Management Packs können Sie potenzielle Probleme proaktiv identifizieren und beheben. Auf diese Weise erweitern die Skype for Business Server 2015 Management Packs die Funktionen von System Center Operations Manager.
  
Diese Informationen wurden basierend auf Version 9319.0 des Monitoring Packs für Skype for Business Server 2015-Kommunikationssoftware geschrieben.
  
## <a name="configuration-overview"></a>Übersicht über die Konfiguration

 Um Ihre Skype for Business Server 2015-Infrastruktur für die Verwendung mit System Center Operations Manager zu konfigurieren, müssen Sie drei Schritte ausführen:
  
Identifizieren und [Konfigurieren des primären Verwaltungsservers.](configure-the-primary.md) Dazu müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [konfigurieren Sie die Skype for Business Server Computer, die überwacht werden.](configure-computers-to-monitor.md) Um einen Skype for Business Server Computer mithilfe von System Center Operations Manager zu überwachen, müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server so konfigurieren, dass er als Proxy fungiert. 
  
 Identifizieren [und Installieren und Konfigurieren von Monitorknoten.](watcher-nodes.md) Monitorknoten sind Computer, die in regelmäßigen Abständen Skype for Business Server synthetischen Transaktionen ausgeführt werden– Windows PowerShell Cmdlets, die überprüfen, ob schlüssel Skype for Business Server Komponenten, z. B. die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum Austauschen von Chatnachrichten, erwartungsgemäß funktionieren. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager-Stammverwaltungsserver und Agent-Support

Die Management Packs können mit System Center Operations Manager 2007 R2 (64-Bit) (nur für Migrationszwecke unterstützt) oder System Center Operations Manager 2012 SP1 &amp; R2 (64-Bit) oder System Center Operations Manager 2016 (64-Bit) verwendet werden. In der folgenden Tabelle sind die unterstützten Konfigurationen für die Management Packs für Skype for Business Server 2015 aufgeführt: 
  
|Konfiguration|Unterstützt?|
|:-----|:-----|
|Windows Server 2008 R2-Betriebssystem  <br/> Windows Server 2012 R2-Betriebssystem   |Ja. Sowohl auf Skype for Business Server Server 2015 als auch auf Monitorknoten für synthetische Transaktionen.   |
|Gruppierte Server   |Nicht unterstützt   |
|Agentlose Überwachung   |Nicht unterstützt   |
|Virtuelle Umgebung   |Ja.   |
|Domänenverbundene Serverrollen   |Alle internen Skype for Business Server 2015-Serverrollen müssen domänenverbunden sein.   |
|Eigenständige Serverrollen   |Skype for Business Server 2015-Edgeserver müssen nicht in die Domäne eingebunden werden.   |
|Topologieeinschränkungen   |Alle Serverrollen in einer Bereitstellung müssen aus derselben Operations Manager-Verwaltungsgruppe überwacht werden.   |
|Watcher-Knoten für synthetische Transaktionen   |Die Verfügbarkeit des Überwachungsszenarios mit einem Watcher-Knoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration erforderlich). Watcher-Knoten müssen nicht in die Domäne eingebunden werden.   |
   
In der folgenden Tabelle sind die Kapazitäts- und Betriebssystemanforderungen für einen Watcher-Knoten für synthetische Transaktionen aufgeführt:
  
|Hardwarekomponente|Mindestanforderung|
|:-----|:-----|
|CPU   |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Vierkern, 2,33 GHz oder höher  <br/> 64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher   |
|Arbeitsspeicher   |8 GB   |
|Betriebssystem   |Windows Server 2008 R2  <br/> Windows Server 2012 R2   |
|Netzwerk   |1 Netzwerkadapter bei 1 GBit/s   |
   
## <a name="prerequisites"></a>Voraussetzungen

Um einen Watcher-Knoten für synthetische Transaktionen auszuführen, müssen Sie zuerst Folgendes installieren:
  
- System Center Operations Manager-Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server hauptinstallationsdateien (OcsCore.msi) und Unified Communications Managed API (UCMA) (Versionen müssen mit der Skype for Business Server WatcherNode.msi Version übereinstimmen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Monitoring Pack

Das Monitoring Pack für Skype for Business Server 2015 enthält die folgenden Dateien:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu in Skype for Business Server 2015 Management Packs.

- Änderungen im Update vom **[September 2019](https://www.microsoft.com/en-in/download/details.aspx?id=47364)** Bei einigen Warnungen wurden Sonderzeichen entfernt. In einigen Fällen beeinträchtigen Sonderzeichen die Benachrichtigungsfunktion des SCOM-Befehlskanals.

- **Automatische Ermittlung für die Clientanmeldung** Clientanwendungen, die sich bei Skype for Business Server 2015 anmelden, ermitteln häufig automatisch den Server für die Anmeldung. Synthetische Transaktionen unterstützen jetzt die Überprüfung, dass die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Benutzerdefinierte Ausführungsintervalle für synthetische Transaktionen** Zur Vereinfachung des Einrichtungsprozesses von Watcher-Knoten können synthetische Transaktionen Benutzerkonten freigeben. Dadurch wird die Häufigkeit verlangsamt, mit der die Tests ausgeführt werden, während die Tests serialisiert werden, um Konflikte zu vermeiden. Standardmäßig werden synthetische Transaktionen alle 15 Minuten ausgeführt, um sicherzustellen, dass alle Tests über genügend Zeit zum Ausführen verfügen. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden möchten, können jetzt auch das Ausführungsintervall reduzieren.
    
- **Synthetische Transaktion für Video-Interoperabilitätsdienste** Kunden, die von Lösungen anderer Anbieter zu Skype for Business Server 2015 migrieren, möchten häufig weiterhin die Videotelekonferenzgeräte (Video Teleconferencing Devices, VTCs) von diesen anderen Anbietern verwenden. Video Interop Server ist eine neue Skype for Business Server 2015-Serverrolle, mit der Kunden weiterhin Cisco-VTCs in ihren Konferenzräumen verwenden können, indem sie sich über einen Video-SIP-Trunk mit Cisco CUCM verbinden. Dieses Feature fügt auch eine synthetische Transaktion hinzu, um zu überprüfen, ob der Video-Interoperabilitätsserver aktiv ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Anwendungsfreigabekonferenzen** Die End-to-End-Szenarioüberprüfung für Anwendungsfreigabekonferenzen wird jetzt unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachungsszenarien

Das Skype for Business Server 2015 Management Pack nutzt eine Vielzahl von Features, mit denen Sie Probleme erkennen und diagnostizieren können. Diese Features bieten einen Einblick in die Integrität einer Skype for Business Server 2015-Umgebung in Echtzeit.
  
|Überwachungsszenario|Beschreibung|
|:-----|:-----|
|Synthetische Transaktionen   | Windows PowerShell Cmdlets, um eine hohe Verfügbarkeit von Szenarien wie Anmeldung, Anwesenheit, Chat und Konferenzen für Benutzer zu testen und sicherzustellen. <br/> Die synthetischen Transaktionen können von jedem geografischen Standort aus ausgeführt werden, einschließlich innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen.  <br/> Wenn eine synthetische Transaktion fehlschlägt, werden HTML-Protokolle erstellt, um die genaue Art des Fehlers zu ermitteln. Dazu gehören das Verständnis, welche Aktion fehlgeschlagen ist, die Latenz der einzelnen Aktionen, die zum Ausführen des Tests verwendete Befehlszeile und der spezifische Fehler, der aufgetreten ist.   |
|Warnungen zur Anruf zuverlässigkeit   |Von Skype for Business Server 2015-Servern geschriebene Kommunikationsdatensätze (KDS) geben an, ob Benutzer in der Lage sind, eine Verbindung mit einem Anruf herzustellen oder warum ein Anruf beendet wird. Anrufzuverlässigkeitswarnungen fragen die KDS-Datenbank ab, um Warnungen zu erstellen, die angeben, wenn bei einer hohen Anzahl von Benutzern Konnektivitätsprobleme bei Peer-to-Peer-Anrufen oder grundlegenden Konferenzfunktionen auftreten.  <br/> Die Szenarioabdeckung umfasst Audioanrufe, Peer-to-Peer-Chatnachrichten und andere Konferenzfunktionen.   |
|Warnungen zur Medienqualität   |Datenbankabfragen mit QoE-Berichten (Quality of Experience), die von Skype for Business Server 2015-Clients am Ende jedes Anrufs veröffentlicht wurden. Diese Abfragen erzeugen Warnungen, die Szenarien anheften, in denen Die Medienqualität bei Anrufen und Konferenzen am wahrscheinlichsten beeinträchtigt wird. Die Daten basieren auf wichtigen Metriken, z. B. Paketlatenz und -verlust, die direkt zur Qualität der Benutzererfahrung beitragen.   |
|Warnungen zur Komponentenintegrität   |Einzelne Serverkomponenten lösen Warnungen über Ereignisprotokolle und Leistungsindikatoren aus, um Fehlerbedingungen anzugeben, die sich erheblich auf Benutzerszenarien auswirken können. Diese Warnungen weisen auf eine Vielzahl von Bedingungen hin, z. B. nicht ausgeführte Dienste, hohe Fehlerraten, hohe Nachrichtenlatenz oder Konnektivitätsprobleme.   |
|Überwachung der Abhängigkeitsintegrität   |Skype for Business Server kann aus verschiedenen externen Gründen fehlschlagen. Das Management Pack überwacht und sammelt Daten für kritische externe Abhängigkeiten, die auf schwerwiegende Probleme hinweisen können. Diese Abhängigkeiten umfassen die Verfügbarkeit von Internetinformationsdienste (IIS) und die CPU von Servern, die für Skype for Business Server verwendet werden.   |

   
### <a name="alert-prioritization"></a>Priorisierung von Warnungen

Warnungen werden in die folgenden Kategorien unterteilt: 
  
 **Warnungen mit hoher Priorität:** Diese Warnungen weisen auf Bedingungen hin, die zu Dienstausfällen für große Benutzergruppen führen und sofortige Maßnahmen erfordern. Ausfälle, die von synthetischen Transaktionen und Offlinediensten (z. B. Skype for Business Server Audio-/Videokonferenzen) erkannt werden, gelten als Warnungen mit hoher Priorität. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype for Business Server 2015 verfügt über integrierte Hochverfügbarkeitsfeatures für diese Situationen, z. B. mehrere Front-End-Server hinter Lastenausgleichsservern.
  
 **Warnungen mit mittlerer Priorität:** Diese Warnungen deuten auf Bedingungen hin, die sich auf eine Teilmenge von Benutzern auswirken, oder weisen auf Probleme bei der Anrufqualität hin, z. B. Komponentenfehler, Latenz beim Anrufaufbau oder niedrigere Audioqualität bei Anrufen. Warnungen in dieser Kategorie sind zustandsbehaftet (d. h. die Art der Warnung ändert sich basierend auf dem Status der Netzwerkverbindung.) Wenn z. B. die Zeiten für die Anruferstellung auf Latenz hinweisen, dann aber wieder zu einem normalen Schwellenwert zurückkehren, würde diese Warnung mit mittlerer Priorität automatisch in System Center Operations Manager aufgelöst werden, und Administratoren müssten keine Maßnahmen ergreifen. Warnungen, die nicht automatisch aufgelöst werden können, werden in der Regel am selben Geschäftstag von Administratoren behoben.
  
 **Weitere Warnungen:** Diese Warnungen werden von Komponenten generiert, die sich auf einen bestimmten Benutzer oder eine Teilmenge von Benutzern auswirken können. Eine typische Warnung wäre beispielsweise, dass der Adressbuchdienst den Active Directory® Domain Services (AD DS)-Eintrag für den Benutzer nicht analysieren konnte: testuser@contoso.com. Administratoren können diese Warnungen jederzeit beheben, wenn Zeit verfügbar ist.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype for Business Server 2015 Management Packs bieten eine höhere Abdeckung für Warnungen durch synthetische Transaktionen. Synthetische Transaktionen sind Windows PowerShell Cmdlets, die in das Operations Manager Management Pack integriert sind, um End-to-End-Benutzerszenarien zu testen. Wenn Sie einen Server zum Ausführen synthetischer Transaktionen festlegen, werden diese Cmdlets in regelmäßigen Abständen vom Management Pack ausgelöst. Fehler aufgrund einer synthetischen Transaktion generieren eine zustandsbehaftete Warnung. Im Folgenden werden synthetische Transaktionen für Skype for Business Server 2015 unterstützt:
  


|Unterstützte synthetische Transaktionen für Registrierung, Anwesenheit und Kontakte|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|1   |Registrierung (Benutzeranmeldung)   |Verfügbarer Lync Server 2010 und höher   |
|2   |Adressbuchdienst (Dateidownload)   |Verfügbarer Lync Server 2010 und höher   |
|3   |Adressbuchwebabfrage   |Verfügbarer Lync Server 2010 und höher   |
|4   |Anwesenheit   |Verfügbarer Lync Server 2010 und höher   |
|5   |Einheitlicher Kontaktspeicher   |Verfügbarer Lync Server 2013 und höher   |

  

|Unterstützte synthetische Transaktionen für Peer-to-Peer-Dienste|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|6    |Peer-to-Peer-Chat   |Verfügbar in Lync Server 2010 und darüber hinaus   |
|7    |Peer-to-Peer-Audiovideo   |Verfügbar in Lync Server 2010 und darüber hinaus   |
|8    |MCX-Peer-zu-Peer-Chatnachricht (mobil)   |Verfügbar in der Version vom September 2011 von Lync Server 2010 bis Skype for Business 2015   |
 
> [!NOTE]
> McX(Mobility Service)-Unterstützung für mobile Legacyclients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen Skype for Business mobile Clients verwenden bereits Unified Communications Web API (UCWA), um Chatnachrichten, Anwesenheitsinformationen und Kontakte zu unterstützen. Benutzer mit Legacyclients, die MCX verwenden, müssen auf einen aktuellen Client aktualisieren.


|Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|9    |Audio/Video-Konferenzen   |Verfügbar in Lync Server 2010 und darüber hinaus   |
|10   |Datenkonferenzen   |Verfügbar in Lync Server 2013 und darüber hinaus   |
|11   |Chatkonferenzen   |Verfügbar in Lync Server 2010 und darüber hinaus   |
|12    | Beständiger Chat  |Verfügbar in Lync Server 2013 und darüber hinaus   |
|13   |Teilnehmen an Startprogramm (geplante Besprechungen)   |Verfügbar in Lync Server 2013 und darüber hinaus   |
|14    |Einwahlkonferenzen   |Neu in Skype for Business Server 2015   |
|15    |Konferenzen zur Anwendungsfreigabe   |Neu in Skype for Business Server 2015   |
|16   |UCWA-Konferenz (Webbesprechung)   |Neu in Skype for Business Server 2015   |


|Unterstützte synthetische Transaktionen für Netzwerk- und Partnerabhängigkeiten|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|17    |AV-Edgekonnektivität   |Verfügbar in Lync Server 2013 und darüber hinaus   |
|18    |AV Edge Connectivity Exchange Unified Message Connectivity (Voicemail)   |Verfügbar in Lync Server 2013 und darüber hinaus   |
|19   |PSTN-Peer-to-Peer-Anruf   |Verfügbar in Lync Server 2010 und darüber hinaus   |
|20   |XMPP-Chat (Partnerverbund)   |Verfügbar in Lync Server 2013 und Skype for Business 2015   |
| 21   |Video-Interoperabilitätsserver   |Neu in Skype for Business Server 2015   |

   
## <a name="how-health-rolls-up"></a>Roll-up für Integrität

In der folgenden Tabelle sind die Integritätszustände von Objekten aufgeführt, die Skype for Business Server Monitoring Pack verwenden.
  
|Management Pack-Objekt|Beschreibung|
|:-----|:-----|
|Skype for Business Server Einsatz   |Stellt die Bereitstellung von Skype for Business Server 2015 in der Organisation dar.   |
|Skype for Business Server Website   |Stellt unterschiedliche geografische Standorte dar, an denen Dienste bereitgestellt werden.   |
|Skype for Business Server Pool   |Ein Pool (innerhalb eines Standorts), der Benutzern Kommunikationsdienste wie Chat und Konferenzen bereitstellt. Gilt für Front-End-Pools, Edgepools und Directorpools, auch wenn sich nur ein einzelner Computer in einem bestimmten Pool befindet.   |
|Skype for Business Server Rolle   |Eine Serverrolle, die Skype for Business Server Dienst hostet.   |
|Skype for Business Server Service   |Stellt eine Funktionalität dar, die auf einem bestimmten Computer bereitgestellt wird (z. B. Benutzerdienst auf fp01.contoso.com).   |
|Skype for Business Server Komponente   |Eine Komponente des Diensts (z. B. ist die Adressbuchdownloadkomponente Teil des Webdiensts).   |
|Skype for Business Server Poolüberwachung   |Eine Instanz synthetischer Transaktionen, die für einen Pool ausgeführt werden.   |
|Skype for Business Server Registrar Watcher   |Eine Instanz synthetischer Transaktionen, die für einen Registrierungsstellenpool ausgeführt werden.   |
|Skype for Business Server User Services Pool Watcher   |Eine Instanz synthetischer Transaktionen, die für einen Benutzerdienstpool ausgeführt werden.   |
|Skype for Business Server VoIP-Poolüberwachung   |Eine Instanz synthetischer Transaktionen, die für einen VoIP-Pool ausgeführt werden.   |
|Skype for Business Server Portüberwachung   |Eine Instanz von Portüberprüfungen, die für einen Pool ausgeführt werden.   |
|Watcher für einfache URLs   |Führt HTTPS-Untersuchung der konfigurierten einfachen URLs in einer Bereitstellung aus.   |
   
![SCOM-Rollup.](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Ein Skype for Business Server Pool kann mehrere einzelne Skype for Business Server Systeme enthalten (mit mehr als einer Skype for Business Server Rolle, Skype for Business Server Dienst und Skype for Business Server-Komponente). Daher ist der Ausfall eines einzelnen Servers oder einer Komponente weniger wichtig für den Gesamtzustand des Skype for Business Server-Pools, da andere Server im selben Pool den Anwendungsdienst für den Client bereitstellen können. Die Integrität wird auf prozentualer Ebene auf den Skype for Business Server-Pool aufgerollt. 
  
Der Skype for Business Server Pool watcher führt synthetische Transaktionen für einen Skype for Business Server Pool durch. Durch aufeinander folgende Fehler einer oder mehrerer synthetischer Transaktionen (ein Prozess, der als aufeinander folgendes Abrufintervall bezeichnet wird) wird der kritische Integritätsstatus auf Poolebene (die schlechteste aller synthetischen Transaktionen) wie im folgenden Diagramm dargestellt. 
  
![Aufeinander folgendeS Abrufen des SCOM-Rollups.](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Operations Manager speichert standardmäßig alle Anpassungen, z. B. Außerkraftsetzungen im Standardverwaltungspaket. Als bewährte Methode sollten Sie ein separates Management Pack für jedes versiegelte Management Pack erstellen, das Sie anpassen möchten. 
  
Wenn Sie ein Management Pack zum Speichern benutzerdefinierter Einstellungen für ein versiegeltes Management Pack erstellen, empfehlen wir, das neue Management Pack entsprechend zu benennen, z. B. "Skype for Business Server 2015-Anpassungen". 
  
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
    
Fragen zu Operations Manager und Monitoring Packs finden Sie im [Community-Forum System Center Operations Manager.](https://go.microsoft.com/fwlink/p/?LinkID=179635)
  
Eine hilfreiche Ressource ist der [Blog System Center Operations Manager-Entfesselung,](https://opsmgrunleashed.wordpress.com/) der Beiträge "Nach Beispiel" für bestimmte Überwachungspakete enthält.
  
Weitere Informationen zu Operations Manager finden Sie in den folgenden Blogs: 
  
- [Operations Manager Team Blog](https://blogs.technet.com/momteam/default.aspx)
    
- [Gedanken zu OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
   
> [!IMPORTANT]
> Alle Informationen und Inhalte auf Nicht-Microsoft-Websites werden vom Besitzer oder den Benutzern der Website bereitgestellt. Microsoft übernimmt keine garantiernden, ausdrücklichen, konkludenten oder gesetzlichen Garantien hinsichtlich der Informationen auf dieser Website. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015-Verwaltungstools](../../management-tools/management-tools.md)