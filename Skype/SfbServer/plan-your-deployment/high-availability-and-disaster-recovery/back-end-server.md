---
title: Hohe Verfügbarkeit des Back-End-Servers in Skype for Business Server
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
description: Erfahren Sie mehr über die back-End Server-Hochverfügbarkeitsoptionen, die in Skype for Business Server unterstützt werden, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen, Datenbankspiegelung und SQL Failoverclustering.
ms.openlocfilehash: 31ec37d898bd1f04c07142de1849928656f3238e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119374"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Hohe Verfügbarkeit des Back-End-Servers in Skype for Business Server
 
Erfahren Sie mehr über die back-End Server-Hochverfügbarkeitsoptionen, die in Skype for Business Server unterstützt werden, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen, Datenbankspiegelung und SQL Failoverclustering.
  
Um die hohe Verfügbarkeit für Ihre Back-End-Server zu verbessern, haben Sie vier Optionen:
  
- Datenbankspiegelung
    
- AlwaysOn-Verfügbarkeitsgruppen
    
- AlwaysOn Failover Cluster Instances (FCI)
    
- SQL Failoverclustering
    
Die Verwendung einer dieser Lösungen ist optional, es wird jedoch empfohlen, die Geschäftskontinuität Ihrer Organisation auf sicherzustellen. Andernfalls kann der Ausfall eines einzelnen Datenbankservers zu einem Verlust wichtiger Skype for Business Server-Daten führen. 
  
Sie können die Datenbankspiegelung nur mit dem Topologie-Generator einrichten. Für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen oder SQL-Failoverclustering verwenden Sie SQL Server, um die Hochverfügbarkeitslösung zu erstellen. Anschließend können Sie den Topologie-Generator verwenden, um sie einem Front-End-Pool zuzuordnen.
  
Wenn Sie die Hohe Verfügbarkeit von Back-End-Server in einem Front-End-Pool verwenden, der mit einem anderen Front-End-Pool für die Notfallwiederherstellung gekoppelt ist, sollten Sie in beiden Pools dieselbe Back-End-Hochverfügbarkeitslösung verwenden. 
  
## <a name="database-mirroring"></a>Datenbankspiegelung

Skype for Business Server unterstützt die Spiegelung mit der folgenden Datenbanksoftware:
  
- SQL Server 2019, Enterprise Edition und Standard Edition

- SQL Server 2017, Enterprise Edition und Standard Edition

- SQL Server 2016, Enterprise Edition und Standard Edition

- SQL Server 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und CU2, Enterprise Edition und Standard Edition
    

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI) und SQL Failoverclustering sind die einzigen unterstützten Optionen mit Skype for Business Server 2019.
    
Die asynchrone Datenbankspiegelung wird für die Hohe Verfügbarkeit des Back-End-Servers in Skype for Business Server nicht unterstützt. Im rest dieses Dokuments bedeutet Datenbankspiegelung synchrone Datenbankspiegelung, sofern nicht ausdrücklich anders angegeben. 
  
Wenn Sie die Datenbankspiegelung in einem Front-End-Pool bereitstellen, werden alle Skype for Business Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, wenn er sich in diesem Pool befindet, sowie die Anwendungsdatenbank der Reaktionsgruppe und die Anwendungsdatenbank zum Parken von Anrufen, wenn diese Anwendungen im Pool ausgeführt werden. 
  
Bei der Datenbankspiegelung müssen Sie keinen freigegebenen Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher. 
  
Sie können die Datenbankspiegelung mit oder ohne Zeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.
  
Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Richtlinien für die Planung der Back-End-Serverspiegelung

Im Allgemeinen erfordert das Einrichten SQL Spiegelung zwischen den beiden Back-End-Servern mit einem Zeugen Folgendes:
  
- Die Version des primären Servers muss SQL Server die SQL unterstützen.
    
- Primär, Spiegel und Zeuge (sofern bereitgestellt) müssen die gleiche Version von SQL Server. 
    
- Der primäre und der Spiegel müssen die gleiche Edition von SQL Server. Der Zeuge hat möglicherweise eine andere Edition.
    
Weitere SQL bewährte Methoden zur Unterstützung SQL für eine Zeugenrolle finden Sie unter  ["Datenbankspiegelungszeuge"](/sql/database-engine/database-mirroring/database-mirroring-witness) in der MSDN Library.
  
Bevor Sie die Serverspiegelung konfigurieren, müssen Sie zuerst SQL Datenbankberechtigungen richtig einrichten. Weitere Informationen finden Sie unter "Einrichten von Anmeldekonten für datenbankspiegelung oder  [AlwaysOn-Verfügbarkeitsgruppen (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).
  
