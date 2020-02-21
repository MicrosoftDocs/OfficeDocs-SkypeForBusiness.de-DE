---
title: Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Centralized Logging Service configuration settings
ms:assetid: f455c3aa-0061-413d-bdfb-a3e78f82723d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721938(v=OCS.15)
ms:contentKeyID: 49733875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7811c8c55a7c759076382ecf102868cc6c7abf09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-centralized-logging-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fbad6-102">Verwalten der Konfigurationseinstellungen für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbad6-102">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbad6-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fbad6-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fbad6-104">Der zentralisierte Protokollierungsdienst wird von Einstellungen und Parametern gesteuert und konfiguriert, die vom zentralisierten Protokollierungsdienst-Controller (CLSController) erstellt und verwendet werden, um Befehle an den zentralen Protokollierungsdienst-Agent des einzelnen Computers zu senden ( CLSAgent).</span><span class="sxs-lookup"><span data-stu-id="fbad6-104">The Centralized Logging Service is controlled and configured by settings and parameters that are created and used by the Centralized Logging Service Controller (CLSController) to send commands to the individual computer’s Centralized Logging Service Agent (CLSAgent).</span></span> <span data-ttu-id="fbad6-105">Der Agent verarbeitet die an ihn gesendeten Befehle und verwendet (im Fall eines Start Befehls) die Konfiguration der Szenarien, Anbieter, Protokollgröße, Ablauf Verfolgungs Dauer und Flags, um mit dem Sammeln von Ablaufverfolgungsprotokollen entsprechend den bereitgestellten Konfigurationsinformationen zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="fbad6-105">The agent processes the commands that are sent to it and (in the case of a Start command) uses the configuration of the scenarios, providers, log size, trace duration, and flags to begin collecting trace logs according to the configuration information provided.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="fbad6-106">Nicht alle Windows PowerShell-Cmdlets, die für den zentralisierten Protokollierungsdienst aufgeführt sind, sind für die Verwendung mit lync Server 2013 lokalen Bereitstellungen vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="fbad6-106">Not all Windows PowerShell cmdlets listed for the Centralized Logging Service are intended for use with Lync Server 2013 on-premises deployments.</span></span> <span data-ttu-id="fbad6-107">Die folgenden Cmdlets sind zwar möglicherweise anscheinend funktionsfähig, aber nicht für die Verwendung mit lync Server 2013 lokalen Bereitstellungen ausgelegt:</span><span class="sxs-lookup"><span data-stu-id="fbad6-107">Although they may appear to work, the following cmdlets are not designed to function with Lync Server 2013 on-premises deployments:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="fbad6-108"><STRONG>CsClsRegion-Cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Sets-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>und <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span><span class="sxs-lookup"><span data-stu-id="fbad6-108"><STRONG>CsClsRegion cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ204879(v=OCS.15)">Get-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204746(v=OCS.15)">Set-CsClsRegion</A>, <A href="https://technet.microsoft.com/library/JJ204658(v=OCS.15)">New-CsClsRegion</A>, and <A href="https://technet.microsoft.com/library/JJ204971(v=OCS.15)">Remove-CsClsRegion</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="fbad6-109"><STRONG>CsClsSearchTerm-Cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> und <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Sets-CsClsSearchTerm</A>.</span><span class="sxs-lookup"><span data-stu-id="fbad6-109"><STRONG>CsClsSearchTerm cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205061(v=OCS.15)">Get-CsClsSearchTerm</A> and <A href="https://technet.microsoft.com/library/JJ204911(v=OCS.15)">Set-CsClsSearchTerm</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="fbad6-110"><STRONG>CsClsSecurityGroup-Cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Sets-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>und <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span><span class="sxs-lookup"><span data-stu-id="fbad6-110"><STRONG>CsClsSecurityGroup cmdlets:</STRONG> <A href="https://technet.microsoft.com/library/JJ205285(v=OCS.15)">Get-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ204700(v=OCS.15)">Set-CsClsSecurityGroup</A>, <A href="https://technet.microsoft.com/library/JJ205359(v=OCS.15)">New-CsClsSecurityGroup</A>, and <A href="https://technet.microsoft.com/library/JJ204958(v=OCS.15)">Remove-CsClsSecurityGroup</A>.</span></span></P></LI></UL><span data-ttu-id="fbad6-111">Die in diesen Cmdlets definierten Einstellungen behindern oder verursachen keine unerwünschten Verhaltensweisen, sind jedoch für die Verwendung mit Microsoft Office 365 ausgelegt und ergeben keine erwarteten Ergebnisse in lokalen Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="fbad6-111">The settings defined in these cmdlets will not hinder or cause any adverse behavior, but they are designed for use with Microsoft Office 365 and will not yield the expected results in on-premises deployments.</span></span> <span data-ttu-id="fbad6-112">Dies bedeutet nicht, dass diese Cmdlets in lokalen Bereitstellungen nicht verwendet werden, ihre Verwendung ist jedoch ein erweitertes Thema, das in dieser Dokumentation nicht behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="fbad6-112">This is not to say that there is no use for these cmdlets in on-premises deployments, but their use is a more advanced topic that is not covered in this documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbad6-113">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fbad6-113">In This Section</span></span>

<span data-ttu-id="fbad6-114">In den Themen in diesem Abschnitt werden die Konfigurationsoptionen, Parameter und Einstellungen für den zentralisierten Protokollierungsdienst definiert.</span><span class="sxs-lookup"><span data-stu-id="fbad6-114">The topics in this section define the configuration options, parameters, and settings for the Centralized Logging Service.</span></span> <span data-ttu-id="fbad6-115">Informationen zum Konfigurieren des zentralisierten Protokollierungsdiensts, zum Abrufen der Konfigurationseinstellungen, zum Erstellen von Szenarien, zur Verwaltung von Sicherheitsgruppen für den zentralisierten Protokollierungsdienst, zum Suchen und mehr finden Sie in den folgenden Themen.</span><span class="sxs-lookup"><span data-stu-id="fbad6-115">Information about how to configure the Centralized Logging Service, how to retrieve the configuration settings, creation of scenarios, management of security groups for Centralized Logging Service, searching, and more is contained in the following topics.</span></span>

  - [<span data-ttu-id="fbad6-116">Verwalten der Konfiguration von Computer-, Standort-und globalen zentralisierten Protokollierungs Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbad6-116">Managing computer, site and global Centralized Logging Service configuration in Lync Server 2013</span></span>](lync-server-2013-managing-computer-site-and-global-centralized-logging-service-configuration.md)

  - [<span data-ttu-id="fbad6-117">Konfigurieren von Anbietern für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbad6-117">Configuring providers for Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-providers-for-centralized-logging-service.md)

  - [<span data-ttu-id="fbad6-118">Konfigurieren von Szenarien für den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbad6-118">Configuring scenarios for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-configuring-scenarios-for-the-centralized-logging-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbad6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbad6-119">See Also</span></span>


[<span data-ttu-id="fbad6-120">Übersicht über den zentralisierten Protokollierungsdienst in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbad6-120">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)  
[<span data-ttu-id="fbad6-121">Cmdlets für die zentralisierte Protokollierung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbad6-121">Centralized Logging cmdlets in Lync Server 2013</span></span>](lync-server-2013-centralized-logging-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

