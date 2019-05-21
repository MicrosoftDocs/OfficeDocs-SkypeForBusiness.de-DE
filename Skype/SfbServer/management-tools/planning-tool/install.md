---
title: Installieren des Planungstools in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Planungstools von Skype for Business Server 2015 beginnen, müssen Sie zuerst das Planungstool installieren. Das Planungs Tool muss nicht auf einer Workstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten. In der Readme-Datei, die dem Planungs Tool beigefügt ist, finden Sie wichtige Informationen zum Installieren und Verwenden des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.
ms.openlocfilehash: 192eae34bf6cf3fa53be82d8cb4450f960c90314
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279127"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="dc500-106">Installieren des Planungstools in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dc500-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="dc500-107">Bevor Sie mit dem Entwerfen und Planen Ihrer Skype for Business Server 2015-Infrastruktur mithilfe des Planungstools von Skype for Business Server 2015 beginnen, müssen Sie zuerst das Planungstool installieren.</span><span class="sxs-lookup"><span data-stu-id="dc500-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="dc500-108">Das Planungs Tool muss nicht auf einer Workstation oder einem Server bereitgestellt werden, die Teil der Domäne oder Infrastruktur ist, in der Sie Skype for Business Server 2015 installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="dc500-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="dc500-109">In der Readme-Datei, die dem Planungs Tool beigefügt ist, finden Sie wichtige Informationen zum Installieren und Verwenden des Tools.</span><span class="sxs-lookup"><span data-stu-id="dc500-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="dc500-110">Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="dc500-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc500-111">Das Planungs Tool erfordert die Installation durch einen Benutzer mit Administratorrechten und-Berechtigungen auf dem Computer, auf dem das Tool installiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="dc500-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="dc500-112">Die unterstützten Betriebssysteme für die Installation und den Betrieb des Planungstools sind:</span><span class="sxs-lookup"><span data-stu-id="dc500-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="dc500-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="dc500-113">Windows 10</span></span>

- <span data-ttu-id="dc500-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="dc500-114">Windows 8</span></span>

- <span data-ttu-id="dc500-115">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="dc500-115">Windows 8.1</span></span>

- <span data-ttu-id="dc500-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dc500-116">Windows Server 2012</span></span>

- <span data-ttu-id="dc500-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="dc500-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="dc500-118">Windows 7, 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="dc500-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="dc500-119">Windows 7, 64-Bit-Version unter Verwendung von Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="dc500-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="dc500-120">Windows Server 2008 R2 unter Verwendung von WOW</span><span class="sxs-lookup"><span data-stu-id="dc500-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="dc500-121">Darüber hinaus erfordert das Planungs Tool Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="dc500-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="dc500-122">Nachdem die Voraussetzungen für die Vorinstallation erfüllt sind, können Sie das Planungs Tool installieren.</span><span class="sxs-lookup"><span data-stu-id="dc500-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="dc500-123">So installieren Sie das Planungstool</span><span class="sxs-lookup"><span data-stu-id="dc500-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="dc500-124">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="dc500-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="dc500-125">Suchen Sie im Windows-Explorer oder einem Befehlsfenster nach dem Verzeichnis, in dem Sie die Installationsdateien des Planungstools heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="dc500-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="dc500-p103">Suchen Sie die Datei SkypeForBusinessPlanningTool.msi. Machen Sie im Windows Explorer einen Doppelklick auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein und drücken Sie die **Eingabetaste**, um die Datei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="dc500-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="dc500-129">Klicken Sie auf der Willkommensseite des Setup-Assistenten für das **Skype for Business Server 2015-Planungstool** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc500-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="dc500-130">Lesen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** aus, sofern Sie die Bedingungen akzeptieren, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc500-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="dc500-p104">Geben Sie an, in welchem Verzeichnis die Dateien des Planungstools installiert werden sollen. Der Standardspeicherort lautet „C:\Programme (x86)\Skype for Business Server 2015\Planning Tool“. Wenn Sie ein anderes Installationsverzeichnis auswählen möchten, klicken Sie auf **Ändern**. Navigieren Sie im Dialogfeld **Zielordner ändern** zum gewünschten Verzeichnis oder geben Sie ein Verzeichnis ein und klicken Sie nacheinander auf **OK** und auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="dc500-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="dc500-135">Das Installationsprogramm ist nun bereit, das Planungs Tool zu installieren.</span><span class="sxs-lookup"><span data-stu-id="dc500-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="dc500-136">Klicken Sie auf **Installieren**, um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="dc500-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="dc500-137">Die Installation beginnt und der Installationsfortschritt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc500-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="dc500-138">Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.</span><span class="sxs-lookup"><span data-stu-id="dc500-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="dc500-139">Das Planungs Tool ist einsatzbereit.</span><span class="sxs-lookup"><span data-stu-id="dc500-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="dc500-140">Optionale Software</span><span class="sxs-lookup"><span data-stu-id="dc500-140">Optional Software</span></span>
<span data-ttu-id="dc500-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="dc500-141"></span></span>

