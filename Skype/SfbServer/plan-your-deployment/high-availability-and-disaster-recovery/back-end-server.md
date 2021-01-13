---
title: Hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Erfahren Sie mehr über die in Skype for Business Server unterstützten Back-End-Server-Hochverfügbarkeitsoptionen, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen, Datenbankspiegelung und SQL Failoverclustering.
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802925"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server
 
Erfahren Sie mehr über die in Skype for Business Server unterstützten Back-End-Server-Hochverfügbarkeitsoptionen, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen, Datenbankspiegelung und SQL Failoverclustering.
  
Um die hohe Verfügbarkeit für Ihre Back-End-Server zu verbessern, stehen Ihnen vier Optionen zur Verfügung:
  
- Datenbankspiegelung
    
- AlwaysOn-Verfügbarkeitsgruppen
    
- AlwaysOn Failover Cluster Instances (FCI)
    
- SQL Failoverclustering
    
Die Verwendung einer dieser Lösungen ist optional, wird jedoch empfohlen, um die Geschäftskontinuität Ihrer Organisation zu gewährleisten. Andernfalls kann ein Ausfall eines einzelnen Datenbankservers zu einem erheblichen Verlust von Skype for Business Server-Daten führen. 
  
Sie können die Datenbankspiegelung nur mit dem Topologie-Generator einrichten. Für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen oder SQL-Failoverclustering verwenden Sie SQL Server zum Erstellen der Hochverfügbarkeitslösung. Anschließend können Sie den Topologie-Generator verwenden, um sie einem Front-End-Pool zuzuordnen.
  
Wenn Sie die hohe Verfügbarkeit von Back-End-Servern in einem Front-End-Pool verwenden, der mit einem anderen Front-End-Pool für die Notfallwiederherstellung gekoppelt ist, sollten Sie dieselbe Back-End-Hochverfügbarkeitslösung in beiden Pools verwenden. 
  
## <a name="database-mirroring"></a>Datenbankspiegelung

Skype for Business Server unterstützt die Spiegelung mit der folgenden Datenbanksoftware:
  
- SQL Server 2019, Enterprise Edition und Standard Edition

- SQL Server 2017, Enterprise Edition und Standard Edition

- SQL Server 2016, Enterprise Edition und Standard Edition

- SQL Server 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und CU2, Enterprise Edition und Standard Edition
    

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL-Failoverclustering-Methoden sind die einzigen unterstützten Optionen für Skype for Business Server 2019.
    
Die asynchrone Datenbankspiegelung wird für die hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server nicht unterstützt. Im restlichen Dokument bedeutet Datenbankspiegelung synchrone Datenbankspiegelung, sofern nicht anders angegeben. 
  
Wenn Sie die Datenbankspiegelung in einem Front-End-Pool bereitstellen, werden alle Skype for Business Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, sofern er sich in diesem Pool befindet, sowie die Reaktiongruppenanwendungsdatenbank und die Datenbank der Anwendung zum Parken von Anrufen, wenn diese Anwendungen im Pool ausgeführt werden. 
  
Bei der Datenbankspiegelung müssen Sie keinen gemeinsam genutzten Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher. 
  
Sie können die Datenbankspiegelung mit oder ohne Zeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.
  
Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Richtlinien für die Planung der Back-End-Serverspiegelung

Im Allgemeinen erfordert das Einrichten SQL Spiegelung zwischen den beiden Back-End-Servern mit einem Spiegelungszeugen Folgendes:
  
- Die Version des primären Servers muss SQL Server die SQL unterstützen.
    
- Der primäre Spiegel und der Spiegelungszeuge (sofern bereitgestellt) müssen dieselbe Version des SQL Server. 
    
- Die primäre und die Spiegelung müssen dieselbe Edition von SQL Server. Der Zeuge hat möglicherweise eine andere Edition.
    
