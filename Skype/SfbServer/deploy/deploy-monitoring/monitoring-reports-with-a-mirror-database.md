---
title: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Überwachungsberichte einer von Skype for Business Server verwendeten Spiegeldatenbank zuordnen.'
ms.openlocfilehash: 522ed5f9bd6e437a83e9cb3575ca92c0bd049e44
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239886"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server 
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie Überwachungsberichte einer von Skype for Business Server verwendeten Spiegeldatenbank zuordnen.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Überwachungsberichte mit einer Spiegeldatenbank

Wenn Sie einen Spiegel für Ihre Überwachungsdatenbank konfigurieren, dient diese Spiegeldatenbank als primäre Datenbank, wenn es zu einem Failover kommt. Wenn Sie jedoch Skype for Business Server-Überwachungsberichte verwenden und ein Failover erfolgt, stellen Sie möglicherweise fest, dass ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen. Das liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Standort der primären Datenbank und nicht den Standort der Spiegeldatenbank angeben.
  
Damit die Überwachungsberichte ein automatisches Failover zur Spiegeldatenbank durchführen, müssen Sie die Spiegeldatenbank als „Failover-Partner“ zu den zwei Datenbanken hinzufügen, die von den Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetail-Datensatzdaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation der Überwachungsberichte durchgeführt werden sollte.) Sie können die Failover-Partnerinformationen hinzufügen, indem Sie die von den zwei Datenbanken verwendeten Verbindungzeichenfolgenwerte manuell bearbeiten. Verwenden Sie dazu das folgende Verfahren:
  
1. Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services**-Startseite zu öffnen. Die URL für die Reporting Services-Startseite enthält Folgendes:
    
   - Den Präfix **http:**
    
   - Den vollqualifizierten Domänennamen (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. **atl-sql-001.litwareinc.com**)
    
   - Die Zeichenfolge **/Reports_**
    
   - Den Namen der Datenbankinstanz, auf der die Überwachungsberichte installiert sind (z. B. **archinst**)
    
     Wenn SQL Server Reporting Services beispielsweise auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL für die Startseite wie folgt aussehen:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Nachdem Sie die Reporting Services-Startseite geöffnet haben, klicken Sie auf **ServerReports** und dann auf **Reports_Content**. Damit gelangen Sie zur **Reports_Content** -Seite für die Skype for Business Server-Überwachungsberichte.
    
3. Klicken Sie auf der Seite **Reports_Content** auf die Datenquelle **CDRDB**.
    
4. Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld mit der Beschriftung **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge sieht in etwa wie folgt aus:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzufügen. Wenn beispielsweise der Server atl-mirror-001 heißt und die Spiegeldatenbank die archinst-Instanz ist, müssen Sie diese über die folgende Syntax hinzufügen, um die Spiegeldatenbank anzugeben:
    
    Failover Partner=atl-mirror-001\archinst
    
    Ihre bearbeitete Verbindungszeichenfolge sieht wie folgt aus:
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **Anwenden**.
    
7. Klicken Sie auf der Seite **CDRDB** auf den Link **Reports_Content**. Klicken Sie auf die Datenquelle **QMSDB** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Zum Beispiel:
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Klicken Sie auf **Anwenden**.
    
## <a name="see-also"></a>Siehe auch

[Installieren von Überwachungsberichten in Skype for Business Server](install-monitoring-reports.md)
  
[Verwenden von Überwachungsberichten in Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
