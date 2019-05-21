---
title: Verwalten von Skype for Business Server 2015 mithilfe von SCOM Management Packs
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.'
ms.openlocfilehash: 3f8f8d188beee3a67a2b4d7cc6308c60410cbf9a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277650"
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Verwalten von Skype for Business Server 2015 mithilfe von SCOM Management Packs
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.
  
In einer idealen Welt hätten Sie nie Probleme mit Skype for Business Server 2015. Der Skype for Business-Server kann jedoch von externen Faktoren beeinflusst werden, beispielsweise von Netzwerk abstürzen und Hardwarefehlern. Durch die Verwendung von Skype for Business Server 2015-Management Packs können Sie potenzielle Probleme proaktiv erkennen und beheben. Auf diese Weise erweitern die Skype for Business Server 2015-Management Packs die Funktionen von System Center Operations Manager.
  
Diese Informationen wurden auf der Grundlage der Version 9319,0 des Überwachungs Pakets für die Skype for Business Server 2015-Kommunikationssoftware geschrieben.
  
## <a name="configuration-overview"></a>Konfiguration – Überblick

 Wenn Sie Ihre Skype for Business Server 2015-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren möchten, müssen Sie drei Schritte ausführen:
  
Identifizieren und [Konfigurieren Sie den primären Verwaltungs Server](configure-the-primary.md). Dazu müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [Konfigurieren Sie die Skype for Business Server-Computer, die überwacht werden sollen](configure-computers-to-monitor.md). Wenn Sie einen Skype for Business-Server Computer mithilfe von System Center Operations Manager überwachen möchten, müssen Sie die System Center Operations Manager-Agentdateien installieren und die einzelnen Server so konfigurieren, dass Sie als Proxy fungieren. 
  
 Identifizieren und [Installieren und konfigurieren Sie Watcher-Knoten](watcher-nodes.md). Watcher-Knoten sind Computer, die in regelmäßigen Abständen Skype for Business Server-synthetische Transaktionen ausführen – Windows PowerShell-Cmdlets, die überprüfen, ob die Schlüsselkomponenten von Skype for Business Server, wie etwa die Möglichkeit zur Anmeldung am System oder die Möglichkeit zum Austausch von Instant Nachrichten funktionieren wie erwartet. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager-Stamm Verwaltungs Server und Agent-Unterstützung

Die Management Packs können mit System Center Operations Manager 2007 R2 (64-Bit) verwendet werden (nur für Migrationszwecke unterstützt) oder System Center Operations Manager 2012 &amp; SP1 R2 (64-Bit) oder System Center Operations Manager 2016 (64-Bit). In der folgenden Tabelle sind die unterstützten Konfigurationen für die Management Packs für Skype for Business Server 2015 aufgeführt: 
  
|**Konfiguration**|**Stützt?**|
|:-----|:-----|
|Windows Server 2008 R2-Betriebssystem  <br/> Windows Server 2012 R2-Betriebssystem  <br/> |Ja. Sowohl auf den Skype for Business Server 2015-Servern als auch auf den synthetischen Transaktions Überwachungsknoten.  <br/> |
|Clusterserver  <br/> |Nicht unterstützt.  <br/> |
|Agentenlose Überwachung  <br/> |Nicht unterstützt.  <br/> |
|Virtuelle Umgebung  <br/> |Ja.  <br/> |
|Serverrollen, die einer Domäne beigetreten sind  <br/> |Alle internen Skype for Business Server 2015-Serverrollen müssen Domänen verbunden sein.  <br/> |
|Eigenständige Serverrollen  <br/> |Für Skype for Business Server 2015 Edge-Server ist keine Domäne erforderlich.  <br/> |
|Topologieeinschränkungen  <br/> |Alle Serverrollen in einer Bereitstellung müssen von derselben Operations Manager-Verwaltungsgruppe überwacht werden.  <br/> |
|Watcher-Knoten für synthetische Transaktionen  <br/> |Verfügbarkeit eines Überwachungsszenarios mit einem Watcher-Knoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration ist erforderlich). Watcher-Knoten müssen keiner Domäne beigetreten sein.  <br/> |
   
