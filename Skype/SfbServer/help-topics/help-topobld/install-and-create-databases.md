---
title: Installieren und Erstellen von Datenbanken
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
- ms.lync.tb.InstallDatabaseCreateDatabasePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 515754ad-1344-42dc-8219-ee973de2e4c4
description: Sie wählen die Datenbanken aus, die Sie für die Bereitstellung erstellen möchten. Standardmäßig wird die Datenbank auf dem definierten SQL Server des definierten Standorts erstellt, und die Datenbankdateien werden basierend auf dem SQL Server, in dem Sie die Datenbanken platzieren, automatisch bereitgestellt und konfiguriert.
ms.openlocfilehash: ade264fcda73df408f6bb323dd1e3733ccdd45f1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215386"
---
# <a name="install-and-create-databases"></a><span data-ttu-id="4cdbb-104">Installieren und Erstellen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="4cdbb-104">Install and Create Databases</span></span>

<span data-ttu-id="4cdbb-105">Sie wählen die Datenbanken aus, die Sie für die Bereitstellung erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-105">You select the databases that you want to create for your deployment.</span></span> <span data-ttu-id="4cdbb-106">Standardmäßig wird die Datenbank auf dem definierten SQL Server des definierten Standorts erstellt, und die Datenbankdateien werden basierend auf dem SQL Server, in dem Sie die Datenbanken platzieren, automatisch bereitgestellt und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-106">By default, the database will be created on the defined SQL Server in the defined site, and will automatically deploy and configure the database files based on the SQL Server you are placing the databases on.</span></span>

 <span data-ttu-id="4cdbb-p103">**Zu erstellende Datenbanken auswählen**: Aktivieren Sie die Kontrollkästchen aller Datenbanken, die Sie bereitstellen und konfigurieren möchten. Sie können beliebige einzelne oder alle Datenbanken für die Bereitstellung markieren.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-p103">**Select the databases you want to create**: Select the checkbox of any databases that you intend to deploy and configure. Select the check box of any or all databases that you will deploy.</span></span>

> [!CAUTION]
> <span data-ttu-id="4cdbb-109">Die SQL Server müssen bereits für die Instanz konfiguriert worden sein (sofern vorhanden), und die Firewall-Ports müssen geöffnet sein, damit die Instanz, für die Sie die Datenbanken bereitstellen, in die Instanz integriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-109">The SQL Server must already have been configured for the instance (if any) and firewall ports must be opened to accommodate the instance that you are deploying the databases to.</span></span> <span data-ttu-id="4cdbb-110">Ausführliche Informationen finden Sie unter [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span><span class="sxs-lookup"><span data-stu-id="4cdbb-110">For details, see [Configure SQL Server for Lync Server 2013 Preview](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx)</span></span>

 <span data-ttu-id="4cdbb-111">**Erweitert**: Klicken Sie auf die SQL Server, und klicken Sie auf die Schaltfläche **erweitert** , um Optionen für die Speicherorte der Datenbankdateien auf dem SQL Server auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-111">**Advanced**: Click on the SQL Server and click the **Advanced** button to choose options for the database file locations on your SQL Server.</span></span> <span data-ttu-id="4cdbb-112">Ausführliche Informationen zu den erweiterten Optionen für die Anordnung von Datenbankdateien finden Sie unter [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx).</span><span class="sxs-lookup"><span data-stu-id="4cdbb-112">For details on advanced database file placement, see [Database Installation Using Lync Server Management Shell](https://technet.microsoft.com/library/c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c.aspx)</span></span>

 <span data-ttu-id="4cdbb-113">**Zurück**: Wenn Sie auf diese Schaltfläche klicken, gelangen Sie zurück zum vorherigen Bildschirm (je nach Navigation zu diesem Dialogfeld nicht immer verfügbar).</span><span class="sxs-lookup"><span data-stu-id="4cdbb-113">**Back**: Clicking this button returns you to the previous screen (may not always be available, based on how you arrived at this dialog).</span></span>

 <span data-ttu-id="4cdbb-114">**Weiter**: Wenn Sie auf diese Schaltfläche klicken, wird Ihre Auswahl im aktuellen Dialogfeld übernommen, und Sie gelangen zum nächsten Dialogfeld, in dem Sie weitere Informationen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-114">**Next**: Clicking this button commits your selection on the current dialog and takes you to the next dialog for configuring additional information</span></span>

 <span data-ttu-id="4cdbb-115">**Abbrechen**: Wenn Sie auf diese Schaltfläche klicken, wird die Konfiguration beendet, und Ihre Änderungen werden verworfen.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-115">**Cancel**: Clicking this button will quit the configuration and discard your changes.</span></span> <span data-ttu-id="4cdbb-116">Auf einigen Konfigurationsbildschirmen werden Sie in einer Meldung gefragt, ob Sie den Vorgang beenden und Ihre Änderungen verwerfen möchten.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-116">Some, but not all configuration screens will prompt you if you want to quit and discard your changes.</span></span> <span data-ttu-id="4cdbb-117">Wenn Sie **Ja** auswählen, wird die aktuelle Konfiguration geschlossen, und die aktuelle Konfiguration wird geschlossen, und Sie kehren zum Topologie-Generator zurück.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-117">Selecting **Yes** will close the current configuration and close the current configuration and return you to Topology Builder.</span></span> <span data-ttu-id="4cdbb-118">Wenn Sie **Nein** wählen, gelangen Sie zum aktuellen Dialogfeld für die Konfiguration zurück und können die Konfiguration fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-118">Selecting **No** will return you to the current configuration dialog and allow you to continue the configuration.</span></span>

 <span data-ttu-id="4cdbb-119">**Hilfe**: Wenn Sie auf die Schaltfläche **Hilfe** klicken, werden diese Hilfeinformationen zum aktuellen Konfigurationsdialogfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4cdbb-119">**Help**: Clicking the **Help** button displays this help information associated with the current configuration dialog.</span></span>


