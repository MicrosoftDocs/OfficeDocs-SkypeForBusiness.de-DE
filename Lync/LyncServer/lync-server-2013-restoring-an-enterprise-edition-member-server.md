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
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="d9be0-102">Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9be0-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9be0-103">_**Letztes Änderungsdatum des Themas:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d9be0-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d9be0-104">Wenn auf einem Server, auf dem eine der folgenden Serverrollen ausgeführt wird, ein Fehler auftritt, führen Sie die Schritte in diesem Thema aus, um den Server wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d9be0-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="d9be0-105">Wenn mehrere Server unabhängig voneinander auftreten, führen Sie das Verfahren für jeden Server aus.</span><span class="sxs-lookup"><span data-stu-id="d9be0-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="d9be0-106">Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="d9be0-106">Front End Server</span></span>

  - <span data-ttu-id="d9be0-107">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="d9be0-107">Mediation Server</span></span>

  - <span data-ttu-id="d9be0-108">Director</span><span class="sxs-lookup"><span data-stu-id="d9be0-108">Director</span></span>

  - <span data-ttu-id="d9be0-109">Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="d9be0-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="d9be0-110">Edgeserver</span><span class="sxs-lookup"><span data-stu-id="d9be0-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d9be0-111">Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="d9be0-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="d9be0-112">Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht.</span><span class="sxs-lookup"><span data-stu-id="d9be0-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="d9be0-113">Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.</span><span class="sxs-lookup"><span data-stu-id="d9be0-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="d9be0-114">So stellen Sie einen Mitgliedsserver wieder her</span><span class="sxs-lookup"><span data-stu-id="d9be0-114">To restore a member server</span></span>

1.  <span data-ttu-id="d9be0-115">Beginnen Sie mit einem sauberen oder neuen Server, der den gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server aufweist, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.</span><span class="sxs-lookup"><span data-stu-id="d9be0-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d9be0-116">Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="d9be0-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="d9be0-117">Melden Sie sich von einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei dem Server an, den Sie wiederherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="d9be0-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="d9be0-118">Navigieren Sie zum lync Server-Installationsordner oder-Medium, und starten Sie den lync Server- \\Bereitstellungs-Assistenten unter Setup\\amd64\\Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="d9be0-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="d9be0-119">Folgen Sie dem Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d9be0-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="d9be0-120">Führen Sie **Schritt 1: Installieren des lokalen Konfigurationsspeichers** aus, um die lokalen Konfigurationsdateien zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d9be0-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="d9be0-121">Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** aus, um die lync Server-Serverrolle zu installieren.</span><span class="sxs-lookup"><span data-stu-id="d9be0-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="d9be0-122">Führen Sie **Schritt 3 aus: anfordern, installieren oder Zuweisen von Zertifikaten** zum Zuweisen der Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="d9be0-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="d9be0-123">Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="d9be0-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="d9be0-124">Details zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="d9be0-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

