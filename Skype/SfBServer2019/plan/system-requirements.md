---
title: Systemanforderungen für Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: ''
description: 'Zusammenfassung: Bereiten Sie Ihre Skype for Business Server 2019-Server und Domäneninfrastruktur mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und -empfehlungen sowie Zertifikat-DNS, Dateifreigabe und Active Directory-Informationen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.'
ms.openlocfilehash: cd2c262b6a600138e4b8f93216c24ecdf170d75c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112121"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Systemanforderungen für Skype for Business Server 2019
 
**Zusammenfassung:** Bereiten Sie die Installation von Skype for Business Server 2019 mit diesem Thema vor. Hardware, Betriebssystem, Software, Datenbanken, Zertifikate, Active Diretory, DNS und Dateifreigaben werden hier behandelt. Alle Systemanforderungen und -empfehlungen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2019 beginnen. In diesem Artikel werden Sie durch die Planung für Folgendes erläutert:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Betriebssysteme](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Back-End-SQL Datenbanken](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Zertifikate](system-requirements.md#Certs)
  
- [Dateifreigabe](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware für Skype for Business Server 2019
<a name="Hardware"> </a>

Nachdem Sie ihre Topologie heruntergefahren haben (und wenn nicht, können Sie das Thema [Topology Basics for Skype for Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) lesen), ist es an der Zeit, sich Gedanken über Server zu machen. Skype for Business Server 2019-Server erfordern 64-Bit-Hardware. Unsere Empfehlungen für Hardware sind unten aufgeführt. Dies sind keine Anforderungen, aber sie spiegeln die Anforderungen wider, die für eine optimale Leistung erforderlich sind. Wir verfügen über Dokumentation zur Kapazitätsplanung, mit der Sie je nach Ihren Umständen feststellen können, ob Sie mehr als diesen benötigen.
  
Empfohlene Hardware für Standard Edition-Server:

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 8 oder mehr Festplatten mit mindestens 10.000 U/Min. mit mindestens 72 GB freiem Festplattenspeicher (zwei datenträger, die RAID 1 und 6 mit RAID 10 verwenden).  <br/> ODER  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse verbunden sein).  <br/> Dual- oder Multi-Homed-Konfigurationen werden **für** Front-End-Server, Back-End-Server und Standard Edition-Server nicht unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar sind und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verfügen. Dieses Szenario stellt keinen server mit mehreren Homed-Servern dar und wird unterstützt.  <br/> |


Empfohlene Hardware für Front-End-Server und Back-End-Server:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 Gigahertz (GHz) oder höher. <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |64 GIGABYTE (GB).  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 8 oder mehr Festplatten mit mindestens 10.000 U/Min. mit mindestens 72 GB freiem Festplattenspeicher (zwei datenträger, die RAID 1 und 6 mit RAID 10 verwenden).  <br/> ODER  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse verbunden sein).  <br/> Dual- oder Multi-Homed-Konfigurationen werden **für** Front-End-Server, Back-End-Server und Standard Edition-Server nicht unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar sind und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verfügen. Dieses Szenario stellt keinen server mit mehreren Homed-Servern dar und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte.  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 4 oder mehr Festplatten mit 10.000 U/Min. mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten sich in einer 2x RAID 1-Konfiguration befinden).  <br/> ODER  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 10000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse verbunden sein).  <br/> Dual- oder multi-homed-Konfigurationen werden **für** Video-In-Interop-Server und Directors nicht unterstützt. <br/> Für Edgeserver sind zwei Netzwerkschnittstellen erforderlich, bei denen es sich um Netzwerkadapter mit zwei Ports handelt, 1 GBit/s oder höher (oder zwei gekoppelte Netzwerkadapter, für insgesamt vier, bei denen jedes Paar mit einer einzigen MAC-Adresse und einer einzelnen IP-Adresse für insgesamt zwei Paare verbunden ist).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NiCs) unterstützt, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen.  <br/> |


> [!NOTE]
> Unabhängig von der Serverrolle empfehlen wir auch die folgenden Hardwareeinstellungen für Skype for Business Server 2019 (dies kann je nach erworbener Hardwaremarke variieren. Weitere Informationen finden Sie in der Herstellerdokumentation):
> - BIOS config – sollte von NUMA auf FLAT festgelegt werden.
> - Aktivieren Sie Hyperthreading.
> - Die Einstellung für die RSS-Warteschlange sollte auf 8 Warteschlangen festgelegt werden.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Betriebssysteme für Skype for Business Server 2019
<a name="OS"> </a>

