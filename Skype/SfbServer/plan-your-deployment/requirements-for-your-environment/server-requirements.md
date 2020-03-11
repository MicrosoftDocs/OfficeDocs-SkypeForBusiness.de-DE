---
title: Server Anforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Zusammenfassung: bereiten Sie Ihre Skype for Business Server 2015 Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen stehen zur Verfügung, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.'
ms.openlocfilehash: 9cc063a44924bd6080525ca7a751bd1a3356666c
ms.sourcegitcommit: 543f650ad4aff73bccfe7a60b66fb944b4e3c119
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42572793"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Server Anforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Skype for Business Server 2015 Server mit diesem Thema vor. Hardware, Betriebssystem, Datenbanken, Software, alle Systemanforderungen und Empfehlungen stehen zur Verfügung, um eine erfolgreiche Installation und Bereitstellung Ihrer Serverfarm sicherzustellen.

Wenn Sie nach Umgebungsanforderungen wie Active Directory, DNS oder Zertifikaten suchen, können Sie sich die [Umgebungsanforderungen für Skype for Business Server 2015](environmental-requirements.md) Dokument ansehen.
  
Wie Sie vielleicht erwarten, müssen Sie einige Vorbereitungen treffen, bevor Sie mit der Bereitstellung von Skype for Business Server 2015 beginnen. Dieser Artikel führt Sie durch die Planung der folgenden Schritte:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype for Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 verwendet werden](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nachdem Sie nun Ihre Topologie heruntergefahren sind (und wenn Sie dies nicht tun, können Sie die [Grundlagen der Topologie für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) Thema lesen), ist es an der Zeit, über Server nachzudenken. Für Skype for Business Server 2015 Server ist 64-Bit-Hardware erforderlich. Unsere Empfehlungen für die Hardware finden Sie weiter unten. Dabei handelt es sich nicht um Anforderungen, Sie entsprechen jedoch den Anforderungen für eine optimale Leistung. Wir verfügen über eine Dokumentation zur Kapazitätsplanung, mit der Sie bestimmen können, ob Sie je nach Ihren Umständen mehr benötigen.
  
Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 Gigabyte (GB).  <br/> |
|Datenträger  <br/> |Entweder  <br/> • 8 oder mehr 10000-u/min-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz (zwei der Datenträger mit RAID 1 und 6 mit RAID 10).  <br/> ODER  <br/> • Solid State Drives (SSDs), die denselben freien Speicherplatz und ähnliche Leistung wie 8 10000 rpm Mechanical Disk Drives bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeiten).  <br/> Duale oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat **nicht** unterstützt. <br/> Solange Sie nicht dem Betriebssystem ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, können Sie Out-of-Band-Verwaltungssysteme wie DRAC oder ILO verwenden. Dieses Szenario stellt keinen Multi-Homed-Server dar und wird unterstützt.  <br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver, Video-Interop-Server und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |Dualprozessor mit 64 Bit, Quad-Core, 2,26 Gigahertz (GHz) oder höher.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015 Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |16 Gigabyte.  <br/> |
|Datenträger  <br/> |Entweder  <br/> • 4 oder mehr 10000 rpm-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz (die Datenträger sollten sich in einer 2X RAID 1-Konfiguration befinden).  <br/> ODER  <br/> • Solid State Drives (SSDs), die denselben freien Speicherplatz und ähnliche Leistung wie 4 10000 rpm Mechanical Disk Drives bereitstellen können.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 Netzwerkadapter können verwendet werden, müssen jedoch mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeiten).  <br/> Duale oder Multi-Homed-Konfigurationen werden für Video-Interop-Server und Directors **nicht** unterstützt. <br/> Edgeserver benötigen zwei Netzwerkschnittstellen mit zwei Netzwerkadaptern, 1 Gbit/s oder höher (oder zwei gekoppelte Netzwerkadapter für insgesamt vier, wobei jedes Paar mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeitet, wobei insgesamt zwei Paare verwendet werden).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs) zur Konfiguration einer bestimmten PSTN-IP-Adresse unterstützt.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype for Business Server 2015
<a name="OS"> </a>

Nachdem Sie die Hardware installiert haben, müssen Sie Betriebssysteme (OS) installieren. Im folgenden finden Sie das Betriebssystem, mit dem Sie Skype for Business Server 2015 installieren und erfolgreich verwenden können.
  
