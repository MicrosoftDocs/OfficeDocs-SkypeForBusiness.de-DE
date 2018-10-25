---
title: Systemanforderungen für Skype für Business Server 2019
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Zusammenfassung: Vorbereiten Sie Ihrer Skype Business Server 2019 Servern Infrastruktur und die Domäne mit den in diesem Thema. Hardware, OS, Datenbanken, Software, alle die Systemanforderungen und Empfehlungen, zusammen mit Zertifikat DNS, Dateifreigabe und Active Directory-Informationen sind hier zur Sicherstellung einer erfolgreichen Installation und Bereitstellung Ihrer Serverfarm.'
ms.openlocfilehash: e8a5b29bb555df6ae3920d521dd21ca8bbe38d7f
ms.sourcegitcommit: 50dca374ef698dcdf787be815969be58f36562bb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "25784702"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Systemanforderungen für Skype für Business Server 2019
 
**Zusammenfassung:** Vorbereiten von Skype für Business Server 2019 mit diesem Thema zu installieren. Hier werden Hardware, Betriebssystem, Software, Datenbanken, Zertifikate, Active Directory, DNS und Dateifreigaben behandelt. Alle Systemanforderungen und-Empfehlungen sind hier zur Sicherstellung einer erfolgreichen Installation und Bereitstellung Ihrer Serverfarm.
  
