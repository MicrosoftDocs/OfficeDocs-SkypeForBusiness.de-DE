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
ms.openlocfilehash: 82d1ec6b1256326cca9e74d47d27820529050721
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a><span data-ttu-id="bfad2-102">Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfad2-102">Associating Monitoring Reports with a mirror database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfad2-103">_**Letztes Änderungsstand des Themas:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="bfad2-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="bfad2-104">Wenn Sie eine Spiegelung für Ihre Überwachungsdatenbank konfigurieren, wird diese Spiegeldatenbank beim Auftreten eines Failovers als primäre Datenbank übernommen.</span><span class="sxs-lookup"><span data-stu-id="bfad2-104">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="bfad2-105">Wenn Sie jedoch lync Server-Überwachungsberichte verwenden und ein Failover erfolgt, stellen Sie möglicherweise fest, dass ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="bfad2-105">However, if you use Lync Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="bfad2-106">Dies liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Speicherort der primären Datenbank angeben. Sie geben nicht den Speicherort der Spiegeldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="bfad2-106">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>

<span data-ttu-id="bfad2-107">Um Überwachungsberichte automatisch in das Failover auf die Spiegeldatenbank zu übertragen, müssen Sie die Spiegeldatenbank als einen "Failoverpartner" zu den beiden Datenbanken hinzufügen, die von Überwachungsberichten verwendet werden (eine Datenbank für Datensatzdaten des Anrufdetails und die andere für die Qualität von QoE-Daten (Experience)).</span><span class="sxs-lookup"><span data-stu-id="bfad2-107">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data).</span></span> <span data-ttu-id="bfad2-108">(Beachten Sie, dass dieser Schritt ausgeführt werden sollte, nachdem Sie Überwachungsberichte installiert haben.) Sie können die Failover-Partner Informationen hinzufügen, indem Sie die Verbindungszeichenfolgen-Werte, die von diesen beiden Datenbanken verwendet werden, manuell bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="bfad2-108">(Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases.</span></span> <span data-ttu-id="bfad2-109">Führen Sie hierzu das folgende Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="bfad2-109">To do that, complete the following procedure:</span></span>

1.  <span data-ttu-id="bfad2-110">Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services** -Startseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bfad2-110">Use Internet Explorer to open the **SQL Server Reporting Services** home page.</span></span> <span data-ttu-id="bfad2-111">Die URL der Reporting Services-Startseite umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="bfad2-111">The Reporting Services home page URL includes:</span></span>
    
      - <span data-ttu-id="bfad2-112">Das Präfix " **http:** ".</span><span class="sxs-lookup"><span data-stu-id="bfad2-112">The **http:** prefix.</span></span>
    
      - <span data-ttu-id="bfad2-113">Der vollqualifizierte Domänenname (FQDN) des Computers, auf dem die Reporting Services installiert sind (beispielsweise **ATL-SQL-001.litwareinc.com**).</span><span class="sxs-lookup"><span data-stu-id="bfad2-113">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
      - <span data-ttu-id="bfad2-114">Die Zeichenfolge **/Reports\_**.</span><span class="sxs-lookup"><span data-stu-id="bfad2-114">The character string **/Reports\_**.</span></span>
    
      - <span data-ttu-id="bfad2-115">Der Name der Datenbankinstanz, in der die Überwachungsberichte installiert sind (beispielsweise **archinst**).</span><span class="sxs-lookup"><span data-stu-id="bfad2-115">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="bfad2-116">Wenn beispielsweise SQL Server Reporting Services auf dem Computer ATL-SQL-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL der Startseite wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bfad2-116">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  <span data-ttu-id="bfad2-117">Nachdem Sie auf die Homepage der Reporting Services zugegriffen haben, klicken Sie auf **LyncServerReports**, und klicken Sie dann auf **Berichte\_Inhalt**.</span><span class="sxs-lookup"><span data-stu-id="bfad2-117">After you have accessed the Reporting Services home page, click **LyncServerReports**, and then click **Reports\_Content**.</span></span> <span data-ttu-id="bfad2-118">Dadurch gelangen Sie zur Seite **Inhaltsberichte\_** für die lync Server-Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="bfad2-118">That will take you to the **Reports\_Content** page for the Lync Server Monitoring Reports.</span></span>

3.  <span data-ttu-id="bfad2-119">Klicken Sie auf der Seite **Inhaltsberichte\_** auf die Datenquelle **CDRDB** .</span><span class="sxs-lookup"><span data-stu-id="bfad2-119">On the **Reports\_Content** page, click the **CDRDB** data source.</span></span>

4.  <span data-ttu-id="bfad2-120">Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld **Verbindungszeichenfolge**.</span><span class="sxs-lookup"><span data-stu-id="bfad2-120">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**.</span></span> <span data-ttu-id="bfad2-121">Die aktuelle Verbindungszeichenfolge wird wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bfad2-121">The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="bfad2-122">**Datenquelle = (lokal)\\archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="bfad2-122">**Data source=(local)\\archinst;initial catalog=LcsCDR**</span></span>

5.  <span data-ttu-id="bfad2-123">Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="bfad2-123">Edit the connection string to include the server name and database instance for the mirror database.</span></span> <span data-ttu-id="bfad2-124">Wenn der Server beispielsweise den Namen "ATL-Mirror-001" hat und die Spiegeldatenbank in der archinst-Instanz vorhanden ist, müssen Sie hinzufügen, um die Spiegeldatenbank mit dieser Syntax anzugeben:</span><span class="sxs-lookup"><span data-stu-id="bfad2-124">For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="bfad2-125">**Failover Partner = ATL-Mirror-001\\archinst**</span><span class="sxs-lookup"><span data-stu-id="bfad2-125">**Failover Partner=atl-mirror-001\\archinst**</span></span>
    
    <span data-ttu-id="bfad2-126">Die bearbeitete Verbindungszeichenfolge wird wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="bfad2-126">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="bfad2-127">**Datenquelle = (local)\\archinst; Failover Partner = ATL-Mirror-001\\archinst; Initial Catalog = LcsCDR**</span><span class="sxs-lookup"><span data-stu-id="bfad2-127">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=LcsCDR**</span></span>

6.  <span data-ttu-id="bfad2-128">Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="bfad2-128">After updating the connection string, click **Apply**.</span></span>

7.  <span data-ttu-id="bfad2-129">Klicken Sie auf der Seite **CDRDB** auf den Link **Inhaltsberichte\_** .</span><span class="sxs-lookup"><span data-stu-id="bfad2-129">On the **CDRDB** page, click the **Reports\_Content** link.</span></span> <span data-ttu-id="bfad2-130">Klicken Sie auf die Datenquelle **QMSDB** , und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="bfad2-130">Click the **QMSDB** data source, and then edit the connection string for the QoE database.</span></span> <span data-ttu-id="bfad2-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bfad2-131">For example:</span></span>
    
    <span data-ttu-id="bfad2-132">**Datenquelle = (local)\\archinst; Failover Partner = ATL-Mirror-001\\archinst; Initial Catalog = QoEMetrics**</span><span class="sxs-lookup"><span data-stu-id="bfad2-132">**Data source=(local)\\archinst;Failover Partner=atl-mirror-001\\archinst;initial catalog=QoEMetrics**</span></span>

8.  <span data-ttu-id="bfad2-133">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="bfad2-133">Click **Apply**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="bfad2-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfad2-134">See Also</span></span>


[<span data-ttu-id="bfad2-135">Installieren von Lync Server 2013-Überwachungsberichten</span><span class="sxs-lookup"><span data-stu-id="bfad2-135">Installing Lync Server 2013 Monitoring Reports</span></span>](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[<span data-ttu-id="bfad2-136">Verwenden von Überwachungsberichten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfad2-136">Using Monitoring Reports in Lync Server 2013</span></span>](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

