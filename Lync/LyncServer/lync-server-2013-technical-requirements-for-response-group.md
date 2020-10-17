---
title: 'Lync Server 2013: technische Anforderungen für Reaktionsgruppen'
description: 'Lync Server 2013: technische Anforderungen für die Reaktionsgruppe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3125ed8c732960e23970229e99bf5a8487eb96a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550321"
---
# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="43e15-103">Technische Voraussetzungen für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43e15-103">Technical requirements for Response Group in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43e15-104">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="43e15-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="43e15-105">In diesem Abschnitt werden die folgenden technischen Anforderungen für die Reaktionsgruppenanwendung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="43e15-105">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="43e15-106">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="43e15-106">Hardware requirements</span></span>

  - <span data-ttu-id="43e15-107">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="43e15-107">Software requirements</span></span>

  - <span data-ttu-id="43e15-108">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="43e15-108">Port requirements</span></span>

  - <span data-ttu-id="43e15-109">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="43e15-109">Audio file requirements</span></span>

  - <span data-ttu-id="43e15-110">Anforderungen an das Konfigurationstool für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="43e15-110">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="43e15-111">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="43e15-111">Hardware Requirements</span></span>

<span data-ttu-id="43e15-112">Die Reaktionsgruppenanwendung hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="43e15-112">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="43e15-113">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="43e15-113">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="43e15-114">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="43e15-114">Software Requirements</span></span>

<span data-ttu-id="43e15-115">Das Reaktionsgruppenanwendung hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="43e15-115">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="43e15-116">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="43e15-116">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="43e15-117">Wenn Sie Windows Media-Audiodateien (WMA) für Musik und Ankündigungen von Reaktionsgruppen verwenden, muss für alle Front-End-Server oder Standard Edition-Server, auf denen der Reaktionsgruppenanwendung ausgeführt wird, die Windows Media Format-Laufzeitumgebung für Server mit Windows Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="43e15-117">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="43e15-118">Für Windows Server 2008 R2 wird Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="43e15-118">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="43e15-119">Ausführliche Informationen zu Audioanforderungen finden Sie unter "Anforderungen an die Audiodateien" weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="43e15-119">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="43e15-120">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="43e15-120">Port Requirements</span></span>

<span data-ttu-id="43e15-121">Der Reaktionsgruppenanwendung verwendet die folgenden Ports:</span><span class="sxs-lookup"><span data-stu-id="43e15-121">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="43e15-122">**Port 5071**     Wird für SIP-Überwachungsanforderungen verwendet</span><span class="sxs-lookup"><span data-stu-id="43e15-122">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="43e15-123">**Port 8404**     Wird für die Kommunikation zwischen Servern verwendet</span><span class="sxs-lookup"><span data-stu-id="43e15-123">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="43e15-124">Dieser Port wird für den Übereinstimmungs Dienst verwendet und ist erforderlich, wenn die Reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="43e15-124">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="43e15-125">Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können.</span><span class="sxs-lookup"><span data-stu-id="43e15-125">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="43e15-126">Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="43e15-126">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="43e15-127">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="43e15-127">Audio File Requirements</span></span>

<span data-ttu-id="43e15-128">Das Reaktionsgruppenanwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-(WMA-) Dateiformat für Reaktionsgruppen Nachrichten, Wartemusik oder IVR-Fragen (Interactive Voice Response).</span><span class="sxs-lookup"><span data-stu-id="43e15-128">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="43e15-129">Das Windows Media Audiodateiformat erfordert, dass die Windows Media Format-Laufzeitkomponente auf Front-End-Servern installiert ist, auf denen Windows Server 2008 R2 und Windows Server 2008 läuft.</span><span class="sxs-lookup"><span data-stu-id="43e15-129">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="43e15-130">Weitere Informationen finden Sie weiter oben in diesem Abschnitt unter "Software Anforderungen".</span><span class="sxs-lookup"><span data-stu-id="43e15-130">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="43e15-131">Unterstützte WAV-Dateiformate</span><span class="sxs-lookup"><span data-stu-id="43e15-131">Supported Wave File Formats</span></span>

<span data-ttu-id="43e15-132">Alle Wavedateien müssen die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="43e15-132">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="43e15-133">8-Bit- oder 16-Bit-Datei</span><span class="sxs-lookup"><span data-stu-id="43e15-133">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="43e15-134">LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format</span><span class="sxs-lookup"><span data-stu-id="43e15-134">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="43e15-135">Mono oder Stereo</span><span class="sxs-lookup"><span data-stu-id="43e15-135">Mono or stereo</span></span>

  - <span data-ttu-id="43e15-136">4 MB oder weniger</span><span class="sxs-lookup"><span data-stu-id="43e15-136">4MB or less</span></span>

