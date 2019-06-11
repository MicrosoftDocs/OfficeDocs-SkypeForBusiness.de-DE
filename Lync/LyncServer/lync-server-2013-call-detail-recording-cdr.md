---
title: 'Lync Server 2013: Anrufdetailaufzeichnung (CDR)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a15053ee79a246889f1802e5b7801e548574c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="e74c9-102">Anrufdetailaufzeichnung (CDR) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-102">Call detail recording (CDR) in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e74c9-103">_**Letztes Änderungsdatum des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e74c9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e74c9-104">Bei der KDS (Aufzeichnung von Kommunikationsdatensätzen) werden Nutzungs- und Diagnoseinformationen über Peer-to-Peer-Aktivitäten wie Chats, VoIP-Anrufe, Anwendungsfreigaben, Dateiübertragungen und Besprechungen aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e74c9-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="e74c9-105">Anhand der Nutzungsdaten kann die Rendite berechnet werden und die Diagnosedaten können zur Problembehandlung bei Peer-to-Peer-Aktivitäten und Besprechungen genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="e74c9-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="e74c9-106">Wenn Sie lync Server 2013 installieren, können Sie auch eine vordefinierte Sammlung globaler Konfigurationseinstellungen für CdR installieren.</span><span class="sxs-lookup"><span data-stu-id="e74c9-106">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="e74c9-107">In den Themen in diesem Abschnitt wird beschrieben, wie KDS konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="e74c9-107">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e74c9-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e74c9-108">In This Section</span></span>

  - [<span data-ttu-id="e74c9-109">Anzeigen der CDR-Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-109">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="e74c9-110">Aktivieren der Anrufdetailaufzeichnung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-110">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="e74c9-111">Erstellen oder Ändern einer Sammlung von CDR-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-111">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="e74c9-112">Löschen einer vorhandenen Sammlung von CDR-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-112">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="e74c9-113">Manuelles Bereinigen der Datenbanken für die Anrufdetailaufzeichnung und die Qualität von Erfahrungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-113">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e74c9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e74c9-114">See Also</span></span>


[<span data-ttu-id="e74c9-115">Konfigurieren der Einstellungen für die Anrufdetailaufzeichnung und die Qualität der Benutzerfreundlichkeit in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e74c9-115">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

