---
title: System Anforderungen für Skype for Business Server 2019
ms.reviewer: ''
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 'Zusammenfassung: bereiten Sie Ihre Skype for Business Server 2019-Server und die Domäneninfrastruktur in diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sowie Zertifikat-DNS, Dateifreigabe und Active Directory-Informationen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm zu gewährleisten.'
ms.openlocfilehash: b173097377c100fcb03b07d7a502e1e6c096608f
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925326"
---
# <a name="system-requirements-for-skype-for-business-server-2019"></a>System Anforderungen für Skype for Business Server 2019
 
**Zusammenfassung:** Bereiten Sie die Installation von Skype for Business Server 2019 in diesem Thema vor. Hardware, Betriebssystem, Software, Datenbanken, Zertifikate, Active diretoy, DNS und Dateifreigaben werden hier behandelt. Alle Systemanforderungen und-Empfehlungen stehen zur Verfügung, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm zu gewährleisten.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2019 beginnen. Dieser Artikel führt Sie durch die Planung für folgende Arbeitsschritte:
  
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

Nachdem Sie Ihre Topologie heruntergekommen sind (und wenn Sie dies nicht tun, können Sie sich das Thema [Topologie-Grundlagen für Skype for Business Server 2019](../../SfbServer/plan-your-deployment/topology-basics/topology-basics.md) ) angucken, ist es an der Zeit, sich über Server Gedanken zu machen. Für Skype for Business Server 2019-Server ist 64-Bit-Hardware erforderlich. Unsere Empfehlungen für die Hardware finden Sie weiter unten. Zwar handelt es sich dabei nicht um Anforderungen, aber die Empfehlungen entsprechen den Anforderungen, die für eine optimale Leistung erfüllt sein müssen. Wir bieten Ihnen eine Dokumentation zur Kapazitätsplanung, mit deren Hilfe Sie ermitteln können, ob Sie je nach Ihrer Situation Weiteres benötigen.
  
Empfohlene Hardware für Standard Edition-Server:

|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 V3 Dual-Prozessor, 6-adrig, 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dual-oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition-Server **nicht** unterstützt. <br/> Solange Sie nicht für das Betriebssystem verfügbar sind und zum Überwachen und Verwalten von Server Hardware verwendet werden, können Sie Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verwenden. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.  <br/> |


Empfohlene Hardware für Front-End-Server und Back-End-Server:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 V3 Dual-Prozessor, 6-adrig, 2,4 Gigahertz (GHz) oder höher. <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |64 Gigabyte (GB).  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dual-oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server und Standard Edition-Server **nicht** unterstützt. <br/> Solange Sie nicht für das Betriebssystem verfügbar sind und zum Überwachen und Verwalten von Server Hardware verwendet werden, können Sie Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verwenden. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, Standalone-Vermittlungsserver und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Intel Xeon E5-2673 V3 Dual-Prozessor, 6-adrig, 2,4 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2019-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (die Festplatten sollten in einer 2x-RAID-1-Konfiguration sein).  <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 4 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Video-Interop-Server und Directors **nicht** unterstützt. <br/> Edgeserver erfordern zwei Netzwerkschnittstellen, die aus Dual-Port-Netzwerkadaptern bestehen, mit mindestens 1 GBit/s (oder zwei gepaarte Netzwerkadapter, also insgesamt vier; jedes Paar muss mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden, um insgesamt zwei Paare zu erhalten).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs) unterstützt, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen.  <br/> |


> [!NOTE]
> Unabhängig von der Serverrolle empfehlen wir auch die folgenden Hardware-Einstellungen für Skype for Business Server 2019 (Dies kann je nach der von Ihnen erworbenen Hardware variieren, daher beziehen Sie sich bitte auf die Herstellerdokumentation für Einzelheiten):
> - BIOS-Konfiguration – sollte von NUMA auf Flat festgesetzt werden.
> - Aktivieren Sie Hyperthreading.
> - Die Einstellung der RSS-Warteschlange sollte auf 8 Warteschlangen festgelegt sein.

   
## <a name="operating-systems-for-skype-for-business-server-2019"></a>Betriebssysteme für Skype for Business Server 2019
<a name="OS"> </a>

Nachdem Sie die Hardware eingerichtet haben, müssen Sie das Betriebssystem installieren, mit dem Sie Skype for Business Server 2019 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 <br/> |
|Windows Server 2016 <br/> ||
||
   
Alle anderen als die hier aufgelisteten Betriebssysteme funktionieren nicht richtig; versuchen Sie es bitte nicht für die Installation von Skype for Business Server 2019. Die Option Server Core ist beispielsweise nicht aufgeführt und wird daher nicht unterstützt.

