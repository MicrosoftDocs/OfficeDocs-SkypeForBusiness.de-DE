---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Mitgliedsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48af9dd5b35676ee0141b771f8e50e1fbdedae6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="af2d8-102">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af2d8-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af2d8-103">_**Letztes Änderungsstand des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="af2d8-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="af2d8-104">Wenn ein Server mit einer der folgenden Serverrollen ausfällt, führen Sie das Verfahren in diesem Thema aus, um den Server wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="af2d8-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="af2d8-105">Sollten mehrere Server unabhängig voneinander ausfallen, führen Sie diese Schritte für jeden einzelnen Server aus.</span><span class="sxs-lookup"><span data-stu-id="af2d8-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="af2d8-106">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="af2d8-106">Front End Server</span></span>

  - <span data-ttu-id="af2d8-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="af2d8-107">Mediation Server</span></span>

  - <span data-ttu-id="af2d8-108">Director</span><span class="sxs-lookup"><span data-stu-id="af2d8-108">Director</span></span>

  - <span data-ttu-id="af2d8-109">Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="af2d8-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="af2d8-110">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="af2d8-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="af2d8-111">Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="af2d8-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="af2d8-112">Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="af2d8-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="af2d8-113">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="af2d8-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="af2d8-114">So stellen Sie einen Mitgliedsserver wieder her</span><span class="sxs-lookup"><span data-stu-id="af2d8-114">To restore a member server</span></span>

1.  <span data-ttu-id="af2d8-115">Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) als fehlerhaften Server, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="af2d8-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af2d8-116">Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="af2d8-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="af2d8-117">Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei dem Server an, den Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="af2d8-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="af2d8-118">Wechseln Sie zum lync Server Installationsordner oder Medien, und starten Sie den lync Server-Bereitstellungs \\-\\Assistenten\\, der sich unter Setup amd64 Setup. exe befindet.</span><span class="sxs-lookup"><span data-stu-id="af2d8-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="af2d8-119">Folgen Sie dem Bereitstellungs-Assistenten, um folgende Schritte auszuführen:</span><span class="sxs-lookup"><span data-stu-id="af2d8-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="af2d8-120">Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="af2d8-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="af2d8-121">Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server Komponenten** aus, um die lync Server-Server Rolle zu installieren.</span><span class="sxs-lookup"><span data-stu-id="af2d8-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="af2d8-122">Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="af2d8-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="af2d8-123">Führen Sie **Schritt 4: Dienste starten** aus, um die Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="af2d8-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="af2d8-124">Ausführliche Informationen zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="af2d8-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

