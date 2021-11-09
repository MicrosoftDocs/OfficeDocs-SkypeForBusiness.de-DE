---
title: Serveranforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Zusammenfassung: Bereiten Sie Ihre Skype for Business Server 2015-Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sind hier aufgeführt, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.'
ms.openlocfilehash: f12dcd955f044e626deda5e8e21fec00e53b876c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860952"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Serveranforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Skype for Business Server 2015-Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen sind hier aufgeführt, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.

Wenn Sie nach Umgebungsanforderungen wie Active Directory, DNS oder Zertifikaten suchen, können Sie sich die [Umgebungsanforderungen für Skype for Business Server 2015-Dokument](environmental-requirements.md) ansehen.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2015 beginnen. Dieser Artikel führt Sie durch die Planung für Folgendes:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype for Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nun, da Ihre Topologie nicht mehr verfügbar ist (und Wenn Sie dies nicht tun, können Sie sich die [Topologiegrundlagen für Skype for Business Server 2015-Thema](../../plan-your-deployment/topology-basics/topology-basics.md) ansehen), ist es an der Zeit, über Server nachzudenken. Skype for Business Server 2015-Server benötigen 64-Bit-Hardware. Unsere Empfehlungen für Hardware finden Sie unten. Dies sind keine Anforderungen, aber sie spiegeln die Anforderungen wider, die für eine optimale Leistung erforderlich sind. Wir verfügen über eine Dokumentation zur Kapazitätsplanung, mit der Sie je nach Ihren Umständen ermitteln können, ob Sie mehr benötigen.
  
Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition server und Server für beständigen Chat:
  
|Hardwarekomponente|Empfohlen|
|:-----|:-----|
|CPU   |64-Bit-Dualprozessor, Hex-Core, 2,26 GHz oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.   |
|Arbeitsspeicher   |32 Gigabyte (GB).   |
|Datenträger   |ENTWEDER:  <br/> • 8 oder mehr Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (zwei der Festplatten mit RAID 1 und 6 mit RAID 10).  <br/> OR  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 1.0000 U/min bereitstellen können.   |
|Netzwerk   |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse zusammengeführt werden).  <br/> Duale konfigurationen oder Konfigurationen mit mehreren Verwalteten werden für Front-End-Server, Back-End-Server, Standard Edition server und Server für beständigen Chat **nicht** unterstützt. <br/> Solange sie nicht für das Betriebssystem verfügbar gemacht werden und zum Überwachen und Verwalten der Serverhardware verwendet werden, können Sie über Out-of-Band-Verwaltungssysteme wie DRAC oder CSV verfügen. Dieses Szenario stellt keinen Server mit mehreren Verwalteten dar und wird unterstützt.   |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver, Video-Interoperabilitätsserver und Directors:
  
|Hardwarekomponente|Empfohlen|
|:-----|:-----|
|CPU   |64-Bit-Dualprozessor, Vierkern, 2,26 GHz oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.   |
|Arbeitsspeicher   |16 Gigabyte.   |
|Datenträger   |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten in einer 2x RAID 1-Konfiguration vorhanden sein).  <br/> OR  <br/> • SSDs (Solid State Drives), die den gleichen freien Speicherplatz und eine ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 1.000 U/min bereitstellen können.   |
|Netzwerk   |1 Dualport-Netzwerkadapter, 1 GBit/s oder höher (2 Netzwerkadapter können verwendet werden, sie müssen jedoch mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse zusammengeführt werden).  <br/> Duale konfigurationen oder Multi-Homed-Konfigurationen werden für Video-Interoperabilitätsserver und Directors **nicht** unterstützt. <br/> Edgeserver benötigen zwei Netzwerkschnittstellen, bei denen es sich um Dualport-Netzwerkadapter handelt, mindestens 1 GBit/s (oder zwei gekoppelte Netzwerkadapter, insgesamt vier, wobei jedes Paar mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse für insgesamt zwei Paare kombiniert wird).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs) unterstützt, um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen.   |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype for Business Server 2015
<a name="OS"> </a>

Sobald Sie die Hardware eingerichtet haben, müssen Sie Betriebssysteme (BS) installieren. Dies sind das Betriebssystem, mit dem Sie Skype for Business Server 2015 installieren und erfolgreich verwenden können.
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Windows Server 2019 (Sie benötigen Skype for Business kumulatives Update 9 oder höher).  |Windows Server 2016 (Sie benötigen Skype for Business kumulatives Update 5 oder höher. Weitere Informationen finden Sie unter [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))   |
|Windows Server 2012 R2 Datacenter-Betriebssystem mit allen erforderlichen Updates installiert.   |Windows Server 2012 R2 Standard os with all required updates installed.   |
|Windows Server 2012 Datacenter Betriebssystem mit allen erforderlichen Updates installiert.   |Windows Server 2012 Standard Betriebssystem mit allen erforderlichen Updates installiert.   |
   