Weitere SQL bewährte Methoden in Bezug auf die SQL für eine Zeugenrolle finden Sie unter  ["Datenbankspiegelungszeuge"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in der MSDN Library.
  
Bevor Sie die Serverspiegelung konfigurieren, müssen Sie zuerst die SQL datenbankberechtigungen ordnungsgemäß einrichten. Weitere Informationen finden Sie unter  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Bei SQL spiegelung ist der Datenbankwiederherstellungsmodus immer auf **"Full"** festgelegt, d. h., Sie müssen die Größe von Transaktionsprotokollen genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu vermeiden, dass auf den Back-End-Servern nicht mehr genügend Speicherplatz zur Verfügung steht. Die Häufigkeit von Transaktionsprotokollsicherungen hängt von der Protokollzuwachsrate ab, die wiederum von Datenbanktransaktionen abhängt, die durch Benutzeraktivitäten im Front-End-Pool anfallen. Es wird empfohlen, zu bestimmen, wie viel Transaktionsprotokollwachstum für die Arbeitsauslastung der Lync-Bereitstellung zu erwarten ist, damit Sie die Planung entsprechend planen können. Die folgenden Artikel enthalten zusätzliche Informationen zur SQL und Protokollverwaltung:
  
> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die primären, Spiegel- und Zeugenserver (falls gewünscht) zur gleichen Domäne gehören. Wenn Sie eine Spiegelung SQL Servern in verschiedenen Domänen einrichten möchten, lesen Sie ihre SQL Server Dokumentation. 

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL-Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Wiederherstellungszeit für automatisches Back-End-Serverfailover mit Datenbankspiegelung

Für das automatische Back-End-Failover mit Datenbankspiegelung beträgt das Entwicklungsziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) 5 Minuten. Aufgrund der synchronen Datenbankspiegelung wird bei Back-End-Serverausfällen kein Datenverlust erwartet, außer in seltenen Fällen, wenn sowohl der Front-End-Server als auch der Back-End-Server gleichzeitig ausfallen, während Daten zwischen den Servern verschoben werden. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Benutzerfreundlichkeit bei Back-End-Serverausfall mit Datenbankspiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.
  
Wenn Sie die Datenbankspiegelung verwenden und einen Spiegelungszeugen konfiguriert haben und der Prinzipalserver ausfällt, erfolgt das Failover des Back-End-Servers automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.
  
Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft. Während dieser Zeit können aktive Benutzer betroffen sein. Sie werden ihre Sitzungen wie gewohnt für ca. 30 Minuten fortsetzen. Wenn die primäre Datenbank weiterhin nicht wiederhergestellt wird oder ein Administrator kein Over over auf die Sicherung ausgeführt hat, werden die Benutzer in den Ausfallsicherheitsmodus versetzt, was bedeutet, dass sie keine Aufgaben ausführen können, die eine dauerhafte Änderung in Lync Server erfordern (z. B. das Hinzufügen eines Kontakts).
  
Wenn Sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen, oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn-Verfügbarkeitsgruppen und AlwaysOn-Failoverclusterinstanzen

Skype for Business Server unterstützt AlwaysOn-Verfügbarkeitsgruppen nur als aktiv/passiv, nicht aktiv/aktiv. 
  
Zur Verwendung von AlwaysOn-Verfügbarkeitsgruppen oder AlwaysOn-Failoverclusterinstanzen verwenden Sie zunächst SQL Server zum Einrichten und Konfigurieren der Hochverfügbarkeitslösung. Anschließend können Sie den Topologie-Generator verwenden, um ihn einem Front-End-Pool zuzuordnen.

Skype for Business Server unterstützt AlwaysOn mit der folgenden Datenbanksoftware:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition mit Einschränkungen finden Sie weiter unten.

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 und CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 und 2016 werden nur von Skype for Business Server 2019 unterstützt.

> [!NOTE]
> Always On-Verfügbarkeitsgruppen werden in SQL 2016-, 2017- und 2019-Standardeditionen nicht unterstützt, Sie können jedoch Always On-Failoverclusterinstanzen verwenden.  Weitere [Informationen finden Sie unter Editionen und SQL Server 2016.](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)
  
> [!IMPORTANT]
> Instanznamen für mehrere Instanzen der AlwaysOn-Verfügbarkeitsgruppe müssen identisch sein. 
  
Schritte zum Bereitstellen von AlwaysOn-Verfügbarkeitsgruppen finden Sie unter Bereitstellen einer [AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server.](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)
  
## <a name="sql-server-failover-clustering"></a>SQL Server Failoverclustering

Skype for Business Server unterstützt SQL Server Failoverclustering mit der folgenden Datenbanksoftware:
  
- SQL Server 2019, Enterprise Edition und Standard Edition

- SQL Server 2017, Enterprise Edition und Standard Edition

- SQL Server 2016, Enterprise Edition und Standard Edition

- SQL Server 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und CU2, Enterprise Edition und Standard Edition

Wenn Sie SQL Failoverclustering verwenden möchten, sollten Sie zuerst den SQL Server einrichten und konfigurieren, bevor Sie Ihren Front-End-Pool bereitstellen. Bewährte Methoden und Setupanweisungen für Failoverclustering in SQL Server 2012 finden Sie unter [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) .

> [!NOTE]
> SQL Server 2019, 2017 und SQL Server 2016 werden nur von Skype for Business Server 2019 unterstützt.
    
Wenn Sie SQL Failoverclustering verwenden möchten, sollten Sie zuerst den SQL Server einrichten und konfigurieren, bevor Sie Ihren Front-End-Pool bereitstellen. Bewährte Methoden und Setupanweisungen für Failoverclustering in SQL Server 2014 und 2016 finden Sie unter [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) . Informationen zum Failoverclustering in SQL Server 2008 finden Sie unter [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) .
  
Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.
  
