---
title: 'Lync Server 2013: Technische Anforderungen für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Call Park
ms:assetid: 38bcf302-2b72-4492-9266-f6dc31b566e1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204818(v=OCS.15)
ms:contentKeyID: 48183897
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 068c03c3b99e911766d2c60eec2a5515b3750d29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-call-park-in-lync-server-2013"></a><span data-ttu-id="ab4ca-102">Technische Anforderungen für das Parken von Anrufen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab4ca-102">Technical requirements for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab4ca-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ab4ca-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ab4ca-104">In diesem Abschnitt werden die folgenden technischen Voraussetzungen für den Parken von Anrufen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ab4ca-104">This section describes the following technical requirements for Call Park:</span></span>

  - <span data-ttu-id="ab4ca-105">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-105">Hardware requirements</span></span>

  - <span data-ttu-id="ab4ca-106">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-106">Software requirements</span></span>

  - <span data-ttu-id="ab4ca-107">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-107">Port requirements</span></span>

  - <span data-ttu-id="ab4ca-108">Audiodatei-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="ab4ca-109">Hardware Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-109">Hardware Requirements</span></span>

<span data-ttu-id="ab4ca-110">Die Anwendung für den Anruf Park hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-110">The Call Park application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="ab4ca-111">Details zu den Hardwareanforderungen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="ab4ca-112">Software Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-112">Software Requirements</span></span>

<span data-ttu-id="ab4ca-113">Die Anwendung für den Anruf Park hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-113">The Call Park application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="ab4ca-114">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="ab4ca-115">Auf allen Front-End-Servern und Standard Edition-Servern, auf denen die Anwendung für das Parken von Anrufen bereitgestellt wird, muss die Windows Media-Format Laufzeit für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="ab4ca-115">All Front End Servers and Standard Edition servers where the Call Park application is deployed must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="ab4ca-116">Für Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-116">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="ab4ca-117">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-Dateien (WMA) erforderlich, in denen Park Wiedergaben für Musik im Wartebereich aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that Call Park plays for music on hold.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="ab4ca-118">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="ab4ca-118">Port Requirements</span></span>

<span data-ttu-id="ab4ca-119">Die Anwendung für den Anruf Park verwendet den folgenden Port:</span><span class="sxs-lookup"><span data-stu-id="ab4ca-119">The Call Park application uses the following port:</span></span>

  - <span data-ttu-id="ab4ca-120">**Port 5075**   , der für SIP-Überwachungsanforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-120">**Port 5075**   Used for SIP listening requests.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab4ca-121">Dieser Port ist die Standardeinstellung, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-121">This port is a default setting that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="ab4ca-122">Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="ab4ca-123">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="ab4ca-123">Audio File Requirements</span></span>

<span data-ttu-id="ab4ca-124">Die Anwendung "Parken" unterstützt nur WMA-Dateien (Windows Media Audio) für Musik in Wartestellung.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-124">The Call Park application supports only Windows Media Audio (.wma) files for music on hold.</span></span> <span data-ttu-id="ab4ca-125">Sie können den Microsoft Expression Encoder 4 verwenden, um Dateien für Musik in Wartestellung anzupassen.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-125">You can use the Microsoft Expression Encoder 4 to customize files for music on hold.</span></span> <span data-ttu-id="ab4ca-126">Informationen zum Herunterladen von [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)Expression Encoder 4 finden Sie unter "Expression Encoder 4" unter.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-126">To download Expression Encoder 4, see "Expression Encoder 4" at [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span> <span data-ttu-id="ab4ca-127">Verwenden Sie das Tool, um die Datei in ein WMA-Format umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-127">Use the tool to convert the file to a .wma format.</span></span> <span data-ttu-id="ab4ca-128">Das empfohlene Format für Music-on-halten-Dateien im Parken von anrufen ist Media Audio 9, 44 kHz, 16 Bits, Mono, CBR, 32 Kbit/s.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-128">The recommended format for Call Park music-on-hold files is Media Audio 9, 44 kHz, 16 bits, Mono, CBR, 32 kbps.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ab4ca-129">Die konvertierte Datei wird über das Telefon nur mit 16 kHz abgespielt, auch wenn sie mit 44 kHz aufgezeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="ab4ca-129">The converted file plays over the phone only at 16 kHz, even if it was recorded at 44 kHz.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