<span data-ttu-id="43e15-137">Für eine optimale Leistung bei Wavedateien wird eine Mono-WAV-Datei mit 16 kHz und 16 Bit empfohlen.</span><span class="sxs-lookup"><span data-stu-id="43e15-137">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="43e15-138">Unterstützte WMA-Dateiformate</span><span class="sxs-lookup"><span data-stu-id="43e15-138">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="43e15-139">Wenn Sie eine Windows Media Audiodatei verwenden, sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems unter Last überprüfen.</span><span class="sxs-lookup"><span data-stu-id="43e15-139">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="43e15-140">Sie können Microsoft Expression Encoder 4 verwenden, um einen Datei in das WMA-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="43e15-140">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="43e15-141">Informationen zum Herunterladen von Expression Encoder 4 finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843) .</span><span class="sxs-lookup"><span data-stu-id="43e15-141">To download Expression Encoder 4, see [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="43e15-142">Anforderungen an das Konfigurations Tool für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="43e15-142">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="43e15-143">Das Reaktionsgruppen-Konfigurations Tool unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.</span><span class="sxs-lookup"><span data-stu-id="43e15-143">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43e15-144">32-Bit-oder 64-Bit-Versionen der Betriebssysteme werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43e15-144">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="43e15-145">Nur 32-Bit-Versionen von Internet Explorer werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43e15-145">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="43e15-146">Unterstützte Betriebssysteme und Webbrowser</span><span class="sxs-lookup"><span data-stu-id="43e15-146">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43e15-147">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="43e15-147">Operating system</span></span></th>
<th><span data-ttu-id="43e15-148">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="43e15-148">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43e15-149">Windows Vista mit Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="43e15-149">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="43e15-150">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="43e15-150">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="43e15-151">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-151">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-152">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-152">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e15-153">Windows 7</span><span class="sxs-lookup"><span data-stu-id="43e15-153">Windows 7</span></span></p>
<p><span data-ttu-id="43e15-154">Windows 7 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="43e15-154">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="43e15-155">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-155">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-156">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-156">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e15-157">Windows Server 2008 mit Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="43e15-157">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="43e15-158">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="43e15-158">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="43e15-159">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-159">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-160">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-160">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e15-161">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="43e15-161">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="43e15-162">Windows Server 2008 R2 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="43e15-162">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="43e15-163">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-163">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-164">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-164">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="43e15-165">Reaktionsgruppen-Agent-Konsole</span><span class="sxs-lookup"><span data-stu-id="43e15-165">Response Group Agent Console</span></span>

<span data-ttu-id="43e15-166">Die Agent-Konsole unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.</span><span class="sxs-lookup"><span data-stu-id="43e15-166">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43e15-167">32-Bit-oder 64-Bit-Versionen der Betriebssysteme werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43e15-167">32-bit or 64-bit versions of the operating systems are supported.</span></span> <span data-ttu-id="43e15-168">Nur 32-Bit-Versionen von Internet Explorer werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43e15-168">Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="43e15-169">Unterstützte Betriebssysteme und Webbrowser</span><span class="sxs-lookup"><span data-stu-id="43e15-169">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43e15-170">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="43e15-170">Operating system</span></span></th>
<th><span data-ttu-id="43e15-171">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="43e15-171">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43e15-172">Windows Vista mit Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="43e15-172">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="43e15-173">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="43e15-173">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="43e15-174">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-174">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-175">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-175">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e15-176">Windows 7</span><span class="sxs-lookup"><span data-stu-id="43e15-176">Windows 7</span></span></p>
<p><span data-ttu-id="43e15-177">Windows 7 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="43e15-177">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="43e15-178">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-178">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-179">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-179">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-180">Firefox 10,0</span><span class="sxs-lookup"><span data-stu-id="43e15-180">Firefox 10.0</span></span></p>
<p><span data-ttu-id="43e15-181">Chrome 18,0</span><span class="sxs-lookup"><span data-stu-id="43e15-181">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43e15-182">Windows Server 2008 mit Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="43e15-182">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="43e15-183">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="43e15-183">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="43e15-184">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-184">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-185">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-185">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43e15-186">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="43e15-186">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="43e15-187">Windows Server 2008 R2 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="43e15-187">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="43e15-188">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-188">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-189">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="43e15-189">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="43e15-190">Firefox 10,0</span><span class="sxs-lookup"><span data-stu-id="43e15-190">Firefox 10.0</span></span></p>
<p><span data-ttu-id="43e15-191">Chrome 18,0</span><span class="sxs-lookup"><span data-stu-id="43e15-191">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

