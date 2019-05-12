---
title: Aktualisieren von Statistics Manager für Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 71f5d0a0-ca81-4ac1-b590-8f854504f21f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server zu aktualisieren.'
ms.openlocfilehash: 1349d3e67481b2f0dd8c354c01b70a33969ed51d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906718"
---
# <a name="upgrade-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="c156e-103">Aktualisieren von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c156e-103">Upgrade Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="c156e-104">**Zusammenfassung:** Gelesen Sie in diesem Thema erfahren, wie ein Upgrade Statistiken Manager für Skype für Business Server.</span><span class="sxs-lookup"><span data-stu-id="c156e-104">**Summary:** Read this topic to learn how to upgrade Statistics Manager for Skype for Business Server.</span></span>
  
<span data-ttu-id="c156e-105">In diesem Thema wird beschrieben, wie zum Aktualisieren einer vorhandenen Installation von Statistiken Manager für Skype für Business Server – ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c156e-105">This topic describes how to upgrade an existing installation of Statistics Manager for Skype for Business Server—a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="c156e-106">Sie können Leistungsdaten von Hunderten von Servern innerhalb von Sekunden abfragen und die Ergebnisse unmittelbar auf der Statistics Manager-Website anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c156e-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span> 
  
<span data-ttu-id="c156e-107">Weitere Informationen zu Statistiken Manager und die neuen Features in Version 2.0 finden Sie unter [für Statistiken Manager für Skype für Business Server planen](plan.md) und [Bereitstellen von Statistiken Manager für Skype für Business Server](deploy.md).</span><span class="sxs-lookup"><span data-stu-id="c156e-107">For more information about Statistics Manager and the new features in Release 2.0, see [Plan for Statistics Manager for Skype for Business Server](plan.md) and [Deploy Statistics Manager for Skype for Business Server](deploy.md).</span></span>
  
<span data-ttu-id="c156e-108">Es gibt zwei Verfahren für die Aktualisierung:</span><span class="sxs-lookup"><span data-stu-id="c156e-108">There are two methods for upgrading:</span></span>
  
- <span data-ttu-id="c156e-109">**Automatische Aktualisierung.**</span><span class="sxs-lookup"><span data-stu-id="c156e-109">**Automated upgrade.**</span></span> <span data-ttu-id="c156e-110">Diese Methode wird ein automatisiertes Skript verwendet.</span><span class="sxs-lookup"><span data-stu-id="c156e-110">This method uses an automated script.</span></span> <span data-ttu-id="c156e-111">Es ist die einfachste Methode und für alle Upgradeszenarien anwendbar sein.</span><span class="sxs-lookup"><span data-stu-id="c156e-111">It is the easiest method and should be applicable to all upgrade scenarios.</span></span>
    
- <span data-ttu-id="c156e-112">**Manuelle Aktualisierung.**</span><span class="sxs-lookup"><span data-stu-id="c156e-112">**Manual upgrade.**</span></span> <span data-ttu-id="c156e-113">Diese Methode wird als einen Sicherungsplan im ungewöhnliche Fall bereitgestellt, die die automatische Aktualisierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="c156e-113">This method is provided as a backup plan in the unusual case that the automated upgrade fails.</span></span>
    
## <a name="prerequisites"></a><span data-ttu-id="c156e-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c156e-114">Prerequisites</span></span>

<span data-ttu-id="c156e-115">Bevor Sie aktualisieren, stellen Sie sicher, dass Sie über die folgenden Informationen verfügen:</span><span class="sxs-lookup"><span data-stu-id="c156e-115">Before you upgrade, be sure you have the following information:</span></span>
  
- <span data-ttu-id="c156e-116">Active Listener-Zertifikatfingerabdruck</span><span class="sxs-lookup"><span data-stu-id="c156e-116">Active Listener Certificate Thumbprint</span></span>
    
- <span data-ttu-id="c156e-117">Listener-Dienst-Kennwort (eingegeben bei der Installation des Listeners und jedes Agents)</span><span class="sxs-lookup"><span data-stu-id="c156e-117">Listener Service Password (entered on install of the listener and every agent)</span></span>
    
- <span data-ttu-id="c156e-118">SSL-Zertifikat-Konfiguration für die Website</span><span class="sxs-lookup"><span data-stu-id="c156e-118">SSL Certificate configuration for the website</span></span>
    
## <a name="automated-upgrade"></a><span data-ttu-id="c156e-119">Automatische Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="c156e-119">Automated upgrade</span></span>

