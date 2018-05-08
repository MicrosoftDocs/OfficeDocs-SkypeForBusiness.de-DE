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
description: 'Zusammenfassung: Bereiten Sie Ihrer Skype Business Server 2015 Servern mit diesem Thema vor. Mithilfe von Hardware, Betriebssystem, Datenbank, Software und den Systemvoraussetzungen und -empfehlungen können Sie eine erfolgreiche Installation und Bereitstellung Ihrer Server-Farm garantieren.'
ms.openlocfilehash: dfcde40c8084279dca39e830a84ad6e9631530dd
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Serveranforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Server von Skype for Business Server 2015 mit diesem Thema vor. Mithilfe von Hardware, Betriebssystem, Datenbank, Software und den Systemvoraussetzungen und -empfehlungen können Sie eine erfolgreiche Installation und Bereitstellung Ihrer Server-Farm garantieren.
  
Wie zu erwarten, sind einige vorbereitenden Schritte vor Beginn der Bereitstellung von Skype für Business Server 2015. Dieser Artikel führt Sie durch die Planung für folgende Arbeitsschritte:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype für Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden muss](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nun, dass Ihre Topologie nach unten (und wenn Sie nicht möchten, können Sie die [Topologiegrundlagen Skype für Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) Thema Auschecken), hat er Zeit über Server entspricht. Skype für Business Server 2015 Server ist 64-Bit-Hardware erforderlich. Im Folgenden können Sie sich unsere Empfehlungen für die Hardware ansehen. Sind keine Anforderungen, aber sie die Anforderungen für eine optimale Leistung erforderlichen widerspiegeln. Wir bieten Ihnen eine Dokumentation zur Kapazitätsplanung, mit der Sie bestimmen können, ob Sie je nach Ihrer Situation Weiteres benötigen.
  
Empfohlene Hardware für Front-End-Server, Back-End-Servern, Standard Edition-Servern und Servern für beständigen Chat:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz.  <br/> Intel Itanium-Prozessoren werden für Skype für Business Server 2015 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualmodus oder Multihoming-Konfigurationen werden **nicht** unterstützt für Front-End-Server, Back-End-Servern, Standard Edition-Servern und Servern für beständigen Chat. <br/> So lange sie nicht für das Betriebssystem zur Verfügung stehen und zum Überwachen und Verwalten der Server-Hardware verwendet werden, können Sie über Out-Of-Band-Verwaltungssysteme wie DRAC oder ILO verfügen. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.<br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver, Video Interop-Servern und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Vierkern, mindestens 2,26 GHz  <br/> Intel Itanium-Prozessoren werden für Skype für Business Server 2015 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |16 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (die Festplatten sollten in einer 2x-RAID-1-Konfiguration sein).  <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 4 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualmodus oder Multihoming-Konfigurationen werden **nicht** für Video Interop-Server und Director-Server unterstützt. <br/> Edgeserver erfordern zwei Netzwerkschnittstellen, die aus Dual-Port-Netzwerkadaptern bestehen, mit mindestens 1 GBit/s (oder zwei gepaarte Netzwerkadapter, also insgesamt vier; jedes Paar muss mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden, um insgesamt zwei Paare zu erhalten).  <br/> Vermittlungsserver die Installation von zusätzlichen Netzwerkschnittstellenkarten (NICs), die die Konfiguration einer bestimmten PSTN-IP-Adresse zugelassen wird auf eigenständigen unterstützt.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype für Business Server 2015
<a name="OS"> </a>

Nachdem Sie die Hardware verfügen, müssen Sie die Betriebssysteme (OS) installieren. Hierbei handelt es sich um das Betriebssystem, mit denen Sie zum Installieren und Skype für Business Server 2015 erfolgreich zu verwenden.
  
|||
|:-----|:-----|
|Windows Server 2016  <br/> ||
|Windows Server 2012 R2 Datacenter-Betriebssystem mit allen erforderlichen Updates installiert sind.  <br/> |Windows Server 2012 R2 Standard-Betriebssystem mit allen erforderlichen Updates installiert sind.  <br/> |
|Windows Server 2012 Datacenter-Betriebssystem mit allen erforderlichen Updates installiert sind.  <br/> |Windows Server 2012 Standard-Betriebssystem mit allen erforderlichen Updates installiert sind.  <br/> |
   
Wenn es sich nicht in der Liste aufgeführt ist, nicht ordnungsgemäß funktionsfähig, nicht versuchen Sie es für neue Installationen von Skype für Business Server 2015.
  
> [!NOTE]
> Sie werden bemerkt haben, dass Windows Server 2008 R2 nicht in der Liste aufgeführt wird. Wir empfehlen stattdessen Windows Server 2012 R2 für alle neuen Server, die für SFB verwendet werden sollen. Sie sollten Windows Server 2008 R2 nur dann verwenden, wenn Sie bereits Server mit Lync Server 2013 installiert haben und versuchen möchten, ein direktes Update durchzuführen. Windows Server 2008 R2 hat am 13.01.2015 das Ende seines Supportlebenszyklus erreicht. 
  
Zusätzlich zum neuesten Service Pack sollten Sie gegebenenfalls sicherstellen, dass die folgenden Updates installiert werden:
  
- Für Windows Server 2012 sollte KB-Artikel 2858668 installiert werden, bevor ein Upgrade durchgeführt wird. Sie [erhalten sie hier](https://support.microsoft.com/en-us/kb/2858668/).
    
- Wenn Sie Windows Server 2012 R2 verwenden, installieren Sie vor dem Upgrade KB-Artikel 2982006. [Hier gefunden wird](https://support.microsoft.com/en-us/kb/2982006/).
    
- Wenn Sie ein Upgrade auf einer Windows Server 2008 R2-Box durchführen (siehe Anmerkung oben), sollten Sie vorher KB-Artikel 2533623 installieren. [Unter diesem Link ist](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren
<a name="DBs"> </a>

Wenn Sie Skype Business Server 2015 Standard Edition installieren, müssen Sie SQL Server 2014 Express (64-Bit-Edition) auch automatisch installiert ist.
  
Skype für Business Server 2015 Enterprise Edition ist etwas komplizierter, aber die Liste die unterstützte liegt unter (alles 64-Bit-Version ist, werden Sie bemerken, wenden Sie sich nicht verwenden, 32-Bit-Editionen):
  
||||
|:-----|:-----|:-----|
|Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und Sie müssen mit kumulative Update 6 oder höher ([kumulative Update 6 herunterladen](https://support.microsoft.com/en-us/kb/3031047/)) ausführen.  <br/> |Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.  <br/> |Microsoft SQL Server 2008 R2 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.  <br/> |
|Microsoft SQL Server 2014-Standard (64-Bit-Edition), und Sie müssen mit kumulative Update 6 oder höher ([kumulative Update 6 herunterladen](https://support.microsoft.com/en-us/kb/3031047/)) ausführen.  <br/> |Microsoft SQL Server 2012 Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt.  <br/> |Microsoft SQL Server 2008 R2 Standard (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack  <br/> |
   
Wenn Sie die SQL Server-Edition nicht wird, den, die Sie verwenden möchten angezeigt, die hier aufgeführten, können nicht Sie es verwenden.
  
> [!NOTE]
> Sie nun auch müssen Sie SQL Server Reporting Services für den Monitoring Server-Role zu installieren, aber wir brauchen Sie wissen, dass diese Aufgabe ist nicht mit SQL immer auf bis Post-RTM unterstützt werden müssen. 
  
### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL-Spiegelung, SQL-Clustering und SQL AlwaysOn

Sie können SQL-Spiegelung oder SQL-Clustering mit Skype für Business Server 2015 verwenden, wird unterstützt. SQL-Spiegelung richten Sie über die Skype für Business Server-Topologie-Generator. Wenn Sie zum Einrichten von SQL-Clustering beabsichtigt sind, erfolgt, die in SQL Server.
  
Stellen Sie sicher, dass Sie Aktiv/Passiv-Konfiguration für die SQL-Clustering, verfügen, wie das unterstützten Funktionalität ist. Freigeben von den passiven Knoten nicht für andere SQL-Instanz.
  
Für das Failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
- Microsoft SQL Server 2014-Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt.
    
-  Microsoft SQL Server 2012 Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt.
    
- Microsoft SQL Server 2008 R2 Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt.
    
Sechzehn Knoten:
  
- Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.
    
- Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.
    
- Microsoft SQL Server 2008 R2 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.
    
> [!IMPORTANT]
> Für das Upgrade möchten wir Sie sicherstellen, dass SQL Server 2012 SP1 auf den Front-End-Servern, die Sie mindestens verfügen vor dem Upgrade installiert. [Hier ist eine Verknüpfung](https://www.microsoft.com/en-us/download/details.aspx?id=35575) , auf SP1, wenn Sie es dann sofort herunterladen möchten.
  
Wenn Sie zum Lesen von Informationen zu SQL-Spiegelung müssen, haben wir einen hohen Verfügbarkeit von Back-End-Server in Skype für Business Server 2015 Thema. Konfigurieren von SQL Server-Clustern Skype für Business Server 2015 die Schritte zum Abrufen von clustering bereit ist. Es gibt auch weitere Links auf Failover-Clusterunterstützung für SQL für [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx)und [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Neu in dieser Version ist der Support von SQL AlwaysOn. Es wird unterstützt, und erhalten Sie weitere Informationen im Thema [hohe Verfügbarkeit von Back-End-Server in Skype für Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) .
  
## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden muss
<a name="Software"> </a>

Es gibt einige Dinge, die Sie installieren oder Konfigurieren für Server mit Skype für Business Server 2015 müssen also, und sie sind unten aufgeführt. Nach Ausführung dieses sind zusätzliche Anforderungen für bestimmte Serverrollen.
  
 **Alle Server:**
  
|**Software-Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Alle Skype für Business Server Server benötigen Windows PowerShell 3.0 installiert.  <br/> • Wenn Sie die Installation auf Windows Server 2012 oder Windows Server 2012 R2 gerade tun, sind Sie festgelegt, da er bereits vorhanden ist.  <br/> • Wenn Sie ein Upgrade auf Windows Server 2008 R2 ausführen, können Sie die [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) , um darauf zuzugreifen herunterladen. <br/> **Tipp:** Nachdem Sie die richtige PowerShell dort haben, vergewissern Sie sich, dass es BuildVersion 6.2.9200.0 ist oder höher Aufforderung durch das Aufrufen der PowerShell und eingeben `$PSVersionTable`. Dadurch erhalten Sie die gewünschten Informationen.  <br/> |
|Microsoft .NET Framework  <br/> |WCF-Diensten ist ein **Feature** , das als Windows-Feature, klicken Sie unter **Server-Manager**keine erforderliche Downloads installiert hat. <br/> • Stellen Sie sicher, bei der Installation dieses Feature oder bereits installiert ist und Sie sind, überprüfen, ob die Option **HTTP-Aktivierung** auch überprüft und installiert haben, müssen Sie wie folgt: <br/> ![Screenshot, der unter der Features von .NET Framework 4.5 HTTP-Aktivierung die Option zeigt. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Gedanken, wenn Sie erhalten eine zusätzliche Popup sagen müssen einige weitere Aktionen für HTTP-Aktivierung installiert sein installiert werden. Das ist normal, klicken Sie daher einfach auf OK und fahren Sie fort. Wenn dieses Popup-Fenster nicht angezeigt wird, können Sie davon ausgehen, dass diese Komponenten bereits installiert sind, und unbesorgt fortfahren.  <br/> Microsoft .NET Framework ist standardmäßig installiert, wenn Windows Server 2012 R2 oder Windows Server 2016 installiert sind. Skype für Business Server kann mit den folgenden Microsoft .NET Framework-Versionen verwendet werden:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 (für Skype für Business Server CU 5 oder spätere Versionen)  <br/>  .NET Framework 3.5 wahrscheinlich installiert werden standardmäßig auf dem Computer Windows Server 2008 R2 (auf jeden Fall überprüfen um sicherzustellen, dass vor dem upgrade), wird es aber tatsächlich auf Ihren Windows Server 2012/Windows Server 2012 R2-Servern (für neue Installationen). Wenn es in hinzufügen möchten, benötigen Sie Zugriff auf Ihre Installationslaufwerks oder auf dem Installationsmedium (der Ort Ihrer Windows Server installiert wurde, oder, in dem die Installationsdateien sind nun). Fahren Sie dann fort und installieren Sie es als eine Funktion des Server-Manager und geben Sie den Installationspfad zum Installationsmedium an (besonders den Ordner **\sources\sxs**), wenn Sie danach gefragt werden, und fahren Sie mit der Installation fort. <br/> |
|Media Foundation  <br/> |Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format-Laufzeitkomponente mit Microsoft Media Foundation installiert.  <br/> Alle Front-End-Servern und Standard Edition-Server, die für Konferenzen verwendet erfordern die Windows Media Format-Laufzeitkomponente zum Ausführen der Windows Media Audio (WMA)-Dateien, die die Anwendung zum Parken von Anrufen, Ankündigung und Reaktionsgruppe spielen für Ankündigungen und Musik.  <br/> |
|Windows Identity Foundation  <br/> |Wir brauchen Windows Identity Foundation 3.5 auf Server-zu-Server-Authentifizierungsszenarien für Skype für Business Server 2015 unterstützen.  <br/> • Für Windows Server 2012 und Windows Server 2012 R2 besteht keine Notwendigkeit herunterladen. Öffnen Sie den **Server-Manager** und rufen Sie den **Assistenten zum Hinzufügen von Rollen und Features** auf. **Windows Identity Foundation 3.5** wird unter dem Abschnitt **Funktionen** aufgelistet. Wenn sie aktiviert ist, können Sie eine gute. Andernfalls müssen Sie es auswählen und auf „Weiter“ klicken, um zur Schaltfläche **Installieren** zu gelangen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Front-End-Servern und Standard Edition-Server müssen auch:**
  
|**Software-Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (Internet Information Services, IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie alle Standard Edition-Servern mit den folgenden Modulen ausgewählt benötigt:  <br/> • Allgemeine HTTP-Features: Default Dokument, HTTP-Fehler statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungstools, Tracing  <br/> • Performance: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderung filtern, Clientzertifikatzuordnungs-Authentifizierung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: Erweiterbarkeit der .NET 3.5, Erweiterbarkeit der .NET 4.5, ASP.NET 3.5, ASP.NET 4.5 ISAPI-Erweiterungen ISAPI-Filter  <br/> •-Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und-Tools  <br/> Wir sollten beachten Sie außerdem anonymen Zugriff ist auch erforderlich, aber Sie erhalten, die beim Installieren von IIS, damit Sie keinen Ort, an, die in der Liste auswählen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 müssen Sie das Feature **Media Foundation** im **Server-Manager**zu installieren. Nun, Sie starten tatsächlich können Ihre Skype für die Installation von Business Server 2015 ohne eins, jedoch werden Sie aufgefordert, ihn zu installieren und fährt Neustart den Server, bevor Sie die Skype für Business Server 2015 zu installieren. Es empfiehlt sich daher, dies rechtzeitig zu tun. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight unter [diesem Link](https://www.microsoft.com/silverlight/)installieren.  <br/> |
   
> [!NOTE] 
> Sie müssen auch Verzeichnissuche aktivieren, wenn Sie einen System zum Lastenausgleich verwenden. Andernfalls wird eine leere Seite geladen, die das System zum Lastenausgleich einen Fehler berücksichtigen kann. 

Wir zeigen Ihnen nun das Beispiel eines PowerShell-Skripts, um dies zu automatisieren:

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht nach Quelldateien in einer bestimmten Reihenfolge. Wenn eine Verbindung mit dem Internet besteht, greift der Befehl auf Windows Update zu. Ohne Verbindung mit dem Internet müssen Sie dafür sorgen, dass alle Quelldateien für den Befehl zur Verfügung stehen. Weitere Informationen zum Verwenden von PowerShell zum Installieren der Rollen und Funktionen finden Sie unter [installieren oder Deinstallieren von Rollen, Rollendienste oder Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) vergessen Sie nicht auf Windows Update erneut ausführen nach der Installation der erforderlichen Komponenten, auch wenn Sie den PowerShell-Befehl verwenden.

 **Director-Server müssen auch:**
  
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
    
(Wenn Sie wissen möchten, es ist des gleichen Moduls als Front-End-Servern und Standard Edition-Servern mit Dynamic Content Compression festlegen und Verwaltungstools ausgelassen.)
  
Außerdem finden Sie dazu hier PowerShell-Code:
  
```
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Persistent Chatserver müssen auch:**
  
Message Queuing, auch MSMQ genannt. Es ist eine Komponente von Windows Server, und klicken Sie im Abschnitt Features im Server-Manager installieren. Wenn Sie, um weitere Informationen möchten dazu, Auschecken [Installieren und Verwalten von Message Queuing](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Abschließend sei Folgendes gesagt:**
  
Installieren Sie nicht Microsoft Internet Security and Acceleration (ISA) Server Clientsoftware oder andere Winsock Layered Service Provider (LSP)-Software (alle Firewalls von Drittanbietern oder Antiviren-Software für Prüfung enthalten hier wäre) auf keines der Front-End-Servern oder eigenständigen Vermittlungsserver. Schlechte Media Datenverkehr Leistung wurde bei der Installation von dieser Software des beobachtet.
  

