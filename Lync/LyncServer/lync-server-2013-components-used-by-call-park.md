---
title: 'Lync Server 2013: Komponenten für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components used by Call Park
ms:assetid: c7ffbee3-0ce1-48c0-bb56-af098b41d6d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398824(v=OCS.15)
ms:contentKeyID: 48185374
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64f74161230504ee3f24ed19780e0a62ad4e7d08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-used-by-call-park-in-lync-server-2013"></a><span data-ttu-id="961a2-102">Komponenten für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="961a2-102">Components used by Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="961a2-103">_**Letztes Änderungsdatum des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="961a2-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<span data-ttu-id="961a2-104">Die Anwendung Parken wird automatisch installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="961a2-104">The Call Park application is automatically installed when you deploy Enterprise Voice.</span></span> <span data-ttu-id="961a2-105">Sie aktivieren den Anruf Park durch Konfigurieren der VoIP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="961a2-105">You enable Call Park by configuring voice policy.</span></span> <span data-ttu-id="961a2-106">Die folgenden lync Server 2013-Komponenten unterstützen die Anwendung für den Parken von anrufen:</span><span class="sxs-lookup"><span data-stu-id="961a2-106">The following Lync Server 2013 components support the Call Park application:</span></span>

  - <span data-ttu-id="961a2-107">**Application Service**   Application Service stellt eine Plattform zum Bereitstellen, hosten und Verwalten von Unified Communications-Anwendungen bereit, beispielsweise die Anwendung für den Parken von anrufen.</span><span class="sxs-lookup"><span data-stu-id="961a2-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="961a2-108">Der Anwendungsdienst wird auf jedem Front-End-Server in einem Front-End-Pool und auf jedem Standard Edition-Server automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="961a2-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="961a2-109">**Anwendung für den Park anrufen**   die Anwendung "Parken" ist eine der Unified Communications-Anwendungen, die vom Anwendungsdienst gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="961a2-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="961a2-110">Sie wird automatisch bei der Bereitstellung von Enterprise-VoIP integriert.</span><span class="sxs-lookup"><span data-stu-id="961a2-110">It is included automatically when you deploy Enterprise Voice.</span></span> <span data-ttu-id="961a2-111">Rufen Sie Parkplätze an, ruft Anrufe ab und verwaltet die Orbits des Anruf Parks.</span><span class="sxs-lookup"><span data-stu-id="961a2-111">Call Park parks and retrieves calls and manages call park orbits.</span></span>

  - <span data-ttu-id="961a2-112">**Music-on-halte-Datei**   wenn Musik aktiviert ist, wird die Musikdatei wiedergegeben, während ein Anruf abgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="961a2-112">**Music-on hold-file**   If music in enabled, the music file is played while a call is parked.</span></span> <span data-ttu-id="961a2-113">Eine Standard-Musikdatei ist enthalten, wenn die Anwendung für den Parken von Anrufen installiert ist.</span><span class="sxs-lookup"><span data-stu-id="961a2-113">A default music file is included when the Call Park application is installed.</span></span>

  - <span data-ttu-id="961a2-114">**Dateispeicher**   die Anwendung des Anruf Parks verwendet den Dateispeicher, um benutzerdefinierte Audiodateien zu speichern.</span><span class="sxs-lookup"><span data-stu-id="961a2-114">**File Store**   The Call Park application uses File Store to hold custom audio files.</span></span>

  - <span data-ttu-id="961a2-115">**Lync Server-System**   Steuerung Sie können die lync Server-Systemsteuerung verwenden, um die Orbit-Tabelle des Anruf Parks zu konfigurieren und den Anruf Park für Benutzer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="961a2-115">**Lync Server Control Panel**   You can use Lync Server Control Panel to configure the call park orbit table and to enable Call Park for users.</span></span>

  - <span data-ttu-id="961a2-116">**Lync Server-Verwaltungsshell**   alle Einstellungen für die Anruf Park Anwendung können mithilfe der lync Server-Verwaltungsshell-Cmdlets ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="961a2-116">**Lync Server Management Shell**   All Call Park application configuration can be performed by using Lync Server Management Shell cmdlets.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

