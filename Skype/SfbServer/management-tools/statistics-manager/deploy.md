---
title: Bereitstellen von Statistiken Manager für Skype für Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 37b2bb9c-c5d4-4fb0-a976-670b7594b82f
description: 'Zusammenfassung: Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server bereitstellen.'
ms.openlocfilehash: f408f494fc95fecdf0a0e80114d4d68d99181885
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532147"
---
# <a name="deploy-statistics-manager-for-skype-for-business-server"></a><span data-ttu-id="ab6ee-103">Bereitstellen von Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ab6ee-103">Deploy Statistics Manager for Skype for Business Server</span></span>
 
<span data-ttu-id="ab6ee-104">**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie Statistiken Manager für Skype für Business Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-104">**Summary:** Read this topic to learn how to deploy Statistics Manager for Skype for Business Server.</span></span>
  
 <span data-ttu-id="ab6ee-105">Statistiken-Manager für Skype für Business Server ist ein leistungsfähiges Tool, das Sie zum Anzeigen von Skype für Business Server Integrität und Leistung von Daten in Echtzeit ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-105">Statistics Manager for Skype for Business Server is a powerful tool that allows you to view Skype for Business Server health and performance data in real time.</span></span> <span data-ttu-id="ab6ee-106">Sie können Leistungsdaten auf Hunderten von Servern kurzen Abständen Abfragen und sofort Anzeigen der Ergebnisse auf der Website Statistiken-Managers.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-106">You can poll performance data across hundreds of servers every few seconds, and view the results instantly on the Statistics Manager Website.</span></span>
  