<span data-ttu-id="c156e-120">Das Skript wird Ihre aktuelle Zertifikatinformationen sammeln und die alte Version des Produkts deinstallieren Listener Kennwort verwenden aus, und klicken Sie dann die neue Version des Produkts installieren.</span><span class="sxs-lookup"><span data-stu-id="c156e-120">The script will gather your current certificate information and listener password, uninstall the old version of the product, and then install the new version of the product.</span></span> <span data-ttu-id="c156e-121">Die Redis-Instanz auf dem Server installiert wird nicht verschoben werden, damit im Cache gespeicherten Daten über den Upgradeprozess beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c156e-121">The Redis instance installed on the server will not be touched, so any data stored in the cache will be retained through the upgrade process.</span></span>
  
1. <span data-ttu-id="c156e-122">Platzieren Sie die MSI-Dateien für die neue Version der Agent, Listener und Website zusammen mit der Update-StatsMan.ps1-Skript in einem gemeinsamen Ordner auf dem Computer Listener.</span><span class="sxs-lookup"><span data-stu-id="c156e-122">Place the MSI files for the new version of the agent, listener and website along with the Update-StatsMan.ps1 script into a single folder on the Listener computer.</span></span>
    
2. <span data-ttu-id="c156e-123">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="c156e-123">Open an administrative PowerShell window.</span></span> <span data-ttu-id="c156e-124">Aktualisieren Sie die Listener-Komponente:</span><span class="sxs-lookup"><span data-stu-id="c156e-124">Upgrade the Listener component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Listener
   ```

> [!NOTE]
> <span data-ttu-id="c156e-125">Das Statistiken Manager-Dienstkennwort wird unverschlüsselt in der Befehlszeile wie es an das Installationsprogramm übergeben wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c156e-125">The Statistics Manager service password will be displayed in clear text on the command line as it is passed to the installer.</span></span> <span data-ttu-id="c156e-126">Achten Sie darauf, Ihren Bildschirm bei Bedarf entsprechend abzudecken.</span><span class="sxs-lookup"><span data-stu-id="c156e-126">Be sure to shield your monitor as needed.</span></span> 
  
1. <span data-ttu-id="c156e-127">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="c156e-127">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="c156e-128">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="c156e-128">Answer Yes.</span></span>
    
2. <span data-ttu-id="c156e-129">Wenn der Listenerdienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c156e-129">If the Listener service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="c156e-130">Ermöglichen der Anwendung, schließen (der Dienst beendet werden soll, Statistiken Manager-Listener).</span><span class="sxs-lookup"><span data-stu-id="c156e-130">Allow the application to close (the Statistics Manager Listener service will be stopped).</span></span>
    
3. <span data-ttu-id="c156e-131">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="c156e-131">Continue the install process.</span></span> <span data-ttu-id="c156e-132">Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind.</span><span class="sxs-lookup"><span data-stu-id="c156e-132">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="c156e-133">Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c156e-133">If not, add the values you saved before continuing.</span></span>
    
4. <span data-ttu-id="c156e-134">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="c156e-134">Open an administrative PowerShell window.</span></span> <span data-ttu-id="c156e-135">Aktualisieren Sie die Website-Komponente:</span><span class="sxs-lookup"><span data-stu-id="c156e-135">Upgrade the Website component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Website
   ```

5. <span data-ttu-id="c156e-136">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="c156e-136">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="c156e-137">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="c156e-137">Answer Yes.</span></span>
    
6. <span data-ttu-id="c156e-138">Wenn der Agent-Dienst ausgeführt wird, werden Sie aufgefordert, die Anwendung zu schließen, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c156e-138">If the Agent service is running, you will be prompted to close the application before continuing.</span></span> <span data-ttu-id="c156e-139">Warten Sie, bis die Anwendung geschlossen ist (der StatsMan-Agent-Dienst wird beendet).</span><span class="sxs-lookup"><span data-stu-id="c156e-139">Allow the application to close (the StatsMan Agent service will be stopped).</span></span>
    
7. <span data-ttu-id="c156e-140">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="c156e-140">Continue the install process.</span></span> <span data-ttu-id="c156e-141">Beachten Sie, dass Eintragungen für das Dienstkennwort und den Zertifikatfingerabdruck bereits im Voraus vorgenommen worden sind.</span><span class="sxs-lookup"><span data-stu-id="c156e-141">You should notice that the service password and certificate thumbprint are pre-populated.</span></span> <span data-ttu-id="c156e-142">Falls das nicht der Fall ist, tragen Sie die Werte ein, die Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c156e-142">If not, add the values you saved before continuing.</span></span>
    
8. <span data-ttu-id="c156e-143">Öffnen Sie ein PowerShell-Verwaltungsfenster.</span><span class="sxs-lookup"><span data-stu-id="c156e-143">Open an administrative PowerShell window.</span></span> <span data-ttu-id="c156e-144">Aktualisieren Sie die Agent-Komponente:</span><span class="sxs-lookup"><span data-stu-id="c156e-144">Upgrade the Agent component:</span></span>
    
   ```
   .\Update-StatsMan.ps1 -Service Agent
   ```

