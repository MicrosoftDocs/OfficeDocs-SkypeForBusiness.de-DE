---
title: Aktualisieren von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie Statistics Manager für Skype for Business Server aktualisieren.'
ms.openlocfilehash: de88257b628256c47b68036852d82fb6715c043f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992502"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="9d126-103">Aktualisieren von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d126-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="9d126-104">**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie Statistics Manager für Skype for Business Server aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="9d126-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="9d126-105">In diesem Thema wird beschrieben, wie Sie eine vorhandene Installation von Statistics Manager für Skype for Business Server aktualisieren – ein leistungsfähiges Tool, mit dem Sie Skype for Business Server-Integritäts-und-Leistungsdaten in Echtzeit anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="9d126-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="9d126-106">Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d126-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="9d126-107">Weitere Informationen zum Statistik-Manager und zu den neuen Features in Release 2,0 finden Sie unter [Planen von Statistics Manager für Skype for Business Server](plan.md) und [Bereitstellen von Statistics Manager für Skype for Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="9d126-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="9d126-108">Es gibt zwei Verfahren für die Aktualisierung:</span><span class="sxs-lookup"><span data-stu-id="9d126-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="9d126-109">**Automatische Aktualisierung.**</span><span class="sxs-lookup"><span data-stu-id="9d126-109">**Automated upgrade.**</span></span> <span data-ttu-id="9d126-110">Diese Methode verwendet ein automatisches Skript.</span><span class="sxs-lookup"><span data-stu-id="9d126-110">This method uses an automated script.</span></span> <span data-ttu-id="9d126-111">Dies ist die einfachste Methode, die für alle Upgrade-Szenarien gelten sollte.</span><span class="sxs-lookup"><span data-stu-id="9d126-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="9d126-112">**Manuelle Aktualisierung.**</span><span class="sxs-lookup"><span data-stu-id="9d126-112">**Manual upgrade.**</span></span> <span data-ttu-id="9d126-113">Diese Methode wird im ungewöhnlichen Fall als Sicherungsplan bereitgestellt, wenn das automatisierte Upgrade fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="9d126-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="9d126-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9d126-114">Prerequisites</span></span>

<span data-ttu-id="9d126-115">Bevor Sie aktualisieren, stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:</span><span class="sxs-lookup"><span data-stu-id="9d126-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="9d126-116">Active Listener-Zertifikatfingerabdruck</span><span class="sxs-lookup"><span data-stu-id="9d126-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="9d126-117">Listener-Dienst-Kennwort (eingegeben bei der Installation des Listeners und jedes Agents)</span><span class="sxs-lookup"><span data-stu-id="9d126-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="9d126-118">SSL-Zertifikat-Konfiguration für die Website</span><span class="sxs-lookup"><span data-stu-id="9d126-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="9d126-119">Automatische Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="9d126-119">Automated upgrade</span></span>

