---
title: Aktualisieren von Statistics Manager für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server 2015 zu aktualisieren.'
ms.openlocfilehash: d10dd5cd92fc0d7dbbb3285c43df78e8149f58c0
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374857"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server-2015"></a><span data-ttu-id="a33d6-103">Aktualisieren von Statistics Manager für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a33d6-103">Upgrade Statistics Manager for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a33d6-104">**Zusammenfassung:** Gelesen Sie in diesem Thema erfahren, wie ein Upgrade Statistiken Manager für Skype für Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a33d6-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a33d6-105">In diesem Thema wird beschrieben, wie zum Aktualisieren einer vorhandenen Installation von Statistiken Manager für Skype für Business Server – ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a33d6-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="a33d6-106">Sie können Leistungsdaten auf Hunderten von Servern kurzen Abständen Abfragen und sofort Anzeigen der Ergebnisse auf der Website Statistiken-Managers.</span><span class="sxs-lookup"><span data-stu-id="a33d6-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="a33d6-107">Weitere Informationen zu Statistiken Manager und die neuen Features in Version 1.1 finden Sie unter [für Statistiken Manager für Skype für Business Server 2015 planen](plan.md) und [Bereitstellen von Statistiken Manager für Skype für Business Server 2015](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="a33d6-107">For more information about Statistics Manager and the new features in Release 1.1, see [Plan for Statistics Manager for Skype for Business Server 2015](plan.md) and [Deploy Statistics Manager for Skype for Business Server 2015](deploy.md).</span></span> <span data-ttu-id="a33d6-108">Informationen zu bekannten Problemen, die in Version 1.1 behoben sind, finden Sie unter [Bekannte Probleme, die in Version 1.1 behoben wurden](upgrade.md#BKMK_Fixed).</span><span class="sxs-lookup"><span data-stu-id="a33d6-108">For information about known issues fixed in Release 1.1, see [Known issues fixed in release 1.1](upgrade.md#BKMK_Fixed).</span></span>
  
<span data-ttu-id="a33d6-109">Es gibt zwei Verfahren für die Aktualisierung:</span><span class="sxs-lookup"><span data-stu-id="a33d6-109">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="a33d6-110">**Automatische Aktualisierung.**</span><span class="sxs-lookup"><span data-stu-id="a33d6-110">**Automated upgrade.**</span></span> <span data-ttu-id="a33d6-111">Diese Methode wird ein automatisiertes Skript verwendet.</span><span class="sxs-lookup"><span data-stu-id="a33d6-111">This method uses an automated script.</span></span> <span data-ttu-id="a33d6-112">Es ist die einfachste Methode und für alle Upgradeszenarien anwendbar sein.</span><span class="sxs-lookup"><span data-stu-id="a33d6-112">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="a33d6-113">**Manuelle Aktualisierung.**</span><span class="sxs-lookup"><span data-stu-id="a33d6-113">**Manual upgrade.**</span></span> <span data-ttu-id="a33d6-114">Diese Methode wird als einen Sicherungsplan im ungewöhnliche Fall bereitgestellt, die die automatische Aktualisierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a33d6-114">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="a33d6-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a33d6-115">Prerequisites</span></span>

<span data-ttu-id="a33d6-116">Bevor Sie aktualisieren, stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:</span><span class="sxs-lookup"><span data-stu-id="a33d6-116">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="a33d6-117">Active Listener-Zertifikatfingerabdruck</span><span class="sxs-lookup"><span data-stu-id="a33d6-117">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="a33d6-118">Listener-Dienst-Kennwort (eingegeben bei der Installation des Listeners und jedes Agents)</span><span class="sxs-lookup"><span data-stu-id="a33d6-118">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="a33d6-119">SSL-Zertifikat-Konfiguration für die Website</span><span class="sxs-lookup"><span data-stu-id="a33d6-119">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="a33d6-120">Automatische Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="a33d6-120">Automated upgrade</span></span>

<span data-ttu-id="a33d6-121">Das Skript wird Ihre aktuelle Zertifikatinformationen sammeln und die alte Version des Produkts deinstallieren Listener Kennwort verwenden aus, und klicken Sie dann die neue Version des Produkts installieren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-121">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="a33d6-122">Die Redis-Instanz auf dem Server installiert wird nicht verschoben werden, damit im Cache gespeicherten Daten über den Upgradeprozess beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="a33d6-122">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="a33d6-123">Platzieren Sie die MSI-Dateien für die neue Version der Agent, Listener und Website zusammen mit der Update-StatsMan.ps1-Skript in einem gemeinsamen Ordner auf dem Computer Listener.</span><span class="sxs-lookup"><span data-stu-id="a33d6-123">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="a33d6-124">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="a33d6-124">Open an administrative PowerShell window.</span></span> <span data-ttu-id="a33d6-125">Aktualisieren Sie die Listener-Komponente:</span><span class="sxs-lookup"><span data-stu-id="a33d6-125">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="a33d6-126">Das Statistiken Manager-Dienstkennwort wird unverschlüsselt in der Befehlszeile wie es an das Installationsprogramm übergeben wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a33d6-126">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="a33d6-127">Achten Sie darauf, Ihren Bildschirm bei Bedarf entsprechend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="a33d6-127">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="a33d6-128">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-128">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="a33d6-129">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="a33d6-129">Answer Yes.</span></span>
    
2. <span data-ttu-id="a33d6-130">Wenn der Listenerdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-130">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="a33d6-131">Ermöglichen der Anwendung, schließen (der Dienst beendet werden soll, Statistiken Manager-Listener).</span><span class="sxs-lookup"><span data-stu-id="a33d6-131">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="a33d6-132">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="a33d6-132">Continue the install process.</span></span> <span data-ttu-id="a33d6-133">Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind.</span><span class="sxs-lookup"><span data-stu-id="a33d6-133">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="a33d6-134">Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-134">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="a33d6-135">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="a33d6-135">Open an administrative PowerShell window.</span></span> <span data-ttu-id="a33d6-136">Aktualisieren Sie die Website-Komponente:</span><span class="sxs-lookup"><span data-stu-id="a33d6-136">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="a33d6-137">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-137">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="a33d6-138">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="a33d6-138">Answer Yes.</span></span>
    
6. <span data-ttu-id="a33d6-139">Wenn der Agent-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-139">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="a33d6-140">Warten Sie, bis die Anwendung geschlossen ist (der StatsMan-Agent-Dienst wird beendet).</span><span class="sxs-lookup"><span data-stu-id="a33d6-140">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="a33d6-141">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="a33d6-141">Continue the install process.</span></span> <span data-ttu-id="a33d6-142">Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind.</span><span class="sxs-lookup"><span data-stu-id="a33d6-142">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="a33d6-143">Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-143">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="a33d6-144">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="a33d6-144">Open an administrative PowerShell window.</span></span> <span data-ttu-id="a33d6-145">Aktualisieren Sie die Agent-Komponente:</span><span class="sxs-lookup"><span data-stu-id="a33d6-145">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="a33d6-146">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-146">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="a33d6-147">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="a33d6-147">Answer Yes.</span></span>
    
10. <span data-ttu-id="a33d6-148">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="a33d6-148">Continue the install process.</span></span> <span data-ttu-id="a33d6-149">Beachten Sie, dass eine Eintragung für den Website-Port bereits im Voraus vorgenommen worden ist.</span><span class="sxs-lookup"><span data-stu-id="a33d6-149">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="a33d6-150">Falls das nicht der Fall ist, tragen Sie den Wert ein, den Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="a33d6-150">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="a33d6-151">Stellen Sie mithilfe des Browsers sicher, dass die Website wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="a33d6-151">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a33d6-152">Die Agent-Aktualisierung verwendet werden kann mit der Option - NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="a33d6-152">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="a33d6-153">Dies ermöglicht den Prozess Deinstallation/Installation im Hintergrund, führen Sie Tools wie PSExec zu Remote Ausführen des Upgrades für eine große Anzahl von Servern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a33d6-153">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="a33d6-154">Manuelle Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="a33d6-154">Manual upgrade</span></span>

<span data-ttu-id="a33d6-155">Sollte aus irgendeinem Grund die automatisierte Aktualisierung fehlschlagen, können Sie jederzeit eine manuelle Aktualisierung wie folgt durchführen:</span><span class="sxs-lookup"><span data-stu-id="a33d6-155">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="a33d6-156">	Deinstallieren Sie auf dem Listener-Computer den Listener, die Website und den Agent (sofern er auf diesem Server installiert war) über die Systemsteuerung „Programme und Funktionen“.  </span><span class="sxs-lookup"><span data-stu-id="a33d6-156">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="a33d6-157"> Lassen Sie Redis installiert, damit die Daten im Cache während des Aktualisierungsverfahrens erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="a33d6-157">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="a33d6-p119">	Installieren Sie die neuen Versionen der Komponenten einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="a33d6-p119">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>
    
## <a name="known-issues-fixed-in-release-11"></a><span data-ttu-id="a33d6-160">Bekannte Probleme, die in Version 1.1 behoben wurden</span><span class="sxs-lookup"><span data-stu-id="a33d6-160">Known issues fixed in release 1.1</span></span>
<span data-ttu-id="a33d6-161"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="a33d6-161"></span></span>

<span data-ttu-id="a33d6-162">Die folgenden bekannten Probleme wurden in der Version 1.1 behoben:</span><span class="sxs-lookup"><span data-stu-id="a33d6-162">The following known issues have been fixed in release 1.1:</span></span>
  
- <span data-ttu-id="a33d6-163">Benutzeroberfläche/Server/Agent - zahlreiche erhebliche Zuverlässigkeit und Leistung bei</span><span class="sxs-lookup"><span data-stu-id="a33d6-163">UI/Server/Agent - Numerous significant reliability and performance improvements</span></span>
    
- <span data-ttu-id="a33d6-164">UI - Main Filtersteuerelement jetzt sortiert ordnungsgemäß mit anderen Fällen (wurde, führt Personen vorstellen bestimmte Servern im System nicht waren, wenn ihr Gesprächspartner direkt)</span><span class="sxs-lookup"><span data-stu-id="a33d6-164">UI - Main filter control now sorts correctly with different cases (was leading people to think certain servers weren't in the system when they were)</span></span>
    
- <span data-ttu-id="a33d6-165">Server – Serverkomponenten werden jetzt auch auf nicht englischsprachigen Servern installiert.</span><span class="sxs-lookup"><span data-stu-id="a33d6-165">Server - Server components will now install on non-English servers.</span></span>
    
- <span data-ttu-id="a33d6-166">Server/Agent – In einigen Fällen wurden Agent- und Serverkomponenten im Zusammenhang mit .NET-Fehlern in Bezug auf eine bestimmte Version von .NET 4.0 nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="a33d6-166">Server/Agent - In some cases, agent and server components would not install with .NET errors due to a specific version of .NET 4.0.</span></span> <span data-ttu-id="a33d6-167">Dieser Fehler wurde behoben.</span><span class="sxs-lookup"><span data-stu-id="a33d6-167">This has been resolved.</span></span>
    
- <span data-ttu-id="a33d6-168">Agent - erweiterte Protokollierung für den StatsMan Agent hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a33d6-168">Agent - Extended event logging added for the StatsMan Agent.</span></span> <span data-ttu-id="a33d6-169">Der Agent wird nicht mehr bei der Installation auf einem Server nicht in der Topologie abstürzen, dies wird jetzt im Ereignisprotokoll zusammen mit zahlreichen möglichen fehlerbedingungen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="a33d6-169">The agent will no longer crash when installed on a server not in the topology, this will now be logged in the event log, along with many other possible error conditions.</span></span>
    
- <span data-ttu-id="a33d6-170">UI - Webclients mithilfe des Chrome-Browsers würde mehrere Anmeldung fordert sehen, wenn mit einem Clientcomputer nicht mit der gleichen Arbeitsgruppe oder Domäne als Statistiken Manager Webserver verbunden.</span><span class="sxs-lookup"><span data-stu-id="a33d6-170">UI - Web clients using the Chrome browser would see multiple login prompts when using a client computer not joined to the same workgroup or domain as the Statistics Manager Web server.</span></span> <span data-ttu-id="a33d6-171">Jetzt sollte pro Sitzung nur eine einzige Anmeldung notwendig sein.</span><span class="sxs-lookup"><span data-stu-id="a33d6-171">Now only a single login should be required per session.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="a33d6-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a33d6-172">For more information</span></span>
<span data-ttu-id="a33d6-173"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="a33d6-173"></span></span>

<span data-ttu-id="a33d6-174">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a33d6-174">For more information, see the following:</span></span>
  
- [<span data-ttu-id="a33d6-175">Planen der Business Server 2015 für Statistiken Manager für Skype</span><span class="sxs-lookup"><span data-stu-id="a33d6-175">Plan for Statistics Manager for Skype for Business Server 2015</span></span>](plan.md)
    
- [<span data-ttu-id="a33d6-176">Bereitstellen von Statistics Manager für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a33d6-176">Deploy Statistics Manager for Skype for Business Server 2015</span></span>](deploy.md)
    
- [<span data-ttu-id="a33d6-177">Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a33d6-177">Troubleshoot Statistics Manager for Skype for Business Server 2015</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="a33d6-178">Skype für Business Server Statistiken Manager-blog</span><span class="sxs-lookup"><span data-stu-id="a33d6-178">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

