---
title: 'Lync Server 2013: Übersicht über Best Practices Analyzer'
description: 'Lync Server 2013: Overview of Best Practices Analyzer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Best Practices Analyzer
ms:assetid: c5fcaa05-eb1c-4092-90ad-177b127e795b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591349(v=OCS.15)
ms:contentKeyID: 48185364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ea48e88b26fa1081e5770fef2ac24efc21b74cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559281"
---
# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="cbcc9-103">Übersicht über Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbcc9-103">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbcc9-104">_**Letztes Änderungsstand des Themas:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="cbcc9-104">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="cbcc9-105">Sie können lync Server 2013, Best Practices Analyzer verwenden, um Probleme mit ihrer lync Server 2013-Bereitstellung zu identifizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-105">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="cbcc9-106">Der lync Server 2013, Best Practices Analyzer sammelt Konfigurationsinformationen aus lync Server 2013 Komponenten.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-106">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="cbcc9-107">Mit dem richtigen Netzwerkzugriff kann der Best Practices Analyzer Server mit Active Directory-Domänendienste, Exchange Server Unified Messaging (um) und lync Server 2013 untersuchen.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-107">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="cbcc9-108">Sie können Best Practices Analyzer verwenden, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="cbcc9-108">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="cbcc9-109">Proaktives durchführen von Prüfungen, überprüfen, ob die Konfiguration gemäß den empfohlenen bewährten Methoden festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-109">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="cbcc9-110">Automatische Erkennung erforderlicher Updates für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-110">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="cbcc9-111">Erstellen Sie eine Liste von Problemen, beispielsweise suboptimale Konfigurationseinstellungen, nicht unterstützte Optionen, fehlende Updates oder Methoden, die nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-111">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="cbcc9-112">Unterstützen Sie bei der Problembehandlung und bei der Behebung bestimmter Probleme.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-112">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="cbcc9-113">Best Practices Analyzer stellt die folgenden Funktionen bereit:</span><span class="sxs-lookup"><span data-stu-id="cbcc9-113">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="cbcc9-114">Minimale Installationsvoraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-114">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="cbcc9-115">Online Dokumentation zu gemeldeten Problemen, einschließlich Tipps zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-115">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="cbcc9-116">Konfigurationsinformationen, die Sie für eine spätere Überprüfung speichern können.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-116">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="cbcc9-117">Modernste Systemanalyse.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-117">State-of-the-art system analysis.</span></span>

<span data-ttu-id="cbcc9-118">Best Practices Analyzer verwendet eine Reihe von XML-Konfigurationsdateien, um die Informationen zu ermitteln, die aus ihrer lync Server 2013 Umgebung gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-118">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="cbcc9-119">Neben der Überprüfung von Active Directory-Domänendienste werden Quellen wie die Windows Server-Betriebssystemregistrierung und Einstellungen in der Windows-Verwaltungsinstrumentation (WMI) überprüft.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-119">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="cbcc9-120">Best Practices Analyzer vergleicht die erfassten Daten mit einer Reihe vordefinierter Regeln für die Einstellungen und Konfigurationen lync Server 2013 Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-120">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="cbcc9-121">Nachdem die gesammelten Daten mit den vordefinierten Regeln verglichen wurden, meldet das Tool Probleme.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-121">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="cbcc9-122">Best Practices Analyzer enthält für jedes Problem, das es meldet, Informationen darüber, was in der geprüften lync Server 2013 Umgebung gefunden wurde, und die empfohlene Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-122">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="cbcc9-123">Best Practices Analyzer enthält auch Links zu ausführlicheren Informationen zu den spezifischen Problemen.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-123">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cbcc9-124">Der lync Server 2013, Best Practices Analyzer sammelt Konfigurationsinformationen nur aus lync Server 2013-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-124">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="cbcc9-125">Sie können die vorherigen Versionen des Tools verwenden, um frühere Umgebungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-125">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="cbcc9-126">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for Running Best Practices Analyzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cbcc9-126">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