Bei SQL wird der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, was bedeutet, dass Sie die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern müssen, um zu vermeiden, dass auf den Back-End-Servern der Speicherplatz knapp wird. Die Häufigkeit der Transaktionsprotokollsicherungen hängt von der Protokollwachstumsrate ab, die wiederum von Datenbanktransaktionen abhängt, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, zu bestimmen, wie viel Transaktionsprotokollwachstum für Ihre Lync-Bereitstellungsauslastung erwartet wird, damit Sie die Planung entsprechend planen können. Die folgenden Artikel enthalten zusätzliche Informationen zur SQL- und Protokollverwaltung:
  
> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder der Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die primären, spiegel- und zeugenserver (falls gewünscht) zur gleichen Domäne gehören. Wenn Sie die Spiegelung SQL Servern in verschiedenen Domänen einrichten möchten, lesen Sie die SQL Server Dokumentation. 

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Wiederherstellungszeit für automatisches Back-End Server-Failover mit Datenbankspiegelung

Bei automatischem Back-End-Failover mit Datenbankspiegelung beträgt das Engineeringziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) 5 Minuten. Aufgrund der synchronen Datenbankspiegelung erwarten wir keinen Datenverlust bei Back-End-Server-Fehlern, außer in seltenen Fällen, wenn sowohl die Front-End-Server als auch der Back-End-Server gleichzeitig ausfallen, während Daten zwischen den Servern verschoben werden. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Benutzerfreundlichkeit beim Back-End-Serverfehler bei Datenbankspiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.
  
Wenn Sie die Datenbankspiegelung verwenden und einen Zeugen konfiguriert haben und der Prinzipal ausfällt, wird das Failover des Back-End-Servers automatisch und schnell ausgeführt. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.
  
Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft. Während dieser Zeit können aktive Benutzer betroffen sein. Sie setzen ihre Sitzungen für etwa 30 Minuten normal fort. Wenn der Primäre immer noch nicht wiederhergestellt wird oder ein Administrator keinen Fehler bei der Sicherung ausgeführt hat, werden die Benutzer in den Ausfallsicherheitsmodus gewechselt, was bedeutet, dass sie keine Aufgaben ausführen können, für die eine dauerhafte Änderung auf Lync Server erforderlich ist (z. B. hinzufügen eines Kontakts).
  
Wenn Sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen, oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn-Verfügbarkeitsgruppen und AlwaysOn-Failoverclusterinstanzen

Skype for Business Server unterstützt AlwaysOn-Verfügbarkeitsgruppen nur als aktiv/passiv, nicht aktiv/aktiv. 
  
Zum Verwenden von AlwaysOn-Verfügbarkeitsgruppen oder AlwaysOn-Failoverclusterinstanzen verwenden Sie zunächst SQL Server zum Einrichten und Konfigurieren der Hochverfügbarkeitslösung. Anschließend können Sie den Topologie-Generator verwenden, um ihn einem Front-End-Pool zuzuordnen.

Skype for Business Server unterstützt AlwaysOn mit der folgenden Datenbanksoftware:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 und CU2 Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 und 2016 sind die einzigen Versionen, die von Skype for Business Server 2019 unterstützt werden.

> [!NOTE]
> Always On Availability Groups **wird** in SQL 2016, 2017 und 2019 Standard Editionen nicht unterstützt, Sie können jedoch Always On Failover Cluster Instances verwenden. Weitere [Informationen finden Sie unter Editionen und SQL Server 2016.](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)
  
> [!IMPORTANT]
> Instanznamen für mehrere Instanzen der AlwaysOn-Verfügbarkeitsgruppe müssen identisch sein. 
  
Schritte zum Bereitstellen von AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>SQL Server Failoverclustering

Skype for Business Server unterstützt SQL Server Failoverclustering mit der folgenden Datenbanksoftware:
  
- SQL Server 2019, Enterprise Edition und Standard Edition

- SQL Server 2017, Enterprise Edition und Standard Edition

- SQL Server 2016, Enterprise Edition und Standard Edition

- SQL Server 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und CU2, Enterprise Edition und Standard Edition

Zum Verwenden SQL Failoverclustering sollten Sie zuerst den SQL Server einrichten und konfigurieren, bevor Sie Ihren Front-End-Pool bereitstellen. Bewährte Methoden und Setupanweisungen für Failoverclustering in SQL Server 2012 finden Sie unter [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) .

> [!NOTE]
> SQL Server 2019, 2017 und SQL Server 2016 sind die einzigen Versionen, die von Skype for Business Server 2019 unterstützt werden.
    
Zum Verwenden SQL Failoverclustering sollten Sie zuerst den SQL Server einrichten und konfigurieren, bevor Sie Ihren Front-End-Pool bereitstellen. Bewährte Methoden und Setupanweisungen für Failoverclustering in SQL Server 2014 und 2016 finden Sie unter [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) . Informationen zum Failoverclustering in SQL Server 2008 finden Sie unter [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) .
  
Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.