<span data-ttu-id="ab6ee-107">Bevor Sie versuchen, Statistiken Manager zu installieren, achten Sie darauf, dass Sie mit der Software, Netzwerk und Hardware Anforderungen vertraut sind.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-107">Before you attempt to install Statistics Manager, be sure you are familiar with the software, networking, and hardware requirements.</span></span> <span data-ttu-id="ab6ee-108">Weitere Informationen finden Sie unter [Planen für Statistiken Manager für Skype für Business Server](plan.md).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-108">For more information, see [Plan for Statistics Manager for Skype for Business Server](plan.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ab6ee-109">Wenn Sie von einer früheren Version von Statistiken Manager aktualisieren, finden Sie unter [Statistics-Manager für Skype für Business Server aktualisieren](upgrade.md).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-109">If you are upgrading from a previous version of Statistics Manager, see [Upgrade Statistics Manager for Skype for Business Server](upgrade.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ab6ee-110">Die Statistics Manager-Website wurde getestet und funktioniert ordnungsgemäß unter Internet Explorer 11+, Edge 20.10240+ und Chrome 46+ (aktuelle Evergreen-Version).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-110">The Statistics Manager Website has been tested and works correctly on Internet Explorer 11+, Edge 20.10240+ , and Chrome 46+ (current evergreen version).</span></span> 
  
<span data-ttu-id="ab6ee-111">Finden Sie die Statistiken Manager unter [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-111">You can find the Statistics Manager downloadable at [https://aka.ms/StatsManDownload](https://aka.ms/StatsManDownload).</span></span> 
  
<span data-ttu-id="ab6ee-112">Dieses Thema enthält die folgenden Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-112">This topic contains the following sections:</span></span>
  
- [<span data-ttu-id="ab6ee-113">Bereitstellen von Statistics Manager</span><span class="sxs-lookup"><span data-stu-id="ab6ee-113">Deploy Statistics Manager</span></span>](deploy.md#BKMK_Deploy)
    
- [<span data-ttu-id="ab6ee-114">Problembehandlung Ihrer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ab6ee-114">Troubleshoot your deployment</span></span>](deploy.md#BKMK_Troubleshoot)
    
- [<span data-ttu-id="ab6ee-115">Erstellen eines selbstsignierten Zertifikats</span><span class="sxs-lookup"><span data-stu-id="ab6ee-115">Create a self-signed certificate</span></span>](deploy.md#BKMK_SelfCert)
    
## <a name="deploy-statistics-manager"></a><span data-ttu-id="ab6ee-116">Bereitstellen von Statistics Manager</span><span class="sxs-lookup"><span data-stu-id="ab6ee-116">Deploy Statistics Manager</span></span>
<span data-ttu-id="ab6ee-117"><a name="BKMK_Deploy"> </a></span><span class="sxs-lookup"><span data-stu-id="ab6ee-117"></span></span>

<span data-ttu-id="ab6ee-118">Gehen Sie folgendermaßen vor, um Statistiken Manager bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-118">To deploy Statistics Manager, follow these steps:</span></span>
  
1. <span data-ttu-id="ab6ee-119">Bereiten Sie einen Listener-Hostcomputer vor, indem Sie das Redis-System für die InMemory-Zwischenspeicherung installieren und sicherstellen, dass die entsprechenden Zertifikate installiert sind.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-119">Prepare the Listener host machine by installing the Redis in-memory caching system, and by ensuring that you have installed the appropriate certificates.</span></span>
    
2. <span data-ttu-id="ab6ee-120">Installieren Sie den Listener-Dienst auf dem Hostcomputer. </span><span class="sxs-lookup"><span data-stu-id="ab6ee-120">Install the Listener service on the host machine.</span></span> 
    
3. <span data-ttu-id="ab6ee-121">Installieren Sie die Website auf dem Hostcomputer.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-121">Install the Website on the host machine.</span></span>
    
4. <span data-ttu-id="ab6ee-122">Installieren Sie einen Agent auf jedem Skype für Business Server-Computer, den Sie überwachen möchten.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-122">Install an Agent on each Skype for Business Server machine you wish to monitor.</span></span>
    
5. <span data-ttu-id="ab6ee-123">Importieren Sie die Topologie für die Server, die Sie überwachen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-123">Import the topology for the servers you are monitoring.</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab6ee-124">Redis, der Listener-Dienst, und die Website müssen alle auf demselben Hostcomputer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-124">Redis, the Listener service, and the Website must all be installed on the same host machine.</span></span> <span data-ttu-id="ab6ee-125">Stellen Sie sicher, dass das Hostsystem nicht Skype für Business Server installiert.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-125">Be sure the host machine does not have Skype for Business Server installed.</span></span> 
  
### <a name="prepare-the-listener-host-machine"></a><span data-ttu-id="ab6ee-126">Vorbereitung des Listener-Hostcomputers</span><span class="sxs-lookup"><span data-stu-id="ab6ee-126">Prepare the Listener host machine</span></span>

<span data-ttu-id="ab6ee-127">Um den Hostcomputer vorzubereiten, müssen Sie das Redis-System für die InMemory-Zwischenspeicherung installieren und sicherstellen, dass ein gültiges Zertifikat auf dem Computer vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-127">To prepare the host machine, you will need to install the Redis in-memory caching system, and ensure that a valid certificate is on the machine.</span></span> <span data-ttu-id="ab6ee-128">Microsoft empfiehlt die Installation des letzten stabilen Builds von Redis 3.0.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-128">Microsoft recommends that you install the latest stable build of Redis 3.0.</span></span> <span data-ttu-id="ab6ee-129">Statistiken Manager Version 2.0 wurde Redis 3.2.100 getestet.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-129">Statistics Manager version 2.0 was tested with Redis 3.2.100.</span></span> 
  
1. <span data-ttu-id="ab6ee-130">Redis von folgender Website herunterladen: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-130">Download Redis from the following site: [https://github.com/MSOpenTech/redis](https://github.com/MSOpenTech/redis).</span></span> 
    
    <span data-ttu-id="ab6ee-131">Nicht signierte Installer können hier heruntergeladen werden[https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span><span class="sxs-lookup"><span data-stu-id="ab6ee-131">Unsigned installers can be downloaded from [https://github.com/MSOpenTech/redis/releases](https://github.com/MSOpenTech/redis/releases)</span></span>
    
    <span data-ttu-id="ab6ee-132">Bei Bedarf sind signierte Binärdateien über häufig verwendete Paketmanager verfügbar: [Nuget](https://www.nuget.org/packages/Redis-64/) und [Choclatey](https://chocolatey.org/packages/redis-64).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-132">If required, signed binaries are available through popular package managers: [Nuget](https://www.nuget.org/packages/Redis-64/) and [Choclatey](https://chocolatey.org/packages/redis-64).</span></span>
    
   - <span data-ttu-id="ab6ee-133">Führen Sie die bereitgestellte MSI-Datei aus und folgen Sie den Aufforderungen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-133">Run the provided msi and follow the prompts.</span></span>
    
   - <span data-ttu-id="ab6ee-134">Das Kontrollkästchen zum Hinzufügen einer Firewallregel nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-134">Do not check the box to add a firewall rule.</span></span>
    
2. <span data-ttu-id="ab6ee-135">Der Listener-Dienst erfordert ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-135">The Listener service requires a certificate.</span></span> <span data-ttu-id="ab6ee-136">Microsoft empfiehlt, dass ein Zertifikat von einer vertrauenswürdigen Zertifizierungsstelle signiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-136">Microsoft strongly recommends that you have a certificate signed by a trusted certificate authority.</span></span> 
    
    <span data-ttu-id="ab6ee-137">Wenn Sie ein selbstsigniertes Zertifikat verwenden möchten, z. B. für Testzwecke in einem Labor, siehe [Erstellen eines selbstsignierten Zertifikats](deploy.md#BKMK_SelfCert).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-137">If you want to use a self-signed certificate--for testing purposes in a lab, for example--see [Create a self-signed certificate](deploy.md#BKMK_SelfCert).</span></span>
    
    <span data-ttu-id="ab6ee-p106">Beachten Sie, dass der Agent bei Zertifikaten die Fingerabdruck-Verifizierung verwendet (anstatt der Kettenverifizierung). Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-p106">Note that the Agent uses certificate thumbprint verification (instead of chain verification). It will not do full certificate validation because it is possible to use self-signed certificates.</span></span>
    
### <a name="install-the-listener-service"></a><span data-ttu-id="ab6ee-140">Installation des Listener-Diensts</span><span class="sxs-lookup"><span data-stu-id="ab6ee-140">Install the Listener service</span></span>

<span data-ttu-id="ab6ee-141">Installieren Sie den Listener-Dienst auf dem Hostcomputer durch Ausführen der StatsManPerfAgentListener.msi und angeben die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-141">Install the Listener service on the host machine by running the StatsManPerfAgentListener.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="ab6ee-142">Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**. </span><span class="sxs-lookup"><span data-stu-id="ab6ee-142">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="ab6ee-143">Geben Sie auf der nächsten Seite die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-143">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="ab6ee-144">**Dienstkennwort:** Dies ist das Kennwort, mit dem die Remote-Agents den Listener-Dienst authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-144">**Service Password:** This is the password the remote Agents will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="ab6ee-145">**Dienst-Port:** Dies ist die HTTPS-Portnummer, die der Listener verwendet wird, um die Kommunikation mit dem Agenten.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-145">**Service Port:** This is the HTTPS port number that the Listener will use to communicate with the Agents.</span></span> <span data-ttu-id="ab6ee-146">Bei der Installation wird dieser Port durch eine lokale Firewall durchgelassen, es wird eine URL-ACL erstellt und ein SSL-Zertifikat wird an diesen Port gebunden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-146">During installation, this port will be allowed through the local firewall, a URL ACL will be created, and an SSL cert will be bound to this port.</span></span> <span data-ttu-id="ab6ee-147">Der Standardwert ist 8443.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-147">The default is 8443.</span></span>
    
   - <span data-ttu-id="ab6ee-148">**Zertifikat Fingerabdruck:** Hierbei handelt es sich um den Fingerabdruck des Zertifikats, mit denen der Listener das HTTPS-Protokoll zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-148">**Certificate Thumbprint:** This is the certificate thumbprint the Listener will use to encrypt the HTTPS protocol.</span></span> <span data-ttu-id="ab6ee-149">Der Netzwerkdienst muss über eine Leseberechtigung für den privaten Schlüssel verfügen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-149">Network Service must have read access to the private key.</span></span>
    
     <span data-ttu-id="ab6ee-150">Klicken Sie auf die Schaltfläche **Auswählen...**, um den Fingerabdruck auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-150">Click the **Select...** button to choose the thumbprint.</span></span>
    
     <span data-ttu-id="ab6ee-151">Sie finden den Zertifikatfingerabdruck, indem Sie den Zertifikat-Manager oder den folgenden PowerShell-Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-151">You can find the Certificate thumbprint by using Certificate Manager or by using the following PowerShell command:</span></span>
    
   ```
   Get-ChildItem -path cert:\LocalMachine\My
   ```

   - <span data-ttu-id="ab6ee-152">**Dir installieren:** Dies ist das Verzeichnis auf dem die Binärdateien installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-152">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="ab6ee-153">Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-153">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="ab6ee-154">**Anwendungsdaten Dir:** Dies ist das Verzeichnis, in dem der Ordner Logs und andere Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-154">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="ab6ee-155">Sie können den Standardprotokollordner ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-155">You may change it from the default.</span></span> <span data-ttu-id="ab6ee-156">Er wird bei einer Deinstallation nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-156">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="ab6ee-157">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-157">Click **Install**.</span></span>
    
<span data-ttu-id="ab6ee-158">Um die Installation zu validieren, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-158">To validate the installation, perform the following steps:</span></span>
  
1. <span data-ttu-id="ab6ee-159">Öffnen Sie einen Browser, und navigieren Sie zuhttps://localhost:\<service-port\>/healthcheck/</span><span class="sxs-lookup"><span data-stu-id="ab6ee-159">Open a browser and navigate to https://localhost:\<service-port\>/healthcheck/</span></span>
    
    <span data-ttu-id="ab6ee-160">Die Standardeinstellung ist Dienstport 8443 (sofern Sie nicht einen anderen Port festgelegt haben).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-160">By default, the service port is 8443 (unless you specified another port).</span></span>
    
2. <span data-ttu-id="ab6ee-161">Um die ordnungsgemäße Installation des Listeners sicherzustellen, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-161">To ensure the Listener has installed properly, look for the following:</span></span>
    
   - <span data-ttu-id="ab6ee-162">Wenn die Seite für die Integritätsprüfung angezeigt wird, war die Listener-Installation erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-162">If the healthcheck page shows up, the Listener installation was successful.</span></span>
    
   - <span data-ttu-id="ab6ee-163">Wenn der KnownServersCount-Wert 1 oder höher ist, ist die Verbindung mit Redis hergestellt.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-163">If the KnownServersCount is 1 or higher, then the connection to Redis is established.</span></span>
    
   - <span data-ttu-id="ab6ee-164">Nachdem Sie einige Minuten abgewartet haben und nachdem mindestens ein Agent installiert wurde, überprüfen Sie, ob sich der Leistungsindikator erhöht.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-164">After waiting a few minutes, and after at least one Agent has been installed, check to see that the ValuesWritten counter is incrementing.</span></span>
    
### <a name="install-the-website"></a><span data-ttu-id="ab6ee-165">Installieren der Website</span><span class="sxs-lookup"><span data-stu-id="ab6ee-165">Install the Website</span></span>

<span data-ttu-id="ab6ee-166">Installieren Sie die Website auf dem Hostcomputer durch Ausführen der StatsManWebSite.msi und angeben die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-166">Install the Website on the host machine by running the StatsManWebSite.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="ab6ee-167">Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**. </span><span class="sxs-lookup"><span data-stu-id="ab6ee-167">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="ab6ee-168">Geben Sie auf der nächsten Seite die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-168">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="ab6ee-169">**Dienst-Port:** Dies ist die Portnummer an, der die Website überwacht wird.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-169">**Service Port:** This is the port number the web site will listen on.</span></span> <span data-ttu-id="ab6ee-170">Sie können sie später über eine IIS-Manager-Bindung ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-170">You can change it later by using IIS manager binding.</span></span> <span data-ttu-id="ab6ee-171">Bei der Installation wird dieser Port durch die lokale Firewall durchgelassen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-171">During installation, this port will be allowed through the local firewall.</span></span>
    
   - <span data-ttu-id="ab6ee-172">**Dir installieren:** Dies ist das Verzeichnis, in dem die Binärdateien installiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-172">**Install Dir:** This is the directory where the binaries will be installed.</span></span> <span data-ttu-id="ab6ee-173">Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-173">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="ab6ee-174">**Anwendungsdaten Dir:** Dies ist das Verzeichnis, in dem der Ordner Logs und andere Daten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-174">**AppData Dir:** This is the directory where the Logs folder and other data will be stored.</span></span> <span data-ttu-id="ab6ee-175">Sie können den Standardprotokollordner ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-175">You may change it from the default.</span></span> <span data-ttu-id="ab6ee-176">Er wird bei einer Deinstallation nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-176">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="ab6ee-177">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-177">Click **Install**.</span></span>
    
<span data-ttu-id="ab6ee-178">Um die Website anzeigen, öffnen Sie einen Browser, und navigieren Sie zu: http://localhost, Webport\>/.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-178">To view the Website, open a browser, and navigate to: http://localhost,webport\>/.</span></span>
  
<span data-ttu-id="ab6ee-179">Integritätsinformationen nur anzeigen, öffnen Sie einen Browser, und navigieren zu: http://localhost:\<webport\>/healthcheck/.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-179">To view health information only, open a browser, and navigate to: http://localhost:\<webport\>/healthcheck/.</span></span>
  
<span data-ttu-id="ab6ee-180">Der Standardwert für die Webportnummer lautet 8080.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-180">By default, the web port number is 8080.</span></span> <span data-ttu-id="ab6ee-181">Sie können die Portbindung der Website über den IIS-Manager ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-181">You can change the port binding of the website by using IIS manager.</span></span>
  
<span data-ttu-id="ab6ee-182">Das Website-Installationsprogramm fügt eine lokale Sicherheitsgruppe mit dem Namen StatsManWebSiteUsers hinzu.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-182">The web installer adds a local security group, called StatsManWebSiteUsers.</span></span> <span data-ttu-id="ab6ee-183">Sie können dieser Sicherheitsgruppe Konten hinzufügen, um Zugriff auf die Website zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-183">You can add accounts to this security group to grant access to the Website.</span></span> 
  
### <a name="install-the-agents"></a><span data-ttu-id="ab6ee-184">Installation der Agents</span><span class="sxs-lookup"><span data-stu-id="ab6ee-184">Install the Agents</span></span>

<span data-ttu-id="ab6ee-185">Installieren Sie einen Agent auf jedem Skype für Business Server, die Sie durch Ausführen der StatsManPerfAgent.msi und angeben die folgenden überwachen möchten:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-185">Install an Agent on each Skype for Business Server that you wish to monitor by running the StatsManPerfAgent.msi and specifying the following:</span></span>
  
1. <span data-ttu-id="ab6ee-186">Lesen Sie den Lizenzvertrag durch. Wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags zu** und klicken Sie auf **Weiter**. </span><span class="sxs-lookup"><span data-stu-id="ab6ee-186">Review the License Agreement, and if you agree, select **I accept the terms in the license agreement**, and then click **Next**.</span></span> 
    
2. <span data-ttu-id="ab6ee-187">Geben Sie auf der nächsten Seite die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-187">On the next page, specify the following information:</span></span>
    
   - <span data-ttu-id="ab6ee-188">**Dienstkennwort:** Dies ist das Kennwort, mit dem der Remote-Agent den Listener-Dienst authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-188">**Service Password:** This is the password the remote agent will use to authenticate to the Listener service.</span></span>
    
   - <span data-ttu-id="ab6ee-189">**Datendienst-URI:** Dies ist der URI der Listener sich befindet.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-189">**Service URI:** This is the URI where the Listener resides.</span></span> <span data-ttu-id="ab6ee-190">Sollte die https://name:port Format.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-190">It should use the https://name:port format.</span></span>
    
     <span data-ttu-id="ab6ee-191">Sie können einen NETBIOS-Namen oder einen FQDN verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-191">You can use a NETBIOS name or a FQDN.</span></span> <span data-ttu-id="ab6ee-192">Sie können den Namen, der auch als **Betreff** oder **Alternative Antragstellernamen** des Zertifikats auf den Listener-Dienst angegeben wird, aber dies ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-192">You can use the name that is also specified as the **Subject** or **Subject Alternative Names** of the certificate on the Listener service, but this is not a requirement.</span></span>
    
   - <span data-ttu-id="ab6ee-193">**Service Fingerabdruck:** Hierbei handelt es sich um den Fingerabdruck des SSL-Zertifikats der Listener verwendeten.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-193">**Service Thumbprint:** This is the thumbprint of the SSL certificate the Listener is using.</span></span> <span data-ttu-id="ab6ee-194">Der Agent verwendet diesen Fingerabdruck zur Authentifizierung des Listeners.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-194">The Agent will use this thumbprint to authenticate to the Listener.</span></span> <span data-ttu-id="ab6ee-195">(Er führt keine vollständige Verifizierung von Zertifikaten durch, weil es möglich ist, selbstsignierte Zertifikate zu verwenden.)</span><span class="sxs-lookup"><span data-stu-id="ab6ee-195">(It will not do full certificate validation because it is possible to use self-signed certificates.)</span></span>
    
   - <span data-ttu-id="ab6ee-196">**Dir installieren:** Dies ist das Verzeichnis auf dem die Binärdateien installiert werden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-196">**Install Dir:** This is the directory on which the binaries will be installed.</span></span> <span data-ttu-id="ab6ee-197">Sie können das Standardverzeichnis über die Schaltfläche **Durchsuchen...** ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-197">You may change it from the default by using the **Browse...** button.</span></span>
    
   - <span data-ttu-id="ab6ee-198">**Anwendungsdaten Dir:** Dies ist das Verzeichnis, in dem der Ordner Logs und die verschlüsselte Password.txt geschrieben gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-198">**AppData Dir:** This is the directory where the Logs folder and the encrypted password.txt file will be stored.</span></span> <span data-ttu-id="ab6ee-199">Sie können den Standardprotokollordner ändern.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-199">You may thanks change it from the default.</span></span> <span data-ttu-id="ab6ee-200">Er wird bei einer Deinstallation nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-200">It will not be deleted on uninstall.</span></span>
    
3. <span data-ttu-id="ab6ee-201">Klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-201">Click **Install**.</span></span>
    
<span data-ttu-id="ab6ee-p121">Wenn Sie einen Agent auf einer Reihe von Computern installieren, werden Sie dies wahrscheinlich im unbeaufsichtigten Modus durchführen wollen. Beispiel:  </span><span class="sxs-lookup"><span data-stu-id="ab6ee-p121">If you are installing an Agent on numerous machines, you will probably want to do this in unattended mode. For example:</span></span> 
  
```
msiexec /l install.log /i StatsManPerfAgent.msi SERVICE_THUMBPRINT=<thumbprint> SERVICE_PASSWORD=<password> SERVICE_URI=https://<hostname>:<servicePort>/[INSTALLDIR=<directory>][DIR_  STATSMANAPPDATA=<directory>]
```

### <a name="import-the-topology"></a><span data-ttu-id="ab6ee-204">Import der Topologie</span><span class="sxs-lookup"><span data-stu-id="ab6ee-204">Import the topology</span></span>
<span data-ttu-id="ab6ee-205"><a name="BKMK_ImportTopology"> </a></span><span class="sxs-lookup"><span data-stu-id="ab6ee-205"></span></span>

<span data-ttu-id="ab6ee-206">Nachdem Statistiken Manager installiert ist und ausgeführt wird, Sie die Skype für Business Server-Topologie importieren müssen weiß also dieses Managers Statistiken der Website, den Pool und die Rolle der einzelnen Server.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-206">After Statistics Manager is installed and running, you need to import the Skype for Business Server topology so that Statistics Manager knows the Site, Pool, and Role of each server.</span></span> <span data-ttu-id="ab6ee-207">Um Ihre Skype für Business Server-Topologie zu importieren, werden Sie verwenden Sie das [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) -Cmdlet zum Abrufen von Informationen zu allen Pools in Ihrer Organisation und dann importieren diese Informationen in den Statistiken-Manager.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-207">To import your Skype for Business Server topology, you will use the [Get-CsPool](https://docs.microsoft.com/powershell/module/skype/get-cspool?view=skype-ps) cmdlet to retrieve information about each pool in use in your organization, then import this information into Statistics Manager.</span></span>
  
<span data-ttu-id="ab6ee-208">Gehen folgendermaßen Sie vor, um die Skype für Business Server-Topologie zu importieren:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-208">To import the Skype for Business Server topology, follow these steps:</span></span>
  
1. <span data-ttu-id="ab6ee-209">Auf einem Host, der die Skype für Business Server PowerShell-Cmdlets verfügt:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-209">On a host that has the Skype for Business Server PowerShell cmdlets:</span></span>
    
    <span data-ttu-id="ab6ee-210">a.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-210">a.</span></span> <span data-ttu-id="ab6ee-211">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-211">Run the following command:</span></span> 
    
   ```
   Get-CsPool | Export-Clixml -Path mypoolinfo.xml
   ```
    <span data-ttu-id="ab6ee-212">b.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-212">b.</span></span> <span data-ttu-id="ab6ee-213">Kopieren Sie die Datei "mypoolinfo.xml" auf den Server, der den Listener ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-213">Copy the "mypoolinfo.xml" file to the server that runs the Listener.</span></span>
    
2. <span data-ttu-id="ab6ee-214">Auf dem Host, auf dem der Listener ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-214">On the host that runs the Listener:</span></span>
    
   <span data-ttu-id="ab6ee-215">a.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-215">a.</span></span> <span data-ttu-id="ab6ee-216">Führen Sie PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-216">Run PowerShell.</span></span>
    
   <span data-ttu-id="ab6ee-217">b.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-217">b.</span></span> <span data-ttu-id="ab6ee-218">Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-218">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="ab6ee-219">Die Standardeinstellung ist:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-219">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

3. <span data-ttu-id="ab6ee-220">Führen Sie den folgenden Befehl aus, um zu bestätigen, welche Server hinzugefügt und aktualisiert werden:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-220">To confirm which servers are being added and updated, run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -CsPoolFile  <path to mypoolinfo.xml>
   ```

<span data-ttu-id="ab6ee-221">Mit dem folgenden Befehl können Sie alle Optionen anzeigen:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-221">The following command enables you to view all options:</span></span>
  
```
Get-Help .\Update-StatsManServerInfo.ps1 -Detailed 
```

<span data-ttu-id="ab6ee-222">Um Ihre gerade importierten Serverinformationen anzuzeigen, führen Sie das folgende Skript aus:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-222">To see your currently imported server information, run the following script:</span></span> 
  
```
.\Get-StatsManServerInfo.ps1
```

<span data-ttu-id="ab6ee-223">Wenn Sie möchten, zum Überwachen von Servern, die nicht in Ihrer Skype für Business Server-Topologie – einen Exchange-Server sind beispielsweise--Möglichkeiten einen Einzelserver Import auf dem Host, die den Listener ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-223">If you would like to monitor servers that are not in your Skype for Business Server topology--an Exchange Server, for example--you can do a single-server import on the host that runs the Listener.</span></span> <span data-ttu-id="ab6ee-224">Wenn Sie nur einen einzelnen Server importieren möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-224">To do a single-server import, follow these steps:</span></span>
  
1. <span data-ttu-id="ab6ee-225">Navigieren Sie zu dem Verzeichnis, in dem der Listener installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-225">Navigate to the directory on which the Listener is installed.</span></span> <span data-ttu-id="ab6ee-226">Die Standardeinstellung ist:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-226">The default is:</span></span> 
    
   ```
   cd C:\Program Files\Skype for Business Server StatsMan Listener
   ```

2. <span data-ttu-id="ab6ee-227">Führen Sie den folgenden Befehl aus:  </span><span class="sxs-lookup"><span data-stu-id="ab6ee-227">Run the following command:</span></span>
    
   ```
    .\Update-StatsManServerInfo.ps1 -HostName <hostname> -SiteName <name of site> -PoolName <poolName> -Roles <role1>[,<role2>,<roleN>]
   ```

## <a name="troubleshoot-your-deployment"></a><span data-ttu-id="ab6ee-228">Problembehandlung Ihrer Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="ab6ee-228">Troubleshoot your deployment</span></span>
<span data-ttu-id="ab6ee-229"><a name="BKMK_Troubleshoot"> </a></span><span class="sxs-lookup"><span data-stu-id="ab6ee-229"></span></span>

<span data-ttu-id="ab6ee-230">Fall ein Agent nicht startet, überprüfen Sie Folgendes: </span><span class="sxs-lookup"><span data-stu-id="ab6ee-230">If an Agent fails to start, check for the following:</span></span> 
  
- <span data-ttu-id="ab6ee-231">Ist der Agent im Statistik-Manager registriert?</span><span class="sxs-lookup"><span data-stu-id="ab6ee-231">Is the agent registered in Statistics Manager?</span></span>
    
1. <span data-ttu-id="ab6ee-p129">	Stellen Sie sicher, dass Sie die Anweisungen für den Import der Topologie befolgt haben. Siehe auch [Import the topology](deploy.md#BKMK_ImportTopology).  </span><span class="sxs-lookup"><span data-stu-id="ab6ee-p129">Make sure you followed the instructions for importing the topology. See [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
2. <span data-ttu-id="ab6ee-234">Wenn sich der Agent auf einem Server befindet, der in der Topologie nicht aufgeführt ist (zum Beispiel die Knoten in einem SQL-„AlwaysOn“-Cluster), müssen Sie den Agent manuell hinzufügen, indem Sie die Anleitungen in [Import the topology](deploy.md#BKMK_ImportTopology) ausführen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-234">If the Agent is on a server that is not listed in the topology (for example, the nodes in a SQL AlwaysOn cluster), you will need to add the Agent manually by following the instructions in [Import the topology](deploy.md#BKMK_ImportTopology).</span></span>
    
- <span data-ttu-id="ab6ee-235">Kann der Agent den Listener kontaktieren?</span><span class="sxs-lookup"><span data-stu-id="ab6ee-235">Can the Agent contact the Listener?</span></span>
    
1. <span data-ttu-id="ab6ee-236">Stellen Sie sicher, dass der Listener-Dienst ausgeführt wird.  </span><span class="sxs-lookup"><span data-stu-id="ab6ee-236">Make sure the Listener service is running.</span></span> 
    
    <span data-ttu-id="ab6ee-237">Wenn der Listener nicht ausgeführt wird, stellen Sie sicher, dass Redis ausgeführt wird, und versuchen Sie anschließend, den Listener neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-237">If it is not running, make sure Redis is running, and then try to restart the Listener.</span></span>
    
2. <span data-ttu-id="ab6ee-238">Stellen Sie sicher, der Port öffnen, um den Listener-Dienst ist und dass der Agent-Computer mit dem Port kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-238">Make sure the port is open to the Listener service, and that the Agent computer can communicate with the port.</span></span>
    
- <span data-ttu-id="ab6ee-239">Um sicherzustellen, dass Statistiken Manager Daten erfasst, können Sie die CSV-Datei wie folgt überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-239">To ensure that Statistics Manager is collecting data, you can check the CSV file as follows.</span></span> 
    
    <span data-ttu-id="ab6ee-240">Der folgende Befehl ruft die Computer-Speichernamen ab:  </span><span class="sxs-lookup"><span data-stu-id="ab6ee-240">The following command retrieves the counter storage names:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=listcounterstoragenames -mode=verbose | findstr /i processor
  ```

    <span data-ttu-id="ab6ee-241">Der nächste Befehl ruft die Werte ab für die angegebenen Zähler ab: </span><span class="sxs-lookup"><span data-stu-id="ab6ee-241">The next command retrieves the values for the specified counters:</span></span> 
    
  ```
  .\PerfAgentStorageManager.exe -redis=localhost -a=getcountervalues  -counter="\\*\Processor Information\% Processor Time_Mean_Mean\_Total" -file:all-processor.csv
  ```

<span data-ttu-id="ab6ee-242">Informationen über alle Ereignisse, die möglicherweise im Ereignisprotokoll Anwendung angezeigt finden Sie unter [Problembehandlung bei Statistiken Manager für Skype für Business Server](troubleshoot.md).</span><span class="sxs-lookup"><span data-stu-id="ab6ee-242">For information about all the events you might see in the application event log, see [Troubleshoot Statistics Manager for Skype for Business Server](troubleshoot.md).</span></span>
  
## <a name="create-a-self-signed-certificate"></a><span data-ttu-id="ab6ee-243">Erstellen eines selbstsignierten Zertifikats</span><span class="sxs-lookup"><span data-stu-id="ab6ee-243">Create a self-signed certificate</span></span>
<span data-ttu-id="ab6ee-244"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="ab6ee-244"></span></span>

<span data-ttu-id="ab6ee-245">Microsoft empfiehlt dringend die Verwendung eines Zertifikats, das von einer vertrauenswürdigen Zertifizierungsstelle signiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-245">Microsoft strongly recommends that you use a certificate signed by a trusted certificate authority.</span></span> <span data-ttu-id="ab6ee-246">Wenn Sie jedoch zu Testzwecken ein selbst-signiertes Zertifikat verwenden möchten, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-246">However, if you want to use a self-signed certificate for testing purposes, do the following:</span></span> 
  
1. <span data-ttu-id="ab6ee-247">Melden Sie sich als Administrator an und geben Sie in einer PowerShell-Konsole Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-247">From a PowerShell console while logged on as Administrator, type the following:</span></span>
    
   ```
   New-SelfSignedCertificate -DnsName StatsManListener -CertStoreLocation Cert:\LocalMachine\My
   ```

2. <span data-ttu-id="ab6ee-248">Typ `certlm.msc`.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-248">Type  `certlm.msc`.</span></span> <span data-ttu-id="ab6ee-249">Dadurch öffent sich der Zertifikat-Manager für den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-249">This will open the Certificate Manager for the local machine.</span></span>
    
3. <span data-ttu-id="ab6ee-250">Navigieren Sie zur **persönlichen**, und öffnen Sie dann auf **Zertifikate**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-250">Navigate to **Personal**, and then open **Certificates**.</span></span>
    
4. <span data-ttu-id="ab6ee-251">Klicken Sie mit der rechten Maustaste auf **StatsManListener -\>alle Aufgaben -\>Privatschlüssel verwalten**</span><span class="sxs-lookup"><span data-stu-id="ab6ee-251">Right click on **StatsManListener-\>All Tasks-\>Manage Private Keys…**</span></span>
    
5. <span data-ttu-id="ab6ee-252">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-252">Click **Add**.</span></span>
    
6. <span data-ttu-id="ab6ee-253">Geben Sie im Feld **Geben Sie die zu verwendenden Objektnamen ein** folgenden Text ein: Netzwerkdienst</span><span class="sxs-lookup"><span data-stu-id="ab6ee-253">In the **Enter the object names to select** box, type the following: Network Service</span></span>
    
7. <span data-ttu-id="ab6ee-254">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-254">Click **OK**.</span></span>
    
8. <span data-ttu-id="ab6ee-p132">Deaktivieren Sie unter **Vollzugriff** das Kontrollkästchen **Zulassen**. (Nur Leseberechtigung erforderlich)</span><span class="sxs-lookup"><span data-stu-id="ab6ee-p132">Under **Full Control**, un-check the **Allow** check box. (Only Read access is necessary.)</span></span>
    
9. <span data-ttu-id="ab6ee-257">Klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ab6ee-257">Click **OK**.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="ab6ee-258">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab6ee-258">For more information</span></span>
<span data-ttu-id="ab6ee-259"><a name="BKMK_SelfCert"> </a></span><span class="sxs-lookup"><span data-stu-id="ab6ee-259"></span></span>

<span data-ttu-id="ab6ee-260">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ab6ee-260">For more information, see the following:</span></span>
  
- [<span data-ttu-id="ab6ee-261">Planen der Business Server für den Statistiken-Manager für Skype</span><span class="sxs-lookup"><span data-stu-id="ab6ee-261">Plan for Statistics Manager for Skype for Business Server</span></span>](plan.md)
    
- [<span data-ttu-id="ab6ee-262">Aktualisieren von Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ab6ee-262">Upgrade Statistics Manager for Skype for Business Server</span></span>](upgrade.md)
    
- [<span data-ttu-id="ab6ee-263">Problembehandlung bei Statistiken Manager für Skype für Business Server</span><span class="sxs-lookup"><span data-stu-id="ab6ee-263">Troubleshoot Statistics Manager for Skype for Business Server</span></span>](troubleshoot.md)
    
- [<span data-ttu-id="ab6ee-264">Skype for Business Server Statistics Manager-Blog</span><span class="sxs-lookup"><span data-stu-id="ab6ee-264">Skype for Business Server Statistics Manager blog</span></span>](https://blogs.technet.microsoft.com/skypestatsman/)
    

