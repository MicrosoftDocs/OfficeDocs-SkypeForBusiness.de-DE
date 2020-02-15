---
title: 'Lync Server 2013: vom Parken von Anrufen verwendete Komponenten'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a0b6d6bece5fa107e0fe130aab983458acbc0a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="68394-102">Für das Parken von Anrufen in lync Server 2013 verwendete Komponenten</span><span class="sxs-lookup"><span data-stu-id="68394-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68394-103">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="68394-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="68394-104">Das Anwendung zum Parken von Anrufen wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="68394-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="68394-105">Sie können das Parken von Anrufen durch Konfigurieren der VoIP-Richtlinie aktivieren.</span><span class="sxs-lookup"><span data-stu-id="68394-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="68394-106">Die folgenden lync Server 2013 Komponenten unterstützen das Anwendung zum Parken von anrufen:</span><span class="sxs-lookup"><span data-stu-id="68394-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="68394-107">**Anwendungsdienst**   Anwendungsdienst bietet eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen wie der Anwendung zum Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="68394-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="68394-108">Anwendungsdienst wird automatisch auf jedem Front-End-Server in einem Front-End-Pool und auf jeder Standard Edition-Server installiert.</span><span class="sxs-lookup"><span data-stu-id="68394-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="68394-109">**Anwendung zum Parken von Anrufen**   das Anwendung zum Parken von anrufen ist eine der Unified Communications-Anwendungen, die von Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="68394-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="68394-110">Sie wird automatisch bei der Bereitstellung von Enterprise-VoIP einbezogen.</span><span class="sxs-lookup"><span data-stu-id="68394-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="68394-111">Parken von Parks anrufen und Anrufe abrufen und Orbits für das Parken von Anrufen verwalten.</span><span class="sxs-lookup"><span data-stu-id="68394-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="68394-112">**Music-on Hold-Datei**   wenn Music in enabled ist, wird die Musikdatei wiedergegeben, während ein Anruf geparkt wird.</span><span class="sxs-lookup"><span data-stu-id="68394-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="68394-113">Wenn die Anwendung zum Parken von Anrufen installiert ist, wird eine standardmäßige Musikdatei hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="68394-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="68394-114">**Dateispeicher**   der Anwendung zum Parken von Anrufen verwendet Dateispeicher, um benutzerdefinierte Audiodateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="68394-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="68394-115">**Lync Server-Systemsteuerung**   Sie können lync Server-Systemsteuerung verwenden, um die Orbit-Tabelle für das Parken von Anrufen zu konfigurieren und die Funktion zum Parken von Anrufen für Benutzer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="68394-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="68394-116">**Lync Server-Verwaltungsshell**   alle Anwendung zum Parken von Anrufen Konfiguration können mithilfe von lync Server-Verwaltungsshell-Cmdlets ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68394-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

