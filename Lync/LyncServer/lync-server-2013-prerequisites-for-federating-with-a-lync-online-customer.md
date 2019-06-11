---
title: 'Lync Server 2013: Voraussetzungen für die Föderation mit einem lync Online-Kunden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af3db1918e2d347084f1bbdcdf5ea4eb92ae8d91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="32742-102">Voraussetzungen für die Föderation mit einem lync Online-Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32742-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32742-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="32742-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="32742-104">Um eine Föderation mit einem lync Online 2010-Kunden zu verbinden, sollten Sie die anfängliche Bereitstellung und Konfiguration von lync Server 2013 in Ihrer Organisation bereits abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="32742-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="32742-105">Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="32742-105">This includes the following:</span></span>

  - <span data-ttu-id="32742-106">Bereitstellen von mindestens einem Standard Edition-Server oder einem Enterprise Edition-Front-End-Pool in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="32742-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="32742-107">Details zum Bereitstellen interner Server finden Sie unter [Bereitstellen von lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="32742-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="32742-108">Aktivieren interner Benutzerkonten für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32742-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="32742-109">Ausführliche Informationen finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="32742-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="32742-110">Bereitstellen von mindestens einem Edgeserver und den anderen Komponenten, die für die Unterstützung des Zugriffs durch externe Benutzer erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="32742-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="32742-111">Ausführliche Informationen finden Sie unter [Verwalten des Föderations-und des externen Zugriffs auf lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="32742-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="32742-112">Aktivieren der Föderations Unterstützung in Ihrer Organisation und Konfigurieren der geeigneten Methode zum Steuern des Zugriffs durch Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="32742-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="32742-113">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) und [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="32742-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="32742-114">Aktivieren des Zugriffs externer Benutzer für Benutzer in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="32742-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="32742-115">Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) und in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="32742-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

