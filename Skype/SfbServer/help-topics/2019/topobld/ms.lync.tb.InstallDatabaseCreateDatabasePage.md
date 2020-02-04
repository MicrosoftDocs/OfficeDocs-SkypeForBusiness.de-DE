---
title: Installieren und Erstellen von Datenbanken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
ROBOTS: NOINDEX, NOFOLLOW
description: Sie wählen die Datenbanken aus, die Sie für Ihre Bereitstellung erstellen möchten. Standardmäßig wird die Datenbank auf dem definierten SQL Server auf der definierten Website erstellt, und die Datenbankdateien werden basierend auf dem SQL-Server, auf dem Sie die Datenbanken platzieren, automatisch bereitgestellt und konfiguriert.
ms.openlocfilehash: 884043cc1197c60b98c455882740d09157ab3228
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688538"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="677d4-104">Installieren und Erstellen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="677d4-104">Install and Create Databases</span></span>

<span data-ttu-id="677d4-105">Sie wählen die Datenbanken aus, die Sie für Ihre Bereitstellung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="677d4-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="677d4-106">Standardmäßig wird die Datenbank auf dem definierten SQL Server auf der definierten Website erstellt, und die Datenbankdateien werden basierend auf dem SQL-Server, auf dem Sie die Datenbanken platzieren, automatisch bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="677d4-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="677d4-107">**Wählen Sie die Datenbanken aus, die Sie erstellen möchten**: Aktivieren Sie das Kontrollkästchen für alle Datenbanken, die Sie bereitstellen und konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="677d4-107">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure.</span></span> <span data-ttu-id="677d4-108">Aktivieren Sie das Kontrollkästchen für alle oder alle Datenbanken, die bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="677d4-108">Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="677d4-109">Der SQL Server muss bereits für die Instanz (sofern vorhanden) konfiguriert sein, und Firewall-Ports müssen geöffnet sein, damit Sie der Instanz entsprechen, auf die Sie die Datenbanken bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="677d4-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="677d4-110">Ausführliche Informationen finden Sie unter [Konfigurieren von SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) .</span><span class="sxs-lookup"><span data-stu-id="677d4-110">For details, see [Configure SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="677d4-111">**Erweitert**: Klicken Sie auf den SQL Server, und klicken Sie auf die Schaltfläche **erweitert** , um Optionen für die Speicherorte der Datenbankdateien auf Ihrem SQL Server auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="677d4-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="677d4-112">Ausführliche Informationen zur Platzierung erweiterter Datenbankdateien finden Sie unter [Daten Bank Installation mithilfe der lync Server-Verwaltungsshell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx) .</span><span class="sxs-lookup"><span data-stu-id="677d4-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="677d4-113">**Zurück**: durch Klicken auf diese Schaltfläche kehren Sie zum vorherigen Bildschirm zurück (möglicherweise sind Sie nicht immer verfügbar, je nachdem, wie Sie in diesem Dialogfeld angekommen sind).</span><span class="sxs-lookup"><span data-stu-id="677d4-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="677d4-114">**Als nächstes**: Wenn Sie auf diese Schaltfläche klicken, wird Ihre Auswahl im aktuellen Dialogfeld übernommen, und Sie gelangen zum nächsten Dialogfeld zum Konfigurieren zusätzlicher Informationen.</span><span class="sxs-lookup"><span data-stu-id="677d4-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="677d4-115">**Abbrechen**: Wenn Sie auf diese Schaltfläche klicken, wird die Konfiguration beendet, und Sie können Ihre Änderungen verwerfen.</span><span class="sxs-lookup"><span data-stu-id="677d4-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="677d4-116">Einige, aber nicht alle Konfigurationsbildschirme werden Sie auffordern, wenn Sie Ihre Änderungen beenden und verwerfen möchten.</span><span class="sxs-lookup"><span data-stu-id="677d4-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="677d4-117">Wenn Sie **Ja** auswählen, wird die aktuelle Konfiguration geschlossen und die aktuelle Konfiguration geschlossen, und Sie kehren zum Topology Builder zurück.</span><span class="sxs-lookup"><span data-stu-id="677d4-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="677d4-118">Wenn Sie **Nein** auswählen, gelangen Sie zum Dialogfeld aktuelle Konfiguration zurück, in dem Sie die Konfiguration fortsetzen können.</span><span class="sxs-lookup"><span data-stu-id="677d4-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="677d4-119">**Hilfe**: Wenn Sie auf die Schaltfläche **Hilfe** klicken, werden diese Hilfeinformationen im Dialogfeld aktuelle Konfiguration angezeigt.</span><span class="sxs-lookup"><span data-stu-id="677d4-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


