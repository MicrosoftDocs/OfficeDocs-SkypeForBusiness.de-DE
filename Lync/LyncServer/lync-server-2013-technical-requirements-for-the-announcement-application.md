---
title: 'Lync Server 2013: technische Anforderungen für die Ankündigungsanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8687c5b9c5f422994817910eec640cc795798d18
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="58650-102">Technische Anforderungen für die Ankündigungsanwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="58650-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58650-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="58650-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="58650-104">In diesem Abschnitt werden die folgenden technischen Anforderungen für die Ankündigungsanwendung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="58650-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="58650-105">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="58650-105">Hardware requirements</span></span>

  - <span data-ttu-id="58650-106">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="58650-106">Software requirements</span></span>

  - <span data-ttu-id="58650-107">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="58650-107">Port requirements</span></span>

  - <span data-ttu-id="58650-108">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="58650-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="58650-109">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="58650-109">Hardware Requirements</span></span>

<span data-ttu-id="58650-110">Die Ankündigungsanwendung hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="58650-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="58650-111">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="58650-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="58650-112">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="58650-112">Software Requirements</span></span>

<span data-ttu-id="58650-113">Das Ankündigungsanwendung hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="58650-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="58650-114">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="58650-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="58650-115">Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen der Ankündigungsanwendung ausgeführt wird, muss die Windows Media Format-Laufzeitumgebung für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server installiert sein, auf denen Windows Server 2012 ausgeführt wird, oder Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="58650-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="58650-116">Für Windows Server 2008 R2 wird die Windows Media Format-Laufzeitkomponente als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="58650-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="58650-117">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-(WMA-) Dateien erforderlich, die das Ankündigungsanwendung für Ankündigungen und Musik abspielt.</span><span class="sxs-lookup"><span data-stu-id="58650-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="58650-118">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="58650-118">Port Requirements</span></span>

<span data-ttu-id="58650-119">Der Ankündigungsanwendung verwendet den folgenden Port:</span><span class="sxs-lookup"><span data-stu-id="58650-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="58650-120">**Port 5071**   wird für SIP-Überwachungsanforderungen verwendet</span><span class="sxs-lookup"><span data-stu-id="58650-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="58650-121">Dieser Port ist die Standardeinstellung, die Sie ändern können, indem Sie das Cmdlet "Cmdlet <STRONG>festlegen-CsApplicationServer</STRONG> " verwenden.</span><span class="sxs-lookup"><span data-stu-id="58650-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="58650-122">Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="58650-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="58650-123">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="58650-123">Audio File Requirements</span></span>

<span data-ttu-id="58650-124">Das Ankündigungsanwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-(WMA-) Dateiformat für Musik und Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="58650-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="58650-125">Die Anforderungen an die Audiodateien für die Ankündigungsanwendung entsprechen denen für die Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="58650-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="58650-126">Ausführliche Informationen finden Sie unter [Technical Requirements for Response Group in lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="58650-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

