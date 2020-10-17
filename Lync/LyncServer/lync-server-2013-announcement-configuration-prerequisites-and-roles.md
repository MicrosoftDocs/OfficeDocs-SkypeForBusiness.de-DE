---
title: 'Lync Server 2013: Voraussetzungen und Rollen für die Ankündigungs Konfiguration'
description: 'Lync Server 2013: Voraussetzungen und Rollen für die Ankündigungs Konfiguration.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e6e7009adc6826c255e28ddda925b0e9be5fd6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561891"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="15718-103">Voraussetzungen und Rollen für die Ankündigungs Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15718-103">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15718-104">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="15718-104">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="15718-105">Announcement ist eine Enterprise-VoIP-anrufverwaltungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="15718-105">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="15718-106">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die Ankündigung und die Rollenzuweisungen konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="15718-106">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="15718-107">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur Ankündigung gelesen haben (siehe [Planung der anrufverwaltungsfunktionen in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="15718-107">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="15718-108">Konfigurationsvoraussetzungen für Ansagen</span><span class="sxs-lookup"><span data-stu-id="15718-108">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="15718-109">Die Ankündigungsanwendung erfordert die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="15718-109">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="15718-110">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="15718-110">Application service</span></span>

  - <span data-ttu-id="15718-111">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="15718-111">Response Group application</span></span>

  - <span data-ttu-id="15718-112">Dateispeicher für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="15718-112">File Store, to hold audio files</span></span>

<span data-ttu-id="15718-113">All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="15718-113">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="15718-114">Rollen für die Konfiguration von Ansagen</span><span class="sxs-lookup"><span data-stu-id="15718-114">Announcement Configuration Roles</span></span>

<span data-ttu-id="15718-115">Sie können Ansagen mithilfe der folgenden Verwaltungstools konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="15718-115">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="15718-116">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="15718-116">Lync Server Control Panel</span></span>

  - <span data-ttu-id="15718-117">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="15718-117">Lync Server Management Shell</span></span>

<span data-ttu-id="15718-118">Für das Konfigurieren von Ankündigungsanwendung ist eine der folgenden Administratorrollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="15718-118">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="15718-119">**CsVoiceAdministrator**     Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien einschließlich Ankündigungseinstellungen erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="15718-119">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="15718-120">**CsServerAdministrator**     Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen und alle Ankündigungseinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="15718-120">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="15718-121">**CsAdministrator**     Diese Administratorrolle kann alle administrativen Aufgaben ausführen und alle Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="15718-121">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="15718-122">**CsViewOnlyAdministrator**     Diese Administratorrolle kann die Bereitstellung anzeigen, um den Bereitstellungsstatus zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="15718-122">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15718-123">Ausführliche Informationen zu Administrator Benutzerrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="15718-123">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="15718-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15718-124">See Also</span></span>


[<span data-ttu-id="15718-125">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15718-125">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="15718-126">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15718-126">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

