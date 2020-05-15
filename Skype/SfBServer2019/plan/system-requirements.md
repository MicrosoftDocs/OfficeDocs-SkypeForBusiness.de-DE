---
title: System Anforderungen für Skype for Business Server 2019
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
description: 'Zusammenfassung: bereiten Sie Ihre Skype for Business Server 2019-Server und die Domäneninfrastruktur mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sowie Zertifikat-DNS, Dateifreigabe und Active Directory Informationen helfen Ihnen, eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.'
ms.openlocfilehash: 8bb12fa9f5d0cd0144604f21d311c50f7f63b0f4
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232376"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>System Anforderungen für Skype for Business Server 2019
 
**Zusammenfassung:** Bereiten Sie die Installation von Skype for Business Server 2019 mit diesem Thema vor. Hier werden Hardware, Betriebssystem, Software, Datenbanken, Zertifikate, aktive diretos, DNS und Filesharing behandelt. Alle Systemanforderungen und Empfehlungen stehen zur Verfügung, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2019 beginnen. Dieser Artikel führt Sie durch die Planung der folgenden Schritte:
  
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

Nachdem Sie Ihre Topologie heruntergefahren sind (und wenn nicht, können Sie die [Grundlagen der Topologie für Skype for Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) Thema), ist es an der Zeit, über Server nachzudenken. Für Skype for Business Server 2019-Server ist 64-Bit-Hardware erforderlich. Unsere Empfehlungen für die Hardware finden Sie weiter unten. Dabei handelt es sich nicht um Anforderungen, Sie entsprechen jedoch den Anforderungen für eine optimale Leistung. Wir verfügen über eine Dokumentation zur Kapazitätsplanung, mit der Sie bestimmen können, ob Sie je nach Ihren Umständen mehr benötigen.
  
Empfohlene Hardware für Standard Edition-Server:

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 V3 Dualprozessor, 6-adrig, 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |Entweder  <br/> • 8 oder mehr 10000-u/min-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz (zwei der Datenträger mit RAID 1 und 6 mit RAID 10).  <br/> ODER  <br/> • Solid State Drives (SSDs), die denselben freien Speicherplatz und ähnliche Leistung wie 8 10000 rpm Mechanical Disk Drives bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeiten).  <br/> Duale oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition-Server **nicht** unterstützt. <br/> Solange Sie nicht dem Betriebssystem ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, können Sie Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verwenden. Dieses Szenario stellt keinen Multi-Homed-Server dar und wird unterstützt.  <br/> |


Empfohlene Hardware für Front-End-Server und Back-End-Server:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 V3 Dualprozessor, 6-adrig, 2,4 Gigahertz (GHz) oder höher. <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |64 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |Entweder  <br/> • 8 oder mehr 10000-u/min-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz (zwei der Datenträger mit RAID 1 und 6 mit RAID 10).  <br/> ODER  <br/> • Solid State Drives (SSDs), die denselben freien Speicherplatz und ähnliche Leistung wie 8 10000 rpm Mechanical Disk Drives bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeiten).  <br/> Duale oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition-Server **nicht** unterstützt. <br/> Solange Sie nicht dem Betriebssystem ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, können Sie Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verwenden. Dieses Szenario stellt keinen Multi-Homed-Server dar und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 V3 Dualprozessor, 6-adrig, 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte.  <br/> |
|Datenträger  <br/> |Entweder  <br/> • 4 oder mehr 10000 rpm-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten sich in einer 2X RAID 1-Konfiguration befinden).  <br/> ODER  <br/> • Solid State Drives (SSDs), die denselben freien Speicherplatz und ähnliche Leistung wie 4 10000 rpm Mechanical Disk Drives bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeiten).  <br/> Duale oder Multi-Homed-Konfigurationen werden für Video-Interop-Server und Directors **nicht** unterstützt. <br/> Edgeserver benötigen zwei Netzwerkschnittstellen mit zwei Netzwerkadaptern, 1 Gbit/s oder höher (oder zwei gekoppelte Netzwerkadapter für insgesamt vier, wobei jedes Paar mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeitet, wobei insgesamt zwei Paare verwendet werden).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs) zur Konfiguration einer bestimmten PSTN-IP-Adresse unterstützt.  <br/> |


> [!NOTE]
> Unabhängig von der Serverrolle empfehlen wir auch die folgenden Hardwareeinstellungen für Skype for Business Server 2019 (Dies kann je nach der von Ihnen erworbenen Hardware unterschiedlich sein, siehe Herstellerdokumentation für spezifische Informationen):
> - BIOS config-sollte von NUMA auf Flat festgelegt werden.
> - Aktivieren Sie Hyperthreading.
> - Die Einstellung der RSS-Warteschlange sollte auf 8 Warteschlange festgelegt werden.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Betriebssysteme für Skype for Business Server 2019
<a name="OS"> </a>

