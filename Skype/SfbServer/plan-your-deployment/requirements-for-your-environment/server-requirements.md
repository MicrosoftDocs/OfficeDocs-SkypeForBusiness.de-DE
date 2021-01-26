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
description: 'Zusammenfassung: Bereiten Sie Ihre Skype for Business Server 2015-Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sind hier, um eine erfolgreiche Installation und Bereitstellung der Serverfarm sicherzustellen.'
ms.openlocfilehash: b1e7e37e46d0f3f547ed843ce2510d8445a34267
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832075"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Serveranforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Skype for Business Server 2015-Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sind hier, um eine erfolgreiche Installation und Bereitstellung der Serverfarm sicherzustellen.

Wenn Sie nach Umgebungsanforderungen wie Active Directory, DNS oder Zertifikaten suchen, können Sie die Umgebungsanforderungen für [Skype for Business Server 2015 lesen.](environmental-requirements.md)
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2015 beginnen. In diesem Artikel werden Sie durch die Planung für Folgendes gehen:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype for Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nachdem Ihre Topologie nun nicht mehr verfügbar ist (und wenn Sie dies nicht, können Sie das Thema ["Topology Basics for Skype for Business Server 2015"](../../plan-your-deployment/topology-basics/topology-basics.md) lesen), sollten Sie über Server nachdenken. Skype for Business Server 2015-Server benötigen 64-Bit-Hardware. Unsere Empfehlungen für Hardware sind unten aufgeführt. Dies sind keine Anforderungen, aber sie spiegeln die Anforderungen wider, die für eine optimale Leistung erforderlich sind. Wir verfügen über Dokumentation zur Kapazitätsplanung, mit der Sie je nach Ihren Umständen feststellen können, ob Sie mehr als diesen benötigen.
  
Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Hexadezimalkern, 2,26 GHz oder höher.  <br/> Intel -Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GIGABYTE (GB).  <br/> |
|Datenträger  <br/> |EINE DER BEIDEN:  <br/> • 8 oder mehr Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Festplattenspeicher (zwei der Datenträger mit RAID 1 und 6 mit RAID 10).  <br/> ODER  <br/> • Festkörperlaufwerke (Solid State Drives, SSDs), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8.000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse verbunden werden).  <br/> Dual- oder multi-homed-Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat nicht unterstützt.  <br/> Solange sie nicht für das Betriebssystem verfügbar sind und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie out-of-Band-Verwaltungssysteme wie DRAC oder ILO verwenden. Dieses Szenario stellt keinen Server mit mehreren Homes dar und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver, Video-In-Op-Server und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Vierkern, 2,26 GHz oder höher.  <br/> Intel -Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |16 GIGABYTE.  <br/> |
|Datenträger  <br/> |EINE DER BEIDEN:  <br/> • 4 oder mehr Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (die Datenträger sollten sich in einer 2x RAID 1-Konfiguration befinden).  <br/> ODER  <br/> • Festkörperlaufwerke (Solid State Drives, SSDs), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie 4 mechanische Festplattenlaufwerke mit 10.000 U/min bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse verbunden werden).  <br/> Duale oder multi-homed-Konfigurationen werden **für** Video-Interop-Server und -Directors nicht unterstützt. <br/> Edgeserver benötigen zwei Netzwerkschnittstellen, bei denen es sich um Netzwerkadapter mit zwei Ports handelt, 1 GBit/s oder höher (oder zwei gekoppelte Netzwerkadapter für insgesamt vier Netzwerkadapter, bei denen jedes Paar mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse für insgesamt zwei Paare gekoppelt wird).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NiCs) unterstützt, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype for Business Server 2015
<a name="OS"> </a>

