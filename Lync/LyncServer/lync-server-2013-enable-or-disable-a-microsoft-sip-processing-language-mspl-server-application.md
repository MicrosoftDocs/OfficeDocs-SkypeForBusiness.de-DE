---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren einer MSPL-Server Anwendung (Microsoft SIP Processing Language)'
description: 'Lync Server 2013: Aktivieren oder Deaktivieren einer MSPL-Server Anwendung (Microsoft SIP Processing Language).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f919599d6c6a39fea73424f4e287f00636c0982
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544781"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="9896d-103">Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9896d-103">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9896d-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="9896d-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="9896d-105">Sie können lync Server-Systemsteuerung verwenden, um MSPL-Server Anwendungen (Microsoft SIP Processing Language) zu aktivieren oder zu deaktivieren, die in ihrer lync Server 2013 Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9896d-105">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="9896d-106">Bei diesen Anwendungen handelt es sich nur um skriptbasierte Anwendungen, die anstelle der Microsoft lync 2013 Preview-API eine Skriptsprache verwenden.</span><span class="sxs-lookup"><span data-stu-id="9896d-106">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="9896d-107">Nicht alle Skripts können aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="9896d-107">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="9896d-108">Beispielsweise ist das DefaultRouting-Skript aktiviert, und diese Option kann für DefaultRouting nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="9896d-108">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="9896d-109">So aktivieren oder deaktivieren Sie eine MSPL-Serveranwendung</span><span class="sxs-lookup"><span data-stu-id="9896d-109">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="9896d-110">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="9896d-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="9896d-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9896d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9896d-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9896d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9896d-113">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Serveranwendung**.</span><span class="sxs-lookup"><span data-stu-id="9896d-113">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="9896d-114">Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen ggf. zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="9896d-114">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="9896d-115">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="9896d-115">Click **Action**.</span></span>

6.  <span data-ttu-id="9896d-116">Klicken Sie auf Anwendung **aktivieren** oder **Anwendung deaktivieren** (das heißt, wenn das Skript diese Option unterstützt).</span><span class="sxs-lookup"><span data-stu-id="9896d-116">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9896d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9896d-117">See Also</span></span>


[<span data-ttu-id="9896d-118">Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9896d-118">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="9896d-119">Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9896d-119">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="9896d-120">Verwalten der lync Server 2013 Topologie</span><span class="sxs-lookup"><span data-stu-id="9896d-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

