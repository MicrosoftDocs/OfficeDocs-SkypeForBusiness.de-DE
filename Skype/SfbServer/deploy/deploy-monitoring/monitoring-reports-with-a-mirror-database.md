---
title: Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Überwachungsberichte einer von Skype for Business Server verwendeten Spiegeldatenbank zuordnen.'
ms.openlocfilehash: 0727a278b87edd0b3666b04d169dcd3460c8215c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273966"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a><span data-ttu-id="60b95-103">Zuordnen von Überwachungsberichten zu einer Spiegeldatenbank in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="60b95-103">Associate Monitoring Reports with a mirror database in Skype for Business Server</span></span> 
 
<span data-ttu-id="60b95-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie Überwachungsberichte einer von Skype for Business Server verwendeten Spiegeldatenbank zuordnen.</span><span class="sxs-lookup"><span data-stu-id="60b95-104">**Summary:** Learn how to associate Monitoring Reports with a mirror database used by Skype for Business Server.</span></span>
  
## <a name="monitor-reports-with-a-mirror-database"></a><span data-ttu-id="60b95-105">Überwachungsberichte mit einer Spiegeldatenbank</span><span class="sxs-lookup"><span data-stu-id="60b95-105">Monitor reports with a mirror database</span></span>

<span data-ttu-id="60b95-106">Wenn Sie einen Spiegel für Ihre Überwachungsdatenbank konfigurieren, dient diese Spiegeldatenbank als primäre Datenbank, wenn es zu einem Failover kommt.</span><span class="sxs-lookup"><span data-stu-id="60b95-106">If you configure a mirror for your monitoring database, that mirror database will take over as the primary database if a failover occurs.</span></span> <span data-ttu-id="60b95-107">Wenn Sie jedoch Skype for Business Server-Überwachungsberichte verwenden und ein Failover erfolgt, stellen Sie möglicherweise fest, dass ihre Überwachungsberichte keine Verbindung mit der Spiegeldatenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="60b95-107">However, if you use Skype for Business Server Monitoring Reports and a failover occurs, you might find that your Monitoring Reports are not connecting to the mirror database.</span></span> <span data-ttu-id="60b95-108">Das liegt daran, dass Sie bei der Installation von Überwachungsberichten nur den Standort der primären Datenbank und nicht den Standort der Spiegeldatenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="60b95-108">This is because, when you install Monitoring Reports, you specify only the location of the primary database; you do not specify the location of the mirror database.</span></span>
  
<span data-ttu-id="60b95-p102">Damit die Überwachungsberichte ein automatisches Failover zur Spiegeldatenbank durchführen, müssen Sie die Spiegeldatenbank als „Failover-Partner“ zu den zwei Datenbanken hinzufügen, die von den Überwachungsberichten verwendet werden (eine Datenbank für Anrufdetail-Datensatzdaten und die andere für QoE-Daten). (Beachten Sie, dass dieser Schritt nach der Installation der Überwachungsberichte durchgeführt werden sollte.) Sie können die Failover-Partnerinformationen hinzufügen, indem Sie die von den zwei Datenbanken verwendeten Verbindungzeichenfolgenwerte manuell bearbeiten. Verwenden Sie dazu das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="60b95-p102">To get Monitoring Reports to automatically failover to the mirror database, you must add the mirror database as a "failover partner" to the two databases that are used by Monitoring Reports (one database for Call Detail Record data, and the other for Quality of Experience (QoE) data). (Note that this step should be performed after you have installed Monitoring Reports.) You can add the failover partner information by manually editing the connection string values used by these two databases. To do that, complete the following procedure:</span></span>
  
