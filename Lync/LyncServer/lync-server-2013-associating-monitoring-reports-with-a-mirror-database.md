---
title: Verknüpfen von Überwachungsberichten mit einer Spiegeldatenbank
TOCTitle: Verknüpfen von Überwachungsberichten mit einer Spiegeldatenbank
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945624(v=OCS.15)
ms:contentKeyID: 52056348
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verknüpfen von Überwachungsberichten mit einer Spiegeldatenbank

 

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Wenn Sie einen Spiegel für Ihre Überwachungsdatenbank konfigurieren, übernimmt diese Spiegeldatenbank als primäre Datenbank, wenn es zu einem Failover kommt. Wenn Sie jedoch Lync Server-Überwachungsberichte verwenden und es zu einem Failover kommt, stellen Sie möglicherweise fest, dass Ihre Überwachungsberichte keine Verbindung zur Spiegeldatenbank herstellen. Das liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Standort der primären Datenbank und nicht den Standort der Spiegeldatenbank angeben.

Damit die Überwachungsberichte ein automatisches Failover zur Spiegeldatenbank durchführen, müssen Sie die Spiegeldatenbank als "Failover-Partner" zu den zwei Datenbanken hinzufügen, die von den Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetail-Datensatzdaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation der Überwachungsberichte durchgeführt werden sollte.) Sie können die Failover-Partnerinformationen hinzufügen, indem Sie die von den zwei Datenbanken verwendeten Verbindungzeichenfolgenwerte manuell bearbeiten. Verwenden Sie dazu das folgende Verfahren:

1.  Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services**-Startseite zu öffnen. Die URL für die Reporting Services-Startseite enthält Folgendes:
    
      - Den Präfix **http:**
    
      - Den vollqualifizierten Domänennamen (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. **atl-sql-001.litwareinc.com**)
    
      - Die Zeichenfolge **/Reports\_**
    
      - Den Namen der Datenbankinstanz, auf der die Überwachungsberichte installiert sind (z. B. **archinst**)
    
    Wenn SQL Server Reporting Services beispielsweise auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL für die Startseite wie folgt aussehen:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Nachdem Sie die Reporting Services-Startseite geöffnet haben, klicken Sie auf **LyncServerReports** und dann auf **Reports\_Content**. Damit kommen Sie zur Seite **Reports\_Content** für die Lync Server-Überwachungsberichte.

3.  Klicken Sie auf der Seite **Reports\_Content** auf die Datenquelle **CDRDB**.

4.  Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld mit der Beschriftung **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge sieht in etwa wie folgt aus:
    
    **Data source=(local)\\archinst;initial catalog=LcsCDR**

5.  Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzufügen. Wenn beispielsweise der Server atl-mirror-001 heißt und die Spiegeldatenbank die archinst-Instanz ist, müssen Sie diese über die folgende Syntax hinzufügen, um die Spiegeldatenbank anzugeben:
    
    **Failover Partner=atl-mirror-001\\archinst**
    
    Ihre bearbeitete Verbindungszeichenfolge sieht wie folgt aus:
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**

6.  Nach dem Aktualisieren der Verbindungszeichenfolge klicken Sie auf **Übernehmen**.

7.  Klicken Sie auf der Seite **CDRDB** auf den Link **Reports\_Content**. Klicken Sie auf die Datenquelle **QMSDB** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Zum Beispiel:
    
    **Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**

8.  Klicken Sie auf **Übernehmen**.

## Siehe auch

#### Konzepte

[Installieren von Lync Server 2013-Überwachungsberichten](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Verwenden von Überwachungsberichten in Lync Server 2013](lync-server-2013-using-monitoring-reports.md)

