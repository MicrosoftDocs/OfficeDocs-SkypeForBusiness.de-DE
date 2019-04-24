---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
ROBOTS: NOINDEX, NOFOLLOW
description: Zum Bearbeiten der Eigenschaften einer SQL Server-Datenbank müssen Sie die Instanz des SQL Server-Datenbank ändern. Klicken Sie im Dialogfeld Eigenschaften bearbeiten können Aufgaben wie die Archivierungsserver-Datenbank von einem Computer an eine andere verschieben. Darüber hinaus können Sie das Dialogfeld Eigenschaften bearbeiten zum Verwenden der Instanz von SQL Server, der als Host Ändern des zentralen Verwaltungsspeichers.
ms.openlocfilehash: d1b5287344095c062421a6afc56d620c81584fd3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235192"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="64bdc-105">SQL-Speichereinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="64bdc-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="64bdc-106">Zum Bearbeiten der Eigenschaften einer SQL Server-Datenbank müssen Sie die Instanz des SQL Server-Datenbank ändern.</span><span class="sxs-lookup"><span data-stu-id="64bdc-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="64bdc-107">Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** können Aufgaben wie die Archivierungsserver-Datenbank von einem Computer an eine andere verschieben.</span><span class="sxs-lookup"><span data-stu-id="64bdc-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="64bdc-108">Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** zum Verwenden der Instanz von SQL Server, der als Host Ändern des zentralen Verwaltungsspeichers.</span><span class="sxs-lookup"><span data-stu-id="64bdc-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="64bdc-109">Bearbeiten der Eigenschaften einer SQL Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="64bdc-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="64bdc-110">Führen Sie im Topologie-Generator die folgenden Schritte aus, um die Instanz von SQL Server zu ändern, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="64bdc-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="64bdc-111">So ändern Sie eine Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="64bdc-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="64bdc-112">Wählen Sie unter dem Knoten **SQL-Speicher** die gewünschte Datenbank aus, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="64bdc-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="64bdc-113">Klicken Sie im Dialogfeld **Eigenschaften bearbeiten** führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="64bdc-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="64bdc-114">Um die Standardinstanz von SQL Server verwenden, wählen Sie **Standardinstanz** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="64bdc-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="64bdc-115">Um eine benannte Datenbankinstanz verwenden, wählen Sie **Benannte Instanz**, geben Sie den Namen der Instanz in das Textfeld ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="64bdc-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="64bdc-116">Sie sollten nur der Name der Instanz (beispielsweise ArchivingInstance) und nicht den gesamten SQL Server-Pfad eingeben.</span><span class="sxs-lookup"><span data-stu-id="64bdc-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="64bdc-117">Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, wird Topologie-Generator nicht stellen Sie sicher, dass die Datenbankinstanz, die Sie eingegeben haben, um eine gültige Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="64bdc-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="64bdc-118">Angenommen, wenn Sie versehentlich TypeArchivingInstanec als den Namen der Instanz, und klicken Sie dann auf **OK**, Topologie-Generator akzeptiert, dass ungültige Instanz.</span><span class="sxs-lookup"><span data-stu-id="64bdc-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="64bdc-119">Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler beheben: Wenn eine SQL Server-Instanz kann nicht gefunden werden, erstellt der Topologie-Generator diese Instanz nicht für Sie.</span><span class="sxs-lookup"><span data-stu-id="64bdc-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

