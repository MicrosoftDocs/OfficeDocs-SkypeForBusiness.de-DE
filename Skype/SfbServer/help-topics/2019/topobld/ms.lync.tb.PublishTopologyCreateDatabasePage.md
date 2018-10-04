---
title: Erstellen der Datenbank
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologyCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d391619-1cab-4265-ae8a-2519993705bc
ROBOTS: NOINDEX, NOFOLLOW
description: Topologie-Generator bietet die Möglichkeit, Datenbanken auf SQL Server-Speicher zu installieren. Wenn Sie die Datenbanken mithilfe des Topologie-Generator installieren, wird die Anwendung liest Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen Computer mit SQL Server oder SQL Server-Cluster. Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist. Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine verbundene Datenbank installieren müssen, müssen Sie Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet "Install-CsDatabase" stattdessen verwenden.
ms.openlocfilehash: 648dca60cd89cc9eeec7f4787b6464f716fdcee6
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371520"
---
# <a name="create-database"></a><span data-ttu-id="5d96a-106">Erstellen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="5d96a-106">Create Database</span></span>
 
<span data-ttu-id="5d96a-107">Topologie-Generator bietet die Möglichkeit, Datenbanken auf SQL Server-Speicher zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5d96a-107">Topology Builder provides a way to install databases on a SQL Server store.</span></span> <span data-ttu-id="5d96a-108">Wenn Sie die Datenbanken mithilfe des Topologie-Generator installieren, wird die Anwendung liest Informationen aus der Topologie und installiert dann die erforderlichen Datenbanken auf dem angegebenen Computer mit SQL Server oder SQL Server-Cluster.</span><span class="sxs-lookup"><span data-stu-id="5d96a-108">When you install databases by using Topology Builder, the application reads information from the topology and then installs the required databases on the specified SQL Server computer or SQL Server cluster.</span></span> <span data-ttu-id="5d96a-109">Dies ist die einzige Art von Datenbankinstallation, die bei Verwendung des Topologie-Generators verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5d96a-109">This is the only type of database installation available by using Topology Builder.</span></span> <span data-ttu-id="5d96a-110">Wenn Sie eine bestimmte Datenbank auf einem bestimmten Computer installieren müssen oder wenn Sie eine verbundene Datenbank installieren müssen, müssen Sie Windows PowerShell-Befehlszeilenschnittstelle und das Cmdlet " [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) " stattdessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d96a-110">If you need to install a specific database on a specific computer, or if you must install a collocated database, you must use Windows PowerShell command-line interface and the [Install-CsDatabase](https://docs.microsoft.com/powershell/module/skype/install-csdatabase?view=skype-ps) cmdlet instead.</span></span>
  
### <a name="creating-a-database"></a><span data-ttu-id="5d96a-111">Erstellen einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="5d96a-111">Creating a Database</span></span>

1. <span data-ttu-id="5d96a-112">Klicken Sie auf die Skype für Business Server-Knoten, und klicken Sie dann auf **Datenbank installieren**.</span><span class="sxs-lookup"><span data-stu-id="5d96a-112">Click the Skype for Business Server node and then click **Install Database**.</span></span>
    
2. <span data-ttu-id="5d96a-113">Wählen Sie im Dialogfeld **Datenbanken installieren** auf der Seite **Datenbank erstellen** den vollqualifizierten Domänennamen (FQDN) des SQL Server-Speichers, in dem die neuen Datenbanken erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="5d96a-113">In the **Install Databases** dialog box, on the **Create Database** page, select the fully qualified domain name (FQDN) of the SQL Server store where the new databases are to be created.</span></span>
    
3. <span data-ttu-id="5d96a-p103">Klicken Sie auf **Erweitert**. Wählen Sie im Dialogfeld **Speicherort für Datenbankdateien auswählen** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="5d96a-p103">Click **Advanced**. In the **Select Database File Location** dialog box, select one of the following options:</span></span>
    
   - <span data-ttu-id="5d96a-p104">**Speicherort für Datenbankdateien automatisch bestimmen**. Bei Auswahl dieser Option verwendet der Topologie-Generator einen integrierten Algorithmus, um den Speicherort für die Datenbankprotokolle und Datendateien auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="5d96a-p104">**Automatically determine database file location**. If you select this option, Topology Builder uses a built-in algorithm to choose the storage location for the database logs and data files.</span></span>
    
   - <span data-ttu-id="5d96a-118">**Mithilfe von SQL Server-Instanz Standardwerte**.</span><span class="sxs-lookup"><span data-stu-id="5d96a-118">**Use SQL Server instance defaults**.</span></span> <span data-ttu-id="5d96a-119">Wenn Sie diese Option auswählen, wird der integrierte Algorithmus, wählen Sie die Speicherorte für die Datenbankprotokolle und Datendateien nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="5d96a-119">If you select this option, the built-in algorithm is not used to choose the storage locations for the database logs and data files.</span></span> <span data-ttu-id="5d96a-120">Protokoll- und Datendateien werden stattdessen in den durch den SQL Server-Standardeinstellungen Pfad (diese Pfade müssen in konfiguriert werden von SQL Server-Administrator erweiterte) angegebenen Speicherorten gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5d96a-120">Instead, log and data files are stored in the locations specified by the SQL Server defaults path (these paths must be configured in advanced by a SQL Server administrator).</span></span> <span data-ttu-id="5d96a-121">Datendateien werden in der SQL Server-Daten Datei Standardspeicherort gespeichert werden, während der Protokolldateien in der standardmäßigen SQL Server-Protokolldatei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5d96a-121">Data files will be stored in the default SQL Server data file location while log files will be stored in the default SQL Server log file location.</span></span>
    
4. <span data-ttu-id="5d96a-122">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5d96a-122">Click **OK**.</span></span>
    
5. <span data-ttu-id="5d96a-123">Klicken Sie auf der Seite **Datenbank erstellen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="5d96a-123">On the **Create Database** page, click **Next**.</span></span>
    
6. <span data-ttu-id="5d96a-124">Klicken Sie auf der Seite **Datenbankerstellung abgeschlossen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="5d96a-124">On the **Database Creation Complete** page, click **Finish**.</span></span>
    