Wenn sie nicht in dieser Liste enthalten ist, funktioniert sie nicht ordnungsgemäß. Versuchen Sie es bitte nicht für Neuinstallationen von Skype for Business Server 2015.

> [!NOTE]
> Direkte Upgrades des Betriebssystems werden mit Lync Server 2013 nicht unterstützt. Sie müssen einen separaten Pool bereitstellen und Benutzer in den neuen Pool mit einem anderen Betriebssystem migrieren. Alle Server in einem Pool müssen über dieselbe Betriebssystemversion verfügen.
  
> [!NOTE]
> Möglicherweise haben Sie bemerkt, Windows Server 2008 R2 nicht in dieser Liste enthalten ist. Dies liegt daran, dass wir Windows Server 2012 R2 für alle neuen Server empfehlen, die für SFB verwendet werden sollen. Sie sollten Windows Server 2008 R2 nur verwenden, wenn Sie bereits vorhandene Server mit Lync Server 2013 installiert haben und sie direkt aktualisieren möchten. Windows Server 2008 R2 hat am 13.01.2015 das Ende des Mainstream-Supportlebenszyklus erreicht und endet am 14.1.2020.
  
Zusätzlich zum neuesten Service Pack sollten Sie sicherstellen, dass die folgenden Updates installiert sind, sofern sie für Sie relevant sind:
  
