---
title: 'Lync Server 2013: Technische Anforderungen für die Ankündigungsanwendung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for the Announcement application
ms:assetid: fbd8c204-3765-4b22-a0c9-a781b5126366
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205413(v=OCS.15)
ms:contentKeyID: 48185944
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ec0da862ce2032f5a659c9e9b7bd3b437349a3cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-the-announcement-application-in-lync-server-2013"></a><span data-ttu-id="36ab9-102">Technische Anforderungen für die Ankündigungsanwendung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36ab9-102">Technical requirements for the Announcement application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36ab9-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="36ab9-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="36ab9-104">In diesem Abschnitt werden die folgenden technischen Voraussetzungen für die Ankündigungs Anwendung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="36ab9-104">This section describes the following technical requirements for the Announcement application:</span></span>

  - <span data-ttu-id="36ab9-105">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-105">Hardware requirements</span></span>

  - <span data-ttu-id="36ab9-106">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-106">Software requirements</span></span>

  - <span data-ttu-id="36ab9-107">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-107">Port requirements</span></span>

  - <span data-ttu-id="36ab9-108">Audiodatei-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-108">Audio file requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="36ab9-109">Hardware Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-109">Hardware Requirements</span></span>

<span data-ttu-id="36ab9-110">Die Ankündigungs Anwendung hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="36ab9-110">The Announcement application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="36ab9-111">Details zu den Hardwareanforderungen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="36ab9-111">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="36ab9-112">Software Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-112">Software Requirements</span></span>

<span data-ttu-id="36ab9-113">Die Ankündigungs Anwendung verfügt über die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="36ab9-113">The Announcement application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="36ab9-114">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="36ab9-114">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="36ab9-115">Auf allen Front-End-Servern oder Standard Edition-Servern, auf denen die Ankündigungs Anwendung ausgeführt wird, muss die Windows Media-Format Laufzeit für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="36ab9-115">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="36ab9-116">Bei Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.</span><span class="sxs-lookup"><span data-stu-id="36ab9-116">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="36ab9-117">Windows Media Format Runtime oder Microsoft Media Foundation ist für Windows Media Audio-Dateien (WMA) erforderlich, die von der Ankündigungs Anwendung für Ankündigungen und Musik wiedergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="36ab9-117">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="36ab9-118">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-118">Port Requirements</span></span>

<span data-ttu-id="36ab9-119">Die Ankündigungs Anwendung verwendet den folgenden Port:</span><span class="sxs-lookup"><span data-stu-id="36ab9-119">The Announcement application uses the following port:</span></span>

  - <span data-ttu-id="36ab9-120">**Port 5071**   für SIP-Abhör Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36ab9-120">**Port 5071**   Used for SIP listening requests</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36ab9-121">Dieser Port ist die Standardeinstellung, kann aber mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> geändert werden.</span><span class="sxs-lookup"><span data-stu-id="36ab9-121">This port is the default setting, which you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="36ab9-122">Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="36ab9-122">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="36ab9-123">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="36ab9-123">Audio File Requirements</span></span>

<span data-ttu-id="36ab9-124">Die Ankündigungs Anwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-Dateiformat (WMA) für Musik und Ankündigungen.</span><span class="sxs-lookup"><span data-stu-id="36ab9-124">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="36ab9-125">Die Anforderungen an die Audiodateien für die Ankündigungs Anwendung sind identisch mit der Antwortgruppen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="36ab9-125">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="36ab9-126">Ausführliche Informationen finden Sie unter [Technische Voraussetzungen für die Reaktionsgruppe in lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span><span class="sxs-lookup"><span data-stu-id="36ab9-126">For details, see [Technical requirements for Response Group in Lync Server 2013](lync-server-2013-technical-requirements-for-response-group.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

