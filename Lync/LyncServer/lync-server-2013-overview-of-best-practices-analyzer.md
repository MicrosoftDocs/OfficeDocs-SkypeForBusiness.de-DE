---
title: 'Lync Server 2013: Übersicht über Best Practices Analyzer'
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
ms.openlocfilehash: 4dd3cda0375c7c7e9d15f2ecd31b47a1dee587c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530722"
---
# <a name="overview-of-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="2ca8b-102">Übersicht über Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ca8b-102">Overview of Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ca8b-103">_**Letztes Änderungsstand des Themas:** 2012-09-19_</span><span class="sxs-lookup"><span data-stu-id="2ca8b-103">_**Topic Last Modified:** 2012-09-19_</span></span>

<span data-ttu-id="2ca8b-104">Sie können lync Server 2013, Best Practices Analyzer verwenden, um Probleme mit ihrer lync Server 2013-Bereitstellung zu identifizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-104">You can use Lync Server 2013, Best Practices Analyzer to identify and resolve problems with your Lync Server 2013 deployment.</span></span> <span data-ttu-id="2ca8b-105">Der lync Server 2013, Best Practices Analyzer sammelt Konfigurationsinformationen aus lync Server 2013 Komponenten.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-105">The Lync Server 2013, Best Practices Analyzer gathers configuration information from Lync Server 2013 components.</span></span>

<span data-ttu-id="2ca8b-106">Mit dem richtigen Netzwerkzugriff kann der Best Practices Analyzer Server mit Active Directory-Domänendienste, Exchange Server Unified Messaging (um) und lync Server 2013 untersuchen.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-106">With the proper network access, the Best Practices Analyzer can examine servers running Active Directory Domain Services, Exchange Server Unified Messaging (UM), and Lync Server 2013.</span></span> <span data-ttu-id="2ca8b-107">Sie können Best Practices Analyzer verwenden, um Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="2ca8b-107">You can use Best Practices Analyzer to do the following:</span></span>

  - <span data-ttu-id="2ca8b-108">Proaktives durchführen von Prüfungen, überprüfen, ob die Konfiguration gemäß den empfohlenen bewährten Methoden festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-108">Proactively perform checks, verifying that the configuration is set according to recommended best practices.</span></span>

  - <span data-ttu-id="2ca8b-109">Automatische Erkennung erforderlicher Updates für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-109">Automatically detect required updates to Lync Server 2013.</span></span>

  - <span data-ttu-id="2ca8b-110">Erstellen Sie eine Liste von Problemen, beispielsweise suboptimale Konfigurationseinstellungen, nicht unterstützte Optionen, fehlende Updates oder Methoden, die nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-110">Generate a list of issues, such as suboptimal configuration settings, unsupported options, missing updates, or practices that we do not recommend.</span></span>

  - <span data-ttu-id="2ca8b-111">Unterstützen Sie bei der Problembehandlung und bei der Behebung bestimmter Probleme.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-111">Help you troubleshoot and fix specific problems.</span></span>

<span data-ttu-id="2ca8b-112">Best Practices Analyzer stellt die folgenden Funktionen bereit:</span><span class="sxs-lookup"><span data-stu-id="2ca8b-112">Best Practices Analyzer provides the following features:</span></span>

  - <span data-ttu-id="2ca8b-113">Minimale Installationsvoraussetzungen.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-113">Minimal installation prerequisites.</span></span>

  - <span data-ttu-id="2ca8b-114">Online Dokumentation zu gemeldeten Problemen, einschließlich Tipps zur Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-114">Online documentation about reported issues, including troubleshooting tips.</span></span>

  - <span data-ttu-id="2ca8b-115">Konfigurationsinformationen, die Sie für eine spätere Überprüfung speichern können.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-115">Configuration information that you can save for later review.</span></span>

  - <span data-ttu-id="2ca8b-116">Modernste Systemanalyse.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-116">State-of-the-art system analysis.</span></span>

<span data-ttu-id="2ca8b-117">Best Practices Analyzer verwendet eine Reihe von XML-Konfigurationsdateien, um die Informationen zu ermitteln, die aus ihrer lync Server 2013 Umgebung gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-117">Best Practices Analyzer uses a set of XML configuration files to determine the information to gather from your Lync Server 2013 environment.</span></span> <span data-ttu-id="2ca8b-118">Neben der Überprüfung von Active Directory-Domänendienste werden Quellen wie die Windows Server-Betriebssystemregistrierung und Einstellungen in der Windows-Verwaltungsinstrumentation (WMI) überprüft.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-118">In addition to checking Active Directory Domain Services, it checks sources such as the Windows Server operating system registry and settings in Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="2ca8b-119">Best Practices Analyzer vergleicht die erfassten Daten mit einer Reihe vordefinierter Regeln für die Einstellungen und Konfigurationen lync Server 2013 Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-119">Best Practices Analyzer compares the data it gathers with a set of predefined rules for the settings and configurations of Lync Server 2013 deployments.</span></span>

<span data-ttu-id="2ca8b-120">Nachdem die gesammelten Daten mit den vordefinierten Regeln verglichen wurden, meldet das Tool Probleme.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-120">After comparing the collected data with the predefined rules, the tool reports issues.</span></span> <span data-ttu-id="2ca8b-121">Best Practices Analyzer enthält für jedes Problem, das es meldet, Informationen darüber, was in der geprüften lync Server 2013 Umgebung gefunden wurde, und die empfohlene Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-121">For every issue that it reports, Best Practices Analyzer provides information about what was found in the scanned Lync Server 2013 environment and the recommended configuration.</span></span> <span data-ttu-id="2ca8b-122">Best Practices Analyzer enthält auch Links zu ausführlicheren Informationen zu den spezifischen Problemen.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-122">Best Practices Analyzer also provides links to more detailed information about the specific issues.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ca8b-123">Der lync Server 2013, Best Practices Analyzer sammelt Konfigurationsinformationen nur aus lync Server 2013-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-123">The Lync Server 2013, Best Practices Analyzer gathers configuration information only from Lync Server 2013 components.</span></span> <span data-ttu-id="2ca8b-124">Sie können die vorherigen Versionen des Tools verwenden, um frühere Umgebungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-124">You can use the previous versions of the tool to scan previous environments.</span></span> <span data-ttu-id="2ca8b-125">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for Running Best Practices Analyzer in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2ca8b-125">For details, see <A href="lync-server-2013-requirements-for-running-best-practices-analyzer.md">Requirements for running Best Practices Analyzer in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

