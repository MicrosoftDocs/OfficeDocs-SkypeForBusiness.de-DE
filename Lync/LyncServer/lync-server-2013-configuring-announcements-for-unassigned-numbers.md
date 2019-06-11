---
title: 'Lync Server 2013: Konfigurieren von Ansagen für nicht zugewiesene Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring announcements for unassigned numbers
ms:assetid: 45633dd3-78de-4934-867e-33969fc25368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425944(v=OCS.15)
ms:contentKeyID: 48184035
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8375e3481703078013d85060d20d0e9f500374b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-announcements-for-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="45075-102">Konfigurieren von Ansagen für nicht zugewiesene Nummern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-102">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45075-103">_**Letztes Änderungsdatum des Themas:** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="45075-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="45075-104">Bei der Ankündigungs Anwendung handelt es sich um ein Enterprise-VoIP-Feature, mit dem Sie konfigurieren können, was mit Anrufen zu nicht zugewiesenen Erweiterungen geschieht (Erweiterungen, die für Ihre Organisation gültig sind, aber keiner Person oder einem Telefon zugeordnet sind).</span><span class="sxs-lookup"><span data-stu-id="45075-104">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="45075-105">So können Sie beispielsweise Anrufe an nicht zugewiesene Nummern konfigurieren, um eine Nachricht wiederzugeben oder an ein anderes Ziel oder beides übertragen zu werden.</span><span class="sxs-lookup"><span data-stu-id="45075-105">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>

<span data-ttu-id="45075-106">Die Ankündigungs Anwendung wird auf dem Front-End-Server oder Standard Edition-Server als Feature der reaktionsgruppenanwendung installiert, wenn Sie Enterprise-VoIP bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="45075-106">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="45075-107">Sie müssen Ansagen konfigurieren, indem Sie Audiodateien hochladen oder die Text-zu-Sprache-Funktion und die Tabelle nicht zugewiesener Nummern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="45075-107">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>

<span data-ttu-id="45075-108">Dieser Abschnitt führt Sie durch die Konfiguration von lync Server-Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="45075-108">This section guides you through the configuration of Lync Server Announcements.</span></span> <span data-ttu-id="45075-109">Es wird davon ausgegangen, dass Sie die Planungsabschnitte in Bezug auf Ankündigungen bereits gelesen und einen Enterprise Edition-Server oder einen Standard Edition-Server mit Enterprise-VoIP bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="45075-109">It assumes that you have already read the planning sections related to Announcements and deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="45075-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="45075-110">In This Section</span></span>

  - [<span data-ttu-id="45075-111">Konfigurationsvoraussetzungen und -rollen für Ansagen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-111">Announcement configuration prerequisites and roles in Lync Server 2013</span></span>](lync-server-2013-announcement-configuration-prerequisites-and-roles.md)

  - [<span data-ttu-id="45075-112">Bereitstellungsprozess für die Ankündigungs Anwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-112">Deployment process for the Announcement application in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-the-announcement-application.md)

  - [<span data-ttu-id="45075-113">Erstellen einer Ankündigung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-113">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="45075-114">Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-114">Configure the unassigned number table in Lync Server 2013</span></span>](lync-server-2013-configure-the-unassigned-number-table.md)

  - [<span data-ttu-id="45075-115">Optional Überprüfen der Ankündigungs Bereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-115">(Optional) Verify Announcement deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-announcement-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="45075-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45075-116">See Also</span></span>


[<span data-ttu-id="45075-117">Planen der Anruf Verwaltungsfeatures in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="45075-117">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

