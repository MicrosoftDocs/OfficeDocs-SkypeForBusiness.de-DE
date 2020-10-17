---
title: Konfigurationsvoraussetzungen und Benutzerrechte für Gruppenanruf Pickups
description: Konfigurationsvoraussetzungen für die gruppenanrufannahme und Benutzerrechte.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74d2a758b7199634e14ee387d2554b30bf2ae8d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554451"
---
# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="de1a7-103">Konfigurieren von Voraussetzungen und Benutzerrechten für Gruppenanruf Pickups in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de1a7-103">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de1a7-104">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="de1a7-104">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="de1a7-105">Bei der gruppenanrufannahme handelt es sich um eine anrufverwaltungsfunktion, die bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert wird.</span><span class="sxs-lookup"><span data-stu-id="de1a7-105">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="de1a7-106">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die gruppenanrufannahme und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="de1a7-106">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="de1a7-107">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur gruppenanrufannahme gelesen haben (Weitere Informationen finden Sie unter [Planning for Group Call Pickup in lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="de1a7-107">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="de1a7-108">Konfigurationsvoraussetzungen für Gruppenanruf Pickups</span><span class="sxs-lookup"><span data-stu-id="de1a7-108">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="de1a7-109">Für die Gruppenanruf Abholung sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="de1a7-109">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="de1a7-110">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="de1a7-110">Application service</span></span>

  - <span data-ttu-id="de1a7-111">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="de1a7-111">Call Park application</span></span>

<span data-ttu-id="de1a7-112">Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="de1a7-112">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="de1a7-113">Gruppenanruf-Pickup-Konfiguration Benutzerrechte</span><span class="sxs-lookup"><span data-stu-id="de1a7-113">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="de1a7-114">Verwenden Sie die folgenden Verwaltungstools zum Konfigurieren der gruppenanrufannahme:</span><span class="sxs-lookup"><span data-stu-id="de1a7-114">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="de1a7-115">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="de1a7-115">Lync Server Management Shell</span></span>

  - <span data-ttu-id="de1a7-116">SEFAUtil Resource Kit-Tool</span><span class="sxs-lookup"><span data-stu-id="de1a7-116">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="de1a7-117">Verwenden Sie lync Server-Verwaltungsshell zum Erstellen und Verwalten von Anrufgruppen in der Orbit-Tabelle für das Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="de1a7-117">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="de1a7-118">Verwenden Sie das SEFAUtil Resource Kit-Tool, um eine Anrufannahme Gruppe zuzuweisen und die gruppenanrufannahme für Benutzer zu aktivieren oder um die gruppenanrufannahme für Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="de1a7-118">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="de1a7-119">Für die Konfiguration der gruppenanrufannahme sind je nach Aufgabe die folgenden Administratorrollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="de1a7-119">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="de1a7-120">**CsVoiceAdministrator:** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="de1a7-120">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="de1a7-121">**CsUserAdministrator:** Diese Administratorrolle kann die gruppenanrufannahme für Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de1a7-121">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="de1a7-122">Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="de1a7-122">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="de1a7-123">**CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="de1a7-123">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="de1a7-124">**CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="de1a7-124">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="de1a7-125">Ausführliche Informationen zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="de1a7-125">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="de1a7-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de1a7-126">See Also</span></span>


[<span data-ttu-id="de1a7-127">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de1a7-127">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="de1a7-128">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de1a7-128">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

