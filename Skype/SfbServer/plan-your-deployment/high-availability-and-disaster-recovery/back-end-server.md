---
title: Verfügbarkeit von Back-End-Servern in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: Informieren Sie sich über die in Skype for Business Server unterstützten Hochverfügbarkeits-Optionen für den Back-End-Server, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failovercluster-Instanzen, Datenbankspiegelung und SQL-Failover-Clusterunterstützung.
ms.openlocfilehash: db732d106546e5139725713da28bcb9c8b82bb93
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297484"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a>Verfügbarkeit von Back-End-Servern in Skype for Business Server
 
Informieren Sie sich über die in Skype for Business Server unterstützten Hochverfügbarkeits-Optionen für den Back-End-Server, einschließlich AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failovercluster-Instanzen, Datenbankspiegelung und SQL-Failover-Clusterunterstützung.
  
Um die hohe Verfügbarkeit Ihrer Back-End-Server zu verbessern, stehen Ihnen vier Möglichkeiten zur Verfügung:
  
- Datenbankspiegelung
    
- AlwaysOn-Verfügbarkeitsgruppen
    
- AlwaysOn-Failover-Cluster Instanzen (FCI)
    
- SQL-Failoverclustering
    
Die Verwendung einer dieser Lösungen ist optional, wird aber empfohlen, um die Geschäftskontinuität Ihres Unternehmens aufrechtzuerhalten. Andernfalls kann der Verlust signifikanter Skype for Business Server-Daten dazu führen, dass ein einzelner Datenbankserver herunterfällt. 
  
Sie können die Datenbankspiegelung nur mit dem Topologie-Generator einrichten. Für AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen oder SQL-Failover-Clustering verwenden Sie SQL Server zum Erstellen der Lösung für höchste Verfügbarkeit, und Sie können den Topologie-Generator verwenden, um ihn einem Front-End-Pool zuzuordnen.
  
Wenn Sie für den Back-End-Server eine höhere Verfügbarkeit in einem Front-End-Pool verwenden, der mit einem anderen Front-End-Pool für die Disaster Recovery gekoppelt ist, sollten Sie in beiden Pools dieselbe Lösung für das Back-End-Angebot verwenden. 
  
## <a name="database-mirroring"></a>Datenbankspiegelung

Skype for Business Server unterstützt die Spiegelung mit der folgenden Datenbanksoftware:
  
- SQL Server 2017, Enterprise Edition und Standard Edition

- SQL Server 2016, Enterprise Edition und Standard Edition

- SQL Server 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und Cu2, Enterprise Edition und Standard Edition
    

> [!NOTE]
> Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.
    
Die asynchrone Datenbankspiegelung wird für den Back-End-Server mit einer höheren Verfügbarkeit in Skype for Business Server nicht unterstützt. Sofern nicht anders angegeben, steht in diesem Dokument die Datenbankspiegelung für die synchrone Datenbankspiegelung. 
  
Wenn Sie die Datenbankspiegelung in einem Front-End-Pool bereitstellen, werden alle Skype for Business Server-Datenbanken im Pool gespiegelt, einschließlich des zentralen Verwaltungsspeichers, wenn Sie sich in diesem Pool befinden, sowie die Datenbank der reaktionsgruppenanwendung und der Anruf Park Anwendungsdatenbank, wenn diese Anwendungen im Pool ausgeführt werden. 
  
Bei der Datenbankspiegelung müssen Sie keinen gemeinsam genutzten Speicher für die Server verwenden. Jeder Server verwaltet eine Kopie der Datenbanken im lokalen Speicher. 
  
Sie können die Datenbankspiegelung mit oder ohne Spiegelungszeugen bereitstellen. Wir empfehlen die Verwendung eines Spiegelungszeugen, da dadurch das automatische Failover des Back-End-Servers ermöglicht wird. Andernfalls muss ein Administrator das Failover manuell auslösen. Beachten Sie, dass selbst bei der Bereitstellung eines Spiegelungszeugen ein Administrator bei Bedarf das Failover des Back-End-Servers manuell auslösen kann.
  
Wenn Sie einen Spiegelungszeugen verwenden, können Sie einen einzelnen Spiegelungszeugen für mehrere Back-End-Serverpaare verwenden. Es gibt keine strikte 1:1-Entsprechung zwischen Spiegelungszeugen und Back-End-Serverpaaren. Bereitstellungen, bei denen ein einzelner Spiegelungszeuge für mehrere Back-End-Serverpaare verwendet wird, sind nicht ganz so stabil wie Topologien mit einem separaten Spiegelungszeugen für jedes Back-End-Serverpaar. 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a>Richtlinien für die Planung der Spiegelung von Back-End-Servern

