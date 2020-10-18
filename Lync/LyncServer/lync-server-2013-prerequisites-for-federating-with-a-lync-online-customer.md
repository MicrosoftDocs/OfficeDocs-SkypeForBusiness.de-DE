---
title: 'Lync Server 2013: Voraussetzungen für die verbundierung mit einem lync Online-Kunden'
description: 'Lync Server 2013: Voraussetzungen für die verbundierung mit einem lync Online-Kunden.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99eabd4466385402d5e5983665e9349f1244348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579861"
---
# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="9a5db-103">Voraussetzungen für die verbundierung mit einem lync Online-Kunden in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a5db-103">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a5db-104">_**Letztes Änderungsstand des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9a5db-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9a5db-105">Um einen Verbund mit einem lync Online 2010-Kunden abzuschließen, sollten Sie die anfängliche Bereitstellung und Konfiguration von lync Server 2013 in Ihrer Organisation bereits abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="9a5db-105">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="9a5db-106">Dazu gehört Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9a5db-106">This includes the following:</span></span>

  - <span data-ttu-id="9a5db-107">Bereitstellen von mindestens einem Standard Edition-Server oder einem Enterprise Edition-Front-End-Pool in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-107">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="9a5db-108">Ausführliche Informationen zum Bereitstellen interner Server finden Sie unter [Deploying lync Server 2013](lync-server-2013-deploying-lync-server.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-108">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="9a5db-109">Aktivieren interner Benutzerkonten für lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a5db-109">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="9a5db-110">Ausführliche Informationen finden Sie unter [deaktivieren oder erneutes Aktivieren des Benutzerkontos für lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-110">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="9a5db-111">Bereitstellen von mindestens einem Edgeserver und den anderen Komponenten, die zur Unterstützung des Zugriffs durch externe Benutzer erforderlich sind</span><span class="sxs-lookup"><span data-stu-id="9a5db-111">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="9a5db-112">Ausführliche Informationen finden Sie unter [Managing Federation and External Access to lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-112">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="9a5db-113">Aktivieren der Verbundunterstützung in Ihrer Organisation und Konfigurieren der geeigneten Methode für die Steuerung des Zugriffs durch Verbunddomänen.</span><span class="sxs-lookup"><span data-stu-id="9a5db-113">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="9a5db-114">Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) und [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-114">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="9a5db-115">Aktivieren des Zugriffs externer Benutzer für Benutzer in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-115">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="9a5db-116">Ausführliche Informationen finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) und in der Bereitstellungsdokumentation oder Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9a5db-116">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

