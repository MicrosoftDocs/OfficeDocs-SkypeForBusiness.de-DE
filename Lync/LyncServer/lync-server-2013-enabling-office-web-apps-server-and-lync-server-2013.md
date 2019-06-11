---
title: 'Lync Server 2013: Aktivieren von Office Web Apps Server und Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a88a9a1649d8842c9c2c4a1f55aefcfc7853e05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="6729b-102">Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6729b-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6729b-103">_**Letztes Änderungsdatum des Themas:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="6729b-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="6729b-104">Lync Server 2013 verwendet Office Web Apps Server für die Behandlung von PowerPoint-Präsentationen.</span><span class="sxs-lookup"><span data-stu-id="6729b-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="6729b-105">Informationen zu den Vorteilen dieses Ansatzes finden Sie unter [Übersicht über Webkonferenzen in lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6729b-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="6729b-106">Um diese neuen Funktionen verwenden zu können, müssen Administratoren Office Web Apps Server installieren und lync Server 2013 für die Kommunikation mit Office Web Apps Server konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6729b-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="6729b-107">Diese Dokumentation enthält Informationen zum Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="6729b-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="6729b-108">Diese Dokumentation bietet keine Informationen dazu, wie Sie Office Web Apps Server selbst installieren können. Informationen hierzu finden Sie auf <http://go.microsoft.com/fwlink/p/?linkid=257525>der Microsoft Office Web Apps-Bereitstellungswebsite unter.</span><span class="sxs-lookup"><span data-stu-id="6729b-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="6729b-109">Dieser Leitfaden enthält alle erforderlichen Informationen für Office Web Apps Server. Beachten Sie, dass der Office Web Apps-Server auf einem eigenständigen Computer installiert sein sollte, auf dem lync Server, Microsoft SQL Server oder eine andere Serveranwendung nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6729b-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="6729b-110">(Auf diesem Computer darf keine Version von Microsoft Office installiert sein.) Auf jedem Computer, auf dem Office Web Apps-Server ausgeführt wird, muss auch eine bestimmte Softwaregruppe installiert sein (einschließlich .NET Framework 4,5 und Windows PowerShell 3,0). Diese Anforderungen sowie Informationen zum Konfigurieren von Zertifikaten und Internet Informationsdienste (IIS) werden ausführlich auf der Microsoft Office Web Apps-Bereitstellungswebsite unter <http://go.microsoft.com/fwlink/p/?linkid=257525>erläutert.</span><span class="sxs-lookup"><span data-stu-id="6729b-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6729b-111">Die neueste Iteration von Office Web Apps Server heißt Office Online Server, der von lync Server 2013 unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6729b-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="6729b-112">Weitere Informationen finden Sie in der <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server-Dokumentation</A>.</span><span class="sxs-lookup"><span data-stu-id="6729b-112">For more detail, refer to the <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="6729b-113">In diesem Dokument werden die folgenden Themenbereiche behandelt:</span><span class="sxs-lookup"><span data-stu-id="6729b-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="6729b-114">Konfigurieren von lync Server 2013 für die Zusammenarbeit mit Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="6729b-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="6729b-115">Veröffentlichen von Office Web Apps Server in lync Server 2013 mit einem Reverse Proxy Server</span><span class="sxs-lookup"><span data-stu-id="6729b-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="6729b-116">Überprüfen der Konfiguration von Office Web Apps Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6729b-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="6729b-117">Konfigurieren von Clients von lync Server 2013 zur Verwendung mit Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="6729b-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

