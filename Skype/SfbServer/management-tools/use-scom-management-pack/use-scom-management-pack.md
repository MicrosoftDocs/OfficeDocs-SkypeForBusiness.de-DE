---
title: Verwalten von Skype for Business Server 2015 mithilfe von SCOM Management Packs
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ca03f9ab-a227-4903-85a8-427df6a0a5bb
description: 'Zusammenfassung: Informationen Sie zum Konfigurieren Ihrer Skype Business Server 2015 Infrastruktur für System Center Operations Manager entwickelt.'
ms.openlocfilehash: 998413a20f775f48cedfc501650d7562850c9965
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="manage-skype-for-business-server-2015-using-scom-management-pack"></a>Verwalten von Skype for Business Server 2015 mithilfe von SCOM Management Packs
 
**Zusammenfassung:** Informationen Sie zum Konfigurieren Ihrer Skype Business Server 2015 Infrastruktur für System Center Operations Manager entwickelt.
  
In einer idealen Welt würden Sie nie Probleme mit Skype für Business Server 2015 auftreten. Skype für Business Server kann jedoch durch externe Faktoren beeinflusst werden – beispielsweise network Abstürze und Hardwarefehler. Skype für Business Server 2015 Management Packs verwenden, können Sie identifizieren und beheben potenzielle Probleme proaktiv. Auf diese Weise die Skype für Business Server 2015 Management Packs, erweitern die Funktionen von System Center Operations Manager.
  
Diese Informationen wurde basierend auf Version 9319.0 von Monitoring Pack für Skype für die Kommunikationssoftware Business Server 2015 geschrieben.
  
## <a name="configuration-overview"></a>Konfiguration – Überblick

 Um Ihre Skype Business Server 2015 Infrastruktur für System Center Operations Manager entwickelt zu konfigurieren, müssen Sie drei Dinge vornehmen:
  
Identifizieren und [Konfigurieren des primären Verwaltungsservers](configure-the-primary.md). Zu diesem Zweck müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [Konfigurieren der Skype für Business Server-Computer, der überwacht wird](configure-computers-to-monitor.md). Zum Überwachen einer Skype für Business Server-Computer mithilfe von System Center Operations Manager müssen Sie die System Center Operations Manager-Agentdateien installieren und konfigurieren Sie jeden Server, die als Proxy fungiert. 
  
 Identifizieren und [Installieren und Konfigurieren von Watcher-Knoten](watcher-nodes.md). Watcher-Knoten Computer, die in regelmäßigen Abständen Skype für synthetische Transaktionen Business Server ausgeführt werden – Windows PowerShell-Cmdlets, die diesen Schlüssel Skype für Business Server-Komponenten, beispielsweise die Möglichkeit zum Anmelden an das System oder die Möglichkeit zum Austauschen von Sofortnachrichten überprüfen Nachrichten, funktionieren wie erwartet. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>Stammverwaltungsserver System Center Operations Manager und Agent-Unterstützung

Der Management Packs mit System Center Operations Manager 2007 R2 (64-Bit) verwendet werden kann (unterstützt nur aus Gründen der Migration) oder System Center Operations Manager 2012 SP1 &amp; R2 (64-Bit). Die folgende Tabelle enthält die unterstützten Konfigurationen für die Management Packs für Skype für Business Server 2015: 
  
|**Konfiguration**|**Unterstützt?**|
|:-----|:-----|
|Betriebssystem Windows Server 2008 R2  <br/> Betriebssystem Windows Server 2012 R2  <br/> |Ja. Beide auf Skype für Business Server 2015 Server und synthetische Transaktion Watcher-Knoten.  <br/> |
|Clusterserver  <br/> |Nicht unterstützt.  <br/> |
|Agentenlose Überwachung  <br/> |Nicht unterstützt.  <br/> |
|Virtuelle Umgebung  <br/> |Ja.  <br/> |
|Serverrollen, die einer Domäne beigetreten sind  <br/> |Alle internen Skype für Business Server 2015 Serverrollen muss Domäne beigetreten sein.  <br/> |
|Eigenständige Serverrollen  <br/> |Skype für Business Server 2015 Edge-Server sind nicht erforderlich, damit der Domäne beigetreten sein.  <br/> |
|Topologieeinschränkungen  <br/> |Alle Serverrollen in einer Bereitstellung müssen von derselben Operations Manager-Verwaltungsgruppe überwacht werden.  <br/> |
|Watcher-Knoten für synthetische Transaktionen  <br/> |Verfügbarkeit eines Überwachungsszenarios mit einem Watcher-Knoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration ist erforderlich). Watcher-Knoten müssen keiner Domäne beigetreten sein.  <br/> |
   
