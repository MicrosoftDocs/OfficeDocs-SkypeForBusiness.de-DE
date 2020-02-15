---
title: Installieren des WMI-abwärts Kompatibilitätspakets
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2497fb60c4eeb0ef9bba499bd131ef6bba10f3ff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037355"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="2ae63-102">Installieren des WMI-abwärts Kompatibilitätspakets</span><span class="sxs-lookup"><span data-stu-id="2ae63-102">Install WMI Backward Compatibility package</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ae63-103">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2ae63-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2ae63-104">Wenn Sie versuchen, den Zusammenführungs-Assistenten des Topologie-Generators auszuführen, ohne das WMI-Abwärtskompatibilitätspaket zu installieren, tritt der folgende Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="2ae63-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="2ae63-105">![WMI-Fehlermeldung](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI-Fehlermeldung")</span><span class="sxs-lookup"><span data-stu-id="2ae63-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="2ae63-106">Wenn Sie versuchen, das **Merge-CsLegacytopology**-Cmdlet ohne Installieren des WMI-Abwärtskompatibilitätspakets auszuführen, erhalten Sie den folgenden Fehler:</span><span class="sxs-lookup"><span data-stu-id="2ae63-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="2ae63-107">![Fehler bei Windows PowerShell WMI-Anbieter](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Fehler bei Windows PowerShell WMI-Anbieter")</span><span class="sxs-lookup"><span data-stu-id="2ae63-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="2ae63-108">So installieren Sie das WMI-Abwärtskompatibilitätspaket</span><span class="sxs-lookup"><span data-stu-id="2ae63-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="2ae63-109">Navigieren Sie auf den Installationsmedien zu \\Setup\\amd64\\Setup\\OCSWMIBC. MSI.</span><span class="sxs-lookup"><span data-stu-id="2ae63-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="2ae63-110">Installieren Sie OCSWMIBC.MSI.</span><span class="sxs-lookup"><span data-stu-id="2ae63-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2ae63-p101">OCSWMIBC.msi muss auf dem Computer installiert werden, auf dem der Zusammenführungs-Assistent des Topologie-Generators ausgeführt wird. Es wird jedoch empfohlen, OCSWMIBC.msi auf allen Front-End-Servern in der Topologie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2ae63-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2ae63-113">OCSWMIBC. msi kann auf jedem Computer in der Domäne installiert werden, auf dem die lync Server 2013 Kernkomponenten und die lync Server 2013 Verwaltungsshell installiert sind, und über Zugriff auf die Office Communications Server 2007 R2 Topologie (WMI-Anbieter für Active Directory Domäne) verfügt. Dienste (AD DS) und SQL Server).</span><span class="sxs-lookup"><span data-stu-id="2ae63-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

