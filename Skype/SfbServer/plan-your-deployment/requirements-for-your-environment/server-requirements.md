---
title: Serveranforderungen für Skype for Business Server 2015
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8d47b242-b93d-4c2e-a658-23b78bca30b1
description: 'Zusammenfassung: Bereiten Sie Ihre Server von Skype for Business Server 2015 mit diesem Thema vor. Mithilfe von Hardware, Betriebssystem, Datenbank, Software und den Systemvoraussetzungen und -empfehlungen können Sie eine erfolgreiche Installation und Bereitstellung Ihrer Server-Farm garantieren.'
ms.openlocfilehash: 1c970a517fbb984d09aeba066a69726c9461a12c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875897"
---
# <a name="server-requirements-for-skype-for-business-server-2015"></a>Serveranforderungen für Skype for Business Server 2015
 
**Zusammenfassung:** Bereiten Sie Ihre Server von Skype for Business Server 2015 mit diesem Thema vor. Mithilfe von Hardware, Betriebssystem, Datenbank, Software und den Systemvoraussetzungen und -empfehlungen können Sie eine erfolgreiche Installation und Bereitstellung Ihrer Server-Farm garantieren.

Wenn der gesuchte für umgebungsanforderungen, wie Active Directory, DNS oder Zertifikate, können Sie die [umgebungsanforderungen für Skype für Business Server 2015](environmental-requirements.md) Doc Auschecken.
  
Erwartungsgemäß sind vor dem Beginn der Bereitstellung von Skype for Business Server 2015 einige Vorkehrungen zu treffen. Dieser Artikel führt Sie durch die Planung der folgenden Aspekte:
  