Nachdem Sie die Hardware installiert haben, müssen Sie das Betriebssystem installieren, mit dem Sie Skype for Business Server 2019 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Alles andere als die hier aufgeführten Betriebssysteme funktionieren nicht ordnungsgemäß. Versuchen Sie es nicht für Installationen von Skype for Business Server 2019. Beispielsweise wird die Server Core-Option nicht aufgelistet und daher nicht unterstützt.

> [!NOTE]
> Ein "In-Place"-Upgrade des Betriebssystems wird mit Lync Server 2013 nicht unterstützt. Sie müssen einen separaten Pool bereitstellen und Benutzer mit einem anderen Betriebssystem in den neuen Pool migrieren. Alle Server in einem Pool müssen die gleiche Betriebssystemversion haben.

> [!NOTE]
> 
> Wenn Sie Windows Admin Center 2019 auf Ihrem Windows Server 2019-Computer installieren, wird ein Port zum Abhören aufgefordert. Es gibt eine Likliy, auf der Sie Port 443 auswählen können, aber wenn auf diesem Computer Skype for Business Server 2019 installiert ist oder Skype for Business Server 2019 auf dem Computer installiert ist, müssen Sie eine andere Portnummer auswählen.
> 
>Warum ist dies der Fall? Wenn Windows Admin Center 2019 an Port 443 ausgeführt wird, können Sie keine Verbindung mit dem Server mithilfe der Skype for Business-Systemsteuerung herstellen, und Sie können auch keine Verbindung mit einem internen Webdienst herstellen, der auf dem Server ausgeführt wird (Adressbuchwebdienst, AutoErmittlungsdienst, WebTicket-Dienst usw.).  Tatsächlich können Sie keine Verbindung mit einer internen Webdienst-URL herstellen. Wählen Sie einen anderen Port aus, falls Sie Windows Admin Center 2019 auf einem Server mit Skype for Business Server 2019 installieren möchten.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software, die vor einer Skype for Business Server 2019-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für jeden Server mit Skype for Business Server 2019 installieren oder konfigurieren müssen. Diese sind unten aufgeführt, gefolgt von zusätzlichen Anforderungen für bestimmte Serverrollen.

