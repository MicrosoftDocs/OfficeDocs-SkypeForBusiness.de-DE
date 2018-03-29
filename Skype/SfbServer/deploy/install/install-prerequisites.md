---
title: Installieren der erforderlichen Komponenten für Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2ef91a1e-2899-44c8-8e2c-527cb9114a0a
description: 'Zusammenfassung: Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 350f64a2808e51866cd5720cb1955259ff773c81
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="8da36-104">Installieren der erforderlichen Komponenten für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8da36-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8da36-105">**Zusammenfassung:** Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="8da36-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="8da36-106">Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="8da36-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="8da36-107">Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="8da36-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="8da36-108">Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab.</span><span class="sxs-lookup"><span data-stu-id="8da36-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="8da36-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="8da36-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="8da36-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8da36-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="8da36-111">Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.</span><span class="sxs-lookup"><span data-stu-id="8da36-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="8da36-113">Einrichten von Windows Server</span><span class="sxs-lookup"><span data-stu-id="8da36-113">Setup Windows Server</span></span>

<span data-ttu-id="8da36-114">Skype für Business Server 2015 erfordert das Betriebssystem Windows Server und eine Anzahl von erforderlichen Komponenten, bevor es installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8da36-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="8da36-115">Weitere Informationen zur Planung der erforderlichen Komponenten finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8da36-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="8da36-p105">Das nachfolgende Verfahren basiert auf Windows Server 2012 R2. Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen.</span><span class="sxs-lookup"><span data-stu-id="8da36-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8da36-118">Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="8da36-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="8da36-120">Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:</span><span class="sxs-lookup"><span data-stu-id="8da36-120">Watch the video steps for **install prerequisites**:</span></span>
  