|||
|:-----|:-----|
|Windows Server 2019 (Sie benötigen Skype for Business Kumulatives Update 9 oder höher). <br/> |Windows Server 2016 (Sie benötigen Skype for Business Kumulatives Update 5 oder höher. Weitere Informationen finden Sie [KB4015888](https://support.microsoft.com/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter-Betriebssystem mit allen erforderlichen Updates installiert.  <br/> |Windows Server 2012 R2 Standard-Betriebssystem mit allen erforderlichen Updates installiert.  <br/> |
|Windows Server 2012 Datacenter OS mit allen erforderlichen Updates installiert.  <br/> |Windows Server 2012 Standard Betriebssystem mit allen erforderlichen Updates installiert.  <br/> |
   
Wenn es nicht in dieser Liste aufgeführt ist, funktioniert es nicht ordnungsgemäß, versuchen Sie es nicht für neue Installationen von Skype for Business Server 2015. Beachten Sie, dass das direktes Upgrade des Betriebssystems mit lync Server 2013 nicht unterstützt wird.  Sie müssen einen separaten Pool bereitstellen und Benutzer mit einem anderen Betriebssystem in den neuen Pool migrieren.
  
> [!NOTE]
> Möglicherweise haben Sie bemerkt, dass Windows Server 2008 R2 nicht in dieser Liste aufgeführt ist. Das liegt daran, dass Windows Server 2012 R2 für alle neuen Server empfohlen wird, die für SFB verwendet werden sollen. Sie sollten Windows Server 2008 R2 nur verwenden, wenn Sie über vorhandene Server verfügen, auf denen lync Server 2013 bereits installiert ist, und Sie beabsichtigen, ein direktes Upgrade durchführen zu lassen. Windows Server 2008 R2 hat das Ende des Mainstream-Support-Lebenszyklus am 1/13/2015 erreicht und erreicht das Ende des Support-Lebenszyklus am 1/14/2020.
  
Zusätzlich zum neuesten Service Pack sollten Sie sicherstellen, dass die folgenden Updates installiert werden, sofern dies für Sie relevant ist:
  
- Für Windows Server 2012 sollte KB-Artikel 2858668 vor einem Upgrade installiert werden. [Hier erhalten Sie](https://support.microsoft.com/kb/2858668/).
    
- Wenn Sie Windows Server 2012 R2 haben, installieren Sie den KB-Artikel 2982006 vor dem Upgrade. [Sie finden Sie hier](https://support.microsoft.com/kb/2982006/).
    
- Wenn Sie ein Upgrade auf einem Windows Server 2008 R2-Feld durchführen (siehe Hinweis oben), sollten Sie zuerst den KB-Artikel 2533623 installieren. [Es ist unter diesem Link](https://support.microsoft.com/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 verwendet werden
<a name="DBs"> </a>


Wenn Sie Skype for Business Server 2015 Standard Edition installieren, wird auch SQL Server 2014 Express (64-Bit Edition) automatisch installiert.
  
Skype for Business Server 2015 Enterprise Edition ist etwas komplizierter, aber die unterstützte Liste ist unten (alles ist 64-Bit-Edition, Sie werden bemerken, bitte verwenden Sie keine 32-Bit-Editionen):
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen. <br/> |Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen. <br/> |Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit Skype for Business kumulativen Update 7 oder höher ausführen ([Download Skype for Business Kumulatives Update](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und Sie müssen mit dem kumulativen Update 6 oder höher ([Kumulatives Update 6 herunterladen](https://support.microsoft.com/kb/3031047/)) ausführen.  <br/> |Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.  <br/> |
|Microsoft SQL Server 2019 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen. <br/> |Microsoft SQL Server 2017 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen. <br/> |Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit Skype for Business kumulativen Update 7 oder höher ausführen ([Download Skype for Business Kumulatives Update](https://support.microsoft.com/help/3061064)).  <br/> |Microsoft SQL Server 2014 Standard (64-Bit-Edition), und Sie müssen mit dem kumulativen Update 6 oder höher ([Kumulatives Update 6 herunterladen](https://support.microsoft.com/kb/3031047/)) ausführen.  <br/> |Microsoft SQL Server 2012 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.  <br/> |
   
Wenn die SQL Server Edition, die Sie hier aufgelistet verwenden möchten, nicht angezeigt wird, können Sie Sie nicht verwenden.
  
- Außerdem müssen Sie SQL Server Reporting Services für die Monitoring Server Rolle installieren.
- Bei einem gut verbundenen SQL-Back-End sollte die Verbindung mit dem Skype for Business-Front-End lokal und nicht über einen Low-Speed-Link erfolgen. 
- Das Freigeben von SQL-Back-Ends zwischen zwei oder mehr Pools wird nicht unterstützt.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange Speicher
Besprechungsinhalts Dateien wie PowerPoint-Präsentationen werden als Anlagen archiviert. Wenn Sie Skype for Business Archivdaten mit Exchange-Konformitätsdaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und sicherstellen, dass die maximale Speichergröße die Speicherung der Besprechungsinhalts Dateien unterstützt. Sie müssen Exchange vor der Bereitstellung und Aktivierung von Archivierung mithilfe der Microsoft Exchange Integrations Option bereitstellen. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Hardware-und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
  
Bei der Archivierung handelt es sich nicht um eine definierte Serverrolle, Sie müssen keinen separaten Server für die Archivierung installieren. Unified Data Collection-Agents werden auf jeder Enterprise Edition-Front-End-Pool und jedem Standard Edition-Server automatisch installiert und aktiviert. Sie müssen die Archivierungs Topologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.
    
Bei der Archivierung wird der Skype for Business Server Dateispeicher für die temporäre Speicherung von Besprechungsinhalts Dateien verwendet, sodass Sie keinen separaten Dateispeicher für die Archivierung einrichten.
    
Microsoft Message Queuing ist nicht erforderlich.
    
Sie müssen die Infrastruktur für die Archivierung von Speicher einrichten. Dies umfasst das Auswählen von Exchange oder Archivierungsspeicher mithilfe SQL Server.   Skype for Business Server Anforderungen an die Archivierungsinfrastruktur entsprechen denen für die Bereitstellung von Skype for Business Server. Ausführliche Informationen finden Sie unter [Requirements for your Skype for Business Environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Zur Unterstützung von Benutzern, die nicht auf Exchange-Servern verwaltet werden, oder wenn Sie die Option Microsoft Exchange Integration nicht verwenden möchten, müssen Sie den Archivierungsspeicher mit einer 64-Bit-SQL Server Datenbank bereitstellen. 
    
Sie müssen die SQL Server Plattformen einrichten, bevor Sie die Archivierung bereitstellen und aktivieren. Wenn das zum Veröffentlichen der Topologie verwendete Konto über die entsprechenden Administratorrechte und-Berechtigungen verfügt, können Sie beim Veröffentlichen Ihrer Topologie die Archivierungsdatenbank (LcsLog) erstellen. Sie können die Datenbank auch später erstellen, die im Rahmen des Installationsverfahrens enthalten ist. Ausführliche Informationen zu SQL Server finden Sie in der [SQL Server-Dokumentation](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
Die Auslastungs Erweiterung für die Archivierung kann erheblich sein. Daher sollten Sie sicherstellen, dass der Speicherplatz für Front-End-Server ausreicht, auf denen die Archivierung aktiviert ist.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL-Spiegelung, SQL-Clustering und SQL immer

Sie können SQL-Spiegelung oder SQL-Clustering mit Skype for Business Server 2015 verwenden, es wird unterstützt. SQL-Spiegelung wird über den Skype for Business Server Topologie-Generator eingerichtet. Wenn Sie beabsichtigen, SQL-Clustering einzurichten, erfolgt dies in SQL Server.
  
Stellen Sie sicher, dass Sie über eine aktive/passive Konfiguration für SQL-Clustering verfügen, da dies unterstützt wird. Teilen Sie den passiven Knoten nicht mit einer anderen SQL-Instanz.
  
Sie können für Failoverclustering folgende Aktionen ausführen:
  
Zwei Knoten:
  
- Microsoft SQL Server 2019 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

- Microsoft SQL Server 2017 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

- Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, das neueste Service Pack auszuführen.

- Microsoft SQL Server 2014 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.
    
-  Microsoft SQL Server 2012 Standard (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

Sechzehn Knoten:

- Microsoft SQL Server 2019 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, das neueste Service Pack auszuführen.
  
- Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.
    
- Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), und es wird empfohlen, das neueste Service Pack auszuführen.

> [!IMPORTANT]
> Für ein Upgrade sollten Sie sicherstellen, dass Sie auf Ihren Front-End-Servern vor dem Upgrade mindestens SQL Server 2012 SP1 installiert haben. [Hier ist ein Link](https://www.microsoft.com/download/details.aspx?id=35575) zu SP1, wenn Sie es sofort herunterladen möchten.
  
Wenn Sie mehr über die SQL-Spiegelung lesen müssen, haben wir eine hohe Verfügbarkeit des Back-End-Servers in Skype for Business Server 2015 Thema. Konfigurieren Sie SQL Server Clustering für Skype for Business Server 2015 die Schritte zum Vorbereiten des Clusterings. Es gibt auch weitere Links zu Failoverclustering für SQL, für [2014](https://technet.microsoft.com/library/hh231721.aspx), [2012](https://technet.microsoft.com/library/hh231721%28v=sql.110%29.aspx)und [2008](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Neu in der 2015-Version ist die Unterstützung von SQL Always on. Sie wird unterstützt, und Sie können mehr darüber in der [Hochverfügbarkeit des Back-End-Servers in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md) Thema lesen.

> [!NOTE]
> Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failoverclustering-Methoden werden bei Skype for Business Server 2019 bevorzugt.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden sollte
<a name="Software"> </a>

Es gibt einige Dinge, die Sie installieren oder konfigurieren müssen, für jeden Server, auf dem Skype for Business Server 2015 läuft, und diese sind unten aufgeführt. Danach sind zusätzliche Anforderungen für bestimmte Serverrollen.
  
> [Hinweis!] Skype for Business Server 2015 unterstützt .NET Framework 4,8 nicht.
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Auf allen Skype for Business Server Servern muss Windows PowerShell 3,0 installiert sein.  <br/> • Wenn Sie die Installation auf Windows Server 2012 oder Windows Server 2012 R2 durchführen, werden Sie festgelegt, da Sie bereits vorhanden sind.  <br/> • Wenn Sie ein Upgrade auf Windows Server 2008 R2 durchführen, können Sie das [Windows Management Framework 3,0](https://www.microsoft.com/download/details.aspx?id=34595) herunterladen, um es zu erhalten. <br/> **Tipp:** Nachdem Sie die richtige PowerShell dort haben, vergewissern Sie sich, dass BuildVersion 6.2.9200.0 oder höher angezeigt wird, indem Sie zur PowerShell- `$PSVersionTable`Eingabeaufforderung wechseln und die Eingabe durchführen. Dies sollte die benötigten Informationen hervorrufen.  <br/> |
|Microsoft .NET Framework  <br/> |WCF-Dienste ist ein **Feature** , das als Windows-Feature installiert ist, unter **Server-Manager**keine Downloads erforderlich. <br/> • Sie müssen sicherstellen, dass bei der Installation dieses Features oder wenn es bereits installiert ist und Sie es überprüfen, dass die HTTP- **Aktivierungs** Option auch wie folgt überprüft und installiert wird: <br/> ![Screenshot, der die Option "http-Aktivierung" unter dem .NET Framework 4.5 Features anzeigt. ](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Machen Sie sich keine Sorgen, wenn Sie ein zusätzliches Popup erhalten, dass einige andere Dinge installiert werden müssen, damit die HTTP-Aktivierung installiert werden kann. Das ist normal, klicken Sie auf OK, und fahren Sie fort. Wenn Sie dieses Popup nicht erhalten, gehen Sie davon aus, dass diese Dinge bereits installiert sind, und fahren Sie fort.  <br/> Microsoft .NET Framework wird normalerweise installiert, wenn Windows Server 2012 R2 oder Windows Server 2016 installiert sind. Skype for Business Server funktioniert mit den folgenden Microsoft .NET Framework Versionen:  <br/> • .NET 3,5  <br/> • .NET 4,5  <br/> • .NET 4.6. x  <br/> • .NET 4.7.1 (für Skype for Business Server Version Cu 5 oder höher)  <br/> • .NET 4.7.2 (für Skype for Business Server Version Cu 6 oder höher)  <br/>  • .NET 4,8 (für Skype for Business Server Versionen von Cu 9 oder höher) <br/>  Microsoft .NET Framework 3.5 wird wahrscheinlich standardmäßig auf Ihrem Windows Server 2008 R2-Computer installiert (überprüfen Sie auf jeden Fall, ob Sie vor dem Upgrade sicher sind), es wird jedoch tatsächlich nicht auf Ihren Windows Server 2012/Windows Server 2012 R2-Servern (für neue Installationen) liegen. Um Sie in hinzuzufügen, benötigen Sie Zugriff auf Ihr Installationslaufwerk oder-Medium (die Stelle, von der aus Windows Server installiert wurde, oder wo die Installationsdateien jetzt sind). Installieren Sie es dann als Feature aus dem Server-Manager, und zeigen Sie auf die Installationsmedien (insbesondere den Ordner **\sources\sxs** ), wenn Sie danach gefragt werden, und fahren Sie fort, um es zu installieren. <br/> |
|Media Foundation  <br/> |Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format-Laufzeitkomponente mit Microsoft Media Foundation installiert.  <br/> Für alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, ist Windows Media Format Runtime erforderlich, um die Windows Media-Audiodateien (WMA) auszuführen, die von den Anwendungen für das Parken von anrufen, Ankündigungen und Reaktionsgruppen für Ankündigungen und Musik wiedergegeben werden.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3,5 zur Unterstützung von Server-zu-Server-Authentifizierungsszenarien für Skype for Business Server 2015.  <br/> • Für Windows Server 2012 und Windows Server 2012 R2 müssen Sie nichts herunterladen. Öffnen Sie den **Server-Manager**, und wechseln Sie zum **Assistenten zum Hinzufügen von Rollen und Features**. **Windows Identity Foundation 3,5** wird im Abschnitt **Features** aufgeführt. Wenn er überprüft wird, sind Sie gut. Andernfalls wählen Sie Sie aus, und klicken Sie auf Weiter, um die Schaltfläche **Installieren** zu erreichen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS-und AD LDS-Tools  <br/> |
   
 **Front-End-Server und Standard Edition-Server benötigen außerdem Folgendes:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (IIS)  <br/> |IIS ist auf allen Front-End-Servern sowie auf allen Standard Edition-Servern erforderlich, wobei die folgenden Module ausgewählt sind:  <br/> • Allgemeine HTTP-Features: Standarddokument, HTTP-Fehler, statischer Inhalt  <br/> • Integrität und Diagnose: HTTP-Protokollierung, Protokollierungs Tools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Authentifizierung der Client Zertifikatzuordnung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET-Erweiterbarkeit 3,5, .NET-Erweiterbarkeit 4,5, ASP.NET 3.5, ASP.NET 4,5, ISAPI-Erweiterungen, ISAPI-Filter  <br/> • Verwaltungs Tools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und-Tools  <br/> Beachten Sie auch, dass anonymer Zugriff auch erforderlich ist, aber wenn Sie IIS installieren, erhalten Sie, dass Sie nicht über einen Ort verfügen, um das in der Liste auszuwählen.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 müssen Sie das Feature **Media Foundation** im **Server-Manager**installieren. Nun können Sie Ihre Skype for Business Server 2015-Installation ohne diese starten, aber Sie werden aufgefordert, Sie zu installieren und dann den Server neu zu starten, bevor die Installation von Skype for Business Server 2015 fortgesetzt wird. Besser, dies vor der Zeit zu tun. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight unter [diesem Link](https://www.microsoft.com/silverlight/)installieren.  <br/> |
   
> [!NOTE] 
> Möglicherweise müssen Sie auch die Verzeichnissuche aktivieren, wenn Sie ein Lastenausgleichsmodul verwenden. Andernfalls wird eine leere Seite laden, die das Lastenausgleichsmodul möglicherweise einen Fehler zu prüfen. 

Um Ihnen zu helfen, finden Sie hier ein Beispiel-PowerShell-Skript, das Sie ausführen können, um dieses zu automatisieren:

```PowerShell
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht nach Quelldateien in einer bestimmten Reihenfolge. Wenn Sie online sind, greift der Befehl auf Windows Update zu. Wenn Sie jedoch offline sind, müssen Sie sicherstellen, dass die Quelldateien für den Befehl verfügbar sind. Weitere Informationen zur Verwendung von PowerShell zum Installieren von Rollen und Funktionen finden Sie unter [installieren oder Deinstallieren von Rollen, Rollendiensten oder Features](https://technet.microsoft.com/library/hh831809.aspx) vergessen Sie nicht, Windows Update erneut auszuführen, nachdem Sie die erforderlichen Komponenten installiert haben, selbst wenn Sie den PowerShell-Befehl verwenden.

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Server für beständigen Chat benötigen außerdem Folgendes:**
  
Message Queuing, das auch als MSMQ bezeichnet wird. Es handelt sich um eine Windows Server-Komponente, die Sie unter dem Abschnitt "Features" im Server-Manager installieren können. Wenn Sie mehr darüber erfahren möchten, lesen Sie [Installieren und Verwalten von Message Queuing](https://technet.microsoft.com/library/cc771474.aspx).
  
 **Letzte Überlegungen:**
  
Installieren Sie bitte keine ISA (Microsoft Internet Security and Acceleration Server)-Client Software oder andere LSP-Software (Winsock Layered Service Providers) (alle Drittanbieter-Firewalls oder Virenschutz-Netzwerk Inspektions Software wären hier enthalten) auf jeder Ihrer Front-End-Server oder eigenständigen Vermittlungsserver. Bei der Installation dieser Software ist eine schlechte Leistung beim Mediendatenverkehr zu beobachten.
  

