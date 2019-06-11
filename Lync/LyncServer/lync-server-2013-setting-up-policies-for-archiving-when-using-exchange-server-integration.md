---
title: Einrichten von Richtlinien für die Archivierung bei Verwendung der Exchange Server-Integration
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e5f5bf1bcfa9b11a96722df1f6ff7535912bb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="0871b-102">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung der Exchange Server-Integration</span><span class="sxs-lookup"><span data-stu-id="0871b-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0871b-103">_**Letztes Änderungsdatum des Themas:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0871b-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0871b-104">Wenn für Benutzer, die sich in Exchange 2013 befinden, ihre Postfächer in-situ-Speicher abgelegt werden, Steuern Exchange-in-situ-Speicherrichtlinien die Archivierung für diese Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0871b-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="0871b-105">Wenn Sie die Microsoft Exchange-Integration für Ihre Bereitstellung verwenden, überschreiben Exchange 2013-Richtlinien lync Server-Archivierungsrichtlinien für Benutzer, die in Exchange 2013 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0871b-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="0871b-106">Informationen zum Konfigurieren von Exchange-Archivierungsrichtlinien finden Sie in der Exchange 2013-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="0871b-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="0871b-107">Ausführliche Informationen zum Einrichten von Benutzerrichtlinien für Benutzer, die sich in lync Server 2013 befinden, finden Sie unter [Einrichten von Benutzerrichtlinien für die Archivierung in lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0871b-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="0871b-108">Ausführliche Informationen zur Funktionsweise von Richtlinien finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0871b-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="0871b-109">Wenn Sie Exchange 2013 und lync Server 2013 in derselben Gesamtstruktur bereitstellen, steuern Ihre Exchange 2013 in-situ-Speicherrichtlinien die Archivierung.</span><span class="sxs-lookup"><span data-stu-id="0871b-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="0871b-110">Wenn Sie Exchange 2013 und lync Server 2013 in getrennten Gesamtstrukturen bereitstellen, lesen Sie "Bereitstellen von lync Server und Microsoft Exchange in verschiedenen Gesamtstrukturen" in der <A href="lync-server-2013-deployment-checklist-for-archiving.md">Bereitstellungsprüfliste für die Archivierung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0871b-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

