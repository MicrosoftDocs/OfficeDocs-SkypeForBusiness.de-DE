---
title: Verwalten von Skype for Business Server 2019 mithilfe von SCOM Management Pack
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie Ihre Skype for Business Server 2019-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.'
ms.openlocfilehash: 8f19998ad5d46074a1225ae0dd4d901bd367d823
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120384"
---
# <a name="manage-skype-for-business-server-2019-using-scom-management-pack"></a>Verwalten von Skype for Business Server 2019 mithilfe von SCOM Management Pack
 
**Zusammenfassung:** Erfahren Sie, wie Sie Ihre Skype for Business Server 2019-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager konfigurieren.
  
In einer idealen Welt würden nie Probleme mit Skype for Business Server 2019 auftreten. Skype for Business Server kann jedoch von externen Faktoren beeinflusst werden, z. B. Netzwerkabstürzen und Hardwarefehlern. Mithilfe von Skype for Business Server 2019 Management Packs können Sie potenzielle Probleme proaktiv identifizieren und beheben. Auf diese Weise erweitern die Skype for Business Server 2019 Management Packs die Funktionen von System Center Operations Manager.
  
Diese Informationen wurden basierend auf Version 9319.0 der Kommunikationssoftware Monitoring Pack for Skype for Business Server 2019 geschrieben.
  
## <a name="configuration-overview"></a>Übersicht über die Konfiguration

 Um Ihre Skype for Business Server 2019-Infrastruktur für die Zusammenarbeit mit System Center Operations Manager zu konfigurieren, müssen Sie drei Dinge tun:
  
Identifizieren und [Konfigurieren des primären Verwaltungsservers](../../SfbServer/management-tools/use-scom-management-pack/configure-the-primary.md). Dazu müssen Sie System Center Operations Manager 2012 SP1 oder R2 installieren. 
  
 Identifizieren und [Konfigurieren der Skype for Business Server-Computer, die überwacht werden.](../../SfbServer/management-tools/use-scom-management-pack/configure-computers-to-monitor.md) Zum Überwachen eines Skype for Business Server-Computers mithilfe von System Center Operations Manager müssen Sie die System Center Operations Manager-Agentdateien installieren und jeden Server als Proxy konfigurieren. 
  
 Identifizieren und [Installieren und Konfigurieren von Watcherknoten](../../SfbServer/management-tools/use-scom-management-pack/watcher-nodes.md). Watcher-Knoten sind Computer, auf denen regelmäßig synthetische Skype for Business Server-Transaktionen ausgeführt werden– Windows PowerShell-Cmdlets, die überprüfen, ob wichtige Skype for Business Server-Komponenten, z. B. die Möglichkeit, sich am System zu anmelden oder Chatnachrichten austauschen, wie erwartet funktionieren. 
  
## <a name="system-center-operations-manager-root-management-server-and-agent-support"></a>System Center Operations Manager Stammverwaltungsserver und Agentunterstützung

Die Management Packs können mit System Center Operations Manager 2007 R2 (64-Bit) (nur für Migrationszwecke unterstützt) oder System Center Operations Manager 2012 SP1 &amp; R2 (64-Bit) verwendet werden. In der folgenden Tabelle sind die unterstützten Konfigurationen für die Management Packs für Skype for Business Server 2019 aufgeführt: 
  
