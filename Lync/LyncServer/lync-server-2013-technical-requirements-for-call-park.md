---
title: 'Lync Server 2013: technische Anforderungen für das Parken von Anrufen'
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
ms.openlocfilehash: 6467f4047754697322780373521cdd47fe1e1ba3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="f4464-102">Technische Anforderungen für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4464-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4464-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f4464-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f4464-104">In diesem Abschnitt werden die folgenden technischen Anforderungen für das Parken von Anrufen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="f4464-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="f4464-105">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="f4464-105">Hardware requirements</span></span>

  - <span data-ttu-id="f4464-106">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="f4464-106">Software requirements</span></span>

  - <span data-ttu-id="f4464-107">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="f4464-107">Port requirements</span></span>

  - <span data-ttu-id="f4464-108">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="f4464-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="f4464-109">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="f4464-109">Hardware Requirements</span></span>

<span data-ttu-id="f4464-110">Die Anwendung zum Parken von Anrufen hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="f4464-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="f4464-111">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f4464-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="f4464-112">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="f4464-112">Software Requirements</span></span>

<span data-ttu-id="f4464-113">Das Anwendung zum Parken von Anrufen hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="f4464-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="f4464-114">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="f4464-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f4464-115">Auf allen Front-End-Servern und Standard Edition-Servern, auf denen die Anwendung zum Parken von Anrufen bereitgestellt wird, muss die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server installiert sein, auf denen Windows Server 2012 oder Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="f4464-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="f4464-116">Für Windows Server 2008 R2 wird Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="f4464-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="f4464-117">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-(WMA-) Dateien erforderlich, die Park-Wiedergabe für Musik in der Warteschleife aufrufen.</span><span class="sxs-lookup"><span data-stu-id="f4464-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="f4464-118">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="f4464-118">Port Requirements</span></span>

<span data-ttu-id="f4464-119">Der Anwendung zum Parken von Anrufen verwendet den folgenden Port:</span><span class="sxs-lookup"><span data-stu-id="f4464-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="f4464-120">**Port 5075**   wird für SIP-Überwachungsanforderungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f4464-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4464-121">Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können.</span><span class="sxs-lookup"><span data-stu-id="f4464-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="f4464-122">Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f4464-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="f4464-123">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="f4464-123">Audio File Requirements</span></span>

<span data-ttu-id="f4464-124">Das Anwendung zum Parken von Anrufen unterstützt nur Windows Media Audio-(WMA-) Dateien für die Wartemusik.</span><span class="sxs-lookup"><span data-stu-id="f4464-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="f4464-125">Sie können Dateien für Wartemusik mit Microsoft Expression Encoder 4 anpassen.</span><span class="sxs-lookup"><span data-stu-id="f4464-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="f4464-126">Informationen zum Herunterladen von [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)Expression Encoder 4 finden Sie unter "Expression Encoder 4" unter.</span><span class="sxs-lookup"><span data-stu-id="f4464-126">To download Expression Encoder 4, see "Expression Encoder 4" at [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="f4464-127">Verwenden Sie das Tool, um die Datei in ein WMA-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="f4464-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="f4464-128">Das empfohlene Format für Wartemusikdateien für die Anwendung zum Parken von Anrufen ist Media Audio 9, 44 kHz, 16 Bit, Mono, CBR oder 32 KBit/s.</span><span class="sxs-lookup"><span data-stu-id="f4464-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4464-129">Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn diese mit 44 kHz aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="f4464-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

