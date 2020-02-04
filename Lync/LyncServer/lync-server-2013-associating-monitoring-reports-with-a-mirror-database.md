---
title: 'Lync Server 2013: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e5f10e3e4bd3c063cafcb2fd984098482ebf22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-07_

Wenn Sie einen Spiegel für Ihre Überwachungsdatenbank konfigurieren, dient diese Spiegeldatenbank als primäre Datenbank, wenn es zu einem Failover kommt. Wenn Sie jedoch lync Server-Überwachungsberichte verwenden und ein Failover erfolgt, stellen Sie möglicherweise fest, dass ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen. Das liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Standort der primären Datenbank und nicht den Standort der Spiegeldatenbank angeben.

Damit die Überwachungsberichte ein automatisches Failover zur Spiegeldatenbank durchführen, müssen Sie die Spiegeldatenbank als „Failover-Partner“ zu den zwei Datenbanken hinzufügen, die von den Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetail-Datensatzdaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation der Überwachungsberichte durchgeführt werden sollte.) Sie können die Failover-Partnerinformationen hinzufügen, indem Sie die von den zwei Datenbanken verwendeten Verbindungzeichenfolgenwerte manuell bearbeiten. Verwenden Sie dazu das folgende Verfahren:

1.  Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services**-Startseite zu öffnen. Die URL für die Reporting Services-Startseite enthält Folgendes:
    
      - Den Präfix **http:**
    
      - Den vollqualifizierten Domänennamen (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. **atl-sql-001.litwareinc.com**)
    
      - Die Zeichenfolge **/Reports\_**.
    
      - Den Namen der Datenbankinstanz, auf der die Überwachungsberichte installiert sind (z. B. **archinst**)
    
    Wenn SQL Server Reporting Services beispielsweise auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL für die Startseite wie folgt aussehen:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Nachdem Sie auf die Reporting Services-Startseite zugegriffen haben, klicken Sie auf **LyncServerReports**, und klicken Sie dann auf **Inhaltsberichte\_**. Damit gelangen Sie zur Seite " **Inhalts\_Berichte** " für die lync Server-Überwachungsberichte.

3.  Klicken Sie auf der Seite " **Inhaltsberichte\_** " auf die **CDRDB** -Datenquelle.

4.  Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld mit der Beschriftung **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge sieht in etwa wie folgt aus:
    
    **Datenquelle = (lokal)\\archinst; ursprünglicher Katalog = LcsCDR**

5.  Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzufügen. Wenn beispielsweise der Server atl-mirror-001 heißt und die Spiegeldatenbank die archinst-Instanz ist, müssen Sie diese über die folgende Syntax hinzufügen, um die Spiegeldatenbank anzugeben:
    
    **Failover-Partner = ATL-Mirror-\\001 archinst**
    
    Ihre bearbeitete Verbindungszeichenfolge sieht wie folgt aus:
    
    **Datenquelle = (lokal)\\archinst; Failover-Partner = ATL-Mirror-\\001 archinst; Initial Catalog = LcsCDR**

6.  Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **Anwenden**.

7.  Klicken Sie auf der **CDRDB** -Seite auf den Link **Inhaltsberichte\_** . Klicken Sie auf die Datenquelle **QMSDB** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Zum Beispiel:
    
    **Datenquelle = (lokal)\\archinst; Failover-Partner = ATL-Mirror-\\001 archinst; Initial Catalog = Datenbank QoEMetrics werden**

8.  Klicken Sie auf **Anwenden**.

<div>

## <a name="see-also"></a>Siehe auch


[Installieren von lync Server 2013-Überwachungsberichten](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Verwenden von Überwachungsberichten in lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

