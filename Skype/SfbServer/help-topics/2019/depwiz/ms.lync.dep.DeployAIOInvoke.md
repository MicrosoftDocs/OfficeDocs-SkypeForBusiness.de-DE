---
title: Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: Auf der Seite "Befehle ausführen" können die Aufgaben der Installation von SQL Server Express und der Konfiguration als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden. Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank mit dem Namen RTC erstellt. Außerdem werden Firewallregeln erstellt, um den ein-und ausgehenden Zugriff für Server und Clients für die Kommunikation mit der Datenbank und Instanz zu ermöglichen. Nach Abschluss der Aufgabe können Sie die Protokolldatei aus der Dropdownliste auswählen. Die Protokolldatei hat den Namen Bootstrap Local Machine. Nachdem Sie die Protokolldatei ausgewählt haben, klicken Sie auf Protokoll anzeigen. Überprüfen Sie die Protokolldatei auf Fehler und Warnungen. Wenn Sie den Vorgang fortsetzen möchten, klicken Sie auf Fertig stellen. Wenn Sie dies noch nicht getan haben, sollten Sie jetzt Ihre Topologie mit dem Topology Builder definieren.
ms.openlocfilehash: 0a1b8245df8e50ba4da73c98e9dcb865446a0ecc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796966"
---
# <a name="prepare-single-standard-edition-server-invoke"></a><span data-ttu-id="f5f4f-111">Vorbereiten eines einzelnen Standard Edition-Servers (Aufruf)</span><span class="sxs-lookup"><span data-stu-id="f5f4f-111">Prepare Single Standard Edition Server (Invoke)</span></span>
 
<span data-ttu-id="f5f4f-112">Auf der Seite " **Befehle ausführen** " können die Aufgaben der Installation von SQL Server Express und der Konfiguration als zentraler Verwaltungsspeicher im Aufgabenbereich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-112">On the **Executing commands** page, the tasks of installing the SQL Server Express and configuring to act as the Central Management store can be viewed in the task pane.</span></span> <span data-ttu-id="f5f4f-113">Standardmäßig wird eine Instanz einer SQL Server-basierten Datenbank mit dem Namen RTC erstellt.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-113">By default, an instance of a SQL Server-based database named RTC is created.</span></span> <span data-ttu-id="f5f4f-114">Außerdem werden Firewallregeln erstellt, um den ein-und ausgehenden Zugriff für Server und Clients für die Kommunikation mit der Datenbank und Instanz zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-114">Firewall rules are also created to allow inbound and outbound access for servers and clients to communicate with the database and instance.</span></span> <span data-ttu-id="f5f4f-115">Nach Abschluss der Aufgabe können Sie die Protokolldatei aus der Dropdownliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-115">After the task is completed, you can select the log file from the drop-down list.</span></span> <span data-ttu-id="f5f4f-116">Die Protokolldatei hat den Namen **Bootstrap Local Machine**.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-116">The log file is named **Bootstrap local machine**.</span></span> <span data-ttu-id="f5f4f-117">Nachdem Sie die Protokolldatei ausgewählt haben, klicken Sie auf **Protokoll anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-117">After selecting the log file, click **View Log**.</span></span> <span data-ttu-id="f5f4f-118">Überprüfen Sie die Protokolldatei auf Fehler und Warnungen.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-118">Review the log file for any errors and warnings.</span></span> <span data-ttu-id="f5f4f-119">Wenn Sie den Vorgang fortsetzen möchten, klicken Sie auf **Fertig stellen.**</span><span class="sxs-lookup"><span data-stu-id="f5f4f-119">When you are ready to proceed, click **Finish.**</span></span> <span data-ttu-id="f5f4f-120">Wenn Sie dies noch nicht getan haben, sollten Sie jetzt Ihre Topologie mit dem Topology Builder definieren.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-120">You should now define your topology with Topology Builder if you have not already done so.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f5f4f-121">Die Installation von SQL Server Express kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-121">The installation of the SQL Server Express can take some time to complete.</span></span> <span data-ttu-id="f5f4f-122">Während der Installation wird kein Status auf dem Bildschirm oder im Aufgabenbereich angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-122">During the installation, there is no progress visible on the screen or the task pane.</span></span> <span data-ttu-id="f5f4f-123">Um die Installation zu überwachen, sollten Sie den Windows Task-Manager verwenden und nach den msiexec-Prozessen und den Setup Dateien für SQL Server suchen.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-123">To monitor the installation, you should use Windows Task Manager and look for the MSIExec processes and the Setup files for SQL Server.</span></span> <span data-ttu-id="f5f4f-124">Auf diese Weise können Sie den Status der Installation anzeigen und sicherstellen, dass die Installation fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-124">In this way, you can view the status of the install and be sure that the install is proceeding.</span></span> <span data-ttu-id="f5f4f-125">In Abhängigkeit von Faktoren, die den Rahmen dieses Hilfethemas sprengen, kann es bis zu 15 Minuten dauern, bis die SQL Server-Instanz installiert wird.</span><span class="sxs-lookup"><span data-stu-id="f5f4f-125">Depending on factors beyond the scope of this help topic, it can take up to 15 minutes or more for the install the SQL Server instance to complete.</span></span> 
  