Die folgende Tabelle zeigt die Kapazitäts- und Betriebssystemanforderungen für einen Watcher-Knoten für synthetische Transaktionen:
  
|**Hardwarekomponente**|**Mindestanforderung**|
|:-----|:-----|
|CPU  <br/> |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Vierkern, mindestens 2,33 GHz  <br/> 64-Bit-2-Wege-Prozessor, Doppelkern, mindestens 2,33 GHz  <br/> |
|Arbeitsspeicher  <br/> |8 GB  <br/> |
|Betriebssystem  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Netzwerk  <br/> |1 Netzwerkadapter bei 1 GBit/s  <br/> |
   
## <a name="prerequisites"></a>Voraussetzungen

Zum Ausführen eines Watcher-Knotens für synthetische Transaktionen müssen Sie zuerst Folgendes installieren:
  
- System Center Operations Manager-Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server Core-Installationsdateien (OcsCore. msi) und Unified Communications Managed API (UCMA) (Versionen müssen der Skype for Business Server-WatcherNode. MSI-Version entsprechen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Monitoring Pack

Das Überwachungspaket für Skype for Business Server 2015 umfasst die folgenden Dateien:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu bei den Skype for Business Server 2015-Verwaltungs Paketen.
  
- **Automatische Ermittlung für die Client Anmeldung** Client Anwendungen, die sich bei Skype for Business Server 2015 anmelden, erkennen oft automatisch den Server, bei dem Sie sich anmelden. Synthetische Transaktionen unterstützen jetzt die Überprüfung, ob die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Angepasste synthetische Transaktions Ausführungs Intervalle** Um den Setupprozess von Watcher-Knoten zu vereinfachen, können synthetische Transaktionen Benutzerkonten freigeben. Dadurch wird die Häufigkeit reduziert, mit der die Tests ausgeführt werden, da die Tests zur Vermeidung von Konflikten serialisiert werden. Standardmäßig werden synthetische Transaktionen alle 15 Minuten ausgeführt, damit Zeit zum Ausführen aller Tests vorhanden ist. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden möchten, können jetzt auch das Ausführungsintervall verringern.
    
- **Video Interop Services-synthetische Transaktion** Kunden, die von anderen Anbieter Lösungen zu Skype for Business Server 2015 migrieren, möchten häufig die Video Teleconferencing Devices (VTCs) von diesen anderen Anbietern weiterhin verwenden. Video-Interop-Server ist eine neue Serverrolle von Skype for Business Server 2015, mit der Kunden weiterhin Cisco VTCs in ihren Konferenzräumen nutzen können, indem Sie über einen Video-SIP-Trunk eine Verbindung mit Cisco CUCM herstellen. Diese Funktion fügt außerdem eine synthetische Transaktion hinzu, damit überprüft werden kann, ob der Video-Interoperabilität-Server ausgeführt wird und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Konferenzen mit Anwendungsfreigabe** End-to-End-Szenarioüberprüfung für Konferenzen mit Anwendungsfreigabe wird jetzt unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachen von Szenarios

Das Skype for Business Server 2015 Management Pack nutzt eine Vielzahl von Funktionen, die Ihnen helfen, Probleme zu erkennen und zu diagnostizieren. Diese Funktionen bieten eine echt Zeit Sichtbarkeit für den Zustand einer Skype for Business Server 2015-Umgebung.
  
|**Überwachungsszenario**|**Beschreibung**|
|:-----|:-----|
|Synthetische Transaktionen  <br/> | Windows PowerShell-Cmdlets zum Testen und zur Sicherstellungeiner großen Verfügbarkeit von Szenarien wie anmelden, Anwesenheit, Chat und Konferenzen für Benutzer. <br/> Die synthetischen Transaktionen können von einem beliebigen geografischen Standort wie innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen ausgeführt werden.  <br/> Wenn bei einer synthetischen Transaktion ein Fehler auftritt, werden HTML-Protokolle erstellt, um die genaue Art des Ausfalls zu ermitteln. Hierzu gehören die Ermittlung, welche Aktion fehlgeschlagen ist, die Wartezeit jeder Aktion, die Befehlszeile zum Ausführen des Tests und der jeweils aufgetretenen Fehler.  <br/> |
|Warnungen zur Anrufzuverlässigkeit  <br/> |Die von Skype for Business Server 2015-Servern geschriebenen Anruf Detail Datensätze (CDRs) geben an, ob Benutzer in der Lage sind, eine Verbindung mit einem Anruf herzustellen, oder warum ein Anruf beendet wird. Warnungen zur Anrufzuverlässigkeit fragen die KDS-Datenbank ab, um Warnungen zu erstellen, die anzeigen, wenn eine hohe Zahl von Benutzern Verbindungsprobleme bei Peer-zu-Peer-Anrufen oder einfachen Konferenzfunktionen haben.  <br/> Das Szenario deckt Audioanrufe, Peer-zu-Peer-Chatnachrichten und sonstige Konferenzfunktionen ab.  <br/> |
|Warnungen zur Medienqualität  <br/> |Datenbankabfragen, die die von Skype for Business Server 2015-Clients am Ende jedes Anrufs veröffentlichten QoE-Berichte (Quality of Experience) anzeigen. Diese Abfragen führen zu Warnungen, die auf Szenarien hinweisen, bei denen Benutzer während Anrufen und Konferenzen wahrscheinlich eine mangelhafte Medienqualität feststellen. Die Daten basieren auf wichtigen Metriken wie z. B. Paketwartezeit und Paketverlust, die einen direkten Beitrag zur Qualität der Benutzererfahrung leisten.  <br/> |
|Warnungen zur Komponentenintegrität  <br/> |Einzelne Serverkomponenten lösen über Ereignisprotokolle und Leistungsindikatoren Warnungen aus, die auf Fehlerbedingungen hinweisen, welche Endbenutzerszenarios stark beeinträchtigen können. Diese Warnungen sind Hinweis auf eine Reihe von Bedingungen wie z. B. nicht ausgeführte Dienste, hohe Fehlerraten, lange Nachrichtenwartezeiten oder Konnektivitätsprobleme.  <br/> |
|Überwachung der Abhängigkeitsintegrität  <br/> |Für Skype for Business Server kann aus verschiedenen externen Gründen ein Fehler auftreten. Das Management Pack überwacht und erfasst Daten für kritische externe Abhängigkeiten, die schwerwiegende Probleme anzeigen können. Zu diesen Abhängigkeiten gehören die Internet Informationsdienste (IIS)-Verfügbarkeit und die CPU-Auslastung von Servern, die für Skype for Business Server verwendet werden.  <br/> |
   
### <a name="alert-prioritization"></a>Priorisierung von Warnungen

Warnungen werden in den folgenden Kategorien klassifiziert: 
  
 **Benachrichtigungen mit höherer Priorität:** Diese Warnungen weisen auf Bedingungen hin, die zu Dienstunterbrechungen für große Benutzergruppen führen und Sofortmaßnahmen erfordern. Ausfälle, die von synthetischen Transaktionen und Offline Diensten (wie Skype for Business Server Audio/Video Conferencing) erkannt werden, werden als Warnungen mit höherer Priorität angezeigt. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype for Business Server 2015 verfügt über integrierte Funktionen für hohe Verfügbarkeit in diesen Situationen, beispielsweise mehrere Front-End-Server hinter Load-Balancern.
  
 **Warnungen mittlerer Priorität:** Diese Warnungen weisen auf Bedingungen hin, die sich auf eine Teilmenge von Benutzern auswirken oder Probleme bei der Anrufqualität angeben, beispielsweise Komponentenausfälle, Latenz in der Anrufeinrichtung oder niedrigere Audioqualität bei anrufen. Benachrichtigungen in dieser Kategorie sind Stateful (das heißt, die Art der Benachrichtigung ändert sich basierend auf dem Zustand der Netzwerkverbindung.) Wenn beispielsweise die Anrufzeiten die Wartezeit angeben, aber dann zu einem normalen Schwellenwert zurückkehren, wird diese Warnung mit mittlerer Priorität in System Center Operations Manager automatisch aufgelöst, und Administratoren müssen keine Aktion durchführen. Benachrichtigungen, die nicht automatisch aufgelöst werden können, werden in der Regel am gleichen Arbeitstag von Administratoren adressiert.
  
 **Andere Warnungen:** Diese Warnungen werden von Komponenten generiert, die einen bestimmten Benutzer oder einen Teil der Benutzer betreffen können. Ein typisches Beispiel ist eine Warnung, dass der Adressbuchdienst nicht den AD DS-Eintrag (Active Directory®-Domänendienste) für den Benutzer testuser@contoso.com analysieren konnte. Administratoren können auf diese Warnungen reagieren, wenn ihnen Zeit zur Verfügung steht.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype for Business Server 2015-Management Packs bieten erhöhte Reichweite für Benachrichtigungen über synthetische Transaktionen. Synthetische Transaktionen sind in das Operations Manager Management Pack integrierte Windows PowerShell-Cmdlets zum Testen von End-to-End-Benutzerszenarios. Wenn Sie einen Server zum Ausführen synthetischer Transaktionen benennen, werden diese Cmdlets vom Management Pack regelmäßig ausgelöst. Fehler aufgrund einer synthetischen Transaktion generieren eine statusbehaftete Warnung. Hier finden Sie unterstützte synthetische Transaktionen für Skype for Business Server 2015:
  
**Unterstützte synthetische Transaktionen für Registrierung, Anwesenheit und Kontakte**

||||
|:-----|:-----|:-----|
|1  <br/> |Registrierung (Benutzeranmeldung)  <br/> |Verfügbare lync Server 2010 und mehr  <br/> |
|2  <br/> |Adressbuchdienst (Dateidownload)  <br/> |Verfügbare lync Server 2010 und mehr  <br/> |
|3  <br/> |Adressbuch-Webabfrage  <br/> |Verfügbare lync Server 2010 und mehr  <br/> |
|4  <br/> |Anwesenheit  <br/> |Verfügbare lync Server 2010 und mehr  <br/> |
|5  <br/> |Einheitlicher Kontaktspeicher  <br/> |Verfügbare lync Server 2013 und mehr  <br/> |
   
**Unterstützte synthetische Transaktionen für Peer-zu-Peer-Dienste**

||||
|:-----|:-----|:-----|
|6  <br/> |Peer-zu-Peer-Chatnachrichten  <br/> |Verfügbar in lync Server 2010 und mehr  <br/> |
|7  <br/> |Peer-zu-Peer-Audio/Video  <br/> |Verfügbar in lync Server 2010 und mehr  <br/> |
|8  <br/> |MCX-Peer-zu-Peer-Chatnachrichten (Mobiltelefon)  <br/> |Verfügbar in der September 2011-Version von lync Server 2010 zu Skype for Business 2015  <br/> |
 
> [!NOTE]
> MCX (Mobility Service)-Unterstützung für ältere Mobile Clients steht in Skype for Business Server 2019 nicht mehr zur Verfügung. Alle derzeitigen mobilen Skype for Business-Clients verwenden bereits Unified Communications Web API (UCWA) zur Unterstützung von Instant Messaging (im), Anwesenheitsinformationen und Kontakten. Benutzer mit Legacy-Clients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
**Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat**

||||
|:-----|:-----|:-----|
|9  <br/> |Audio/Video-Konferenzen  <br/> |Verfügbar in lync Server 2010 und mehr  <br/> |
|10  <br/> |Datenkonferenzen  <br/> |Verfügbar in lync Server 2013 und mehr  <br/> |
|11  <br/> |Chatkonferenzen  <br/> |Verfügbar in lync Server 2010 und mehr  <br/> |
|12  <br/> | Beständiger Chat <br/> |Verfügbar in lync Server 2013 und mehr  <br/> |
|13  <br/> |Join Launcher (geplante Besprechungen)  <br/> |Verfügbar in lync Server 2013 und mehr  <br/> |
|14  <br/> |Einwahlkonferenzen  <br/> |Neu in Skype for Business Server 2015  <br/> |
|15  <br/> |Anwendungsfreigabekonferenzen  <br/> |Neu in Skype for Business Server 2015  <br/> |
|16  <br/> |UCWA-Konferenz (Teilnahme an Webbesprechungen)  <br/> |Neu in Skype for Business Server 2015  <br/> |
   
**Unterstützte synthetische Transaktionen für Netzwerk- und Partnerabhängigkeiten**

||||
|:-----|:-----|:-----|
|17  <br/> |A/V-Edgekonnektivität  <br/> |Verfügbar in lync Server 2013 und mehr  <br/> |
|18  <br/> |A/V-Edgekonnektivität, Exchange Unified Nachricht-Konnektivität (Voicemail)  <br/> |Verfügbar in lync Server 2013 und mehr  <br/> |
|19  <br/> |PSTN-Peer-zu-Peer-Anrufe  <br/> |Verfügbar in lync Server 2010 und mehr  <br/> |
|20  <br/> |XMPP-Chatnachrichten (Verbund)  <br/> |Verfügbar in lync Server 2013 und Skype for Business 2015  <br/> |
|21  <br/> |Video-Interoperabilität-Server  <br/> |Neu in Skype for Business Server 2015  <br/> |
   
## <a name="how-health-rolls-up"></a>Integritäts-Rollup

In der folgenden Tabelle sind die Integritätsstatus von Objekten des Skype for Business Server-Überwachungs Pakets aufgeführt.
  
|**Management Pack-Objekt**|**Beschreibung**|
|:-----|:-----|
|Skype for Business Server-Bereitstellung  <br/> |Stellt die Bereitstellung von Skype for Business Server 2015 in der Organisation dar.  <br/> |
|Skype for Business Server-Website  <br/> |Stellt die verschiedenen geografischen Standorte dar, an denen Dienste bereitgestellt werden.  <br/> |
|Skype for Business-Server Pool  <br/> |Ein Pool (innerhalb eines Standorts), der Kommunikationsdienste wie Chatnachrichten und Konferenzen für Benutzer bereitstellt. Gilt für Front-End-Pools, Edgepools und Directorpools, selbst wenn nur ein einzelner Computer in einem bestimmten Pool vorhanden ist.  <br/> |
|Skype for Business-Server Rolle  <br/> |Eine Serverrolle, die den Skype for Business Server-Dienst hostet.  <br/> |
|Skype for Business Server-Dienst  <br/> |Stellt eine Funktionalität dar, die auf einem bestimmten Computer bereitgestellt wird (z. B. Benutzerdienst auf fp01.contoso.com).  <br/> |
|Skype for Business-Server Komponente  <br/> |Eine Komponente des Diensts (die Adressbuchdownload-Komponente beispielsweise ist Bestandteil des Webdiensts).  <br/> |
|Skype for Business Server-Pool Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Pool ausgeführt werden.  <br/> |
|Skype for Business Server-Registrierungs Überwachungsdienst  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Registrierungsstellenpool ausgeführt werden  <br/> |
|Pool Watcher für Skype for Business Server-Benutzer Dienste  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Benutzerdienstepool ausgeführt werden.  <br/> |
|Skype for Business Server-sprach Pool Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen VoIP-Pool ausgeführt werden.  <br/> |
|Skype for Business Server-Port Watcher  <br/> |Eine Instanz von Portüberprüfungen, die für einen Pool ausgeführt werden.  <br/> |
|Einfacher URL-Watcher  <br/> |Führt HTTPS-Prüfungen der konfigurierten einfachen URLs in einer Bereitstellung aus.  <br/> |
   
![SCOM-Rollup](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Ein Skype for Business-Serverpool kann mehrere einzelne Skype for Business-Server Systeme (mit mehr als einer Skype for Business-Serverrolle, Skype for Business Server-Dienst und Skype for Business Server-Komponente) enthalten. Daher ist der Ausfall eines einzelnen Servers oder einer Komponente für den Gesamtzustand des Skype for Business Server-Pools unwesentlicher, da andere Server im gleichen Pool den Anwendungsdienst für den Client bereitstellen können. Der Status wird auf einer Prozent Ebene in den Skype for Business Server-Pool hoch gerollt. 
  
Der Skype for Business Server-Pool-Watcher führt synthetische Transaktionen mit einem Skype for Business-Serverpool durch. Der nachfolgende Ausfall eines oder mehrerer synthetischer Transaktionen (ein Prozess, der als aufeinanderfolgendes Aufrufintervall bezeichnet wird) führt ein Rollup des kritischen Integritätszustands auf Poolebene aus (die schlechteste aller synthetischen Transaktionen), wie im nachfolgenden Diagramm dargestellt. 
  
![Aufeinanderfolgende Aufrufe für das SCOM-Rollup](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Standardmäßig speichert Operations Manager alle Anpassungen wie z. B. Außerkraftsetzen des standardmäßigen Management Packs. Eine bewährte Methode besteht darin, ein separates Management Pack für jedes versiegelte Management Pack zu erstellen, das Sie anpassen möchten. 
  
Beim Erstellen eines Management Packs zum Speichern von benutzerdefinierten Einstellungen für ein versiegeltes Management Pack empfehlen wir, das neue Management Pack entsprechend zu benennen, z. B. „Skype for Business Server 2015-Anpassungen“. 
  
Das Erstellen eines neuen Management Packs zum Speichern von Anpassungen der einzelnen versiegelten Management Packs erleichtert das Exportieren der Anpassungen aus einer Testumgebung in eine Produktionsumgebung. Es erleichtert außerdem das Löschen eines Management Packs, da Sie alle Abhängigkeiten löschen müssen, bevor Sie ein Management Pack löschen können. Wenn Anpassungen für alle Management Packs im standardmäßigen Management Pack gespeichert werden und Sie ein einzelnes Management Pack löschen müssen, müssen Sie zuerst das standardmäßige Management Pack löschen, wodurch auch Anpassungen an andere Management Packs gelöscht werden. 
  
## <a name="links"></a>Links

Nachfolgend finden Sie Links zu Informationen zu gängigen Aufgaben im Zusammenhang mit System Center 2012 Monitoring Packs:
  
- [Lebenszyklus des Management Packs](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Importieren eines Management Packs in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Überschreiben einer Regel oder eines Monitors](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Erstellen eines Ausführ als Kontos in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Verwalten von Ausführ Konten und Profilen](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [Exportieren eines Operations Manager-Verwaltungs Pakets](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [Entfernen eines Operations Manager-Verwaltungs Pakets](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Nachfolgend finden Sie Links zu Informationen zu gängigen Aufgaben im Zusammenhang mit System Center 2007 Monitoring Packs:
  
- [Verwalten des Management Pack-Lebenszyklus](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Importieren eines Management Packs in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Überwachen mithilfe von Außerkraftsetzungen](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Erstellen eines Ausführ als Kontos in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Ändern eines vorhandenen ausführbaren Profils](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Exportieren von Management Pack-Anpassungen](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Entfernen eines Management Packs](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Fragen zu Operations Manager und Überwachungs Paketen finden Sie im [System Center Operations Manager-Community-Forum](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Eine nützliche Ressource ist der Blog " [System Center Operations Manager Unleashed](https://opsmgrunleashed.wordpress.com/) ", in dem die Beiträge für bestimmte Überwachungs Pakete "mit dem Beispiel" enthalten sind.
  
Weitere Informationen zum Operations Manager finden Sie in den folgenden Blogs: 
  
- [Operations Manager-Teamblog](https://blogs.technet.com/momteam/default.aspx)
    
- [Blog zu Kevin Holmans OpsMgr](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Gedanken zu OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog von Raphael Burri](https://rburri.wordpress.com/)
    
- [BWren-Verwaltungsbereich](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr + +](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Alle Informationen und Inhalte auf Nicht-Microsoft-Websites werden vom Besitzer oder den Benutzern der Website zur Verfügung gestellt. Microsoft schließt jede ausdrückliche, konkludente oder gesetzliche Gewährleistung in Bezug auf die Informationen auf dieser Website aus. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2015-Verwaltungs Tools](../../management-tools/management-tools.md)