<span data-ttu-id="9d126-120">Das Skript sammelt Ihre aktuellen Zertifikatinformationen und das Listener-Kennwort, deinstallieren die alte Version des Produkts und installieren dann die neue Version des Produkts.</span><span class="sxs-lookup"><span data-stu-id="9d126-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="9d126-121">Die auf dem Server installierte Instanz von "auf dem Server" wird nicht berührt, sodass alle im Cache gespeicherten Daten über den Upgradeprozess aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="9d126-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="9d126-122">Platzieren Sie die MSI-Dateien für die neue Version des Agents, Listener und der Website zusammen mit dem Update-StatsMan. ps1-Skript in einem einzelnen Ordner auf dem Listener-Computer.</span><span class="sxs-lookup"><span data-stu-id="9d126-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="9d126-123">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="9d126-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="9d126-124">Aktualisieren Sie die Listener-Komponente:</span><span class="sxs-lookup"><span data-stu-id="9d126-124">Upgrade the Listener component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="9d126-125">Das Kennwort des Statistik-Manager-Diensts wird in Klartext in der Befehlszeile angezeigt, wenn es an das Installationsprogramm übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="9d126-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="9d126-126">Achten Sie darauf, Ihren Bildschirm bei Bedarf entsprechend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="9d126-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="9d126-127">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="9d126-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="9d126-128">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="9d126-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="9d126-129">Wenn der Listenerdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9d126-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="9d126-130">Zulassen, dass die Anwendung geschlossen wird (der Statistik-Manager-Listener-Dienst wird beendet).</span><span class="sxs-lookup"><span data-stu-id="9d126-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="9d126-131">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="9d126-131">Continue the install process.</span></span> <span data-ttu-id="9d126-132">Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind.</span><span class="sxs-lookup"><span data-stu-id="9d126-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="9d126-133">Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9d126-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="9d126-134">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="9d126-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="9d126-135">Aktualisieren Sie die Website-Komponente:</span><span class="sxs-lookup"><span data-stu-id="9d126-135">Upgrade the Website component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="9d126-136">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="9d126-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="9d126-137">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="9d126-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="9d126-138">Wenn der Agent-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9d126-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="9d126-139">Warten Sie, bis die Anwendung geschlossen ist (der StatsMan-Agent-Dienst wird beendet).</span><span class="sxs-lookup"><span data-stu-id="9d126-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="9d126-140">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="9d126-140">Continue the install process.</span></span> <span data-ttu-id="9d126-141">Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind.</span><span class="sxs-lookup"><span data-stu-id="9d126-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="9d126-142">Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9d126-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="9d126-143">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="9d126-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="9d126-144">Aktualisieren Sie die Agent-Komponente:</span><span class="sxs-lookup"><span data-stu-id="9d126-144">Upgrade the Agent component:</span></span>
    
   ```PowerShell
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="9d126-145">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="9d126-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="9d126-146">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="9d126-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="9d126-147">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="9d126-147">Continue the install process.</span></span> <span data-ttu-id="9d126-148">Beachten Sie, dass eine Eintragung für den Website-Port bereits im Voraus vorgenommen worden ist.</span><span class="sxs-lookup"><span data-stu-id="9d126-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="9d126-149">Falls das nicht der Fall ist, tragen Sie den Wert ein, den Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9d126-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="9d126-150">Stellen Sie mithilfe des Browsers sicher, dass die Website wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9d126-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9d126-151">Das Agent-Upgrade kann mit der Schalter-noprompt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d126-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="9d126-152">Auf diese Weise kann der Deinstallations-/Installationsvorgang im Hintergrund ausgeführt werden, sodass Tools wie PSExec das Upgrade Remote auf einer Vielzahl von Servern durchführen können.</span><span class="sxs-lookup"><span data-stu-id="9d126-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="9d126-153">Manuelle Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="9d126-153">Manual upgrade</span></span>

<span data-ttu-id="9d126-154">Sollte aus irgendeinem Grund die automatisierte Aktualisierung fehlschlagen, können Sie jederzeit eine manuelle Aktualisierung wie folgt durchführen:</span><span class="sxs-lookup"><span data-stu-id="9d126-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="9d126-155">	Deinstallieren Sie auf dem Listener-Computer den Listener, die Website und den Agent (sofern er auf diesem Server installiert war) über die Systemsteuerung „Programme und Funktionen“.  </span><span class="sxs-lookup"><span data-stu-id="9d126-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="9d126-156"> Lassen Sie Redis installiert, damit die Daten im Cache während des Aktualisierungsverfahrens erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="9d126-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="9d126-p118">	Installieren Sie die neuen Versionen der Komponenten einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="9d126-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="9d126-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d126-159">For more information</span></span>
<span data-ttu-id="9d126-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="9d126-160"></span></span>

<span data-ttu-id="9d126-161">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="9d126-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="9d126-162">Planen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d126-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="9d126-163">Bereitstellen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d126-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="9d126-164">Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d126-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
