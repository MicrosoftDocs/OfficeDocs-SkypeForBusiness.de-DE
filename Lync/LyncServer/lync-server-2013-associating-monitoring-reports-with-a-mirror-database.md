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

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="f4f06-102">Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4f06-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4f06-103">_**Letztes Änderungsdatum des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="f4f06-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="f4f06-104">Wenn Sie einen Spiegel für Ihre Überwachungsdatenbank konfigurieren, dient diese Spiegeldatenbank als primäre Datenbank, wenn es zu einem Failover kommt.</span><span class="sxs-lookup"><span data-stu-id="f4f06-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="f4f06-105">Wenn Sie jedoch lync Server-Überwachungsberichte verwenden und ein Failover erfolgt, stellen Sie möglicherweise fest, dass ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="f4f06-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="f4f06-106">Das liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Standort der primären Datenbank und nicht den Standort der Spiegeldatenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="f4f06-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="f4f06-p102">Damit die Überwachungsberichte ein automatisches Failover zur Spiegeldatenbank durchführen, müssen Sie die Spiegeldatenbank als „Failover-Partner“ zu den zwei Datenbanken hinzufügen, die von den Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetail-Datensatzdaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation der Überwachungsberichte durchgeführt werden sollte.) Sie können die Failover-Partnerinformationen hinzufügen, indem Sie die von den zwei Datenbanken verwendeten Verbindungzeichenfolgenwerte manuell bearbeiten. Verwenden Sie dazu das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="f4f06-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="f4f06-p103">Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services**-Startseite zu öffnen. Die URL für die Reporting Services-Startseite enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f4f06-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="f4f06-112">Den Präfix **http:**</span><span class="sxs-lookup"><span data-stu-id="f4f06-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="f4f06-113">Den vollqualifizierten Domänennamen (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. **atl-sql-001.litwareinc.com**)</span><span class="sxs-lookup"><span data-stu-id="f4f06-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="f4f06-114">Die Zeichenfolge **/Reports\_**.</span><span class="sxs-lookup"><span data-stu-id="f4f06-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="f4f06-115">Den Namen der Datenbankinstanz, auf der die Überwachungsberichte installiert sind (z. B. **archinst**)</span><span class="sxs-lookup"><span data-stu-id="f4f06-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="f4f06-116">Wenn SQL Server Reporting Services beispielsweise auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL für die Startseite wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="f4f06-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="f4f06-117">Nachdem Sie auf die Reporting Services-Startseite zugegriffen haben, klicken Sie auf **LyncServerReports**, und klicken Sie dann auf **Inhaltsberichte\_**.</span><span class="sxs-lookup"><span data-stu-id="f4f06-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="f4f06-118">Damit gelangen Sie zur Seite " **Inhalts\_Berichte** " für die lync Server-Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="f4f06-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="f4f06-119">Klicken Sie auf der Seite " **Inhaltsberichte\_** " auf die **CDRDB** -Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f4f06-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="f4f06-p105">Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld mit der Beschriftung **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge sieht in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f4f06-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="f4f06-122">**Datenquelle = (lokal)\\archinst; ursprünglicher Katalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="f4f06-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="f4f06-p106">Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzufügen. Wenn beispielsweise der Server atl-mirror-001 heißt und die Spiegeldatenbank die archinst-Instanz ist, müssen Sie diese über die folgende Syntax hinzufügen, um die Spiegeldatenbank anzugeben:</span><span class="sxs-lookup"><span data-stu-id="f4f06-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="f4f06-125">**Failover-Partner = ATL-Mirror-\\001 archinst**</span><span class="sxs-lookup"><span data-stu-id="f4f06-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="f4f06-126">Ihre bearbeitete Verbindungszeichenfolge sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f4f06-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="f4f06-127">**Datenquelle = (lokal)\\archinst; Failover-Partner = ATL-Mirror-\\001 archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="f4f06-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="f4f06-128">Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="f4f06-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="f4f06-129">Klicken Sie auf der **CDRDB** -Seite auf den Link **Inhaltsberichte\_** .</span><span class="sxs-lookup"><span data-stu-id="f4f06-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="f4f06-130">Klicken Sie auf die Datenquelle **QMSDB** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f4f06-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="f4f06-131">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="f4f06-131">For example:</span></span>
    
    <span data-ttu-id="f4f06-132">**Datenquelle = (lokal)\\archinst; Failover-Partner = ATL-Mirror-\\001 archinst; Initial Catalog = Datenbank QoEMetrics werden**</span><span class="sxs-lookup"><span data-stu-id="f4f06-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="f4f06-133">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="f4f06-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f4f06-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4f06-134">See Also</span></span>


[<span data-ttu-id="f4f06-135">Installieren von lync Server 2013-Überwachungsberichten</span><span class="sxs-lookup"><span data-stu-id="f4f06-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="f4f06-136">Verwenden von Überwachungsberichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4f06-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

