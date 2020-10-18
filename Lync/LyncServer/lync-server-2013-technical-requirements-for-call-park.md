---
title: 'Lync Server 2013: technische Anforderungen für das Parken von Anrufen'
description: 'Lync Server 2013: technische Anforderungen für das Parken von anrufen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ddc17b40f78c42c090d1a87b4580ebdad0a07f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577131"
---
# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="df432-103">Technische Anforderungen für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="df432-103">Technical requirements for Call Park in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df432-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="df432-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="df432-105">In diesem Abschnitt werden die folgenden technischen Anforderungen für das Parken von Anrufen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="df432-105">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="df432-106">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="df432-106">Hardware requirements</span></span>

  - <span data-ttu-id="df432-107">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="df432-107">Software requirements</span></span>

  - <span data-ttu-id="df432-108">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="df432-108">Port requirements</span></span>

  - <span data-ttu-id="df432-109">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="df432-109">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="df432-110">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="df432-110">Hardware Requirements</span></span>

<span data-ttu-id="df432-111">Die Anwendung zum Parken von Anrufen hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="df432-111">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="df432-112">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="df432-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="df432-113">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="df432-113">Software Requirements</span></span>

<span data-ttu-id="df432-114">Das Anwendung zum Parken von Anrufen hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="df432-114">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="df432-115">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="df432-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="df432-116">Auf allen Front-End-Servern und Standard Edition-Servern, auf denen die Anwendung zum Parken von Anrufen bereitgestellt wird, muss die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="df432-116">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="df432-117">Für Windows Server 2008 R2 wird Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="df432-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="df432-118">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-(WMA-) Dateien erforderlich, die Park-Wiedergabe für Musik in der Warteschleife aufrufen.</span><span class="sxs-lookup"><span data-stu-id="df432-118">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="df432-119">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="df432-119">Port Requirements</span></span>

<span data-ttu-id="df432-120">Der Anwendung zum Parken von Anrufen verwendet den folgenden Port:</span><span class="sxs-lookup"><span data-stu-id="df432-120">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="df432-121">**Port 5075**     Wird für SIP-Überwachungsanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="df432-121">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df432-122">Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können.</span><span class="sxs-lookup"><span data-stu-id="df432-122">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="df432-123">Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="df432-123">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="df432-124">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="df432-124">Audio File Requirements</span></span>

<span data-ttu-id="df432-125">Das Anwendung zum Parken von Anrufen unterstützt nur Windows Media Audio-(WMA-) Dateien für die Wartemusik.</span><span class="sxs-lookup"><span data-stu-id="df432-125">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="df432-126">Sie können Dateien für Wartemusik mit Microsoft Expression Encoder 4 anpassen.</span><span class="sxs-lookup"><span data-stu-id="df432-126">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="df432-127">Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter "Expression Encoder 4" unter [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="df432-127">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="df432-128">Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="df432-128">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="df432-129">Das empfohlene Format für Wartemusikdateien für die Anwendung zum Parken von Anrufen ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR oder 32 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="df432-129">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="df432-130">Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn diese mit 44 kHz aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="df432-130">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