Die folgende Tabelle zeigt die Kapazitäts- und Betriebssystemanforderungen für einen Watcher-Knoten für synthetische Transaktionen:
  
|**Hardwarekomponente**|**Mindestanforderung**|
|:-----|:-----|
|CPU  <br/> |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Vierkern, mindestens 2,33 GHz  <br/> 64-Bit-2-Wege-Prozessor, Doppelkern, mindestens 2,33 GHz  <br/> |
|Arbeitsspeicher  <br/> |8 GB  <br/> |
|Betriebssystem  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Netzwerk  <br/> |1 Netzwerkadapter bei 1 GBit/s  <br/> |
   
## <a name="prerequisites"></a>Voraussetzungen

Zum Ausführen eines Watcher-Knotens für synthetische Transaktionen müssen Sie zuerst Folgendes installieren:
  
- System Center Operations Manager-Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype für Business Server Core-Installationsdateien (OcsCore.msi) und Unified Communications Managed API (UCMA) (Versionen müssen die Skype für Business Server WatcherNode.msi Version übereinstimmen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Monitoring Pack

Das Monitoring Pack für Skype für Business Server 2015 umfasst die folgenden Dateien:
  
- Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2015.Monitoring.ComponentAndUser.mp
    
- "Watchernode.msi" ein
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu in Skype für Business Server 2015 Management Packs.
  
- **Automatische Ermittlung für Clientanmeldung** Clientanwendungen, die Skype für Business Server 2015 häufig automatisch anmelden ermitteln den Server anmelden. Synthetische Transaktionen unterstützen jetzt die Überprüfung, ob die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Benutzerdefinierte synthetische Transaktion ausführen Intervallen** Zur Vereinfachung der einrichten Prozess der Watcher-Knoten können synthetische Transaktionen Benutzerkonten freigeben. Dadurch wird die Häufigkeit reduziert, mit der die Tests ausgeführt werden, da die Tests zur Vermeidung von Konflikten serialisiert werden. Standardmäßig werden synthetische Transaktionen alle 15 Minuten ausgeführt, damit Zeit zum Ausführen aller Tests vorhanden ist. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden möchten, können jetzt auch das Ausführungsintervall verringern.
    
- **Synthetische Transaktion Video Interop-Dienste** Kunden, die zu Skype für Business Server 2015 aus anderen anbieterlösungen häufig migrieren wünschen sich weiterhin die Videokonferenzen-Geräte (VTCs) dieser anderen Anbieter verwenden. Interop-Video-Server ist eine neue Skype für Business Server 2015 Serverrolle, mit dem Kunden Cisco VTCs in der Konferenzräume verwenden, indem eine Verbindung mit Cisco CUCM über einen SIP-Trunk video fortsetzen kann. Diese Funktion fügt außerdem eine synthetische Transaktion hinzu, damit überprüft werden kann, ob der Video-Interoperabilität-Server ausgeführt wird und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Konferenzen mit Anwendungsfreigabe** End-to-End-Szenarioüberprüfung für Konferenzen mit Anwendungsfreigabe wird jetzt unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachen von Szenarios

Die Skype für Business Server 2015 Management Pack nutzt eine Vielzahl von Features, mit denen Sie erkennen und Problemdiagnose. Diese Features bieten in Echtzeit Einblick in die Integrität einer Skype für Business Server 2015-Umgebung.
  
|**Monitoring-Szenario**|**Beschreibung**|
|:-----|:-----|
|Synthetische Transaktionen  <br/> | Windows PowerShell-Cmdlets zum Testen und hohe Verfügbarkeit von Szenarien wie etwa Sign in Anwesenheitsinformationen, Sofortnachrichten und Konferenzen für Benutzer dazu beitragen. <br/> Die synthetischen Transaktionen können von einem beliebigen geografischen Standort wie innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen ausgeführt werden.  <br/> Wenn bei einer synthetischen Transaktion ein Fehler auftritt, werden HTML-Protokolle erstellt, um die genaue Art des Ausfalls zu ermitteln. Hierzu gehören die Ermittlung, welche Aktion fehlgeschlagen ist, die Wartezeit jeder Aktion, die Befehlszeile zum Ausführen des Tests und der jeweils aufgetretenen Fehler.  <br/> |
|Warnungen zur Anrufzuverlässigkeit  <br/> |Kommunikationsdatensätze (KDS) von Skype für Business Server 2015 Server geschrieben wider, ob Benutzer zu einem Anruf eine Verbindung herstellen können, oder warum ein Gespräch beendet wird. Warnungen zur Anrufzuverlässigkeit fragen die KDS-Datenbank ab, um Warnungen zu erstellen, die anzeigen, wenn eine hohe Zahl von Benutzern Verbindungsprobleme bei Peer-zu-Peer-Anrufen oder einfachen Konferenzfunktionen haben.  <br/> Das Szenario deckt Audioanrufe, Peer-zu-Peer-Chatnachrichten und sonstige Konferenzfunktionen ab.  <br/> |
|Warnungen zur Medienqualität  <br/> |Datenbankabfragen, die für Business Server 2015 Clients am Ende jeder Aufruf von Skype veröffentlichten Quality of Experience (QoE)-Berichte anzeigen. Diese Abfragen führen zu Warnungen, die auf Szenarien hinweisen, bei denen Benutzer während Anrufen und Konferenzen wahrscheinlich eine mangelhafte Medienqualität feststellen. Die Daten basieren auf wichtigen Metriken wie z. B. Paketwartezeit und Paketverlust, die einen direkten Beitrag zur Qualität der Benutzererfahrung leisten.  <br/> |
|Warnungen zur Komponentenintegrität  <br/> |Einzelne Serverkomponenten lösen über Ereignisprotokolle und Leistungsindikatoren Warnungen aus, die auf Fehlerbedingungen hinweisen, welche Endbenutzerszenarios stark beeinträchtigen können. Diese Warnungen sind Hinweis auf eine Reihe von Bedingungen wie z. B. nicht ausgeführte Dienste, hohe Fehlerraten, lange Nachrichtenwartezeiten oder Konnektivitätsprobleme.  <br/> |
|Überwachung der Abhängigkeitsintegrität  <br/> |Skype für Business Server kann für eine Vielzahl von externen Gründen ein Fehler auftritt. Das Management Pack überwacht und erfasst Daten für kritische externe Abhängigkeiten, die schwerwiegende Probleme anzeigen können. Diese Abhängigkeiten umfassen Verfügbarkeit (Internet Information Services, IIS) und CPU-Server, der für Skype Business Server verwendet.  <br/> |
   
### <a name="alert-prioritization"></a>Priorisierung von Warnungen

Warnungen werden in den folgenden Kategorien klassifiziert: 
  
 **Hohe Priorität Warnungen:** Geben Sie diese Warnungen Bedingungen, die dazu führen, dass Dienstausfälle für große Gruppen von Benutzern und erfordern sofortige Aktion an. Ausfälle von synthetischen Transaktionen und offline-Diensten (wie Skype für Business Server a/v-Konferenzen) erkannt qualifiziert werden, als Warnungen hohe Priorität. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype für Business Server 2015 verfügt über integrierte Funktionen für hohe Verfügbarkeit für diesen Situationen – beispielsweise mehrere Front-End-Server hinter den Systemen zum Lastenausgleich.
  
 **Mittlere Priorität Warnungen:** Geben Sie diese Warnungen an, Bedingungen, die Einfluss auf eine Teilmenge der Benutzer oder geben Sie an, in die Anrufqualität Probleme – beispielsweise Ausfälle, Wartezeiten Herstellen der Verbindung oder niedrigere Audioqualität bei Anrufen. Benachrichtigungen in dieser Kategorie werden dynamische (d. h., die Art der Warnungen Änderungen anhand der Status der Verbindung.) Beispielsweise wenn Aufruf der Herstellung der Zeiten zurückkehren zu einer normalen Schwellenwert Wartezeit anzugeben, diese Warnung mittlere Priorität wäre automatisch aufgelöst in System Center Operations Manager und Administratoren müssen keine Aktion zu übernehmen. Warnungen, die automatisch aufgelöst werden können werden in der Regel durch Administratoren am gleichen Arbeitstag behandelt.
  
 **Andere Warnungen:** Diese Warnungen werden von Komponenten generiert, die einen bestimmten Benutzer oder einen Teil der Benutzer betreffen können. Ein typisches Beispiel ist eine Warnung, dass der Adressbuchdienst nicht den AD DS-Eintrag (Active Directory®-Domänendienste) für den Benutzer testuser@contoso.com analysieren konnte. Administratoren können auf diese Warnungen reagieren, wenn ihnen Zeit zur Verfügung steht.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype für Business Server 2015 Management Packs bieten eine erhöhte Abdeckung für Benachrichtigungen über synthetische Transaktionen. Synthetische Transaktionen sind in das Operations Manager Management Pack integrierte Windows PowerShell-Cmdlets zum Testen von End-to-End-Benutzerszenarios. Wenn Sie einen Server zum Ausführen synthetischer Transaktionen benennen, werden diese Cmdlets vom Management Pack regelmäßig ausgelöst. Fehler aufgrund einer synthetischen Transaktion generieren eine statusbehaftete Warnung. Hier sind unterstützte synthetische Transaktionen für Skype für Business Server 2015:
  
**Synthetische Transaktionen unterstützt für Registrierung, Anwesenheit und Kontakte**

||||
|:-----|:-----|:-----|
|1  <br/> |Registrierung (Benutzeranmeldung)  <br/> |Verfügbare Lync Server 2010 und höher  <br/> |
|2  <br/> |Adressbuchdienst (Dateidownload)  <br/> |Verfügbare Lync Server 2010 und höher  <br/> |
|3  <br/> |Adressbuch-Webabfrage  <br/> |Verfügbare Lync Server 2010 und höher  <br/> |
|4  <br/> |Anwesenheit  <br/> |Verfügbare Lync Server 2010 und höher  <br/> |
|5  <br/> |Einheitlicher Kontaktspeicher  <br/> |Verfügbare Lync Server 2013 und höher  <br/> |
   
**Unterstützte synthetische Transaktionen für Peer-zu-Peer-Dienste**

||||
|:-----|:-----|:-----|
|6  <br/> |Peer-zu-Peer-Chatnachrichten  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|7  <br/> |Peer-zu-Peer-Audio/Video  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|8  <br/> |MCX-Peer-zu-Peer-Chatnachrichten (Mobiltelefon)  <br/> |Verfügbar in der September 2011-Version von Lync Server 2010 und darüber hinaus  <br/> |
   
**Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat**

||||
|:-----|:-----|:-----|
|9  <br/> |Audio/Video-Konferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|10  <br/> |Datenkonferenzen  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|11  <br/> |Chatkonferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|12  <br/> | Beständiger Chat <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|13  <br/> |Join Launcher (geplante Besprechungen)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|14  <br/> |Einwahlkonferenzen  <br/> |Neu in Skype für Business Server 2015  <br/> |
|15  <br/> |Anwendungsfreigabekonferenzen  <br/> |Neu in Skype für Business Server 2015  <br/> |
|16  <br/> |UCWA-Konferenz (Teilnahme an Webbesprechungen)  <br/> |Neu in Skype für Business Server 2015  <br/> |
   
**Unterstützte synthetische Transaktionen für Netzwerk- und Partnerabhängigkeiten**

||||
|:-----|:-----|:-----|
|17  <br/> |A/V-Edgekonnektivität  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|18  <br/> |A/V-Edgekonnektivität, Exchange Unified Nachricht-Konnektivität (Voicemail)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|19  <br/> |PSTN-Peer-zu-Peer-Anrufe  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|20  <br/> |XMPP-Chatnachrichten (Verbund)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|21  <br/> |Video-Interoperabilität-Server  <br/> |Neu in Skype für Business Server 2015  <br/> |
   
## <a name="how-health-rolls-up"></a>Integritäts-Rollup

In der folgenden Tabelle zeigt die Zustände von der Skype-Objekten für Business Server monitoring Pack.
  
|**Management Pack-Objekt**|**Beschreibung**|
|:-----|:-----|
|Skype für Business Server-Bereitstellung  <br/> |Stellt die Bereitstellung von Skype für Business Server 2015 in der Organisation.  <br/> |
|Skype für Business Server-Website  <br/> |Stellt die verschiedenen geografischen Standorte dar, an denen Dienste bereitgestellt werden.  <br/> |
|Skype für Business Server-Pool  <br/> |Ein Pool (innerhalb eines Standorts), der Kommunikationsdienste wie Chatnachrichten und Konferenzen für Benutzer bereitstellt. Gilt für Front-End-Pools, Edgepools und Directorpools, selbst wenn nur ein einzelner Computer in einem bestimmten Pool vorhanden ist.  <br/> |
|Skype für die Business-Serverrollen  <br/> |Eine Serverrolle, die Skype für Business Server-Dienst gehostet wird.  <br/> |
|Skype für Business Server-Dienst  <br/> |Stellt eine Funktionalität dar, die auf einem bestimmten Computer bereitgestellt wird (z. B. Benutzerdienst auf fp01.contoso.com).  <br/> |
|Skype für Business Server-Komponente  <br/> |Eine Komponente des Diensts (die Adressbuchdownload-Komponente beispielsweise ist Bestandteil des Webdiensts).  <br/> |
|Skype für Business Server Pool Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Pool ausgeführt werden.  <br/> |
|Skype für Business Server Registrierungsstelle Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Registrierungsstellenpool ausgeführt werden  <br/> |
|Skype für Business Server Benutzer Services Pool Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen Benutzerdienstepool ausgeführt werden.  <br/> |
|Skype für Business Server VoIP Pool Watcher  <br/> |Eine Instanz von synthetischen Transaktionen, die für einen VoIP-Pool ausgeführt werden.  <br/> |
|Skype für Business Server Port Watcher  <br/> |Eine Instanz von Portüberprüfungen, die für einen Pool ausgeführt werden.  <br/> |
|Einfacher URL-Watcher  <br/> |Führt HTTPS-Prüfungen der konfigurierten einfachen URLs in einer Bereitstellung aus.  <br/> |
   
![SCOM-Rollup](../../media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Eine Skype für Business Server-Pool kann mehrere einzelne Skype für Business Server-Systeme (mit mehr als eine Skype für Business Server-Role, Skype für Business Server-Dienst und Skype für Business Server-Komponente) enthalten. Aus diesem Grund ist der Ausfall eines einzelnen Servers oder der Komponente weniger entscheidend für die allgemeine Integrität der Skype für Business Server-Pool, da anderen Servern im selben Pool den Anwendungsdienst an dem Client bereitstellen können. Die Integrität wird auf einer Ebene Prozentsatz, der Skype für Business Serverpool Rollup. 
  
Die Skype für Business Server Pool Watcher führt synthetische Transaktionen gegen eine Skype für Business Server-Pool. Der nachfolgende Ausfall eines oder mehrerer synthetischer Transaktionen (ein Prozess, der als aufeinanderfolgendes Aufrufintervall bezeichnet wird) führt ein Rollup des kritischen Integritätszustands auf Poolebene aus (die schlechteste aller synthetischen Transaktionen), wie im nachfolgenden Diagramm dargestellt. 
  
![Aufeinanderfolgende Aufrufe für das SCOM-Rollup](../../media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Standardmäßig speichert Operations Manager alle Anpassungen wie z. B. Außerkraftsetzen des standardmäßigen Management Packs. Eine bewährte Methode besteht darin, ein separates Management Pack für jedes versiegelte Management Pack zu erstellen, das Sie anpassen möchten. 
  
Beim Erstellen eines Management Packs zum Speichern von benutzerdefinierten Einstellungen für ein versiegeltes Management Pack empfehlen wir, das neue Management Pack entsprechend zu benennen, z. B. „Skype for Business Server 2015-Anpassungen“. 
  
Das Erstellen eines neuen Management Packs zum Speichern von Anpassungen der einzelnen versiegelten Management Packs erleichtert das Exportieren der Anpassungen aus einer Testumgebung in eine Produktionsumgebung. Es erleichtert außerdem das Löschen eines Management Packs, da Sie alle Abhängigkeiten löschen müssen, bevor Sie ein Management Pack löschen können. Wenn Anpassungen für alle Management Packs im standardmäßigen Management Pack gespeichert werden und Sie ein einzelnes Management Pack löschen müssen, müssen Sie zuerst das standardmäßige Management Pack löschen, wodurch auch Anpassungen an andere Management Packs gelöscht werden. 
  
## <a name="links"></a>Links

Nachfolgend finden Sie Links zu Informationen zu gängigen Aufgaben im Zusammenhang mit System Center 2012 Monitoring Packs:
  
- [Management Pack-Lebenszyklus](https://technet.microsoft.com/en-us/library/hh212732.aspx)
    
- [Gewusst wie: Importieren eines Management Packs in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212691.aspx)
    
- [Gewusst wie: Überschreiben einer Regel- oder Monitorbezogenen](https://technet.microsoft.com/en-us/library/hh212869.aspx)
    
- [Zum Erstellen einer Ausführen als Konto in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh321655.aspx)
    
- [Verwalten von Ausführen als Konten und Profile](https://technet.microsoft.com/en-us/library/hh212714.aspx)
    
- [So exportieren Sie ein Management Pack für Operations Manager](https://technet.microsoft.com/en-us/library/hh320149.aspx)
    
- [So entfernen Sie ein Management Pack für Operations Manager](https://technet.microsoft.com/en-us/library/hh230746.aspx)
    
Nachfolgend finden Sie Links zu Informationen zu gängigen Aufgaben im Zusammenhang mit System Center 2007 Monitoring Packs:
  
- [Verwalten der Management Pack-Lebenszyklus](https://go.microsoft.com/fwlink/p/?LinkId=211463)
    
- [Gewusst wie: Importieren ein Management Packs in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=142351)
    
- [Überwachen der Verwendung überschreibt](https://go.microsoft.com/fwlink/p/?LinkID=117777)
    
- [Gewusst wie: Erstellen einer Ausführen als Konto in Operations Manager 2007](https://go.microsoft.com/fwlink/p/?LinkID=165410)
    
- [Gewusst wie: Ändern einer vorhandenen Ausführen als Profil](https://go.microsoft.com/fwlink/p/?LinkID=165412)
    
- [Management Pack Anpassungen exportieren](https://go.microsoft.com/fwlink/p/?LinkId=209940)
    
- [Gewusst wie: entfernen ein Management Packs](https://go.microsoft.com/fwlink/p/?LinkId=209941)
    
Fragen Operations Manager und Überwachung Packs finden Sie im [System Center Operations Manager Community-Forum](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Eine nützliche Ressource ist im [System Center Operations Manager verbreitet](https://opsmgrunleashed.wordpress.com/) Blog, das Beiträge für bestimmte monitoring Packs "By Example" enthält.
  
Weitere Informationen zum Operations Manager finden Sie in den folgenden Blogs: 
  
- [Operations Manager-Teamblog](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holmans OpsMgr Blog (engl.)](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Gedanken auf OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog Raphael Burris (engl.)](https://rburri.wordpress.com/)
    
- [BWren des Management Speicherplatz](https://blogs.technet.com/brianwren/default.aspx)
    
- [OpsMgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Alle Informationen und Inhalte auf Nicht-Microsoft-Websites werden vom Besitzer oder den Benutzern der Website zur Verfügung gestellt. Microsoft schließt jede ausdrückliche, konkludente oder gesetzliche Gewährleistung in Bezug auf die Informationen auf dieser Website aus. 
  
## <a name="see-also"></a>Siehe auch

#### 

[Skype für Business Server 2015-Verwaltungstools](../../management-tools/management-tools.md)