![Ihr Browser unterstützt kein Video. Installieren von Microsoft Silverlight, Adobe Flash Player oder Internet Explorer 9.](../../media/MSN_Video_Widget.gif)
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="8da36-123">Installieren der erforderlichen Rollen und Funktionen für Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="8da36-123">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="8da36-124">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8da36-124">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="8da36-125">Lesen Sie die Seite **Bevor Sie beginnen** , um sich bei der Installation von Rollen und Features in Windows Server vertraut zu machen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8da36-125">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="8da36-126">Wählen Sie **Rollenbasierte oder funktionsbasierte Installation** aus und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8da36-126">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="8da36-127">Wählen Sie den Server, auf dem Sie werden Installieren von Skype für Business Server 2015, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8da36-127">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="8da36-128">Wählen Sie die Rolle **Webserver (IIS)** aus und klicken Sie im daraufhin geöffneten Fenster auf **Funktionen hinzufügen** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8da36-128">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="8da36-129">Stellen Sie sicher, die Software-Features aufgeführt, die in der [Software, die vor einem Skype für Business Server 2015 Bereitstellung installiert werden muss,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) auf dem Server, auf denen Skype für Business Server 2015 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8da36-129">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="8da36-130">Hier ist eine verkürzte Liste:</span><span class="sxs-lookup"><span data-stu-id="8da36-130">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="8da36-131">.NET Framework-Features</span><span class="sxs-lookup"><span data-stu-id="8da36-131">.NET Framework Features</span></span>
    
   - <span data-ttu-id="8da36-132">WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="8da36-132">WCF Services</span></span>
    
   - <span data-ttu-id="8da36-133">HTTP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="8da36-133">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8da36-p108">HTTP-Aktivierung erfordert zusätzliche Funktionen. Klicken Sie im Warndialogfeld, das bei Auswahl von „HTTP-Aktivierung“ angezeigt wird, auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8da36-p108">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="8da36-136">Media Foundation (von Front-End-Servern und Standard Edition-Servern für Konferenzen verwendet erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="8da36-136">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="8da36-137">Remoteserver-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="8da36-137">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="8da36-138">Verwaltungstools für Rollen</span><span class="sxs-lookup"><span data-stu-id="8da36-138">Role Administration Tools</span></span>
    
   - <span data-ttu-id="8da36-139">AD DS</span><span class="sxs-lookup"><span data-stu-id="8da36-139">AD DS</span></span> 
    
   - <span data-ttu-id="8da36-140">AD LDS</span><span class="sxs-lookup"><span data-stu-id="8da36-140">AD LDS</span></span>
    
   - <span data-ttu-id="8da36-141">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="8da36-141">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="8da36-142">Klicken Sie auf **Weiter**, um mit dem Assistenten fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="8da36-142">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="8da36-143">Lesen Sie die Anmerkungen zur **Webserverrolle (IIS)** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="8da36-143">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="8da36-144">Wählen Sie folgende **Webserver (IIS)-Rollendienste** aus.</span><span class="sxs-lookup"><span data-stu-id="8da36-144">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="8da36-145">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="8da36-145">Common HTTP Features</span></span>
    
   - <span data-ttu-id="8da36-146">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="8da36-146">Default Document</span></span>
    
   - <span data-ttu-id="8da36-147">Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="8da36-147">Directory Browsing</span></span>
    
   - <span data-ttu-id="8da36-148">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="8da36-148">HTTP Errors</span></span>
    
   - <span data-ttu-id="8da36-149">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="8da36-149">Static Content</span></span>
    
   - <span data-ttu-id="8da36-150">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="8da36-150">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="8da36-151">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="8da36-151">HTTP Logging</span></span>
    
   - <span data-ttu-id="8da36-152">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="8da36-152">Logging Tools</span></span>
    
   - <span data-ttu-id="8da36-153">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="8da36-153">Tracing</span></span>
    
   - <span data-ttu-id="8da36-154">Leistung</span><span class="sxs-lookup"><span data-stu-id="8da36-154">Performance</span></span>
    
   - <span data-ttu-id="8da36-155">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="8da36-155">Static Content Compression</span></span>
    
   - <span data-ttu-id="8da36-156">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="8da36-156">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="8da36-157">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8da36-157">Security</span></span>
    
   - <span data-ttu-id="8da36-158">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="8da36-158">Request Filtering</span></span>
    
   - <span data-ttu-id="8da36-159">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8da36-159">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="8da36-160">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8da36-160">Windows Authentication</span></span>
    
   - <span data-ttu-id="8da36-161">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="8da36-161">Application Development</span></span>
    
   - <span data-ttu-id="8da36-162">.NET-Erweiterbarkeit 3.5</span><span class="sxs-lookup"><span data-stu-id="8da36-162">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="8da36-163">.NET-Erweiterbarkeit 4.5</span><span class="sxs-lookup"><span data-stu-id="8da36-163">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="8da36-164">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="8da36-164">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="8da36-165">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="8da36-165">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="8da36-166">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="8da36-166">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="8da36-167">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="8da36-167">ISAPI Filters</span></span>
    
   - <span data-ttu-id="8da36-168">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="8da36-168">Management Tools</span></span>
    
   - <span data-ttu-id="8da36-169">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="8da36-169">IIS Management Console</span></span>
    
   - <span data-ttu-id="8da36-170">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="8da36-170">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="8da36-171">Klicken Sie auf **Weiter**, um mit dem Assistenten fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="8da36-171">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="8da36-172">Prüfen Sie die Installationsauswahl, um sicherzustellen, dass alle Anforderungen erfüllt sind, und klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="8da36-172">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="8da36-173">Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8da36-173">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="8da36-174">Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8da36-174">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="8da36-175">Die Quelldateien befinden sich im Verzeichnis „sources\sxs“.</span><span class="sxs-lookup"><span data-stu-id="8da36-175">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="8da36-176">Wenn das Windows Server 2012 R2-Medium beispielsweise in Laufwerk D eingelegt wurde, würde der Pfad `d:\sources\sxs` lauten.</span><span class="sxs-lookup"><span data-stu-id="8da36-176">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="8da36-177">> Es ist wichtig, dass Sie die neuesten Updates von Windows Update verfügen.</span><span class="sxs-lookup"><span data-stu-id="8da36-177">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="8da36-178">Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten über die erforderlichen Updates manuell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8da36-178">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="8da36-179">Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="8da36-179">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="8da36-180">Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.</span><span class="sxs-lookup"><span data-stu-id="8da36-180">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="8da36-181">Wenn Sie Skype Business Server-Systemsteuerung auf diesem Server verwenden müssen Sie auch Silverlight installieren.</span><span class="sxs-lookup"><span data-stu-id="8da36-181">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="8da36-182">Zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="8da36-182">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="8da36-183">Die erforderlichen Softwarekomponenten können über den nachfolgend aufgeführten PowerShell-Befehl installiert werden.</span><span class="sxs-lookup"><span data-stu-id="8da36-183">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="8da36-184">Der Befehl sucht Quelldateien in einer spezifischen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="8da36-184">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="8da36-185">Wenn eine Verbindung mit dem Internet besteht, greift der Befehl auf Windows Update zu.</span><span class="sxs-lookup"><span data-stu-id="8da36-185">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="8da36-186">Ohne Verbindung mit dem Internet müssen Sie dafür sorgen, dass alle Quelldateien für den Befehl zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="8da36-186">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="8da36-187">Weitere Informationen zum Verwenden von PowerShell-Rollen und-Features installieren finden Sie unter [installieren oder Deinstallieren von Rollen, Rollendienste oder Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) und [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="8da36-187">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="8da36-188">Denken Sie daran, nach Installation der erforderlichen Softwarekomponenten Windows Update erneut auszuführen, selbst wenn Sie den PowerShell-Befehl verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="8da36-188">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="8da36-189">Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8da36-189">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="8da36-190">Ausführliche Informationen zum die genauen erforderlichen Komponenten erforderlich, die für jeden Servertyp finden Sie unter [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8da36-190">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

