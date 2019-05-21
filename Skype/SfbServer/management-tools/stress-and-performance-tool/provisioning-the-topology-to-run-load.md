---
title: Bereitstellen der Topologie zum Ausführen der Auslastung in Stress-und Leistungs Szenarien
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Änderungen oder Bereitstellung von Skype for Business Server 2015-Topologie, um Benutzern das erfolgreiche Ausführen des Stress-und Leistungstools zu ermöglichen.
ms.openlocfilehash: c7cdc10b3667ac99376904c81309df739e49844a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299702"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a><span data-ttu-id="ffe8c-103">Bereitstellen der Topologie zum Ausführen der Auslastung in Stress-und Leistungs Szenarien</span><span class="sxs-lookup"><span data-stu-id="ffe8c-103">Provisioning the topology to run load in Stress and Performance scenarios</span></span>
 
<span data-ttu-id="ffe8c-104">Änderungen oder Bereitstellung von Skype for Business Server 2015-Topologie, um Benutzern das erfolgreiche Ausführen des Stress-und Leistungstools zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-104">Skype for Business Server 2015 topology changes or provisioning to allow users to successfully run the Stress and Performance tool.</span></span>
  
<span data-ttu-id="ffe8c-105">Je nach Ihren vorhandenen Einstellungen und der Konfiguration für Ihre Bereitstellung von Skype for Business Server 2015 müssen Sie möglicherweise einige Änderungen in Ihrer Umgebung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-105">Depending on your existing settings and configuration for your deployment of Skype for Business Server 2015, you might need to make some changes in your environment.</span></span> <span data-ttu-id="ffe8c-106">Die folgende Liste enthält die folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="ffe8c-106">The following is a list of those changes:</span></span>
  
1. <span data-ttu-id="ffe8c-107">Setzen Sie die Windows PowerShell-Ausführungsrichtlinie auf Unrestricted.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-107">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="ffe8c-108">Wenn Sie nicht genau wissen, auf was Sie derzeit eingestellt ist, können Sie die Skype for Business Server-Verwaltungsshell öffnen und diesen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffe8c-108">If you're not sure what it's set to currently, you can open the Skype for Business Server Management Shell and run this command:</span></span>
    
   ```
   Get-ExecutionPolicy
   ```

   <span data-ttu-id="ffe8c-109">Wenn der Wert Unrestricted nicht zurückgegeben wird, müssen Sie Folgendes ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffe8c-109">If the value Unrestricted is not returned, you'll need to run this next:</span></span>
    
   ```
   Set-ExecutionPolicy -Unrestricted
   ```

2. <span data-ttu-id="ffe8c-110">Um Skype for Business Server effektiv zu konfigurieren, müssen Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="ffe8c-110">To effectively configure Skype for Business Server, you'll need to:</span></span>
    
    - <span data-ttu-id="ffe8c-111">Machen Sie sich mit Ihrer Skype for Business Server 2015-Topologie vertraut (wie Computernamen, Dienstinstanzen, Websitenamen und Richtlinien).</span><span class="sxs-lookup"><span data-stu-id="ffe8c-111">Be familiar with your Skype for Business Server 2015 topology (such as computer names, service instances, site names, and policies).</span></span>
    
    - <span data-ttu-id="ffe8c-112">Weisen Sie einige der Benutzer zu, die Gruppen zugeordnet sind, wie etwa Gruppen-Sammelanschlüsse (beispielsweise SIP-URIs).</span><span class="sxs-lookup"><span data-stu-id="ffe8c-112">Assign some of the users that are created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>
    
3. <span data-ttu-id="ffe8c-113">Wenn Sie ein Skript über die Befehlszeile ausführen möchten, können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="ffe8c-113">To run a script from command line, you can use:</span></span>
    
   ```
   PowerShell.exe -file <path to the file>
   ```

4. <span data-ttu-id="ffe8c-114">Nachdem Sie ein Skript aus diesem Paket ausgeführt haben, werden die resultierenden Ablaufverfolgungen in der Regel in einer Datei im gleichen Pfad gespeichert, von dem aus das Skript ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-114">Typically, after you've run a script from this package, the resulting traces will be stored in a file in the same path from where the script was run.</span></span> <span data-ttu-id="ffe8c-115">Außerdem gibt es ein Benennungsformat \<: Skript\>Name $h $ m $ s. txt.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-115">There's a naming format as well, \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="ffe8c-116">Wenn Sie also ArchivingPolicy. ps1 auf 12:15 Uhr ausgeführt haben, erhalten Sie eine Protokolldatei mit dem Namen ArchivingPolicy121500. txt.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-116">So if you ran the ArchivingPolicy.ps1 at 12:15 PM, you'll get a log file named ArchivingPolicy121500.txt.</span></span>
    
5. <span data-ttu-id="ffe8c-117">Obwohl wir diese Beispiele für Ihre Serverkonfiguration bereitgestellt haben, liegt es an Ihnen, sowohl Ihre Konfiguration zu ändern als auch nach Abschluss der Auslastungstests wiederherzustellen oder zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ffe8c-117">While we've provided these examples for your server configuration, it's up to you to both modify your configuration and restore or roll it back after you've finished running the load testing.</span></span>
    

