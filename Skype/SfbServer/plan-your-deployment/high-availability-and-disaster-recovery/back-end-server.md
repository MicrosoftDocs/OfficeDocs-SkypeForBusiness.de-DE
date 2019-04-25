---
title: Back-End-Server hohe Verfügbarkeit in Skype für Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Informationen Sie zu Business Server, einschließlich des AlwaysOn Availability Groups, AlwaysOn-Failoverclusterinstanzen, datenbankspiegelung und SQL-Failover-Clusterunterstützung in Skype unterstützten Optionen für die hohe Verfügbarkeit der Back-End-Server.
ms.openlocfilehash: 5f95ea1a1a856db945e1d0fac5683b1fb8c4c02e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214103"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Back-End-Server hohe Verfügbarkeit in Skype für Business Server
 
Informationen Sie zu Business Server, einschließlich des AlwaysOn Availability Groups, AlwaysOn-Failoverclusterinstanzen, datenbankspiegelung und SQL-Failover-Clusterunterstützung in Skype unterstützten Optionen für die hohe Verfügbarkeit der Back-End-Server.
  
Um die hohe Verfügbarkeit Ihrer Back-End-Server zu verbessern, stehen Ihnen vier Möglichkeiten zur Verfügung:
  
- Datenbankspiegelung
    
- AlwaysOn-Verfügbarkeitsgruppen
    
- AlwaysOn-Failoverclusterinstanzen (FCI)
    
- SQL-Failoverclustering
    
Die Verwendung einer dieser Lösungen ist optional, wird aber empfohlen, um die Geschäftskontinuität Ihres Unternehmens aufrechtzuerhalten. Anderenfalls konnte mit einem einzelnen Datenbankserver sinken die erhebliche Skype für Business Server-Daten verloren. 
  
Sie können mithilfe des Topologie-Generator-Database mirroring einrichten. Für AlwaysOn Availability Groups, AlwaysOn-Failoverclusterinstanzen oder SQL-Failover-Clusterunterstützung Sie SQL Server verwenden, um die Lösung für hohe Verfügbarkeit zu erstellen, und Sie können Topologie-Generator verwenden, um diesen mit einem Front-End-Pool zuordnen.
  
Wenn Sie hohen Verfügbarkeit von Back-End-Server auf einem Front-End-Pool, die für die Wiederherstellung einer anderen Front-End-Pool zugeordnet ist verwenden, sollten Sie die gleiche Back-End-Lösung für hohe Verfügbarkeit in beiden Pools verwenden. 
  
## <a name="database-mirroring"></a>Datenbankspiegelung

Skype für Business Server unterstützt Spiegelung mit der folgenden Datenbanksoftware:
  
- SQLServer 2016, Enterprise Edition und Standard Edition

- SQLServer 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und CU2, Enterprise Edition und Standard Edition
    

> [!NOTE]
> SQL Server 2016 ist die einzige Version von Skype für Business Server 2019 unterstützt.
    
Asynchrone datenbankspiegelung ist für hohe Verfügbarkeit von Back-End-Server in Skype für Business Server nicht unterstützt. Sofern nicht anders angegeben, steht in diesem Dokument die Datenbankspiegelung für die synchrone Datenbankspiegelung. 
  
Wenn Sie die datenbankspiegelung in einem Front-End-Pool bereitstellen, alle Skype für Business Server-Datenbanken im Pool gespiegelt werden, einschließlich des zentralen Verwaltungsspeichers, wenn es in diesem Pool als auch die Datenbank der Reaktionsgruppenanwendung und die Parken befindet Anwendungsdatenbank, wenn diese Anwendung im Pool ausgeführt werden. 
  
Bei der Datenbankspiegelung müssen Sie keinen gemeinsam genutzten Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher. 
  
Sie können die Datenbankspiegelung mit oder ohne Spiegelungszeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.
  
Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Richtlinien für die Planung der Spiegelung von Back-End-Servern

Im Allgemeinen müssen folgende Voraussetzungen erfüllt sein, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:
  
- Der primäre Server-Version von SQL Server muss SQL-Spiegelung unterstützen.
    
- Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden. 
    
- Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.
    
