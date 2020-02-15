---
title: 'Lync Server 2013: von der Ankündigungsanwendung verwendete Komponenten'
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
ms.openlocfilehash: a888ca21e26a21103d1c45e74518c3d224d18a7b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="c3fcf-102">Von der Ankündigungsanwendung in lync Server 2013 verwendete Komponenten</span><span class="sxs-lookup"><span data-stu-id="c3fcf-102">Components used by the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3fcf-103">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="c3fcf-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="c3fcf-104">In lync Server 2013 ist der Ankündigungsanwendung eine Komponente der Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-104">In Lync Server 2013, the Announcement application is a component of the Response Group application.</span></span> <span data-ttu-id="c3fcf-105">Wenn Sie Enterprise-VoIP bereitstellen, wird der Ankündigungsanwendung automatisch zusammen mit dem Reaktionsgruppenanwendung installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-105">When you deploy Enterprise Voice, the Announcement application is automatically installed and activated along with the Response Group application.</span></span> <span data-ttu-id="c3fcf-106">In diesem Abschnitt werden die Komponenten beschrieben, die den Ankündigungsanwendung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-106">This section describes the components that support the Announcement application.</span></span>

<div>

## <a name="announcement-application-components"></a><span data-ttu-id="c3fcf-107">Komponenten der Ankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="c3fcf-107">Announcement Application Components</span></span>

<span data-ttu-id="c3fcf-108">Die folgenden lync Server Komponenten unterstützen das Ankündigungsanwendung:</span><span class="sxs-lookup"><span data-stu-id="c3fcf-108">The following Lync Server components support the Announcement application:</span></span>

  - <span data-ttu-id="c3fcf-109">**Anwendungsdienst**   Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications.</span></span> <span data-ttu-id="c3fcf-110">Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-110">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="c3fcf-111">**Reaktionsgruppenanwendung**   das Reaktionsgruppenanwendung ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="c3fcf-112">Wenn ein nicht zugewiesener Telefonnummern Bereich für die Weiterleitung an eine Ansage konfiguriert ist, muss der Reaktionsgruppenanwendung die Anrufe an die Telefonnummer weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-112">When an unassigned phone number range is configured to route to an announcement, the Response Group application is required to route the calls made to the phone number.</span></span> <span data-ttu-id="c3fcf-113">(Reaktionsgruppenanwendung ist nicht erforderlich, wenn alle Bereiche für die Weiterleitung an Exchange Unified Messaging (um) konfiguriert sind.)</span><span class="sxs-lookup"><span data-stu-id="c3fcf-113">(Response Group application is not required if all the ranges are configured to route to Exchange Unified Messaging (UM).)</span></span>

  - <span data-ttu-id="c3fcf-114">**Audiodateien**   -Audiodateien werden für die Ankündigungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-114">**Audio files**   Audio files are used for the announcements.</span></span>

  - <span data-ttu-id="c3fcf-115">**Dateispeicher**   der Ankündigungsanwendung verwendet Dateispeicher, um seine Audiodateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-115">**File Store**   The Announcement application uses File Store to store its audio files.</span></span>

  - <span data-ttu-id="c3fcf-116">**Lync Server-Systemsteuerung**   Sie lync Server-Systemsteuerung verwenden können, um die Tabelle nicht zugewiesener Nummern zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-116">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the unassigned number table.</span></span>

  - <span data-ttu-id="c3fcf-117">**Lync Server-Verwaltungsshell**   Sie können lync Server-Verwaltungsshell-Cmdlets zum Konfigurieren von Ankündigungseinstellungen und der Tabelle nicht zugewiesener Nummern verwenden.</span><span class="sxs-lookup"><span data-stu-id="c3fcf-117">**Lync Server Management Shell**   You can use Lync Server Management Shell cmdlets to configure Announcement settings and the unassigned number table.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

