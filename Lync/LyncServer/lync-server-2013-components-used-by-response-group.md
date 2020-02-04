---
title: 'Lync Server 2013: Von Reaktionsgruppen verwendete Komponenten'
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
ms.openlocfilehash: 81275ca027971d661d3323fbfc175c51d4f4d7d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-response-group-in-lync-server-2013"></a><span data-ttu-id="1a987-102">Von Reaktionsgruppen verwendete Komponenten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a987-102">Components used by Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a987-103">_**Letztes Änderungsdatum des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="1a987-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="1a987-104">Die reaktionsgruppenanwendung wird automatisch aktiviert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a987-104">The Response Group application is automatically enabled when you deploy Enterprise Voice.</span></span> <span data-ttu-id="1a987-105">In diesem Abschnitt werden die Komponenten beschrieben, die die reaktionsgruppenanwendung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1a987-105">This section describes the components that support the Response Group application.</span></span>

<div>

## <a name="response-group-components"></a><span data-ttu-id="1a987-106">Komponenten der Reaktionsgruppe</span><span class="sxs-lookup"><span data-stu-id="1a987-106">Response Group Components</span></span>

<span data-ttu-id="1a987-107">Die folgenden Microsoft lync Server 2013-Komponenten unterstützen die reaktionsgruppenanwendung:</span><span class="sxs-lookup"><span data-stu-id="1a987-107">The following Microsoft Lync Server 2013 components support the Response Group application:</span></span>

  - <span data-ttu-id="1a987-108">**Application Service**   Application Service bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen, beispielsweise der Reaktionsgruppe.</span><span class="sxs-lookup"><span data-stu-id="1a987-108">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as Response Group.</span></span> <span data-ttu-id="1a987-109">Der Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="1a987-109">The Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="1a987-110">**Reaktionsgruppenanwendung**   die Antwortgruppen Anwendung ist eine der Unified Communications-Anwendungen, die vom Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="1a987-110">**Response Group application**   The Response Group application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="1a987-111">Sie wird automatisch einbezogen, wenn Sie die Reaktionsgruppe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a987-111">It is included automatically when you deploy Response Group.</span></span> <span data-ttu-id="1a987-112">Die Antwortgruppen Anwendung leitet eingehende Anrufe an Gruppen von Agents weiter und Warteschlangen.</span><span class="sxs-lookup"><span data-stu-id="1a987-112">The Response Group application routes and queues incoming calls to groups of agents.</span></span>

  - <span data-ttu-id="1a987-113">**Sprachpaket**   ein Sprachpaket ist erforderlich, um Text-zu-Sprache-und Spracherkennung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1a987-113">**Language pack**   A language pack is required to support text-to-speech and speech recognition.</span></span> <span data-ttu-id="1a987-114">Diese Sprachtechnologien werden zum Konfigurieren von Nachrichten verwendet, beispielsweise für die Willkommensnachricht oder für andere Ansagen sowie für Fragen und Antworten der interaktiven Sprachantwort (Interactive Voice Response, IVR).</span><span class="sxs-lookup"><span data-stu-id="1a987-114">These speech technologies are used when you configure messages, such as the welcome message and other prompts, and interactive voice response (IVR) questions and answers.</span></span> <span data-ttu-id="1a987-115">Standardmäßig werden die 26 unterstützten Sprachpakete installiert, wenn Sie lync Server 2013 bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a987-115">By default, the 26 supported language packs are installed when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="1a987-116">**Audiodateien**Audiodateien werden für Nachrichten und Musik im Wartebereich verwendet.   </span><span class="sxs-lookup"><span data-stu-id="1a987-116">**Audio files**   Audio files are used for messages and on-hold music.</span></span>

  - <span data-ttu-id="1a987-117">**Datei**   Speicher-Reaktionsgruppe verwendet den Dateispeicher zum Speichern von Audiodateien.</span><span class="sxs-lookup"><span data-stu-id="1a987-117">**File Store**   Response Group uses File store to store audio files.</span></span> <span data-ttu-id="1a987-118">Mehrere Antwortgruppen Pools können dieselbe Instanz des Dateispeichers verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a987-118">Multiple Response Group pools can use the same instance of File store.</span></span>

  - <span data-ttu-id="1a987-119">**Reaktionsgruppen-Konfigurationstool**   das Reaktionsgruppen-Konfigurationstool ist ein webbasiertes Tool, das zum Erstellen und Konfigurieren von Reaktionsgruppen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1a987-119">**Response Group Configuration Tool**   The Response Group Configuration Tool is a web-based tool that is used to create and configure response groups.</span></span> <span data-ttu-id="1a987-120">Beim Installieren von Webdiensten ist das Tool für die Reaktionsgruppen Konfiguration enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a987-120">The Response Group Configuration Tool is included when you install Web Services.</span></span>

  - <span data-ttu-id="1a987-121">**Microsoft lync Server 2013-System**   Steuerung Sie können die lync Server-Systemsteuerung verwenden, um Agentengruppen und-Warteschlangen für Reaktionsgruppen einzurichten und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1a987-121">**Microsoft Lync Server 2013 Control Panel**   You can use Lync Server Control Panel to setup and configure agent groups and queues for response groups.</span></span>

  - <span data-ttu-id="1a987-122">**Lync Server-Verwaltungsshell**   alle Einstellungen der Reaktionsgruppe können mithilfe der lync Server-Verwaltungsshell-Cmdlets konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="1a987-122">**Lync Server Management Shell**   All Response Group settings can be configured by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="1a987-123">\*\*\*\*   Formelle Agents für Microsoft lync 2013 (Agents, die sich bei der Gruppe anmelden müssen, bevor Sie Anrufe für die Gruppe annehmen können) verwenden Sie lync 2013, um sich bei der Gruppe anzumelden und sich abzumelden.</span><span class="sxs-lookup"><span data-stu-id="1a987-123">**Microsoft Lync 2013**   Formal agents (agents who are required to sign in to the group before they can accept calls for the group) use Lync 2013 to sign in to and sign out from the group.</span></span> <span data-ttu-id="1a987-124">Wenn eine Agentengruppe für formelle Agents konfiguriert ist, klicken die Agents auf ein Menüelement in lync 2013, um Internet Explorer zu öffnen und eine Webseite-Konsole für die Anmeldung bei der Gruppe anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1a987-124">If an agent group is configured for formal agents, the agents click a menu item in Lync 2013 to open Internet Explorer and display a webpage console for signing in and out of the group.</span></span>

  - <span data-ttu-id="1a987-125">**Web**Services-Webdienste sind für das Reaktionsgruppen-Konfigurations Tool, die Anmelde-und Abmelde Konsole des Agents, die lync Server-Systemsteuerung und den Client-Webdienst der Reaktionsgruppe erforderlich.   </span><span class="sxs-lookup"><span data-stu-id="1a987-125">**Web Services**   Web Services is required for Response Group Configuration Tool, the agents’ sign-in and sign-out console, Lync Server Control Panel, and Response Group client web service.</span></span>

  - <span data-ttu-id="1a987-126">**Antwortgruppen-Client-Web-Service**   Response Group-Anwendung bietet einen Client-Webdienst, der von Drittanbieter-Anwendungen verwendet werden kann, um Informationen zu Agents, Agentengruppen Mitgliedschaft, Agent-Anmeldestatus, Anrufstatus für Gruppen und die Gruppen abzurufen, die anonyme Anrufe unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1a987-126">**Response Group Client Web Service**   Response Group application provides a client web service, which can be used by third-party applications to retrieve information about agents, agent group membership, agent sign-in status, call status for groups, and the groups that support anonymous calls.</span></span> <span data-ttu-id="1a987-127">Lync 2013 und lync 2010 Attendant verwenden den Client-Webdienst der Reaktionsgruppe, um die Liste der Antwortgruppen abzurufen, die von Agents für anonyme Anrufe verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1a987-127">Lync 2013 and Lync 2010 Attendant use Response Group Client Web service to retrieve the list of response groups that agents can use to make anonymous calls.</span></span> <span data-ttu-id="1a987-128">Der Client-Webdienst ist bei der Installation von Webdiensten enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a987-128">The client web service is included when you install Web Services.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

