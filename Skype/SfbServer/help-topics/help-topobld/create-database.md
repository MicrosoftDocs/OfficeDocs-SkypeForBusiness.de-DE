---
title: Erstellen der Datenbank
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
description: Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server-Speicher. Wenn Sie Datenbanken mit dem Topologie-Generator installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server-Computer oder SQL Server-Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine in der Datenbank enthaltene Datenbank installieren müssen, müssen Sie stattdessen die Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet "installieren-CsDatabase" verwenden.
ms.openlocfilehash: a4248827b7eba83534b0fdc2dc82dcaa3487e2d0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305962"
---
# <a name="create-database"></a><span data-ttu-id="ddd24-106">Erstellen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="ddd24-106">Create Database</span></span>
 
<span data-ttu-id="ddd24-107">Der Topologie-Generator bietet eine Möglichkeit zum Installieren von Datenbanken in einem SQL Server-Speicher.</span><span class="sxs-lookup"><span data-stu-id="ddd24-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="ddd24-108">Wenn Sie Datenbanken mit dem Topologie-Generator installieren, liest die Anwendung Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen SQL Server-Computer oder SQL Server-Cluster.</span><span class="sxs-lookup"><span data-stu-id="ddd24-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="ddd24-109">Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ddd24-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="ddd24-110">Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine in der Datenbank enthaltene Datenbank installieren müssen, müssen Sie stattdessen die Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet " [Installieren-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) " verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddd24-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="ddd24-111">Erstellen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="ddd24-111">Creating a Database</span></span>

1. <span data-ttu-id="ddd24-112">Klicken Sie auf den Knoten Skype for Business Server 2015, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="ddd24-112">Click the Skype for Business Server 2015 node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="ddd24-113">Wählen Sie im Dialogfeld **Datenbanken installieren** auf der Seite **Datenbank erstellen** den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des SQL Server-Speichers aus, in dem die neuen Datenbanken erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ddd24-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="ddd24-p103">Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="ddd24-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="ddd24-p104">**Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ddd24-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="ddd24-118">**Verwenden Sie die Standardeinstellungen für SQL Server-Instanzen**.</span><span class="sxs-lookup"><span data-stu-id="ddd24-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="ddd24-119">Wenn Sie diese Option auswählen, wird der integrierte Algorithmus nicht verwendet, um die Speicherorte für die Datenbankprotokolle und Datendateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ddd24-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="ddd24-120">Stattdessen werden Protokoll-und Datendateien an den Speicherorten gespeichert, die vom SQL Server-Standardpfad angegeben werden (diese Pfade müssen von einem SQL Server-Administrator in Advanced konfiguriert werden).</span><span class="sxs-lookup"><span data-stu-id="ddd24-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="ddd24-121">Datendateien werden im Standardspeicherort der SQL Server-Datendatei gespeichert, während Protokolldateien im Standardspeicherort der SQL Server-Protokolldatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ddd24-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="ddd24-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddd24-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="ddd24-123">Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ddd24-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="ddd24-124">Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ddd24-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

