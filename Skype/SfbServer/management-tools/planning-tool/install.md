---
title: Installieren des Planungstools in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
description: Vor Beginn entwerfen und planen Ihre Skype für Business Server 2015 Infrastruktur mithilfe der Skype für Business Server 2015-Planungstool, Sie müssen zuerst installieren das Planungstool. Das Planungstool muss nicht bereitgestellt werden, auf einer Arbeitsstation oder einem Server, der Teil der Domäne oder der Infrastruktur, in der Sie Skype für Business Server 2015 installieren möchten. Die Planungstool gehörenden Infodatei enthält wichtige Informationen zur Installation und Verwendung des Tools. Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.
ms.openlocfilehash: 64d510eedc01149e7119e3ec92ea09cd9a6c842a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915024"
---
# <a name="install-the-planning-tool-in-skype-for-business-server-2015"></a><span data-ttu-id="a6f4e-106">Installieren des Planungstools in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a6f4e-106">Install the Planning Tool in Skype for Business Server 2015</span></span>

<span data-ttu-id="a6f4e-107">Vor Beginn entwerfen und planen Ihre Skype für Business Server 2015 Infrastruktur mithilfe der Skype für Business Server 2015-Planungstool, Sie müssen zuerst installieren das Planungstool.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-107">Before you begin designing and planning your Skype for Business Server 2015 infrastructure by using the Skype for Business Server 2015 Planning Tool, you must first install the Planning Tool.</span></span> <span data-ttu-id="a6f4e-108">Das Planungstool muss nicht bereitgestellt werden, auf einer Arbeitsstation oder einem Server, der Teil der Domäne oder der Infrastruktur, in der Sie Skype für Business Server 2015 installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-108">The Planning Tool does not need to be deployed to a workstation or server that is part of the domain or infrastructure where you plan to install Skype for Business Server 2015.</span></span> <span data-ttu-id="a6f4e-109">Die Planungstool gehörenden Infodatei enthält wichtige Informationen zur Installation und Verwendung des Tools.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-109">The Readme file that accompanies the Planning Tool details important information about installing and using the tool.</span></span> <span data-ttu-id="a6f4e-110">Einige Informationen aus dieser Datei werden zur Verdeutlichung im Folgenden noch einmal aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-110">Some of the information in the Readme file is duplicated here for clarity.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6f4e-111">Das Planungstool erfordert Installation von einem Benutzer mit Administratorrechten und-Berechtigungen auf dem Computer, auf dem das Tool installiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-111">The Planning Tool requires installation by a user with administrator rights and permissions on the computer on which the tool is to be installed.</span></span>

<span data-ttu-id="a6f4e-112">Die unterstützten Betriebssysteme für Installation und Verwendung des Planungstool sind:</span><span class="sxs-lookup"><span data-stu-id="a6f4e-112">The supported operating systems for installation and operation of the Planning Tool are:</span></span>

- <span data-ttu-id="a6f4e-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6f4e-113">Windows 10</span></span>

- <span data-ttu-id="a6f4e-114">Windows 8</span><span class="sxs-lookup"><span data-stu-id="a6f4e-114">Windows 8</span></span>

- <span data-ttu-id="a6f4e-115">Windows 8,1</span><span class="sxs-lookup"><span data-stu-id="a6f4e-115">Windows 8.1</span></span>

- <span data-ttu-id="a6f4e-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="a6f4e-116">Windows Server 2012</span></span>

- <span data-ttu-id="a6f4e-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a6f4e-117">Windows Server 2012 R2</span></span>

- <span data-ttu-id="a6f4e-118">Windows 7, 32-Bit-Version</span><span class="sxs-lookup"><span data-stu-id="a6f4e-118">Windows 7, 32-bit edition</span></span>

- <span data-ttu-id="a6f4e-119">Windows 7, 64-Bit-Version unter Verwendung von Windows on Win32 (WOW)</span><span class="sxs-lookup"><span data-stu-id="a6f4e-119">Windows 7, 64-bit edition using Windows on Win32 (WOW)</span></span>

- <span data-ttu-id="a6f4e-120">Windows Server 2008 R2 unter Verwendung von WOW</span><span class="sxs-lookup"><span data-stu-id="a6f4e-120">Windows Server 2008 R2, using WOW</span></span>

<span data-ttu-id="a6f4e-121">Darüber hinaus erfordert das Planungstool für Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-121">Additionally, the Planning Tool requires Microsoft .NET Framework 4.5.</span></span>

<span data-ttu-id="a6f4e-122">Wenn die Vorinstallation Anforderungen erfüllt sind, können Sie dann das Planungstool installieren.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-122">After the preinstallation requirements are met, you can then install the Planning Tool.</span></span>



## <a name="to-install-the-planning-tool"></a><span data-ttu-id="a6f4e-123">So installieren Sie das Planungstool</span><span class="sxs-lookup"><span data-stu-id="a6f4e-123">To install the Planning Tool</span></span>

