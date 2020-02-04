---
title: 'Lync Server 2013: Von der Ankündigungsanwendung verwendete Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by the Announcement application
ms:assetid: 7b1a0281-cf31-459d-a734-5f10a129089c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398608(v=OCS.15)
ms:contentKeyID: 48184595
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52ef0b1da665f8797f29582e9ce9e1d311287d61
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="32bd8-102">Von der Ankündigungsanwendung in Lync Server 2013 verwendete Komponenten</span><span class="sxs-lookup"><span data-stu-id="32bd8-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32bd8-103">_**Letztes Änderungsdatum des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="32bd8-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="32bd8-104">In lync Server 2013 ist die Ankündigungs Anwendung eine Komponente der reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="32bd8-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="32bd8-105">Wenn Sie Enterprise-VoIP bereitstellen, wird die Ankündigungs Anwendung zusammen mit der reaktionsgruppenanwendung automatisch installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="32bd8-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="32bd8-106">In diesem Abschnitt werden die Komponenten beschrieben, die die Ankündigungs Anwendung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="32bd8-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="32bd8-107">Ankündigungs Anwendungskomponenten</span><span class="sxs-lookup"><span data-stu-id="32bd8-107">Announcement Application Components</span></span>

<span data-ttu-id="32bd8-108">Die folgenden lync Server-Komponenten unterstützen die Ankündigungs Anwendung:</span><span class="sxs-lookup"><span data-stu-id="32bd8-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="32bd8-109">**Application Service**   Application Service bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="32bd8-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="32bd8-110">Der Anwendungsdienst wird auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="32bd8-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="32bd8-111">**Reaktionsgruppenanwendung**   die Antwortgruppen Anwendung ist eine der Unified Communications-Anwendungen, die vom Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="32bd8-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="32bd8-112">Wenn ein nicht zugewiesener Telefonnummern Bereich so konfiguriert ist, dass er zu einer Ankündigung weitergeleitet wird, ist die reaktionsgruppenanwendung erforderlich, um die an die Telefonnummer vorgenommenen Anrufe weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="32bd8-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="32bd8-113">(Antwortgruppen Anwendung ist nicht erforderlich, wenn alle Bereiche für die Weiterleitung an Exchange Unified Messaging (um) konfiguriert sind.)</span><span class="sxs-lookup"><span data-stu-id="32bd8-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="32bd8-114">**Audiodateien**   -Audiodateien werden für Ankündigungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="32bd8-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="32bd8-115">**Dateispeicher**   die Ankündigungs Anwendung verwendet den Dateispeicher zum Speichern der Audiodateien.</span><span class="sxs-lookup"><span data-stu-id="32bd8-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="32bd8-116">**Lync Server Control Panel**   Sie können die lync Server Control Panel verwenden, um die Tabelle nicht zugewiesene Nummern zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="32bd8-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="32bd8-117">**Lync Server-Verwaltungsshell**   Sie können Cmdlets der lync Server-Verwaltungsshell verwenden, um Ankündigungseinstellungen und die Tabelle "nicht zugewiesene Nummern" zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="32bd8-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

