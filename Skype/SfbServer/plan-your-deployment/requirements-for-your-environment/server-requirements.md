---
title: Serveranforderungen für Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: Bereiten Sie Ihre Server von Skype for Business Server 2015 mit diesem Thema vor. Mithilfe von Hardware, Betriebssystem, Datenbank, Software und den Systemvoraussetzungen und -empfehlungen können Sie eine erfolgreiche Installation und Bereitstellung Ihrer Server-Farm garantieren.
ms.openlocfilehash: dfcde40c8084279dca39e830a84ad6e9631530dd
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Serveranforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Server von Skype for Business Server 2015 mit diesem Thema vor. Mithilfe von Hardware, Betriebssystem, Datenbank, Software und den Systemvoraussetzungen und -empfehlungen können Sie eine erfolgreiche Installation und Bereitstellung Ihrer Server-Farm garantieren.
  
Wie Sie vielleicht schon erwartet haben, sind vor dem Beginn der Bereitstellung von  einige Vorkehrungen zu treffen. Dieser Artikel führt Sie durch die Planung für folgende Arbeitsschritte:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype for Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden muss](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nachdem Sie jetzt Ihre Topologie heruntergefahren haben (falls Sie dies noch nicht getan haben, können Sie im Thema [](../../plan-your-deployment/topology-basics/topology-basics.md) nachlesen), müssen Sie sich um die Server kümmern. Skype for Business Server 2015 servers will require 64-bit hardware. Im Folgenden können Sie sich unsere Empfehlungen für die Hardware ansehen. Zwar handelt es sich dabei nicht um Anforderungen, aber die Empfehlungen reflektieren die Anforderungen, die für eine optimale Leistung notwendig sind. Wir bieten Ihnen eine Dokumentation zur Kapazitätsplanung, mit der Sie bestimmen können, ob Sie je nach Ihrer Situation Weiteres benötigen.
  
Recommended hardware for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz.  <br/> Intel Itanium processors are not supported for Skype for Business Server 2015 roles.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dual or multi-homed configurations are **not** supported for Front End Servers, Back End Servers, Standard Edition servers, and Persistent Chat Servers. <br/> So lange sie nicht für das Betriebssystem zur Verfügung stehen und zum Überwachen und Verwalten der Server-Hardware verwendet werden, können Sie über Out-Of-Band-Verwaltungssysteme wie DRAC oder ILO verfügen. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.<br/> |
   
Recommended hardware for Edge Servers, standalone Mediation Servers, Video Interop Servers, and Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Vierkern, mindestens 2,26 GHz  <br/> Intel Itanium processors are not supported for Skype for Business Server 2015 roles.  <br/> |
|Arbeitsspeicher  <br/> |16 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (die Festplatten sollten in einer 2x-RAID-1-Konfiguration sein).  <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 4 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Duale oder Multihoming-Konfigurationen werden nicht für  und  unterstützt. <br/> Edgeserver erfordern zwei Netzwerkschnittstellen, die aus Dual-Port-Netzwerkadaptern bestehen, mit mindestens 1 GBit/s (oder zwei gepaarte Netzwerkadapter, also insgesamt vier; jedes Paar muss mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden, um insgesamt zwei Paare zu erhalten).  <br/> Auf einem eigenständigen  wird die Installation von zusätzlichen NICs zwecks Konfiguration einer spezifischen PSTN-IP-Adresse unterstützt.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype for Business Server 2015
<a name="OS"> </a>

Nachdem Sie die Hardware eingerichtet haben, müssen Sie die Betriebssysteme installieren. Im Folgenden werden die Betriebssysteme aufgeführt, die eine erfolgreiche Installation und Verwendung von  ermöglichen.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 Datacenter OS with all required updates installed.  <br/> |Windows Server 2012 R2 Standard OS with all required updates installed.  <br/> |
| Datacenter-Betriebssystem mit allen erforderlichen Updates installiert.  <br/> | Standard-Betriebssystem mit allen erforderlichen Updates installiert.  <br/> |
   
Alle nicht aufgeführten Betriebssysteme arbeiten nicht ordnungsgemäß. Versuchen Sie daher nicht, diese für neue Installationen von  zu installieren.
  
> [!NOTE]
> Sie werden bemerkt haben, dass Windows Server 2008 R2 nicht in der Liste aufgeführt wird. Wir empfehlen stattdessen Windows Server 2012 R2 für alle neuen Server, die für SFB verwendet werden sollen. Sie sollten Windows Server 2008 R2 nur dann verwenden, wenn Sie bereits Server mit Lync Server 2013 installiert haben und versuchen möchten, ein direktes Update durchzuführen. Windows Server 2008 R2 hat am 13.01.2015 das Ende seines Supportlebenszyklus erreicht. 
  
Zusätzlich zum neuesten Service Pack sollten Sie gegebenenfalls sicherstellen, dass die folgenden Updates installiert werden:
  
- Für Windows Server 2012 sollte KB-Artikel 2858668 installiert werden, bevor ein Upgrade durchgeführt wird. [Get it here](https://support.microsoft.com/en-us/kb/2858668/).
    
- Wenn Sie Windows Server 2012 R2 verwenden, installieren Sie vor dem Upgrade KB-Artikel 2982006. [It's found here](https://support.microsoft.com/en-us/kb/2982006/).
    
- Wenn Sie ein Upgrade auf einer Windows Server 2008 R2-Box durchführen (siehe Anmerkung oben), sollten Sie vorher KB-Artikel 2533623 installieren. [It's at this link](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren
<a name="DBs"> </a>

When installing Skype for Business Server 2015 Standard Edition, you'll have SQL Server 2014 Express (64-bit edition) is automatically installed as well.
  
Skype for Business Server 2015 Enterprise Edition is a little more complicated, but the supported list is below (everything is 64-bit edition, you'll notice, please don't use 32-bit editions):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 Enterprise (64-bit edition), and you must run with Cumulative Update 6 or later ([download Cumulative Update 6](https://support.microsoft.com/en-us/kb/3031047/)).  <br/> | Enterprise (64-Bit-Edition) – das neueste Service Pack wird empfohlen.  <br/> | Enterprise (64-Bit-Edition) – das neueste Service Pack wird empfohlen.  <br/> |
| Standard (64-Bit-Edition), Ausführung mit kumulativem Update 6 oder neuer ( Cumulative update package 6 for SQL Server 2014 https://support.microsoft.com/de-de/kb/3031047/ ).  <br/> | Standard (64-Bit-Edition) – das neueste Service Pack wird empfohlen.  <br/> |Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.  <br/> |
   
Wenn die von Ihnen gewünschte -Edition nicht aufgeführt wird, können Sie sie nicht verwenden.
  
> [!NOTE]
> Sie müssen auch die SQL Server Reporting Services für die Monitoring Server-Role installieren, aber Sie müssen wissen, dass diese Aufgabe mit SQL Always On erst Post-RTM unterstützt sein wird. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL-Spiegelung, SQL-Clustering und SQL AlwaysOn

You are able to use SQL Mirroring or SQL Clustering with Skype for Business Server 2015, it's supported. SQL Mirroring's set up through the Skype for Business Server Topology Builder. If you're intent on setting up SQL Clustering, that's done in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL-Clustering verfügen, da nur diese Variante unterstützt wird. Teilen Sie den passiven Knoten mit keiner anderen SQL-Instanz.
  
Für das Failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
-  Standard (64-Bit-Edition) – das neueste Service Pack wird empfohlen.
    
-   Standard (64-Bit-Edition) – das neueste Service Pack wird empfohlen.
    
- Microsoft SQL Server 2008 R2 Standard (64-Bit-Version). Darüber hinaus wird das neueste Service Pack empfohlen.
    
Sechzehn Knoten:
  
-  Enterprise (64-Bit-Edition) – das neueste Service Pack wird empfohlen.
    
-  Enterprise (64-Bit-Edition) – das neueste Service Pack wird empfohlen.
    
-  Enterprise (64-Bit-Edition) – das neueste Service Pack wird empfohlen.
    
> [!IMPORTANT]
> Für das Upgrade sollten Sie sicherstellen, dass Sie auf Ihren n mindestens das SP1 für  installiert haben, bevor Sie ein Upgrade durchführen. [Hier finden Sie den Linkhttps://www.microsoft.com/de-de/download/details.aspx?id=35575](https://www.microsoft.com/en-us/download/details.aspx?id=35575), um das SP1 direkt herunterzuladen.
  
Falls Sie mehr über die SQL-Spiegelung lesen möchten, bieten wir Ihnen ein Thema zu einer hohen Verfügbarkeit bei Back-End-Servern in  an. Configure SQL Server clustering for Skype for Business Server 2015 has the steps for getting clustering ready. There are also further links on failover clustering for SQL, for [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx), and [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Neu in dieser Version ist der Support von SQL AlwaysOn. It is supported, and you can read more about it in the [Back End Server high availability in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) topic.
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden muss
<a name="Software"> </a>

There are some things you're going to need to install or configure for any server running Skype for Business Server 2015, and they're listed below. After that are additional requirements for specific server roles.
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |All Skype for Business Server servers need Windows PowerShell 3.0 installed.  <br/> • If you're doing the installation on Windows Server 2012 or Windows Server 2012 R2, you're set, because it's already there.  <br/> • If you're doing an upgrade on Windows Server 2008 R2, you can download the [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) to get it. <br/> Nachdem Sie dort die korrekte PowerShell installiert haben, überprüfen Sie, ob ihre BuildVersion 6.2.9200.0 oder neuer ist, indem Sie zur PowerShell-Eingabeaufforderung wechseln und `$PSVersionTable` eingeben. Dadurch erhalten Sie die gewünschten Informationen.  <br/> |
|Microsoft .NET Framework  <br/> |Die WCF-Dienste sind als Funktion von  unter Server-Manager installiert. Sie müssen nichts herunterladen. <br/> • Wenn Sie diese Funktion installieren oder wenn die Funktion bereits installiert ist und Sie sie überprüfen möchten, müssen Sie sicherstellen, dass wie in dieser Abbildung auch die Option **HTTP-Aktivierung** aktiviert und installiert ist: <br/> ![Screenshot showing HTTP Activation option under the .NET Framework 4.5 Features.](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Don't worry if you get an additional pop-up saying some other things need to be installed for HTTP Activation to be installed. Das ist normal, klicken Sie daher einfach auf OK und fahren Sie fort. Wenn dieses Popup-Fenster nicht angezeigt wird, können Sie davon ausgehen, dass diese Komponenten bereits installiert sind, und unbesorgt fortfahren.  <br/> Microsoft .NET Framework is usually installed when Windows Server 2012 R2 or Windows Server 2016 are installed. Skype for Business Server works with the following Microsoft .NET Framework versions:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 (für  CU 5 oder höhere Versionen)  <br/>  .NET Framework 3.5 wurde wahrscheinlich standardmäßig auf Ihrem -Computer installiert (überprüfen Sie dies unbedingt vor dem Upgrade), befindet sich aber nicht auf den Servern unter / (bei neuen Installationen). Um es hinzuzufügen, benötigen Sie den Zugriff auf Ihr Installationslaufwerk oder auf Ihr Installationsmedium (den Ort, von dem aus Sie  installiert haben oder an dem sich die Installationsdateien jetzt befinden). Fahren Sie dann fort und installieren Sie es als eine Funktion des Server-Manager und geben Sie den Installationspfad zum Installationsmedium an (besonders den Ordner **\sources\sxs**), wenn Sie danach gefragt werden, und fahren Sie mit der Installation fort. <br/> |
|Media Foundation  <br/> |For Windows Server 2016, Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.  <br/> Alle  und , die für Konferenzen verwendet werden, benötigen die Windows Media-Format-Laufzeitkomponente, um die WMA-Dateien (Windows Media Audio) auszuführen. Über diese Dateien geben die Anwendungen für das Parken von Anrufen, für Ankündigungen und für Reaktionsgruppen Ankündigungen und Musik wieder.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5 für die Unterstützung von Szenarien mit Server-zu-Server-Authentifizierung für .  <br/> • For Windows Server 2012 and Windows Server 2012 R2, there's no need to download anything. Öffnen Sie den **Server-Manager** und rufen Sie den **Assistenten zum Hinzufügen von Rollen und Features** auf. **Windows Identity Foundation 3.5** wird unter dem Abschnitt **Funktionen** aufgelistet. Wenn es aktiviert ist, ist alles so weit in Ordnung. Andernfalls müssen Sie es auswählen und auf „Weiter“ klicken, um zur Schaltfläche **Installieren** zu gelangen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Front End Servers and Standard Edition server also need:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (Internet Information Services, IIS)  <br/> |IIS wird auf allen n sowie auf allen n mit den folgenden ausgewählten Modulen benötigt:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, Statischer Inhalt  <br/> • Systemzustand und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Authentifizierung über Clientzertifikatzuordnung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET-Erweiterbarkeit 3.5, .NET-Erweiterbarkeit 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI-Erweiterungen, ISAPI-Filter  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -tools  <br/> Außerdem weisen wir darauf hin, dass ein anonymer Zugriff notwendig ist, aber diesen erhalten Sie, wenn Sie IIS installieren. Daher sehen Sie auf der Liste keine Auswahlmöglichkeit dafür.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | For Windows Server 2016, Windows Server 2012, and Windows Server 2012 R2, you'll need to install the **Media Foundation** feature in **Server Manager**. Sie können die -Installation auch ohne diese Funktion starten, aber Sie werden aufgefordert, sie zu installieren und den Server neu zu starten, bevor die -Installation fortgeführt wird. Es empfiehlt sich daher, dies rechtzeitig zu tun. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight unter [diesem Linkhttps://www.microsoft.com/silverlight/](https://www.microsoft.com/silverlight/) installieren.  <br/> |
   
> [!NOTE] 
> You may also need to enable Directory Browsing if you are using a load balancer. Otherwise a blank page will load which the load balancer might consider a failure. 

Wir zeigen Ihnen nun das Beispiel eines PowerShell-Skripts, um dies zu automatisieren:

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht Quelldateien in einer spezifischen Reihenfolge. Wenn eine Verbindung mit dem Internet besteht, greift der Befehl auf Windows Update zu. Ohne Verbindung mit dem Internet müssen Sie dafür sorgen, dass alle Quelldateien für den Befehl zur Verfügung stehen. For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.

 **Directors also need:**
  
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
    
  - • .NET 3.5
    
  - • .NET 4.5
    
  - ISAPI-Erweiterung
    
  - ISAPI-Filter
    
(Es ist das selbe Modulset wie für die n und die n, nur ohne Komprimierung dynamischer Inhalte und Verwaltungstools.)
  
Außerdem finden Sie dazu hier PowerShell-Code:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Persistent Chat Servers also need:**
  
Message Queuing, auch MSMQ genannt. Dies ist eine -Komponente und Sie können sie unter dem Features-Abschnitt im Server-Manager installieren. Falls Sie mehr dazu erfahren möchten, lesen Sie den Abschnitt [Installieren und Verwalten von Message Queuinghttps://technet.microsoft.com/de-de/library/cc771474.aspx](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Abschließend sei Folgendes gesagt:**
  
Installieren Sie keine -Clientsoftware oder andere Winsock-Mehrschicht-Dienstanbietersoftware auf Ihren Front-End-Servern oder eigenständigen Vermittlungsservern. Dies schließt auch alle Drittanbieterfirewalls oder Antiviren-Netzwerkinspektionssoftware ein. Poor media traffic performance has been seen when that software's installed.
  

