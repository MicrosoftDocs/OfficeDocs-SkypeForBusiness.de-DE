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
ms.openlocfilehash: 6f84b4f0a95c45297ad809e6b04217e711c3dd5e
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="install-prerequisites-for-skype-for-business-server-2015"></a><span data-ttu-id="7b539-104">Installieren der erforderlichen Komponenten für Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7b539-104">Install prerequisites for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7b539-105">**Zusammenfassung:** Informationen Sie zu den Servern und Serverrollen, die Sie vor der Installation von Skype für Business Server 2015 konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="7b539-105">**Summary:** Learn about the servers and server roles you must configure before you install Skype for Business Server 2015.</span></span> <span data-ttu-id="7b539-106">Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="7b539-106">Download a free trial of Skype for Business Server 2015 from the [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="7b539-107">Die Installation der erforderlichen Softwarekomponenten besteht in der Einrichtung von Windows Server durch Installation der erforderlichen Rollen und Funktionen auf jedem Server in der Topologie.</span><span class="sxs-lookup"><span data-stu-id="7b539-107">Installing prerequisites consists of setting up Windows Server by installing the required roles and features on each of the servers in the topology.</span></span> <span data-ttu-id="7b539-108">Welche Komponenten erforderlich sind, hängt von der Rolle des jeweiligen Servers in der Topologie ab.</span><span class="sxs-lookup"><span data-stu-id="7b539-108">The requirements are based on the role the server will fulfill in the topology.</span></span> <span data-ttu-id="7b539-109">Sie können die Schritte 1 bis 5 in einer beliebigen Reihenfolge ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b539-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="7b539-110">Die Schritte 6, 7 und 8 müssen jedoch wie in der Abbildung dargestellt nacheinander und nach den Schritten 1 bis 5 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7b539-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5, as outlined in the diagram.</span></span> <span data-ttu-id="7b539-111">Die Installation der erforderlichen Softwarekomponenten ist Schritt 1 von 8.</span><span class="sxs-lookup"><span data-stu-id="7b539-111">Installing prerequisites is step 1 of 8.</span></span>
  
![Übersichtsdiagramm – Voraussetzungen für die Installation](../../media/0a85349b-b398-4e04-8901-8f4bd25d8afe.png)
  
## <a name="setup-windows-server"></a><span data-ttu-id="7b539-113">Einrichten von Windows Server</span><span class="sxs-lookup"><span data-stu-id="7b539-113">Setup Windows Server</span></span>

<span data-ttu-id="7b539-114">Skype für Business Server 2015 erfordert das Betriebssystem Windows Server und eine Anzahl von erforderlichen Komponenten, bevor es installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="7b539-114">Skype for Business Server 2015 requires the Windows Server operating system and a number of prerequisites before it can be installed.</span></span> <span data-ttu-id="7b539-115">Weitere Informationen zur Planung der erforderlichen Komponenten finden Sie unter [Server-Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b539-115">For details on planning for prerequisites, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  
> [!TIP]
> <span data-ttu-id="7b539-p105">Das nachfolgende Verfahren basiert auf Windows Server 2012 R2. Wenn Sie eine andere Windows Server-Version verwenden, kann die Vorgehensweise leicht abweichen.</span><span class="sxs-lookup"><span data-stu-id="7b539-p105">This procedure uses Windows Server 2012 R2. If you are using a different version of Windows Server, the procedure might be slightly different.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="7b539-118">Bevor Sie beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist.</span><span class="sxs-lookup"><span data-stu-id="7b539-118">Before you begin, make sure that Windows Server is up-to-date by using Windows Update.</span></span> 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
<span data-ttu-id="7b539-120">Schauen Sie sich das Video mit den Schritten zum **Imstallieren der erforderlichen Komponenten** an:</span><span class="sxs-lookup"><span data-stu-id="7b539-120">Watch the video steps for **install prerequisites**:</span></span>
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/02447c2a-5b26-432f-aad6-b9b05cc93478?autoplay=false]
  
### <a name="install-required-roles-and-features-for-front-end-servers"></a><span data-ttu-id="7b539-121">Installieren der erforderlichen Rollen und Funktionen für Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="7b539-121">Install required roles and features for front-end servers</span></span>

1. <span data-ttu-id="7b539-122">Öffnen Sie Server-Manager und klicken Sie auf **Rollen und Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7b539-122">Open Server Manager, and click **Add roles and features**.</span></span>
    
2. <span data-ttu-id="7b539-123">Lesen Sie die Seite **Bevor Sie beginnen** , um sich bei der Installation von Rollen und Features in Windows Server vertraut zu machen, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7b539-123">Read the **Before You Begin** page to familiarize yourself with installing roles and features in Windows Server, and then click **Next**.</span></span>
    
3. <span data-ttu-id="7b539-124">Wählen Sie **Rollenbasierte oder funktionsbasierte Installation** aus und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7b539-124">Select **Role-based or feature-based installation**, and click **Next**.</span></span>
    
4. <span data-ttu-id="7b539-125">Wählen Sie den Server, auf dem Sie werden Installieren von Skype für Business Server 2015, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7b539-125">Select the server on which you will be installing Skype for Business Server 2015, and click **Next**.</span></span>
    
5. <span data-ttu-id="7b539-126">Wählen Sie die Rolle **Webserver (IIS)** aus und klicken Sie im daraufhin geöffneten Fenster auf **Funktionen hinzufügen** und dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7b539-126">Select the **Web Server (IIS)** role, and when the required features window pops up, click **Add Features**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="7b539-127">Stellen Sie sicher, die Software-Features aufgeführt, die in der [Software, die vor einem Skype für Business Server 2015 Bereitstellung installiert werden muss,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) auf dem Server, auf denen Skype für Business Server 2015 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7b539-127">Make sure the software features listed in [Software that should be installed before a Skype for Business Server 2015 deployment](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md#Software) are on the server that will run Skype for Business Server 2015.</span></span> <span data-ttu-id="7b539-128">Hier ist eine verkürzte Liste:</span><span class="sxs-lookup"><span data-stu-id="7b539-128">Here's an abbreviated list:</span></span>
    
   - <span data-ttu-id="7b539-129">.NET Framework-Features</span><span class="sxs-lookup"><span data-stu-id="7b539-129">.NET Framework Features</span></span>
    
   - <span data-ttu-id="7b539-130">WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="7b539-130">WCF Services</span></span>
    
   - <span data-ttu-id="7b539-131">HTTP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="7b539-131">HTTP Activation</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7b539-p107">HTTP-Aktivierung erfordert zusätzliche Funktionen. Klicken Sie im Warndialogfeld, das bei Auswahl von „HTTP-Aktivierung“ angezeigt wird, auf **Funktionen hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7b539-p107">HTTP Activation requires additional features. Click **Add Features** to the warning dialog box that pops up when you select HTTP Activation.</span></span>
  
   - <span data-ttu-id="7b539-134">Media Foundation (von Front-End-Servern und Standard Edition-Servern für Konferenzen verwendet erforderlich.)</span><span class="sxs-lookup"><span data-stu-id="7b539-134">Media Foundation (required by Front End Servers and Standard Edition servers used for conferencing.)</span></span>
    
   - <span data-ttu-id="7b539-135">Remoteserver-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="7b539-135">Remote Server Administration Tools</span></span>
    
   - <span data-ttu-id="7b539-136">Verwaltungstools für Rollen</span><span class="sxs-lookup"><span data-stu-id="7b539-136">Role Administration Tools</span></span>
    
   - <span data-ttu-id="7b539-137">AD DS</span><span class="sxs-lookup"><span data-stu-id="7b539-137">AD DS</span></span> 
    
   - <span data-ttu-id="7b539-138">AD LDS</span><span class="sxs-lookup"><span data-stu-id="7b539-138">AD LDS</span></span>
    
   - <span data-ttu-id="7b539-139">Windows Identity Foundation 3.5</span><span class="sxs-lookup"><span data-stu-id="7b539-139">Windows Identity Foundation 3.5</span></span>
    
7. <span data-ttu-id="7b539-140">Klicken Sie auf **Weiter**, um mit dem Assistenten fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="7b539-140">Click **Next** to continue through the wizard.</span></span>
    
8. <span data-ttu-id="7b539-141">Lesen Sie die Anmerkungen zur **Webserverrolle (IIS)** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7b539-141">Read through the notes about the **Web Server Role (IIS)**, and then click **Next**.</span></span>
    
9. <span data-ttu-id="7b539-142">Wählen Sie folgende **Webserver (IIS)-Rollendienste** aus.</span><span class="sxs-lookup"><span data-stu-id="7b539-142">Select the following **Web Server (IIS) role services**.</span></span>
    
   - <span data-ttu-id="7b539-143">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="7b539-143">Common HTTP Features</span></span>
    
   - <span data-ttu-id="7b539-144">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="7b539-144">Default Document</span></span>
    
   - <span data-ttu-id="7b539-145">Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="7b539-145">Directory Browsing</span></span>
    
   - <span data-ttu-id="7b539-146">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="7b539-146">HTTP Errors</span></span>
    
   - <span data-ttu-id="7b539-147">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="7b539-147">Static Content</span></span>
    
   - <span data-ttu-id="7b539-148">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="7b539-148">Health and Diagnostics</span></span>
    
   - <span data-ttu-id="7b539-149">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="7b539-149">HTTP Logging</span></span>
    
   - <span data-ttu-id="7b539-150">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="7b539-150">Logging Tools</span></span>
    
   - <span data-ttu-id="7b539-151">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="7b539-151">Tracing</span></span>
    
   - <span data-ttu-id="7b539-152">Leistung</span><span class="sxs-lookup"><span data-stu-id="7b539-152">Performance</span></span>
    
   - <span data-ttu-id="7b539-153">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="7b539-153">Static Content Compression</span></span>
    
   - <span data-ttu-id="7b539-154">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="7b539-154">Dynamic Content Compression</span></span>
    
   - <span data-ttu-id="7b539-155">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="7b539-155">Security</span></span>
    
   - <span data-ttu-id="7b539-156">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="7b539-156">Request Filtering</span></span>
    
   - <span data-ttu-id="7b539-157">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7b539-157">Client Certificate Mapping Authentication</span></span>
    
   - <span data-ttu-id="7b539-158">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7b539-158">Windows Authentication</span></span>
    
   - <span data-ttu-id="7b539-159">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="7b539-159">Application Development</span></span>
    
   - <span data-ttu-id="7b539-160">.NET-Erweiterbarkeit 3.5</span><span class="sxs-lookup"><span data-stu-id="7b539-160">.NET Extensibility 3.5</span></span>
    
   - <span data-ttu-id="7b539-161">.NET-Erweiterbarkeit 4.5</span><span class="sxs-lookup"><span data-stu-id="7b539-161">.NET Extensibility 4.5</span></span>
    
   - <span data-ttu-id="7b539-162">ASP.NET 3.5</span><span class="sxs-lookup"><span data-stu-id="7b539-162">ASP.NET 3.5</span></span>
    
   - <span data-ttu-id="7b539-163">ASP.NET 4.5</span><span class="sxs-lookup"><span data-stu-id="7b539-163">ASP.NET 4.5</span></span>
    
   - <span data-ttu-id="7b539-164">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="7b539-164">ISAPI Extensions</span></span>
    
   - <span data-ttu-id="7b539-165">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="7b539-165">ISAPI Filters</span></span>
    
   - <span data-ttu-id="7b539-166">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="7b539-166">Management Tools</span></span>
    
   - <span data-ttu-id="7b539-167">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="7b539-167">IIS Management Console</span></span>
    
   - <span data-ttu-id="7b539-168">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="7b539-168">IIS Management Scripts and Tools</span></span>
    
10. <span data-ttu-id="7b539-169">Klicken Sie auf **Weiter**, um mit dem Assistenten fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="7b539-169">Click **Next** to continue through the wizard.</span></span>
    
11. <span data-ttu-id="7b539-170">Prüfen Sie die Installationsauswahl, um sicherzustellen, dass alle Anforderungen erfüllt sind, und klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="7b539-170">Review the installation selections to make sure all requirements are selected, and then click **Install**.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="7b539-171">Windows Server 2012 R2 installiert nicht standardmäßig alle Quelldateien der erforderlichen Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7b539-171">Windows Server 2012 R2 does not install all of the source files for the required features by default.</span></span> <span data-ttu-id="7b539-172">Wenn der Server nicht mit dem Internet verbunden ist, müssen Sie das Windows Server 2012 R2-Installationsmedium einlegen und **Alternativen Quellpfad angeben** auswählen, um die erforderlichen Funktionen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7b539-172">If the server is not connected to the Internet, you will need to insert the Windows Server 2012 R2 media and select **Specify an alternate source path** in order to install the required features.</span></span> <span data-ttu-id="7b539-173">Die Quelldateien befinden sich im Verzeichnis „sources\sxs“.</span><span class="sxs-lookup"><span data-stu-id="7b539-173">The source files are located in the sources\sxs directory.</span></span> <span data-ttu-id="7b539-174">Wenn das Windows Server 2012 R2-Medium beispielsweise in Laufwerk D eingelegt wurde, würde der Pfad `d:\sources\sxs` lauten.</span><span class="sxs-lookup"><span data-stu-id="7b539-174">For example, if the Windows Server 2012 R2 media is in drive D, you would set the path to `d:\sources\sxs`.</span></span> <span data-ttu-id="7b539-175">> Es ist wichtig, dass Sie die neuesten Updates von Windows Update verfügen.</span><span class="sxs-lookup"><span data-stu-id="7b539-175">> It is important that you have the latest updates from Windows Update.</span></span> <span data-ttu-id="7b539-176">Wenn Sie nicht mit dem Internet verbunden sind, müssen Sie alle relevanten Updates sowie alle erforderlichen Komponenten über die erforderlichen Updates manuell zu installieren.</span><span class="sxs-lookup"><span data-stu-id="7b539-176">If you are not connected to the Internet, you will need to manually install all relevant updates as well as any prerequisites to the required updates.</span></span> 
  
12. <span data-ttu-id="7b539-177">Wenn der Abschluss der Installation angezeigt wird, müssen Sie den Server neu starten, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7b539-177">When the dialog box indicates that the installation has completed, you will need to reboot the server to complete the process.</span></span>
    
13. <span data-ttu-id="7b539-178">Führen Sie **Windows Update** erneut aus, um zu prüfen, ob es ein Update für die installierten Rollen und Dienste gibt.</span><span class="sxs-lookup"><span data-stu-id="7b539-178">Run **Windows Update** again to check if there are any updates to the roles and services that were installed.</span></span>
    
14. <span data-ttu-id="7b539-179">Wenn Sie Skype Business Server-Systemsteuerung auf diesem Server verwenden müssen Sie auch Silverlight installieren.</span><span class="sxs-lookup"><span data-stu-id="7b539-179">If you will be using Skype for Business Server Control Panel on this server then you must also install Silverlight.</span></span> <span data-ttu-id="7b539-180">Zum Installieren von Silverlight finden Sie unter [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span><span class="sxs-lookup"><span data-stu-id="7b539-180">To install Silverlight, see [Microsoft Silverlight](https://www.microsoft.com/silverlight/).</span></span>
    
<span data-ttu-id="7b539-181">Die erforderlichen Softwarekomponenten können über den nachfolgend aufgeführten PowerShell-Befehl installiert werden.</span><span class="sxs-lookup"><span data-stu-id="7b539-181">The prerequisites can be installed by running the following PowerShell command.</span></span> <span data-ttu-id="7b539-182">Der Befehl sucht Quelldateien in einer spezifischen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="7b539-182">Note that the command looks for source files in a specific order.</span></span> <span data-ttu-id="7b539-183">Wenn eine Verbindung mit dem Internet besteht, greift der Befehl auf Windows Update zu.</span><span class="sxs-lookup"><span data-stu-id="7b539-183">If you are online, the command accesses Windows Update.</span></span> <span data-ttu-id="7b539-184">Ohne Verbindung mit dem Internet müssen Sie dafür sorgen, dass alle Quelldateien für den Befehl zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="7b539-184">However, if you are offline, you need to make sure the source files are available to the command.</span></span> <span data-ttu-id="7b539-185">Weitere Informationen zum Verwenden von PowerShell-Rollen und-Features installieren finden Sie unter [installieren oder Deinstallieren von Rollen, Rollendienste oder Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) und [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span><span class="sxs-lookup"><span data-stu-id="7b539-185">For more information about using PowerShell to install roles and features, see [Install or Uninstall Roles, Role Services, or Features](https://technet.microsoft.com/en-us/library/hh831809.aspx) and [Install-WindowsFeature](https://technet.microsoft.com/en-us/library/jj205467.aspx).</span></span> <span data-ttu-id="7b539-186">Denken Sie daran, nach Installation der erforderlichen Softwarekomponenten Windows Update erneut auszuführen, selbst wenn Sie den PowerShell-Befehl verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="7b539-186">Don't forget to run Windows Update again after you install prerequisites, even if you use the PowerShell command.</span></span>
```
Add-WindowsFeature NET-Framework-Core, RSAT-ADDS, Windows-Identity-Foundation, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Dir-Browsing, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Server-Media-Foundation, BITS
```

> [!IMPORTANT]
> <span data-ttu-id="7b539-187">Für Server, die eine andere Funktion als die eines Front-End-Servers haben, z. B. Director, Persistent Chat oder Edge, sind eigene Softwarekomponenten erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7b539-187">The prerequisites for servers performing roles other than front-end server, such as the role of Director, Persistent Chat, or Edge, have their own prerequisites.</span></span> <span data-ttu-id="7b539-188">Ausführliche Informationen zum die genauen erforderlichen Komponenten erforderlich, die für jeden Servertyp finden Sie unter [Anforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b539-188">For details on the exact prerequisites required by each server type, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span> 
  

