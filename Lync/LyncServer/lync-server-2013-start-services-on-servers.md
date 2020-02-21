---
title: 'Lync Server 2013: Starten von Diensten auf Servern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cab7d2e53b981cc971284cfad37f89ca4749590
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="653f6-102">Starten von Diensten auf Servern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="653f6-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="653f6-103">_**Letztes Änderungsstand des Themas:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="653f6-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="653f6-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein, oder an Sie müssen geeignete Berechtigungen delegiert worden sein.</span><span class="sxs-lookup"><span data-stu-id="653f6-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="653f6-105">Ausführliche Informationen zum Delegieren von Berechtigungen finden Sie im Thema [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="653f6-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="653f6-106">Nachdem Sie den lokalen Konfigurationsspeicher auf Ihren Servern installiert, die lync Server 2013 Komponenten installiert und Zertifikate auf einem Front-End-Server oder Front-End-Server konfiguriert haben, müssen Sie die lync Server 2013 Dienste auf dem Server starten.</span><span class="sxs-lookup"><span data-stu-id="653f6-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="653f6-107">Verwenden Sie das folgende Verfahren, um Dienste auf jeder Front-End-Server in Ihrer Bereitstellung zu starten.</span><span class="sxs-lookup"><span data-stu-id="653f6-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="653f6-108">So starten Sie Dienste auf einer Standard Edition oder Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="653f6-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="653f6-109">Klicken Sie im lync Server-Bereitstellungs-Assistenten auf der Seite **lync Server 2013** auf **Ausführen** neben **Schritt 4: Dienste starten**.</span><span class="sxs-lookup"><span data-stu-id="653f6-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="653f6-110">Klicken Sie auf der Seite **Dienste starten** auf **weiter** , um die lync Server Dienste auf dem Server zu starten.</span><span class="sxs-lookup"><span data-stu-id="653f6-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="653f6-111">Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="653f6-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="653f6-112">Der Befehl zum Starten der Dienste auf dem Server ist eine Best-Effort-Methode zum Anzeigen, dass die Dienste wirklich gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="653f6-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="653f6-113">Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider.</span><span class="sxs-lookup"><span data-stu-id="653f6-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="653f6-114">Es wird empfohlen, den Schritt <STRONG>Dienststatus (optional)</STRONG> unmittelbar nach Ausführung des Schritts <STRONG>Dienste starten</STRONG> auszuführen und mithilfe der Microsoft Management Console (MMC) zu bestätigen, dass die Dienste erfolgreich gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="653f6-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="653f6-115">Wenn lync Server Dienst noch nicht gestartet wurde, können Sie in der MMC mit der rechten Maustaste auf diesen Dienst klicken, und klicken Sie dann auf <STRONG>starten</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="653f6-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

