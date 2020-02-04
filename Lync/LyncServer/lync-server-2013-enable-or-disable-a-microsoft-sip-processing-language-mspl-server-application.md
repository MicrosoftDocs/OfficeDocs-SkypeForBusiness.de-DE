---
title: 'Lync Server 2013: Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Server Anwendung'
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
ms.openlocfilehash: 12fb1160742898b65b14ea17bc10a9c6ed56c780
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736205"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="b1810-102">Aktivieren oder Deaktivieren einer Microsoft SIP Processing Language (MSPL)-Serveranwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1810-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1810-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b1810-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="b1810-104">Sie können die lync Server-Systemsteuerung verwenden, um MSPL-Serveranwendungen (Microsoft SIP Processing Language) zu aktivieren oder zu deaktivieren, die in ihrer lync Server 2013-Umgebung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b1810-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="b1810-105">Bei diesen Anwendungen handelt es sich um nur-Skript-Anwendungen, die eine Skriptsprache anstelle der Microsoft lync 2013 Preview-API verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1810-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="b1810-106">Nicht alle Skripts können aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b1810-106">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="b1810-107">Beispielsweise ist das DefaultRouting-Skript aktiviert, und diese Option kann für DefaultRouting nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="b1810-107">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="b1810-108">So aktivieren oder deaktivieren Sie eine MSPL-Serveranwendung</span><span class="sxs-lookup"><span data-stu-id="b1810-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="b1810-109">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="b1810-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="b1810-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b1810-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b1810-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b1810-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b1810-112">Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie dann auf **Server Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="b1810-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="b1810-113">Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="b1810-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="b1810-114">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="b1810-114">Click **Action**.</span></span>

6.  <span data-ttu-id="b1810-115">Klicken Sie auf Anwendung **aktivieren** oder **Anwendung deaktivieren** (das heißt, wenn das Skript diese Option unterstützt).</span><span class="sxs-lookup"><span data-stu-id="b1810-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b1810-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1810-116">See Also</span></span>


[<span data-ttu-id="b1810-117">Kennzeichnen einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1810-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="b1810-118">Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b1810-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="b1810-119">Verwalten der Lync Server 2013-Topologie</span><span class="sxs-lookup"><span data-stu-id="b1810-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