1. <span data-ttu-id="60b95-p103">Verwenden Sie Internet Explorer, um die **SQL Server Reporting Services**-Startseite zu öffnen. Die URL für die Reporting Services-Startseite enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="60b95-p103">Use Internet Explorer to open the **SQL Server Reporting Services** home page. The Reporting Services home page URL includes:</span></span>
    
   - <span data-ttu-id="60b95-114">Den Präfix **http:**</span><span class="sxs-lookup"><span data-stu-id="60b95-114">The **http:** prefix.</span></span>
    
   - <span data-ttu-id="60b95-115">Den vollqualifizierten Domänennamen (FQDN) des Computers, auf dem die Reporting Services installiert sind (z. B. **atl-sql-001.litwareinc.com**)</span><span class="sxs-lookup"><span data-stu-id="60b95-115">The fully qualified domain name (FQDN) of the computer where the Reporting Services are installed (for example, **atl-sql-001.litwareinc.com**).</span></span>
    
   - <span data-ttu-id="60b95-116">Die Zeichenfolge **/Reports_**</span><span class="sxs-lookup"><span data-stu-id="60b95-116">The character string **/Reports_**.</span></span>
    
   - <span data-ttu-id="60b95-117">Den Namen der Datenbankinstanz, auf der die Überwachungsberichte installiert sind (z. B. **archinst**)</span><span class="sxs-lookup"><span data-stu-id="60b95-117">The name of the database instance where the Monitoring Reports are installed (for example, **archinst**).</span></span>
    
     <span data-ttu-id="60b95-118">Wenn SQL Server Reporting Services beispielsweise auf dem Computer atl-sql-001.litwareinc.com installiert wurde und die Überwachungsberichte die Datenbankinstanz archinst verwenden, würde die URL für die Startseite wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="60b95-118">For example, if SQL Server Reporting Services was installed on the computer atl-sql-001.litwareinc.com and the Monitoring Reports use the database instance archinst, the home page URL would look like this:</span></span>
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. <span data-ttu-id="60b95-119">Nachdem Sie die Reporting Services-Startseite geöffnet haben, klicken Sie auf **ServerReports** und dann auf **Reports_Content**.</span><span class="sxs-lookup"><span data-stu-id="60b95-119">After you have accessed the Reporting Services home page, click **ServerReports**, and then click **Reports_Content**.</span></span> <span data-ttu-id="60b95-120">Damit gelangen Sie zur **Reports_Content** -Seite für die Skype for Business Server-Überwachungsberichte.</span><span class="sxs-lookup"><span data-stu-id="60b95-120">That will take you to the **Reports_Content** page for the Skype for Business Server Monitoring Reports.</span></span>
    
3. <span data-ttu-id="60b95-121">Klicken Sie auf der Seite **Reports_Content** auf die Datenquelle **CDRDB**.</span><span class="sxs-lookup"><span data-stu-id="60b95-121">On the **Reports_Content** page, click the **CDRDB** data source.</span></span>
    
4. <span data-ttu-id="60b95-p105">Suchen Sie auf der Seite **CDRDB** auf der Registerkarte **Eigenschaften** nach dem Textfeld mit der Beschriftung **Verbindungszeichenfolge**. Die aktuelle Verbindungszeichenfolge sieht in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="60b95-p105">On the **CDRDB** page, on the **Properties** tab, look for the text box labeled **Connection string**. The current connection string will look similar to this:</span></span>
    
    <span data-ttu-id="60b95-124">Data source=(local)\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="60b95-124">Data source=(local)\archinst;initial catalog=LcsCDR</span></span>
    
5. <span data-ttu-id="60b95-p106">Bearbeiten Sie die Verbindungszeichenfolge, um den Servernamen und die Datenbankinstanz für die Spiegeldatenbank einzufügen. Wenn beispielsweise der Server atl-mirror-001 heißt und die Spiegeldatenbank die archinst-Instanz ist, müssen Sie diese über die folgende Syntax hinzufügen, um die Spiegeldatenbank anzugeben:</span><span class="sxs-lookup"><span data-stu-id="60b95-p106">Edit the connection string to include the server name and database instance for the mirror database. For example, if the server is named atl-mirror-001 and the mirror database is in the archinst instance, you will need to add to specify the mirror database using this syntax:</span></span>
    
    <span data-ttu-id="60b95-127">Failover Partner=atl-mirror-001\archinst</span><span class="sxs-lookup"><span data-stu-id="60b95-127">Failover Partner=atl-mirror-001\archinst</span></span>
    
    <span data-ttu-id="60b95-128">Ihre bearbeitete Verbindungszeichenfolge sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="60b95-128">Your edited connection string will look like this:</span></span>
    
    <span data-ttu-id="60b95-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span><span class="sxs-lookup"><span data-stu-id="60b95-129">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR</span></span>
    
6. <span data-ttu-id="60b95-130">Klicken Sie nach dem Aktualisieren der Verbindungszeichenfolge auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="60b95-130">After updating the connection string, click **Apply**.</span></span>
    
7. <span data-ttu-id="60b95-p107">Klicken Sie auf der Seite **CDRDB** auf den Link **Reports_Content**. Klicken Sie auf die Datenquelle **QMSDB** und bearbeiten Sie dann die Verbindungszeichenfolge für die QoE-Datenbank. Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="60b95-p107">On the **CDRDB** page, click the **Reports_Content** link. Click the **QMSDB** data source, and then edit the connection string for the QoE database. For example:</span></span>
    
    <span data-ttu-id="60b95-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span><span class="sxs-lookup"><span data-stu-id="60b95-134">Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics</span></span>
    
8. <span data-ttu-id="60b95-135">Klicken Sie auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="60b95-135">Click **Apply**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="60b95-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60b95-136">See also</span></span>

[<span data-ttu-id="60b95-137">Installieren von Überwachungsberichten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="60b95-137">Install Monitoring Reports in Skype for Business Server</span></span>](install-monitoring-reports.md)
  
[<span data-ttu-id="60b95-138">Verwenden von Überwachungsberichten in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="60b95-138">Using Monitoring Reports in Skype for Business Server</span></span>](../../manage/health-and-monitoring/monitoring-reports.md)