Nachdem Sie die Hardware installiert haben, müssen Sie das Betriebssystem (OS) installieren, mit dem Sie Skype for Business Server 2019 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Alles andere als die hier aufgelisteten Betriebssysteme funktionieren nicht ordnungsgemäß; versuchen Sie es nicht für Installationen von Skype for Business Server 2019. Beispielsweise ist die Server Core-Option nicht aufgeführt und wird daher nicht unterstützt.

> [!NOTE]
> Das in-Place-Upgrade des Betriebssystems wird mit lync Server 2013 nicht unterstützt. Sie müssen einen separaten Pool bereitstellen und Benutzer mit einem anderen Betriebssystem in den neuen Pool migrieren. Alle Server in einem Pool müssen dieselbe Betriebssystemversion aufweisen.

> [!NOTE]
> 
> Wenn Sie Windows Admin Center 2019 auf Ihrem Windows Server 2019-Computer installieren, werden Sie aufgefordert, einen Port für die Überwachung anzufordern. Es gibt einen liklihood, den Sie möglicherweise Port 443 auswählen, aber wenn auf dem Computer Skype for Business Server 2019 installiert ist oder Skype for Business Server 2019 darauf installiert ist, müssen Sie eine andere Portnummer auswählen.
> 
>Warum ist dies der Fall? Wenn Windows Admin Center 2019 auf Port 443 läuft, können Sie über die Skype for Business-Systemsteuerung keine Verbindung mit dem Server herstellen, und Sie können auch keine Verbindung mit einem internen Webdienst herstellen, der auf dem Server (Adressbuch-Webdienst, AutoErmittlungsdienst, WebTICKET-Dienst usw.) durchführen wird.  Tatsächlich können Sie keine Verbindung mit einer internen Webdienst-URL herstellen. Wählen Sie einen anderen Port aus, für den Fall, dass Sie Windows Admin Center 2019 auf einem Server mit Skype for Business Server 2019 platzieren möchten.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software, die vor einer Skype for Business Server 2019-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für jeden Server mit Skype for Business Server 2019 installieren oder konfigurieren müssen. Diese werden unten aufgeführt, gefolgt von zusätzlichen Anforderungen für bestimmte Serverrollen.