1. <span data-ttu-id="a6f4e-124">Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-124">Log on to the local computer as a member of the Administrators group.</span></span>

2. <span data-ttu-id="a6f4e-125">Verwenden Sie Windows Explorer oder ein Befehlsfenster, suchen Sie das Verzeichnis, in dem Sie die Planungstool-Installationsdateien heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-125">Using Windows Explorer or a command window, locate the directory where you downloaded the Planning Tool installation files.</span></span>

3. <span data-ttu-id="a6f4e-p103">Suchen Sie die Datei SkypeForBusinessPlanningTool.msi. Machen Sie im Windows Explorer einen Doppelklick auf die Datei. Geben Sie im Befehlsfenster den Namen der Datei ein und drücken Sie die **Eingabetaste**, um die Datei auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-p103">Locate the SkypeForBusinessPlanningTool.msi. In Windows Explorer, double-click the file. In the command window, type the name of the file, and then press **Enter** to run the file.</span></span>

4. <span data-ttu-id="a6f4e-129">Klicken Sie auf der Willkommensseite des Setup-Assistenten für das **Skype for Business Server 2015-Planungstool** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-129">On the Welcome page of the **Skype for Business Server 2015, Planning Tool Setup Wizard**, click **Next**.</span></span>

5. <span data-ttu-id="a6f4e-130">Lesen Sie den **Endbenutzer-Lizenzvertrag**, wählen Sie die Option **Ich stimme den Bedingungen des Lizenzvertrags zu** aus, sofern Sie die Bedingungen akzeptieren, und klicken Sie anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-130">Review the **End-User License Agreement**, select **I accept the terms in the License Agreement** if you choose to accept the terms of use in the license agreement, and then click **Next**.</span></span>

6. <span data-ttu-id="a6f4e-p104">Geben Sie an, in welchem Verzeichnis die Dateien des Planungstools installiert werden sollen. Der Standardspeicherort lautet „C:\Programme (x86)\Skype for Business Server 2015\Planning Tool“. Wenn Sie ein anderes Installationsverzeichnis auswählen möchten, klicken Sie auf **Ändern**. Navigieren Sie im Dialogfeld **Zielordner ändern** zum gewünschten Verzeichnis oder geben Sie ein Verzeichnis ein und klicken Sie nacheinander auf **OK** und auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-p104">Choose where to install the Planning Tool files. The default location is C:\Program Files (x86)\Skype for Business Server 2015\Planning Tool. If you want to change the installation location, click **Change**. On **Change destination folder**, browse or type the location to install the files, click **OK**, and then click **Next**.</span></span>

7. <span data-ttu-id="a6f4e-135">Der Installer ist jetzt so installieren Sie das Planungstool bereit.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-135">The installer is now ready to install the Planning Tool.</span></span> <span data-ttu-id="a6f4e-136">Klicken Sie auf **Installieren**, um den Installationsvorgang zu starten.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-136">Click **Install** to begin the installation process.</span></span>

8. <span data-ttu-id="a6f4e-137">Die Installation beginnt und der Installationsfortschritt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-137">The installation will start, and the progress will be displayed.</span></span> <span data-ttu-id="a6f4e-138">Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-138">After the installation is successfully completed, click **Finish**.</span></span>

9. <span data-ttu-id="a6f4e-139">Das Planungstool ist für die Verwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-139">The Planning Tool is ready for use.</span></span>

## <a name="optional-software"></a><span data-ttu-id="a6f4e-140">Optionale Software</span><span class="sxs-lookup"><span data-stu-id="a6f4e-140">Optional Software</span></span>
<span data-ttu-id="a6f4e-141"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f4e-141"></span></span>

<span data-ttu-id="a6f4e-142">Die Skype für Business Server 2015 Planungstool dient zum Exportieren nach Microsoft Excel und Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-142">The Skype for Business Server 2015 Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="a6f4e-143">Während dieser Anwendungen nicht für den Betrieb von Planungstool erforderlich sind, sie die Bereitstellung und die Dokumentation des Entwurfs erhebliche Wert hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-143">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

### <a name="microsoft-excel"></a><span data-ttu-id="a6f4e-144">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="a6f4e-144">Microsoft Excel</span></span>

<span data-ttu-id="a6f4e-145">Beim Exportieren Ihres Entwurfs nach Microsoft Excel wird ein Bericht in Form einer Tabelle mit sieben Registerkarten erstellt:</span><span class="sxs-lookup"><span data-stu-id="a6f4e-145">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

- <span data-ttu-id="a6f4e-146">Zusammenfassung: Zeigt Informationen auf Standortkonfiguration, einschließlich Benutzeranzahl, Einstellungen für die Ressourcenkapazität und Profilinformationen Server.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-146">Summary - Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

