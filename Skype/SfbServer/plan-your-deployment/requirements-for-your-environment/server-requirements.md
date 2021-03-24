---
title: Serveranforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Zusammenfassung: Bereiten Sie Ihre Skype for Business Server 2015-Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.'
ms.openlocfilehash: d1a80fd991b8fe078f2a53d73e7f37eb66903220
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104041"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Serveranforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Skype for Business Server 2015-Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sind hier, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.

Wenn Sie nach Umgebungsanforderungen wie Active Directory, DNS oder Zertifikaten suchen, können Sie sich das Dokument "Umgebungsanforderungen für [Skype for Business Server 2015"](environmental-requirements.md) anschauen.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2015 beginnen. In diesem Artikel werden Sie durch die Planung für Folgendes erläutert:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype for Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nachdem Die Topologie nun nicht mehr verfügbar ist (und wenn sie nicht, können Sie das Thema [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) lesen), ist es an der Zeit, sich Gedanken über Server zu machen. Skype for Business Server 2015-Server benötigen 64-Bit-Hardware. Unsere Empfehlungen für Hardware sind unten aufgeführt. Dies sind keine Anforderungen, aber sie spiegeln die Anforderungen wider, die für eine optimale Leistung erforderlich sind. Wir verfügen über Dokumentation zur Kapazitätsplanung, mit der Sie je nach Ihren Umständen feststellen können, ob Sie mehr als diesen benötigen.
  
Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 8 oder mehr Festplatten mit mindestens 10.000 U/Min. mit mindestens 72 GB freiem Festplattenspeicher (zwei datenträger, die RAID 1 und 6 mit RAID 10 verwenden).  <br/> ODER  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse verbunden sein).  <br/> Dual- oder Multi-Homed-Konfigurationen werden **für** Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat nicht unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar sind und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verfügen. Dieses Szenario stellt keinen server mit mehreren Homed-Servern dar und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver, Video-Interop-Server und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Quad-Core, 2,26 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |16 Gigabyte.  <br/> |
|Datenträger  <br/> |ENTWEDER:  <br/> • 4 oder mehr Festplatten mit 10.000 U/Min. mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten sich in einer 2x RAID 1-Konfiguration befinden).  <br/> ODER  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 10000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse verbunden sein).  <br/> Dual- oder multi-homed-Konfigurationen werden **für** Video-In-Interop-Server und Directors nicht unterstützt. <br/> Für Edgeserver sind zwei Netzwerkschnittstellen erforderlich, bei denen es sich um Netzwerkadapter mit zwei Ports handelt, 1 GBit/s oder höher (oder zwei gekoppelte Netzwerkadapter, für insgesamt vier, bei denen jedes Paar mit einer einzigen MAC-Adresse und einer einzelnen IP-Adresse für insgesamt zwei Paare verbunden ist).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NiCs) unterstützt, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype for Business Server 2015
<a name="OS"> </a>

