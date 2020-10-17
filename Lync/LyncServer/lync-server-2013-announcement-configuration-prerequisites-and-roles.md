---
title: 'Lync Server 2013: Voraussetzungen und Rollen für die Ankündigungs Konfiguration'
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
ms.openlocfilehash: 46b5dac5c800f2e11829940445f9ebfe28c1a95c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531692"
---
# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a><span data-ttu-id="0b4c3-102">Voraussetzungen und Rollen für die Ankündigungs Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b4c3-102">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b4c3-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="0b4c3-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="0b4c3-104">Announcement ist eine Enterprise-VoIP-anrufverwaltungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-104">Announcement is an Enterprise Voice call management feature.</span></span> <span data-ttu-id="0b4c3-105">In diesem Thema wird beschrieben, was Sie benötigen, bevor Sie die Ankündigung und die Rollenzuweisungen konfigurieren können, die Sie zum Ausführen von Konfigurationsaufgaben benötigen.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-105">This topic describes what you need to have in place before you can configure Announcement and the role assignments that you need to perform configuration tasks.</span></span>

<span data-ttu-id="0b4c3-106">In diesem Abschnitt wird davon ausgegangen, dass Sie die Planungsdokumentation zur Ankündigung gelesen haben (siehe [Planung der anrufverwaltungsfunktionen in lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span><span class="sxs-lookup"><span data-stu-id="0b4c3-106">This section assumes that you have read the planning documentation related to Announcement (see [Planning for call management features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)).</span></span>

<div>

## <a name="announcement-configuration-prerequisites"></a><span data-ttu-id="0b4c3-107">Konfigurationsvoraussetzungen für Ansagen</span><span class="sxs-lookup"><span data-stu-id="0b4c3-107">Announcement Configuration Prerequisites</span></span>

<span data-ttu-id="0b4c3-108">Die Ankündigungsanwendung erfordert die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="0b4c3-108">The Announcement application requires the following components:</span></span>

  - <span data-ttu-id="0b4c3-109">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="0b4c3-109">Application service</span></span>

  - <span data-ttu-id="0b4c3-110">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="0b4c3-110">Response Group application</span></span>

  - <span data-ttu-id="0b4c3-111">Dateispeicher für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="0b4c3-111">File Store, to hold audio files</span></span>

<span data-ttu-id="0b4c3-112">All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-112">All of these components are installed by default when you deploy Enterprise Voice.</span></span>

</div>

<div>

## <a name="announcement-configuration-roles"></a><span data-ttu-id="0b4c3-113">Rollen für die Konfiguration von Ansagen</span><span class="sxs-lookup"><span data-stu-id="0b4c3-113">Announcement Configuration Roles</span></span>

<span data-ttu-id="0b4c3-114">Sie können Ansagen mithilfe der folgenden Verwaltungstools konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0b4c3-114">You can use the following administrative tools to configure announcements:</span></span>

  - <span data-ttu-id="0b4c3-115">Lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="0b4c3-115">Lync Server Control Panel</span></span>

  - <span data-ttu-id="0b4c3-116">Lync Server-Verwaltungsshell</span><span class="sxs-lookup"><span data-stu-id="0b4c3-116">Lync Server Management Shell</span></span>

<span data-ttu-id="0b4c3-117">Für das Konfigurieren von Ankündigungsanwendung ist eine der folgenden Administratorrollen erforderlich:</span><span class="sxs-lookup"><span data-stu-id="0b4c3-117">Configuring Announcement application requires one of the following administrative roles:</span></span>

  - <span data-ttu-id="0b4c3-118">**CsVoiceAdministrator**     Diese Administratorrolle kann alle VoIP-bezogenen Einstellungen und Richtlinien einschließlich Ankündigungseinstellungen erstellen, konfigurieren und verwalten.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-118">**CsVoiceAdministrator**   This administrator role can create, configure, and manage all voice-related settings and policies, including Announcement settings.</span></span>

  - <span data-ttu-id="0b4c3-119">**CsServerAdministrator**     Diese Administratorrolle kann Server und Dienste verwalten, überwachen und Problembehandlung durchführen und alle Ankündigungseinstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-119">**CsServerAdministrator**   This administrator role can manage, monitor, and troubleshoot servers and services, and configure all Announcement settings.</span></span>

  - <span data-ttu-id="0b4c3-120">**CsAdministrator**     Diese Administratorrolle kann alle administrativen Aufgaben ausführen und alle Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-120">**CsAdministrator**   This administrator role can perform all administrative tasks and modify all settings.</span></span>

  - <span data-ttu-id="0b4c3-121">**CsViewOnlyAdministrator**     Diese Administratorrolle kann die Bereitstellung anzeigen, um den Bereitstellungsstatus zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-121">**CsViewOnlyAdministrator**   This administrator role can view the deployment to monitor deployment health.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0b4c3-122">Ausführliche Informationen zu Administrator Benutzerrechten finden Sie unter <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for Role-Based Access Control in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="0b4c3-122">For details about administrative user rights, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0b4c3-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b4c3-123">See Also</span></span>


[<span data-ttu-id="0b4c3-124">Bereitstellen von Enterprise-VoIP in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b4c3-124">Deploying Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-deploying-enterprise-voice.md)  


[<span data-ttu-id="0b4c3-125">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b4c3-125">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

