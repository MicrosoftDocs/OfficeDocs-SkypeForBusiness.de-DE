---
title: SQL-Speichereinstellungen – Erweiterung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Wenn Sie die Eigenschaften einer SQL Server-Datenbank bearbeiten möchten, müssen Sie die SQL Server-Datenbankinstanz ändern. Sie können das DialogfeldEigenschaften bearbeiten nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungs Server-Datenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das DialogfeldEigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
ms.openlocfilehash: 2d9f03f7aed8aecc591a3f7c9177b5286fb3772b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684348"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="14f16-105">SQL-Speichereinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="14f16-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="14f16-106">Wenn Sie die Eigenschaften einer SQL Server-Datenbank bearbeiten möchten, müssen Sie die SQL Server-Datenbankinstanz ändern.</span><span class="sxs-lookup"><span data-stu-id="14f16-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="14f16-107">Sie können das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungs Server-Datenbank von einem Computer auf einen anderen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="14f16-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="14f16-108">Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.</span><span class="sxs-lookup"><span data-stu-id="14f16-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="14f16-109">Bearbeiten der Eigenschaften einer SQL Server-Datenbank</span><span class="sxs-lookup"><span data-stu-id="14f16-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="14f16-110">Wenn Sie die Instanz von SQL Server ändern möchten, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird, führen Sie das folgende Verfahren im Topologie-Generator aus:</span><span class="sxs-lookup"><span data-stu-id="14f16-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="14f16-111">So ändern Sie eine Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="14f16-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="14f16-112">Wählen Sie die entsprechende Datenbank unter dem Knoten **SQL Stores** aus, und klicken Sie dann auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="14f16-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="14f16-113">Führen Sie im Dialogfeld **Eigenschaften bearbeiten** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="14f16-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="14f16-114">Wenn Sie die standardmäßige SQL Server-Instanz verwenden möchten, wählen Sie **Standardinstanz** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="14f16-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="14f16-115">Wenn Sie eine benannte Datenbankinstanz verwenden möchten, wählen Sie **benannte Instanz**aus, geben Sie den Namen der Instanz in das Textfeld ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="14f16-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="14f16-116">Geben Sie nur den Namen der Instanz (beispielsweise ArchivingInstance) und nicht den gesamten SQL Server-Pfad ein.</span><span class="sxs-lookup"><span data-stu-id="14f16-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="14f16-117">Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, überprüft der Topologie-Generator nicht, ob es sich bei der von Ihnen eingegebenen Datenbankinstanz um eine gültige Instanz handelt.</span><span class="sxs-lookup"><span data-stu-id="14f16-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="14f16-118">Wenn Sie beispielsweise versehentlich als typeArchivingInstanec und dann auf **OK**klicken, akzeptiert der Topologie-Generator diese ungültige Instanz.</span><span class="sxs-lookup"><span data-stu-id="14f16-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="14f16-119">Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler korrigieren: Wenn eine SQL Server-Instanz nicht gefunden werden kann, wird diese Instanz von Topology Builder nicht für Sie erstellt.</span><span class="sxs-lookup"><span data-stu-id="14f16-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

