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
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Erfahren Sie mehr über die in Skype for Business Server unterstützten Back-End-Server-Hochverfügbarkeitsoptionen, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen, Datenbankspiegelung und SQL Failoverclustering.
ms.openlocfilehash: ce84429d77b8da426913d873d99d2f70badc4d12
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595483"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Hohe Verfügbarkeit von Back-End-Servern in Skype for Business Server
 
Erfahren Sie mehr über die in Skype for Business Server unterstützten Back-End-Server-Hochverfügbarkeitsoptionen, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen, Datenbankspiegelung und SQL Failoverclustering.
  
Um die hohe Verfügbarkeit für Ihre Back-End-Server zu verbessern, stehen Ihnen vier Optionen zur Verfügung:
  
- Datenbankspiegelung
    
- AlwaysOn-Verfügbarkeitsgruppen
    
- AlwaysOn-Failoverclusterinstanzen (FCI)
    
- SQL Failoverclustering
    
Die Verwendung einer dieser Lösungen ist optional, wird jedoch empfohlen, um die Geschäftskontinuität Ihrer Organisation aufrechtzuerhalten. Andernfalls kann der Ausfall eines einzelnen Datenbankservers zu einem Verlust erheblicher Skype for Business Server Daten führen. 
  
Sie können die Datenbankspiegelung nur mithilfe des Topologie-Generators einrichten. Für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen oder SQL Failoverclustering verwenden Sie SQL Server, um die Hochverfügbarkeitslösung zu erstellen. Anschließend können Sie den Topologie-Generator verwenden, um sie einem Front-End-Pool zuzuordnen.
  
Wenn Sie die hohe Verfügbarkeit des Back-End-Servers in einem Front-End-Pool verwenden, der mit einem anderen Front-End-Pool für die Notfallwiederherstellung gekoppelt ist, sollten Sie die gleiche Back-End-Lösung für hohe Verfügbarkeit in beiden Pools verwenden. 
  
## <a name="database-mirroring"></a>Datenbankspiegelung

Skype for Business Server unterstützt die Spiegelung mit der folgenden Datenbanksoftware:
  
- SQL Server 2019, sowohl Enterprise Edition als auch Standard Edition

- SQL Server 2017, sowohl Enterprise Edition als auch Standard Edition

- SQL Server 2016, sowohl Enterprise Edition als auch Standard Edition

- SQL Server 2014, sowohl Enterprise Edition als auch Standard Edition
    
- SQL Server 2012 SP2 und CU2, sowohl Enterprise Edition als auch Standard Edition
    

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering-Methoden sind die einzigen unterstützten Optionen mit Skype for Business Server 2019.
    
Die asynchrone Datenbankspiegelung wird für hohe Verfügbarkeit des Back-End-Servers in Skype for Business Server nicht unterstützt. Im restlichen Teil dieses Dokuments bedeutet die Datenbankspiegelung die synchrone Datenbankspiegelung, sofern nicht anders angegeben. 
  
Wenn Sie die Datenbankspiegelung in einem Front-End-Pool bereitstellen, werden alle Skype for Business Server Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, sofern er sich in diesem Pool befindet, sowie die Reaktionsgruppenanwendungsdatenbank und die Datenbank der Anwendung zum Parken von Anrufen, wenn diese Anwendungen im Pool ausgeführt werden. 
  
Bei der Datenbankspiegelung müssen Sie keinen freigegebenen Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher. 
  
Sie können die Datenbankspiegelung mit oder ohne Zeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.
  
Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Richtlinien für die Planung der Back-End-Serverspiegelung

Im Allgemeinen erfordert das Einrichten SQL Spiegelung zwischen den beiden Back-End-Servern mit einem Zeugen Folgendes:
  
- Die Version von SQL Server des primären Servers muss SQL Spiegelung unterstützen.
    
- Der Primäre, Spiegel und der Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server aufweisen. 
    
- Die primäre und die Spiegelung müssen die gleiche Edition von SQL Server aufweisen. Der Zeuge hat möglicherweise eine andere Edition.
    
SQL bewährten Methoden in Bezug darauf, welche SQL Versionen für eine Zeugenrolle unterstützt werden, finden Sie unter ["Datenbankspiegelungszeugen"](/sql/database-engine/database-mirroring/database-mirroring-witness) in der MSDN Library.
  
