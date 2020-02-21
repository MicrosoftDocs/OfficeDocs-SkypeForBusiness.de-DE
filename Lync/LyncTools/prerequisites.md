---
title: Voraussetzungen
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prerequisites
ms:assetid: 48016bea-be3b-4ba5-8df8-d8ad4d9243d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945592(v=OCS.15)
ms:contentKeyID: 51541417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4f10cb1bdf5733dbe54519325475871be10564
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196148"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites"></a><span data-ttu-id="2e795-102">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2e795-102">Prerequisites</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e795-103">_**Letztes Änderungsstand des Themas:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="2e795-103">_**Topic Last Modified:** 2013-02-19_</span></span>

<span data-ttu-id="2e795-104">Es gibt verschiedene Hardware-, Software-und Systemkonfigurations Anforderungen, die Sie zum Ausführen des lync Server 2013 Stress-und Leistungstools benötigen.</span><span class="sxs-lookup"><span data-stu-id="2e795-104">There are various hardware, software, and system configuration requirements that you’ll need to run the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="client-hardware-requirements"></a><span data-ttu-id="2e795-105">Client Hardware Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e795-105">Client Hardware Requirements</span></span>

<span data-ttu-id="2e795-106">Um das Tool für die lync Server 2013 Spannung und Leistung in ihrer lync Server 2013-Bereitstellung auszuführen, benötigen Sie für jeden 4.500-Benutzer, dessen Auslastung Sie simulieren möchten, mindestens einen dedizierten Computer, der die folgenden minimalen Hardwareanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="2e795-106">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, for every 4,500 users whose load you want to simulate, you’ll need at least one dedicated computer that meets the following minimum hardware requirements:</span></span>

  - <span data-ttu-id="2e795-107">1 Gigabit-Netzwerkadapter</span><span class="sxs-lookup"><span data-stu-id="2e795-107">1 gigabit network adapter</span></span>

  - <span data-ttu-id="2e795-108">8 GB RAM</span><span class="sxs-lookup"><span data-stu-id="2e795-108">8-GB ram</span></span>

  - <span data-ttu-id="2e795-109">2 Dual-Core-zentral Verarbeitungseinheiten (CPUs)</span><span class="sxs-lookup"><span data-stu-id="2e795-109">2 dual-core central processing units (CPUs)</span></span>

</div>

<div>

## <a name="client-software-requirements"></a><span data-ttu-id="2e795-110">Client Software Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e795-110">Client Software Requirements</span></span>

<span data-ttu-id="2e795-111">Zum Ausführen des lync Server 2013 Stress and Performance-Tools in ihrer lync Server 2013-Bereitstellung sind die folgenden Betriebssysteme unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2e795-111">To run the Lync Server 2013 Stress and Performance Tool on your Lync Server 2013 deployment, the supported operating systems are:</span></span>

  - <span data-ttu-id="2e795-112">Windows Server 2012 Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="2e795-112">Windows Server 2012 operating system</span></span>

  - <span data-ttu-id="2e795-113">Windows Server 2008 Betriebssystem (64-Bit-Edition)</span><span class="sxs-lookup"><span data-stu-id="2e795-113">Windows Server 2008 operating system (64-bit edition)</span></span>

<span data-ttu-id="2e795-114">Der Clientcomputer muss die folgenden Softwareanforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="2e795-114">Your client computer must meet the following software requirements:</span></span>

  - <span data-ttu-id="2e795-115">Sie müssen die [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) Laufzeit installiert haben.</span><span class="sxs-lookup"><span data-stu-id="2e795-115">You must have the [Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?linkid=143212) runtime installed.</span></span>

  - <span data-ttu-id="2e795-116">In Windows Server 2008/Windows Server 2012 muss das Feature "Desktop Darstellung" aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="2e795-116">On Windows Server 2008/Windows Server 2012, the Desktop Experience feature must be enabled.</span></span>

  - <span data-ttu-id="2e795-117">Sie müssen das [Microsoft Visual C++ 2012 Redistributable Package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installiert haben.</span><span class="sxs-lookup"><span data-stu-id="2e795-117">You must have the [Microsoft Visual C++ 2012 redistributable package](https://go.microsoft.com/fwlink/?linkid=143216) (x64) installed.</span></span>

  - <span data-ttu-id="2e795-118">Eine vollständig konfigurierte lync Server 2013-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="2e795-118">A fully configured Lync Server 2013 deployment.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2e795-119">Verwaltete API von Microsoft Unified Communications (UCMA) 4,0-Bibliotheken sind im Installationspaket enthalten, daher ist UCMA nicht erforderlich und sollte nicht auf Clientcomputern installiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e795-119">Microsoft Unified Communications Managed API (UCMA) 4.0 libraries are included in the installation package, so UCMA is not required and should not be installed on client computers.</span></span>



</div>

</div>

<div>

## <a name="configuration-requirements"></a><span data-ttu-id="2e795-120">Konfigurationsanforderungen</span><span class="sxs-lookup"><span data-stu-id="2e795-120">Configuration Requirements</span></span>

<span data-ttu-id="2e795-121">Die Computer, auf denen das lync Server 2013 Stress-und Leistungs Tool ausgeführt wird, müssen entsprechend den folgenden Anforderungen konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="2e795-121">The computers that will run the Lync Server 2013 Stress and Performance Tool must be configured according to the following requirements:</span></span>

1.  <span data-ttu-id="2e795-122">Sie müssen als Mitglied der Gruppe "Domänen" oder "lokale Administratoren" angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="2e795-122">You must be logged on as a member of the Domain or Local Admins group.</span></span>

2.  <span data-ttu-id="2e795-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool. exe) kann nicht auf einem Computer ausgeführt werden, auf dem auch lync Server 2013-Komponenten ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2e795-123">Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) cannot be run on a computer that is also running Lync Server 2013 components.</span></span>

3.  <span data-ttu-id="2e795-124">Sie müssen das lync Server 2013-Benutzer Erstellungstool (UserProvisioningTool. exe) auf der Front-End-Server oder auf dem Standard Edition-Server ausführen, in dem sich die Benutzerkonten befinden.</span><span class="sxs-lookup"><span data-stu-id="2e795-124">You must run the Lync Server 2013 User Creation tool (UserProvisioningTool.exe) on the Front End Server or on the Standard Edition server where the user accounts will reside.</span></span> <span data-ttu-id="2e795-125">Wenn das Tool mehrmals ausgeführt wird, muss jeder Benutzer, der für Microsoft Unified Communications aktiviert ist, über eine eindeutige Telefonnummer verfügen.</span><span class="sxs-lookup"><span data-stu-id="2e795-125">When the tool is run multiple times, each user who is enabled for Microsoft Unified Communications must have a unique phone number.</span></span>

4.  <span data-ttu-id="2e795-126">Die Größe der Auslagerungsdatei sollte vom System verwaltet werden oder sollte mindestens 1,5 mal so groß sein wie der RAM-Wert des Systems.</span><span class="sxs-lookup"><span data-stu-id="2e795-126">The page file size should be system-managed, or should be at least 1.5 times the amount of RAM on the system.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

