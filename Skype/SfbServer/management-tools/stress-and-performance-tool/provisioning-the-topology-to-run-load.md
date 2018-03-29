---
title: Bereitstellung der Topologie zum Laden in Stress and Performance Szenarien ausführen
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype für Business Server 2015 topologieänderungen oder Bereitstellung für Benutzer zu das Stress and Performance-Tool erfolgreich ausgeführt.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="bbad3-103">Bereitstellung der Topologie zum Laden in Stress and Performance Szenarien ausführen</span><span class="sxs-lookup"><span data-stu-id="bbad3-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="bbad3-104">Skype für Business Server 2015 topologieänderungen oder Bereitstellung für Benutzer zu das Stress and Performance-Tool erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bbad3-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="bbad3-105">Je nach der vorhandenen Einstellungen und die Konfiguration für die Bereitstellung von Skype für Business Server 2015 müssen Sie möglicherweise einige Änderungen in Ihrer Umgebung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="bbad3-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="bbad3-106">Es folgt eine Liste mit diesen Änderungen:</span><span class="sxs-lookup"><span data-stu-id="bbad3-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="bbad3-107">Legen Sie die Windows PowerShell-Ausführungsrichtlinie nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="bbad3-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="bbad3-108">Wenn Sie nicht sicher sind, was ist können festlegen auf aktuell, Sie die Skype für Business Server-Verwaltungsshell öffnen und führen Sie diesen Befehl:</span><span class="sxs-lookup"><span data-stu-id="bbad3-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
  ```
  Get-ExecutionPolicy
  ```

  <span data-ttu-id="bbad3-109">Wenn der Wert Unrestricted nicht zurückgegeben wird, müssen Sie diesem als Nächstes ausführen:</span><span class="sxs-lookup"><span data-stu-id="bbad3-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. <span data-ttu-id="bbad3-110">Um effektiv Skype für Business Server konfigurieren, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="bbad3-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="bbad3-111">Mit Ihrer Skype für Business Server 2015 Topologie (beispielsweise Computernamen, Dienstinstanzen, Websitenamen und Richtlinien) vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="bbad3-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="bbad3-112">Weisen Sie einige Benutzer, die Gruppen erstellt werden, wie Response Group Sammelanschlüssen (beispielsweise SIP-URIs).</span><span class="sxs-lookup"><span data-stu-id="bbad3-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="bbad3-113">Wenn Sie ein Skript über die Befehlszeile ausführen, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="bbad3-113">To run a script from command line, you can use:</span></span>
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. <span data-ttu-id="bbad3-114">Nach dem Ausführen eines Skripts aus diesem Paket werden in der Regel, die sich ergebende Spuren gespeichert werden in einer Datei in demselben Pfad in dem das Skript ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="bbad3-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="bbad3-115">Es ist auch ein Namensformat \<Skriptname\>$h$m$s.txt.</span><span class="sxs-lookup"><span data-stu-id="bbad3-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="bbad3-116">Also, wenn Sie die ArchivingPolicy.ps1 12:15 Uhr ausgeführt haben, Abrufen eine Protokolldatei namens ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="bbad3-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="bbad3-117">Während es in diesen Beispielen für die Serverkonfiguration bereitgestellt haben, ist es Ihnen Ändern der Konfigurations und Wiederherstellen oder ein Rollback durchführen, Sichern Sie nach Abschluss der Auslastungstests ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bbad3-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