- [Hardware für Skype for Business Server 2015](server-requirements.md#Hardware)
  
- [Betriebssysteme für Skype for Business Server 2015](server-requirements.md#OS)
  
- [Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren](server-requirements.md#DBs)
  
- [Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden muss](server-requirements.md#Software)
  
## <a name="hardware-for-skype-for-business-server-2015"></a>Hardware für Skype for Business Server 2015
<a name="Hardware"> </a>

Nachdem Sie jetzt Ihre Topologie geplant haben (falls Sie dies noch nicht getan haben, lesen Sie [Topologiegrundlagen für Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)), müssen Sie sich um die Server kümmern. Für Skype for Business Server 2015-Server benötigen Sie 64-Bit-Hardware. Unsere Empfehlungen für die Hardware finden Sie weiter unten. Zwar handelt es sich dabei nicht um Anforderungen, aber die Empfehlungen entsprechen den Anforderungen, die für eine optimale Leistung erfüllt sein müssen. Wir bieten Ihnen eine Dokumentation zur Kapazitätsplanung, mit deren Hilfe Sie ermitteln können, ob Sie je nach Ihrer Situation Weiteres benötigen.
  
Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz.  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |32 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (2 der Festplatten mit RAID 1 und 6 Festplatten mit RAID 10).   <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 8 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat **nicht** unterstützt. <br/> So lange sie nicht für das Betriebssystem zur Verfügung stehen und zum Überwachen und Verwalten der Server-Hardware verwendet werden, können Sie über Out-Of-Band-Verwaltungssysteme wie DRAC oder ILO verfügen. Dieses Szenario bildet keinen Multihoming-Server und wird unterstützt.<br/> |
   
Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver, Video-Interop-Server und Directors:
  
|**Hardwarekomponente**|**Empfohlen**|
|:-----|:-----|
|CPU  <br/> |64-Bit-Dualprozessor, Vierkern, mindestens 2,26 GHz  <br/> Intel Itanium-Prozessoren werden für Skype for Business Server 2015-Rollen nicht unterstützt.  <br/> |
|Arbeitsspeicher  <br/> |16 GB.  <br/> |
|Festplatte  <br/> |ENTWEDER:  <br/> • Mindestens 4 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz (die Festplatten sollten in einer 2x-RAID-1-Konfiguration sein).  <br/> ODER  <br/> • SSDs (Solid State Drives) mit einer Leistung, die mit 4 mechanischen Festplattenlaufwerken bei 10.000 U/min vergleichbar ist.  <br/> |
|Netzwerk  <br/> |1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (Es können auch 2 Netzwerkadapter verwendet werden, wobei diese mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden müssen).  <br/> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Video-Interop-Server und Directors **nicht** unterstützt. <br/> Edgeserver erfordern zwei Netzwerkschnittstellen, die aus Dual-Port-Netzwerkadaptern bestehen, mit mindestens 1 GBit/s (oder zwei gepaarte Netzwerkadapter, also insgesamt vier; jedes Paar muss mit einer einzigen MAC-Adresse und einer einzigen IP-Adresse kombiniert werden, um insgesamt zwei Paare zu erhalten).  <br/> Auf eigenständigen Vermittlungsservern wird die Installation von zusätzlichen Netzwerkadaptern für die Konfiguration einer spezifischen PSTN-IP-Adresse unterstützt.  <br/> |
   
## <a name="operating-systems-for-skype-for-business-server-2015"></a>Betriebssysteme für Skype for Business Server 2015
<a name="OS"> </a>

Nachdem Sie die Hardware eingerichtet haben, müssen Sie Betriebssysteme installieren. Unter den folgenden Betriebssystemen können Sie Skype for Business Server 2015 installieren und erfolgreich verwenden.
  
|||
|:-----|:-----|
|Windows Server 2016 (Skype für Business kumulativen Update 5 oder höher erforderlich. Weitere Informationen zur Überprüfung [KB4015888](https://support.microsoft.com/en-gb/help/4015888/how-to-install-skype-for-business-server-2015-on-windows-server-2016))  <br/> ||
|Windows Server 2012 R2 Datacenter mit allen erforderlichen Updates  <br/> |Windows Server 2012 R2 Standard mit allen erforderlichen Updates  <br/> |
|Windows Server 2012 Datacenter mit allen erforderlichen Updates  <br/> |Windows Server 2012 Standard mit erforderlichen Updates  <br/> |
   
Nicht aufgeführte Betriebssysteme funktionieren nicht ordnungsgemäß. Versuchen Sie daher nicht, diese Betriebssysteme für neue Installationen von Skype for Business Server 2015 zu installieren.
  
> [!NOTE]
> Sie werden bemerkt haben, dass Windows Server 2008 R2 nicht in der Liste aufgeführt wird. Wir empfehlen stattdessen Windows Server 2012 R2 für alle neuen Server, die für SFB verwendet werden sollen. Sie sollten Windows Server 2008 R2 nur dann verwenden, wenn Sie bereits Server mit Lync Server 2013 installiert haben und versuchen möchten, ein direktes Update durchzuführen. Windows Server 2008 R2 hat am 13.01.2015 das Ende seines Supportlebenszyklus erreicht. 
  
Zusätzlich zum neuesten Service Pack sollten Sie gegebenenfalls sicherstellen, dass die folgenden Updates installiert werden:
  
- Für Windows Server 2012 sollte vor einem Upgrade die Software aus KB-Artikel 2858668 installiert werden, die Sie [hier](https://support.microsoft.com/en-us/kb/2858668/) finden.
    
- Wenn Sie Windows Server 2012 R2 verwenden, installieren Sie vor einem Upgrade die Software aus KB-Artikel 2982006. [Diese können Sie hier herunterladen](https://support.microsoft.com/en-us/kb/2982006/).
    
- Wenn Sie auf einem Windows Server 2008 R2-Computer ein Upgrade durchführen (siehe Hinweis oben), sollten Sie vorher die Software aus KB-Artikel 2533623 installieren. [Hier ist der entsprechende Link](https://support.microsoft.com/en-us/kb/2533623/).
    
## <a name="back-end-databases-that-will-work-with-skype-for-business-server-2015"></a>Back-End-Datenbanken, die mit Skype for Business Server 2015 funktionieren
<a name="DBs"> </a>

Wenn Sie Skype for Business Server 2015 Standard Edition installieren, wird automatisch auch SQL Server 2014 Express (64-Bit-Edition) installiert.
  
Skype for Business Server 2015 Enterprise Edition ist etwas komplizierter. Die Liste der unterstützten Betriebssysteme finden Sie weiter unten. (Wie Sie feststellen werden, handelt es sich nur um 64-Bit-Editionen. 32-Bit-Editionen sollten Sie nicht verwenden.)
  
|||||
|:-----|:-----|:-----|:-----|:-----|
|Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack. <br/> |Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit Skype für Business kumulative Update 7 oder höher ([Skype für Business kumulative Update herunterladen](https://support.microsoft.com/en-us/help/3061064)) ausführen.  <br/> |Microsoft SQL Server 2014 Enterprise (64-Bit-Edition) mit dem kumulativen Update 6 oder höher ([kumulatives Update 6 herunterladen](https://support.microsoft.com/en-us/kb/3031047/))  <br/> |Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), dazu empfehlen wir das neueste Service Pack.  <br/> |
|Microsoft SQL Server 2017 Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt. <br/> |Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher, und Sie müssen mit Skype für Business kumulative Update 7 oder höher ([Skype für Business kumulative Update herunterladen](https://support.microsoft.com/en-us/help/3061064)) ausführen.  <br/> |Microsoft SQL Server 2014 Standard (64-Bit-Edition) mit dem kumulativen Update 6 oder höher ([kumulatives Update 6 herunterladen](https://support.microsoft.com/en-us/kb/3031047/))  <br/> |Microsoft SQL Server 2012 Standard (64-Bit-Edition), dazu empfehlen wir das neueste Service Pack.  <br/> |
   
Wenn die von Ihnen gewünschte SQL Server-Edition nicht aufgeführt wird, können Sie sie nicht verwenden.
  
> [!NOTE]
> Sie nun auch müssen Sie SQL Server Reporting Services für den Monitoring Server-Role zu installieren.

### <a name="microsoft-exchange-storage"></a>Microsoft Exchange-Speicher
Meeting content files, such as PowerPoint presentations, are archived as attachments. Wenn Sie Skype für Geschäftsdaten für Archivierung mit Exchange Kompatibilitätsdaten speichern möchten, müssen Sie Exchange für Ihre Exchange-Bereitstellung verwenden und stellen Sie sicher, dass die maximale Speichergröße Speicherung von der Besprechung Inhaltsdateien unterstützt. Sie müssen vor dem Bereitstellen und Aktivieren der Archivierung die Option Microsoft Exchange-Integration mit Exchange bereitstellen. 
    
    If you choose to use Exchange storage, you do not need to deploy separate SQL Server databases for archiving, unless you have Skype for Business users who are not homed on your Exchange servers. If you deploy archiving using the Microsoft Exchange integration option, Skype for Business archive data is stored with Exchange compliance data only for the users who are homed on your Exchange servers. 
  
## <a name="hardware-and-software-requirements-for-archiving-in-skype-for-business-server-2015"></a>Hardware- und Softwareanforderungen für die Archivierung in Skype for Business Server 2015
  
Archivierung ist keine Serverrolle definierten, Sie müssen nicht auf einen separaten Server für die Archivierung zu installieren. Unified Datenerfassungs-Agenten werden installiert und automatisch auf jedem Enterprise Edition-Front-End-Pool und jedem Standard Edition-Server aktiviert. Sie müssen Ihre Archivierungstopologie mithilfe des Topologie-Generators aktivieren und veröffentlichen.
    
Archivierung werden die Skype für Business Server-Dateispeicher für die temporäre Speicherung von Dateien, sodass keine separate dateispeicherung für die Archivierung eingerichtet werden mit Besprechungsinhalten verwendet.
    
Microsoft Message Queuing ist nicht erforderlich.
    
Die Infrastruktur für Archivierungsspeicher muss eingerichtet werden. Dazu gehört das entweder Exchange auswählen oder Archivierungsspeicher mithilfe von SQL Server.   Skype für Business-Archivierung infrastrukturanforderungen sind die gleichen wie bei der Bereitstellung von Skype für Business Server. Weitere Informationen hierzu finden Sie unter [Anforderungen für Ihre Skype für Business-Umgebung](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). 
  
> [!NOTE]
> Zur Unterstützung von Benutzern, die nicht auf Exchange-Servern verwaltet werden, oder wenn Sie nicht die Option Microsoft Exchange-Integration verwenden möchten, müssen Sie Archivierungsspeicher mit einer 64-Bit-SQL Server-Datenbank bereitstellen. 
    
Sie müssen die SQL Server-Plattformen vor der Bereitstellung und Aktivieren der Archivierung einrichten. Wenn das Konto, das zum Veröffentlichen der Topologie verwendet werden soll, mit den erforderlichen Administratorrechten und -berechtigungen ausgestattet ist, können Sie die Archivierungsdatenbank (LcsLog) beim Veröffentlichen der Topologie erstellen. Sie können die Datenbank auch später erstellen, z. B. im Rahmen des Installationsverfahrens. Ausführliche Informationen zu SQL Server finden Sie unter der [SQL Server-Dokumentation](https://go.microsoft.com/fwlink/p/?linkID=129045).
    
Die Auslastung im Zuge der Archivierung kann erheblich steigen. Aus diesem Grund sollten Sie sicherstellen, dass Speicherplatz für Front-End-Servern geeignet ist, auf dem die Archivierung aktiviert ist.

### <a name="sql-mirroring-sql-clustering-and-sql-always-on"></a>SQL-Spiegelung, SQL-Clustering und SQL AlwaysOn

Die Verwendung von SQL-Spiegelung oder SQL-Clustering mit Skype for Business Server 2015 wird unterstützt. SQL-Spiegelung wird über den Skype for Business Server-Topologie-Generator eingerichtet. Wenn Sie SQL-Clustering einrichten möchten, verwenden Sie SQL Server.
  
Stellen Sie sicher, dass Sie über eine Aktiv/Passiv-Konfiguration für SQL-Clustering verfügen, da nur diese Variante unterstützt wird. Teilen Sie den passiven Knoten mit keiner anderen SQL-Instanz.
  
Für das Failoverclustering können Sie Folgendes verwenden:
  
Zwei Knoten:
  
- Microsoft SQL Server 2017 Standard (64-Bit-Edition), und es wird empfohlen wird mit dem neuesten Servicepack ausgeführt.

- Microsoft SQL Server 2016 Standard (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, mit dem neuesten Servicepack.

- Microsoft SQL Server 2014 Standard (64-Bit-Edition), dazu empfehlen wir das neueste Service Pack.
    
-  Microsoft SQL Server 2012 Standard (64-Bit-Edition), dazu empfehlen wir das neueste Service Pack.

Sechzehn Knoten:

- Microsoft SQL Server 2017 Enterprise (64-Bit-Edition), und wir empfehlen mit dem neuesten Servicepack.

- Microsoft SQL Server 2016 Enterprise (64-Bit-Edition) mit Service Pack 1 oder höher. Es wird empfohlen, mit dem neuesten Servicepack.
  
- Microsoft SQL Server 2014 Enterprise (64-Bit-Edition), dazu empfehlen wir das neueste Service Pack.
    
- Microsoft SQL Server 2012 Enterprise (64-Bit-Edition), dazu empfehlen wir das neueste Service Pack.

> [!IMPORTANT]
> Bei einem Upgrade sollten Sie im Vorfeld sicherstellen, dass auf den Front-End-Servern mindestens SQL Server 2012 SP1 installiert ist. [Unter diesem Link](https://www.microsoft.com/en-us/download/details.aspx?id=35575) können Sie SP1 direkt herunterladen.
  
Falls Sie mehr über die SQL-Spiegelung lesen möchten, bieten wir Ihnen ein Thema zur hohen Verfügbarkeit bei Back-End-Servern in Skype for Business Server 2015 an. Unter „Konfigurieren von SQL Server-Clustering für Skype for Business Server 2015“ finden Sie die Schritte zum Vorbereiten von Clustering. Außerdem gibt es weitere Links zum Thema Failoverclustering für SQL, und zwar für [2014](https://technet.microsoft.com/en-us/library/hh231721.aspx), [2012](https://technet.microsoft.com/en-us/library/hh231721%28v=sql.110%29.aspx) und [2008](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
> [!NOTE]
> Neue ist für die Version 2015 Unterstützung für SQL immer auf. Weitere Informationen dazu finden Sie im Thema [Hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/back-end-server.md).

> [!NOTE]
> SQL-Spiegelung wird steht in Skype für Business Server 2015 jedoch nicht mehr in unterstützt Skype für Business Server 2019. Die AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL clustering Failovermethoden werden bevorzugt mit Skype für Business Server 2019.  

## <a name="software-that-should-be-installed-before-a-skype-for-business-server-2015-deployment"></a>Software, die vor einer Skype for Business Server 2015-Bereitstellung installiert werden muss
<a name="Software"> </a>

Es gibt ein paar Dinge, die Sie für jeden Server mit Skype for Business Server 2015 installieren oder konfigurieren müssen. Weiter unten finden Sie eine entsprechende Liste. Auf die Liste folgen die zusätzlichen Anforderungen für bestimmte Serverrollen.
  
 **Alle Server:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Windows PowerShell 3.0  <br/> |Auf allen Skype for Business Server-Servern muss Windows PowerShell 3.0 installiert sein.  <br/> • Wenn Sie die Installation unter Windows Server 2012 oder Windows Server 2012 R2 ausführen, müssen Sie nichts mehr tun, da PowerShell bereits installiert ist.  <br/> • Wenn Sie unter Windows Server 2008 R2 ein Upgrade durchführen, können Sie [Windows Management Framework 3.0](https://www.microsoft.com/en-us/download/details.aspx?id=34595) herunterladen, um PowerShell zu installieren. <br/> **Tipp:** Vergewissern Sie sich nach der Installation von PowerShell, dass es sich um Buildversion 6.2.9200.0 oder höher handelt. Wechseln Sie dazu zur PowerShell-Eingabeaufforderung, und geben Sie `$PSVersionTable` ein. Dadurch erhalten Sie die gewünschten Informationen.  <br/> |
|Microsoft .NET Framework  <br/> |Die WCF-Dienste sind als Windows-**Funktion** unter **Server-Manager** installiert. Sie müssen nichts herunterladen. <br/> • Wenn Sie diese Funktion installieren oder wenn die Funktion bereits installiert ist und Sie sie überprüfen möchten, müssen Sie sicherstellen, dass wie in dieser Abbildung auch die Option **HTTP-Aktivierung** aktiviert und installiert ist: <br/> ![Screenshot mit der Option „HTTP-Aktivierung“ in den Funktionen von .NET Framework 4.5](../../media/a4064fa0-fa49-4474-bd98-b9a79ff68f8b.png)Machen Sie sich keine Sorgen, wenn ein zusätzliches Popupfenster angezeigt wird und Sie darüber informiert, dass für die HTTP-Aktivierung weitere Komponenten installiert werden müssen. Das ist normal, klicken Sie daher einfach auf „OK“, und fahren Sie fort. Wenn dieses Popupfenster nicht angezeigt wird, können Sie davon ausgehen, dass diese Komponenten bereits installiert sind, und fortfahren.  <br/> Microsoft .NET Framework wird normalerweise bei der Installation von Windows Server 2012 R2 oder Windows Server 2016 installiert. Skype for Business Server funktioniert mit den folgenden Versionen von Microsoft .NET Framework:  <br/> • .NET 3.5  <br/> • .NET 4.5  <br/> • .NET 4.6.x  <br/> • .NET 4.7 (für Skype for Business Server CU 5 oder höhere Versionen)  <br/>  .NET Framework 3.5 wurde wahrscheinlich standardmäßig auf Ihrem Windows Server 2008 R2-Computer installiert (überprüfen Sie dies unbedingt vor dem Upgrade), befindet sich aber nicht auf den Servern unter Windows Server 2012 oder Windows Server 2012 R2 (bei neuen Installationen). Um die Komponente hinzuzufügen, benötigen Sie Zugriff auf Ihr Installationslaufwerk oder auf Ihr Installationsmedium (den Ort, von dem aus Windows Server installiert wurde bzw. an dem sich die Installationsdateien jetzt befinden). Fahren Sie dann fort und installieren Sie es als eine Funktion des Server-Manager und geben Sie den Installationspfad zum Installationsmedium an (besonders den Ordner **\sources\sxs**), wenn Sie danach gefragt werden, und fahren Sie mit der Installation fort. <br/> |
|Media Foundation  <br/> |Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media-Format-Laufzeitkomponente zusammen mit Microsoft Media Foundation installiert.  <br/> Alle Front-End-Server und Standard Edition-Server, die für Konferenzen verwendet werden, benötigen die Windows Media-Format-Laufzeitkomponente, damit die WMA-Dateien (Windows Media Audio) ausgeführt werden können. Über diese Dateien geben die Anwendungen für das Parken von Anrufen, für Ankündigungen und für Reaktionsgruppen Ankündigungen und Musik wieder.  <br/> |
|Windows Identity Foundation  <br/> |Wir benötigen Windows Identity Foundation 3.5 für die Unterstützung von Szenarien mit Server-zu-Server-Authentifizierung für Skype for Business Server 2015.  <br/> • Für Windows Server 2012 und Windows Server 2012 R2 müssen Sie nichts herunterladen. Öffnen Sie den **Server-Manager** und rufen Sie den **Assistenten zum Hinzufügen von Rollen und Features** auf. **Windows Identity Foundation 3.5** wird unter dem Abschnitt **Funktionen** aufgelistet. Wenn das entsprechende Kontrollkästchen aktiviert ist, ist alles soweit in Ordnung. Andernfalls müssen Sie es auswählen und auf „Weiter“ klicken, um zur Schaltfläche **Installieren** zu gelangen. <br/> |
|Remoteserver-Verwaltungstools  <br/> |Rollenverwaltungstools: AD DS- und AD LDS-Tools  <br/> |
   
 **Für Front-End-Server und Standard Edition-Server benötigen Sie außerdem Folgendes:**
  
|**Software/Rolle**|**Details**|
|:-----|:-----|
|Internetinformationsdienste (Internet Information Services, IIS)  <br/> |IIS wird auf allen Front-End-Servern sowie auf allen Standard Edition-Servern benötigt. Dabei müssen die folgenden Module ausgewählt sein:  <br/> • Gemeinsam genutzte HTTP-Features: Standarddokument, HTTP-Fehler, Statischer Inhalt  <br/> • Systemzustand und Diagnose: HTTP-Protokollierung, Protokollierungstools, Ablaufverfolgung  <br/> • Leistung: Komprimierung statischer Inhalte, Komprimierung dynamischer Inhalte  <br/> • Sicherheit: Anforderungsfilterung, Authentifizierung über Clientzertifikatzuordnung, Windows-Authentifizierung  <br/> • Anwendungsentwicklung: .NET-Erweiterbarkeit 3.5, .NET-Erweiterbarkeit 4.5, ASP.NET 3.5, ASP.NET 4.5, ISAPI-Erweiterungen, ISAPI-Filter  <br/> • Verwaltungstools: IIS-Verwaltungskonsole, IIS-Verwaltungsskripts und -tools  <br/> Außerdem weisen wir darauf hin, dass anonymer Zugriff notwendig ist. Diesen erhalten Sie jedoch, wenn Sie IIS installieren. Daher sehen Sie in der Liste keine Auswahlmöglichkeit dafür.  <br/> |
|Windows Media Format-Laufzeitkomponente  <br/> | Für Windows Server 2016, Windows Server 2012 und Windows Server 2012 R2 müssen Sie die Funktion **Media Foundation** im **Server-Manager** installieren. Sie können die Skype for Business Server 2015-Installation auch ohne diese Funktion starten, aber Sie werden aufgefordert, sie zu installieren und den Server neu zu starten, bevor die Skype for Business Server 2015-Installation fortgesetzt wird. Es empfiehlt sich daher, dies rechtzeitig zu tun. <br/> |
|Silverlight  <br/> |Sie können die neueste Version von Silverlight über [diesen Link](https://www.microsoft.com/silverlight/) installieren.  <br/> |
   
> [!NOTE] 
> Wenn Sie ein Lastenausgleichsmodul verwenden, müssen Sie möglicherweise auch die Verzeichnissuche aktivieren. Andernfalls wird eine leere Seite geladen, die das Lastenausgleichsmodul möglicherweise für einen Fehler hält. 

Wir zeigen Ihnen nun das Beispiel eines PowerShell-Skripts, um dies zu automatisieren:

```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS, Desktop-Experience, Telnet-Client
```

> [!NOTE] 
> Der Befehl sucht in einer bestimmten Reihenfolge nach Quelldateien. Wenn Sie online sind, greift der Befehl auf Windows Update zu. Wenn Sie jedoch offline sind, müssen Sie dafür sorgen, dass alle Quelldateien für den Befehl zur Verfügung stehen. Weitere Informationen zur Verwendung von PowerShell für die Installation von Rollen und Funktionen finden Sie unter [Installieren oder Deinstallieren von Rollen, Rollendiensten oder Funktionen](https://technet.microsoft.com/en-us/library/hh831809.aspx). Führen Sie unbedingt Windows Update nach der Installation der erforderlichen Komponenten erneut aus, auch wenn Sie den PowerShell-Befehl verwendet haben.

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
Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client
```

 **Für Server für beständigen Chat benötigen Sie außerdem Folgendes:**
  
Message Queuing, auch MSMQ genannt. Dabei handelt es sich um eine Komponente von Windows Server, die Sie im Server-Manager im Abschnitt „Features“ installieren können. Wenn Sie mehr darüber wissen möchten, lesen Sie [Installieren und Verwalten von Message Queuing](https://technet.microsoft.com/en-us/library/cc771474.aspx).
  
 **Abschließend sei Folgendes gesagt:**
  
Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Clientsoftware oder andere Winsock-Mehrschicht-Dienstanbietersoftware auf Ihren Front-End-Servern oder eigenständigen Vermittlungsservern. Dies schließt auch sämtliche Drittanbieterfirewalls oder Antiviren-Netzwerkinspektionssoftware ein. Die Installation dieser Software kann die Leistung des Mediendatenverkehrs beeinträchtigen.
  