Best Practices für SQL im Hinblick auf die für eine Rolle Zeugen welche SQL-Versionen unterstützt werden finden Sie unter ["Datenbank-Spiegelungszeuge"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in der MSDN Library.
  
Bevor Sie die Serverspiegelung konfigurieren, müssen Sie zuerst die SQL-Datenbankberechtigungen richtig einrichten. Weitere Informationen hierzu finden Sie unter ["Einrichten von Anmeldekonten für Datenbank-Spiegelung oder AlwaysOn Availability Groups (SQLServer)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h. Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu verhindern, dass der Speicherplatz auf den Back-End-Servern zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Lync-Bereitstellungsarbeitsauslastung ermitteln und eine entsprechende Planung vornehmen. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:
  
> [!IMPORTANT]
> Über Topologie-Generator oder Cmdlets zum Einrichten und Entfernen von SQL-Spiegelung werden nur, wenn die primäre, Spiegel und Zeuge (sofern gewünscht) Server derselben Domäne angehören. Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server. 

> [!NOTE]
> SQL-Spiegelung wird steht in Skype für Business Server 2015 jedoch nicht mehr in unterstützt Skype für Business Server 2019. Die AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instanzen (FCI) und SQL clustering Failovermethoden werden bevorzugt mit Skype für Business Server 2019.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Wiederherstellungszeit für automatisches Failover des Back-End-Servers mit Datenbankspiegelung

Für automatisches Back-End-Failover mit Datenbankspiegelung wird ein Zielwert von 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) angestrebt. Aufgrund der synchronen Datenbankspiegelung wird nicht von einem Datenverlust bei Ausfällen von Back-End-Servern ausgegangen, außer in seltenen Fällen, wenn die Front-End-Server und der Back-End-Server beim Verschieben von Daten zwischen diesen Servern gleichzeitig ausfallen. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Benutzerfreundlichkeit beim Ausfall eines Back-End-Servers mit Datenbankspiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.
  
Wenn Sie die Datenbankspiegelung verwenden und einen Spiegelungszeugen konfiguriert haben und der Prinzipalserver ausfällt, erfolgt das Failover des Back-End-Servers automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.
  
Ist keine Zeugen konfiguriert, dauert es einige Zeit, die der Administrator das Failover manuell aufrufen. Während dieser Zeiten können aktive Benutzer beeinträchtigt werden. Sie weiterhin ihre Sitzungen wie gewohnt für etwa 30 Minuten. Wenn die primäre noch nicht wiederhergestellt wurde oder ein Administrator nicht nicht über die Sicherung konnte, werden dann Benutzer gewechselt wurde Ausfallsicherheitsmodus ist, d. h., sie zum Ausführen von Aufgaben, die eine beständige Änderung für Lync Server sind (beispielsweise das Hinzufügen eines Kontakts) erfordern.
  
Wenn sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn-Verfügbarkeitsgruppen und AlwaysOn-Failoverclusterinstanzen

AlwaysOn Availability Groups und AlwaysOn-Failoverclusterinstanzen werden nur in SQL Server 2014 Enterprise Edition und SQL Server 2012 Enterprise Edition unterstützt. Skype für Business Server unterstützt AlwaysOn Availability Groups nur als aktiv/passiv, nicht aktiv/aktiv. 
  
Um AlwaysOn Availability Groups oder AlwaysOn-Failoverclusterinstanzen verwenden möchten, verwenden Sie zuerst SQL Server einrichten und Konfigurieren der Lösung für hohe Verfügbarkeit. Topologie-Generator können dann diesen mit einem Front-End-Pool zuordnen.
  
> [!IMPORTANT]
> Instanznamen für mehrere Instanzen von AlwaysOn Availability Group müssen identisch sein. 
  
Schritte für die Bereitstellung von AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [Bereitstellen einer AlwaysOn Availability Group auf einem Back End-Server in Skype für Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Failoverclustering bei SQL-Servern

Skype für Business Server unterstützt SQL Server-Failover-Clusterunterstützung mit der folgenden Datenbanksoftware:
  
- SQLServer 2017, Enterprise Edition und Standard Edition

- SQLServer 2016, Enterprise Edition und Standard Edition

- SQLServer 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und CU2, Enterprise Edition und Standard Edition

Wenn SQL-Failover-Clusterunterstützung verwenden möchten, sollten Sie zunächst einrichten und konfigurieren den SQL Server-Cluster vor der Bereitstellung von den Front-End-Pool. Bewährte Methoden und zur Einrichtung für Failover-Clusterunterstützung in SQL Server 2012 finden Sie unter [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).

> [!NOTE]
> SQL Server 2017 und SQL Server 2016 sind die einzigen Versionen von Skype für Business Server 2019 unterstützt.
    
Wenn SQL-Failover-Clusterunterstützung verwenden möchten, sollten Sie zunächst einrichten und konfigurieren den SQL Server-Cluster vor der Bereitstellung von den Front-End-Pool. Bewährte Methoden und Anweisungen zum Failover-Clusterunterstützung in SQL Server 2014 und 2016 einrichten, finden Sie unter [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Failover-Clusterunterstützung in SQL Server 2008 finden Sie unter [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).
  
Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.
  

