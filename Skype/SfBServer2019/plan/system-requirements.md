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
ms.localizationpriority: medium
ms.collection: ''
description: 'Zusammenfassung: Bereiten Sie Ihre Skype for Business Server 2019-Server und Domäneninfrastruktur mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sowie Zertifikat-DNS-, Dateifreigabe- und Active Directory-Informationen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.'
ms.openlocfilehash: d5714c5606c69d6aba0befa03a6556a5da8ab443
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728364"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>Systemanforderungen für Skype for Business Server 2019
 
**Zusammenfassung:** Bereiten Sie die Installation Skype for Business Server 2019 mit diesem Thema vor. Hier werden Hardware, Betriebssystem, Software, Datenbanken, Zertifikate, Active Diretory, DNS und Dateifreigaben behandelt. Alle Systemanforderungen und Empfehlungen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2019 beginnen. Dieser Artikel führt Sie durch die Planung für Folgendes:
  
- [Hardware](system-requirements.md#Hardware)
  
- [Betriebssysteme](system-requirements.md#OS)
  
- [Software](system-requirements.md#Software)

- [Back-End-SQL-Datenbanken](system-requirements.md#DBs)
  
- [Active Directory](system-requirements.md#AD)
  
- [Domain Name System (DNS)](system-requirements.md#DNS)
  
- [Zertifikate](system-requirements.md#Certs)
  
- [Dateifreigabe](system-requirements.md#Fileshare)

  
## <a name="hardware-for-skype-for-business-server-2019"></a>Hardware für Skype for Business Server 2019
<a name="Hardware"> </a>

Wenn Die Topologie nicht mehr verfügbar ist (und wenn Sie dies nicht tun, können Sie sich die [Topologiegrundlagen für Skype for Business Server 2019-Thema](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ansehen), ist es an der Zeit, über Server nachzudenken. Skype for Business Server 2019-Server benötigen 64-Bit-Hardware. Unsere Empfehlungen für Hardware finden Sie unten. Dies sind keine Anforderungen, aber sie spiegeln die Anforderungen wider, die für eine optimale Leistung erforderlich sind. Wir verfügen über eine Dokumentation zur Kapazitätsplanung, mit der Sie je nach Ihren Umständen ermitteln können, ob Sie mehr benötigen.
  
Empfohlene Hardware für Standard Edition Server:

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 8 oder mehr Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (zwei der Festplatten mit RAID 1 und 6 mit RAID 10).  <br/> OR  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 1.0000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse zusammengeführt werden).  <br/> Dual- oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition Server **nicht** unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar gemacht werden und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder GIF verfügen. Dieses Szenario stellt keinen Server mit mehreren Verwalteten dar und wird unterstützt.  <br/> |


Empfohlene Hardware für Front-End-Server und Back-End-Server:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher. <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |64 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 8 oder mehr Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (zwei der Festplatten mit RAID 1 und 6 mit RAID 10).  <br/> OR  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 1.0000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse zusammengeführt werden).  <br/> Dual- oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition Server **nicht** unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar gemacht werden und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder GIF verfügen. Dieses Szenario stellt keinen Server mit mehreren Verwalteten dar und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 v3 Dualprozessor, 6-Core, 2,4 GHz oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte.  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten in einer 2x RAID 1-Konfiguration vorhanden sein).  <br/> OR  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 1.000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse zusammengeführt werden).  <br/> Duale konfigurationen oder Multi-Homed-Konfigurationen werden für Video-Interoperabilitätsserver und Directors **nicht** unterstützt. <br/> Edgeserver benötigen zwei Netzwerkschnittstellen, bei denen es sich um Dualport-Netzwerkadapter handelt, mindestens 1 GBit/s (oder zwei gekoppelte Netzwerkadapter, insgesamt vier, wobei jedes Paar mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse für insgesamt zwei Paare kombiniert wird).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (Network Interface Cards, NICs) unterstützt, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen.  <br/> |


> [!NOTE]
> Unabhängig von der Serverrolle empfehlen wir auch die folgenden Hardwareeinstellungen für Skype for Business Server 2019 (dies kann je nach erworbener Hardwaremarke variieren. Einzelheiten hierzu finden Sie in der Herstellerdokumentation:
> - BIOS-Konfiguration – sollte von NUMA auf FLAT festgelegt werden.
> - Aktivieren Sie Hyperthreading.
> - Die RSS-Warteschlangeneinstellung sollte auf 8 Warteschlangen festgelegt werden.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Betriebssysteme für Skype for Business Server 2019
<a name="OS"> </a>

Nachdem Sie die Hardware installiert haben, müssen Sie das Betriebssystem installieren, mit dem Sie Skype for Business Server 2019 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Andere als die hier aufgeführten Betriebssysteme funktionieren nicht ordnungsgemäß. versuchen Sie es nicht für Installationen von Skype for Business Server 2019. Beispielsweise wird die Server Core-Option nicht aufgeführt und daher nicht unterstützt.

> [!NOTE]
> Direkte Upgrades des Betriebssystems werden mit Lync Server 2013 nicht unterstützt. Sie müssen einen separaten Pool bereitstellen und Benutzer in den neuen Pool mit einem anderen Betriebssystem migrieren. Alle Server in einem Pool müssen über dieselbe Betriebssystemversion verfügen.

> [!NOTE]
> 
> Wenn Sie Windows Admin Center 2019 auf Ihrem Windows Server 2019-Computer installieren, werden Sie aufgefordert, einen Port anzuhören. Möglicherweise wählen Sie Port 443 aus, aber wenn auf diesem Computer Skype for Business Server 2019 installiert ist oder Skype for Business Server 2019 installiert ist, müssen Sie eine andere Portnummer auswählen.
> 
>Warum ist dies der Fall? Wenn Windows Admin Center 2019 an Port 443 ausgeführt wird, können Sie keine Verbindung mit dem Server über die Skype for Business Systemsteuerung herstellen, und Sie können auch keine Verbindung mit einem internen Webdienst herstellen, der auf dem Server ausgeführt wird (Adressbuchwebdienst, AutoErmittlungsdienst, WebTicket-Dienst usw.).  Tatsächlich können Sie keine Verbindung mit einer internen Webdienst-URL herstellen. Wählen Sie einen anderen Port aus, falls Sie Windows Admin Center 2019 auf einem Server mit Skype for Business Server 2019 platzieren möchten.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software, die vor einer Skype for Business Server 2019-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für jeden Server installieren oder konfigurieren müssen, auf dem Skype for Business Server 2019 ausgeführt wird. Diese werden unten aufgeführt, gefolgt von zusätzlichen Anforderungen für bestimmte Serverrollen.

> [!IMPORTANT]
> Skype For Business 2019 unterstützt .Net Framework 4.8. 
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Alle Skype for Business Server Server müssen Windows PowerShell 3.0 installiert sein.  <br/> • Diese sollte standardmäßig mit Windows Server 2016 installiert werden.<br/> |
|Microsoft .NET Framework  <br/> |WCF-Dienste sind ein **Feature,** das als Windows-Feature unter **Server-Manager** installiert ist und zunächst keine Downloads benötigt. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert ist und Sie es aktivieren, dass die **HTTP-Aktivierungsoption** ebenfalls aktiviert und installiert ist, z. B.: <br/> ![Screenshot der HTTP-Aktivierungsoption unter den Features .NET Framework 4.5.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, das besagt, dass einige andere Dinge installiert werden müssen, damit die HTTP-Aktivierung installiert werden kann. Das ist normal; Klicken Sie auf "OK", und fahren Sie fort. Wenn Sie dieses Popup nicht erhalten, können Sie davon ausgehen, dass diese Elemente bereits installiert sind, und fortfahren.  <br/> Microsoft .NET Framework wird in der Regel installiert, wenn Windows Server 2016 installiert ist. Skype for Business Server erfordert jedoch Microsoft .NET Framework 4.7 oder 4.8, daher müssten Sie es wahrscheinlich aktualisieren. Das Update finden Sie [hier](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/)<br/> |
|Media Foundation  <br/> |Für Windows Server 2016 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.  <br/> Alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, erfordern Windows Media Format Runtime, um die WMA-Dateien (Windows Media Audio) auszuführen, die von den Anwendungen für das Parken von Anrufen, ankündigungen und Reaktionsgruppen für Ankündigungen und Musik wiedergegeben werden.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5, um Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2019 zu unterstützen.  <br/> • Für Windows Server 2016 müssen Sie nichts herunterladen. Öffnen Sie **den Server-Manager,** und wechseln Sie zum Assistenten zum Hinzufügen von **Rollen und Features.** **Windows Identity Foundation 3.5** ist im Abschnitt **"Features"** aufgeführt. Wenn sie ausgewählt ist, sind Sie gut. Wählen Sie sie andernfalls aus, und klicken Sie auf **"Weiter",** um die Schaltfläche **"Installieren"** zu erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Front-End-Server und Standard Edition-Server benötigen außerdem Folgendes:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition Servern benötigt, wobei die folgenden Module ausgewählt sind:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Clientzertifikatzuordnungsauthentifizierung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -Tools  <br/> Beachten Sie, dass anonymer Zugriff ebenfalls erforderlich ist, aber Sie erhalten dies, wenn Sie IIS installieren, sodass Sie keinen Ort haben, um ihn in der Liste auszuwählen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016 müssen Sie das **Media Foundation-Feature** im **Server-Manager** installieren. Sie können ihre Skype for Business Server 2019-Installation tatsächlich ohne diese starten. Sie werden jedoch aufgefordert, sie zu installieren und dann den Server neu zu starten, bevor die Skype for Business Server 2019-Installation fortgesetzt wird. Es ist besser, dies im Voraus zu tun. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight [hier](https://www.microsoft.com/silverlight/)installieren.  <br/> |
   
Um Ihnen zu helfen, finden Sie hier ein Beispiel für ein PowerShell-Skript, das Sie ausführen können, um dies zu automatisieren:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **Directors benötigen außerdem:**
  
IIS, wobei die folgenden Module ausgewählt sind:
  
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
    
  - .NET-Erweiterbarkeit 3.5
    
  - .NET-Erweiterbarkeit 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ISAPI-Erweiterung
    
  - ISAPI-Filter
    
(Wenn Sie sich fragen, ist es dasselbe Modul wie die Front-End-Server und Standard Edition-Server, wobei die Tools für die Komprimierung dynamischer Inhalte und die Verwaltungstools weggelassen werden.)
  
Dafür haben wir auch folgenden PowerShell-Code:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Back-End-Datenbanken, die mit Skype for Business Server 2019 funktionieren
<a name="DBs"> </a>

Bei der Installation von Skype for Business Server 2019-Standard Edition verfügen Sie über SQL Server 2016 Express (64-Bit-Edition).

Skype for Business Server 2019-Enterprise Edition erfordert vollständige SQL Server, wie unten angegeben (nur 64-Bit-Edition; verwenden Sie keine 32-Bit-Editionen):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausführen.  <br/> |Microsoft SQL Server 2017 (64-Bit-Edition) und sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |
Microsoft SQL Server 2016 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausführen.|
 |

Wenn die hier aufgeführte SQL Server Edition, die Sie verwenden möchten, nicht angezeigt wird, können Sie sie nicht verwenden.
  
> [!NOTE]
> Außerdem müssen Sie SQL Server Reporting Services für die Monitoring Server-Rolle installieren. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL Clustering und SQL AlwaysOn

SQL Clustering mit Skype for Business Server 2019 wird unterstützt. Wenn Sie SQL Clustering einrichten möchten, geschieht dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL Clustering verfügen, die unterstützt wird. Teilen Sie den passiven Knoten nicht mit anderen SQL Instanzen.
  
Für Failoverclustering stehen Folgendes zur Auswahl:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2016 Standard (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.

16 Knoten:
  
- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.
- Microsoft SQL Server 2016-Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.

SQL AlwaysOn wird unterstützt. Weitere Informationen finden Sie in [der Back-End-Server-Hochverfügbarkeit in Skype for Business Server 2019.](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)
  

###  <a name="additional-server-installation-recommendations"></a>Zusätzliche Empfehlungen für die Serverinstallation:
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA)-Server-Clientsoftware oder andere Winsock Layered Service Providers (LSP)-Software (Firewalls von Drittanbietern oder Antiviren-Netzwerküberprüfungssoftware wären hier enthalten) auf einem Ihrer Front-End-Server oder eigenständigen Vermittlungsservern. Bei der Installation dieser Software wurde eine schlechte Leistung des Mediendatenverkehrs festgestellt.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Obwohl ein Großteil der Konfigurationsdaten für Server und Dienste im zentralen Verwaltungsspeicher Skype for Business Server 2019 gespeichert ist, sind einige Dinge weiterhin in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Skype for Business Server 2015 und Lync Server 2013 zur Aufrechterhaltung der Abwärtskompatibilität mit den vorherigen unterstützten Versionen  <br/> |
|Daten  <br/> |Sip-URI des Benutzers und andere Benutzereinstellungen  <br/> |
||Kontaktobjekte für Anwendungen (z. B. die Reaktionsgruppenanwendung und die Konferenzzentralenanwendung)  <br/> |
||Aus Gründen der Abwärtskompatibilität veröffentlichte Daten  <br/> |
||Ein Dienststeuerungspunkt (SCP) für den zentralen Verwaltungsspeicher  <br/> |
||Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssystem für Domänencontroller

Die folgenden Domänencontroller-Betriebssysteme können verwendet werden:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2019 bereitstellen, und die Gesamtstrukturfunktionsebene jeder Gesamtstruktur, in der Sie Skype for Business Server 2019 bereitstellen, muss eine der folgenden Sein:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Können Sie in diesen Umgebungen schreibgeschützte Domänencontroller verwenden? Sicher, solange auch beschreibbare Domänencontroller verfügbar sind.
  
Es ist wichtig zu wissen, dass Skype for Business Server 2019 keine Domänen mit einzelnen Bezeichnungen unterstützt. Welche sind das? Wenn Sie eine Stammdomäne mit der Bezeichnung "contoso.local" haben, ist dies in Ordnung. Wenn Sie über eine Stammdomäne verfügen, die nur als lokal bezeichnet wird, funktioniert dies nicht und wird daher nicht unterstützt. Etwas mehr dazu wurde [in diesem Knowledge Base-Artikel](https://support.microsoft.com/kb/300684/)geschrieben.
  
Skype for Business Server 2019 unterstützt auch das Umbenennen von Domänen nicht. Wenn Sie Ihre Domäne wirklich umbenennen müssen, müssen Sie Skype for Business Server 2019 deinstallieren, die Domäne umbenennen und dann Skype for Business Server 2019 neu installieren.
  
Schließlich können Sie es mit einer Domäne mit einer gesperrten AD DS-Umgebung zu tun haben, und das ist in Ordnung. Weitere Informationen zum Bereitstellen von Skype for Business Server 2019 in einer gesperrten AD DS-Umgebung finden Sie in der Bereitstellungsdokumentation.
  
### <a name="ad-topologies"></a>AD-Topologien

Unterstützte Topologien in Skype for Business Server 2019 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business Ressourcengesamtstrukturtopologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Ressourcengesamtstrukturtopologie mit Skype for Business Online und Azure Active Directory Verbinden
    
Wir haben Diagramme und Beschreibungen, die Ihnen helfen, zu bestimmen, welche Topologie Sie in Ihrer Umgebung haben oder was Sie vor der Installation von Skype for Business Server 2019 einrichten müssen. Um dies einfach zu halten, schließen wir auch einen Schlüssel ein:
  
![Dies ist ein Schlüssel für die Symbole, die für Skype for Business Topologiediagramme verwendet werden.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm der Active Directory-Gesamtstruktur mit einer einzelnen Domäne.](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Es wird nicht einfacher als dies; Es handelt sich um eine einzelne Domänengesamtstruktur, eine allgemeine Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Eine einzelne Gesamtstruktur, eine einzelne Struktur und ein Stummschaltungsdomänendiagramm.](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt erneut eine einzelne Gesamtstruktur, hat aber auch eine oder mehrere untergeordnete Domänen (in diesem spezifischen Beispiel gibt es drei). Die Domäne, in der die Benutzer erstellt werden, unterscheidet sich möglicherweise von der Domäne Skype for Business Server 2019 bereitgestellt wird. Warum machen Sie sich Gedanken darüber? Beachten Sie, dass sich bei der Bereitstellung eines Skype for Business Server Front-End-Pools alle Server in diesem Pool in einer einzigen Domäne befinden müssen. Sie können domänenübergreifende Verwaltung über Skype for Business Server Unterstützung von Windows universellen Administratorgruppen haben.
  
Im obigen Diagramm sehen Sie, dass Benutzer aus einer Domäne auf Skype for Business Server Pools aus derselben Domäne oder aus verschiedenen Domänen zugreifen können, auch wenn sich diese Benutzer in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Eine einzelne Gesamtstruktur, mehrere Strukturen und ein nicht zusammenhängendes Namespacediagramm.](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Möglicherweise haben Sie eine Topologie ähnlich wie in diesem Diagramm, in der Sie über eine Gesamtstruktur verfügen, innerhalb dieser Gesamtstruktur befinden sich jedoch mehrere Domänen mit separaten AD-Namespaces. In diesem Fall ist dieses Diagramm eine gute Abbildung, da es Benutzer in drei verschiedenen Domänen enthält, die auf Skype for Business Server 2019 zugreifen. Durchgezogene Linien deuten darauf hin, dass sie auf einen Skype for Business Server Pool in ihrer eigenen Domäne zugreifen, während eine gestrichelte Linie angibt, dass sie zu einem Pool in einer anderen Struktur wechseln.
  
Wie Sie sehen können, können Benutzer in derselben Domäne, derselben Struktur oder sogar einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Mehrere Gesamtstrukturen in einem Topologiediagramm der zentralen Gesamtstruktur.](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 unterstützt mehrere Gesamtstrukturen, die in einer zentralen Gesamtstrukturtopologie konfiguriert sind. Wenn Sie nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte darin, um Benutzer in den anderen Gesamtstrukturen darzustellen, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert dies? Ein Verzeichnissynchronisierungsprodukt (z. B. Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während ihres bestehens. Wenn ein Konto erstellt oder aus einer Gesamtstruktur gelöscht wird, wird diese Änderung mit dem entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre AD-Infrastruktur eingerichtet ist, ist der Umstieg auf diese Topologie möglicherweise nicht einfach, aber wenn Sie bereits dort sind oder Ihre Gesamtstrukturinfrastruktur planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2019-Bereitstellung in einer einzigen Gesamtstruktur zentralisieren, während Benutzer das Vorhandensein anderer Benutzer in einer beliebigen Gesamtstruktur suchen, kommunizieren und anzeigen können. Alle Benutzerkontaktupdates werden automatisch mit Synchronisierungssoftware behandelt.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business Ressourcengesamtstrukturtopologie
<a name="BKMK_multipleforestopology"> </a>

![Mehrere Gesamtstrukturen in einem Topologiediagramm der Ressourcengesamtstruktur.](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine Topologie der Ressourcengesamtstruktur wird ebenfalls unterstützt. Hier ist eine Gesamtstruktur für die Ausführung Ihrer Serveranwendungen vorgesehen, z. B. Microsoft Exchange Server und Skype for Business Server 2019. Diese Ressourcengesamtstrukturen hosten auch eine synchronisierte Darstellung aktiver Benutzerobjekte, jedoch keine angemeldeten Benutzerkonten. Die Ressourcengesamtstruktur ist also eine freigegebene Dienstumgebung für andere Gesamtstrukturen, in denen sich Benutzerobjekte befinden, und sie haben eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.
  
Beachten Sie, dass Exchange Server in derselben Ressourcengesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden können.
  
Um Skype for Business Server 2019 in dieser Topologie bereitzustellen, erstellen Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen (wenn sich Microsoft Exchange Server bereits in der Umgebung befindet, ist dies möglicherweise für Sie der Fall). Anschließend benötigen Sie ein Verzeichnissynchronisierungstool (z. B. Forefront Identity Manager oder FIM), um Benutzerkonten während ihres Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business Ressourcengesamtstrukturtopologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die in [mehreren Gesamtstrukturen in einer Skype for Business Topologie der Ressourcengesamtstruktur](system-requirements.md#BKMK_multipleforestopology)beschrieben ist.
  
In dieser Topologie gibt es eine oder mehrere Benutzergesamtstrukturen, und Skype for Business Server in einer dedizierten Ressourcengesamtstruktur bereitgestellt wird. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder einer anderen Gesamtstruktur bereitgestellt und für Hybridbereitstellungen mit Exchange Online konfiguriert werden, oder E-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie ist kein Diagramm verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Ressourcengesamtstrukturtopologie mit Skype for Business Online und Azure Active Directory Verbinden
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung. Sie werden mit Microsoft 365 mithilfe von Azure AD Verbinden synchronisiert. Alle Benutzer sind über Microsoft 365 für Skype for Business aktiviert.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
In diesem Szenario gibt es mehrere lokale Gesamtstrukturen mit einer Ressourcengesamtstrukturtopologie. Es besteht eine voll vertrauenswürdige Beziehung zwischen den Active Directory-Gesamtstrukturen. Das Azure Active Directory Verbinden Tool wird verwendet, um Konten zwischen den lokalen Benutzergesamtstrukturen und Microsoft 365 oder Office 365 zu synchronisieren.
  
 Die Organisation verfügt auch über Microsoft 365 oder Office 365 und verwendet [Azure Active Directory Verbinden,](/azure/active-directory/connect/active-directory-aadconnect) um ihre lokalen Konten mit Microsoft 365 oder Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, werden über Microsoft 365 oder Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Single Sign-On-Authentifizierung wird von einer Active Directory-Verbunddienste-Farm in der Benutzergesamtstruktur bereitgestellt.
  
In diesem Szenario wird die Bereitstellung Exchange lokalen Exchange Online, einer Hybridlösung Exchange oder die Bereitstellung Exchange unterstützt. (Das Diagramm zeigt nur Exchange lokal, aber die anderen Exchange Lösungen werden ebenfalls vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Ressourcengesamtstrukturtopologie mit hybrider Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzergesamtstrukturen, und Skype for Business wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt und für den Hybridmodus mit Skype for Business Online konfiguriert. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für hybride Exchange Online konfiguriert werden. Alternativ können E-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter Konfigurieren einer Umgebung mit [mehreren Gesamtstrukturen für hybride Skype for Business.](../../SfbHybrid/hybrid/configure-a-multi-forest-environment-for-hybrid.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Skype for Business Server 2019 erfordert DNS aus den folgenden Gründen:
  
- DNS ermöglicht es Skype for Business Server 2019, interne Server oder Pools zu ermitteln, sodass eine Server-zu-Server-Kommunikation möglich ist.
    
- MIT DNS können Clientcomputer den Front-End-Pool oder Standard Edition Server ermitteln, der für SIP-Transaktionen verwendet wird.
    
- Einfache URLs für Konferenzen werden den Servern zugeordnet, auf denen diese Konferenzen gehostet werden.
    
- DNS ermöglicht externen Benutzern und Clientcomputern die Verbindung mit Ihren Edgeservern oder dem HTTP-Reverseproxy für Chatnachrichten oder Konferenzen.
    
- Damit können Unified Communications(UC)-Geräte, die nicht angemeldet sind, den Front-End-Pool oder Standard Edition Server ermitteln, auf dem der Geräteaktualisierungswebdienst ausgeführt wird, um Updates abzurufen und Protokolle zu senden.
    
- Mithilfe von DNS können mobile Clients Webdienstressourcen automatisch ermitteln, ohne dass Benutzer manuell URLs in ihre Geräteeinstellungen eingeben müssen.
    
- Es wird beim DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2019 keine internationalisierten Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig zu beachten, dass jeder Name im DNS mit dem Computernamen identisch ist, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2019 verwendet wird. Insbesondere können in der Umgebung keine Kurznamen vorhanden sein, und es müssen FQDNs für den Topologie-Generator vorhanden sein.
  
Dies scheint für jeden Computer logisch zu sein, der bereits einer Domäne beigetreten ist, aber wenn Sie über einen Edgeserver verfügen, der nicht mit Ihrer Domäne verbunden ist, hat er möglicherweise einen Kurznamen ohne Domänensuffix. Stellen Sie sicher, dass dies nicht der Fall ist, entweder im DNS oder auf dem Edgeserver oder einem Skype for Business Server 2019-Server oder -Pool.
  
Verwenden Sie auf jeden Fall keine Unicode-Zeichen oder Unterstriche. Standardzeichen (A-Z, a-z, 0-9 und Bindestriche) werden von externen DNS- und öffentlichen Zertifizierungsstellen unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen, daran ist es wichtig zu denken), sodass Sie sich viel Probleme ersparen, wenn Sie dies von Anfang an benennen.
  
Weitere Informationen zu DNS-Anforderungen für Netzwerke finden Sie im Abschnitt ["Networking"](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) in unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Eines der wichtigsten Dinge, die Sie vor der Bereitstellung tun können, ist sicherzustellen, dass Ihre Zertifikate in ordnung sind. Skype for Business Server 2019 benötigt eine Public Key-Infrastruktur (PKI) für TLS-Verbindungen (Transport Layer Security) und MTLS-Verbindungen (Mutual Transport Layer Security). Um auf standardisierte Weise sicher zu kommunizieren, verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstellen ausgestellt wurden.
  
Dies sind einige der Elemente, für die Skype for Business Server 2019 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Clients und Servern
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Externer Benutzerzugriff auf Audio-/Videositzungen ,Anwendungsfreigabe und Konferenzen
    
- Kommunizieren mit Webanwendungen und Outlook Web Access (OWA)
    
Die Zertifikatplanung ist daher ein Muss. Sehen wir uns nun eine Liste einiger Dinge an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Skype for Business Server 2019 unterstützt die SUITE SHA-1 und SHA-2 der Digestgrößen (224, 256, 384 und 512 Bit) und erfüllt oder überschreitet die Betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server unterstützt, die Skype for Business Server 2019 ausgeführt werden.
    
- Die automatische Registrierung wird für Skype for Business Server 2019-Edgeserver nicht unterstützt.
    
> [!NOTE]
> Die Verwendung des RSASSA-PSS-Signaturalgorithmus wird nicht unterstützt und kann unter anderem zu Fehlern bei Anmelde- und Anrufweiterleitungsproblemen führen. 
  
- Verschlüsselungsschlüssellängen von 1024, 2048 und 4096 werden unterstützt. Es werden Schlüssellängen von 2048 und höher empfohlen.
    
- Der Standardmäßige Digestalgorithmus oder Hashsignaturalgorithmus ist RSA. Die Algorithmen ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist eine Menge zu bedenken, und es gibt eine Vielzahl von Komfortniveaus beim Anfordern von Zertifikaten von einer Zertifizierungsstelle. Nachfolgend finden Sie weitere Anleitungen, um Ihre Planung so problemlos wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten ihrer internen Server, und höchstwahrscheinlich erhalten Sie diese von einer internen Zertifizierungsstelle (die sich in Ihrer Domäne befindet). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle (eine im Internet) anfordern. Wenn Sie sich fragen, zu welcher öffentlichen Zertifizierungsstelle Sie gehen sollten, können Sie sich die Liste der [Unified Communications-Zertifikatpartner](../../SfbPartnerCertification/certification/services-ssl.md) ansehen.
  
Außerdem benötigen Sie Zertifikate, wenn Skype for Business Server 2019 mit anderen Anwendungen und Servern kommuniziert, z. B. Microsoft Exchange Server. Dies muss natürlich ein Zertifikat sein, das diese anderen Apps und Server auf unterstützte Weise verwenden können. Skype for Business Server 2019 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und -Autorisierung. Wenn Sie daran interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2019.
  
Skype for Business Server 2019 umfasst auch Unterstützung für (ohne Dass) Zertifikate, die mit der sha-256-Kryptografiehashfunktion signiert wurden. Um den externen Zugriff mit SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mit SHA-256 ausgestellt werden.
  
Um die Dinge einfach zu halten, haben wir die Zertifikatanforderungen für Standard Edition Server, Front-End-Pools und andere Rollen in die folgenden Tabellen eingefügt, wobei die fiktiven contoso.com als Beispiele verwendet werden (Sie werden wahrscheinlich etwas anderes für Ihre Umgebung verwenden). Hierbei handelt es sich um standardmäßige Webserverzertifikate mit privaten Schlüsseln, die nicht exportierbar sind. Einige zusätzliche Punkte, die Sie beachten müssen:
  
- Die erweiterte Schlüsselverwendung (EKU) des Servers wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Jeder Anzeigename des Zertifikats muss im Computerspeicher eindeutig sein.
    
- Gemäß den folgenden Beispielnamen müssen sie dem alternativen Antragstellernamen (Subject Alternative Name, SAN) des Zertifikats hinzugefügt werden, wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben.
    
Zertifikate für Standard Edition Server:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Auf Standard Edition Servern ist der Server-FQDN identisch mit dem Pool-FQDN.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (identisch mit dem FQDN des Servers)  <br/> AND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=se01.contoso.com; SAN= \* .contoso.com  <br/> |Sie können den internen Web-FQDN im Topologie-Generator nicht überschreiben.  <br/> Wenn Sie über mehrere einfache Besprechungs-URLs verfügen, müssen Sie alle als SANs einschließen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> AND  <br/> • Einfache EINWAHL-URL  <br/> • Besprechung einfacher URLs pro SIP-Domäne  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Front-End-Pool:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (der NICHT mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • Skype for Business Pool-FQDN  <br/> AND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> AND  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN= \* .contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Director, FQDN des Directorpools.  <br/> Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in der Gruppenrichtlinie ein strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für sip.sipdomain (für jede sip-Domäne, die Sie haben).  <br/> |pool.contoso.com; SAN=dir01.contoso.com  <br/> Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (identisch mit dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • Skype for Business Pool-FQDN  <br/> AND  <br/> • Erfüllen einfacher URLs  <br/> • Einfache EINWAHL-URL  <br/> • Einfache ADMIN-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=dir01.contoso.com SAN= \* .contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> AND  <br/> • Besprechung einfacher URLs pro SIP-Domäne  <br/> • Einfache EINWAHL-URL  <br/> OR  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der externe Web-FQDN des Director muss sich vom Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN= \* .contoso.com  <br/> |
   
Zertifikate für eigenständigen Vermittlungsserver:
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedsservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance (insbesondere Survivable Branch Appliance 2015 für Skype for Business Server 2019):
  
|**Zertifikat**|**Antragstellername/allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Appliance  <br/> |SIP.\<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für externen Benutzerzugriff (Edge)

Skype for Business Server 2019 unterstützt die Verwendung eines **einzelnen öffentlichen Zertifikats** für externe Zugriffs- und Webkonferenz-Edgeschnittstellen sowie den A/V-Authentifizierungsdienst, der alle über die Edgeserver bereitgestellt wird. Ihre interne Edgeschnittstelle verwendet in der Regel ein privates Zertifikat, das von Ihrer internen Zertifizierungsstelle ausgestellt wurde. Wenn Sie dies bevorzugen, können Sie auch hierfür ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle stammt.
  
Ihr Reverseproxy (RP) verwendet auch ein öffentliches Zertifikat und verschlüsselt die Kommunikation von Ihrem RP an Clients und das RP zu internen Servern mithilfe von HTTP (oder genauer gesagt TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie einige zusätzliche Einträge mit alternativen Antragstellernamen in Ihre Zertifikate aufnehmen, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Sie benötigen SAN-Namen für die automatische Ermittlung für die folgenden Zertifikate:
  
- Directorpool
    
- Front-End-Pool
    
- Reverse-Proxy
    
Die Einzelheiten sind in den folgenden Tabellen aufgeführt.
  
Hier ist eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2019 bereitgestellt, ohne Mobilität bereitzustellen, und dies kommt später, wenn Sie bereits Zertifikate in Ihrer Umgebung haben. Die erneute Bereitstellung über eine interne Zertifizierungsstelle ist in der Regel ziemlich einfach, aber mit öffentlichen Zertifikaten von einer öffentlichen Zertifizierungsstelle kann dies etwas pricyer sein.
  
Wenn Sie sich dies ansehen und viele SIP-Domänen haben (was das Hinzufügen von SANS teurer machen würde), können Sie Ihren Reverseproxy so konfigurieren, dass er HTTP für die ursprüngliche AutoErmittlungsdienstanforderung verwendet, anstatt HTTPS (die Standardkonfiguration) zu verwenden. Der Artikel ["Plan for Mobility"](../../SfbServer/plan-your-deployment/mobility.md) enthält weitere Informationen dazu.
  
Zertifikatanforderungen für Directorpool und Front-End-Pool:
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|Url des internen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscoverinternal.\<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Alternativ können Sie SAN= \* verwenden.\<sipdomain\>
  
Zertifikatanforderungen für Reverseproxys (öffentliche Zertifizierungsstelle):
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |SAN=lyncdiscover.\<sipdomain\>  <br/> |
   
Dieser SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener auf Ihrem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Der Reverseproxylistener verfügt über SANs für ihre externen Webdienst-URLs. Einige Beispiele sind SAN=skypewebextpool01.contoso.com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2019 kann die gleiche Dateifreigabe für den gesamten Dateispeicher verwenden. Beachten Sie Dabei Folgendes:
  
- Eine Dateifreigabe muss sich entweder auf direct Attached Storage (DAS) oder einem Speicherbereichsnetzwerk (SAN) befinden. Dazu gehören das dfs (Distributed File System) und ein redundantes Array unabhängiger Datenträger (RAID) für Dateispeicher. Weitere Informationen zu DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj127250(v=ws.11))
    
- Wir empfehlen einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie bereits eine verwenden, sollten Sie Windows Server 2012 oder höhere Versionen clustern.

> [!Note]
> **Warum die neuesten Windows?** Ältere Versionen verfügen möglicherweise nicht über die richtigen Berechtigungen, um alle Features zu aktivieren. Sie können den Clusteradministrator verwenden, um die Dateifreigaben zu erstellen. Weitere Informationen finden Sie in diesem Supportartikel [zum Erstellen von Dateifreigaben auf einem Cluster.](https://support.microsoft.com/help/224967)
    
> [!CAUTION]
> You should know that using network attached storage (NAS) as a file share isn't supported, so use one of the options listed above. Diese Unterstützungseinschränkung wird durch den variablen Entwurf von NAS-Geräten verursacht, die die Anpassungsfähigkeit des Dateisystems an den Windows serverbasierten Computer bereitstellen müssen, der auf das freigegebene Dateisystem der Geräte zugreift.