Wie zu erwarten, sind einige vorbereitenden Schritte vor Beginn der Bereitstellung von Skype für Business Server 2019. Dieser Artikel führt Sie durch die Planung der folgenden Aspekte:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Betriebssysteme](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Back-End-SQL-Datenbanken](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Zertifikate](system-requirements.md#Certs)
  
- [Dateifreigabe](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware für Skype für Business Server 2019
<a name="Hardware"> </a>

Nachdem Sie Ihrer Topologie nach unten (und haben Sie dies nicht zutrifft, können Sie die [Topologiegrundlagen Skype für Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) Thema Auschecken), hat es Zeit über Server entspricht. Skype für Business Server 2019 Server ist 64-Bit-Hardware erforderlich. Unsere Empfehlungen für die Hardware finden Sie weiter unten. Zwar handelt es sich dabei nicht um Anforderungen, aber die Empfehlungen entsprechen den Anforderungen, die für eine optimale Leistung erfüllt sein müssen. Wir bieten Ihnen eine Dokumentation zur Kapazitätsplanung, mit deren Hilfe Sie ermitteln können, ob Sie je nach Ihrer Situation Weiteres benötigen.
  
Empfohlene Hardware für Standard Edition-Server:

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype für Business Server 2019 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualmodus oder Multihoming-Konfigurationen werden **nicht** für Front-End-Server, Back-End-Servern und Standard Edition Server unterstützt. <br/> Solange sie nicht verfügbar, für das Betriebssystem gemacht sind und zu überwachen und Verwalten von Serverhardware verwendet werden, können Sie Out-of-Band-Management-Systemen, wie DRAC oder ILO haben. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.  <br/> |


Empfohlene Hardware für Front-End-Server und Back-End-Servern:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher. <br/> Intel Itanium-Prozessoren werden für Skype für Business Server 2019 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |64 Gigabyte (GB).  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualmodus oder Multihoming-Konfigurationen werden **nicht** für Front-End-Server, Back-End-Servern und Standard Edition Server unterstützt. <br/> Solange sie nicht verfügbar, für das Betriebssystem gemacht sind und zu überwachen und Verwalten von Serverhardware verwendet werden, können Sie Out-of-Band-Management-Systemen, wie DRAC oder ILO haben. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3-Dualprozessor, 6-Core mit 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype für Business Server 2019 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (die Festplatten sollten in einer 2x-RAID-1-Konfiguration sein).  <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 4 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Video-Interop-Server und Directors **nicht** unterstützt. <br/> Edgeserver erfordern zwei Netzwerkschnittstellen, die aus Dual-Port-Netzwerkadaptern bestehen, mit mindestens 1 GBit/s (oder zwei gepaarte Netzwerkadapter, also insgesamt vier; jedes Paar muss mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden, um insgesamt zwei Paare zu erhalten).  <br/> Auf eigenständigen Vermittlungsserver wird die Installation von zusätzlichen Netzwerkschnittstellenkarten (NICs), um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen, unterstützt.  <br/> |


> [!NOTE]
> Unabhängig von der Serverrolle, empfehlen wir auch die folgenden hardwareeinstellungen für Skype für Business Server 2019 (Dies kann variieren je nach dem Hersteller der Hardware, die Sie gekauft haben, dass Näheres Dokumentation des Herstellers Einzelheiten):
> - BIOS-Config - festgelegt werden sollte flach aus NUMA.
> - Aktivieren Sie Hyperthreading.
> - Die Einstellung der RSS-Warteschlange sollte auf 8 Warteschlange festgelegt werden.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Betriebssysteme für Skype für Business Server 2019
<a name="OS"> </a>

Nachdem Sie die Hardware verfügen, müssen Sie für das Betriebssystem installieren (OS), mit denen Sie zum Installieren und verwenden Skype erfolgreich für Business Server 2019.
  
|||
|:-----|:-----|
|WindowsServer 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Alles außer den hier aufgelisteten Betriebssystemen nicht ordnungsgemäß funktioniert; Versuchen Sie nicht es für die Installation von Skype für Business Server 2019.

> [!NOTE]
> 
> Wenn Sie auf dem Computer Windows Server 2019 Windows Admin Center 2019 installieren, werden Sie für einen Port Abhören aufgefordert. Es ist eine Liklihood Sie Port 443 auswählen können, jedoch ist dieses Computers Skype für Business Server 2019 installiert wurde, oder Skype für Business Server 2019 installiert haben, wählen Sie dann Sie müssen eine andere Portnummer.
> 
>Warum dies der Fall ist? Wenn Windows Admin Center 2019 an Port 443 ausgeführt wird, Sie werden nicht mit dem Server mit der Skype für die Business-Systemsteuerung herstellen, und Sie können Sie eine Verbindung herstellen auf einen beliebigen internen Webdienst auf dem Server (Web Adressbuchdienst ausgeführt Autodiscover Service, WebTicket Service usw.).  Tatsächlich werden Sie keine internen Webdienst-URL herstellen sein. Wählen Sie einen anderen Port, in der Ereignisprozedur benötigen oder Windows Admin Center 2019 auf einem Server mit Skype für Business Server 2019 aufnehmen möchten.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software, die vor einem Skype für Business Server 2019 Bereitstellung installiert werden muss
<a name="Software"> </a>

Es gibt einige Dinge, die Sie also installieren oder für einen Server mit Skype für Business Server 2019 konfigurieren müssen. Diese sind unten aufgeführt, gefolgt von zusätzlichen Anforderungen für bestimmte Serverrollen.
  
 **Alle Server:**
  
|**Software-Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Auf allen Skype for Business Server-Servern muss Windows PowerShell 3.0 installiert sein.  <br/> • Dies standardmäßig mit Windows Server 2016 installiert werden soll.<br/> |
|Microsoft .NET Framework  <br/> |Die WCF-Dienste sind als Windows-**Funktion** unter **Server-Manager** installiert. Sie müssen nichts herunterladen. <br/> • Wenn Sie diese Funktion installieren oder wenn die Funktion bereits installiert ist und Sie sie überprüfen möchten, müssen Sie sicherstellen, dass wie in dieser Abbildung auch die Option **HTTP-Aktivierung** aktiviert und installiert ist: <br/> ![Screenshot mit HTTP-Aktivierungsoption unter den .NET Framework 4.5-Features](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Machen Sie sich keine Sorgen, wenn ein zusätzliches Popup-Fenster angezeigt wird und Sie darüber informiert, dass für die HTTP-Aktivierung noch andere Komponenten installiert werden müssen. Das ist normal. Klicken Sie auf OK, und fahren Sie fort. Wenn Sie dies Popupfenster nicht erhalten, können Sie davon ausgehen, Dinge bereits installiert sind, und fahren Sie fort.  <br/> Microsoft .NET Framework wird in der Regel zusammen mit Windows Server 2016 installiert ist. Skype for Business Server funktioniert mit den folgenden Versionen von Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 <br/> |
|Media Foundation  <br/> |Für Windows Server 2016 wird die Windows Media Format-Laufzeitkomponente mit Microsoft Media Foundation installiert.  <br/> Alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, benötigen die Windows Media-Format-Laufzeitkomponente, damit die WMA-Dateien (Windows Media Audio) ausgeführt werden können. Über diese Dateien geben die Anwendungen für das Parken von Anrufen, für Ankündigungen und für Reaktionsgruppen Ankündigungen und Musik wieder.  <br/> |
|Windows Identity Foundation  <br/> |Wir brauchen Windows Identity Foundation 3.5 auf Server-zu-Server-Authentifizierungsszenarien für Skype für Business Server 2019 unterstützen.  <br/> • Für Windows Server 2016, besteht keine Notwendigkeit herunterladen. Öffnen Sie den **Server-Manager** und rufen Sie den **Assistenten zum Hinzufügen von Rollen und Features** auf. **Windows Identity Foundation 3.5** wird unter dem Abschnitt **Funktionen** aufgelistet. Wenn es aktiviert ist, können Sie eine gute. Andernfalls wählen Sie sie aus, und klicken Sie auf **Weiter** , um die Schaltfläche **Installieren** zu erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Für Front-End-Server und Standard Edition-Server benötigen Sie außerdem Folgendes:**
  
|**Software-Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (Internet Information Services, IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition-Servern benötigt. Dabei müssen die folgenden Module ausgewählt sein:  <br/> • Gemeinsam genutzte HTTP-Features: Standarddokument, HTTP-Fehler, Statischer Inhalt  <br/> • Systemzustand und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Authentifizierung über Clientzertifikatzuordnung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET-Erweiterbarkeit 3.5, .NET-Erweiterbarkeit 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI-Erweiterungen, ISAPI-Filter  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -tools  <br/> Beachten Sie, dass anonymer Zugriff ist auch erforderlich, aber Sie, die beim Installieren von IIS erhalten, sodass Sie nicht über einen Ort für die Auswahl in der Liste verfügen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016 müssen Sie das Feature **Media Foundation** im **Server-Manager**zu installieren. Ihre Skype für die Installation von Business Server 2019 ohne diese tatsächlich können starten aber werden Sie aufgefordert, ihn zu installieren, und klicken Sie dann den Server, bevor Sie die Skype für Business Server 2019 installieren Neustart fortgesetzt wird. Es ist besser, dies voraus. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight installieren [hier](https://www.microsoft.com/silverlight/).  <br/> |
   
Wir zeigen Ihnen nun das Beispiel eines PowerShell-Skripts, um dies zu automatisieren:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

 **Für Directors benötigen Sie außerdem Folgendes:**
  
IIS mit den folgenden ausgewählten Modulen:
  
- Allgemeine HTTP-Funktionen
    
  - Standarddokument
    
  - HTTP-Fehler
    
  - Statischer Inhalt
    
- Integrität und Diagnose
    
  - HTTP-Protokollierung
    
  - Protokollierungstools
    
  - Ablaufverfolgung
    
- Leistung
    
  - Komprimierung statischer Inhalte
    
- Sicherheit
    
  - Anforderungsfilterung
    
  - Clientzertifikatzuordnungs-Authentifizierung
    
  - Windows-Authentifizierung
    
- Anwendungsentwicklung
    
  - .NET-Erweiterbarkeit 3.5
    
  - .NET-Erweiterbarkeit 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI-Erweiterung
    
  - ISAPI-Filter
    
(Hierbei handelt es sich um die gleichen Module wie für die Front-End-Server und Standard Edition-Server, nur ohne die Komprimierung dynamischer Inhalte und die Verwaltungstools.)
  
Außerdem finden Sie dazu hier PowerShell-Code:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Back-End-Datenbanken, die mit Skype für Business Server 2019 funktioniert
<a name="DBs"> </a>

Wenn Sie Skype Business Server 2019 Standard Edition installieren, müssen Sie SQL Server 2016 Express (64-Bit-Edition).

Skype für Business Server 2019 Enterprise Edition benötigen vollständiger SQL Server, wie unten angegeben (nur 64-Bit-Version; nicht verwenden Sie 32-Bit-Editionen):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2016 (64-Bit-Edition), und Sie müssen mit den neuesten Updates und mit AlwaysOn-Verfügbarkeitsgruppen ausführen.  <br/> ||
 |
   
Wenn die von Ihnen gewünschte SQL Server-Edition nicht aufgeführt wird, können Sie sie nicht verwenden.
  
> [!NOTE]
> Außerdem müssen Sie SQL Server Reporting Services für den Monitoring Server-Role zu installieren. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL-Clustering und SQL immer auf

SQL-Clustering mit Skype für Business Server 2019 wird unterstützt. Wenn Sie SQL-Clustering einrichten möchten, erfolgt, die in SQL Server.
  
Stellen Sie sicher, dass Sie Aktiv/Passiv-Konfiguration für die SQL-Clustering, ist der unterstützt wird. Teilen Sie den passiven Knoten mit keiner anderen SQL-Instanz.
  
Für das Failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
- Microsoft SQL Server 2016 Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt.
    
Sechzehn Knoten:
  
- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.
    
Wir haben einen Artikel, Configure SQL Server clustering für Skype für Business Server 2019, die die Schritte zum Abrufen von clustering bereit.
 
SQL immer auf wird unterstützt, und Sie erhalten weitere genauer darüber in [hoher Verfügbarkeit von Back-End-Server in Skype für Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Zusätzliche Server mit der Installation beginnen:
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Clientsoftware oder andere Winsock-Mehrschicht-Dienstanbietersoftware auf Ihren Front-End-Servern oder eigenständigen Vermittlungsservern. Dies schließt auch sämtliche Drittanbieterfirewalls oder Antiviren-Netzwerkinspektionssoftware ein. Schlechte Media Datenverkehr Leistung wurde beobachtet, wenn diese Software installiert ist.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Obwohl viele der die Konfigurationsdaten für Server und Dienste in der Skype für Business Server 2019 zentralen Verwaltungsspeicher gespeichert werden, sind einige Punkte, die noch in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Skype für Business Server 2015 und Lync Server 2013 zum Aufrechterhalten der Abwärtskompatibilität mit der zuvor unterstützten Versionen  <br/> |
|Daten  <br/> |Der Benutzer-SIP-URI und andere Einstellungen  <br/> |
||Kontaktobjekte für Anwendungen (wie die reaktionsgruppenanwendung und die Anwendung Konferenzzentrale)  <br/> |
||Zur Abwärtskompatibilität veröffentlichte Daten  <br/> |
||Einen Dienststeuerungspunkt (SCP) für den zentralen Verwaltungsspeicher  <br/> |
||Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssysteme für Domänencontroller

Die folgenden Domänencontroller-Betriebssysteme kann verwendet werden:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Die Domänenfunktionsebene von jeder Domäne, die Sie zum Business Server 2019 in Skype bereitstellen und die Gesamtstrukturfunktionsebene von einer beliebigen Gesamtstruktur Ihnen Skype für Business Server 2019 in bereitgestellte, müssen eine der folgenden sein:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Dürfen in diesen Umgebungen schreibgeschützte Domänencontroller vorhanden sein? Sicher, solange dort auch sofern nicht schreibgeschützte Domänencontroller sind verfügbar.
  
Es ist wichtig, zu wissen, dass Skype für Business Server 2019 Domänen mit einfacher Bezeichnung unterstützt. Was ist das? Wenn Sie eine mit der Bezeichnung contoso.local Stammdomäne verfügen, geht, die kein Problem sein. Wenn Sie über eine Stammdomäne, die nur lokale heißt verfügen, nicht dadurch arbeiten, und nicht dementsprechend unterstützt. Mehr Informationen dazu finden Sie [in diesem Artikel der Knowledge Base](https://support.microsoft.com/kb/300684/en-us).
  
Skype für Business Server 2019 unterstützt keine auch Umbenennen von Domänen. Wenn Sie Ihre Domäne umbenennen müssen, müssen Sie So deinstallieren Sie Skype für Business Server 2019, führen Sie das Umbenennen von Domänen, und Neuinstallieren von Skype für Business Server 2019.
  
Schließlich Sie möglicherweise eine Domäne, in einer gesperrten AD DS-Umgebung zuständig sein, und das ist gut. Wir haben Weitere Informationen zum Bereitstellen von Skype für Business Server 2019 in einer gesperrten AD DS-Umgebung in der Bereitstellungsdokumentation.
  
### <a name="ad-topologies"></a>AD-Topologien

Unterstützte Topologien in Skype für Business Server 2019 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
    
Wir haben Diagramme und eine Beschreibung können Sie bestimmen, welche Topologie Sie in Ihrer Umgebung oder um benötigen Sie möglicherweise vor der Installation von Skype für Business Server 2019 eingerichtet haben. Wenn Sie um einfach zu halten, sind wir auch einen Schlüssel einschließlich:
  
![Schlüssel zu den Symbolen, die für Skype for Business-Topologiediagramme verwendet werden](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm einer einzelnen Active-Directory-Gesamtstruktur mit einer einzigen Domäne](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Es ist einfacher, als dies abgerufen werden. Es ist eine Gesamtstruktur mit einer Domäne eine häufig verwendete Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm mit einer einzigen Gesamtstruktur, einer einzelnen Struktur und mehreren Domänen](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt eine einzelne Gesamtstruktur, erneut, besitzt jedoch eine oder mehrere untergeordnete Domänen sowie (stehen drei in diesem Beispiel). Damit die Domäne, der die Benutzer in erstellt werden von der Skype-Domäne unterscheiden kann für Business Server 2019 bereitgestellt wird. Warum sorgen halten Sie davon? Es ist wichtig, die merken, wenn Sie einen Skype für Business Server-Front-End-Pool bereitstellen, müssen alle Server in diesem Pool in einer einzelnen Domäne sein. Sie können Cross-Domain-Verwaltung über Skype für Business Server für die Unterstützung von universellen Windows-Administratorgruppen haben.
  
Die in der Abbildung sehen Sie sich, dass Benutzer von einer Domäne Skype für Business Server-Pools aus derselben Domäne oder aus verschiedenen Domänen zugreifen können, auch wenn diese Benutzer in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm mit einer einzigen Gesamtstruktur, mehreren Strukturen und getrennten Namespaces](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Dieses Diagramm ähnelt eine Topologie mit möglicherweise, in einer Gesamtstruktur verfügen, aber in der Gesamtstruktur, mehrere Domänen mit separaten Active Directory-Namespaces verwendet werden. Dieses Diagramm ist in diesem Fall eine gute Illustration, da es Benutzer in drei unterschiedlichen Domänen, die Zugriff auf Skype für Business Server 2019 enthält. Einfarbige Linien anzugeben, dass sie einen Skype für Business Server Pool in ihrer eigenen Domäne zugreifen können, während eine gestrichelte Linie gibt an, dass der Kunde in einen Pool in einer anderen Struktur vollständig sind.
  
Wie Sie sehen können, können Benutzer in derselben Domäne, derselben Struktur oder sogar einer anderen Struktur Pools erfolgreich zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype für Business Server 2019 unterstützt mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. Wenn Sie nicht sicher sind, was Ihnen ist, verwendet die zentrale Gesamtstruktur in der Topologie Objekte im es zur Darstellung von Benutzern in anderen Gesamtstrukturen und Hosts von Benutzerkonten für alle Benutzer in der Gesamtstruktur an.
  
Wie funktioniert das? Ein verzeichnissynchronisierungsprogramm (wie Forefront Identity Manager oder FIM) verwaltet Benutzerkonten in der gesamten auf das Vorhandensein eines Unternehmens. Wenn ein Konto erstellt oder in der Gesamtstruktur gelöscht wird, wird diese Änderung im entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Deutlich, wenn Ihre Active Directory-Infrastruktur vorhanden ist, verschieben für diese Topologie ist möglicherweise nicht einfach, aber wenn Sie bereits vorhanden, oder weiterhin Planung Ihrer Gesamtstruktur Infrastruktur sind, kann dies eine gute Wahl sein. Sie können Ihre Skype für die Bereitstellung in einer einzelnen Gesamtstruktur, Business Server 2019 zentralisieren, während Benutzer kommunizieren, suchen und die Anwesenheit von anderen Benutzern in einer beliebigen Gesamtstruktur anzeigen können. Alle Benutzer, Kontakt Updates werden automatisch mit Synchronisierungssoftware behandelt.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie
<a name="BKMK_multipleforestopology"> </a>

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine Topologie mit Ressourcengesamtstruktur wird ebenfalls unterstützt. Es ist, in eine Gesamtstruktur für die Ausführung von Server-Anwendungen wie Microsoft Exchange Server und Skype für Business Server 2019 vorgesehen ist. Diese Ressourcengesamtstrukturen auch hostet, eine synchronisierte Darstellung des aktiven User-Objekte, jedoch keine bei der Anmeldung aktivierten Benutzerkonten. Damit die Ressourcengesamtstruktur eine Umgebung mit gemeinsamen Diensten für die anderen Gesamtstrukturen, ist in dem sich Benutzerobjekte befinden und auf Gesamtstrukturebene Vertrauensstellung mit der Ressourcengesamtstruktur lassen.
  
Beachten Sie, dass Exchange Server in der gleichen Gesamtstruktur als Skype für Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden kann.
  
Um Skype für Business Server 2019 bei dieser Art von Topologie bereitstellen, würden Sie ein deaktiviertes Benutzerobjekt erstellen, in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen (wenn Microsoft Exchange Server bereits in der Umgebung vorhanden ist, kann dies für Sie). Benötigen Sie eine verzeichnissynchronisierungstool (wie Forefront Identity Manager oder FIM) Benutzerkonten mit über ihres gesamten Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die unter [Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie](system-requirements.md#BKMK_multipleforestopology) beschrieben wird.
  
In dieser Topologie sind eine oder mehrere Benutzergesamtstrukturen und Skype für Business Server in einer dedizierten Ressourcengesamtstruktur bereitgestellt wird. Exchange Server lokal bereitgestellt in der gleichen Gesamtstruktur oder einer anderen Gesamtstruktur werden können und für die hybridbereitstellung mit Exchange Online konfiguriert sind, oder e-Mail-Dienste können ausschließlich von Exchange Online bereitgestellt werden, für die lokalen Konten. Es ist kein Diagramm für diese Topologie verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung und sind mit Office 365 unter Verwendung von Azure AD Connect synchronisiert. Alle Benutzer sind für Skype for Business über Office 365 aktiviert.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Bei diesem Szenario sind mehrere lokale Gesamtstrukturen mit einer Topologie mit Ressourcengesamtstruktur vorhanden. Zwischen den Active Directory-Gesamtstrukturen besteht eine vollständige Vertrauensstellung. Das Tool „Azure Active Directory Connect“ wird zur Synchronisierung von Konten zwischen den lokalen Benutzergesamtstrukturen und Office 365 verwendet.
  
 Die Organisation verfügt außerdem über Office 365 und verwendet [Azure Active Directory Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect) zur Synchronisierung ihrer lokalen Konten mit Office 365. Für Skype für Unternehmen aktivierte Benutzer werden über Office 365 und Skype für Business Online aktiviert. Skype für Business Server ist nicht lokal bereitgestellt.
  
Authentifizierung für einmaliges Anmelden wird von einer Active Directory Federation Services-Farm befindet sich in der benutzergesamtstruktur bereitgestellt.
  
In diesem Szenario wird es zum Bereitstellen von Exchange lokal, Exchange Online eine hybride Exchange-Lösung oder nicht in allen Bereitstellung von Exchange werden unterstützt. (Das Diagramm zeigt nur lokale Exchange-Organisation, aber die anderen Exchange-Lösungen sind auch vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business-Hybridbereitstellung
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario vorhanden sind oder mehr lokalen Benutzergesamtstrukturen und Skype für Unternehmen in einer dedizierten Ressourcengesamtstruktur bereitgestellt wird und mit Skype für Hybridmodus für Business Online konfiguriert. Exchange Server lokal bereitgestellt in der gleichen Gesamtstruktur oder einer anderen Gesamtstruktur werden können und für die hybridbereitstellung mit Exchange Online konfiguriert werden kann. Alternativ können e-Mail-Dienste für die lokalen Konten ausschließlich von Exchange Online bereitgestellt werden.
  
Weitere Informationen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für hybride Skype für Unternehmen](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype für Business Server 2019 erfordert DNS, aus den folgenden Gründen:
  
- DNS ermöglicht Skype für Business Server 2019 erkennen interner Server oder Pools, für die Server-zu-Server-Kommunikation ermöglicht.
    
- DNS ermöglicht Computern ermitteln können, die Front-End-Pool oder Standard Edition-Server für die SIP-Transaktionen verwendet wird.
    
- Es ordnet einfache URLs für Konferenzen den Servern zu, auf denen diese Konferenzen gehostet werden.
    
- DNS ermöglicht externen Benutzern und Clientcomputern Verbindung mit Ihrer Edge-Server oder dem HTTP-Reverseproxy für instant messaging (IM) oder für Konferenzen.
    
- Sie können die unified Communications (UC) Geräte, die in protokolliert werden nicht erkennen, den Front-End-Pool oder Standard Edition-Server mit der geräteaktualisierungswebdienst zum Abrufen von Updates und Protokolle senden können.
    
- Die Verwendung von DNS ermöglicht mobilen Clients die automatische Ermittlung von Webdienstressourcen, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.
    
- Es wurde in DNS-Lastenausgleich verwendet.
    
Es ist wichtig, beachten Sie, dass Skype für Business Server 2019 internationalisierten Domänennamen (IDNs) nicht unterstützt.
  
Und es ist sehr wichtig, denken Sie daran, dass ein Name im DNS identisch mit den Namen des Computers, auf einem beliebigen Server für Business Server 2019 von Skype verwendeten konfiguriert werden. Insbesondere wir keinen Short-Namen in der Umgebung, und die FQDNs für Topologie-Generator.
  
Dies scheint, als wäre es logische für jeden Computer, der bereits Mitglied einer Domäne, doch wenn Sie einen Edge-Server, der nicht an Ihre Domäne verbunden ist verfügen, es kann Standardwert einen kurzen Namen, wobei keine Domänensuffix. Stellen Sie sicher, dass dies nicht der Fall, in DNS oder auf dem Edge-Server oder eine beliebige Skype für Business Server 2019 Server oder Pool, darum geht ist.
  
Definitiv verwenden Sie nicht Unicode-Zeichen oder Unterstriche. Standard Zeichen (A – Z, a – Z, 0-9 und Bindestriche) werden von externen DNS- und öffentlichen Zertifizierungsstellen unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen es ist wichtig, denken Sie daran), sodass Sie sich selbst viel Aufwand Ersatzteile werden, wenn Sie einen Namen mit diesem Hintergrund vom Anfang.
  
Weitere Informationen zu den DNS-Anforderungen für Networking entnehmen Sie dem Abschnitt [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Stellen Sie vor der Bereitstellung unbedingt sicher, dass Ihre Zertifikate in Ordnung sind. Skype für Business Server 2019 benötigt eine public Key-Infrastruktur (PKI) für den Transport layer Security (TLS) und mutual Transport Layer Security (MTLS) Verbindungen. Im Grunde verwendet Skype für Business Server sicher in eine standardisierte Methode für die Kommunikation von Zertifizierungsstellen (CAs) ausgestellte Zertifikate.
  
Dies sind einige Aspekte, die für Business Server 2019 Skype-Zertifikaten für verwendet:
  
- TLS-Verbindungen zwischen Client und Server
    
- MTLS-Verbindungen zwischen Servern
    
- Verwenden die automatische DNS-Ermittlung von Partnern Verbund
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf AV-Sitzungen, Anwendungsfreigabe und Konferenzen
    
- Kommunizieren mit dem Webanwendungen und Outlook Web Access (OWA)
    
Zertifikatsplanung ist also ein muss. Nun, sehen wir uns eine Liste der einige Aufgaben Sie beim Anfordern von Zertifikaten bedenken müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Skype für Business Server 2019 unterstützt die SHA-1 und SHA-2-Programmsuite Digest (224, 256, 384 und 512-Bit), wird die Größe und erfüllt oder überschreitet die betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server mit Skype für Business Server 2019 unterstützt.
    
- Die automatische Registrierung wird für Skype für Business Server 2019 Edge-Server nicht unterstützt.
    
> [!NOTE]
> Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei der Anmeldung und Problemen mit der Anrufweiterleitung führen.  
  
- Es werden Verschlüsselungsschlüssellängen von 1.024, 2.048 und 4.096 Bit unterstützt. Empfohlen werden Schlüssellängen ab 2.048 Bit.
    
- Der standardmäßige Digest- bzw. Hashsignaturalgorithmus ist RSA. Die Algorithmen ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist eine Menge überlegen und stehen verschiedene Ebenen Komfort Anfordern von Zertifikaten von einer Zertifizierungsstelle. Wir geben Sie einige weitere Leitlinien unten um Ihrer Planung so einfach wie möglich zu machen.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten der von internen Servern und in den meisten Fällen erhalten Sie diese von einer internen Zertifizierungsstelle (die eine Zertifizierungsstelle befindet sich in Ihrer Domäne ist). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle (eins, die sich im Internet befinden) anfordern. Wenn Sie, welche öffentlichen Zertifizierungsstelle wissen möchten sollte navigieren Sie zu, Sie können die [Unified Communications-Partner Zertifikats](https://support.microsoft.com/kb/929395/en-us) Liste Auschecken.
  
Sie nun auch Zertifikate benötigen, wenn Skype für Business Server 2019 mit anderen Anwendungen und Server, wie beispielsweise Microsoft Exchange Server kommuniziert. Dies muss natürlich ein Zertifikat werden, die diese anderen apps und Server unterstützte Weise verwenden können. Skype für Business Server 2019 und andere Microsoft-Produkte unterstützen das Protokoll Open Authorization (OAuth) für Server-zu-Server-Authentifizierung und Autorisierung. Wenn Sie dies interessiert sind, haben wir eine zusätzliche Planungsartikel für OAuth und Skype für Business Server 2019.
  
Skype für Business Server 2019 umfasst auch Unterstützung für (ohne) mithilfe der kryptografischen Hash-Funktion SHA-256 signierte Zertifikate. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle unter Verwendung von SHA-256 ausgestellt werden.
  
Um Dinge einfach zu halten, haben wir die Anforderungen an Zertifikate für Standard Edition-Server, Front-End-Pools und andere Rollen in den folgenden Tabellen mit Speichern verwendeten Beispiele (Sie wahrscheinlich etwas anderes für verwenden die fiktive "contoso.com" Ihre Umgebung). Dies sind alle standard-Web-Serverzertifikate mit privaten Schlüsseln, die nicht exportiert werden können. Zusätzliche beachtet werden:
  
- Die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Der Anzeigename jedes Zertifikats muss im Computerspeicher eindeutig sein.
    
- Gemäß den Anweisungen in den Beispielnamen unten Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben müssen sie auf das Zertifikat Subject Alternative Name (SAN) hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Name/gemeinsamen Antragstellername**|**Alternativer Antragstellername**|**Beispiel**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.  <br/> |Für Standard Edition-Server ist der FQDN des Servers identisch mit den vollqualifizierten Domänennamen des Pools.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interne Web-FQDN (Dies entspricht dem FQDN des Servers ist)  <br/> UND  <br/> • Meet einfache URLs  <br/> • DFÜ-einfache URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für einfache URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> Sn=se01.contoso.com; SAN=se01.contoso.com; SAN =\*. "contoso.com"  <br/> |Das interne Web-FQDN im Topologie-Generator kann nicht überschrieben werden.  <br/> Wenn Sie mehrere einfache Meet-URLs haben, müssen Sie schließen Sie alle von ihnen als SANs.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externen Web-FQDN  <br/> UND  <br/> • DFÜ-einfache URL  <br/> • Meet einfache URLs pro SIP-Domäne  <br/> ODER  <br/> • Ein Platzhaltereintrag für einfache URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> Sn=se01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. "contoso.com"  <br/> |Wenn Sie mehrere einfache Meet-URLs haben, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Front-End-Pool:
  
|**Zertifikat**|**Name/gemeinsamen Antragstellername**|**Alternativer Antragstellername**|**Beispiel**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interne Web-FQDN (der nicht identisch mit den FQDN des Servers ist)  <br/> • FQDN des Servers  <br/> • Skype für Business Pool-FQDN  <br/> UND  <br/> • Meet einfache URLs  <br/> • DFÜ-einfache URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für einfache URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> Sn=ee01.contoso.com; SAN=ee01.contoso.com; SAN =\*. "contoso.com"  <br/> |Wenn Sie mehrere einfache Meet-URLs haben, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externen Web-FQDN  <br/> UND  <br/> • DFÜ-einfache URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für einfache URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> Sn=ee01.contoso.com; SAN=webcon01.contoso.com; SAN =\*. "contoso.com"  <br/> |Wenn Sie mehrere einfache Meet-URLs haben, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Name/gemeinsamen Antragstellername**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Default (Standard)  <br/> |Directorpool  <br/> |FQDN des Directors, des FQDN des Director-Pools.  <br/> Wenn in diesem Pool Server die automatische Anmeldung für Clients und exakte DNS-Abgleich ist erforderlich, in den Gruppenrichtlinien, Sie benötigen auch Einträge für sip.sipdomain (für jede SIP-Domäne).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Wenn dieser Director-Pool der Server für die automatische Anmeldung für Clients ist und exakte DNS-Abgleich in den Gruppenrichtlinien erforderlich ist, benötigen Sie auch festgelegt; SAN=SIP.Fabrikam.com  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interne Web-FQDN (Dies entspricht dem FQDN des Servers ist)  <br/> • FQDN des Servers  <br/> • Skype für Business Pool-FQDN  <br/> UND  <br/> • Meet einfache URLs  <br/> • DFÜ-einfache URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für einfache URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> Sn=dir01.contoso.com; SAN=dir01.contoso.com SAN =\*. "contoso.com"  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externen Web-FQDN  <br/> UND  <br/> • Meet einfache URLs pro SIP-Domäne  <br/> • DFÜ-einfache URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für einfache URLs  <br/> |Director externe Web-FQDN muss sich von den Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> Sn=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN =\*. "contoso.com"  <br/> |
   
Zertifikate für eigenständige Vermittlungsserver:
  
|**Zertifikat**|**Name/gemeinsamen Antragstellername**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedsservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance (insbesondere Survivable Branch-Gerät 2015 für Skype für Business Server 2019):
  
|**Zertifikat**|**Name/gemeinsamen Antragstellername**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Anwendung  <br/> |SIP. \<Sipdomain\> (Sie benötigen nur ein Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den Zugriff externer Benutzer (Edge)

Skype für Business Server 2019 unterstützt die Verwendung von ein **einzelnes öffentliches Zertifikat** für Zugriff und Konferenzen externe edgeschnittstellen plus der A / V-Authentifizierungsdienst, die alle über die Edgeserver bereitgestellt wird. Die interne Schnittstelle des Edgeservers wird in der Regel verwenden Sie ein privates Zertifikat von Ihrem internen Zertifizierungsstelle ausgestellt, aber wenn Sie es vorziehen, können ein öffentliches Zertifikat für diese ebenfalls, wenn sie von einer vertrauenswürdigen Zertifizierungsstelle stammt.
  
Ihr Reverseproxy (RP) wird ebenfalls ein öffentliches Zertifikat verwenden und es verschlüsselt die Kommunikation zwischen Ihrem Reverseproxy und den Clients sowie zwischen dem Reverseproxy und den internen Servern mithilfe von HTTP (oder präziser: TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen, und Sie sind automatische Ermittlung für mobile Clients unterstützen, können Sie ihm müssen einige zusätzliche Subject alternative Namenseinträge Zertifikate die sichere Verbindung von mobilen Clients zu unterstützen.
  
Sie benötigen die SAN-Namen für die automatische Ermittlung für folgende Zertifikate:
  
- Directorpool
    
- Front-End-Pool
    
- Reverseproxy
    
Weitere Informationen sind in den folgenden Tabellen aufgeführt.
  
Dies ist bei dem vorab etwas Planung ist gut, aber manchmal Sie Skype für Business Server 2019 ohne zum Bereitstellen von Mobilität bereitgestellt haben, und, die von später, wenn Sie Zertifikate bereits in Ihrer Umgebung haben. Neu sie über eine interne Zertifizierungsstelle ausgestellt wird in der Regel recht einfach, aber mit öffentliche Zertifikate von einer öffentlichen Zertifizierungsstelle, sind, die ein wenig mehr pricy.
  
Ist, die sich ansehen und viele SIP-Domänen vorhanden sind (die stellen würde hinzufügen teurer SANS), können Sie konfigurieren Ihren Reverseproxy aufrufen, um HTTP für die erste Autodiscover Service-Anforderung, anstatt über HTTPS (Dies ist die Standardeinstellung verwenden Konfiguration). Im Artikel [Planen für die Mobilität](../../SfbServer/plan-your-deployment/mobility.md) enthält weitere Informationen zu diesem.
  
Director-Pool und Front-End-Pool-Zertifikats Anforderungen:
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|Interne URL des AutoErmittlungsdiensts  <br/> |SAN = Lyncdiscoverinternal. \<Sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |SAN = Lyncdiscover. \<Sipdomain\>  <br/> |
   
Alternativ können Sie SAN =\*. \<Sipdomain\>
  
Reverseproxy-Zertifikatsanforderungen (öffentliche ZS):
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |SAN = Lyncdiscover. \<Sipdomain\>  <br/> |
   
Dieser SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener (Secure Sockets Layer) auf dem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Der Reverseproxy Listener schlägt SANs für Ihre externe Web Services URL(s) verfügen. Beispiele umfassen SAN=skypewebextpool01.contoso.com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (dies optional ist). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype für Business Server 2019 kann die gleichen Dateifreigabe für alle Dateispeicher verwenden. Beachten Sie bitte Folgendes:
  
- Eine Dateifreigabe muss sich entweder auf DAS (Direct Attached Storage) oder auf einem SAN (Storage Area Network) befinden, einschließlich des DFS (Distributed File System) sowie von RAID-Komponenten (Redundant Array of Independent Disks) für Dateispeicher. Wenn Sie mehr über DFS für Windows Server 2012 erfahren möchten, finden Sie auf [dieser DFS-Seite](https://technet.microsoft.com/en-us/library/jj127250.aspx) weitere Informationen.
    
- Es wird empfohlen, einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie eine verwenden, sollten Sie Windows Server 2012 oder Windows Server 2012 R2 Cluster bilden. Warum die neuesten Windows? Ältere Versionen möglicherweise nicht die richtigen Berechtigungen für alle Features zu aktivieren. Sie können Clusterverwaltung verwenden, um die Dateifreigaben erstellen, und dieser [Erstellen eines Clusters](https://support.microsoft.com/en-us/help/224967) KB-Artikel helfen Ihnen mit diesen Details.
    
> [!CAUTION]
> Beachten Sie, dass Network Attached Storage (NAS) als Dateifreigabe nicht unterstützt wird. Verwenden Sie daher eine der oben genannten Optionen. 
  