<span data-ttu-id="dc500-142">Das Planungs Tool für Skype for Business Server 2015 ist für den Export nach Microsoft Excel und Microsoft Visio konzipiert.</span><span class="sxs-lookup"><span data-stu-id="dc500-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="dc500-143">Obwohl diese Anwendungen nicht für den Betrieb des Planungstools erforderlich sind, fügen Sie der Bereitstellung und Dokumentation Ihres Entwurfs einen erheblichen Mehrwert hinzu.</span><span class="sxs-lookup"><span data-stu-id="dc500-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="dc500-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="dc500-144">Microsoft Excel</span></span>

<span data-ttu-id="dc500-145">Beim Exportieren Ihres Entwurfs nach Microsoft Excel wird ein Bericht in Form einer Tabelle mit sieben Registerkarten erstellt:</span><span class="sxs-lookup"><span data-stu-id="dc500-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="dc500-146">Zusammenfassung: zeigt Informationen zur Websitekonfiguration an, einschließlich Benutzeranzahl, Kapazitätseinstellungen und Server Profilinformationen.</span><span class="sxs-lookup"><span data-stu-id="dc500-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="dc500-147">Hardwareprofil – zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server an, die in der Topologie angegeben sind, einschließlich CPU, Arbeitsspeicher, Datenträger und Netzwerkschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dc500-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="dc500-148">Die Anzahl und die empfohlenen Spezifikationen für die Serverkomponenten sind auch enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc500-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="dc500-149">Darüber hinaus ist jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="dc500-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="dc500-150">Ports-Anforderungen – zeigt einen Bericht aller aktivierten Ports und die Zuordnung zu Domain Name System Load Balancing (DNS lb) und Hardware Load Balancer (HLB) an.</span><span class="sxs-lookup"><span data-stu-id="dc500-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="dc500-151">Sie sollten diesen Bericht zum Planen der Konfiguration von Firewall sowie DNS-Lastenausgleich und Hardwaregeräten zum Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="dc500-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="dc500-152">Zusammenfassungsbericht – zeigt die allgemeine Zusammenfassung der Einstellungen an, die zum Einrichten Ihres Edge-Server-Netzwerks erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dc500-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="dc500-153">Bericht "Zertifikate" – zeigt den Antragstellernamen und die alternativen Betreffnamen an, die für die für die Ausführung der Edgeserver erforderlichen Zertifikate erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="dc500-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="dc500-154">Firewallbericht – zeigt die Quell-und Zielports sowie IP-Adressen sowohl für externe als auch für interne Schnittstellen an.</span><span class="sxs-lookup"><span data-stu-id="dc500-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="dc500-155">DNS-Bericht – zeigt den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) und IP/VIP-Adressen für jeden von Ihnen erstellten DNS-Eintrag an.</span><span class="sxs-lookup"><span data-stu-id="dc500-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="dc500-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="dc500-156">Microsoft Visio</span></span>

<span data-ttu-id="dc500-p110">Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="dc500-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="dc500-160">Wenn Ihr Entwurf groß genug ist, um mehr als drei Front-End-Server zu erfordern, wird eine zusätzliche Seite für den Front-End-Pool, Front-End-Server, den Computer mit SQL Server, IP-Adressen und FQDNs erstellt.</span><span class="sxs-lookup"><span data-stu-id="dc500-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="dc500-161">Globale Topologie – Diagramm der konfigurierten Skype for Business Server 2015-Websites.</span><span class="sxs-lookup"><span data-stu-id="dc500-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="dc500-162">Registerkarte "Website Name" – zeigt die Topologie der Websitekonfiguration mit Edgeserver, Firewall, PSTN (Public Switched Telephone Network) mit Gateways und der internen Server Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="dc500-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="dc500-163">Die interne Bereitstellung besteht aus konfigurierten Servern und Pools, einschließlich der Front-End-Pools, SQL Server-basierten Servern, Active Directory-Domänendiensten, Directors, Exchange Unified Messaging (um)-Servern, Exchange-Postfachservern, Office Web Apps-Servern, Vermittlungsserver und persistente Chat Server.</span><span class="sxs-lookup"><span data-stu-id="dc500-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="dc500-164">Edge-Netzwerkdiagramm – Diagramm, in dem die Edgeserver-Konfiguration mit zugehörigen IP-Adressen und FQDNs erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="dc500-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="dc500-165">DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten.</span><span class="sxs-lookup"><span data-stu-id="dc500-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="dc500-166">Darüber hinaus werden Directors und der Front-End-Server oder der Front-End-Pool mit zugeordneter DNS lb oder HLB und der zugewiesenen IP-Adresse (das Planungs Tool unterstützt IPv4-und IPv6-Adressen) und dem FQDN angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dc500-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc500-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc500-167">See also</span></span>
<span data-ttu-id="dc500-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="dc500-168"></span></span>

[<span data-ttu-id="dc500-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="dc500-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