Bevor Sie die Serverspiegelung konfigurieren, müssen Sie zuerst SQL Datenbankberechtigungen ordnungsgemäß einrichten. Ausführliche Informationen finden Sie unter ["Einrichten von Anmeldekonten für datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).
  
Bei SQL Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **"Vollständig"** festgelegt, was bedeutet, dass Sie die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern müssen, um zu vermeiden, dass der Speicherplatz auf den Back-End-Servern knapp wird. Die Häufigkeit von Transaktionsprotokollsicherungen hängt von der Protokoll-Wachstumsrate ab, die wiederum von Datenbanktransaktionen abhängt, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie bestimmen, wie viel Transaktionsprotokoll-Wachstum für Ihre Lync-Bereitstellungsworkload erwartet wird, damit Sie die Planung entsprechend durchführen können. Die folgenden Artikel enthalten zusätzliche Informationen zu SQL Sicherung und Protokollverwaltung:
  
> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen von SQL Spiegelung wird nur unterstützt, wenn die Primären-, Spiegel- und Zeugenserver (falls gewünscht) zur gleichen Domäne gehören. Wenn Sie SQL Spiegelung zwischen Servern in verschiedenen Domänen einrichten möchten, lesen Sie die Dokumentation zu Ihrer SQL Server. 

> [!NOTE]
> SQL Spiegelung ist in Skype for Business Server 2015 verfügbar, wird jedoch in Skype for Business Server 2019 nicht mehr unterstützt. Die Methoden AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failoverclusterinstanzen (FCI) und SQL Failoverclustering werden mit Skype for Business Server 2019 bevorzugt.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Wiederherstellungszeit für automatisches Back-End-Serverfailover mit Datenbankspiegelung

Für das automatische Back-End-Failover mit Datenbankspiegelung beträgt das Entwicklungsziel für die Wiederherstellungszeit (Recovery Time Objective, RTO) 5 Minuten. Aufgrund der synchronen Datenbankspiegelung wird bei Back-End-Serverfehlern kein Datenverlust erwartet, außer in seltenen Fällen, wenn sowohl die Front-End-Server als auch der Back-End-Server gleichzeitig ausfallen, während Daten zwischen den Servern verschoben werden. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Benutzerfreundlichkeit bei Back-End-Server-Fehlern mit Datenbankspiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.
  
Wenn Sie die Datenbankspiegelung verwenden und einen Zeugen konfiguriert haben und der Prinzipal fehlschlägt, erfolgt das Back-End-Serverfailover automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.
  
Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft. Während dieser Zeit können aktive Benutzer betroffen sein. Sie setzen ihre Sitzungen etwa 30 Minuten lang normal fort. Wenn das primäre Element immer noch nicht wiederhergestellt wird oder ein Administrator nicht zur Sicherung übergegangen ist, werden die Benutzer in den Ausfallsicherheitsmodus umgeschaltet, was bedeutet, dass sie keine Aufgaben ausführen können, die eine dauerhafte Änderung auf Lync Server erfordern (z. B. das Hinzufügen eines Kontakts).
  
Wenn Sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen, oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn-Verfügbarkeitsgruppen und AlwaysOn-Failoverclusterinstanzen

Skype for Business Server unterstützt AlwaysOn-Verfügbarkeitsgruppen nur als aktiv/passiv, nicht aktiv/aktiv. 
  
Um AlwaysOn-Verfügbarkeitsgruppen oder AlwaysOn-Failoverclusterinstanzen zu verwenden, verwenden Sie zuerst SQL Server, um die Hochverfügbarkeitslösung einzurichten und zu konfigurieren. Anschließend können Sie den Topologie-Generator verwenden, um ihn einem Front-End-Pool zuzuordnen.

Skype for Business Server unterstützt AlwaysOn mit der folgenden Datenbanksoftware:

- SQL Server 2019 Enterprise Edition

- SQL Server 2019 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2- und CU2-Enterprise Edition

> [!NOTE]
> SQL Server 2019, 2017 und 2016 sind die einzigen Versionen, die von Skype for Business Server 2019 unterstützt werden.

> [!NOTE]
> AlwaysOn-Verfügbarkeitsgruppen werden in SQL Standardeditionen 2016, 2017 und 2019 **nicht** unterstützt, Sie können jedoch Always On-Failoverclusterinstanzen verwenden. Weitere Informationen finden Sie unter ["Editionen" und den unterstützten Features von SQL Server 2016.](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)
  
> [!IMPORTANT]
> Instanznamen für mehrere AlwaysOn-Verfügbarkeitsgruppeninstanzen müssen identisch sein. 
  
Schritte zum Bereitstellen von AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [Bereitstellen einer AlwaysOn-Verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server.](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)
  
## <a name="sql-server-failover-clustering"></a>SQL Server Failoverclustering

Skype for Business Server unterstützt SQL Server Failoverclustering mit der folgenden Datenbanksoftware:
  
- SQL Server 2019, sowohl Enterprise Edition als auch Standard Edition

- SQL Server 2017, sowohl Enterprise Edition als auch Standard Edition

- SQL Server 2016, sowohl Enterprise Edition als auch Standard Edition

- SQL Server 2014, sowohl Enterprise Edition als auch Standard Edition
    
- SQL Server 2012 SP2 und CU2, sowohl Enterprise Edition als auch Standard Edition

Um SQL Failoverclustering zu verwenden, sollten Sie zuerst den SQL Server Cluster einrichten und konfigurieren, bevor Sie Ihren Front-End-Pool bereitstellen. Bewährte Methoden und Anweisungen zum Einrichten von Failoverclustering in SQL Server 2012 finden Sie unter [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) .

> [!NOTE]
> SQL Server 2019, 2017 und SQL Server 2016 sind die einzigen Versionen, die von Skype for Business Server 2019 unterstützt werden.
    
Um SQL Failoverclustering zu verwenden, sollten Sie zuerst den SQL Server Cluster einrichten und konfigurieren, bevor Sie Ihren Front-End-Pool bereitstellen. Bewährte Methoden und Anweisungen zum Einrichten von Failoverclustering in SQL Server 2014 und 2016 finden Sie unter [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) . Informationen zum Failoverclustering in SQL Server 2008 finden Sie unter [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) .
  
Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.
