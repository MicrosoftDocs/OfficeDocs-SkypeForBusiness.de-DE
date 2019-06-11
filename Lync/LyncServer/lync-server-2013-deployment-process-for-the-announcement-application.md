---
title: 'Lync Server 2013: Bereitstellungsprozess für die Ankündigungs Anwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for the Announcement application
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398545(v=OCS.15)
ms:contentKeyID: 48184500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2b1e9f8dd78b299a8e89e958f5b1c03acdffb7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="93194-102">Bereitstellungsprozess für die Ankündigungs Anwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="93194-102">Deployment process for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93194-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="93194-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="93194-104">Dieser Abschnitt enthält eine Übersicht über die Schritte, die beim Bereitstellen der Ankündigungs Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="93194-104">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="93194-105">Sie müssen Enterprise-VoIP bereitstellen, bevor Sie Ankündigungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="93194-105">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="93194-106">Die von der Ankündigungs Anwendung benötigten Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.</span><span class="sxs-lookup"><span data-stu-id="93194-106">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="announcement-deployment-process"></a><span data-ttu-id="93194-107">Bereitstellungsprozess für Ansagen</span><span class="sxs-lookup"><span data-stu-id="93194-107">Announcement Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="93194-108">Phase</span><span class="sxs-lookup"><span data-stu-id="93194-108">Phase</span></span></th>
<th><span data-ttu-id="93194-109">Schritte</span><span class="sxs-lookup"><span data-stu-id="93194-109">Steps</span></span></th>
<th><span data-ttu-id="93194-110">Rollen</span><span class="sxs-lookup"><span data-stu-id="93194-110">Roles</span></span></th>
<th><span data-ttu-id="93194-111">Bereitstellungsdokumentation</span><span class="sxs-lookup"><span data-stu-id="93194-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="93194-112">Konfigurieren von Ansageeinstellungen</span><span class="sxs-lookup"><span data-stu-id="93194-112">Configure Announcement settings</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="93194-113">Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS)</span><span class="sxs-lookup"><span data-stu-id="93194-113">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span></p></li>
<li><p><span data-ttu-id="93194-114">Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu.</span><span class="sxs-lookup"><span data-stu-id="93194-114">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="93194-115">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="93194-115">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="93194-116">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="93194-116">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="93194-117">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="93194-117">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="93194-118">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="93194-118">CsAdministrator</span></span></p>
<p><span data-ttu-id="93194-119">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="93194-119">CsViewOnlyAdministrator</span></span></p></td>
<td><p><span data-ttu-id="93194-120"><a href="lync-server-2013-create-an-announcement.md">Erstellen einer Ankündigung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93194-120"><a href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="93194-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93194-121"><a href="lync-server-2013-configure-the-unassigned-number-table.md">Configure the unassigned number table in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="93194-122">Überprüfen Ihrer Bereitstellung von Ansagen</span><span class="sxs-lookup"><span data-stu-id="93194-122">Verify your Announcement deployment</span></span></p></td>
<td><p><span data-ttu-id="93194-123">Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.</span><span class="sxs-lookup"><span data-stu-id="93194-123">Test by listening to announcements to verify that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="93194-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">Optional Überprüfen der Ankündigungs Bereitstellung in lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="93194-124"><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Verify Announcement deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

