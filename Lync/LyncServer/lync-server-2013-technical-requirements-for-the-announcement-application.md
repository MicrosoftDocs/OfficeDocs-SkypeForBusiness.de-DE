---
title: 'Lync Server 2013: technische Anforderungen für die Ankündigungsanwendung'
description: 'Lync Server 2013: Technische Voraussetzungen für die Ankündigungsanwendung.'
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
ms.openlocfilehash: adc5019408b79301bbcda3993ceb7d96ee4d9b7d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550311"
---
# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="8e880-103">Technische Anforderungen für die Ankündigungsanwendung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e880-103">Technical requirements for the Announcement application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e880-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8e880-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8e880-105">In diesem Abschnitt werden die folgenden technischen Anforderungen für die Ankündigungsanwendung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="8e880-105">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="8e880-106">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="8e880-106">Hardware requirements</span></span>

  - <span data-ttu-id="8e880-107">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="8e880-107">Software requirements</span></span>

  - <span data-ttu-id="8e880-108">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="8e880-108">Port requirements</span></span>

  - <span data-ttu-id="8e880-109">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="8e880-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="8e880-110">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="8e880-110">Hardware Requirements</span></span>

<span data-ttu-id="8e880-111">Die Ankündigungsanwendung hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="8e880-111">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="8e880-112">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8e880-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="8e880-113">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="8e880-113">Software Requirements</span></span>

<span data-ttu-id="8e880-114">Das Ankündigungsanwendung hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="8e880-114">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="8e880-115">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="8e880-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8e880-116">Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen der Ankündigungsanwendung ausgeführt wird, muss die Windows Media Format-Laufzeitumgebung für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="8e880-116">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="8e880-117">Für Windows Server 2008 R2 wird die Windows Media Format-Laufzeitkomponente als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="8e880-117">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="8e880-118">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-(WMA-) Dateien erforderlich, die das Ankündigungsanwendung für Ankündigungen und Musik abspielt.</span><span class="sxs-lookup"><span data-stu-id="8e880-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="8e880-119">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="8e880-119">Port Requirements</span></span>

<span data-ttu-id="8e880-120">Der Ankündigungsanwendung verwendet den folgenden Port:</span><span class="sxs-lookup"><span data-stu-id="8e880-120">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="8e880-121">**Port 5071**     Wird für SIP-Überwachungsanforderungen verwendet</span><span class="sxs-lookup"><span data-stu-id="8e880-121">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8e880-122">Dieser Port ist die Standardeinstellung, die Sie ändern können, indem Sie das Cmdlet "Cmdlet <STRONG>festlegen-CsApplicationServer</STRONG> " verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e880-122">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="8e880-123">Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="8e880-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="8e880-124">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="8e880-124">Audio File Requirements</span></span>

<span data-ttu-id="8e880-125">Das Ankündigungsanwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-(WMA-) Dateiformat für Musik und Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="8e880-125">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="8e880-126">Die Anforderungen an die Audiodateien für die Ankündigungsanwendung entsprechen denen für die Reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="8e880-126">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="8e880-127">Ausführliche Informationen finden Sie unter [Technical Requirements for Response Group in lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="8e880-127">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

