---
title: Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Zusammenfassung: Erfahren Sie, wie Sie ein Update oder Patch auf eine Back-End-Server in Skype für Business Server installieren.'
ms.openlocfilehash: 14acff1aea501bf47dff95053259187570d2f990
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server-2015"></a><span data-ttu-id="a483a-103">Patchen oder Aktualisieren eines Back-End-Servers oder Standard Edition-Servers in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a483a-103">Patch or update a Back End Server or Standard Edition server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a483a-104">**Zusammenfassung:** Hier erfahren Sie, wie Sie ein Update oder Patch auf eine Back-End-Server in Skype für Business Server installieren.</span><span class="sxs-lookup"><span data-stu-id="a483a-104">**Summary:** Learn how to install an update or patch on a Back End Server in Skype for Business Server.</span></span>
  
<span data-ttu-id="a483a-105">In diesem Thema wird erläutert, wie Sie ein Update auf einen Enterprise Edition Back-End-Server oder Standard Edition-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="a483a-105">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>
  
<span data-ttu-id="a483a-106">Wenn eine Back-End-Server nach unten für mindestens 30 Minuten ist während der Aktualisierung werden, können Benutzer dann in ausfallsicherheitsmodus gehen.</span><span class="sxs-lookup"><span data-stu-id="a483a-106">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="a483a-107">Wenn die Aktualisierung abgeschlossen ist und die Back-End-Server erneut mit den Front-End-Servern im Pool verbunden ist, werden Benutzer an voller Funktionsumfang zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a483a-107">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="a483a-108">Wenn das Upgrade weniger als 30 Minuten dauert, sind die Benutzer davon nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="a483a-108">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="a483a-109">Back-End-Server oder Standard Edition-Server aktualisieren</span><span class="sxs-lookup"><span data-stu-id="a483a-109">To update a back end server or Standard Edition server</span></span>

1. <span data-ttu-id="a483a-110">Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle CsAdministrator an.</span><span class="sxs-lookup"><span data-stu-id="a483a-110">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>
    
2. <span data-ttu-id="a483a-111">Laden Sie das Update herunter und extrahieren Sie es auf die lokale Festplatte.</span><span class="sxs-lookup"><span data-stu-id="a483a-111">Download the update and extract it to the local hard disk.</span></span>
    
3. <span data-ttu-id="a483a-112">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business 2015**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a483a-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
4. <span data-ttu-id="a483a-113">Skype für Business Server-Dienste zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a483a-113">Stop Skype for Business Server services.</span></span> <span data-ttu-id="a483a-114">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-114">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

5. <span data-ttu-id="a483a-p103">Beenden Sie den WWW-Dienst (World Wide Web). Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net stop w3svc
   ```

6. <span data-ttu-id="a483a-117">Schließen Sie alle Skype für Windows Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="a483a-117">Close all Skype for Business Server Management Shell windows.</span></span>
    
7. <span data-ttu-id="a483a-118">Installieren Sie das Update.</span><span class="sxs-lookup"><span data-stu-id="a483a-118">Install the update.</span></span>
    
8. <span data-ttu-id="a483a-119">Starten Sie die Skype für Business Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Skype für Business 2015**und klicken Sie dann auf **Skype für Business Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a483a-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**..</span></span>
    
9. <span data-ttu-id="a483a-120">Skype für Business Server-Dienste erneut aus, um die globalen Assemblycache (GAC) – d Assemblys catch zu beenden.</span><span class="sxs-lookup"><span data-stu-id="a483a-120">Stop Skype for Business Server services again to catch Global Assembly Cache (GAC) -d assemblies.</span></span> <span data-ttu-id="a483a-121">Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-121">At the command line, type:</span></span>
    
    ```
    Stop-CsWindowsService
    ```

10. <span data-ttu-id="a483a-p105">Starten Sie den WWW-Dienst neu. Geben Sie in der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
    ```
    net start w3svc
    ```

11. <span data-ttu-id="a483a-124">Übernehmen Sie die vorgenommenen Änderungen für die SQL Server-Datenbanken, indem Sie einen der folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="a483a-124">Apply the changes made to the SQL Server databases by doing one of the following:</span></span>
    
    - <span data-ttu-id="a483a-125">Wenn hierbei handelt es sich um einen Enterprise Edition Back-End-Server und keine verbundenen Datenbanken auf diesem Server, wie die Archivierung oder Überwachung Datenbanken vorhanden sind, geben Sie Folgendes an der Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-125">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - <span data-ttu-id="a483a-126">Wenn hierbei handelt es sich um einen Enterprise Edition Back-End-Server und auf diesem Server gemeinsam ausgeführte Datenbanken vorhanden sind, geben Sie Folgendes an der Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-126">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - <span data-ttu-id="a483a-127">Ist dies ein Standard Edition-Server, geben Sie Folgendes an der Befehlszeile ein:</span><span class="sxs-lookup"><span data-stu-id="a483a-127">If this is an Standard Edition server, type the following at a command line:</span></span>
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```