|**Konfiguration**|**Unterstützt?**|
|:-----|:-----|
|Windows Server 2008 R2-Betriebssystem  <br/> Windows Server 2012 R2-Betriebssystem  <br/> |Ja. Sowohl auf Skype for Business Server 2019-Servern als auch auf synthetischen Transaktions-Watcher-Knoten.  <br/> |
|Gruppierte Server  <br/> |Nicht unterstützt  <br/> |
|Agentlose Überwachung  <br/> |Nicht unterstützt  <br/> |
|Virtuelle Umgebung  <br/> |Ja.  <br/> |
|In die Domäne getretene Serverrollen  <br/> |Alle internen Skype for Business Server 2019-Serverrollen müssen der Domäne beigetreten sein.  <br/> |
|Eigenständige Serverrollen  <br/> |Skype for Business Server 2019-Edgeserver müssen nicht der Domäne beigetreten sein.  <br/> |
|Topologieeinschränkungen  <br/> |Alle Serverrollen in einer Bereitstellung müssen von derselben Operations Manager-Verwaltungsgruppe überwacht werden.  <br/> |
|Watcherknoten für synthetische Transaktionen  <br/> |Die Verfügbarkeit des Überwachungsszenarios mit einem Überwachungsknoten für synthetische Transaktionen wird unterstützt (zusätzliche Konfiguration erforderlich). Watcherknoten müssen nicht mit der Domäne verbunden sein.  <br/> |
   
In der folgenden Tabelle sind die Kapazitäts- und Betriebssystemanforderungen für einen synthetischen Transaktions-Watcher-Knoten aufgeführt:
  
|**Hardwarekomponente**|**Mindestanforderung**|
|:-----|:-----|
|CPU  <br/> |Eine der folgenden Optionen:  <br/> 64-Bit-Prozessor, Quad-Core, 2,33 GHz oder höher  <br/> 64-Bit-2-Wege-Prozessor, Dual-Core, 2,33 GHz oder höher  <br/> |
|Arbeitsspeicher  <br/> |8 GB  <br/> |
|Betriebssystem  <br/> |Windows Server 2008 R2  <br/> Windows Server 2012 R2  <br/> |
|Netzwerk  <br/> |1 Netzwerkadapter bei 1 GBit/s  <br/> |
   
## <a name="prerequisites"></a>Voraussetzungen

Zum Ausführen eines synthetischen Transaktions-Watcher-Knotens müssen Sie zuerst Folgendes installieren:
  
- System Center Operations Manager Agent 
    
-  Microsoft .NET Framework 4.5
    
- Skype for Business Server-Kerninstallationsdateien (OcsCore.msi) und Unified Communications Managed API (UCMA) (Versionen müssen mit der Skype for Business Server-WatcherNode.msi übereinstimmen)
    
## <a name="files-in-this-monitoring-pack"></a>Dateien in diesem Monitoring Pack

Das Monitoring Pack für Skype for Business Server 2019 enthält die folgenden Dateien:
  
- Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp
    
- Microsoft.LS.2019.Monitoring.ComponentAndUser.mp
    
- WatcherNode.msi
    
## <a name="whats-new"></a>Neuerungen

Die folgenden Features sind neu in Skype for Business Server 2019 Management Packs.

