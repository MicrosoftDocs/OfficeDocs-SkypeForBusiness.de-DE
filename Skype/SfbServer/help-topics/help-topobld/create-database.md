---
title: Erstellen der Datenbank
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server Speicher. Wenn Sie Datenbanken mithilfe des Topologie-Generators installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server Computer oder SQL Server Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren oder eine zusammenhängende Datenbank installieren müssen, müssen Sie stattdessen Windows PowerShell Befehlszeilenschnittstelle und das Cmdlet Install-CsDatabase verwenden.
ms.openlocfilehash: ea7daab44c6075e40e3f8a1b900fe43b84048ed5
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219506"
---
# <a name="create-database"></a><span data-ttu-id="3a250-106">Datenbank erstellen</span><span class="sxs-lookup"><span data-stu-id="3a250-106">Create Database</span></span>
 
<span data-ttu-id="3a250-107">Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server Speicher.</span><span class="sxs-lookup"><span data-stu-id="3a250-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="3a250-108">Wenn Sie Datenbanken mithilfe des Topologie-Generators installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server Computer oder SQL Server Cluster.</span><span class="sxs-lookup"><span data-stu-id="3a250-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="3a250-109">Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3a250-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="3a250-110">Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren oder eine zusammenhängende Datenbank installieren müssen, müssen Sie stattdessen Windows PowerShell Befehlszeilenschnittstelle und das Cmdlet [install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a250-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="3a250-111">Erstellen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="3a250-111">Creating a Database</span></span>

1. <span data-ttu-id="3a250-112">Klicken Sie auf den Knoten Skype for Business Server 2015, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="3a250-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="3a250-113">Wählen Sie im Dialogfeld **Datenbanken installieren** auf der Seite **Datenbank erstellen** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des SQL Server Speichers aus, in dem die neuen Datenbanken erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a250-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="3a250-p103">Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="3a250-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="3a250-p104">**Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a250-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="3a250-118">**Standardpfade der SQL Server-Instanz verwenden**.</span><span class="sxs-lookup"><span data-stu-id="3a250-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="3a250-119">Wenn Sie diese Option auswählen, wird der integrierte Algorithmus nicht verwendet, um die Speicherorte für die Datenbankprotokolle und Datendateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="3a250-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="3a250-120">Stattdessen werden Protokoll-und Datendateien an den Speicherorten gespeichert, die durch den Pfad der SQL Server Standardeinstellungen angegeben werden (diese Pfade müssen von einem SQL Server Administrator in erweitert konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="3a250-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="3a250-121">Datendateien werden im standardmäßigen SQL Server Datendateispeicherort gespeichert, während Protokolldateien am Speicherort der Standard SQL Server Protokolldatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="3a250-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="3a250-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a250-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="3a250-123">Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3a250-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="3a250-124">Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="3a250-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