Nachdem Sie die Hardware installiert haben, müssen Sie Betriebssysteme installieren. Dies sind die Betriebssysteme, mit denen Sie Skype for Business Server 2015 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 (Sie benötigen kumulatives Skype for Business Update 9 oder höher). <br/> |Windows Server 2016 (Sie benötigen kumulatives Skype for Business Update 5 oder höher. Weitere Informationen finden Sie unter [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter OS mit allen erforderlichen Updates installiert.  <br/> |Windows Server 2012 R2 Standardbetriebssystem mit allen erforderlichen Updates installiert.  <br/> |
|Windows Server 2012 Datencenterbetriebssystem mit allen erforderlichen Updates installiert.  <br/> |Windows Server 2012 Standardbetriebssystem mit allen erforderlichen Updates installiert.  <br/> |
   
Wenn es nicht in dieser Liste enthalten ist, funktioniert es nicht ordnungsgemäß, versuchen Sie es nicht für neue Installationen von Skype for Business Server 2015.

> [!NOTE]
> Ein "In-Place"-Upgrade des Betriebssystems wird mit Lync Server 2013 nicht unterstützt. Sie müssen einen separaten Pool bereitstellen und Benutzer mit einem anderen Betriebssystem in den neuen Pool migrieren. Alle Server in einem Pool müssen die gleiche Betriebssystemversion haben.
  
> [!NOTE]
> Möglicherweise haben Sie bemerkt, Windows Server 2008 R2 nicht in dieser Liste enthalten ist. Das liegt daran, dass wir empfehlen, Windows Server 2012 R2 für alle neuen Server für SFB zu verwenden. Sie sollten nur Windows Server 2008 R2 verwenden, wenn Bereitsserver mit Lync Server 2013 bereits installiert sind und Sie beabsichtigen, ein in-place-Upgrade dieser Server zu durchführen. Windows Server 2008 R2 am 13.01.2015 das Ende des allgemeinen Supportlebenszyklus erreicht und das Ende des Supportlebenszyklus am 14.01.2020 erreicht.
  
Zusätzlich zum neuesten Service Pack sollten Sie sicherstellen, dass die folgenden Updates installiert werden, sofern dies für Sie relevant ist:
  
- Für Windows Server 2012 sollte der KB-Artikel 2858668 vor einem Upgrade installiert werden. [Hier erhalten Sie es](https://support.microsoft.com/kb/2858668/).
    
- Wenn Sie R2 Windows Server 2012 haben, installieren Sie vor dem Upgrade den KB-Artikel 2982006. [Sie finden sie hier](https://support.microsoft.com/kb/2982006/).
    
- Wenn Sie ein Upgrade auf ein Windows Server 2008 R2 (siehe hinweis oben) durchführen, sollten Sie zuerst den KB-Artikel 2533623 installieren. [Sie finden sie unter diesem Link](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren
<a name="DBs"> </a>


Bei der Installation von Skype for Business Server 2015 Standard Edition müssen Sie auch SQL Server 2014 Express (64-Bit-Edition) automatisch installiert werden.
  
Skype for Business Server 2015 Enterprise Edition ist etwas komplizierter, aber die unterstützte Liste ist unten aufgeführt (alles ist eine 64-Bit-Edition, Sie werden feststellen, dass Sie keine 32-Bit-Editionen verwenden):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2017 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit kumulativem Skype for Business Update 7 oder höher ([kumulatives Skype for Business-Update](https://support.microsoft.com/help/3061064)herunterladen ) ausführen.  <br/> |Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und Sie müssen mit kumulativem Update 6 oder höher ausführen ([kumulatives Update 6 herunterladen](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.  <br/> |
|Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit kumulativem Skype for Business Update 7 oder höher ([kumulatives Skype for Business-Update](https://support.microsoft.com/help/3061064)herunterladen) ausführen.  <br/> |Microsoft SQL Server 2014 Standard (64-Bit-Edition) und sie müssen mit kumulativem Update 6 oder höher ausgeführt werden ([kumulatives Update 6 herunterladen](https://support.microsoft.com/kb/3031047/)).  <br/> |Microsoft SQL Server 2012 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.  <br/> |
   
Wenn die zu verwendende SQL Server nicht angezeigt wird, können Sie sie nicht verwenden.
  
- Außerdem müssen Sie die Reporting Services SQL Server Monitoring Server-Rolle installieren.
- Bei einem gut verbundenen SQL sollte die Verbindung mit dem Skype for Business-Front-End lokal und nicht über eine Verbindung mit niedriger Geschwindigkeit verbunden sein. 
- Die freigabe SQL back ends zwischen zwei oder mehr Pools wird nicht unterstützt.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange-Speicher
Besprechungsinhaltsdateien, z. B. PowerPoint-Präsentationen, werden als Anlagen archiviert. Wenn Sie Skype for Business-Archivdaten mit Exchange-Kompatibilitätsdaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und sicherstellen, dass die maximale Speichergröße die Speicherung der Besprechungsinhaltsdateien unterstützt. Sie müssen Exchange bereitstellen, bevor Sie die Archivierung mithilfe der Microsoft Exchange-Integrationsoption bereitstellen und aktivieren. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
  
Die Archivierung ist keine definierte Serverrolle, Sie müssen keinen separaten Server für die Archivierung installieren. Unified Data Collection Agents werden automatisch in jedem Enterprise Edition-Front-End-Pool und jedem Standard Edition Server installiert und aktiviert. Sie müssen Ihre Archivierungstopologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.
    
Die Archivierung verwendet den Skype for Business Server-Dateispeicher für die temporäre Speicherung von Besprechungsinhaltsdateien, sodass Sie keinen separaten Dateispeicher für die Archivierung einrichten.
    
Microsoft Message Queuing ist nicht erforderlich.
    
Sie müssen die Infrastruktur für den Archivierungsspeicher einrichten. Dies umfasst die Auswahl von Exchange- oder Archivierungsspeicher mithilfe SQL Server.   Die Anforderungen an die Skype for Business Server-Archivierungsinfrastruktur sind mit der Bereitstellung von Skype for Business Server identisch. Weitere Informationen finden Sie [unter Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Um Benutzer zu unterstützen, die nicht auf Exchange-Servern gespeichert sind, oder wenn Sie die Microsoft Exchange-Integrationsoption nicht verwenden möchten, müssen Sie Archivierungsspeicher mithilfe einer 64-Bit-SQL Server bereitstellen. 
    
Sie müssen die SQL Server vor der Bereitstellung und Aktivierung der Archivierung einrichten. Wenn das Zum Veröffentlichen der Topologie zu verwendende Konto über die entsprechenden Administratorrechte und -berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsverfahrens enthalten ist. Ausführliche Informationen zu SQL Server finden Sie in [der SQL Server Dokumentation](/sql/sql-server/).
    
Die Auslastung für die Archivierung kann erheblich sein. Daher sollten Sie sicherstellen, dass der Speicherplatz für Front-End-Server ausreicht, auf denen die Archivierung aktiviert ist.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Spiegelung, SQL Clustering und SQL Immer ein

Sie können die SQL spiegelung oder SQL Clustering mit Skype for Business Server 2015 verwenden, es wird unterstützt. SQL die Einrichtung der Spiegelung über den Skype for Business Server-Topologie-Generator. Wenn Sie die Einrichtung eines SQL möchten, geschieht dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL verfügen, da dies unterstützt wird. Teilen Sie den passiven Knoten nicht mit anderen SQL Instanz.
  
Für failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, mit dem neuesten Service Pack ausgeführt zu werden.

- Microsoft SQL Server 2014 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
    
-  Microsoft SQL Server 2012 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

Sechzehn Knoten:

- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, mit dem neuesten Service Pack ausgeführt zu werden.
  
- Microsoft SQL Server 2014 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

> [!IMPORTANT]
> Für das Upgrade sollten Sie sicherstellen, dass auf Ihren Front-End-Servern mindestens SQL Server 2012 SP1 vor dem Upgrade installiert ist. [Hier finden Sie einen Link zu](https://www.microsoft.com/download/details.aspx?id=35575) SP1, wenn Sie ihn sofort herunterladen möchten.
  
Wenn Sie mehr über die Spiegelung SQL lesen müssen, haben wir ein Thema zur hohen Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015. Configure SQL Server clustering for Skype for Business Server 2015 has the steps for getting clustering ready. Es gibt auch weitere Links zum Failoverclustering für SQL, für [2014,](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))und [2008](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)).
  
> [!NOTE]
> Neu in der Version 2015 ist die Unterstützung von SQL Always On. Es wird unterstützt, und Weitere Informationen dazu finden Sie im Thema [Back-End Server High Availability in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für jeden Server mit Skype for Business Server 2015 installieren oder konfigurieren müssen, und sie sind unten aufgeführt. Danach sind zusätzliche Anforderungen für bestimmte Serverrollen erforderlich.

  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Alle Skype for Business Server-Server müssen Windows PowerShell 3.0 installiert sein.  <br/> • Wenn Sie die Installation auf Windows Server 2012 oder Windows Server 2012 R2 machen, werden Sie festgelegt, da sie bereits vorhanden ist.  <br/> • Wenn Sie ein Upgrade auf Windows Server 2008 R2 durchführen, können Sie das Windows Management Framework [3.0](https://www.microsoft.com/download/details.aspx?id=34595) herunterladen, um es zu erhalten. <br/> **Tipp:** Sobald Sie die richtige PowerShell dort haben, vergewissern Sie sich, dass es sich um BuildVersion 6.2.9200.0 oder höher oder höher, indem Sie zur PowerShell-Eingabeaufforderung gehen und `$PSVersionTable` eingeben. Dies sollte die benötigten Informationen enthalten.  <br/> |
|Microsoft .NET Framework  <br/> |WCF-Dienste ist ein **Feature,** das als Windows-Feature unter **Dem Server-Manager** installiert ist, ohne dass Downloads erforderlich sind. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert ist und Sie es überprüfen, dass die **Option HTTP-Aktivierung** wie folgt aktiviert und installiert ist: <br/> ![Screenshot der HTTP-Aktivierungsoption unter .NET Framework 4.5-Features. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, in dem sie sagen, dass einige andere Dinge installiert werden müssen, damit die HTTP-Aktivierung installiert werden kann. Das ist normal, klicken Sie auf OK, und gehen Sie weiter. Wenn Sie dieses Popup nicht erhalten, gehen Sie davon aus, dass diese Dinge bereits installiert sind, und gehen Sie weiter.  <br/> Microsoft .NET Framework wird in der Regel installiert, Windows Server 2012 R2 oder Windows Server 2016 installiert sind. Skype for Business Server funktioniert mit den folgenden Microsoft .NET Framework Versionen:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (für Skype for Business Server CU 5 oder höher)  <br/> • .NET 4.7.2 (für Skype for Business Server CU 6 oder höher)  <br/>  • .NET 4.8 (für Skype for Business Server CU 9 oder höher) <br/>  .NET Framework 3.5 wird wahrscheinlich standardmäßig auf Ihrem Windows Server 2008 R2-Computer installiert (vergewissern Sie sich unbedingt vor dem Upgrade), es wird jedoch nicht auf Ihren Windows Server 2012/Windows Server 2012 R2-Servern (bei neuen Installationen) installiert. Zum Hinzufügen benötigen Sie Zugriff auf Das Installationslaufwerk oder die Medien (der Ort, an dem Windows Server installiert wurde oder wo sich die Installationsdateien befinden). Fahren Sie dann fort, und installieren Sie es als Feature vom Server-Manager, zeigen Sie auf das Installationsmedium (insbesondere den **Ordner \sources\sxs),** wenn Sie danach gefragt werden, und fahren Sie mit der Installation fort. <br/> |
|Media Foundation  <br/> |Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.  <br/> Für alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, ist die Windows Media Format Runtime erforderlich, um die Windows Media Audio (WMA)-Dateien ausführen zu können, die von den Anwendungen zum Parken von Anrufen, Ansagen und Reaktionsgruppe für Ansagen und Musik verwendet werden.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5, um Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2015 zu unterstützen.  <br/> • Für Windows Server 2012 und Windows Server 2012 R2 ist kein Download nötig. Öffnen **Sie Den Server-Manager,** und wechseln Sie zum Assistenten zum Hinzufügen **von Rollen und Features.** **Windows Identity Foundation 3.5 ist** im Abschnitt **Features** aufgeführt. Wenn sie aktiviert ist, sind Sie gut. Wählen Sie andernfalls die Option aus, und klicken Sie auf Weiter, um die **Schaltfläche Installieren zu** erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Front-End-Server und Standard Edition-Server benötigen außerdem:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition-Servern benötigt, bei denen die folgenden Module ausgewählt sind:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Statische Inhaltskomprimierung, dynamische Inhaltskomprimierung  <br/> • Sicherheit: Anforderungsfilterung, Clientzertifikatzuordnungsauthentifizierung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -Tools  <br/> Wir sollten auch beachten, dass auch anonymer Zugriff erforderlich ist, aber Sie erhalten dies, wenn Sie IIS installieren, damit Sie keinen Ort haben, um diesen in der Liste auszuwählen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 müssen Sie das **Media Foundation-Feature** im **Server Manager installieren.** Jetzt können Sie ihre Skype for Business Server 2015-Installation ohne diese installation starten, aber Sie werden aufgefordert, sie zu installieren, und dann den Server neu starten, bevor die Skype for Business Server 2015-Installation fortgesetzt wird. Es ist besser, dies im Voraus zu tun. <br/> |
|Silverlight  <br/> |Unter diesem Link können Sie die neueste Version von Silverlight [installieren.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> Möglicherweise müssen Sie das Verzeichnisbrowsing auch aktivieren, wenn Sie einen Lastenausgleich verwenden. Andernfalls wird eine leere Seite geladen, die vom Lastenausgleich als Fehler in Betracht kommt. 

Um Ihnen zu helfen, finden Sie hier ein PowerShell-Beispielskript, das Sie ausführen können, um dies zu automatisieren:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht in einer bestimmten Reihenfolge nach Quelldateien. Wenn Sie online sind, zugrifft der Befehl auf Windows Update. Wenn Sie jedoch offline sind, müssen Sie sicherstellen, dass die Quelldateien für den Befehl verfügbar sind. Weitere Informationen zur Verwendung von PowerShell zum Installieren von Rollen und Features finden Sie unter Installieren oder Deinstallieren von [Rollen, Rollendiensten](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) oder Features Vergessen Sie nicht, Windows Update nach der Installation der erforderlichen Komponenten erneut auszuführen, auch wenn Sie den Befehl PowerShell verwenden.

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Server für beständigen Chat benötigen außerdem:**
  
Message Queuing, das auch MSMQ genannt wird. Es ist eine Windows Server-Komponente, die Sie im Abschnitt Features im Server Manager installieren können. Weitere Informationen finden Sie unter [Installing and Managing Message Queuing](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11)).
  
 **Letzte Gedanken:**
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Clientsoftware oder eine andere Software des Winsock Layered Service Providers (LSP) (Firewalls von Drittanbietern oder Antivirennetzwerkinspektionssoftware wäre hier enthalten) auf einem Ihrer Front-End-Server oder eigenständigen Vermittlungsserver. Bei der Installation dieser Software wurde eine schlechte Mediendatenverkehrleistung gesehen.