- **Änderungen im [Update vom September 2019](https://www.microsoft.com/download/details.aspx?id=57511)** Bei einigen Warnungen wurden Sonderzeichen entfernt. In einigen Fällen stören Sonderzeichen das Benachrichtigungsfeature für den SCOM-Befehlskanal.

- **Automatische Ermittlung für die Client-Anmeldung** Clientanwendungen, die sich bei Skype for Business Server 2019 anmelden, ermitteln häufig automatisch den Server für die Anmeldung. Synthetische Transaktionen unterstützen jetzt die Überprüfung, ob die automatische Ermittlung ordnungsgemäß konfiguriert ist.
    
- **Angepasste Intervalle für die Ausführung synthetischer Transaktionen** Um den Einrichtungsprozess von Watcher Nodes zu vereinfachen, können synthetische Transaktionen Benutzerkonten gemeinsam verwenden. Dadurch wird die Häufigkeit verlangsamt, mit der die Tests ausgeführt werden, wenn die Tests serialisiert werden, um Konflikte zu vermeiden. Synthetische Transaktionen werden standardmäßig alle 15 Minuten ausgeführt, um sicherzustellen, dass alle Tests ausgeführt werden können. Administratoren, die mehr Benutzer oder weniger Tests pro Benutzer verwenden, können nun auch das Ausführungsintervall reduzieren.
    
- **Synthetische Transaktion für Video Interop Services** Kunden, die von anderen Anbieterlösungen zu Skype for Business Server 2019 migrieren, möchten häufig weiterhin die Videotelekonferenzgeräte (VTCs) dieser anderen Anbieter verwenden. Video Interop Server ist eine neue Skype for Business Server 2019-Serverrolle, mit der Kunden cisco VTCs weiterhin in ihren Konferenzräumen verwenden können, indem sie über einen Video-SIP-Trunk eine Verbindung mit Cisco CUCM herstellen. Dieses Feature fügt außerdem eine synthetische Transaktion hinzu, um zu überprüfen, ob der Video interop Server verfügbar ist und eingehende Verbindungen über einen Video-SIP-Trunk verarbeiten kann.
    
- **Synthetische Transaktion für Anwendungsfreigabekonferenzen** Die End-to-End-Szenarioüberprüfung für Anwendungsfreigabekonferenzen wird jetzt unterstützt.
    
## <a name="monitoring-scenarios"></a>Überwachungsszenarien

Das Skype for Business Server 2019 Management Pack nutzt eine Vielzahl von Features, um Probleme zu erkennen und zu diagnostizieren. Diese Features bieten Echtzeitsicht auf den Zustand einer Skype for Business Server 2019-Umgebung.
  
|**Überwachungsszenario**|**Beschreibung**|
|:-----|:-----|
|Synthetische Transaktionen  <br/> | Windows PowerShell cmdlets zum Testen und Sicherstellen einer hohen Verfügbarkeit von Szenarien wie Anmeldung, Anwesenheit, Telefonkonferenzen und Konferenzen für Benutzer. <br/> Die synthetischen Transaktionen können von jedem geografischen Standort ausgeführt werden, auch innerhalb des Unternehmens, außerhalb des Unternehmens und in Zweigstellen.  <br/> Wenn bei einer synthetischen Transaktion ein Fehler auftritt, werden HTML-Protokolle erstellt, um die genaue Art des Fehlers zu ermitteln. Dies umfasst das Verständnis, welche Aktion fehlgeschlagen ist, die Wartezeit der einzelnen Aktionen, die Befehlszeile, die zum Ausführen des Tests verwendet wird, und den spezifischen Fehler, der aufgetreten ist.  <br/> |
|Warnungen zur Anrufzuverlässigkeit  <br/> |Von Skype for Business Server 2019-Servern verfasste Anrufdetaildatensätze (Call Detail Records, CDRs) geben an, ob Benutzer eine Verbindung mit einem Anruf herstellen können oder warum ein Anruf beendet wird. Anrufzuverlässigkeitswarnungen fragen die CDR-Datenbank ab, um Warnungen zu generieren, die angeben, ob bei einer hohen Anzahl von Benutzern Verbindungsprobleme bei Peer-zu-Peer-Anrufen oder grundlegenden Konferenzfunktionen auftreten.  <br/> Die Szenarioabdeckung umfasst Audioanrufe, Peer-to-Peer-Chats und andere Konferenzfunktionen.  <br/> |
|Warnungen zur Medienqualität  <br/> |Datenbankabfragen, die sich auf QoE-Berichte (Quality of Experience) von Skype for Business Server 2019-Clients am Ende jedes Anrufs anzeigen. Diese Abfragen erzeugen Warnungen, in denen Szenarien mit hoher Wahrscheinlichkeit gefährdete Medienqualität bei Anrufen und Konferenzen auftreten. Die Daten sind auf wichtigen Metriken wie Paketwartezeit und -verlust aufgebaut, die direkt zur Qualität der Benutzerfreundlichkeit beitragen.  <br/> |
|Komponentenintegzustandswarnungen  <br/> |Einzelne Serverkomponenten auslösen Warnungen über Ereignisprotokolle und Leistungsindikatoren, um Fehlerbedingungen anzugeben, die sich erheblich auf Benutzerszenarien auswirken können. Diese Warnungen weisen auf eine Vielzahl von Bedingungen hin, z. B. nicht ausgeführte Dienste, hohe Fehlerraten, hohe Nachrichtenlatenz oder Konnektivitätsprobleme.  <br/> |
|Überwachung der Abhängigkeitsinteität  <br/> |Skype for Business Server kann aus verschiedenen externen Gründen fehlschlagen. Das Management Pack überwacht und sammelt Daten für kritische externe Abhängigkeiten, die auf schwerwiegende Probleme hinweisen können. Diese Abhängigkeiten umfassen die Verfügbarkeit von Internetinformationsdienste (Internet Information Services, IIS) und die CPU von Servern, die für Skype for Business Server verwendet werden.  <br/> |
   
### <a name="alert-prioritization"></a>Warnungs priorisierung

Warnungen werden in die folgenden Kategorien unterteilt: 
  
 **Warnungen mit hoher Priorität:** Diese Warnungen weisen auf Bedingungen hin, die Dienstausfälle für große Benutzergruppen verursachen und sofortige Maßnahmen erfordern. Ausfälle, die von synthetischen Transaktionen und Offlinediensten (z. B. Skype for Business Server Audio/Video Conferencing) erkannt werden, gelten als Warnungen mit hoher Priorität. Im Gegensatz dazu ist ein Komponentenfehler auf einem einzelnen Computer keine Warnung mit hoher Priorität. Skype for Business Server 2019 verfügt für diese Situationen über integrierte Hochverfügbarkeitsfeatures, z. B. mehrere Front-End-Server hinter Lastenausgleichsservern.
  
 **Warnungen mit mittlerer Priorität:** Diese Warnungen weisen auf Bedingungen hin, die sich auf eine Teilmenge von Benutzern auswirken oder auf Probleme in der Anrufqualität hinweisen, z. B. Komponentenfehler, Wartezeiten bei der Anrufeinrichtung oder eine niedrigere Audioqualität bei Anrufen. Warnungen in dieser Kategorie sind statusreich (d. h. die Art der Warnung ändert sich basierend auf dem Status der Netzwerkverbindung.) Wenn z. B. die Zeiten für die Anrufereinrichtung die Wartezeit angeben, aber dann zu einem normalen Schwellenwert zurückkehren, wird diese Warnung mit mittlerer Priorität im System Center Operations Manager automatisch aufgelöst, und Administratoren müssen keine Maßnahmen ergreifen. Warnungen, die nicht automatisch aufgelöst werden können, werden in der Regel von Administratoren am gleichen Geschäftstag adressiert.
  
 **Weitere Warnungen:** Diese Warnungen werden von Komponenten generiert, die sich auf einen bestimmten Benutzer oder eine Teilmenge von Benutzern auswirken können. Eine typische Warnung wäre beispielsweise, dass der Adressbuchdienst den Active Directory® Domain Services (AD DS)-Eintrag für Benutzer nicht analysieren konnte: testuser@contoso.com. Administratoren können diese Warnungen immer dann adressiert haben, wenn ihnen Zeit zur Verfügung steht.
  
### <a name="synthetic-transactions"></a>Synthetische Transaktionen

Skype for Business Server 2019 Management Packs bieten eine höhere Abdeckung von Warnungen durch synthetische Transaktionen. Synthetische Transaktionen sind Windows PowerShell cmdlets, die in das Operations Manager Management Pack integriert sind, um End-to-End-Benutzerszenarien zu testen. Wenn Sie einen Server zum Ausführen synthetischer Transaktionen festlegen, werden diese Cmdlets regelmäßig vom Management Pack ausgelöst. Fehler, die sich aus einer synthetischen Transaktion ergeben, generieren eine Statuswarnung. Hier sind unterstützte synthetische Transaktionen für Skype for Business Server 2019:
  
**Unterstützte synthetische Transaktionen für Registrierung, Anwesenheit und Kontakte**

||||
|:-----|:-----|:-----|
|1  <br/> |Registrierung (Benutzeranmeldung)  <br/> |Verfügbar für Lync Server 2010 und darüber hinaus  <br/> |
|2  <br/> |Adressbuchdienst (Dateidownload)  <br/> |Verfügbar für Lync Server 2010 und darüber hinaus  <br/> |
|3  <br/> |Adressbuchwebabfrage  <br/> |Verfügbar für Lync Server 2010 und darüber hinaus  <br/> |
|4   <br/> |Anwesenheit  <br/> |Verfügbar für Lync Server 2010 und darüber hinaus  <br/> |
|5   <br/> |Einheitlicher Kontaktspeicher  <br/> |Verfügbar für Lync Server 2013 und darüber hinaus  <br/> |
   
**Unterstützte synthetische Transaktionen für Peer-to-Peer-Dienste**

||||
|:-----|:-----|:-----|
|6   <br/> |Peer-to-Peer-Chat  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|7   <br/> |Peer-to-Peer-Audiovideo  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|8   <br/> |MCX Peer-to-Peer-Sofortnachricht (mobil)  <br/> |Verfügbar in der September 2011-Version von Lync Server 2010 für Skype for Business 2019  <br/> |
 
> [!NOTE]
> McX(Mobility Service)-Unterstützung für ältere mobile Clients ist in Skype for Business Server 2019 nicht mehr verfügbar. Alle aktuellen mobilen Skype for Business-Clients verwenden bereits die Unified Communications Web API (UCWA) zur Unterstützung von Chat, Anwesenheit und Kontakten. Benutzer mit Legacyclients, die MCX verwenden, müssen ein Upgrade auf einen aktuellen Client durchführen.
  
**Unterstützte synthetische Transaktionen für Konferenzen und beständigen Chat**

||||
|:-----|:-----|:-----|
|9   <br/> |Audio/Video-Konferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|10    <br/> |Datenkonferenzen  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|11  <br/> |Chatkonferenzen  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|12   <br/> | Beständiger Chat <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|13  <br/> |Teilnehmen Startprogramm (geplante Besprechungen)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|14   <br/> |Einwahlkonferenzen  <br/> |Verfügbar in Skype for Business Server 2015 und darüber hinaus <br/> |
|15   <br/> |Anwendungsfreigabekonferenzen  <br/> |Verfügbar in Skype for Business Server 2015 und darüber hinaus <br/> |
|16   <br/> |UCWA Conference (Web Meeting Join)  <br/> |Verfügbar in Skype for Business Server 2015 und darüber hinaus <br/> |
   
**Unterstützte synthetische Transaktionen für Netzwerk- und Partnerabhängigkeiten**

||||
|:-----|:-----|:-----|
|17   <br/> |AV Edge Connectivity  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|18   <br/> |AV Edge Connectivity Exchange Unified Message Connectivity (Voicemail)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
|19  <br/> |PSTN-Peer-zu-Peer-Anruf  <br/> |Verfügbar in Lync Server 2010 und darüber hinaus  <br/> |
|20  <br/> |XMPP Instant Messaging (Verbund)  <br/> |Verfügbar in Lync Server 2013 und darüber hinaus  <br/> |
| 21  <br/> |Video-Interoperabilitätsserver  <br/> |Verfügbar in Skype for Business Server 2015 und darüber hinaus  <br/> |
   
## <a name="how-health-rolls-up"></a>So wird integritätsroll up

Die folgende Tabelle zeigt den Integritätszustand von Objekten, die das Skype for Business Server Monitoring Pack enthält.
  
|**Management Pack-Objekt**|**Beschreibung**|
|:-----|:-----|
|Skype for Business Server-Bereitstellung  <br/> |Stellt die Bereitstellung von Skype for Business Server 2019 in der Organisation dar.  <br/> |
|Skype for Business Server Site  <br/> |Stellt verschiedene geografische Standorte dar, an denen Dienste bereitgestellt werden.  <br/> |
|Skype for Business Server Pool  <br/> |Ein Pool (innerhalb eines Standorts), der Benutzern Kommunikationsdienste wie Chat und Konferenzen zur Verfügung stellt. Gilt für Front-End-Pools, Edgepools und Director-Pools, auch wenn nur ein einzelner Computer in einem bestimmten Pool vorhanden ist.  <br/> |
|Skype for Business Server Role  <br/> |Eine Serverrolle, die Skype for Business Server Service hostet.  <br/> |
|Skype for Business Server Service  <br/> |Stellt eine Auf einem bestimmten Computer bereitgestellte Funktionalität dar (z. B. Benutzerdienst auf fp01.contoso.com).  <br/> |
|Skype for Business Server-Komponente  <br/> |Eine Komponente des Diensts (z. B. die Komponente "Adressbuchdownload" ist Teil des Webdiensts).  <br/> |
|Skype for Business Server Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Pool ausgeführt werden.  <br/> |
|Skype for Business Server Registrar Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Registrierungsstellenpool ausgeführt werden.  <br/> |
|Skype for Business Server User Services Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen User Services-Pool ausgeführt werden.  <br/> |
|Skype for Business Server Voice Pool Watcher  <br/> |Eine Instanz synthetischer Transaktionen, die für einen Voicepool ausgeführt werden.  <br/> |
|Skype for Business Server Port Watcher  <br/> |Eine Instanz von Portprüfungen, die für einen Pool ausgeführt werden.  <br/> |
|Einfacher URL-Watcher  <br/> |Führt eine HTTPS-Probe der konfigurierten einfachen URLs in einer Bereitstellung durch.  <br/> |
   
![SCOM-Rollup](../../SfbServer/media/de16195d-3aed-412e-9def-07a481d2ff0f.png)
  
Ein Skype for Business Server-Pool kann mehrere einzelne Skype for Business Server-Systeme enthalten (mit mehr als einer Skype for Business Server-Rolle, einem Skype for Business Server-Dienst und einer Skype for Business Server-Komponente). Daher ist der Ausfall eines einzelnen Servers oder einer Komponente weniger wichtig für den Gesamtzustand des Skype for Business Server-Pools, da andere Server im gleichen Pool den Anwendungsdienst für den Client bereitstellen können. Der Integritätsrollup wird auf einer Prozentebene zum Skype for Business Server-Pool ausgeführt. 
  
Der Skype for Business Server Pool Watcher führt synthetische Transaktionen für einen Skype for Business Server-Pool aus. Bei einem aufeinander folgenden Fehler einer oder mehreren synthetischen Transaktionen (einem Prozess, der als aufeinander folgendes Abrufintervall bezeichnet wird) wird der kritische Integritätsstatus auf poolebene (am schlechtesten bei einer synthetischen Transaktion) rollupiert, wie im folgenden Diagramm dargestellt. 
  
![Aufeinander folgende Abrufe des SCOM-Rollups](../../SfbServer/media/655de542-cca7-4eda-8052-9a7703ecd0e9.png)
  
## <a name="best-practice-create-a-management-pack-for-customizations"></a>Bewährte Methode: Erstellen eines Management Packs für Anpassungen

Standardmäßig speichert Operations Manager alle Anpassungen, z. B. Überschreibungen im Standardverwaltungspaket. Als bewährte Methode sollten Sie ein separates Management Pack für jedes versiegelte Management Pack erstellen, das Sie anpassen möchten. 
  
Wenn Sie ein Management Pack zum Speichern angepasster Einstellungen für ein versiegeltes Management Pack erstellen, wird empfohlen, das neue Management Pack entsprechend zu benennen, z. B. "Skype for Business Server 2019 Customizations".
  
Das Erstellen eines neuen Management Packs zum Speichern von Anpassungen jedes versiegelten Management Packs erleichtert das Exportieren der Anpassungen aus einer Testumgebung in eine Produktionsumgebung. Dies erleichtert auch das Löschen eines Management Packs, da Sie alle Abhängigkeiten löschen müssen, bevor Sie ein Management Pack löschen können. Wenn Anpassungen für alle Management Packs im Standardverwaltungspaket gespeichert werden und Sie ein einzelnes Management Pack löschen müssen, müssen Sie zuerst das Standardverwaltungspaket löschen, das auch Anpassungen an anderen Management Packs löscht. 
  
## <a name="links"></a>Links

Die folgenden Links verbinden Sie mit Informationen zu allgemeinen Aufgaben, die System Center 2012 Monitoring Packs zugeordnet sind:
  
- [Lebenszyklus von Management Pack](/previous-versions/system-center/system-center-2012-R2/hh212732(v=sc.12))
    
- [Importieren eines Management Packs in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh212691(v=sc.12))
    
- [Überschreiben einer Regel oder eines Monitors](/previous-versions/system-center/system-center-2012-R2/hh212869(v=sc.12))
    
- [Erstellen eines "Als Konto ausführen" in Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh321655(v=sc.12))
    
- [Verwalten der Ausführung als Konten und Profile](/previous-versions/system-center/system-center-2012-R2/hh212714(v=sc.12))
    
- [Exportieren eines Operations Manager Management Packs](/previous-versions/system-center/system-center-2012-R2/hh320149(v=sc.12))
    
- [Entfernen eines Operations Manager Management Packs](/previous-versions/system-center/system-center-2012-R2/hh230746(v=sc.12))
    
Die folgenden Links verbinden Sie mit Informationen zu allgemeinen Aufgaben, die System Center 2007 Monitoring Packs zugeordnet sind:
  
- [Verwalten des Management Pack-Lebenszyklus](/previous-versions/system-center/operations-manager-2007-r2/cc974486(v=technet.10))
    
- [Importieren eines Management Packs in Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/cc974494(v=technet.10))
    
- [Überwachen von Außerkraftsetzungen](/previous-versions/system-center/operations-manager-2007-r2/bb309719(v=technet.10))
    
- [So erstellen Sie ein Konto ausführen in Operations Manager 2007](/previous-versions/system-center/operations-manager-2007-r2/bb309445(v=technet.10))
    
- [So ändern Sie eine vorhandene Ausführung als Profil](/previous-versions/system-center/operations-manager-2007-r2/dd891202(v=technet.10))
    
- [Exportieren von Management Pack-Anpassungen](/previous-versions/system-center/operations-manager-2007-r2/cc974487(v=technet.10))
    
- [Entfernen eines Management Packs](/previous-versions/system-center/operations-manager-2007-r2/cc974489(v=technet.10))
    
Fragen zu Operations Manager und Monitoring Packs finden Sie im [System Center Operations Manager-Communityforum](https://go.microsoft.com/fwlink/p/?LinkID=179635).
  
Eine nützliche Ressource ist der [Blog System Center Operations Manager Unleashed,](https://opsmgrunleashed.wordpress.com/) der "Nach Beispiel" Beiträge für bestimmte Monitoring Packs enthält.
  
Weitere Informationen zum Operations Manager finden Sie in den folgenden Blogs: 
  
- [Operations Manager-Teamblog](https://blogs.technet.com/momteam/default.aspx)
    
- [Kevin Holmans OpsMgr-Blog](https://blogs.technet.com/kevinholman/default.aspx)
    
- [Gedanken zu OpsMgr](https://thoughtsonopsmgr.blogspot.com/)
    
- [Blog von Raffael Burri](https://rburri.wordpress.com/)
    
- [Verwaltungsraum von BWren](https://blogs.technet.com/brianwren/default.aspx)
    
- [Ops Mgr ++](https://blogs.msdn.com/boris_yanushpolsky/default.aspx)
    
> [!IMPORTANT]
> Alle Informationen und Inhalte auf Nicht-Microsoft-Websites werden vom Besitzer oder den Benutzern der Website bereitgestellt. Microsoft übertut keine ausdrücklichen, impliziten oder gesetzlichen Garantien für die Informationen auf dieser Website. 
  
## <a name="see-also"></a>Siehe auch

[Skype for Business Server 2019-Verwaltungstools](../management-tools-2019.md)