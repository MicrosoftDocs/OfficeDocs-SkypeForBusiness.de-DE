---
title: Installieren und Erstellen von Datenbanken
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Sie wählen Sie die Datenbanken, die Sie für Ihre Bereitstellung erstellen möchten. In der Standardeinstellung wird die Datenbank erstellt werden, auf dem definierten SQL Server in der definierten Site und automatisch bereitstellen und konfigurieren die Datenbankdateien basierend auf dem SQL Server, die Sie die Datenbanken auf platzieren.
ms.openlocfilehash: 70bd185b4e559215df7d3623dc5591648e718ed9
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979358"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="af26d-104">Installieren und Erstellen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="af26d-104">Install and Create Databases</span></span>
 
<span data-ttu-id="af26d-105">Sie wählen Sie die Datenbanken, die Sie für Ihre Bereitstellung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="af26d-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="af26d-106">In der Standardeinstellung wird die Datenbank erstellt werden, auf dem definierten SQL Server in der definierten Site und automatisch bereitstellen und konfigurieren die Datenbankdateien basierend auf dem SQL Server, die Sie die Datenbanken auf platzieren.</span><span class="sxs-lookup"><span data-stu-id="af26d-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>
  
 <span data-ttu-id="af26d-107">**Wählen Sie die Datenbanken, den Sie erstellen möchten**: Aktivieren Sie das Kontrollkästchen alle Datenbanken, die Sie bereitstellen und konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="af26d-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="af26d-108">Wählen Sie das Kontrollkästchen für einige oder alle Datenbanken, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="af26d-108">Select the check box of any or all databases that you will deploy.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="af26d-109">SQL Server muss bereits konfiguriert wurden für die Instanz (sofern vorhanden) und Firewallports geöffnet werden müssen, um die Instanz aufzunehmen, der Sie für die Datenbanken bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="af26d-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="af26d-110">Weitere Informationen hierzu finden Sie unter [Konfigurieren von SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="af26d-110">For details, see [Configure SQL Server](http://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>
  
 <span data-ttu-id="af26d-111">**Erweitert**: Klicken Sie auf dem SQL Server, und klicken Sie auf die Schaltfläche **Erweitert** , um Optionen für die Datenbank Speicherorte auf dem SQL Server auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="af26d-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="af26d-112">Ausführliche Informationen zum Platzieren der erweiterten Datenbankdatei finden Sie unter [Datenbank Installation mithilfe von Lync Server-Verwaltungsshell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span><span class="sxs-lookup"><span data-stu-id="af26d-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](http://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>
  
 <span data-ttu-id="af26d-113">**Zurück**: auf diese Schaltfläche, kehren Sie zurück zum vorherigen Bildschirm (möglicherweise nicht immer zur Verfügung, basierend auf, wie Sie auf dieses Dialogfeld gelangt sind).</span><span class="sxs-lookup"><span data-stu-id="af26d-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>
  
 <span data-ttu-id="af26d-114">**Weiter**: durch Klicken auf diese Schaltfläche, führt ein Commit für Ihre Auswahl im aktuellen Dialogfeld, und Sie gelangen zum nächsten Dialogfeld Weitere Informationen konfigurieren</span><span class="sxs-lookup"><span data-stu-id="af26d-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>
  
 <span data-ttu-id="af26d-115">**Abbrechen**: Beenden Sie die Konfiguration wird durch Klicken auf diese Schaltfläche, und die Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="af26d-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="af26d-116">Einige, jedoch nicht alle Konfigurationsbildschirme werden Sie aufgefordert, wenn Sie möchten, um zu beenden und Ihre Änderungen zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="af26d-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="af26d-117">Bei Auswahl von **Ja** wird die aktuelle Konfiguration zu schließen und schließen Sie die aktuelle Konfiguration und kehren Sie zum Topologie-Generator zurück.</span><span class="sxs-lookup"><span data-stu-id="af26d-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="af26d-118">Wenn Sie **Nein** auswählen wird gelangen Sie wieder in den aktuellen Konfigurationsdialogfeld und ermöglichen Ihnen, die Konfiguration fortgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="af26d-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>
  
 <span data-ttu-id="af26d-119">**Hilfe**: durch Klicken auf die Schaltfläche **Hilfe** diese Hilfeinformationen im Zusammenhang mit der aktuellen Konfigurationsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af26d-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>
  

