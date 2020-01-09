---
title: Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie ein Update oder Patch auf einem Back-End-Server in Skype for Business Server installieren.'
ms.openlocfilehash: a88224c508426d16217adb87693515314b03e40f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991500"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a><span data-ttu-id="2106d-103">Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2106d-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server</span></span>
 
<span data-ttu-id="2106d-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie ein Update oder Patch auf einem Back-End-Server in Skype for Business Server installieren.</span><span class="sxs-lookup"><span data-stu-id="2106d-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="2106d-105">In diesem Thema wird erläutert, wie Sie ein Update auf einem Enterprise Edition-Back-End-Server oder einem Standard Edition-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="2106d-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="2106d-106">Wenn ein Back-End-Server während eines Upgrades für mindestens 30 Minuten nicht mehr zur Verfügung steht, können Benutzer dann in den Widerstands Modus wechseln.</span><span class="sxs-lookup"><span data-stu-id="2106d-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="2106d-107">Wenn die Aktualisierung abgeschlossen ist und die Back-End-Server wieder mit den Front-End-Servern im Pool verbunden sind, werden die Benutzer an die vollständige Funktionalität zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2106d-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="2106d-108">Wenn das Upgrade weniger als 30 Minuten dauert, sind die Benutzer davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="2106d-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="2106d-109">Back-End-Server oder Standard Edition-Server aktualisieren</span><span class="sxs-lookup"><span data-stu-id="2106d-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="2106d-110">Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle CsAdministrator an.</span><span class="sxs-lookup"><span data-stu-id="2106d-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="2106d-111">Laden Sie das Update herunter und extrahieren Sie es auf die lokale Festplatte.</span><span class="sxs-lookup"><span data-stu-id="2106d-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="2106d-112">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="2106d-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="2106d-113">Beenden Sie die Skype for Business Server-Dienste.</span><span class="sxs-lookup"><span data-stu-id="2106d-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="2106d-114">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-114">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="2106d-115">Beenden Sie den WWW-Dienst (World Wide Web).</span><span class="sxs-lookup"><span data-stu-id="2106d-115">Stop the World Wide Web service.</span></span> <span data-ttu-id="2106d-116">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-116">At the command line, type:</span></span>
    
    ```PowerShell
    net stop w3svc
   ```

6. <span data-ttu-id="2106d-117">Schließen Sie alle Skype for Business Server-Verwaltungsshell-Fenster.</span><span class="sxs-lookup"><span data-stu-id="2106d-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="2106d-118">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="2106d-118">Install the update.</span></span>
    
8. <span data-ttu-id="2106d-119">Starten Sie die Skype for Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype for**Business, und klicken Sie dann auf **Skype for Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="2106d-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
9. <span data-ttu-id="2106d-120">Beenden Sie die Skype for Business Server-Dienste erneut, um globale Assemblycache-d-Assemblys zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="2106d-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="2106d-121">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-121">At the command line, type:</span></span>
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="2106d-p105">Starten Sie den WWW-Dienst neu. Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```PowerShell
    net start w3svc
    ```

11. <span data-ttu-id="2106d-124">Übernehmen Sie die vorgenommenen Änderungen für die SQL Server-Datenbanken, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="2106d-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="2106d-125">Wenn dies ein Enterprise Edition-Back-End-Server ist und auf diesem Server keine zusammengefassten Datenbanken wie Archivierungs-oder Überwachungsdatenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="2106d-126">Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server zusammengefasste Datenbanken vorhanden sind, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="2106d-127">Wenn es sich um einen Standard Edition-Server handelt, geben Sie Folgendes an einer Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="2106d-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