- <span data-ttu-id="a6f4e-147">Hardware-Profil - zeigt einen Bericht zu den empfohlenen Hardwarekonfigurationen für Server, die in der Topologie, einschließlich CPU, Arbeitsspeicher, Festplatten und Netzwerkschnittstelle angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-147">Hardware Profile - Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="a6f4e-148">Die Anzahl und die empfohlenen Spezifikationen für die Serverkomponenten sind auch enthalten.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-148">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="a6f4e-149">Darüber hinaus ist jeder Server nach Standort definiert, um eine vollständige Darstellung der Serveranforderungen nach Standort bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-149">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

- <span data-ttu-id="a6f4e-150">Anforderungen an Ports - Bericht für alle Ports, die aktiviert sind und die Zuordnung zu Domain Name System-Lastenausgleich (DNS-kg) und Hardwaregeräten zum Lastenausgleich (Hardwarelastenausgleich) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-150">Ports Requirements - Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="a6f4e-151">Sie sollten diesen Bericht zum Planen der Konfiguration von Firewall sowie DNS-Lastenausgleich und Hardwaregeräten zum Lastenausgleich verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-151">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

- <span data-ttu-id="a6f4e-152">Zusammenfassungsbericht - zeigt die allgemeine Zusammenfassung der Einstellungen, die zum Einrichten eines Netzwerks Edge-Server erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-152">Summary Report - Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

- <span data-ttu-id="a6f4e-153">Zertifikatbericht – zeigt den Antragstellernamen und alternative Antragstellernamen, die für die Zertifikate erforderlich, um den Edge-Servern mit abrufen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-153">Certificates Report - Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

- <span data-ttu-id="a6f4e-154">Bericht - zeigt die Quell- und Ziel-Ports und IP-Adressen für externe und interne Schnittstellen Firewall.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-154">Firewall Report - Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

- <span data-ttu-id="a6f4e-155">DNS-Bericht - zeigt den vollqualifizierten Domänennamen (FQDN) und IP-Adresse/VIP-Adressen erforderlich für jeden DNS-Eintrag, zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-155">DNS Report - Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

### <a name="microsoft-visio"></a><span data-ttu-id="a6f4e-156">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="a6f4e-156">Microsoft Visio</span></span>

<span data-ttu-id="a6f4e-p110">Beim Exportieren Ihres Entwurfs nach Microsoft Visio wird ein Diagramm erstellt, das Sie zur Dokumentation Ihrer konfigurierten Topologie und Infrastruktur verwenden können. Das importierte Diagramm kann bearbeitet und neu angeordnet werden, um Ihre Dokumentationsanforderungen zu erfüllen. Das typische Visio-Diagramm umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="a6f4e-p110">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f4e-160">Wenn Ihr Entwurf groß genug für mehr als drei Front-End-Servern erforderlich ist, wird eine zusätzliche Seite für den Front-End-Pool Front-End-Server, dem Computer mit SQL Server, IP-Adressen und FQDNs erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-160">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>

- <span data-ttu-id="a6f4e-161">Globale Topologie – Diagramm der konfigurierten Skype für Business Server 2015 Websites.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-161">Global Topology - Diagram of configured Skype for Business Server 2015 sites.</span></span>

- <span data-ttu-id="a6f4e-162">Registerkarte Site-Name - Telefon zeigt die Standorttopologie Konfiguration mit Edge-Server, Firewall, Public Switched Telephone Network (PSTN)-Gateways und der interne Server-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-162">Site Name tab - Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="a6f4e-163">Interne Bereitstellung besteht der konfigurierten Server und Pools, einschließlich der Front-End-pools, Directors für den SQL Server-basierten Server Active Directory Domain Services, Exchange Unified Messaging (UM) Server, Exchange-Postfachserver, Office Web Apps-Server, Vermittlungsserver und Server für beständigen Chat.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-163">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

- <span data-ttu-id="a6f4e-164">Edge-Netzplandiagramm - Diagramm mit ausführlichen Informationen zu den Edge-Server-Konfiguration mit zugeordneten IP-Adressen und FQDNs.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-164">Edge Network Diagram - Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="a6f4e-165">DNS-Lastenausgleich und Hardwarelastenausgleich sind ebenfalls enthalten.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-165">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="a6f4e-166">Darüber hinaus werden von Directors und dem Front-End-Server oder Front-End-Pool angezeigt, mit zugeordneten DNS kg oder Hardwaregeräts zum Lastenausgleich und die zugeordnete IP-Adresse (das Planungstool unterstützt sowohl IPv4 als auch IPv6-Adressen) und den FQDN.</span><span class="sxs-lookup"><span data-stu-id="a6f4e-166">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6f4e-167">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6f4e-167">See also</span></span>
<span data-ttu-id="a6f4e-168"><a name="Optional_Software"> </a></span><span class="sxs-lookup"><span data-stu-id="a6f4e-168"></span></span>

[<span data-ttu-id="a6f4e-169">Installing the Planning Tool</span><span class="sxs-lookup"><span data-stu-id="a6f4e-169">Installing the Planning Tool</span></span>](https://technet.microsoft.com/library/ebdc9e26-4b22-4b02-85b9-7462bcfe7c93.aspx)
