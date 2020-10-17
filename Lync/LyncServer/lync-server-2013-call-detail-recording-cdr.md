---
title: 'Lync Server 2013: Aufzeichnung von Gesprächs Details (KDS)'
description: 'Lync Server 2013: Aufzeichnung von Kommunikationsdatensätzen (CDR).'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call detail recording (CDR)
ms:assetid: 67726075-c77c-4191-a64f-a1cf5c7bcbb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688079(v=OCS.15)
ms:contentKeyID: 49733675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590f99fd0b8649ffb3c4df039488dc54a8f3b7b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561791"
---
# <a name="call-detail-recording-cdr-in-lync-server-2013"></a><span data-ttu-id="2f08e-103">Aufzeichnung von Kommunikationsdatensätzen (KDS) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-103">Call detail recording (CDR) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f08e-104">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="2f08e-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="2f08e-105">Bei CDR (Call Detail Recording, Aufzeichnung von Kommunikationsdatensätzen) werden Nutzungs- und Diagnoseinformationen über Peer-zu-Peer-Aktivitäten wie Instant Messaging, VoIP-Anrufe, Anwendungsfreigaben, Dateiübertragungen und Besprechungen aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2f08e-105">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities, including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="2f08e-106">Anhand der Nutzungsdaten kann die Rendite berechnet werden, und die Diagnosedaten können zur Problembehandlung bei Peer-zu-Peer-Aktivitäten und Besprechungen genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="2f08e-106">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span> <span data-ttu-id="2f08e-107">Wenn Sie lync Server 2013 installieren, installieren Sie auch eine vordefinierte Sammlung globaler Konfigurationseinstellungen für KDS.</span><span class="sxs-lookup"><span data-stu-id="2f08e-107">When you install Lync Server 2013, you will also install a predefined collection of global configuration settings for CDR.</span></span> <span data-ttu-id="2f08e-108">In den Themen in diesem Abschnitt wird beschrieben, wie CDR konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="2f08e-108">Use the topics in this section to configure CDR.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2f08e-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2f08e-109">In This Section</span></span>

  - [<span data-ttu-id="2f08e-110">Anzeigen von KDS-Konfigurationsinformationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-110">View CDR configuration information in Lync Server 2013</span></span>](lync-server-2013-view-cdr-configuration-information.md)

  - [<span data-ttu-id="2f08e-111">Aktivieren der Aufzeichnung von Anrufdetails in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-111">Enable call detail recording in Lync Server 2013</span></span>](lync-server-2013-enable-call-detail-recording.md)

  - [<span data-ttu-id="2f08e-112">Erstellen oder Ändern einer Auflistung von KDS-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-112">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="2f08e-113">Löschen einer vorhandenen Auflistung von KDS-Konfigurationseinstellungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-113">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-cdr-configuration-settings.md)

  - [<span data-ttu-id="2f08e-114">Manuelles Löschen der Datenbanken für das Aufzeichnen von Anrufen und der Qualität von Experience in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-114">Manually purging the call detail recording and Quality of Experience databases in Lync Server 2013</span></span>](lync-server-2013-manually-purging-the-call-detail-recording-and-quality-of-experience-databases.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2f08e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f08e-115">See Also</span></span>


[<span data-ttu-id="2f08e-116">Konfigurieren der Einstellungen für die Aufzeichnung von Gesprächsdaten und der erfahrungsqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2f08e-116">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

