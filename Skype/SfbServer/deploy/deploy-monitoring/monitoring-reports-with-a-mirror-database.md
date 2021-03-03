---
title: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Zusammenfassung: Informationen zum Zuordnen von Überwachungsberichten zu einer spiegelungsdatenbank, die von Skype for Business Server verwendet wird.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802165"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie, wie Sie Überwachungsberichte einer Spiegeldatenbank zuordnen, die von Skype for Business Server verwendet wird.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Überwachen von Berichten mit einer Spiegeldatenbank

Wenn Sie einen Spiegel für ihre Überwachungsdatenbank konfigurieren, übernimmt diese Spiegeldatenbank bei einem Failover die primäre Datenbank. Wenn Sie jedoch Skype for Business Server Monitoring Reports verwenden und ein Failover auftritt, können Sie feststellen, dass Ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen. Dies liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Speicherort der primären Datenbank angeben. Sie geben nicht den Speicherort der Spiegeldatenbank an.
  
Damit Überwachungsberichte automatisch ein Failover zur Spiegeldatenbank ausführen, müssen Sie die Spiegeldatenbank als "Failoverpartner" zu den beiden Datenbanken hinzufügen, die von Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetaildaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation von Überwachungsberichten ausgeführt werden sollte.) Sie können die Informationen des Failoverpartners hinzufügen, indem Sie die verbindungszeichenfolgenwerte, die von diesen beiden Datenbanken verwendet werden, manuell bearbeiten. Führen Sie hierzu das folgende Verfahren aus:
  
1. Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services** zu öffnen. Die Url der Reporting Services-Startseite umfasst:
    
   - Das **Präfix http:.**
    
   - Der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Computers, auf dem Reporting Services installiert ist (z. B. **atl-sql-001.litwareinc.com**).
    
   - Die Zeichenfolge **/Reports_**.
    
   - Der Name der Datenbankinstanz, in der die Überwachungsberichte installiert sind (z. B. **Archinst**).
    
     Wenn beispielsweise SQL Server Reporting Services auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL der Startseite wie die folgende aussehen:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Nachdem Sie auf die Reporting Services-Startseite zugegriffen haben, klicken Sie auf **"ServerReports"** und dann **auf Reports_Content**. Auf diese Seite gelangen Sie **zur Reports_Content** für die Skype for Business Server-Überwachungsberichte.
    
3. Klicken Sie **auf Reports_Content** seite auf die **CDRDB-Datenquelle.**
    
4. Suchen Sie auf der Seite  **"CDRDB"** auf der Registerkarte "Eigenschaften" nach dem Textfeld mit der Bezeichnung **"Verbindungszeichenfolge".** Die aktuelle Verbindungszeichenfolge sieht in etwa so aus:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Bearbeiten Sie die Verbindungszeichenfolge so, dass sie den Servernamen und die Datenbankinstanz für die Spiegeldatenbank enthält. Wenn der Server beispielsweise "atl-mirror-001" heißt und sich die Spiegeldatenbank in der archinst-Instanz befindet, müssen Sie die Spiegeldatenbank mit der folgenden Syntax angeben:
    
    Failover Partner=atl-mirror-001\archinst
    
    Die bearbeitete Verbindungszeichenfolge sieht wie hier aussehen:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **Übernehmen**.
    
7. Klicken Sie **auf der Seite "CDRDB"** auf **den Reports_Content** Link. Klicken Sie **auf die DATENQUELLE DESTDB,** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Beispiel:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Klicken Sie auf **Anwenden**.
    
## <a name="see-also"></a>Siehe auch

[Installieren von Überwachungsberichten in Skype for Business Server](install-monitoring-reports.md)
  
[Verwenden von Überwachungsberichten in Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
