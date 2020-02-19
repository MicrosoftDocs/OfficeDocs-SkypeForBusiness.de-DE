---
title: Konfigurationsvoraussetzungen und Benutzerrechte für Gruppenanruf Pickups
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
ms.openlocfilehash: 6344dea7e4ba4273905af6549ced3f900922e4e5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140308"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="fe284-102">Konfigurieren von Voraussetzungen und Benutzerrechten für Gruppenanruf Pickups in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe284-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe284-103">_**Letztes Änderungsstand des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="fe284-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="fe284-104">Bei der gruppenanrufannahme handelt es sich um eine anrufverwaltungsfunktion, die bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert wird.</span><span class="sxs-lookup"><span data-stu-id="fe284-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="fe284-105">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die gruppenanrufannahme und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="fe284-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="fe284-106">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur gruppenanrufannahme gelesen haben (Weitere Informationen finden Sie unter [Planning for Group Call Pickup in lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="fe284-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="fe284-107">Konfigurationsvoraussetzungen für Gruppenanruf Pickups</span><span class="sxs-lookup"><span data-stu-id="fe284-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="fe284-108">Für die Gruppenanruf Abholung sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="fe284-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="fe284-109">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="fe284-109">Application service</span></span>

  - <span data-ttu-id="fe284-110">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="fe284-110">Call Park application</span></span>

<span data-ttu-id="fe284-111">Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fe284-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="fe284-112">Gruppenanruf-Pickup-Konfiguration Benutzerrechte</span><span class="sxs-lookup"><span data-stu-id="fe284-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="fe284-113">Verwenden Sie die folgenden Verwaltungstools zum Konfigurieren der gruppenanrufannahme:</span><span class="sxs-lookup"><span data-stu-id="fe284-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="fe284-114">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="fe284-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="fe284-115">SEFAUtil Resource Kit-Tool</span><span class="sxs-lookup"><span data-stu-id="fe284-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="fe284-116">Verwenden Sie lync Server-Verwaltungsshell zum Erstellen und Verwalten von Anrufgruppen in der Orbit-Tabelle für das Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="fe284-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="fe284-117">Verwenden Sie das SEFAUtil Resource Kit-Tool, um eine Anrufannahme Gruppe zuzuweisen und die gruppenanrufannahme für Benutzer zu aktivieren oder um die gruppenanrufannahme für Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe284-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="fe284-118">Für die Konfiguration der gruppenanrufannahme sind je nach Aufgabe die folgenden Administratorrollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="fe284-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="fe284-119">**CsVoiceAdministrator:** Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="fe284-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="fe284-120">**CsUserAdministrator:** Diese Administratorrolle kann die gruppenanrufannahme für Benutzer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe284-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="fe284-121">Diese Administratorrolle hat außerdem schreibgeschützten Zugriff auf alle VoIP-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="fe284-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="fe284-122">**CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="fe284-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="fe284-123">**CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="fe284-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="fe284-124">Ausführliche Informationen zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="fe284-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fe284-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe284-125">See Also</span></span>


[<span data-ttu-id="fe284-126">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe284-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="fe284-127">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe284-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