Sobald Sie die Hardware installiert haben, müssen Sie Betriebssysteme installieren. Dies sind die Betriebssysteme, mit denen Sie Skype for Business Server 2015 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 (Sie benötigen skype for Business kumulatives Update 9 oder höher). <br/> |Windows Server 2016 (Sie benötigen skype for Business kumulatives Update 5 oder höher. Weitere Informationen finden Sie unter [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter-Betriebssystem mit allen erforderlichen Updates.  <br/> |Windows Server 2012 R2 Standard os with all required updates installed.  <br/> |
|Windows Server 2012 datencenterbetriebssystem mit allen erforderlichen Updates installiert.  <br/> |Windows Server 2012 Standardbetriebssystem mit allen erforderlichen Updates installiert.  <br/> |
   
Wenn es nicht in dieser Liste enthalten ist, funktioniert es nicht ordnungsgemäß, versuchen Sie es nicht für Neuinstallationen von Skype for Business Server 2015.

> [!NOTE]
> Ein in-Place-Upgrade des Betriebssystems wird mit Lync Server 2013 nicht unterstützt. Sie müssen einen separaten Pool bereitstellen und Benutzer in den neuen Pool mit einem anderen Betriebssystem migrieren. Alle Server in einem Pool müssen dieselbe Betriebssystemversion haben.
  
> [!NOTE]
> Möglicherweise haben Sie bemerkt, Windows Server 2008 R2 nicht in dieser Liste enthalten ist. Das liegt daran, dass wir empfehlen, Windows Server 2012 R2 für alle neuen Server für SFB zu verwenden. Sie sollten nur Windows Server 2008 R2 verwenden, wenn Sie bereits Server mit Lync Server 2013 installiert haben und beabsichtigen, ein in-Place-Upgrade dieser Server zu durchführen. Windows Server 2008 R2 am 13.01.2015 das Ende des gesamten Supportlebenszyklus erreicht und erreicht das Ende des Supportlebenszyklus am 14.01.2020.
  
Zusätzlich zum neuesten Service Pack sollten Sie sicherstellen, dass die folgenden Updates installiert werden, sofern dies für Sie relevant ist:
  
- For Windows Server 2012, KB article 2858668 should be installed before an upgrade. [Hier erhalten Sie es.](https://support.microsoft.com/kb/2858668/)
    
- If you have Windows Server 2012 R2, please install KB article 2982006 before upgrading. [Sie finden sie hier.](https://support.microsoft.com/kb/2982006/)
    
- Wenn Sie ein Upgrade auf einem Windows Server 2008 R2 (siehe hinweis oben) durchführen, sollten Sie zuerst den Artikel 2533623 in KB installieren. [Sie finden sie unter diesem Link.](https://support.microsoft.com/kb/2533623/)
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren
<a name="DBs"> </a>


Bei der Installation von Skype for Business Server 2015 Standard Edition wird auch SQL Server 2014 Express (64-Bit-Edition) automatisch installiert.
  
Skype for Business Server 2015 Enterprise Edition ist etwas komplizierter, aber die unterstützte Liste ist unten aufgeführt (alles ist eine 64-Bit-Edition, Sie werden feststellen, dass Sie keine 32-Bit-Editionen verwenden):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2017 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit dem kumulativen Update 7 oder höher für Skype for Business (kumulatives Update für[Skype for Business](https://support.microsoft.com/help/3061064)herunterladen) ausgeführt werden.  <br/> |Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und Sie müssen mit kumulativem Update 6 oder höher[(kumulatives Update 6 herunterladen) ausgeführt werden.](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.  <br/> |
|Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack. <br/> |Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit dem kumulativen Update 7 oder höher für Skype for Business (kumulatives Update für[Skype for Business](https://support.microsoft.com/help/3061064)herunterladen) ausgeführt werden.  <br/> |Microsoft SQL Server 2014 Standard (64-Bit-Edition) und Sie müssen mit kumulativem Update 6 oder höher[(kumulatives Update 6 herunterladen) ausgeführt werden.](https://support.microsoft.com/kb/3031047/)  <br/> |Microsoft SQL Server 2012 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.  <br/> |
   
Wenn die zu verwendende SQL Server hier nicht aufgeführt ist, können Sie sie nicht verwenden.
  
- Sie müssen auch reporting Services für die Monitoring SQL Server installieren.
- Bei einem gut verbundenen SQL sollte die Verbindung zum Skype for Business-Front-End lokal und nicht über eine Verbindung mit niedriger Geschwindigkeit sein. 
- Die SQL von Back ends zwischen zwei oder mehr Pools wird nicht unterstützt.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange Storage
Besprechungsinhaltsdateien, z. B. PowerPoint-Präsentationen, werden als Anlagen archiviert. Wenn Sie Skype for Business-Archivdaten mit Exchange-Kompatibilitätsdaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und sicherstellen, dass die maximale Speichergröße das Speichern der Besprechungsinhaltsdateien unterstützt. Sie müssen Exchange bereitstellen, bevor Sie die Archivierung mithilfe der Microsoft Exchange-Integrationsoption bereitstellen und aktivieren. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
  
Die Archivierung ist keine definierte Serverrolle, sie müssen keinen separaten Server für die Archivierung installieren. Unified Data Collection Agents werden automatisch in jedem Front-End-Pool der Enterprise Edition und auf jedem Standard Edition-Server installiert und aktiviert. Sie müssen Ihre Archivierungstopologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.
    
Die Archivierung verwendet den Skype for Business Server-Dateispeicher für die temporäre Speicherung von Besprechungsinhaltsdateien, sodass Sie keinen separaten Dateispeicher für die Archivierung einrichten.
    
Microsoft Message Queuing ist nicht erforderlich.
    
Sie müssen die Infrastruktur für den Archivierungsspeicher einrichten. Dies umfasst die Auswahl von Exchange- oder Archivierungsspeicher mithilfe SQL Server.   Die Anforderungen an die Archivierungsinfrastruktur von Skype for Business Server entsprechen den Anforderungen für die Bereitstellung von Skype for Business Server. Weitere Informationen finden Sie unter ["Anforderungen für Ihre Skype for Business-Umgebung".](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Zur Unterstützung von Benutzern, die nicht auf den Exchange-Servern gespeichert sind oder die Microsoft Exchange-Integrationsoption nicht verwenden möchten, müssen Sie den Archivierungsspeicher mithilfe einer 64-Bit-SQL Server bereitstellen. 
    
Sie müssen die SQL Server vor der Bereitstellung und Aktivierung der Archivierung einrichten. Wenn das Zum Veröffentlichen der Topologie zu verwendende Konto über die entsprechenden Administratorrechte und -berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsvorganges enthalten ist. Ausführliche Informationen zu SQL Server finden Sie in der [SQL Server Dokumentation.](https://go.microsoft.com/fwlink/p/?linkID=129045)
    
Die Laststeigerung für die Archivierung kann erheblich sein. Daher sollten Sie sicherstellen, dass der Speicherplatz für Front-End-Server ausreicht, auf denen die Archivierung aktiviert ist.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Spiegelung, SQL Clustering und SQL Immer ein

Sie können die SQL spiegelung oder SQL clustering mit Skype for Business Server 2015 verwenden, dies wird unterstützt. SQL die Spiegelung über den Skype for Business Server-Topologie-Generator eingerichtet. Wenn Sie das Clustering einrichten SQL möchten, geschieht dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine Aktiv/Passiv-Konfiguration für SQL verfügen, da dies unterstützt wird. Geben Sie den passiven Knoten nicht für andere SQL freigeben.
  
Für Failoverclustering kann Folgendes vorhanden sein:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, das neueste Service Pack zu nutzen.

- Microsoft SQL Server 2014 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
    
-  Microsoft SQL Server 2012 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

16 Knoten:

- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, das neueste Service Pack zu nutzen.
  
- Microsoft SQL Server 2014 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

> [!IMPORTANT]
> Für das Upgrade sollten Sie sicherstellen, dass auf ihren Front-End-Servern mindestens SQL Server 2012 SP1 vor dem Upgrade installiert ist. [Hier ist ein Link zu](https://www.microsoft.com/download/details.aspx?id=35575) SP1, wenn Sie es sofort herunterladen möchten.
  
Wenn Sie weitere Informationen zur SQL benötigen, haben wir ein Thema zur hohen Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015. Das SQL Server clustering für Skype for Business Server 2015 hat die Schritte zum Bereiten des Clusterings. Es gibt auch weitere Links zum Failoverclustering für SQL, [für 2014,](https://technet.microsoft.com/library/hh231721.aspx) [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)und [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Neu in der Version 2015 ist die Unterstützung von SQL Always On. Er wird unterstützt, und Weitere Informationen dazu finden Sie im Thema "Hohe Verfügbarkeit des [Back-End-Servers in Skype for Business Server 2015".](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md)

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL-Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für jeden Server installieren oder konfigurieren müssen, auf dem Skype for Business Server 2015 ausgeführt wird, und sie sind unten aufgeführt. Danach sind zusätzliche Anforderungen für bestimmte Serverrollen erforderlich.

  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Alle Skype for Business Server-Server müssen Windows PowerShell 3.0 installiert sein.  <br/> • Wenn Sie die Installation auf Windows Server 2012 oder Windows Server 2012 R2 machen, sind Sie festgelegt, da sie bereits vorhanden ist.  <br/> • Wenn Sie ein Upgrade auf einem Windows Server 2008 R2 durchführen, können Sie Windows Management Framework [3.0](https://www.microsoft.com/download/details.aspx?id=34595) herunterladen, um es zu erhalten. <br/> **Tipp:** Sobald Sie die richtige PowerShell dort haben, vergewissern Sie sich, dass Es BuildVersion 6.2.9200.0 oder höher ist, indem Sie die PowerShell-Eingabeaufforderung und Eingabe `$PSVersionTable` eingeben. Dies sollte die benötigten Informationen enthalten.  <br/> |
|Microsoft .NET Framework  <br/> |Bei den WCF-Diensten handelt es sich um ein **Feature,** das als Windows-Feature unter dem **Server-Manager** installiert wird, ohne dass Downloads erforderlich sind. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert  ist und sie aktiviert ist, dass die Option für die HTTP-Aktivierung wie folgt aktiviert und installiert ist: <br/> ![Screenshot mit der Option "HTTP-Aktivierung" unter den .NET Framework 4.5-Features. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, in dem sie darüber auf dem Weg zur Installation der HTTP-Aktivierung wissen, dass noch andere Dinge installiert werden müssen. Das ist normal, klicken Sie auf "OK", und gehen Sie weiter. Wenn Sie dieses Popup nicht erhalten, gehen Sie davon aus, dass diese Dinge bereits installiert sind, und gehen Sie weiter.  <br/> Microsoft .NET Framework wird normalerweise installiert, wenn Windows Server 2012 R2 oder Windows Server 2016 installiert werden. Skype for Business Server funktioniert mit den folgenden Microsoft .NET Framework-Versionen:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (für Skype for Business Server CU 5 oder höher)  <br/> • .NET 4.7.2 (für Skype for Business Server CU 6 oder höher)  <br/>  • .NET 4.8 (für Skype for Business Server CU 9 oder höher) <br/>  .NET Framework 3.5 wird wahrscheinlich standardmäßig auf Ihrem Windows Server 2008 R2-Computer installiert (überprüfen Sie dies unbedingt vor dem Upgrade), es wird sich jedoch nicht auf Ihren Windows Server 2012/Windows Server 2012 R2-Servern befinden (bei Neuinstallationen). Um es hinzuzufügen, benötigen Sie Zugriff auf Das Installationslaufwerk oder das Installationsmedium (den Ort, von dem aus Windows Server installiert wurde oder wo sich die Installationsdateien jetzt befinden). Installieren Sie es dann als Feature im Server-Manager, zeigen Sie auf das Installationsmedium (insbesondere den Ordner **"\sources\sxs"),** wenn Sie danach gefragt werden, und fahren Sie mit der Installation fort. <br/> |
|Media Foundation  <br/> |Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.  <br/> Für alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, ist die Windows Media Format Runtime erforderlich, um die Windows Media Audio (.wma)-Dateien ausführen zu können, die von den Anwendungen zum Parken von Anrufen, zur Ansage und zur Reaktionsgruppe für Ansagen und Musik verwendet werden.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5, um Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2015 zu unterstützen.  <br/> • Für Windows Server 2012 und Windows Server 2012 R2 muss nichts heruntergeladen werden. Öffnen **Sie den Server-Manager,** und wechseln Sie zum Assistenten zum Hinzufügen **von Rollen und Features.** **Windows Identity Foundation 3.5 wird** im Abschnitt **"Features"** aufgeführt. Wenn sie aktiviert ist, sind Sie gut. Klicken Sie andernfalls auf "Weiter", um die Schaltfläche **"Installieren"** zu erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Front-End-Server und Standard Edition-Server benötigen außerdem:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition-Servern benötigt, und die folgenden Module sind ausgewählt:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Clientzertifikatzuordnungsauthentifizierung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -Tools  <br/> Wir sollten auch beachten, dass auch anonymer Zugriff erforderlich ist, aber Sie erhalten dies, wenn Sie IIS installieren, damit Sie keinen Ort haben, den Sie in der Liste auswählen können.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 müssen Sie das **Media** Foundation-Feature im **Server Manager installieren.** Jetzt können Sie ihre Skype for Business Server 2015-Installation ohne diese starten, aber Sie werden aufgefordert, sie zu installieren und dann den Server neu zu starten, bevor die Skype for Business Server 2015-Installation fortgesetzt wird. Es ist besser, dies im Voraus zu tun. <br/> |
|Silverlight  <br/> |Unter diesem Link können Sie die neueste Version von Silverlight [installieren.](https://www.microsoft.com/silverlight/)  <br/> |
   
> [!NOTE] 
> Wenn Sie einen Lastenausgleich verwenden, müssen Sie möglicherweise auch die Verzeichnissuche aktivieren. Andernfalls wird eine leere Seite geladen, die vom Lastenausgleichssaldo als Fehler in Betracht kommt. 

Um Ihnen zu helfen, finden Sie hier ein Beispiel-PowerShell-Skript, das Sie ausführen können, um dies zu automatisieren:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht in einer bestimmten Reihenfolge nach Quelldateien. Wenn Sie online sind, zugrifft der Befehl auf Windows Update. Wenn Sie jedoch offline sind, müssen Sie sicherstellen, dass die Quelldateien für den Befehl verfügbar sind. Weitere Informationen zur Verwendung von PowerShell zum Installieren von Rollen und Features finden Sie unter "Installieren oder Deinstallieren von [Rollen, Rollendiensten](https://technet.microsoft.com/library/hh831809.aspx) oder Features". Vergessen Sie nicht, Windows Update nach der Installation der erforderlichen Komponenten erneut auszuführen, auch wenn Sie den Befehl "PowerShell" verwenden.

 **Directors benötigen außerdem:**
  
IIS mit den folgenden ausgewählten Modulen:
  
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
    
  - Clientzertifikatszuordnungsauthentifizierung
    
  - Windows-Authentifizierung
    
- Anwendungsentwicklung
    
  - .NET Extensibility 3.5
    
  - .NET-Erweiterbarkeit 4.5
    
  - ASP.NET 3.5
    
  - ASP.NET 4.5
    
  - ERWEITERUNG ISAPI
    
  - ISAPI-Filter
    
(Wenn Sie sich fragen, ist es dasselbe Modul wie die Front-End-Server und Standard Edition-Server, und die Tools für die Komprimierung dynamischer Inhalte und Verwaltungstools sind nicht verfügbar.)
  
Und hier finden Sie auch folgenden PowerShell-Code:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Server für beständigen Chat benötigen außerdem:**
  
Message Queuing, auch MSMQ genannt. Es ist eine Windows Server-Komponente, die Sie im Abschnitt "Features" im Server Manager installieren können. Weitere Informationen finden Sie unter "Installieren und Verwalten von [Message Queuing".](https://technet.microsoft.com/library/cc771474.aspx)
  
 **Letzte Überlegungen:**
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Clientsoftware oder andere Winsock Layered Service Providers (LSP)-Software (hier sind Firewalls oder Antivirennetzwerkinspektionssoftware enthalten) auf Ihren Front-End-Servern oder eigenständigen Vermittlungsservern. Bei der Installation dieser Software wurde eine schlechte Leistung des Mediendatenverkehrs gesehen.
  

