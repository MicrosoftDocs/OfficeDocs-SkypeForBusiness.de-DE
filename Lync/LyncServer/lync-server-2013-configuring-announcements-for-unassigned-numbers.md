---
title: 'Lync Server 2013: Konfigurieren von Ankündigungen für nicht zugewiesene Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c352e7a4f062e6a9a1aab0bf52289c20102cc7fe
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517552"
---
# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="e2936-102">Konfigurieren von Ankündigungen für nicht zugewiesene Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2936-103">_**Letztes Änderungsstand des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="e2936-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="e2936-104">Bei der Ankündigungsanwendung handelt es sich um eine Enterprise-VoIP-Funktion, mit der Sie konfigurieren können, was mit Aufrufen von nicht zugewiesenen Erweiterungen geschieht (Erweiterungen, die für Ihre Organisation gültig sind, aber keiner Person oder einem Telefon zugewiesen sind).</span><span class="sxs-lookup"><span data-stu-id="e2936-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="e2936-105">Beispielsweise können Sie Anrufe für nicht zugewiesene Nummern so konfigurieren, dass eine Nachricht wiedergegeben oder an ein anderes Ziel oder beides übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="e2936-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="e2936-106">Das Ankündigungsanwendung wird als ein Feature von Reaktionsgruppenanwendung auf der Front-End-Server oder Standard Edition-Server installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e2936-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="e2936-107">Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion konfigurieren und die Tabelle nicht zugewiesener Nummern definieren.</span><span class="sxs-lookup"><span data-stu-id="e2936-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="e2936-108">Dieser Abschnitt führt Sie durch die Konfiguration von lync Server Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="e2936-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="e2936-109">Es wird davon ausgegangen, dass Sie bereits die Planungsabschnitte im Zusammenhang mit Ankündigungen gelesen und eine Enterprise Edition-Server oder ein Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="e2936-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2936-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e2936-110">In This Section</span></span>

  - [<span data-ttu-id="e2936-111">Voraussetzungen und Rollen für die Ankündigungs Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="e2936-112">Bereitstellungsprozess für die Ankündigungsanwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="e2936-113">Erstellen einer Ansage in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="e2936-114">Konfigurieren der Tabelle nicht zugewiesener Nummern in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="e2936-115">Optional Überprüfen der Ankündigungs Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e2936-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2936-116">See Also</span></span>


[<span data-ttu-id="e2936-117">Planen von Funktionen für die Anrufverwaltung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2936-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

