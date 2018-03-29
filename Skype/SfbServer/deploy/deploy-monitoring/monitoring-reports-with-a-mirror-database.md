---
title: Ordnen Sie einer Spiegeldatenbank in Skype für Business Server 2015 Überwachungsberichte
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Zusammenfassung: Erfahren Sie, wie eine Spiegeldatenbank wird von Skype für Business Server 2015 Überwachungsberichte zugeordnet.'
ms.openlocfilehash: 246f16fd54133e2a6cf1e26a8126d0ec546bd686
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server-2015"></a><span data-ttu-id="1488b-103">Ordnen Sie einer Spiegeldatenbank in Skype für Business Server 2015 Überwachungsberichte</span><span class="sxs-lookup"><span data-stu-id="1488b-103">Associate Monitoring Reports with a mirror database in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1488b-104">**Zusammenfassung:** Hier erfahren Sie, wie eine Spiegeldatenbank wird von Skype für Business Server 2015 Überwachungsberichte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1488b-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server 2015.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="1488b-105">Überwachungsberichte mit einer Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="1488b-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="1488b-106">Wenn Sie einen Spiegel für Ihre Überwachungsdatenbank konfigurieren, dient diese Spiegeldatenbank als primäre Datenbank, wenn es zu einem Failover kommt.</span><span class="sxs-lookup"><span data-stu-id="1488b-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="1488b-107">Jedoch möglicherweise, wenn Sie Skype zur Business-Überwachungsberichte und ein Failover auftritt, Sie feststellen, dass Ihre Überwachungsberichte nicht die Spiegeldatenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="1488b-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="1488b-108">Das liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Standort der primären Datenbank und nicht den Standort der Spiegeldatenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="1488b-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="1488b-p102">Damit die Überwachungsberichte ein automatisches Failover zur Spiegeldatenbank durchführen, müssen Sie die Spiegeldatenbank als „Failover-Partner“ zu den zwei Datenbanken hinzufügen, die von den Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetail-Datensatzdaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation der Überwachungsberichte durchgeführt werden sollte.) Sie können die Failover-Partnerinformationen hinzufügen, indem Sie die von den zwei Datenbanken verwendeten Verbindungzeichenfolgenwerte manuell bearbeiten. Verwenden Sie dazu das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="1488b-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="1488b-p103">Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services**-Startseite zu öffnen. Die URL für die Reporting Services-Startseite enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1488b-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="1488b-114">Den Präfix **http:**</span><span class="sxs-lookup"><span data-stu-id="1488b-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="1488b-115">Den vollqualifizierten Domänennamen (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. **atl-sql-001.litwareinc.com**)</span><span class="sxs-lookup"><span data-stu-id="1488b-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="1488b-116">Die Zeichenfolge **/Reports_**</span><span class="sxs-lookup"><span data-stu-id="1488b-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="1488b-117">Den Namen der Datenbankinstanz, auf der die Überwachungsberichte installiert sind (z. B. **archinst**)</span><span class="sxs-lookup"><span data-stu-id="1488b-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
    <span data-ttu-id="1488b-118">Wenn SQL Server Reporting Services beispielsweise auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL für die Startseite wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="1488b-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
    **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="1488b-119">Nachdem Sie die Reporting Services-Startseite geöffnet haben, klicken Sie auf **ServerReports** und dann auf **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="1488b-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="1488b-120">Die Sie zur Seite **Reports_Content** für die Skype für Business Server-Überwachungsberichte dauert.</span><span class="sxs-lookup"><span data-stu-id="1488b-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="1488b-121">Klicken Sie auf der Seite **Reports_Content** auf die Datenquelle **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="1488b-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="1488b-p105">Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld mit der Beschriftung **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge sieht in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1488b-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="1488b-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="1488b-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="1488b-p106">Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzufügen. Wenn beispielsweise der Server atl-mirror-001 heißt und die Spiegeldatenbank die archinst-Instanz ist, müssen Sie diese über die folgende Syntax hinzufügen, um die Spiegeldatenbank anzugeben:</span><span class="sxs-lookup"><span data-stu-id="1488b-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="1488b-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="1488b-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="1488b-128">Ihre bearbeitete Verbindungszeichenfolge sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1488b-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="1488b-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="1488b-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="1488b-130">Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="1488b-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="1488b-p107">Klicken Sie auf der Seite **CDRDB** auf den Link **Reports_Content**. Klicken Sie auf die Datenquelle **QMSDB** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1488b-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="1488b-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="1488b-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="1488b-135">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="1488b-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1488b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1488b-136">See also</span></span>

#### 

[<span data-ttu-id="1488b-137">Installieren von Überwachungsberichten in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1488b-137">Install Monitoring Reports in Skype for Business Server 2015</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="1488b-138">Verwenden von Überwachungsberichten in Skype für Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1488b-138">Using Monitoring Reports in Skype for Business Server 2015</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)