> [!IMPORTANT]
> Skype For Business 2019 unterstützt .Net Framework 4.8. 
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Alle Skype for Business Server-Server müssen Windows PowerShell 3.0 installiert sein.  <br/> • Dies sollte standardmäßig mit Windows Server 2016 installiert werden.<br/> |
|Microsoft .NET Framework  <br/> |WCF-Dienste ist ein **Feature,** das unter **Server Manager** als Windows-Feature installiert ist und zunächst keine Downloads erforderlich ist. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert ist und Sie es überprüfen, dass die **Option HTTP-Aktivierung** ebenfalls aktiviert und installiert ist, wie dies der <br/> ![Screenshot der HTTP-Aktivierungsoption unter .NET Framework 4.5-Features.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, in dem sie sagen, dass einige andere Dinge installiert werden müssen, damit die HTTP-Aktivierung installiert werden kann. Das ist normal. Klicken Sie auf OK, und gehen Sie weiter. Wenn Sie dieses Popup nicht erhalten, können Sie davon ausgehen, dass diese Dinge bereits installiert sind.  <br/> Microsoft .NET Framework in der Regel installiert, wenn Windows Server 2016 installiert ist. Skype for Business Server erfordert microsoft .NET Framework 4.7 oder 4.8, daher müssen Sie es wahrscheinlich aktualisieren. Das Update finden Sie [hier.](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Für Windows Server 2016 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.  <br/> Für alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, ist die Windows Media Format Runtime erforderlich, um die Windows Media Audio (WMA)-Dateien ausführen zu können, die von den Anwendungen zum Parken von Anrufen, Ansagen und Reaktionsgruppe für Ansagen und Musik verwendet werden.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5, um Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2019 zu unterstützen.  <br/> • Für Windows Server 2016 ist kein Download erforderlich. Öffnen **Sie Den Server-Manager,** und wechseln Sie zum Assistenten zum Hinzufügen **von Rollen und Features.** **Windows Identity Foundation 3.5 ist** im Abschnitt **Features** aufgeführt. Wenn sie ausgewählt ist, sind Sie gut. Wählen Sie andernfalls die Option aus, und klicken Sie auf **Weiter,** um die **Schaltfläche Installieren zu** erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Front-End-Server und Standard Edition-Server benötigen außerdem:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition-Servern benötigt, bei denen die folgenden Module ausgewählt sind:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Statische Inhaltskomprimierung, dynamische Inhaltskomprimierung  <br/> • Sicherheit: Anforderungsfilterung, Clientzertifikatzuordnungsauthentifizierung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -Tools  <br/> Beachten Sie, dass auch anonymer Zugriff erforderlich ist, Sie erhalten dies jedoch bei der Installation von IIS, sodass Sie keinen Ort haben, um ihn in der Liste auszuwählen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016 müssen Sie das **Media Foundation-Feature** im **Server Manager installieren.** Sie können Ihre Skype for Business Server 2019-Installation auch ohne diesen Start starten, aber Sie werden aufgefordert, sie zu installieren, und dann den Server neu starten, bevor die Skype for Business Server 2019-Installation fortgesetzt wird. Es ist besser, dies im Voraus zu tun. <br/> |
|Silverlight  <br/> |Sie können hier die neueste Version von Silverlight [installieren.](https://www.microsoft.com/silverlight/)  <br/> |
   
Um Ihnen zu helfen, finden Sie hier ein PowerShell-Beispielskript, das Sie ausführen können, um dies zu automatisieren:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **Directors benötigen außerdem:**
  
IIS mit den folgenden Modulen ausgewählt:
  
- Allgemeine HTTP-Features
    
  - Standarddokument
    
  - HTTP-Fehler
    
  - Statischer Inhalt
    
- Systemzustand und Diagnose
    
  - HTTP-Protokollierung
    
  - Protokollierungstools
    
  - Ablaufverfolgung
    
- Leistung
    
  - Komprimierung statischer Inhalte
    
- Sicherheit
    
  - Anforderungsfilterung
    
  - Clientzertifikatzuordnungsauthentifizierung
    
  - Windows-Authentifizierung
    
- Anwendungsentwicklung
    
  - .NET Extensibility 3.5
    
  - .NET-Erweiterbarkeit 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI-Erweiterung
    
  - ISAPI-Filter
    
(Wenn Sie sich fragen, ist es dasselbe Modul wie die Front-End-Server und Standard Edition-Server, während die Tools für die dynamische Inhaltskomprimierung und -verwaltung nicht verfügbar sind.)
  
Dazu haben wir auch folgenden PowerShell-Code:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Back-End-Datenbanken, die mit Skype for Business Server 2019 funktionieren
<a name="DBs"> </a>

Bei der Installation von Skype for Business Server 2019 Standard Edition haben Sie SQL Server 2016 Express (64-Bit-Edition).

Skype for Business Server 2019 Enterprise Edition erfordert vollständige SQL Server, wie unten angegeben (nur 64-Bit-Edition; verwenden Sie keine 32-Bit-Editionen):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-Bit-Edition) und Sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |Microsoft SQL Server 2017 (64-Bit-Edition) und Sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |
Microsoft SQL Server 2016 (64-Bit-Edition) und sie müssen mit den neuesten Updates ausgeführt werden.|
 |

Wenn die zu verwendende SQL Server nicht angezeigt wird, können Sie sie nicht verwenden.
  
> [!NOTE]
> Sie müssen auch SQL Server Reporting Services für die Monitoring Server-Rolle installieren. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL clustering und SQL Always On

SQL Clustering mit Skype for Business Server 2019 wird unterstützt. Wenn Sie eine SQL einrichten möchten, erfolgt dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL clustering verfügen, die unterstützt wird. Teilen Sie den passiven Knoten nicht mit anderen SQL Instanz.
  
Für failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2016 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

Sechzehn Knoten:
  
- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

SQL Always On wird unterstützt, und Weitere Informationen dazu finden Sie unter [Back-End Server-Hochverfügbarkeit in Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Weitere Serverinstallationsempfehlungen:
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Clientsoftware oder eine andere Software des Winsock Layered Service Providers (LSP) (Firewalls von Drittanbietern oder Antivirennetzwerkinspektionssoftware wäre hier enthalten) auf einem Ihrer Front-End-Server oder eigenständigen Vermittlungsserver. Bei der Installation dieser Software wurde eine schlechte Mediendatenverkehrleistung gesehen.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Obwohl ein Teil der Konfigurationsdaten für Server und Dienste im zentralen Skype for Business Server 2019-Verwaltungsspeicher gespeichert ist, werden einige Dinge noch in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Skype for Business Server 2015 und Lync Server 2013 zur Aufrechterhaltung der Abwärtskompatibilität mit den vorherigen unterstützten Versionen  <br/> |
|Daten  <br/> |Benutzer-SIP-URI und andere Benutzereinstellungen  <br/> |
||Kontaktobjekte für Anwendungen (z. B. die Reaktionsgruppe und die Konferenz attendant-Anwendung)  <br/> |
||Daten, die aus Abwärtskompatibilität veröffentlicht wurden  <br/> |
||Ein Dienststeuerungspunkt (Service Control Point, SCP) für den zentralen Verwaltungsspeicher  <br/> |
||Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssystem für Domänencontroller

Die folgenden Domänencontrollerbetriebssysteme können verwendet werden:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2019 bereitstellen, und die Gesamtstrukturfunktionsebene jeder Gesamtstruktur, in der Sie Skype for Business Server 2019 bereitstellen, muss eine der folgenden Sein:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Können Sie in diesen Umgebungen schreibgeschützte Domänencontroller verwenden? Sicher, solange auch beschreibbare Domänencontroller verfügbar sind.
  
Es ist wichtig zu wissen, dass Skype for Business Server 2019 keine Domänen mit einem Namen unterstützt. Was sind sie? Wenn Sie über eine Stammdomäne mit der Bezeichnung "contoso.local" verfügen, ist dies in Ordnung. Wenn Sie über eine Stammdomäne verfügen, die nur lokal heißt, funktioniert dies nicht und wird daher nicht unterstützt. Ein wenig mehr dazu wurde [in diesem Knowledge Base-Artikel geschrieben.](https://support.microsoft.com/kb/300684/)
  
Skype for Business Server 2019 unterstützt auch das Umbenennen von Domänen nicht. Wenn Sie Ihre Domäne wirklich umbenennen müssen, müssen Sie Skype for Business Server 2019 deinstallieren, die Domäne umbenennen und Dann Skype for Business Server 2019 neu installieren.
  
Schließlich können Sie es mit einer Domäne mit einer gesperrten AD DS-Umgebung zu tun haben, und das ist in Ordnung. Weitere Informationen zum Bereitstellen von Skype for Business Server 2019 in einer gesperrten AD DS-Umgebung finden Sie in der Bereitstellungsdokumentation.
  
### <a name="ad-topologies"></a>AD-Topologien

Unterstützte Topologien in Skype for Business Server 2019 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcen gesamtstrukturtopologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Ressourcenstrukturtopologie mit Skype for Business Online und Azure Active Directory Connect
    
Wir verfügen über Diagramme und Beschreibungen, mit deren Hilfe Sie bestimmen können, welche Topologie Sie in Ihrer Umgebung haben oder was Sie vor der Installation von Skype for Business Server 2019 einrichten müssen. Um dies einfach zu halten, ist auch ein Schlüssel dabei:
  
![Der ist ein Schlüssel zu den Symbolen, die für Skype for Business-Topologiediagramme verwendet werden](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm der einzelnen Active Directory-Gesamtstruktur mit einer einzelnen Domäne](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Es wird nicht einfacher. Es ist eine einzelne Domänen gesamtstruktur, eine allgemeine Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm einer einzelnen Gesamtstruktur, einzelner Struktur und Mutipledomänen](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt wiederum eine einzelne Gesamtstruktur, verfügt aber auch über eine oder mehrere untergeordnete Domänen (in diesem beispiel sind drei enthalten). Die Domäne, in der die Benutzer erstellt werden, kann sich also von der Domäne unterscheiden, in der Skype for Business Server 2019 bereitgestellt wird. Warum sorgen Sie sich darum? Bei der Bereitstellung eines Skype for Business Server-Front-End-Pools müssen sich alle Server in diesem Pool in einer einzigen Domäne befinden. Sie können domänenübergreifende Verwaltung über Skype for Business Server-Unterstützung für universelle Windows-Administratorgruppen haben.
  
Im obigen Diagramm sehen Sie, dass Benutzer aus einer Domäne in der Lage sind, von derselben Domäne oder von unterschiedlichen Domänen aus auf Skype for Business Server-Pools zu zugreifen, auch wenn diese Benutzer sich in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm mit einer einzelnen Gesamtstruktur, mehreren Gesamtstrukturen und nicht einheitlichen Namespaces](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Möglicherweise haben Sie eine Topologie ähnlich diesem Diagramm, in der Sie über eine Gesamtstruktur verfügen, aber innerhalb dieser Gesamtstruktur mehrere Domänen mit separaten AD-Namespaces sind. In diesem Fall ist dieses Diagramm eine gute Illustration, da es Benutzer in drei verschiedenen Domänen enthält, die auf Skype for Business Server 2019 zugreifen. Einfarbige Linien deuten darauf hin, dass sie in ihrer eigenen Domäne auf einen Skype for Business Server-Pool zugreifen, während eine gestrichelte Linie angibt, dass sie zu einem Pool in einer anderen Struktur gehen.
  
Wie Sie sehen können, können Benutzer in derselben Domäne, derselben Struktur oder sogar einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Mehrere Gesamtstrukturen in einem Diagramm mit einer zentralen Gesamtstrukturtopologie](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 unterstützt mehrere Gesamtstrukturen, die in einer zentralen Gesamtstrukturtopologie konfiguriert sind. Wenn Sie nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte in dieser, um Benutzer in den anderen Gesamtstrukturen zu repräsentieren, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert das? Ein Verzeichnissynchronisierungsprodukt (z. B. Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während ihrer gesamten Existenz. Wenn ein Konto erstellt oder aus einer Gesamtstruktur gelöscht wird, wird diese Änderung mit dem entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre AD-Infrastruktur vorhanden ist, ist der Wechsel zu dieser Topologie möglicherweise nicht einfach, aber wenn Sie bereits vorhanden sind oder ihre Gesamtstrukturinfrastruktur noch planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2019-Bereitstellung in einer einzigen Gesamtstruktur zentralisieren, während Benutzer die Anwesenheit anderer Benutzer in einer beliebigen Gesamtstruktur durchsuchen, kommunizieren und anzeigen können. Alle Benutzerkontaktupdates werden automatisch mit Synchronisierungssoftware behandelt.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcen-Gesamtstrukturtopologie
<a name="BKMK_multipleforestopology"> </a>

![Mehrere Gesamtstrukturen in einem Topologiediagramm der Ressourcen gesamtstruktur](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine Topologie der Ressourcen gesamtstruktur wird ebenfalls unterstützt. Hier ist eine Gesamtstruktur für die Ausführung Ihrer Serveranwendungen wie Microsoft Exchange Server und Skype for Business Server 2019 dedizierte. Diese Ressourcen gesamtstrukturen hosten auch eine synchronisierte Darstellung aktiver Benutzerobjekte, aber keine anmeldefähigen Benutzerkonten. Die Ressourcen gesamtstruktur ist also eine Umgebung für gemeinsame Dienste für andere Gesamtstrukturen, in denen sich Benutzerobjekte befinden, und sie haben eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcen gesamtstruktur.
  
Beachten Sie, Exchange Server in derselben Ressourcen gesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden können.
  
Zum Bereitstellen von Skype for Business Server 2019 in dieser Topologie würden Sie ein deaktiviertes Benutzerobjekt in der Ressourcen gesamtstruktur für jedes Benutzerkonto in den Benutzer gesamtstrukturen erstellen (wenn sich Microsoft Exchange Server bereits in der Umgebung befindet, kann dies für Sie geschehen). Anschließend benötigen Sie ein Verzeichnissynchronisierungstool (z. B. Forefront Identity Manager oder FIM), um Benutzerkonten über ihren Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcen gesamtstrukturtopologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die in Mehreren Gesamtstrukturen [in einer Skype for Business-Ressourcen gesamtstrukturtopologie beschrieben wird.](system-requirements.md#BKMK_multipleforestopology)
  
In dieser Topologie gibt es eine oder mehrere Benutzer gesamtstrukturen, und Skype for Business Server wird in einer dedizierten Ressourcen gesamtstruktur bereitgestellt. Exchange Server können lokal in derselben Ressourcen gesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für die Hybridbereitstellung mit Exchange Online konfiguriert werden, oder E-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie ist kein Diagramm verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Ressourcenstrukturtopologie mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzer- und eine Ressourcen gesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung. Sie werden mit Microsoft 365 mithilfe von Azure AD Connect synchronisiert. Alle Benutzer sind über Microsoft 365 für Skype for Business aktiviert.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Bei diesem Szenario gibt es mehrere Gesamtstrukturen lokal mit einer Topologie der Ressourcen gesamtstruktur. Es besteht eine vollständige Vertrauensstellung zwischen den Active Directory-Gesamtstrukturen. Das Azure Active Directory Connect-Tool wird zum Synchronisieren von Konten zwischen den lokalen Benutzer gesamtstrukturen und Microsoft 365 oder Office 365 verwendet.
  
 Die Organisation verfügt auch über Microsoft 365 oder Office 365 und verwendet [Azure Active Directory Connect,](/azure/active-directory/connect/active-directory-aadconnect) um ihre lokalen Konten mit Microsoft 365 oder Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, werden über Microsoft 365 oder Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die einmalige Anmeldeauthentifizierung wird von einer Active Directory-Verbunddienstefarm in der Benutzerstruktur bereitgestellt.
  
In diesem Szenario wird es unterstützt, Exchange lokal, Exchange Online, eine Hybrid-Exchange-Lösung oder exchange überhaupt nicht bereitgestellt zu haben. (Das Diagramm zeigt nur lokale Exchange-Lösungen, aber auch die anderen Exchange-Lösungen werden vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Ressourcen gesamtstrukturtopologie mit Hybrid skype for Business
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzerforen, und Skype for Business wird in einer dedizierten Ressourcen gesamtstruktur bereitgestellt und für den Hybridmodus mit Skype for Business Online konfiguriert. Exchange Server kann lokal in derselben Ressourcen gesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt werden und kann für die Hybridbereitstellung mit Exchange Online konfiguriert werden. Alternativ können E-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter [Configure a multi-forest environment for hybrid Skype for Business](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 erfordert DNS aus den folgenden Gründen:
  
- MIT DNS kann Skype for Business Server 2019 interne Server oder Pools ermitteln, wodurch die Server-zu-Server-Kommunikation möglich ist.
    
- MIT DNS können Clientcomputer den Front-End-Pool oder Standard Edition-Server ermitteln, der für SIP-Transaktionen verwendet wird.
    
- Es ordnet einfache URLs für Konferenzen den Servern zu, die diese Konferenzen hosten.
    
- DNS ermöglicht externen Benutzern und Clientcomputern, eine Verbindung mit Ihren Edgeservern oder dem HTTP-Reverseproxy für Chatnachrichten oder Konferenzen herzustellen.
    
- Damit können Unified Communications (UC)-Geräte, die nicht angemeldet sind, den Front-End-Pool oder standard Edition-Server ermitteln, auf dem der Device Update-Webdienst ausgeführt wird, um Updates zu erhalten und Protokolle zu senden.
    
- Die Verwendung von DNS ermöglicht mobilen Clients das automatische Ermitteln von Webdienstressourcen, ohne dass Benutzer urLs manuell in ihren Geräteeinstellungen eingeben müssen.
    
- Sie wird im DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2019 keine internationalisierten Domänennamen (Internationalized Domain Names, IDNs) unterstützt.
  
Und es ist äußerst wichtig zu beachten, dass jeder Name in DNS mit dem Computernamen identisch ist, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2019 verwendet wird. Insbesondere können wir in der Umgebung keine Kurznamen haben und müssen über FQDNs für den Topologie-Generator verfügen.
  
Dies scheint für jeden Computer, der bereits einer Domäne beigetreten ist, logisch zu sein. Wenn Sie jedoch über einen Edgeserver verfügen, der ihrer Domäne nicht beigetreten ist, ist möglicherweise ein kurzer Name ohne Domänensuffix standardmäßig vorhanden. Stellen Sie sicher, dass dies weder in DNS noch auf dem Edgeserver oder einem Skype for Business Server 2019-Server oder -Pool der Fall ist.
  
Verwenden Sie keine Unicode-Zeichen oder Unterstriche. Standardzeichen (A-Z, a-z, 0-9 und Bindestriche) werden von externen DNS- und öffentlichen Zertifizierungsbehörden unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen, das ist wichtig zu beachten), damit Sie sich viel Mühe ersparen, wenn Sie dies von Anfang an berücksichtigen.
  
Weitere Informationen zu den DNS-Anforderungen für Netzwerke finden Sie im Abschnitt [Netzwerk](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) in unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Eine der wichtigsten Dinge, die Sie vor der Bereitstellung tun können, ist sicherzustellen, dass Ihre Zertifikate in der Reihenfolge sind. Skype for Business Server 2019 benötigt eine Public Key Infrastructure (PKI) für TLS-Verbindungen (Transport Layer Security) und MTLS (Mutual Transport Layer Security). Grundsätzlich verwendet Skype for Business Server Zertifikate, die von Zertifizierungsbehörden (Certificate Authorities, CAs) ausgestellt wurden, um auf standardisierte Weise sicher zu kommunizieren.
  
Dies sind einige der Dinge, für die Skype for Business Server 2019 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Clients und Servern
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf Audio-/Videositzungen, Anwendungsfreigabe und Konferenzen
    
- Sprechen mit Webanwendungen und Outlook Web Access (OWA)
    
Daher ist die Zertifikatplanung ein Muss. Sehen wir uns nun eine Liste einiger Dinge an, die Sie beim Anfordern von Zertifikaten berücksichtigen müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mit einem vom Betriebssystem unterstützten Signaturalgorithmus signiert werden. Skype for Business Server 2019 unterstützt die SHA-1- und SHA-2-Suite mit Digestgrößen (224, 256, 384 und 512-Bit) und erfüllt oder übertrifft die Betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server mit Skype for Business Server 2019 unterstützt.
    
- Die automatische Registrierung wird für Skype for Business Server 2019-Edgeserver nicht unterstützt.
    
> [!NOTE]
> Die Verwendung des RSASSA-PSS-Signaturalgorithmus wird nicht unterstützt und kann u. A. zu Fehlern bei anmelde- und anrufverteilten Problemen führen. 
  
- Verschlüsselungsschlüssellängen von 1024, 2048 und 4096 werden unterstützt. Schlüssellängen von 2048 und höher werden empfohlen.
    
- Der Standardalgorithmus für den Digest oder die Hashsignierung ist RSA. Die ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist sehr viel zu überlegen, und es gibt eine Vielzahl von Komfortstufen beim Anfordern von Zertifikaten von einer Zertifizierungsstelle. Wir geben Ihnen nachfolgend einige weitere Anleitungen, um Ihre Planung so schmerzfrei wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten internen Server, und sie werden höchstwahrscheinlich von einer internen Zertifizierungsstelle (d. h. einer Zertifizierungsstelle, die sich in Ihrer Domäne befindet) erhalten. Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle (eine im Internet) anfordern. Wenn Sie sich fragen, zu welcher öffentlichen Zertifizierungsstelle Sie wechseln sollten, können Sie die Liste der [Unified Communications-Zertifikatpartner](../../SfbPartnerCertification/certification/services-ssl.md) lesen.
  
Sie benötigen auch Zertifikate, wenn Skype for Business Server 2019 mit anderen Anwendungen und Servern kommuniziert, z. B. Microsoft Exchange Server. Dies muss natürlich ein Zertifikat sein, das von diesen anderen Apps und Servern unterstützt werden kann. Skype for Business Server 2019 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung. Wenn Sie daran interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2019.
  
Skype for Business Server 2019 bietet auch Unterstützung für (ohne Dass) Zertifikate, die mit der kryptografischen Sha-256-Hashfunktion signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mit SHA-256 ausgestellt werden.
  
Um die Dinge unkompliziert zu halten, haben wir die Zertifikatanforderungen für Standard Edition-Server, Front-End-Pools und andere Rollen in die folgenden Tabellen 2013 eingedg. Die fiktive contoso.com wird für Beispiele verwendet (Sie verwenden wahrscheinlich etwas anderes für Ihre Umgebung). Dies sind alle Standardwebserverzertifikate mit privaten Schlüsseln, die nicht exportiert werden können. Einige zusätzliche Dinge, die Sie beachten müssen:
  
- Server enhanced key usage (EKU) wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Jeder Anzeigename des Zertifikats muss im Computerspeicher eindeutig sein.
    
- Wenn Sie in Ihrem DNS sipinternal.contoso.com oder sipexternal.contoso.com konfiguriert haben, müssen sie entsprechend den folgenden Beispielnamen dem alternativen Subject Name (SAN) des Zertifikats hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Betreffname/gemeinsamer Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Auf Standard Edition-Servern ist der Server-FQDN mit dem Pool-FQDN identisch.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (der mit dem FQDN des Servers identisch ist)  <br/> UND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINwahl-URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Sie können den internen Web-FQDN im Topologie-Generator nicht außer Kraft setzen.  <br/> Wenn Sie über mehrere einfache MEET-URLs verfügen, müssen Sie alle als SANs verwenden.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache EINwahl-URL  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Front-End-Pool:
  
|**Zertifikat**|**Betreffname/gemeinsamer Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (nicht identisch mit dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business-Pools  <br/> UND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINwahl-URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache EINwahl-URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Betreffname/gemeinsamer Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Director, FQDN des Directorpools.  <br/> Wenn dieser Pool der automatische Anmeldeserver für Clients ist und in der Gruppenrichtlinie ein strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für sip.sipdomain (für jede sip-Domäne, die Sie haben).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (der mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business-Pools  <br/> UND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINwahl-URL  <br/> • Einfache Admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> • Einfache EINwahl-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der externe Web-FQDN des Director muss sich vom Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Zertifikate für eigenständigen Vermittlungsserver:
  
|**Zertifikat**|**Betreffname/gemeinsamer Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance (insbesondere Survivable Branch Appliance 2015 for Skype for Business Server 2019):
  
|**Zertifikat**|**Betreffname/gemeinsamer Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Appliance  <br/> |SIP.\<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den externen Benutzerzugriff (Edge)

Skype for Business Server 2019  unterstützt die Verwendung eines einzelnen öffentlichen Zertifikats für externe Zugriffs- und Webkonferenz-Edgeschnittstellen sowie den A/V-Authentifizierungsdienst, der alle über die Edgeserver bereitgestellt wird. Ihre interne Edgeschnittstelle verwendet in der Regel ein privates Zertifikat, das von Ihrer internen Zertifizierungsstelle ausgestellt wurde, aber wenn Es ihnen lieber wäre, können Sie auch hier ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle kommt.
  
Ihr Reverseproxy (RP) verwendet auch ein öffentliches Zertifikat und verschlüsselt die Kommunikation von Ihrer RP zu Clients und die RP zu internen Servern mithilfe von HTTP (genauer gesagt TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie einige zusätzliche Alternative Namenseinträge für Betreffs in Ihre Zertifikate eingeben, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Sie benötigen san-Namen für die automatische Ermittlung für die folgenden Zertifikate:
  
- Directorpool
    
- Front-End-Pool
    
- Reverse-Proxy
    
Die Spezifischen sind in den folgenden Tabellen aufgeführt.
  
Hier ist eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2019 bereitgestellt, ohne Mobilität bereitstellen zu wollen, und das kommt später vor, wenn Sie bereits Zertifikate in Ihrer Umgebung haben. Die Neuauflage über eine interne Zertifizierungsstelle ist in der Regel recht einfach, aber bei öffentlichen Zertifikaten einer öffentlichen Zertifizierungsstelle kann dies etwas prigiger sein.
  
Wenn Sie dies sehen und über viele SIP-Domänen verfügen (was das Hinzufügen von SANS verteuern würde), können Sie Ihren Reverseproxy so konfigurieren, dass http für die anfängliche AutoErmittlungsdienstanforderung verwendet wird, anstatt HTTPS (die Standardkonfiguration) zu verwenden. Der [Artikel Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) enthält weitere Informationen dazu.
  
Anforderungen an Directorpool- und Front-End-Poolzertifikate:
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des internen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Alternativ können Sie SAN= \* verwenden.\<sipdomain\>
  
Anforderungen an das Reverseproxyzertifikat (Public Ca):
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Dieses SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener auf Ihrem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Ihr Reverseproxylistener hat SANs für Ihre externen Webdienst-URL(n). Einige Beispiele wären SAN=skypewebextpool01.contoso.com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2019 kann dieselbe Dateifreigabe für den ganzen Dateispeicher verwenden. Beachten Sie Folgendes:
  
- Eine Dateifreigabe muss sich entweder im direkt angefügten Speicher (DIRECT Attached Storage, DAS) oder in einem Speicherbereichsnetzwerk (Storage Area Network, SAN) befinden, und dies umfasst das verteilte Dateisystem (Distributed File System, DFS) sowie ein redundantes Array unabhängiger Datenträger (INDEPENDENT Disks, RAID) für Dateispeicher. Weitere Informationen zu DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- Wir empfehlen einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie bereits eine verwenden, sollten Sie Windows Server 2012 oder höher clustern

> [!Note]
> **Warum das neueste Windows?** Ältere Versionen verfügen möglicherweise nicht über die richtigen Berechtigungen, um alle Features zu aktivieren. Sie können den Clusteradministrator verwenden, um die Dateifreigaben zu erstellen. Weitere Informationen finden Sie in diesem Supportartikel Zum Erstellen [von Dateifreigaben in](https://support.microsoft.com/help/224967) einem Cluster.
    
> [!CAUTION]
> Sie sollten wissen, dass die Verwendung von NAS (Network Attached Storage) als Dateifreigabe nicht unterstützt wird. Verwenden Sie daher eine der oben aufgeführten Optionen. Diese Unterstützungsbeschränkung wird durch den variablen Entwurf von NAS-Geräten verursacht, die die Anpassungsfähigkeit des Dateisystems an den Windows Server-basierten Computer bereitstellen müssen, der auf das freigegebene Dateisystem der Geräte zutritt.