9. <span data-ttu-id="c156e-145">Beim Ausführen des Skripts sollten Sie aufgefordert werden, die alte Version des Produkts zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="c156e-145">On running the script, you should be prompted to uninstall the old version of the product.</span></span> <span data-ttu-id="c156e-146">Bestätigen Sie dies mit „Ja“.</span><span class="sxs-lookup"><span data-stu-id="c156e-146">Answer Yes.</span></span>
    
10. <span data-ttu-id="c156e-147">Setzen Sie den Installationsprozess fort.</span><span class="sxs-lookup"><span data-stu-id="c156e-147">Continue the install process.</span></span> <span data-ttu-id="c156e-148">Beachten Sie, dass eine Eintragung für den Website-Port bereits im Voraus vorgenommen worden ist.</span><span class="sxs-lookup"><span data-stu-id="c156e-148">You should notice that the website port is pre-populated.</span></span> <span data-ttu-id="c156e-149">Falls das nicht der Fall ist, tragen Sie den Wert ein, den Sie zuvor gespeichert haben, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c156e-149">If not, add the value you saved before continuing.</span></span>
    
11. <span data-ttu-id="c156e-150">Stellen Sie mithilfe des Browsers sicher, dass die Website wie erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="c156e-150">Verify the website is working as expected using the browser.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c156e-151">Die Agent-Aktualisierung verwendet werden kann mit der Option - NoPrompt.</span><span class="sxs-lookup"><span data-stu-id="c156e-151">The Agent upgrade can be used with the -NoPrompt switch.</span></span> <span data-ttu-id="c156e-152">Dies ermöglicht den Prozess Deinstallation/Installation im Hintergrund, führen Sie Tools wie PSExec zu Remote Ausführen des Upgrades für eine große Anzahl von Servern zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="c156e-152">This will allow the uninstall/install process to run silently, allowing tools such as PSExec to run the upgrade remotely on a large number of servers.</span></span> 
  
### <a name="manual-upgrade"></a><span data-ttu-id="c156e-153">Manuelle Aktualisierung</span><span class="sxs-lookup"><span data-stu-id="c156e-153">Manual upgrade</span></span>

<span data-ttu-id="c156e-154">Sollte aus irgendeinem Grund die automatisierte Aktualisierung fehlschlagen, können Sie jederzeit eine manuelle Aktualisierung wie folgt durchführen:</span><span class="sxs-lookup"><span data-stu-id="c156e-154">If for some reason, the automated upgrade fails, you can always perform a manual upgrade as follows:</span></span>
  
1. <span data-ttu-id="c156e-155">	Deinstallieren Sie auf dem Listener-Computer den Listener, die Website und den Agent (sofern er auf diesem Server installiert war) über die Systemsteuerung „Programme und Funktionen“.  </span><span class="sxs-lookup"><span data-stu-id="c156e-155">On the Listener computer, uninstall the Listener, Website and the Agent (if it was installed on this server) via the Programs and Features control panel.</span></span> 
    
    > [!NOTE]
    >  <span data-ttu-id="c156e-156"> Lassen Sie Redis installiert, damit die Daten im Cache während des Aktualisierungsverfahrens erhalten bleiben.</span><span class="sxs-lookup"><span data-stu-id="c156e-156">Keep Redis installed so that the data in the cache will then be maintained through the upgrade process.</span></span>
  
2. <span data-ttu-id="c156e-p118">	Installieren Sie die neuen Versionen der Komponenten einschließlich der oben gespeicherten Werte, wenn Sie dazu aufgefordert werden. Weitere Informationen zum Installieren von Komponenten finden Sie unter [Deploy Statistics Manager](deploy.md#BKMK_Deploy).</span><span class="sxs-lookup"><span data-stu-id="c156e-p118">Install the new versions of the components, including the values you saved above when prompted for them. For more information about installing components, see [Deploy Statistics Manager](deploy.md#BKMK_Deploy)</span></span>

    
## <a name="for-more-information"></a><span data-ttu-id="c156e-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c156e-159">For more information</span></span>
<span data-ttu-id="c156e-160"><a name="BKMK_Fixed"> </a></span><span class="sxs-lookup"><span data-stu-id="c156e-160"></span></span>

<span data-ttu-id="c156e-161">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c156e-161">For more information, see the following:</span></span>
  
- [<span data-ttu-id="c156e-162">Planen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c156e-162">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="c156e-163">Bereitstellen von Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c156e-163">Deploy Statistics Manager for Skype for Business Server</span></span>](deploy.md)
    
- [<span data-ttu-id="c156e-164">Behandeln von Problemen im Zusammenhang mit Statistics Manager für Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c156e-164">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
