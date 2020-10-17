---
title: 'Lync Server 2013: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank'
description: 'Lync Server 2013: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank.'
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
ms.openlocfilehash: d64b37901e7939b5e904dec73caac2d3483e2d71
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568801"
---
# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-07_

Wenn Sie eine Spiegelung für Ihre Überwachungsdatenbank konfigurieren, wird diese Spiegeldatenbank beim Auftreten eines Failovers als primäre Datenbank übernommen. Wenn Sie jedoch lync Server-Überwachungsberichte verwenden und ein Failover erfolgt, stellen Sie möglicherweise fest, dass ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen. Dies liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Speicherort der primären Datenbank angeben. Sie geben nicht den Speicherort der Spiegeldatenbank an.

Um Überwachungsberichte automatisch auf die Spiegeldatenbank zu Failovern, müssen Sie die Spiegeldatenbank als einen "Failoverpartner" zu den beiden Datenbanken hinzufügen, die von Überwachungsberichten verwendet werden (eine Datenbank für Datensatzdaten des Anrufdetails und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt ausgeführt werden sollte, nachdem Sie Überwachungsberichte installiert haben.) Sie können die Failover-Partner Informationen hinzufügen, indem Sie die Verbindungszeichenfolgen-Werte, die von diesen beiden Datenbanken verwendet werden, manuell bearbeiten. Führen Sie hierzu das folgende Verfahren aus:

1.  Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services** -Startseite zu öffnen. Die URL der Reporting Services-Startseite umfasst Folgendes:
    
      - Das Präfix " **http:** ".
    
      - Der vollqualifizierte Domänenname (FQDN) des Computers, auf dem die Reporting Services installiert sind (beispielsweise **ATL-SQL-001.litwareinc.com**).
    
      - Die Zeichenfolge **/Reports \_ **.
    
      - Der Name der Datenbankinstanz, in der die Überwachungsberichte installiert sind (beispielsweise **archinst**).
    
    Wenn beispielsweise SQL Server Reporting Services auf dem Computer ATL-SQL-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL der Startseite wie folgt aussehen:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Nachdem Sie auf die Homepage der Reporting Services zugegriffen haben, klicken Sie auf **LyncServerReports**, und klicken Sie dann auf **Berichte \_ Inhalt**. Dadurch gelangen Sie zur Seite ** \_ Inhaltsberichte** für die lync Server-Überwachungsberichte.

3.  Klicken Sie auf der Seite ** \_ Inhaltsberichte** auf die Datenquelle **CDRDB** .

4.  Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge wird wie folgt aussehen:
    
    **Datenquelle = (lokal) \\ archinst; Initial Catalog = LcsCDR**

5.  Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzubeziehen. Wenn der Server beispielsweise den Namen "ATL-Mirror-001" hat und die Spiegeldatenbank in der archinst-Instanz vorhanden ist, müssen Sie hinzufügen, um die Spiegeldatenbank mit dieser Syntax anzugeben:
    
    **Failover Partner = ATL-Mirror-001 \\ archinst**
    
    Die bearbeitete Verbindungszeichenfolge wird wie folgt aussehen:
    
    **Datenquelle = (local) \\ archinst; Failover Partner = ATL-Mirror-001 \\ archinst; Initial Catalog = LcsCDR**

6.  Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf über **nehmen**.

7.  Klicken Sie auf der Seite **CDRDB** auf den Link ** \_ Inhaltsberichte** . Klicken Sie auf die Datenquelle **QMSDB** , und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Zum Beispiel:
    
    **Datenquelle = (local) \\ archinst; Failover Partner = ATL-Mirror-001 \\ archinst; Initial Catalog = QoEMetrics**

8.  Klicken Sie auf **Anwenden**.

<div>

## <a name="see-also"></a>Siehe auch


[Installieren von Lync Server 2013-Überwachungsberichten](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Verwenden von Überwachungsberichten in lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