> [!NOTE]
> 
> Wenn Sie Windows Admin Center 2019 auf Ihrem Windows Server 2019-Computer installieren, werden Sie aufgefordert, einen Port zum anhören zu erhalten. Es gibt ein liklihood, das Sie Port 443 auswählen können, aber wenn auf diesem Computer Skype for Business Server 2019 installiert ist oder Skype for Business Server 2019 darauf installiert ist, müssen Sie eine andere Portnummer auswählen.
> 
>Warum ist das der Fall? Wenn Windows Admin Center 2019 auf Port 443 ausgeführt wird, können Sie keine Verbindung mit dem Server über das Skype Control Panel für Unternehmen herstellen, und Sie können keine Verbindung mit einem internen Webdienst herstellen, der auf dem Server ausgeführt wird (Adressbuch-Webdienst , AutoErmittlungsdienst, WebTICKET-Dienst usw.).  Tatsächlich können Sie keine Verbindung mit einer internen Webdienst-URL herstellen. Bitte wählen Sie einen anderen Port aus, falls Sie das Windows Admin Center 2019 auf einem Server mit Skype for Business Server 2019 installieren möchten.
> 

  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2019-deployment"></a>Software, die vor der Bereitstellung von Skype for Business Server 2019 installiert werden soll
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für einen Server installieren oder konfigurieren müssen, auf dem Skype for Business Server 2019 ausgeführt wird. Diese sind nachfolgend aufgeführt, gefolgt von zusätzlichen Anforderungen für bestimmte Serverrollen.
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Auf allen Skype for Business Server-Servern muss Windows PowerShell 3.0 installiert sein.  <br/> • Dieser sollte standardmäßig mit Windows Server 2016 installiert werden.<br/> |
|Microsoft .NET Framework  <br/> |WCF-Dienste ist ein **Feature** , das als Windows-Feature installiert ist, und unter **Server-Manager**zunächst keine Downloads erforderlich sind. <br/> • Wenn Sie diese Funktion installieren oder wenn die Funktion bereits installiert ist und Sie sie überprüfen möchten, müssen Sie sicherstellen, dass wie in dieser Abbildung auch die Option **HTTP-Aktivierung** aktiviert und installiert ist: <br/> ![Screenshot mit HTTP-Aktivierungsoption unter den .NET Framework 4.5-Features](../../SfbServer/media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Machen Sie sich keine Sorgen, wenn ein zusätzliches Popup-Fenster angezeigt wird und Sie darüber informiert, dass für die HTTP-Aktivierung noch andere Komponenten installiert werden müssen. Das ist normal; Klicken Sie auf OK, und gehen Sie weiter. Wenn Sie dieses Popup nicht erhalten, können Sie davon ausgehen, dass diese Dinge bereits installiert sind und weiter gehen.  <br/> Microsoft .NET Framework wird normalerweise installiert, wenn Windows Server 2016 installiert ist. Skype for Business Server erfordert zwar Microsoft .NET Framework 4,7, Sie müssen es also wahrscheinlich aktualisieren. Sie können das Update [hier](https://support.microsoft.com/en-us/help/3186497/the-net-framework-4-7-offline-installer-for-windows/) finden.<br/> |
|Media Foundation  <br/> |Bei Windows Server 2016 wird die Windows Media-Format Laufzeit mit Microsoft Media Foundation installiert.  <br/> Alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, benötigen die Windows Media-Format-Laufzeitkomponente, damit die WMA-Dateien (Windows Media Audio) ausgeführt werden können. Über diese Dateien geben die Anwendungen für das Parken von Anrufen, für Ankündigungen und für Reaktionsgruppen Ankündigungen und Musik wieder.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3,5, um Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2019 zu unterstützen.  <br/> • Für Windows Server 2016 müssen Sie nichts herunterladen. Öffnen Sie den **Server-Manager** und rufen Sie den **Assistenten zum Hinzufügen von Rollen und Features** auf. **Windows Identity Foundation 3.5** wird unter dem Abschnitt **Funktionen** aufgelistet. Wenn diese Option ausgewählt ist, sind Sie gut. Wählen Sie andernfalls die Option aus, und klicken Sie auf **weiter** , um die Schaltfläche **Installieren** zu erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Für Front-End-Server und Standard Edition-Server benötigen Sie außerdem Folgendes:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (Internet Information Services, IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition-Servern benötigt. Dabei müssen die folgenden Module ausgewählt sein:  <br/> • Gemeinsam genutzte HTTP-Features: Standarddokument, HTTP-Fehler, Statischer Inhalt  <br/> • Systemzustand und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Authentifizierung über Clientzertifikatzuordnung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET-Erweiterbarkeit 3.5, .NET-Erweiterbarkeit 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI-Erweiterungen, ISAPI-Filter  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -tools  <br/> Beachten Sie, dass auch anonymer Zugriff erforderlich ist, aber Sie erhalten dies, wenn Sie IIS installieren, sodass Sie keinen Ort haben, um ihn in der Liste auszuwählen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016 müssen Sie das Feature **Media Foundation** im **Server-Manager**installieren. Sie können Ihre Skype for Business Server 2019-Installation zwar ohne diese starten, aber Sie werden aufgefordert, Sie zu installieren und den Server dann neu zu starten, bevor die Installation von Skype for Business Server 2019 fortgesetzt wird. Es ist besser, es vor der Zeit zu tun. <br/> |
|Silverlight  <br/> |[Hier](https://www.microsoft.com/silverlight/)können Sie die neueste Silverlight-Version installieren.  <br/> |
   
Wir zeigen Ihnen nun das Beispiel eines PowerShell-Skripts, um dies zu automatisieren:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, Telnet-Client, BITS, ManagementOData, Web-Mgmt-Console, Web-Metabase, Web-Lgcy-Mgmt-Console, Web-Lgcy-Scripting, Web-WMI, Web-Scripting-Tools, Web-Mgmt-Service
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

## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2019"></a>Back-End-Datenbanken, die mit Skype for Business Server 2019 funktionieren
<a name="DBs"> </a>

Bei der Installation von Skype for Business Server 2019 Standard Edition haben Sie SQL Server 2016 Express (64-Bit Edition).

Für Skype for Business Server 2019 Enterprise Edition ist vollständiger SQL Server erforderlich, wie unten angegeben (nur 64-Bit-Edition; Bitte verwenden Sie keine 32-Bit-Editionen):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2019 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |Microsoft SQL Server 2017 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausgeführt werden.  <br/> |
Microsoft SQL Server 2016 (64-Bit-Edition), und Sie müssen mit den neuesten Updates ausgeführt werden.|
 |

Wenn die von Ihnen gewünschte SQL Server-Edition nicht aufgeführt wird, können Sie sie nicht verwenden.
  
> [!NOTE]
> Sie müssen auch SQL Server Reporting Services für die Monitoring Server-Rolle installieren. 
  
### <a name="sql-clustering-and-sql-always-on"></a>SQL-Clustering und SQL Always on

SQL-Clustering mit Skype for Business Server 2019 wird unterstützt. Wenn Sie SQL-Clustering einrichten möchten, erfolgt dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL Clustering verfügen, die unterstützt wird. Teilen Sie den passiven Knoten mit keiner anderen SQL-Instanz.
  
Für das Failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten.
- Microsoft SQL Server 2017 Standard (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten.
- Microsoft SQL Server 2016 Standard (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten.

Sechzehn Knoten:
  
- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten.
- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten.
- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition), und wir empfehlen, mit dem neuesten Service Pack zu starten.

SQL Always on wird unterstützt, und weitere Informationen dazu finden Sie unter [Back-End-Server-Höchstverfügbarkeit in Skype for Business Server 2019](../../SfbServer/plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).
  

###  <a name="additional-server-installation-recommendations"></a>Weitere Empfehlungen zur Server Installation:
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Clientsoftware oder andere Winsock-Mehrschicht-Dienstanbietersoftware auf Ihren Front-End-Servern oder eigenständigen Vermittlungsservern. Dies schließt auch sämtliche Drittanbieterfirewalls oder Antiviren-Netzwerkinspektionssoftware ein. Bei der Installation dieser Software wurde die Leistung des Medien Verkehrs schlechter angezeigt.
  

## <a name="active-directory"></a>Active Directory
<a name="AD"> </a>

Obwohl viele Konfigurationsdaten für Server und Dienste im Skype for Business Server 2019 Central-Verwaltungsspeicher gespeichert sind, gibt es noch einige Dinge, die in Active Directory gespeichert sind:
  
|**Active Directory-Objekte**|**Objekttypen**|
|:-----|:-----|
|Schemaerweiterungen  <br/> |Benutzerobjekterweiterungen  <br/> |
||Erweiterungen für Skype for Business Server 2015 und lync Server 2013, um die Abwärtskompatibilität mit den vorherigen unterstützten Versionen zu gewährleisten  <br/> |
|Daten  <br/> |Der Benutzer-SIP-URI und andere Einstellungen  <br/> |
||Kontaktobjekte für Anwendungen (wie die reaktionsgruppenanwendung und die Anwendung Conferencing Attendant)  <br/> |
||Aus Gründen der Abwärtskompatibilität veröffentlichte Daten  <br/> |
||Einen Dienst Kontrollpunkt (Service Control Point, SCP) für den zentralen Verwaltungsspeicher  <br/> |
||Kerberos-Authentifizierungs Konto (ein optionales Computerobjekt)  <br/> |
   
### <a name="os-for-domain-controllers"></a>Betriebssysteme für Domänencontroller

Die folgenden Domänen Controller-Betriebssysteme können verwendet werden:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Die Domänenfunktionsebene jeder Domäne, in der Sie Skype for Business Server 2019 bereitstellen, und die Gesamtstrukturfunktionsebene einer beliebigen Gesamtstruktur, in die Sie Skype for Business Server 2019 einbringen, müssen eine der folgenden sein:
  
- Windows Server 2019

- Windows Server 2016
    
- Windows Server 2012 R2
    
- Windows Server 2012
    
Dürfen in diesen Umgebungen schreibgeschützte Domänencontroller vorhanden sein? Sicher, solange auch schreibbare Domänencontroller verfügbar sind.
  
Es ist wichtig zu wissen, dass Skype for Business Server 2019 keine Single-Labeling-Domains unterstützt. Was ist das? Wenn Sie über eine Stammdomäne mit der Bezeichnung "contoso. local" verfügen, wird das in Ordnung sein. Wenn Sie über eine Stammdomäne verfügen, die nur den Namen local hat, wird dies nicht funktionieren und wird daher nicht unterstützt. Ein wenig mehr dazu wurde [in diesem Knowledge Base-Artikel](https://support.microsoft.com/kb/300684/en-us)geschrieben.
  
Skype for Business Server 2019 unterstützt auch keine Umbenennung von Domänen. Wenn Sie Ihre Domäne wirklich umbenennen müssen, müssen Sie Skype for Business Server 2019 deinstallieren, die Domäne umbenennen und dann Skype for Business Server 2019 erneut installieren.
  
Schließlich handelt es sich möglicherweise um eine Domäne mit einer gesperrten AD DS-Umgebung, und das ist in Ordnung. Wir haben weitere Informationen dazu, wie Sie Skype for Business Server 2019 in einer gesperrten AD DS-Umgebung in der Bereitstellungsdokumentation bereitstellen können.
  
### <a name="ad-topologies"></a>AD-Topologien

Unterstützte Topologien in Skype for Business Server 2019 sind:
  
- Einzelne Gesamtstruktur mit einzelner Domäne
    
- Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen
    
- Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces
    
- Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur
    
- Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie mit Exchange Online
    
- Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
    
Wir verfügen über Diagramme und Beschreibungen, mit denen Sie ermitteln können, welche Topologie in Ihrer Umgebung vorhanden ist, oder was Sie vor der Installation von Skype for Business Server 2019 einrichten müssen. Um es einfach zu halten, werden wir auch einen Schlüssel einbeziehen:
  
![Schlüssel zu den Symbolen, die für Skype for Business-Topologiediagramme verwendet werden](../../SfbServer/media/cc0dbc17-cf81-4b79-bf99-4614cc6828a0.png)
  
#### <a name="single-forest-with-single-domain"></a>Einzelne Gesamtstruktur mit einzelner Domäne

![Diagramm einer einzelnen Active-Directory-Gesamtstruktur mit einer einzigen Domäne](../../SfbServer/media/24921a0b-3a3e-4bad-8427-49300e2e3f7a.png)
  
Einfacher geht es nicht. Es handelt sich um eine einzelne Domänengesamtstruktur, eine gemeinsame Topologie.
  
#### <a name="single-forest-with-a-single-tree-and-multiple-domains"></a>Einzelne Gesamtstruktur mit einer Struktur und mehreren Domänen

![Diagramm mit einer einzigen Gesamtstruktur, einer einzelnen Struktur und mehreren Domänen](../../SfbServer/media/63b9f0dd-6bac-4ba9-ae68-8be032d09dcb.png)
  
Dieses Diagramm zeigt erneut eine einzelne Gesamtstruktur, es gibt aber auch eine oder mehrere untergeordnete Domänen (in diesem konkreten Beispiel gibt es drei). Die Domäne, in der die Benutzer erstellt werden, unterscheidet sich möglicherweise von der Domäne, in der Skype for Business Server 2019 bereitgestellt wird. Warum sollten Sie sich Sorgen machen? Beachten Sie, dass bei der Bereitstellungeines Skype for Business Server-Front-End-Pools alle Server in diesem Pool eine einzige Domäne aufweisen müssen. Sie können über eine domänenübergreifende Verwaltung über die Skype for Business Server-Unterstützung von Windows universelle Administratorgruppen verfügen.
  
Im obigen Diagramm können Sie sehen, dass Benutzer aus einer Domäne in der Lage sind, auf Skype for Business Server-Pools aus der gleichen Domäne oder aus unterschiedlichen Domänen zuzugreifen, selbst wenn diese Benutzer in einer untergeordneten Domäne sind.
  
#### <a name="single-forest-with-multiple-trees-and-disjoint-namespaces"></a>Einzelne Gesamtstruktur mit mehreren Strukturen und nicht zusammenhängenden Namespaces

![Diagramm mit einer einzigen Gesamtstruktur, mehreren Strukturen und getrennten Namespaces](../../SfbServer/media/5ede77a1-f5d2-499c-a2c8-d02f3c2f7cd7.png)
  
Sie haben möglicherweise eine ähnliche Topologie wie in diesem Diagramm, in der Sie über eine Gesamtstruktur verfügen, aber innerhalb dieser Gesamtstruktur mehrere Domänen mit separaten AD-Namespaces sind. In diesem Fall ist dieses Diagramm eine gute Illustration, da es Benutzer in drei verschiedenen Domänen umfasst, die auf Skype for Business Server 2019 zugreifen. Durchgezogene Linien weisen darauf hin, dass Sie in ihrer eigenen Domäne auf einen Skype for Business-Server Pool zugreifen, während eine gestrichelte Linie angibt, dass Sie in einer anderen Struktur zu einem Pool wechseln.
  
Wie Sie sehen können, können Benutzer in der gleichen Domäne, derselben Struktur oder sogar einer anderen Struktur erfolgreich auf Pools zugreifen.
  
#### <a name="multiple-forests-in-a-central-forest-topology"></a>Mehrere Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit zentraler Gesamtstruktur](../../SfbServer/media/fec40746-4254-4c84-86b9-aad4a616ea2f.png)
  
Skype for Business Server 2019 unterstützt mehrere Gesamtstrukturen, die in einer zentralen Gesamtstrukturtopologie konfiguriert sind. Wenn Sie nicht sicher sind, was Sie haben, verwendet die zentrale Gesamtstruktur in der Topologie Objekte, um Benutzer in den anderen Gesamtstrukturen darzustellen, und hostet Benutzerkonten für alle Benutzer in der Gesamtstruktur.
  
Wie funktioniert das? Mit einem Verzeichnis Synchronisierungs Produkt (wie Forefront Identity Manager oder FIM) werden die Benutzerkonten Ihrer Organisation während der gesamten Existenz verwaltet. Wenn ein Konto erstellt oder in der Gesamtstruktur gelöscht wird, wird diese Änderung im entsprechenden Kontakt in der zentralen Gesamtstruktur synchronisiert.
  
Wenn Ihre Anzeigen Infrastruktur vorhanden ist, ist das Verschieben zu dieser Topologie möglicherweise nicht einfach, aber wenn Sie bereits vorhanden sind oder Ihre Gesamtstruktur Infrastruktur noch planen, kann dies eine gute Wahl sein. Sie können Ihre Skype for Business Server 2019-Bereitstellung in einer einzigen Gesamtstruktur zentralisieren, während Benutzer in jeder Gesamtstruktur suchen, kommunizieren und die Anwesenheit anderer Benutzer anzeigen können. Alle Benutzer Kontakt Updates werden automatisch mit der Synchronisierungssoftware verarbeitet.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie
<a name="BKMK_multipleforestopology"> </a>

![Diagramm mit mehreren Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur](../../SfbServer/media/41efa3b6-d9e6-47df-992b-fefcfc39a80d.png)
  
Eine Ressourcengesamtstrukturtopologie wird ebenfalls unterstützt. Hier wird eine Gesamtstruktur für die Ausführung ihrer Serveranwendungen wie Microsoft Exchange Server und Skype for Business Server 2019 bereitgestellt. Diese Ressourcengesamtstrukturen hosten auch eine synchronisierte Darstellung von aktiven Benutzerobjekten, jedoch keine Anmelde fähigen Benutzerkonten. Die Ressourcengesamtstruktur ist also eine Umgebung mit freigegebenen Diensten für andere Gesamtstrukturen, in der sich die Benutzerobjekte befinden, und Sie verfügen über eine Vertrauensstellung auf Gesamtstrukturebene mit der Ressourcengesamtstruktur.
  
Beachten Sie, dass Exchange Server in derselben Ressourcengesamtstruktur wie Skype for Business Server oder in einer anderen Gesamtstruktur bereitgestellt werden kann.
  
Zur Bereitstellung von Skype for Business Server 2019 in dieser Art von Topologie erstellen Sie für jedes Benutzerkonto in den Benutzergesamtstrukturen ein deaktiviertes Benutzerobjekt in der Ressourcengesamtstruktur (wenn sich Microsoft Exchange Server bereits in der Umgebung befindet, ist dies möglicherweise für Sie erledigt). Dann benötigen Sie ein Verzeichnissynchronisierungstool (wie Forefront Identity Manager oder FIM), um Benutzerkonten über ihren Lebenszyklus zu verwalten.
  
#### <a name="multiple-forests-in-a-skype-for-business-resource-forest-topology-with-exchange-online"></a>Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie mit Exchange Online
<a name="BKMK_multipleforestopology"> </a>

Diese Topologie ähnelt der Topologie, die unter [Mehrere Gesamtstrukturen in einer Skype for Business-Ressourcengesamtstruktur-Topologie](system-requirements.md#BKMK_multipleforestopology) beschrieben wird.
  
In dieser Topologie gibt es eine oder mehrere Benutzergesamtstrukturen, und Skype for Business Server wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt. Exchange Server kann lokal in derselben Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt und für hybride mit Exchange Online konfiguriert werden, oder e-Mail-Dienste können ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden. Für diese Topologie steht kein Diagramm zur Verfügung.
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-skype-for-business-online-and-azure-active-directory-connect"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business Online und Azure Active Directory Connect
<a name="BKMK_multipleforestopology"> </a>

![Zeigt zwei AD-Gesamtstrukturen, eine Benutzergesamtstruktur und eine Ressourcengesamtstruktur an. Die beiden Gesamtstrukturen haben eine Vertrauensstellung und sind mit Office 365 unter Verwendung von Azure AD Connect synchronisiert. Alle Benutzer sind für Skype for Business über Office 365 aktiviert.](../../SfbServer/media/6d54558d-8786-4ebf-90f6-55ae3fdb5ae7.jpg)
  
Bei diesem Szenario sind mehrere lokale Gesamtstrukturen mit einer Topologie mit Ressourcengesamtstruktur vorhanden. Zwischen den Active Directory-Gesamtstrukturen besteht eine vollständige Vertrauensstellung. Das Tool „Azure Active Directory Connect“ wird zur Synchronisierung von Konten zwischen den lokalen Benutzergesamtstrukturen und Office 365 verwendet.
  
 Die Organisation verfügt auch über Office 365 und verwendet [Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) , um Ihre lokalen Konten mit Office 365 zu synchronisieren. Benutzer, die für Skype for Business aktiviert sind, werden über Office 365 und Skype for Business Online aktiviert. Skype for Business Server wird nicht lokal bereitgestellt.
  
Die Authentifizierung für einmaliges Anmelden wird von einer Active Directory-Verbunddienst Farm bereitgestellt, die sich in der Benutzergesamtstruktur befindet.
  
In diesem Szenario wird die Bereitstellung von Exchange lokal, Exchange Online, einer hybriden Exchange-Lösung oder die Bereitstellung von Exchange überhaupt nicht unterstützt. (Das Diagramm zeigt nur lokal Exchange, aber auch die anderen Exchange-Lösungen werden vollständig unterstützt.)
  
#### <a name="multiple-forests-in-a-resource-forest-topology-with-hybrid-skype-for-business"></a>Mehrere Gesamtstrukturen in einer Topologie mit Ressourcengesamtstruktur mit Skype for Business-Hybridbereitstellung
<a name="BKMK_multipleforestopology"> </a>

In diesem Szenario gibt es eine oder mehrere lokale Benutzergesamtstrukturen, und Skype for Business wird in einer dedizierten Ressourcengesamtstruktur bereitgestellt und für den Hybrid Modus mit Skype for Business Online konfiguriert. Exchange Server kann lokal in der gleichen Ressourcengesamtstruktur oder in einer anderen Gesamtstruktur bereitgestellt werden und kann für hybride mit Exchange Online konfiguriert werden. Alternativ können e-Mail-Dienste ausschließlich von Exchange Online für die lokalen Konten bereitgestellt werden.
  
Weitere Informationen finden Sie unter [Konfigurieren einer Multi-Forest-Umgebung für Hybrid-Skype for Business](../../SfbServer/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/configure-a-multi-forest-environment-for-hybrid.md).
  
## <a name="domain-name-system-dns"></a>DNS (Domain Name System)
<a name="DNS"> </a>

Skype for Business Server 2019 erfordert DNS, und zwar aus folgenden Gründen:
  
- DNS ermöglicht es Skype for Business Server 2019, interne Server oder Pools zu erkennen, was eine Server-zu-Server-Kommunikation ermöglicht.
    
- Mit DNS können Clientcomputer den Front-End-Pool oder Standard Edition-Server ermitteln, der für SIP-Transaktionen verwendet wird.
    
- Es ordnet einfache URLs für Konferenzen den Servern zu, auf denen diese Konferenzen gehostet werden.
    
- DNS ermöglicht es externen Benutzern und Clientcomputern, eine Verbindung mit Ihren Edge-Servern oder dem HTTP-Reverseproxy für Sofortnachrichten (im) oder Konferenzen herzustellen.
    
- Mit dieser Option können Unified Communications (UC)-Geräte, die nicht angemeldet sind, den Front-End-Pool oder den Standard Edition-Server ermitteln, auf dem der Geräte Update-Webdienst ausgeführt wird, um Updates zu erhalten und Protokolle zu senden.
    
- Die Verwendung von DNS ermöglicht mobilen Clients die automatische Ermittlung von Webdienstressourcen, ohne dass Benutzer in den Geräteeinstellungen manuell URLs eingeben müssen.
    
- Sie wird im DNS-Lastenausgleich verwendet.
    
Es ist wichtig zu beachten, dass Skype for Business Server 2019 keine Internationalisierungs Domänennamen (IDNs) unterstützt.
  
Und es ist äußerst wichtig, daran zu erinnern, dass jeder Name in DNS mit dem Computernamen identisch ist, der auf jedem Server konfiguriert ist, der von Skype for Business Server 2019 verwendet wird. Insbesondere können wir keine Kurznamen in der Umgebung haben und FQDNs für den Topologie-Generator aufweisen.
  
Dies scheint so zu sein, als wäre es für jeden Computer, der bereits einer Domäne beigetreten ist, logisch, doch wenn Sie über einen Edgeserver verfügen, der nicht zu Ihrer Domäne gehört, ist möglicherweise ein Standardname mit einem kurzen Namen ohne Domänensuffix vorhanden. Stellen Sie sicher, dass dies nicht der Fall ist, entweder in DNS oder auf dem Edgeserver oder einem beliebigen Skype for Business Server 2019-Server oder-Pool.
  
Verwenden Sie definitiv keine Unicode-Zeichen oder Unterstriche. Standard Zeichen (die a-z, a-z, 0-9 und Bindestriche sind) werden von externen DNS-und öffentlichen Zertifizierungsstellen unterstützt (Sie müssen dem SN im Zertifikat FQDNs zuweisen, es ist wichtig, sich daran zu erinnern), damit Sie sich selbst eine Menge Ärger ersparen, wenn Sie den Namen angeben. in diesem Sinn von Anfang an.
  
Weitere Informationen zu den DNS-Anforderungen für Networking entnehmen Sie dem Abschnitt [Networking](../../SfbServer/plan-your-deployment/network-requirements/network-requirements.md) unserer Planungsdokumentation.
  
## <a name="certificates"></a>Zertifikate
<a name="Certs"> </a>

Stellen Sie vor der Bereitstellung unbedingt sicher, dass Ihre Zertifikate in Ordnung sind. Skype for Business Server 2019 benötigt eine Public Key-Infrastruktur (PKI) für Transport Layer Security (TLS) und MTLS-Verbindungen (Mutual Transport Layer Security). Um in standardisierter Weise sicher zu kommunizieren, verwendet Skype for Business Server Zertifikate, die von Zertifizierungsstellen ausgestellt wurden.
  
Dies sind einige der Dinge, für die Skype for Business Server 2019 Zertifikate verwendet:
  
- TLS-Verbindungen zwischen Client und Server
    
- MTLS-Verbindungen zwischen Servern
    
- Föderation mithilfe der automatischen DNS-Ermittlung von Partnern
    
- Zugriff von Remotebenutzern auf Sofortnachrichten
    
- Zugriff externer Benutzer auf AV-Sitzungen, Anwendungsfreigabe und Konferenzen
    
- Unterhaltungen mit Webanwendungen und Outlook Web Access (OWA)
    
Daher ist die Zertifikatplanung ein muss. Sehen wir uns nun eine Liste mit einigen der Dinge an, die Sie beim Anfordern von Zertifikaten beachten müssen:
  
- Alle Serverzertifikate müssen die Serverautorisierung (Enhanced Key Usage [EKU], erweiterte Schlüsselverwendung für Server) unterstützen.
    
- Alle Serverzertifikate müssen einen Zertifikatsperrlisten-Verteilungspunkt unterstützen.
    
- Alle Zertifikate müssen mithilfe eines Signaturalgorithmus signiert werden, der vom Betriebssystem unterstützt wird. Skype for Business Server 2019 unterstützt die SHA-1-und SHA-2-Suite von Digest-Größen (224, 256, 384 und 512-Bit) und erfüllt oder überschreitet die Anforderungen des Betriebssystems.
    
- Die automatische Registrierung wird für interne Server unterstützt, auf denen Skype for Business Server 2019 ausgeführt wird.
    
- Die automatische Registrierung wird für Skype for Business Server 2019 Edge-Server nicht unterstützt.
    
> [!NOTE]
> Die Verwendung des Signaturalgorithmus RSASSA-PSS wird nicht unterstützt und kann unter anderem zu Fehlern bei der Anmeldung und Problemen mit der Anrufweiterleitung führen.  
  
- Es werden Verschlüsselungsschlüssellängen von 1.024, 2.048 und 4.096 Bit unterstützt. Empfohlen werden Schlüssellängen ab 2.048 Bit.
    
- Der standardmäßige Digest- bzw. Hashsignaturalgorithmus ist RSA. Die Algorithmen ECDH_P256, ECDH_P384 und ECDH_P521 werden ebenfalls unterstützt.
    
Das ist viel zu überlegen, und es gibt verschiedene Komfortstufen, bei denen Zertifikate von einer Zertifizierungsstelle angefordert werden. Nachfolgend finden Sie einige weitere Anleitungen, die Ihnen helfen, Ihre Planung so schmerzlos wie möglich zu gestalten.
  
### <a name="certificates-for-your-internal-servers"></a>Zertifikate für Ihre internen Server

Sie benötigen Zertifikate für die meisten internen Server, und Sie erhalten Sie wahrscheinlich von einer internen Zertifizierungsstelle (eine Zertifizierungsstelle, die sich in Ihrer Domäne befindet). Wenn Sie möchten, können Sie diese Zertifikate von einer externen Zertifizierungsstelle anfordern (eine im Internet). Wenn Sie sich Fragen, zu welcher öffentlichen Zertifizierungsstelle Sie wechseln sollten, sehen Sie sich die Liste der [Unified Communications-Zertifikat Partner](/SkypeForBusiness/certification/services-ssl) an.
  
Außerdem benötigen Sie Zertifikate, wenn Skype for Business Server 2019 mit anderen Anwendungen und Servern wie Microsoft Exchange Server kommuniziert. Dies muss natürlich ein Zertifikat sein, das diese anderen apps und Server auf unterstützte Weise verwenden können. Skype for Business Server 2019 und andere Microsoft-Produkte unterstützen das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung. Wenn Sie daran interessiert sind, haben wir einen zusätzlichen Planungsartikel für OAuth und Skype for Business Server 2019.
  
Skype for Business Server 2019 enthält auch Unterstützung für (ohne erforderlich) Zertifikate, die mit der SHA-256-kryptografischen Hashfunktion signiert wurden. Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, muss das externe Zertifikat von einer öffentlichen Zertifizierungsstelle unter Verwendung von SHA-256 ausgestellt werden.
  
Um die Dinge unkompliziert zu halten, haben wir die Zertifikatanforderungen für Standard Edition-Server, Front-End-Pools und andere Rollen in den folgenden Tabellen zusammengestellt, wobei die fiktiven contoso.com-Beispiele verwendet werden (wahrscheinlich verwenden Sie etwas anderes für Ihre Umgebung). Hierbei handelt es sich um alle standardmäßigen Webserverzertifikate mit privaten Schlüsseln, die nicht exportierbar sind. Weitere Hinweise:
  
- Die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server wird automatisch konfiguriert, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.
    
- Der Anzeigename jedes Zertifikats muss im Computerspeicher eindeutig sein.
    
- Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie gemäß den folgenden Beispiel Namen zum alternativen Namen (Subject Name, San) des Zertifikats hinzugefügt werden.
    
Zertifikate für Standard Edition-Server:
  
|**Zertifikat**|**Name des Antragstellers/gebräuchlicher Name**|**Alternativer Antragstellername**|**Beispiel**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.  <br/> |Auf Standard Edition-Servern entspricht der Server-FQDN dem FQDN des Pools.  <br/> Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (entspricht dem FQDN des Servers)  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = SE01. contoso. com; San =\*. contoso.com  <br/> |Sie können den internen Web-FQDN im Topologie-Generator nicht außer Kraft setzen.  <br/> Wenn Sie über mehrere einfache URLs verfügen, müssen Sie alle als Sans angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Einfache URLs pro SIP-Domäne erfüllen  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = SE01. contoso. com; San = webcon01. contoso. com; San =\*. contoso.com  <br/> |Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für Front-End-Server in einem Front-End-Pool:
  
|**Zertifikat**|**Name des Antragstellers/gebräuchlicher Name**|**Alternativer Antragstellername**|**Beispiel**|**Anmerkungen**|
|:-----|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools und FQDN des Servers  <br/> Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.  <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).  <br/> |SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com   <br/> Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.  <br/> |Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.  <br/> Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.  <br/> |
|Web, intern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (der nicht mit dem FQDN des Servers identisch ist)  <br/> • Server-FQDN  <br/> • Skype for Business-Pool-FQDN  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = ee01. contoso. com; San =\*. contoso.com  <br/> |Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
|Web, extern  <br/> |FQDN des Pools  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = ee01. contoso. com; San = webcon01. contoso. com; San =\*. contoso.com  <br/> |Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.  <br/> Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.  <br/> |
   
Zertifikate für den Direktor:
  
|**Zertifikat**|**Name des Antragstellers/gebräuchlicher Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |Directorpool  <br/> |FQDN des Directors, FQDN des Director-Pools.  <br/> Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für SIP. sipdomain (für jede SIP-Domäne, die Sie haben).  <br/> |pool.contoso.com; SAN=dir01.contoso.com   <br/> Wenn dieser Director-Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch San = SIP. contoso. com; San = SIP. fabrikam. com  <br/> |
|Web, intern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Interner Web-FQDN (entspricht dem FQDN des Servers)  <br/> • Server-FQDN  <br/> • Skype for Business-Pool-FQDN  <br/> UND  <br/> • Einfache URLs erfüllen  <br/> • Einfache URL für Einwahl  <br/> • Einfache Administrator-URL  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = dir01. contoso. com San =\*. contoso.com  <br/> |
|Web, extern  <br/> |FQDN des Servers  <br/> |Jeder der folgenden:  <br/> • Externer Web-FQDN  <br/> UND  <br/> • Einfache URLs pro SIP-Domäne erfüllen  <br/> • Einfache URL für Einwahl  <br/> ODER  <br/> • Ein Platzhaltereintrag für die einfachen URLs  <br/> |Der FQDN des Director External Web muss vom Front-End-Pool oder Front-End-Server abweichen.  <br/> SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com  <br/> Mit einem Platzhalterzertifikat:  <br/> SN = dir01. contoso. com; San = directorwebcon01. contoso. com San =\*. contoso.com  <br/> |
   
Zertifikate für eigenständigen Vermittlungs Server:
  
|**Zertifikat**|**Name des Antragstellers/gebräuchlicher Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN des Pools  <br/> |FQDN des Pools  <br/> FQDN des Poolmitgliedsservers  <br/> |SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net  <br/> |
   
Zertifikate für Survivable Branch Appliance (insbesondere Survivable Branch Appliance 2015 für Skype for Business Server 2019):
  
|**Zertifikat**|**Name des Antragstellers/gebräuchlicher Name**|**Alternativer Antragstellername**|**Beispiel**|
|:-----|:-----|:-----|:-----|
|Standard  <br/> |FQDN der Anwendung  <br/> |SIP. \<sipdomain\> (Sie benötigen nur einen Eintrag pro SIP-Domäne)  <br/> |SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com  <br/> |
   
### <a name="certificates-for-external-user-access-edge"></a>Zertifikate für den Zugriff externer Benutzer (Edge)

Skype for Business Server 2019 unterstützt die Verwendung eines **einzigen öffentlichen Zertifikats** für Access-und Webkonferenz-Edge-externe Schnittstellen sowie den a/V-Authentifizierungsdienst, der alle über die Edgeserver (s) bereitgestellt wird. Ihre Edge-interne Schnittstelle verwendet normalerweise ein privates Zertifikat, das von ihrer internen Zertifizierungsstelle ausgestellt wurde, Sie können aber auch ein öffentliches Zertifikat verwenden, wenn es von einer vertrauenswürdigen Zertifizierungsstelle ist.
  
Ihr Reverseproxy (RP) wird ebenfalls ein öffentliches Zertifikat verwenden und es verschlüsselt die Kommunikation zwischen Ihrem Reverseproxy und den Clients sowie zwischen dem Reverseproxy und den internen Servern mithilfe von HTTP (oder präziser: TLS über HTTP).
  
### <a name="certificates-for-mobility"></a>Zertifikate für Mobilität

Wenn Sie Mobilität bereitstellen und die automatische Ermittlung für mobile Clients unterstützen, müssen Sie für Ihre Zertifikate einige zusätzliche Alternative Namen Einträge für Subjekte hinzufügen, um die sicheren Verbindungen von den mobilen Clients zu unterstützen.
  
Sie benötigen San-Namen für die automatische Erkennung für die folgenden Zertifikate:
  
- Directorpool
    
- Front-End-Pool
    
- Reverseproxy
    
Die Einzelheiten sind in den folgenden Tabellen aufgeführt.
  
Hier ist eine kleine Vorplanung gut, aber manchmal haben Sie Skype for Business Server 2019 bereitgestellt, ohne dass Sie Mobilität bereitstellen möchten, und das wird später, wenn Sie bereits über Zertifikate in Ihrer Umgebung verfügen. Eine erneute Veröffentlichung über eine interne Zertifizierungsstelle ist in der Regel ziemlich einfach, aber mit öffentlichen Zertifikaten einer öffentlichen Zertifizierungsstelle, die etwas teurer sein kann.
  
Wenn Sie dies sehen, und wenn Sie über viele SIP-Domänen verfügen (wodurch das Hinzufügen von Sans teurer wird), können Sie Ihren Reverse-Proxy so konfigurieren, dass er http für die anfängliche AutoErmittlungsdienst Anforderung verwendet, anstatt HTTPS zu verwenden (Dies ist die Standardeinstellung Konfiguration). Im Artikel [Plan für Mobilität](../../SfbServer/plan-your-deployment/mobility.md) finden Sie weitere Informationen dazu.
  
Zertifikatanforderungen für Director Pool und Front-End-Pool:
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|Interne URL des AutoErmittlungsdiensts  <br/> |San = lyncdiscoverinternal. \<sipdomain\>  <br/> |
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover. \<sipdomain\>  <br/> |
   
Sie können auch San =\*verwenden. \<sipdomain\>
  
Reverseproxy-Zertifikatsanforderungen (öffentliche ZS):
  
|**Beschreibung**|**SAN-Eintrag**|
|:-----|:-----|
|URL des externen AutoErmittlungsdiensts  <br/> |San = lyncdiscover. \<sipdomain\>  <br/> |
   
Dieser SAN muss dem Zertifikat zugewiesen werden, das dem SSL-Listener (Secure Sockets Layer) auf dem Reverseproxy zugewiesen ist.
  
> [!NOTE]
> Ihr Reverse Proxy-Listener wird Sans für Ihre externen Webdienste-URL (s) haben. Einige Beispiele sind San = skypewebextpool01. contoso. com und dirwebexternal.contoso.com, wenn Sie den Director bereitgestellt haben (Dies ist optional). 
  
## <a name="file-share"></a>Dateifreigabe
<a name="Fileshare"> </a>

Skype for Business Server 2019 kann dieselbe Dateifreigabe für alle Dateispeicher verwenden. Beachten Sie bitte Folgendes:
  
- Eine Dateifreigabe muss sich entweder auf DAS (Direct Attached Storage) oder auf einem SAN (Storage Area Network) befinden, einschließlich des DFS (Distributed File System) sowie von RAID-Komponenten (Redundant Array of Independent Disks) für Dateispeicher. Weitere Informationen zu DFS für Windows Server 2012 finden Sie auf [dieser DFS-Seite](https://technet.microsoft.com/en-us/library/jj127250.aspx).
    
- Wir empfehlen einen freigegebenen Cluster für die Dateifreigabe. Wenn Sie eine verwenden, sollten Sie Windows Server 2012 oder Windows Server 2012 R2 gruppieren. Warum die neuesten Windows-Version? Ältere Versionen verfügen möglicherweise nicht über die erforderlichen Berechtigungen, um alle Features zu aktivieren. Sie können die Clusterverwaltung verwenden, um die Dateifreigaben zu erstellen, und dieses [Erstellen eines Cluster](https://support.microsoft.com/en-us/help/224967) -KB-Artikels wird Ihnen bei diesen Details helfen.
    
> [!CAUTION]
> Beachten Sie, dass Network Attached Storage (NAS) als Dateifreigabe nicht unterstützt wird. Verwenden Sie daher eine der oben genannten Optionen. 
  








