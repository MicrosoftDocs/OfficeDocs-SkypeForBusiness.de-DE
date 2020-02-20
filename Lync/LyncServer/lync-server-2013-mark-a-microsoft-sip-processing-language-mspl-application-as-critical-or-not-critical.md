---
title: 'Lync Server 2013: Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45f763f9afbb52247bc3571a4d17f415c344e87e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="c5cae-102">Markieren einer MSPL-Anwendung (Microsoft SIP Processing Language) als kritisch oder nicht kritisch in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5cae-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5cae-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c5cae-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c5cae-104">MSPL-Serveranwendungen (Microsoft SIP Processing Language) sind nur Skriptanwendungen, die die MSPL-Skriptsprache anstelle der Microsoft lync 2010 API verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5cae-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="c5cae-105">Einige MSPL-Serveranwendungen werden als kritisch eingestuft.</span><span class="sxs-lookup"><span data-stu-id="c5cae-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="c5cae-106">Wenn ein Skript kritisch ist, muss das Skript beim Systemstart gestartet werden, damit lync Server 2013 gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c5cae-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="c5cae-107">Wenn das Skript fehlschlägt, während lync Server ausgeführt wird, wird der Server nicht heruntergefahren, aber das Senden des Datenverkehrs an das Skript wird beendet, und es werden Fehler im Ereignisprotokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5cae-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="c5cae-108">Sie können lync Server-Systemsteuerung verwenden, um MSPL-Server Anwendungen (Microsoft SIP Processing Language) als kritisch zu kennzeichnen oder Sie zu markieren.</span><span class="sxs-lookup"><span data-stu-id="c5cae-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="c5cae-p102">Nicht alle Skripts unterstützen diese Option. Beispielsweise ist das DefaultRouting-Skript als kritisch markiert, und diese Option kann für "DefaultRouting" nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c5cae-p102">Not all scripts support this option. For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="c5cae-111">So markieren Sie eine MSPL-Serveranwendung als kritisch oder heben die Markierung auf</span><span class="sxs-lookup"><span data-stu-id="c5cae-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="c5cae-112">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="c5cae-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="c5cae-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c5cae-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c5cae-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c5cae-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c5cae-115">Klicken Sie in der linken Navigationsleiste auf **Topologie** und dann auf **Serveranwendung**.</span><span class="sxs-lookup"><span data-stu-id="c5cae-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="c5cae-116">Klicken Sie auf der Seite **Serveranwendung** auf eine Spaltenüberschrift, um die Anwendungen ggf. zu sortieren, und klicken Sie dann auf die Serveranwendung, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c5cae-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="c5cae-117">Klicken Sie auf **Aktion**.</span><span class="sxs-lookup"><span data-stu-id="c5cae-117">Click **Action**.</span></span>

6.  <span data-ttu-id="c5cae-118">Klicken Sie auf **Als kritisch markieren** oder **Markierung aufheben** (sofern das Skript diese Option unterstützt).</span><span class="sxs-lookup"><span data-stu-id="c5cae-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5cae-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5cae-119">See Also</span></span>


[<span data-ttu-id="c5cae-120">Aktivieren oder Deaktivieren einer MSPL-Serveranwendung (Microsoft SIP Processing Language) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5cae-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="c5cae-121">Anzeigen von MSPL-Serveranwendungen (Microsoft SIP Processing Language) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5cae-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="c5cae-122">Verwalten der lync Server 2013 Topologie</span><span class="sxs-lookup"><span data-stu-id="c5cae-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

