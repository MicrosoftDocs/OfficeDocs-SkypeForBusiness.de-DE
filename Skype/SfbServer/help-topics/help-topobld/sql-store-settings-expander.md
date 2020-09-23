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
- CSH
ms.custom:
- ms.lync.tb.SqlStoreSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bd269d52-6f87-4433-b9b0-2b543fea845d
description: Zum Bearbeiten der Eigenschaften einer SQL Server Datenbank müssen Sie die SQL Server Datenbankinstanz ändern. Sie können das DialogfeldEigenschaften bearbeiten nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungsserver Datenbank von einem Computer auf einen anderen auszuführen. Darüber hinaus können Sie das DialogfeldEigenschaften bearbeiten nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.
ms.openlocfilehash: e3b16d8c6eab4f4918ef39b3c4f1ab4d0c6fc057
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219610"
---
# <a name="sql-store-settings-expander"></a><span data-ttu-id="f7d64-105">SQL-Speichereinstellungen – Erweiterung</span><span class="sxs-lookup"><span data-stu-id="f7d64-105">SQL Store Settings Expander</span></span>
 
<span data-ttu-id="f7d64-106">Zum Bearbeiten der Eigenschaften einer SQL Server Datenbank müssen Sie die SQL Server Datenbankinstanz ändern.</span><span class="sxs-lookup"><span data-stu-id="f7d64-106">To edit the properties of a SQL Server database, you must change the SQL Server database instance.</span></span> <span data-ttu-id="f7d64-107">Sie können das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um Aufgaben wie das Verschieben Ihrer Archivierungsserver Datenbank von einem Computer auf einen anderen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f7d64-107">You cannot use the **Edit Properties** dialog box to perform tasks such as moving your Archiving Server database from one computer to another.</span></span> <span data-ttu-id="f7d64-108">Darüber hinaus können Sie das Dialogfeld **Eigenschaften bearbeiten** nicht verwenden, um die Instanz von SQL Server zu ändern, die den zentralen Verwaltungsspeicher hostet.</span><span class="sxs-lookup"><span data-stu-id="f7d64-108">In addition, you cannot use the **Edit Properties** dialog box to change the instance of SQL Server that hosts the Central Management store.</span></span>
  
## <a name="editing-the-properties-of-a-sql-server-database"></a><span data-ttu-id="f7d64-109">Bearbeiten der Eigenschaften einer SQL Server Datenbank</span><span class="sxs-lookup"><span data-stu-id="f7d64-109">Editing the Properties of a SQL Server Database</span></span>

<span data-ttu-id="f7d64-110">Zum Ändern der Instanz von SQL Server, die von einer anderen Datenbank als dem zentralen Verwaltungsspeicher verwendet wird, führen Sie das folgende Verfahren im Topologie-Generator aus:</span><span class="sxs-lookup"><span data-stu-id="f7d64-110">To change the instance of SQL Server that is used by any database other than the Central Management store, complete the following procedure in Topology Builder:</span></span>
  
### <a name="to-modify-an-instance-of-sql-server"></a><span data-ttu-id="f7d64-111">So ändern Sie eine Instanz von SQL Server</span><span class="sxs-lookup"><span data-stu-id="f7d64-111">To modify an instance of SQL Server</span></span>

1. <span data-ttu-id="f7d64-112">Wählen Sie unter dem Knoten **SQL-Speicher** die gewünschte Datenbank aus, und klicken Sie auf **Eigenschaften bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f7d64-112">Select the appropriate database under the **SQL stores** node, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="f7d64-113">Führen Sie im Dialogfeld **Eigenschaften bearbeiten** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f7d64-113">In the **Edit Properties** dialog box, do one of the following:</span></span>
    
   - <span data-ttu-id="f7d64-114">Wenn Sie die Standard SQL Server Instanz verwenden möchten, wählen Sie **Standardinstanz** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7d64-114">To use the default SQL Server instance, select **Default Instance** and then click **OK**.</span></span>
    
   - <span data-ttu-id="f7d64-115">Wählen Sie zum Verwenden einer benannten Datenbankinstanz die Option **Benannte Instanz** aus, geben Sie den Instanznamen in das Textfeld ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f7d64-115">To use a named database instance, select **Named Instance**, enter the instance name in the text box, and then click **OK**.</span></span> <span data-ttu-id="f7d64-116">Geben Sie nur den Namen der Instanz ein (beispielsweise ArchivingInstance), und nicht den gesamten SQL Server Pfad.</span><span class="sxs-lookup"><span data-stu-id="f7d64-116">You should enter only the instance name (for example, ArchivingInstance), and not the entire SQL Server path.</span></span>
    
<span data-ttu-id="f7d64-117">Wenn Sie im Dialogfeld **Eigenschaften bearbeiten** arbeiten, überprüft der Topologie-Generator nicht, ob es sich bei der Datenbankinstanz, die Sie eingegeben haben, um eine gültige Instanz handelt.</span><span class="sxs-lookup"><span data-stu-id="f7d64-117">When you are working in the **Edit Properties** dialog box, Topology Builder will not verify that the database instance that you have entered is a valid instance.</span></span> <span data-ttu-id="f7d64-118">Wenn Sie beispielsweise versehentlich typeArchivingInstanec als Instanzname und dann auf **OK**klicken, akzeptiert Topologie-Generator diese ungültige Instanz.</span><span class="sxs-lookup"><span data-stu-id="f7d64-118">For example, if you inadvertently typeArchivingInstanec as the instance name and then click **OK**, Topology Builder will accept that invalid instance.</span></span> <span data-ttu-id="f7d64-119">Bevor Sie diese Topologie veröffentlichen können, müssen Sie diesen Fehler korrigieren: Wenn eine SQL Server Instanz nicht gefunden werden kann, erstellt der Topologie-Generator diese Instanz nicht für Sie.</span><span class="sxs-lookup"><span data-stu-id="f7d64-119">Before you can publish this topology, you must correct this mistake: if a SQL Server instance cannot be found, Topology Builder will not create that instance for you.</span></span>
  