> [!IMPORTANT]
> Skype for Business 2019 unterstützt .NET Framework 4,8. 
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Auf allen Skype for Business Server Servern muss Windows PowerShell 3,0 installiert sein.  <br/> • Diese sollte standardmäßig mit Windows Server 2016 installiert werden.<br/> |
|Microsoft .NET Framework  <br/> |WCF-Dienste ist ein **Feature** , das als Windows-Feature installiert ist, unter **Server-Manager**, anfänglich keine Downloads erforderlich. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert ist und Sie es überprüfen, dass die HTTP- **Aktivierungs** Option ebenfalls überprüft und installiert wird, wie folgt: <br/> ![Screenshot, der die Option "http-Aktivierung" unter dem .NET Framework 4.5 Features anzeigt.](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, dass einige andere Dinge installiert werden müssen, damit die HTTP-Aktivierung installiert werden kann. Das ist normal; Klicken Sie auf OK, und fahren Sie fort. Wenn Sie dieses Popup nicht erhalten, können Sie davon ausgehen, dass diese Dinge bereits installiert sind und weiter gehen.  <br/> Microsoft .NET Framework wird normalerweise bei der Installation von Windows Server 2016 installiert. Skype for Business Server erfordert zwar Microsoft .NET Framework 4,7 oder 4,8, daher müssen Sie Sie wahrscheinlich aktualisieren. Sie können das Update [hier](https://support.microsoft.com/help/3186497/the-net-framework-4-7-offline-installer-for-windows/) finden.<br/> |
|Media Foundation  <br/> |Für Windows Server 2016 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.  <br/> Für alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, ist Windows Media Format Runtime erforderlich, um die Windows Media-Audiodateien (WMA) auszuführen, die von den Anwendungen für das Parken von anrufen, Ankündigungen und Reaktionsgruppen für Ankündigungen und Musik wiedergegeben werden.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3,5 zur Unterstützung von Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2019.  <br/> • Für Windows Server 2016 müssen Sie nichts herunterladen. Öffnen Sie den **Server-Manager**, und wechseln Sie zum **Assistenten zum Hinzufügen von Rollen und Features**. **Windows Identity Foundation 3,5** wird im Abschnitt **Features** aufgeführt. Wenn Sie ausgewählt ist, sind Sie gut. Andernfalls wählen Sie Sie aus, und klicken Sie auf **weiter** , um die Schaltfläche **Installieren** zu erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS-und AD LDS-Tools  <br/> |
   
 **Front-End-Server und Standard Edition-Server benötigen außerdem Folgendes:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (IIS)  <br/> |IIS ist auf allen Front-End-Servern sowie auf allen Standard Edition-Servern erforderlich, wobei die folgenden Module ausgewählt sind:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungs Tools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Authentifizierung der Client Zertifikatzuordnung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET-Erweiterbarkeit 3,5, .NET-Erweiterbarkeit 4,5, ASP.NET 3.5, ASP.NET 4,5, ISAPI-Erweiterungen, ISAPI-Filter  <br/> • Verwaltungs Tools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und-Tools  <br/> Beachten Sie, dass auch anonymer Zugriff erforderlich ist, Sie erhalten dies jedoch bei der Installation von IIS, sodass Sie diesen nicht in der Liste auswählen können.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016 müssen Sie das Feature **Media Foundation** im **Server-Manager**installieren. Sie können Ihre Skype for Business Server 2019-Installation ohne diese Funktion starten, aber Sie werden aufgefordert, Sie zu installieren und den Server dann neu zu starten, bevor die Installation von Skype for Business Server 2019 fortgesetzt wird. Es ist besser, dies vor der Zeit zu tun. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight [hier](https://www.microsoft.com/silverlight/)installieren.  <br/> |
   
Um Ihnen zu helfen, finden Sie hier ein Beispiel-PowerShell-Skript, das Sie ausführen können, um dieses zu automatisieren:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
```

 **Directors benötigen außerdem Folgendes:**
  
IIS, wobei die folgenden Module ausgewählt wurden:
  
- Allgemeine HTTP-Features
    
  - Standarddokument
    
  - HTTP-Fehler
    
  - Statischer Inhalt
    
- Systemzustand und Diagnose
    
  - HTTP-Protokollierung
    
  - Protokollierungstools
    
  - Tracing
    
- Leistung
    
  - Komprimierung statischer Inhalte
    
- Sicherheit
    
  - Anforderungsfilterung
    
  - Authentifizierung der Client Zertifikatzuordnung
    
  - Windows-Authentifizierung
    
- Anwendungsentwicklung
    
  - .NET-Erweiterbarkeit 3,5
    
  - .NET-Erweiterbarkeit 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4,5
    
  - ISAPI-Erweiterung
    
  - ISAPI-Filter
    
(Wenn Sie sich Fragen, ist es das gleiche Modul, das als Front-End-Server und Standard Edition-Server festgelegt ist, wobei die dynamischen Inhaltskomprimierung und Verwaltungs Tools ausgelassen werden.)
  
Außerdem gibt es unten einen PowerShell-Code:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, Telnet-Client
```

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Back-End-Datenbanken, die mit Skype for Business Server 2019 verwendet werden
<a name="DBs"> </a>

Bei der Installation von Skype for Business Server 2019 Standard Edition haben Sie SQL Server 2016 Express (64-Bit Edition).

Skype for Business Server 2019 Enterprise Edition erfordert eine vollständige SQL Server, wie unten angegeben (nur 64-Bit-Edition; Bitte verwenden Sie keine 32-Bit-Editionen):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |Microsoft SQL Server 2017 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |
Microsoft SQL Server 2016 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausgeführt werden.|
 |

Wenn die SQL Server Edition, die Sie hier aufgelistet verwenden möchten, nicht angezeigt wird, können Sie Sie nicht verwenden.
  
> [!NOTE]
> Sie müssen auch SQL Server Reporting Services für die Monitoring Server Rolle installieren. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL-Clustering und SQL Always on

SQL-Clustering mit Skype for Business Server 2019 wird unterstützt. Wenn Sie SQL-Clustering einrichten möchten, erfolgt dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL-Clustering verfügen, die unterstützt wird. Teilen Sie den passiven Knoten nicht mit einer anderen SQL-Instanz.
  
Sie können für Failoverclustering folgende Aktionen ausführen:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.
- Microsoft SQL Server 2017 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.
- Microsoft SQL Server 2016 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

Sechzehn Knoten:
  
- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.
- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.
- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

SQL Always-on wird unterstützt, und weitere Informationen dazu finden Sie unter [Back End Server High Availability in Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Weitere Empfehlungen zur Server Installation:
  
Installieren Sie bitte keine ISA (Microsoft Internet Security and Acceleration Server)-Client Software oder andere LSP-Software (Winsock Layered Service Providers) (alle Drittanbieter-Firewalls oder Antivirensoftware-Netzwerk Inspektions Software wären hier enthalten) auf allen Front-End-Servern oder eigenständigen Vermittlungsservern. Bei der Installation dieser Software ist eine schlechte Leistung beim Mediendatenverkehr zu beobachten.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Obwohl ein Großteil der Konfigurationsdaten für Server und Dienste im Skype for Business Server 2019-zentralen Verwaltungsspeicher gespeichert ist, werden einige Dinge noch in Active Directory gespeichert:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Skype for Business Server 2015 und lync Server 2013, um die Abwärtskompatibilität mit den vorherigen unterstützten Versionen aufrechtzuerhalten  <br/> |
|Daten  <br/> |SIP-URI des Benutzers und andere Benutzereinstellungen  <br/> |
||Kontaktobjekte für Anwendungen (wie Reaktionsgruppenanwendung und Konferenzzentrale)  <br/> |
||Aus Gründen der Abwärtskompatibilität veröffentlichte Daten  <br/> |
||Einen Dienststeuerungspunkt (Service Control Points, SCP) für den zentralen Verwaltungsspeicher  <br/> |
||Das Kerberos-Authentifizierungskonto (ein optionales Computerobjekt)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssystem für Domänencontroller

Die folgenden Betriebssysteme für Domänen Controller können verwendet werden:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2019 bereitstellen, und die Gesamtstrukturfunktionsebene einer Gesamtstruktur, die Sie Skype for Business Server 2019 in bereitstellen, muss eine der folgenden sein:
  
- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Können in diesen Umgebungen schreibgeschützte Domänencontroller vorhanden sein? Sicher, solange auch schreibbare Domänencontroller verfügbar sind.
  
Es ist wichtig zu wissen, dass Skype for Business Server 2019 keine Domänen mit einfacher Bezeichnung unterstützt. Was sind sie? Wenn Sie über eine Stammdomäne mit dem Namen "contoso. local" verfügen, wird das gut gehen. Wenn Sie über eine Stammdomäne verfügen, die nur local heißt, funktioniert das nicht, und es wird daher nicht unterstützt. Ein wenig mehr dazu wurde [in diesem Knowledge Base-Artikel](https://support.microsoft.com/kb/300684/)geschrieben.
  
Skype for Business Server 2019 unterstützt auch nicht das Umbenennen von Domänen. Wenn Sie Ihre Domäne wirklich umbenennen müssen, müssen Sie Skype for Business Server 2019 deinstallieren, die Domänenumbenennung durchführen und dann Skype for Business Server 2019 erneut installieren.
  
Schließlich haben Sie möglicherweise mit einer Domäne mit einer gesperrten AD DS Umgebung zu tun, und das ist in Ordnung. Weitere Informationen zum Bereitstellen von Skype for Business Server 2019 in einer gesperrten AD DS Umgebung finden Sie in der Bereitstellungsdokumentation.
  
### <a name="ad-topologies"></a>AD-Topologien

Unterstützte Topologien in Skype for Business Server 2019 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Skype for Business Ressourcengesamtstruktur mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
    
Wir verfügen über Diagramme und Beschreibungen, mit denen Sie ermitteln können, welche Topologie in Ihrer Umgebung vorhanden ist, oder was Sie vor der Installation von Skype for Business Server 2019 einrichten müssen. Um es einfach zu halten, werden wir auch einen Schlüssel einschließen:
  
![Der ist ein Schlüssel zu den Symbolen, die für Skype for Business Topologie-Diagramme verwendet werden.](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm Active Directory einzelnen Gesamtstruktur mit einer einzelnen Domäne](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Dies wird nicht einfacher. Es handelt sich um eine einzelne Domänengesamtstruktur, eine gemeinsame Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm für eine einzelne Gesamtstruktur, eine einzelne Struktur und mehreren Domänen](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt wieder eine einzelne Gesamtstruktur, aber Sie hat auch eine oder mehrere untergeordnete Domänen (es gibt drei in diesem spezifischen Beispiel). Die Domäne, in der die Benutzer erstellt werden, unterscheidet sich möglicherweise von der Domäne, in der Skype for Business Server 2019 bereitgestellt wird. Warum sollten Sie sich darüber Gedanken machen? Beachten Sie, dass bei der Bereitstellungeines Skype for Business Server Front-End-Pool alle Server in diesem Pool sich in einer einzigen Domäne befinden müssen. Sie können eine domänenübergreifende Verwaltung über Skype for Business Server Unterstützung von universellen Windows-Administratorgruppen haben.
  
Im obigen Diagramm sehen Sie, dass Benutzer aus einer Domäne auf Skype for Business Server Pools aus derselben oder aus unterschiedlichen Domänen zugreifen können, selbst wenn sich diese Benutzer in einer untergeordneten Domäne befinden.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm für eine einzelne Gesamtstruktur, mehrere Strukturen und nicht zusammenhängende Namespaces](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Sie haben möglicherweise eine Topologie ähnlich wie in diesem Diagramm, in dem Sie eine Gesamtstruktur haben, aber innerhalb dieser Gesamtstruktur mehrere Domänen mit separaten AD-Namespaces sind. In diesem Fall ist dieses Diagramm eine gute Illustration, da es Benutzer in drei verschiedenen Domänen enthält, die auf Skype for Business Server 2019 zugreifen. Durchgezogene Linien deuten darauf hin, dass Sie auf einen Skype for Business Server Pool in ihrer eigenen Domäne zugreifen, während eine gestrichelte Linie angibt, dass Sie in einen Pool in einer anderen Struktur wechseln.
  
Wie Sie sehen können, können Benutzer in derselben Domäne, in der gleichen Struktur oder sogar in einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Mehrere Gesamtstrukturen in einem Topologie-Diagramm der zentralen Gesamtstruktur](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 unterstützt mehrere Gesamtstrukturen, die in einer Topologie mit zentraler Gesamtstruktur konfiguriert sind. Wenn Sie sich nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte, um Benutzer in den anderen Gesamtstrukturen darzustellen, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert das? Ein Verzeichnis Synchronisierungs Produkt (beispielsweise Forefront Identity Manager oder FIM) verwaltet die Benutzerkonten Ihrer Organisation während Ihres gesamten Bestehens. Wenn ein Konto aus einer Gesamtstruktur erstellt oder gelöscht wird, wird diese Änderung mit dem entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre AD-Infrastruktur vorhanden ist, ist die Umstellung auf diese Topologie möglicherweise nicht einfach, aber wenn Sie bereits vorhanden sind oder Ihre Gesamtstruktur Infrastruktur planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2019-Bereitstellung in einer einzelnen Gesamtstruktur zentralisieren, während Benutzer in jeder Gesamtstruktur suchen, kommunizieren und das vorhanden sein anderer Benutzer anzeigen können. Alle Benutzer Kontakt Updates werden automatisch mit der Synchronisierungssoftware verarbeitet.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie
<a name="BKMK_multipleforestopology"> </a>

![Mehrere Gesamtstrukturen in einem Topologie-Diagramm der Ressourcengesamtstruktur](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Außerdem wird eine Topologie mit Ressourcengesamtstruktur unterstützt. Es ist, wo eine Gesamtstruktur für die Ausführung ihrer Serveranwendungen dediziert ist, wie Exchange Server und Skype for Business Server 2019. Diese Ressourcengesamtstrukturen hosten auch eine synchronisierte Darstellung von aktiven Benutzerobjekten, jedoch keine Anmelde aktivierten Benutzerkonten. Die Ressourcengesamtstruktur ist also eine Umgebung für gemeinsame Dienste für andere Gesamtstrukturen, in der sich die Benutzerobjekte befinden, und Sie verfügen über eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.
  
Beachten Sie, dass Exchange Server in derselben Ressourcengesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden können.
  
Um Skype for Business Server 2019 in dieser Art von Topologie bereitzustellen, würden Sie ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur für jedes Benutzerkonto in den Benutzergesamtstrukturen erstellen (falls Exchange Server bereits in der Umgebung vorhanden ist, ist dies möglicherweise für Sie erledigt). Anschließend benötigen Sie ein Verzeichnissynchronisierungstool (wie Forefront Identity Manager oder FIM), um Benutzerkonten über ihren Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Topologie mit Skype for Business Ressourcengesamtstruktur mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der in [mehreren Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie](system-requirements.md#BKMK_multipleforestopology)beschriebenen Topologie.
  
In dieser Topologie gibt es eine oder mehrere Benutzergesamtstrukturen, und Skype for Business Server wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für hybridbereitstellung mit Exchange Online konfiguriert werden, oder e-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie ist kein Diagramm verfügbar.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur. Die beiden Gesamtstrukturen haben eine Vertrauensstellung. Sie werden mit Microsoft 365 mit Azure AD Connect synchronisiert. Alle Benutzer sind für Skype for Business über Microsoft 365 aktiviert.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
In diesem Szenario gibt es mehrere Gesamtstrukturen mit einer Topologie mit einer Ressourcengesamtstruktur. Zwischen den Active Directory Gesamtstrukturen besteht eine voll vertrauenswürdige Beziehung. Das Azure Active Directory Connect-Tool wird zum Synchronisieren von Konten zwischen den lokalen Benutzergesamtstrukturen und Microsoft 365 oder Office 365 verwendet.
  
 Die Organisation verfügt außerdem über Microsoft 365 oder Office 365 und verwendet [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) , um Ihre lokalen Konten mit Microsoft 365 oder Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, sind über Microsoft 365 oder Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Authentifizierung mit einmaligem Anmelden wird von einer Active Directory Verbunddienst Farm bereitgestellt, die sich in der Benutzergesamtstruktur befindet.
  
In diesem Szenario wird es unterstützt, Exchange lokal, Exchange Online, eine hybride Exchange-Lösung bereitzustellen oder überhaupt keine Exchange-Bereitstellung zu haben. (Das Diagramm zeigt nur lokale Exchange-Bereitstellung, aber auch die anderen Exchange-Lösungen werden vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Hybrid Skype for Business
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzergesamtstrukturen, und Skype for Business wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt und für den Hybrid Modus mit Skype for Business Online konfiguriert. Exchange Server können lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt werden und können für hybride mit Exchange Online konfiguriert werden. Alternativ können e-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter [Konfigurieren einer Umgebung mit mehreren Gesamtstrukturen für Hybrid Skype for Business](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>Domain Name System (DNS)
<a name="DNS"> </a>

Für Skype for Business Server 2019 ist DNS aus folgenden Gründen erforderlich:
  
- Mithilfe von DNS kann Skype for Business Server 2019 interne Server oder Pools ermitteln, sodass eine Server-zu-Server-Kommunikation möglich ist.
    
- DNS ermöglicht Clientcomputern, die Front-End-Pool oder Standard Edition-Server zu ermitteln, die für SIP-Transaktionen verwendet werden.
    
- Es ordnet einfache URLs für Konferenzen mit den Servern zu, die diese Konferenzen hosten.
    
- Mit DNS können externe Benutzer und Clientcomputer eine Verbindung mit ihren Edgeserver oder dem HTTP-Reverseproxy für Chatnachrichten oder Konferenzen herstellen.
    
- Mit dieser Option können Unified Communications-Geräte (UC), die nicht angemeldet sind, die Front-End-Pool oder Standard Edition-Server, auf dem der Geräte Update-Webdienst installiert ist, zum Abrufen von Updates und Senden von Protokollen ermitteln.
    
- Durch die Verwendung von DNS können mobile Clients automatisch Webdienste-Ressourcen ermitteln, ohne dass Benutzer in ihren Geräteeinstellungen manuell URLs eingeben müssen.
    
- Sie wird im DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2019 keine internationalen Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig zu beachten, dass alle DNS-Namen mit dem Computernamen übereinstimmen, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2019 verwendet wird. Insbesondere dürfen keine Kurznamen in der Umgebung vorhanden sein, und es müssen FQDNs für den Topologie-Generator vorhanden sein.
  
Dies scheint logisch für alle Computer zu sein, die bereits einer Domäne beigetreten sind, aber wenn Sie über eine Edgeserver verfügen, die nicht mit Ihrer Domäne verbunden ist, kann die Standardeinstellung ein kurzer Name ohne Domänensuffix sein. Stellen Sie sicher, dass dies nicht der Fall ist, weder in DNS noch im Edgeserver oder in einem Skype for Business Server 2019-Server oder-Pool, was das betrifft.
  
Verwenden Sie definitiv keine Unicode-Zeichen oder Unterstriche. Standard Zeichen (a-z, a-z, 0-9 und Bindestriche) werden von externen DNS-und öffentlichen Zertifizierungsstellen unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen, es ist wichtig, sich daran zu erinnern), daher ersparen Sie sich eine Menge Probleme, wenn Sie den Namen in diesem Sinne von Anfang an berücksichtigen.
  
Weitere Informationen zu den DNS-Anforderungen für Netzwerke finden Sie im Abschnitt [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) in unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Eines der wichtigsten Dinge, die Sie vor der Bereitstellung tun können, ist sicherzustellen, dass Ihre Zertifikate ordnungsgemäß sind. Skype for Business Server 2019 benötigt eine Public Key-Infrastruktur (PKI) für TLS (Transport Layer Security) und MTLS-Verbindungen (Mutual Transport Layer Security). Um eine standardisierte sichere Kommunikation sicherzustellen, verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstellen ausgestellt wurden.
  
Dies sind einige der Dinge, in denen Skype for Business Server 2019 Zertifikate für Folgendes verwendet:
  
- TLS-Verbindungen zwischen Clients und Servern
    
- MTLS-Verbindungen zwischen Servern
    
- Partnerverbund mit automatischer DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf Audio/Video-Sitzungen (AV), Anwendungsfreigabe und Konferenzen
    
- Im Gespräch mit Webanwendungen und-Outlook Web Access (OWA)
    
Die Zertifikatplanung ist daher ein muss. Nun sehen wir uns eine Liste mit einigen Dingen an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mit einem vom Betriebssystemunter stützten Signaturalgorithmus signiert werden. Skype for Business Server 2019 unterstützt die SHA-1-und SHA-2-Suite mit Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Betriebssystemanforderungen.
    
- Die automatische Registrierung wird für interne Server mit Skype for Business Server 2019 unterstützt.
    
- Die automatische Registrierung wird für Skype for Business Server 2019-Edge-Server nicht unterstützt.
    
> [!NOTE]
> Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei Anmelde-und Anruf Weiterleitungs Problemen führen. 
  
- Die Verschlüsselungsschlüssel Längen 1024, 2048 und 4096 werden unterstützt. Die Schlüssellängen von 2048 und höher werden empfohlen.
    
- Der standardmäßige Digest-oder Hashsignatur Algorithmus ist RSA. Die ECDH_P256-, ECDH_P384-und ECDH_P521 Algorithmen werden ebenfalls unterstützt.
    
Das ist eine Menge zu denken, und es gibt eine Vielzahl von Komfort Ebenen mit dem Anfordern von Zertifikaten von einer Zertifizierungsstelle. Im folgenden erhalten Sie weitere Anleitungen, um Ihre Planung so schmerzlos wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten internen Server, und höchstwahrscheinlich erhalten Sie diese von einer internen Zertifizierungsstelle (eine in Ihrer Domäne befindliche Zertifizierungsstelle). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle anfordern (eine im Internet befindliche). Wenn Sie sich Fragen, welche öffentliche Zertifizierungsstelle Sie besuchen sollten, können Sie die Liste [Unified Communications Zertifikat Partner](/SkypeForBusiness/certification/services-ssl) Auschecken.
  
Außerdem benötigen Sie Zertifikate, wenn Skype for Business Server 2019 mit anderen Anwendungen und Servern wie Exchange Server kommuniziert. Dies muss natürlich ein Zertifikat sein, das von diesen anderen apps und Servern in unter stützter Weise verwendet werden kann. Skype for Business Server 2019 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Wenn Sie an diesem Thema interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2019.
  
Skype for Business Server 2019 enthält auch Unterstützung für (ohne erforderliche) Zertifikate, die mit der kryptografischen Hashfunktion von SHA-256 signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mit SHA-256 ausgestellt werden.
  
Um die Dinge so einfach wie möglich zu halten, haben wir die Zertifikatanforderungen für Standard Edition-Server, Front-End-Pools und andere Rollen in den folgenden Tabellen formuliert, wobei die fiktive Contoso.com als Beispiele verwendet wird (Sie verwenden wahrscheinlich etwas anderes für Ihre Umgebung). Hierbei handelt es sich um alle standardmäßigen Webserverzertifikate mit privaten Schlüsseln, die nicht exportierbar sind. Einige zusätzliche Dinge, die Sie beachten sollten:
  
- Die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) von Servern wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Jeder Zertifikatanzeige Name muss im Computerspeicher eindeutig sein.
    
- Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie gemäß den folgenden Beispiel Namen zum alternativen Antragstellernamen (San) des Zertifikats hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN = SE01. contoso. com; San = SE01. contoso. com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Auf Standard Edition-Servern ist der FQDN des Servers identisch mit dem FQDN des Pools.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner FQDN des Webs (entspricht dem FQDN des Servers)  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = SE01. contoso. com; San = SE01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = SE01. contoso. com; San = \* . contoso.com  <br/> |Sie können den internen webfqdn im Topologie-Generator nicht außer Kraft setzen.  <br/> Wenn Sie über mehrere einfache URLs verfügen, müssen Sie Sie alle als Sans einschließen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer FQDN des Webs  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = SE01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = webcon01. contoso. com; San = \* . contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einer Front-End-Pool:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|**Comments**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).  <br/> |SN = EEpool. contoso. com; San = EEpool. contoso. com; San = ee01. contoso. com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner FQDN des Webs (der nicht mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business Pools  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = ee01. contoso. com; San = ee01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = ee01. contoso. com; San = \* . contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer FQDN des Webs  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = ee01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = webcon01. contoso. com; San = \* . contoso.com  <br/> |Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Director:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Directors, FQDN des Directorpool.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für "SIP. sipdomain" "(für jede SIP-Domäne, die Sie haben).  <br/> |Pool.contoso.com; San = dir01. contoso. com  <br/> Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner FQDN des Webs (entspricht dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • FQDN des Skype for Business Pools  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache admin-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN = dir01. contoso. com; San = dir01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = dir01. contoso. com San = \* . contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer FQDN des Webs  <br/> UND  <br/> • Erfüllen einfacher URLs pro SIP-Domäne  <br/> • Einfache URL für Einwahl  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der externe Director-webfqdn muss sich von dem Front-End-Pool oder Front-End-Server unterscheiden.  <br/> SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = \* . contoso.com  <br/> |
   
Zertifikate für eigenständige Vermittlungsserver:
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Pool Mitgliedsservers  <br/> |SN = medsvr-Pool.contoso.net; San = medsvr-Pool.contoso.net; San = medsvr01. contoso. net  <br/> |
   
Zertifikate für Survivable Branch Appliance (insbesondere Survivable Branch Appliance 2015 für Skype for Business Server 2019):
  
|**Zertifikat**|**Antragstellername/Allgemeiner Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Appliance  <br/> |SIP. \< sipdomain " \> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN = sba01. contoso. net; San = SIP. contoso. com; San = SIP. fabrikam. com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den Zugriff durch externe Benutzer (Edge)

Skype for Business Server 2019 unterstützt die Verwendung eines **einzelnen öffentlichen Zertifikats** für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst, der über die Edgeserver bereitgestellt wird. In der internen Edge-Schnittstelle wird in der Regel ein privates Zertifikat verwendet, das von ihrer internen Zertifizierungsstelle ausgestellt wird, aber wenn Sie es bevorzugen, können Sie auch ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle stammt.
  
Ihr Reverseproxy (Reverse Proxy) verwendet auch ein öffentliches Zertifikat und verschlüsselt die Kommunikation zwischen Ihrer RP und den Clients und die RP mit internen Servern mithilfe von http (genauer gesagt TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie einige zusätzliche Alternative Antragstellernamen-Einträge in Ihre Zertifikate aufnehmen, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Sie benötigen San-Namen für die automatische Ermittlung in den folgenden Zertifikaten:
  
- Directorpool
    
- Front-End-Pool
    
- Reverseproxy
    
Die Details sind in den folgenden Tabellen aufgeführt.
  
Hier ist eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2019 ohne die Bereitstellung von Mobilität bereitgestellt, und das kommt später vor, wenn Sie bereits über Zertifikate in Ihrer Umgebung verfügen. Die Neuausstellung über eine interne Zertifizierungsstelle ist normalerweise recht einfach, aber mit öffentlichen Zertifikaten einer öffentlichen Zertifizierungsstelle kann dies ein wenig teurer sein.
  
Wenn Sie sich das ansehen, und wenn Sie viele SIP-Domänen haben (wodurch das Hinzufügen von Sans teurer wäre), können Sie den Reverseproxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Dies ist die Standardkonfiguration). Der Artikel [Plan for Mobility](../../SfbServer/plan-your-deployment/mobility.md) enthält weitere Informationen dazu.
  
Zertifikatanforderungen für Directorpool und Front-End-Pool:
  
|**Beschreibung**|**San-Eintrag**|
|:-----|:-----|
|URL des internen AutoErmittlungsdiensts  <br/> |San = "lyncdiscoverinternal". \< sipdomain "\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover. \< sipdomain "\>  <br/> |
   
Alternativ können Sie auch "San =" verwenden \* . \< sipdomain "\>
  
Zertifikatanforderungen für Reverse Proxys (öffentliche Zertifizierungsstellen):
  
|**Beschreibung**|**San-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover. \< sipdomain "\>  <br/> |
   
Dieses San muss dem Zertifikat zugewiesen werden, das dem SSL-Listener auf dem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Ihr Reverse Proxy-Listener wird Sans für Ihre externe Webdienste-URL (n) haben. Einige Beispiele wären San = skypewebextpool01. contoso. com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2019 kann dieselbe Dateifreigabe für alle Dateispeicher verwenden. Sie müssen Folgendes berücksichtigen:
  
- Eine Dateifreigabe muss entweder im Direct-Attached Storage (das) oder im San (Storage Area Network) vorhanden sein, und dies umfasst das verteilte Datei System (DFS) sowie ein redundantes Array von unabhängigen Datenträgern (RAID) für Dateispeicher. Weitere Informationen zum DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite](https://technet.microsoft.com/library/jj127250.aspx).
    
- Es wird ein freigegebener Cluster für die Dateifreigabe empfohlen. Wenn Sie bereits einen verwenden, sollten Sie Windows Server 2012 oder höhere Versionen Cluster

> [!Note]
> **Warum die neuesten Fenster?** Ältere Versionen verfügen möglicherweise nicht über die richtigen Berechtigungen, um alle Features zu aktivieren. Sie können die Cluster Verwaltung verwenden, um die Dateifreigaben zu erstellen. Weitere Informationen finden Sie in diesem Support Artikel [Gewusst wie: Erstellen von Dateifreigaben in einem Cluster](https://support.microsoft.com/help/224967) .
    
> [!CAUTION]
> Sie sollten wissen, dass die Verwendung von NAS (Network Attached Storage) als Dateifreigabe nicht unterstützt wird, verwenden Sie daher eine der oben aufgeführten Optionen. Diese Support Einschränkung wird durch den Variablen Entwurf von NAS-Geräten verursacht, die Dateisystem Anpassungsfähigkeit an den Windows Server-basierten Computer bieten müssen, der auf das freigegebene Dateisystem des Geräts zugreift.
  