Im Allgemeinen müssen folgende Voraussetzungen erfüllt sein, um eine SQL-Spiegelung zwischen zwei Back-End-Servern mit einem Zeugen auszuführen:
  
- Die SQL Server-Version des Primärservers muss die SQL-Spiegelung unterstützen.
    
- Prinzipal, Spiegel und Zeuge (sofern bereitgestellt) müssen dieselbe Version von SQL Server verwenden. 
    
- Prinzipal und Spiegel müssen dieselbe Version von SQL Server verwenden. Der Zeuge darf eine andere Version verwenden.
    
Informationen zu SQL-bewährten Methoden in Bezug auf die Unterstützung von SQL-Versionen für eine Zeugenrolle finden Sie unter ["Daten Bank Spiegelungs Zeuge"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in der MSDN Library.
  
Bevor Sie die Serverspiegelung konfigurieren, müssen Sie zuerst die SQL-Datenbankberechtigungen richtig einrichten. Ausführliche Informationen finden Sie unter ["Einrichten von Anmeldekonten für Datenbankspiegelung oder AlwaysOn-Verfügbarkeitsgruppen (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).
  
Bei der SQL-Spiegelung ist der Datenbankwiederherstellungsmodus immer auf **Vollständig** festgelegt, d. h. Sie müssen die Größe des Transaktionsprotokolls genau überwachen und Transaktionsprotokolle regelmäßig sichern, um zu verhindern, dass der Speicherplatz auf den Back-End-Servern zur Neige geht. Die Häufigkeit der Transaktionsprotokollsicherungen ist abhängig von der Wachstumsrate des Protokolls. Letztere richtet sich wiederum nach den Datenbanktransaktionen, die durch Benutzeraktivitäten im Front-End-Pool entstehen. Es wird empfohlen, dass Sie das zu erwartende Wachstum des Transaktionsprotokolls für Ihre Lync-Bereitstellungsarbeitsauslastung ermitteln und eine entsprechende Planung vornehmen. In den folgenden Artikeln finden Sie zusätzliche Informationen zur SQL-Sicherung und Protokollverwaltung:
  
> [!IMPORTANT]
> Die Verwendung des Topologie-Generators oder von Cmdlets zum Einrichten und Entfernen der SQL-Spiegelung wird nur unterstützt, wenn die Server für primär-, Spiegel-und Zeugen (falls erwünscht) zur gleichen Domäne gehören. Wenn Sie die SQL-Spiegelung für Server einrichten möchten, die sich in unterschiedlichen Domänen befinden, erhalten Sie weitere Informationen in der Dokumentation zu SQL Server. 

> [!NOTE]
> Die SQL-Spiegelung ist in Skype for Business Server 2015 verfügbar, wird aber in Skype for Business Server 2019 nicht mehr unterstützt. Die AlwaysOn-Verfügbarkeitsgruppen, AlwaysOn-Failover-Cluster Instanzen (FCI) und SQL-Failover-Clustering-Methoden werden in Skype for Business Server 2019 bevorzugt.
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a>Wiederherstellungszeit für automatisches Failover des Back-End-Servers mit Datenbankspiegelung

Für automatisches Back-End-Failover mit Datenbankspiegelung wird ein Zielwert von 5 Minuten für die Wiederherstellungszeit (Recovery Time Objective, RTO) angestrebt. Aufgrund der synchronen Datenbankspiegelung wird nicht von einem Datenverlust bei Ausfällen von Back-End-Servern ausgegangen, außer in seltenen Fällen, wenn die Front-End-Server und der Back-End-Server beim Verschieben von Daten zwischen diesen Servern gleichzeitig ausfallen. Für den Wiederherstellungspunkt (Recovery Point Objective, RPO) wird ein Zielwert von 5 Minuten angestrebt.
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a>Benutzerfreundlichkeit beim Ausfall eines Back-End-Servers mit Datenbankspiegelung

Die Benutzerfreundlichkeit bei einem Ausfall hängt von der Art des Ausfalls und Ihrer Topologie ab.
  
Wenn Sie die Datenbankspiegelung verwenden und einen Spiegelungszeugen konfiguriert haben und der Prinzipalserver ausfällt, erfolgt das Failover des Back-End-Servers automatisch und schnell. Aktive Benutzer sollten bei ihren laufenden Sitzungen keine große Unterbrechung feststellen.
  
Wenn kein Zeuge konfiguriert ist, dauert es einige Zeit, bis der Administrator das Failover manuell aufruft. Während dieser Zeit sind möglicherweise aktive Benutzer betroffen. Sie werden Ihre Sitzungen wie gewohnt für etwa 30 Minuten fortsetzen. Wenn die primäre Person immer noch nicht wiederhergestellt wird oder ein Administrator nicht an die Sicherung gescheitert ist, werden die Benutzer in den Stabilitäts Modus versetzt, was bedeutet, dass Sie keine Aufgaben ausführen können, die eine dauerhafte Änderung auf lync Server erfordern (beispielsweise das Hinzufügen eines Kontakts).
  
Wenn sowohl der Prinzipalserver als auch der Spiegel-Back-End-Server ausfallen oder wenn einer dieser Server und der Spiegelungszeuge ausfallen, ist der Back-End-Server nicht mehr verfügbar (selbst wenn der Prinzipalserver weiterhin einsatzbereit ist). In diesem Fall werden die aktiven Benutzer nach einer Weile auf den Ausfallsicherheitsmodus umgestellt.
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a>AlwaysOn-Verfügbarkeitsgruppen und AlwaysOn-Failoverclusterinstanzen

Skype for Business Server unterstützt AlwaysOn-Verfügbarkeitsgruppen nur als aktiv/passiv, nicht aktiv/aktiv. 
  
Um AlwaysOn-Verfügbarkeitsgruppen oder AlwaysOn-Failovercluster-Instanzen zu verwenden, verwenden Sie zuerst SQL Server zum Einrichten und Konfigurieren der Lösung für Hochverfügbarkeit. Anschließend können Sie den Topologie-Generator verwenden, um ihn einem Front-End-Pool zuzuordnen.

Skype for Business Server unterstützt AlwaysOn mit folgender Datenbanksoftware:

- SQL Server 2017 Enterprise Edition

- SQL Server 2017 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2016 Enterprise Edition

- SQL Server 2016 Standard Edition mit Einschränkungen, siehe Hinweis unten

- SQL Server 2014 Enterprise Edition
    
- SQL Server 2012 SP2 und Cu2 Enterprise Edition

> [!NOTE]
> SQL Server 2017 und SQL Server 2016 sind die einzigen Versionen, die von Skype for Business Server 2019 unterstützt werden.

> [!NOTE]
> Immer auf Verfügbarkeitsgruppen wird in den Standard Editionen von SQL 2016 und 2017 **nicht** unterstützt, Sie können jedoch immer für Failovercluster-Instanzen verwendet werden. Weitere Informationen finden Sie unter [Editionen und unterstützte Features von SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) .
  
> [!IMPORTANT]
> Instanzennamen für mehrere AlwaysOn-Verfügbarkeitsgruppen Instanzen müssen identisch sein. 
  
Schritte zum Bereitstellen von AlwaysOn-Verfügbarkeitsgruppen finden Sie unter [Bereitstelleneiner AlwaysOn-verfügbarkeitsgruppe auf einem Back-End-Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).
  
## <a name="sql-server-failover-clustering"></a>Failoverclustering bei SQL-Servern

Skype for Business Server unterstützt die SQL Server-Failover-Clusterunterstützung mit der folgenden Datenbanksoftware:
  
- SQL Server 2017, Enterprise Edition und Standard Edition

- SQL Server 2016, Enterprise Edition und Standard Edition

- SQL Server 2014, Enterprise Edition und Standard Edition
    
- SQL Server 2012 SP2 und Cu2, Enterprise Edition und Standard Edition

Wenn Sie die SQL-Failover-Clusterunterstützung verwenden möchten, sollten Sie zuerst den SQL Server-Cluster einrichten und konfigurieren, bevor Sie den Front-End-Pool bereitstellen. Bewährte Methoden und Setupanweisungen für Failovercluster in SQL Server 2012 finden Sie unter [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).

> [!NOTE]
> SQL Server 2017 und SQL Server 2016 sind die einzigen Versionen, die von Skype for Business Server 2019 unterstützt werden.
    
Wenn Sie die SQL-Failover-Clusterunterstützung verwenden möchten, sollten Sie zuerst den SQL Server-Cluster einrichten und konfigurieren, bevor Sie den Front-End-Pool bereitstellen. Bewährte Methoden und Setupanweisungen für Failovercluster in SQL Server 2014 und 2016 finden Sie unter [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx). Informationen zum Failover-Clustering in SQL Server 2008 [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)finden Sie unter.
  
Wenn Sie SQL Server installieren, sollten Sie auch SQL Server Management Studio installieren, um die Speicherorte für Datenbank und Protokolldateien zu verwalten. SQL Server Management Studio ist eine optionale Komponente bei der Installation von SQL Server.
  

