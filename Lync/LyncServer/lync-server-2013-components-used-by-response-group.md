---
title: 'Lync Server 2013: von der Reaktionsgruppe verwendete Komponenten'
description: 'Lync Server 2013: von der Reaktionsgruppe verwendete Komponenten.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Response Group
ms:assetid: 2b058785-47ca-43b7-b3de-6928a60dc685
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425768(v=OCS.15)
ms:contentKeyID: 48183693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a1e916d9e4bf986bf0337a6f1f1dd918ff2772e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571701"
---
# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="1b79e-103">Von der Reaktionsgruppe in lync Server 2013 verwendete Komponenten</span><span class="sxs-lookup"><span data-stu-id="1b79e-103">Components used by Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b79e-104">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1b79e-104">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1b79e-105">Das Reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1b79e-105">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="1b79e-106">In diesem Abschnitt werden die Komponenten beschrieben, die den Reaktionsgruppenanwendung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1b79e-106">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="1b79e-107">Reaktionsgruppenkomponenten</span><span class="sxs-lookup"><span data-stu-id="1b79e-107">Response Group Components</span></span>

<span data-ttu-id="1b79e-108">Die folgenden Microsoft lync Server 2013 Komponenten unterstützen das Reaktionsgruppenanwendung:</span><span class="sxs-lookup"><span data-stu-id="1b79e-108">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="1b79e-109">**Anwendungsdienst**     Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen wie Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1b79e-109">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="1b79e-110">Das Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="1b79e-110">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="1b79e-111">**Reaktionsgruppenanwendung**     Die Reaktionsgruppenanwendung ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1b79e-111">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="1b79e-112">Sie wird automatisch bei der Bereitstellung der Reaktionsgruppe einbezogen.</span><span class="sxs-lookup"><span data-stu-id="1b79e-112">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="1b79e-113">Das Reaktionsgruppenanwendung leitet eingehende Anrufe an Gruppen von Agents weiter und Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="1b79e-113">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="1b79e-114">**Sprachpaket**     Zur Unterstützung von Text-zu-Sprache-und Spracherkennung ist ein Sprachpaket erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b79e-114">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="1b79e-115">Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR).</span><span class="sxs-lookup"><span data-stu-id="1b79e-115">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="1b79e-116">Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1b79e-116">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="1b79e-117">**Audio-Dateien**     Audiodateien werden für Nachrichten und Wartemusik verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b79e-117">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="1b79e-118">**Dateispeicher**     Die Reaktionsgruppe verwendet den Dateispeicher zum Speichern von Audiodateien.</span><span class="sxs-lookup"><span data-stu-id="1b79e-118">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="1b79e-119">Mehrere Reaktionsgruppen Pools können dieselbe Instanz des Dateispeichers verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b79e-119">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="1b79e-120">**Reaktionsgruppen-Konfigurations Tool**     Das Reaktionsgruppen-Konfigurationstool ist ein webbasiertes Tool, das zum Erstellen und Konfigurieren von Reaktionsgruppen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1b79e-120">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="1b79e-121">Das Tool zum Konfigurieren von Reaktionsgruppen ist enthalten, wenn Sie Webdienste installieren.</span><span class="sxs-lookup"><span data-stu-id="1b79e-121">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="1b79e-122">**Microsoft lync Server 2013-System**     Steuerung Sie können lync Server-Systemsteuerung verwenden, um Agentgruppen und Warteschlangen für Reaktionsgruppen einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1b79e-122">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="1b79e-123">**Lync Server-Verwaltungsshell**     Alle Einstellungen der Reaktionsgruppe können mithilfe von lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1b79e-123">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="1b79e-124">**Microsoft lync 2013**     Formelle Agents (Agents, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe für die Gruppe annehmen können) verwenden Sie lync 2013, um sich bei der Gruppe anzumelden und abzumelden.</span><span class="sxs-lookup"><span data-stu-id="1b79e-124">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="1b79e-125">Wenn eine Agentgruppe für formelle Agents konfiguriert ist, klicken die Agents auf ein Menüelement in lync 2013, um Internet Explorer zu öffnen und eine Webseiten Konsole zum ein-und Ausloggen der Gruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b79e-125">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="1b79e-126">**Webdienste**     Webdienste ist für das Konfigurations Tool für Reaktionsgruppen, die Anmelde-und Abmelde Konsole der Agents, lync Server-Systemsteuerung und den Client-Webdienst der Reaktionsgruppe erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1b79e-126">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="1b79e-127">**Client-Webdienst**     für Reaktionsgruppen Reaktionsgruppenanwendung stellt einen Client-Webdienst bereit, der von Drittanbieteranwendungen zum Abrufen von Informationen zu Agents, zur Agent-Gruppenmitgliedschaft, zum Agent-Anmeldestatus, zum Anrufstatus für Gruppen und zu den Gruppen, die anonyme Anrufe unterstützen, verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b79e-127">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="1b79e-128">Lync 2013 und lync 2010 Attendant den Client-Webdienst für Reaktionsgruppen verwenden, um die Liste der Reaktionsgruppen abzurufen, mit denen Agents anonyme Anrufe tätigen können.</span><span class="sxs-lookup"><span data-stu-id="1b79e-128">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="1b79e-129">Der Clientwebdienst ist in der Installation der Webdienste enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b79e-129">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

