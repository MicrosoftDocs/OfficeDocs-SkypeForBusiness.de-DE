---
title: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Zusammenfassung: Erfahren Sie, wie Sie Überwachungsberichte einer spiegeldatenbank zuordnen, die von Skype for Business Server verwendet wird.'
ms.openlocfilehash: a30a107f8a5f5df6bb11bc8c409bf7376438f619
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60748851"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server 
 
**Zusammenfassung:** Erfahren Sie, wie Sie Überwachungsberichte einer spiegeldatenbank zuordnen, die von Skype for Business Server verwendet wird.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Überwachen von Berichten mit einer Spiegeldatenbank

Wenn Sie einen Spiegel für Die Überwachungsdatenbank konfigurieren, übernimmt diese Spiegeldatenbank als primäre Datenbank, wenn ein Failover auftritt. Wenn Sie jedoch Skype for Business Server Überwachungsberichte verwenden und ein Failover auftritt, stellen Sie möglicherweise fest, dass Ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen. Dies liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Speicherort der primären Datenbank angeben. Sie geben nicht den Speicherort der Spiegeldatenbank an.
  
Um Überwachungsberichte zum automatischen Failover auf die Spiegeldatenbank zu erhalten, müssen Sie die Spiegeldatenbank als "Failoverpartner" zu den beiden Datenbanken hinzufügen, die von Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetaildaten und die andere für QoE-Daten (Quality of Experience). (Beachten Sie, dass dieser Schritt ausgeführt werden sollte, nachdem Sie Überwachungsberichte installiert haben.) Sie können die Failoverpartnerinformationen hinzufügen, indem Sie die von diesen beiden Datenbanken verwendeten Verbindungszeichenfolgenwerte manuell bearbeiten. Führen Sie hierzu das folgende Verfahren aus:
  
1. Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services** Startseite zu öffnen. Die Homepage-URL für Reporting Services umfasst Folgendes:
    
   - Das **Präfix "http:".**
    
   - Der vollqualifizierte Domänenname (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. `atl-sql-001.litwareinc.com` ).
    
   - Die Zeichenfolge **/Reports_**.
    
   - Der Name der Datenbankinstanz, in der die Überwachungsberichte installiert sind (z. B. **"archinst").**
    
     Wenn beispielsweise SQL Server Reporting Services auf dem Computer installiert wurde `atl-sql-001.litwareinc.com` und die Überwachungsberichte die Datenbankinstanz "archinst" verwenden, würde die URL der Startseite wie folgt aussehen:
    
     `http://atl-sql-001.litwareinc.com/Reports_archinst`
    
2. Nachdem Sie auf die Reporting Services-Startseite zugegriffen haben, klicken Sie auf **"ServerReports"** und dann auf **Reports_Content**. Dadurch gelangen Sie zur **Reports_Content** Seite für die Skype for Business Server Überwachungsberichte.
    
3. Klicken Sie auf der **Reports_Content** Seite auf die **CDRDB-Datenquelle.**
    
4. Suchen Sie auf der **CdRDB-Seite** auf der Registerkarte **"Eigenschaften"** nach dem Textfeld mit der Bezeichnung **Verbindungszeichenfolge.** Die aktuelle Verbindungszeichenfolge sieht etwa wie folgt aus:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzuschließen. Wenn der Server beispielsweise "atl-mirror-001" heißt und sich die Spiegeldatenbank in der "archinst"-Instanz befindet, müssen Sie die Spiegeldatenbank mit dieser Syntax angeben:
    
    Failover Partner=atl-mirror-001\archinst
    
    Die bearbeitete Verbindungszeichenfolge sieht wie folgt aus:
    
    Data source=(local)\archinst; Failover partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **"Übernehmen".**
    
7. Klicken Sie auf der **CDRDB-Seite** auf den Link **Reports_Content.** Klicken Sie auf die **QMSDB-Datenquelle,** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Beispiel:
    
    `Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics`
    
8. Klicken Sie auf **Anwenden**.
    
## <a name="see-also"></a>Weitere Informationen

[Installieren von Überwachungsberichten in Skype for Business Server](install-monitoring-reports.md)
  
[Verwenden von Überwachungsberichten in Skype for Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