- Für Windows Server 2012 sollten KB-Artikel 2858668 vor einem Upgrade installiert werden. [Rufen Sie es hier ab.](https://support.microsoft.com/kb/2858668/)
    
- Wenn Sie über Windows Server 2012 R2 verfügen, installieren Sie den KB-Artikel 2982006 vor dem Upgrade. [Es ist hier zu finden.](https://support.microsoft.com/kb/2982006/)
    
- Wenn Sie ein Upgrade auf einem feld Windows Server 2008 R2 durchführen (siehe Hinweis oben), sollten Sie zuerst den KB-Artikel 2533623 installieren. [Sie befindet sich unter diesem Link.](https://support.microsoft.com/kb/2533623/)
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren
<a name="DBs"> </a>


Bei der Installation von Skype for Business Server 2015-Standard Edition wird SQL Server 2014 Express (64-Bit-Edition) automatisch installiert.
  
Skype for Business Server 2015-Enterprise Edition ist etwas komplizierter, aber die unterstützte Liste befindet sich unten (alles ist 64-Bit-Edition, Sie werden feststellen, bitte verwenden Sie keine 32-Bit-Editionen):
  
|&nbsp;|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.  |Microsoft SQL Server 2017-Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.  |Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit Skype for Business kumulativen Update 7 oder höher ausführen ([laden Sie Skype for Business kumulatives Update herunter).](https://support.microsoft.com/help/3061064)   |Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und Sie müssen mit kumulativem Update 6 oder höher[(kumulatives Update 6 herunterladen)](https://support.microsoft.com/kb/3031047/)ausführen.   |Microsoft SQL Server 2012-Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.   |
|Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.  |Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.  |Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit Skype for Business kumulativen Update 7 oder höher ausführen ([laden Sie Skype for Business kumulative Update herunter).](https://support.microsoft.com/help/3061064)   |Microsoft SQL Server 2014 Standard (64-Bit-Edition), und Sie müssen mit kumulativem Update 6 oder höher[(kumulatives Update 6 herunterladen)](https://support.microsoft.com/kb/3031047/)ausführen.   |Microsoft SQL Server 2012 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.   |
   
Wenn die hier aufgeführte SQL Server Edition, die Sie verwenden möchten, nicht angezeigt wird, können Sie sie nicht verwenden.
  
- Außerdem müssen Sie SQL Server Reporting Services für die Monitoring Server-Rolle installieren.
- Für eine gut verbundene SQL Back-End sollte die Verbindung mit dem Skype for Business Front-End lokal sein und nicht über eine Verbindung mit niedriger Geschwindigkeit. 
- Die Freigabe SQL Back-Ends zwischen zwei oder mehr Pools wird nicht unterstützt.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange-Speicher
Besprechungsinhaltsdateien, z. B. PowerPoint Präsentationen, werden als Anlagen archiviert. Wenn Sie Skype for Business Archivdaten mit Exchange Compliancedaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und sicherstellen, dass die maximale Speichergröße die Speicherung der Besprechungsinhaltsdateien unterstützt. Sie müssen Exchange bereitstellen, bevor Sie die Archivierung mithilfe der Microsoft Exchange-Integrationsoption bereitstellen und aktivieren. 
    
Wenn Sie Exchange Speicher verwenden, müssen Sie keine separaten SQL Server Datenbanken für die Archivierung bereitstellen, es sei denn, Sie verfügen über Skype for Business Benutzer, die nicht auf Ihren Exchange Servern verwaltet werden. Wenn Sie die Archivierung mithilfe der Microsoft Exchange-Integrationsoption bereitstellen, werden Skype for Business Archivdaten mit Exchange Compliancedaten nur für die Benutzer gespeichert, die auf Ihren Exchange Servern verwaltet werden. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
  
Die Archivierung ist keine definierte Serverrolle, Sie müssen keinen separaten Server für die Archivierung installieren. Einheitliche Datensammlungs-Agents werden automatisch auf jedem Enterprise Edition Front-End-Pool und jedem Standard Edition Server installiert und aktiviert. Sie müssen die Archivierungstopologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.
    
Die Archivierung verwendet den Skype for Business Server Dateispeicher für die temporäre Speicherung von Besprechungsinhaltsdateien, sodass Sie keinen separaten Dateispeicher für die Archivierung einrichten.
    
Microsoft Message Queuing ist nicht erforderlich.
    
Sie müssen die Infrastruktur für den Archivierungsspeicher einrichten. Dazu gehört die Auswahl von Exchange oder Archivierungsspeicher mit SQL Server.   Skype for Business Server Die Anforderungen an die Archivierungsinfrastruktur sind mit denen für die Bereitstellung von Skype for Business Server identisch. Ausführliche Informationen finden Sie unter ["Anforderungen für Ihre Skype for Business Umgebung".](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) 
  
> [!NOTE]
> Um Benutzer zu unterstützen, die nicht auf Exchange Servern verwaltet werden, oder wenn Sie die Microsoft Exchange-Integrationsoption nicht verwenden möchten, müssen Sie den Archivierungsspeicher mithilfe einer 64-Bit-SQL Server-Datenbank bereitstellen. 
    
Sie müssen die SQL Server Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren. Wenn das zum Veröffentlichen der Topologie zu verwendende Konto über die entsprechenden Administratorrechte und Berechtigungen verfügt, können Sie die Archivierungsdatenbank (LcsLog) erstellen, wenn Sie Ihre Topologie veröffentlichen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsvorganges enthalten ist. Ausführliche Informationen zu SQL Server finden Sie in der [SQL Server Dokumentation.](/sql/sql-server/)
    
Die Laststeigerung für die Archivierung kann erheblich sein. Daher sollten Sie sicherstellen, dass der Speicherplatz für Front-End-Server ausreicht, auf denen die Archivierung aktiviert ist.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL Spiegelung, SQL Clustering und SQL AlwaysOn

Sie können SQL Spiegelung oder SQL Clustering mit Skype for Business Server 2015 verwenden, wird dies unterstützt. SQL Die Spiegelung wird über den Skype for Business Server Topologie-Generator eingerichtet. Wenn Sie SQL Clustering einrichten möchten, geschieht dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL Clustering verfügen, da dies unterstützt wird. Geben Sie den passiven Knoten nicht für andere SQL Instanz frei.
  
Für Failoverclustering stehen Folgendes zur Auswahl:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2017 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, das neueste Service Pack zu verwenden.

- Microsoft SQL Server 2014 Standard (64-Bit-Edition) und wir empfehlen die Ausführung mit dem neuesten Service Pack.
    
-  Microsoft SQL Server 2012 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack zu verwenden.

16 Knoten:

- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.

- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, das neueste Service Pack zu verwenden.
  
- Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), und wir empfehlen die Ausführung mit dem neuesten Service Pack.

> [!IMPORTANT]
> Beim Upgrade sollten Sie sicherstellen, dass auf Ihren Front-End-Servern mindestens SQL Server 2012 SP1 vor dem Upgrade installiert ist. [Hier ist ein Link](https://www.microsoft.com/download/details.aspx?id=35575) zu SP1, wenn Sie es sofort herunterladen möchten.
  
Wenn Sie mehr über SQL Spiegelung lesen müssen, finden Sie in Skype for Business Server 2015 eine Back-End-Server-Hochverfügbarkeit. Konfigurieren SQL Server Clustering für Skype for Business Server 2015 umfasst die Schritte zum Vorbereiten des Clusterings. Es gibt auch weitere Links zum Failoverclustering für SQL, für [2014,](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) [2012](/previous-versions/sql/sql-server-2012/hh231721(v=sql.110))und [2008.](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105))
  
> [!NOTE]
> Neu in der Version 2015 ist die Unterstützung von SQL AlwaysOn. Es wird unterstützt, und Sie können weitere Informationen dazu im Thema zur hohen Verfügbarkeit von [Back-End-Servern in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) lesen.

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie für jeden Server installieren oder konfigurieren müssen, auf dem Skype for Business Server 2015 ausgeführt wird, und sie sind unten aufgeführt. Danach folgen zusätzliche Anforderungen für bestimmte Serverrollen.

  
 **Alle Server:**
  
|Software/Rolle|Details|
|:-----|:-----|
|Windows PowerShell 3.0   |Alle Skype for Business Server Server müssen Windows PowerShell 3.0 installiert sein.  <br/> • Wenn Sie die Installation auf Windows Server 2012 oder Windows Server 2012 R2 durchführen, sind Sie festgelegt, da sie bereits vorhanden ist.  <br/> • Wenn Sie ein Upgrade auf Windows Server 2008 R2 durchführen, können Sie die [Windows Management Framework 3.0](https://www.microsoft.com/download/details.aspx?id=34595) herunterladen, um sie zu erhalten. <br/> **Tipp:** Sobald Sie die richtige PowerShell aktiviert haben, bestätigen Sie, dass es sich um BuildVersion 6.2.9200.0 oder höher handelt, indem Sie zur PowerShell-Eingabeaufforderung wechseln und `$PSVersionTable` eingeben. Dadurch sollten die benötigten Informationen angezeigt werden.   |
|Microsoft .NET Framework   |WCF-Dienste sind ein **Feature,** das als Windows-Feature unter **Server-Manager** installiert ist, ohne dass Downloads erforderlich sind. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert ist und Sie es aktivieren, dass die **HTTP-Aktivierungsoption** ebenfalls wie folgt aktiviert und installiert ist: <br/> ![Screenshot der HTTP-Aktivierungsoption unter den Features .NET Framework 4.5.](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png) <br/> Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, das besagt, dass einige andere Dinge installiert werden müssen, damit die HTTP-Aktivierung installiert werden kann. Das ist normal, klicken Sie auf "OK", und fahren Sie fort. Wenn Sie dieses Popup nicht erhalten, gehen Sie davon aus, dass diese Elemente bereits installiert sind, und fahren Sie fort.  <br/> Microsoft .NET Framework wird in der Regel installiert, wenn Windows Server 2012 R2 oder Windows Server 2016 installiert sind. Skype for Business Server funktioniert mit den folgenden Microsoft .NET Framework-Versionen:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7.1 (für Skype for Business Server CU 5 oder höher)  <br/> • .NET 4.7.2 (für Skype for Business Server CU 6 oder höher)  <br/>  • .NET 4.8 (für Skype for Business Server CU 9 oder höher) <br/>  .NET Framework 3.5 wird wahrscheinlich standardmäßig auf Ihrem Windows Server 2008 R2-Computer installiert (überprüfen Sie auf jeden Fall, ob Sie sich vor dem Upgrade vergewissern), aber es befindet sich nicht auf Ihren Windows Server 2012/Windows Server 2012 R2-Servern (für Neuinstallationen). Um es hinzuzufügen, benötigen Sie Zugriff auf Ihr Installationslaufwerk oder Medien (den Ort, von dem aus Ihr Windows Server installiert wurde oder wo sich die Installationsdateien jetzt befinden). Installieren Sie es dann als Feature vom Server-Manager, zeigen Sie auf das Installationsmedium (insbesondere den Ordner **\sources\sxs),** wenn Sie dazu aufgefordert werden, und installieren Sie es weiter.  |
|Media Foundation   |Für Windows Server 2016 wird Windows Server 2012 und Windows Server 2012 R2 die Windows Media Format Runtime mit Microsoft Media Foundation installiert.  <br/> Alle Front-End-Server und Standard Edition server, die für Konferenzen verwendet werden, erfordern Windows Media Format Runtime, um die WMA-Dateien (Windows Media Audio) auszuführen, die von den Anwendungen für das Parken von Anrufen, ankündigungen und Reaktionsgruppen für Ankündigungen und Musik wiedergegeben werden.   |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5, um Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2015 zu unterstützen.  <br/> • Für Windows Server 2012 und Windows Server 2012 R2 müssen Sie nichts herunterladen. Öffnen Sie **den Server-Manager,** und wechseln Sie zum Assistenten zum Hinzufügen von **Rollen und Features.** **Windows Identity Foundation 3.5** ist im Abschnitt **"Features"** aufgeführt. Wenn es aktiviert ist, sind Sie gut. Wählen Sie sie andernfalls aus, und klicken Sie auf "Weiter", um die Schaltfläche **"Installieren"** zu erreichen.  |
|Remoteserver-Verwaltungstools   |Rollenverwaltungstools: AD DS- und AD LDS-Tools   |
   
 **Front-End-Server und Standard Edition Server benötigen außerdem Folgendes:**
  
|Software/Rolle|Details|
|:-----|:-----|
|Internetinformationsdienste (IIS)   |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition Servern benötigt, wobei die folgenden Module ausgewählt sind:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Clientzertifikatzuordnungsauthentifizierung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET Extensibility 3.5, .NET Extensibility 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI Extensions, ISAPI Filters  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -Tools  <br/> Wir sollten auch beachten, dass anonymer Zugriff ebenfalls erforderlich ist, aber Sie erhalten dies, wenn Sie IIS installieren, sodass Sie keinen Ort haben, an dem Sie diesen in der Liste auswählen können.   |
|Windows Media Format-Laufzeitkomponente   | Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 müssen Sie das **Media Foundation-Feature** im **Server-Manager** installieren. Jetzt können Sie ihre Skype for Business Server 2015-Installation ohne diese starten. Sie werden jedoch aufgefordert, sie zu installieren und dann den Server neu zu starten, bevor die Skype for Business Server 2015-Installation fortgesetzt wird. Besser, dies im Voraus zu tun.  |
|Silverlight   |Sie können die neueste Version von Silverlight unter [diesem Link](https://www.microsoft.com/silverlight/)installieren.   |
   
> [!NOTE] 
> Möglicherweise müssen Sie auch das Verzeichnisbrowsen aktivieren, wenn Sie einen Lastenausgleich verwenden. Andernfalls wird eine leere Seite geladen, die vom Lastenausgleich möglicherweise als Fehler betrachtet wird. 

Um Ihnen zu helfen, finden Sie hier ein Beispiel für ein PowerShell-Skript, das Sie ausführen können, um dies zu automatisieren:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht in einer bestimmten Reihenfolge nach Quelldateien. Wenn Sie online sind, greift der Befehl auf Windows Update zu. Wenn Sie jedoch offline sind, müssen Sie sicherstellen, dass die Quelldateien für den Befehl verfügbar sind. Weitere Informationen zur Verwendung von PowerShell zum Installieren von Rollen und Features finden Sie unter [Installieren oder Deinstallieren von Rollen, Rollendiensten oder Features.](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831809(v=ws.11)) Vergessen Sie nicht, Windows Update nach der Installation der erforderlichen Komponenten erneut auszuführen, auch wenn Sie den PowerShell-Befehl verwenden.

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
    
(Wenn Sie sich fragen, ist es dasselbe Modul wie die Front-End-Server und Standard Edition-Server, wobei die Tools für die dynamische Inhaltskomprimierung und -verwaltung weggelassen werden.)
  
Dafür haben wir auch folgenden PowerShell-Code:
  
```PowerShell
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Server für beständigen Chat benötigen außerdem Folgendes:**
  
Message Queuing, auch MSMQ genannt. Es handelt sich um eine Windows Serverkomponente, die Sie im Abschnitt "Features" im Server-Manager installieren können. Weitere Informationen hierzu finden Sie unter ["Installieren und Verwalten von Message Queuing".](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771474(v=ws.11))
  
 **Letzte Gedanken:**
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA)-Server-Clientsoftware oder andere Winsock Layered Service Providers (LSP)-Software (Firewalls von Drittanbietern oder Antiviren-Netzwerküberprüfungssoftware wären hier enthalten) auf einem Ihrer Front-End-Server oder eigenständigen Vermittlungsservern. Bei der Installation dieser Software wurde eine schlechte Leistung des Mediendatenverkehrs festgestellt.
