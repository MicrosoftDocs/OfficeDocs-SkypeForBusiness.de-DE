---
title: Voraussetzungen für Gruppenanruf-Pickup-Konfiguration und Benutzerrechte
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
ms.openlocfilehash: 2ed2a44ccd1730de2ebede4b08c1a4d3d7e0da9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a><span data-ttu-id="99003-102">Voraussetzungen für Gruppenanruf-Pickup-Konfiguration und Benutzerrechte in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99003-102">Group Call Pickup configuration prerequisites and user rights in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99003-103">_**Letztes Änderungsdatum des Themas:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="99003-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="99003-104">Bei der Gruppenanruf Abholung handelt es sich um ein Anruf Verwaltungsfeature, das standardmäßig bei der Bereitstellung von Enterprise-VoIP installiert wird.</span><span class="sxs-lookup"><span data-stu-id="99003-104">Group Call Pickup is a call management feature that is installed by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="99003-105">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die Gruppenanruf Abholung und die Benutzerrechte konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="99003-105">This topic describes what you need to have in place before you can configure Group Call Pickup and the user rights that you need to perform configuration tasks.</span></span>

<span data-ttu-id="99003-106">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation gelesen haben, die sich auf die Gruppenanruf Abholung bezieht (siehe [Planen der Gruppenanruf Abholung in lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span><span class="sxs-lookup"><span data-stu-id="99003-106">This section assumes that you have read the planning documentation related to Group Call Pickup (see [Planning for Group Call Pickup in Lync Server 2013](lync-server-2013-planning-for-group-call-pickup.md)).</span></span>

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a><span data-ttu-id="99003-107">Voraussetzungen für Gruppenanruf-Pickup-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="99003-107">Group Call Pickup Configuration Prerequisites</span></span>

<span data-ttu-id="99003-108">Für die Gruppenanruf Abholung sind die folgenden Komponenten erforderlich:</span><span class="sxs-lookup"><span data-stu-id="99003-108">Group Call Pickup requires the following components:</span></span>

  - <span data-ttu-id="99003-109">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="99003-109">Application service</span></span>

  - <span data-ttu-id="99003-110">Anwendung zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="99003-110">Call Park application</span></span>

<span data-ttu-id="99003-111">Diese Komponenten werden automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="99003-111">These components are installed automatically when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a><span data-ttu-id="99003-112">Benutzerrechte für Gruppenanruf-Pickup-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="99003-112">Group Call Pickup Configuration User Rights</span></span>

<span data-ttu-id="99003-113">Sie verwenden die folgenden Verwaltungstools, um die Gruppenanruf Abholung zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="99003-113">You use the following administrative tools to configure Group Call Pickup:</span></span>

  - <span data-ttu-id="99003-114">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="99003-114">Lync Server Management Shell</span></span>

  - <span data-ttu-id="99003-115">SEFAUtil Resource Kit-Tool</span><span class="sxs-lookup"><span data-stu-id="99003-115">SEFAUtil resource kit tool</span></span>

<span data-ttu-id="99003-116">Verwenden Sie die lync Server-Verwaltungsshell zum Erstellen und Verwalten von Anruf-Abhol Gruppen in der Orbit-Tabelle des Anruf Parks.</span><span class="sxs-lookup"><span data-stu-id="99003-116">Use Lync Server Management Shell to create and manage call pickup groups in the Call Park orbit table.</span></span> <span data-ttu-id="99003-117">Verwenden Sie das SEFAUtil Resource Kit-Tool, um eine Anruf Abhol Gruppe zuzuweisen und die Gruppenanruf Abholung für Benutzer zu aktivieren oder die Gruppenanruf Abholung für Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="99003-117">Use the SEFAUtil resource kit tool to assign a call pickup group and enable Group Call Pickup for users or to disable Group Call Pickup for users.</span></span>

<span data-ttu-id="99003-118">Die Konfiguration der Gruppenanruf Abholung erfordert je nach Aufgabe eine der folgenden Administratorrollen:</span><span class="sxs-lookup"><span data-stu-id="99003-118">Configuring Group Call Pickup requires any of the following administrative roles, depending on the task:</span></span>

  - <span data-ttu-id="99003-119">**CsVoiceAdministrator:** Diese Administratorrolle kann alle sprachbezogenen Einstellungen und Richtlinien erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="99003-119">**CsVoiceAdministrator:** This administrator role can create, configure, and manage all voice-related settings and policies.</span></span>

  - <span data-ttu-id="99003-120">**CsUserAdministrator:** Mit dieser Administratorrolle kann die Gruppenanruf Abholung für Benutzer aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="99003-120">**CsUserAdministrator:** This administrator role can enable Group Call Pickup for users.</span></span> <span data-ttu-id="99003-121">Diese Administratorrolle verfügt auch über die schreibgeschützte Ansicht Zugriff auf alle Sprachkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="99003-121">This administrator role also has read-only view access to all voice configurations.</span></span>

  - <span data-ttu-id="99003-122">**CsServerAdministrator:** Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen.</span><span class="sxs-lookup"><span data-stu-id="99003-122">**CsServerAdministrator:** This administrator role can manage, monitor, and troubleshoot servers and services.</span></span>

  - <span data-ttu-id="99003-123">**CsAdministrator:** Diese Administratorrolle kann alle Aufgaben von CsVoiceAdministrator, CsServerAdministrator und CsUserAdministrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="99003-123">**CsAdministrator:** This administrator role can perform all of the tasks of CsVoiceAdministrator, CsServerAdministrator, and CsUserAdministrator.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="99003-124">Details zu Administratorrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planen der rollenbasierten Zugriffssteuerung in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="99003-124">For details about administrative rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="99003-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99003-125">See Also</span></span>


[<span data-ttu-id="99003-126">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99003-126">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="99003-127">Planen der Anruf Verwaltungsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99003-127">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

