---
title: 'Lync Server 2013: Technische Anforderungen für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for Response Group
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204863(v=OCS.15)
ms:contentKeyID: 48184044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd87cb270d527753d9c6404ded4162791b542f7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a><span data-ttu-id="26bfd-102">Technische Anforderungen für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26bfd-102">Technical requirements for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26bfd-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="26bfd-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="26bfd-104">In diesem Abschnitt werden die folgenden technischen Voraussetzungen für die reaktionsgruppenanwendung beschrieben:</span><span class="sxs-lookup"><span data-stu-id="26bfd-104">This section describes the following technical requirements for the Response Group application:</span></span>

  - <span data-ttu-id="26bfd-105">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-105">Hardware requirements</span></span>

  - <span data-ttu-id="26bfd-106">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-106">Software requirements</span></span>

  - <span data-ttu-id="26bfd-107">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-107">Port requirements</span></span>

  - <span data-ttu-id="26bfd-108">Audiodatei-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-108">Audio file requirements</span></span>

  - <span data-ttu-id="26bfd-109">Anforderungen für das Konfigurationstool für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="26bfd-109">Response Group configuration tool requirements</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="26bfd-110">Hardware Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-110">Hardware Requirements</span></span>

<span data-ttu-id="26bfd-111">Die Antwortgruppen Anwendung hat die gleichen Hardwareanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="26bfd-111">The Response Group application has the same hardware requirements as Front End Servers.</span></span> <span data-ttu-id="26bfd-112">Details zu den Hardwareanforderungen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="26bfd-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="26bfd-113">Software Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-113">Software Requirements</span></span>

<span data-ttu-id="26bfd-114">Die reaktionsgruppenanwendung hat dieselben Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="26bfd-114">The Response Group application has the same operating system requirements and software prerequisites as Front End Servers.</span></span> <span data-ttu-id="26bfd-115">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="26bfd-115">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="26bfd-116">Wenn Sie Windows Media Audio (WMA)-Dateien für die Musik und Ankündigungen von Reaktionsgruppen verwenden, muss für alle Front-End-Server oder Standard Edition-Server, auf denen die reaktionsgruppenanwendung ausgeführt wird, die Windows Media-Format Laufzeit für Server unter Windows installiert sein. Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="26bfd-116">If you use Windows Media Audio (.wma) files for Response Group music and announcements, all Front End Servers or Standard Editions servers that run the Response Group application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="26bfd-117">Für Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.</span><span class="sxs-lookup"><span data-stu-id="26bfd-117">For Windows Server 2008 R2, Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span>

<span data-ttu-id="26bfd-118">Weitere Informationen zu Audioanforderungen finden Sie unter "Anforderungen an die Audiodateien" weiter unten in diesem Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="26bfd-118">For more details about audio requirements, see "Audio File Requirements" later in this section.</span></span>

</div>

<div>

## <a name="port-requirements"></a><span data-ttu-id="26bfd-119">Portanforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-119">Port Requirements</span></span>

<span data-ttu-id="26bfd-120">Die Antwortgruppen Anwendung verwendet die folgenden Ports:</span><span class="sxs-lookup"><span data-stu-id="26bfd-120">The Response Group application uses the following ports:</span></span>

  - <span data-ttu-id="26bfd-121">**Port 5071**   für SIP-Abhör Anforderungen</span><span class="sxs-lookup"><span data-stu-id="26bfd-121">**Port 5071**   Used for SIP listening requests</span></span>

  - <span data-ttu-id="26bfd-122">**Port 8404**   , der für die Kommunikation zwischen Servern verwendet wird</span><span class="sxs-lookup"><span data-stu-id="26bfd-122">**Port 8404**   Used for interserver communications</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26bfd-123">Dieser Port wird für den Übereinstimmungs Dienst verwendet und ist erforderlich, wenn die reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="26bfd-123">This port is used for the Match Making service and is required when the Response Group application is deployed in a pool that has more than one Front End Server.</span></span>

    
    </div>

<div>


> [!NOTE]  
> <span data-ttu-id="26bfd-124">Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können.</span><span class="sxs-lookup"><span data-stu-id="26bfd-124">These ports are default settings that you can change by using the <STRONG>Set-CsApplicationServer</STRONG> cmdlet.</span></span> <span data-ttu-id="26bfd-125">Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="26bfd-125">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>



</div>

</div>

<div>

## <a name="audio-file-requirements"></a><span data-ttu-id="26bfd-126">Anforderungen für Audiodateien</span><span class="sxs-lookup"><span data-stu-id="26bfd-126">Audio File Requirements</span></span>

<span data-ttu-id="26bfd-127">Die Antwortgruppen Anwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-Dateiformat (WMA) für Reaktionsgruppen Nachrichten, Warteschleife-Musik oder IVR-Fragen (Interactive Voice Response).</span><span class="sxs-lookup"><span data-stu-id="26bfd-127">The Response Group application supports wave (.wav) file format and Windows Media audio (.wma) file format for Response Group messages, on-hold music, or interactive voice response (IVR) questions.</span></span>

<span data-ttu-id="26bfd-128">Das Windows Media-Audiodateiformat setzt voraus, dass die Windows Media-Format Laufzeit auf Front-End-Servern mit Windows Server 2008 R2 und Windows Server 2008 installiert ist.</span><span class="sxs-lookup"><span data-stu-id="26bfd-128">The Windows Media audio file format requires that the Windows Media Format Runtime is installed on Front End Servers running Windows Server 2008 R2 and Windows Server 2008.</span></span> <span data-ttu-id="26bfd-129">Nähere Informationen dazu finden Sie weiter oben in diesem Abschnitt unter „Softwareanforderungen“.</span><span class="sxs-lookup"><span data-stu-id="26bfd-129">For more details, see "Software Requirements" earlier in this section.</span></span>

<div>

## <a name="supported-wave-file-formats"></a><span data-ttu-id="26bfd-130">Unterstützte WAV-Dateiformate</span><span class="sxs-lookup"><span data-stu-id="26bfd-130">Supported Wave File Formats</span></span>

<span data-ttu-id="26bfd-131">WAV-Dateien müssen folgenden Anforderungen entsprechen:</span><span class="sxs-lookup"><span data-stu-id="26bfd-131">All wave files must meet the following requirements:</span></span>

  - <span data-ttu-id="26bfd-132">8- oder 16-Bit-Datei</span><span class="sxs-lookup"><span data-stu-id="26bfd-132">8-bit or 16-bit file</span></span>

  - <span data-ttu-id="26bfd-133">LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format</span><span class="sxs-lookup"><span data-stu-id="26bfd-133">Linear pulse code modulation (LPCM), A-Law, or mu-Law format</span></span>

  - <span data-ttu-id="26bfd-134">Mono oder Stereo</span><span class="sxs-lookup"><span data-stu-id="26bfd-134">Mono or stereo</span></span>

  - <span data-ttu-id="26bfd-135">Maximal 4 MB</span><span class="sxs-lookup"><span data-stu-id="26bfd-135">4MB or less</span></span>

<span data-ttu-id="26bfd-136">Um die beste Leistung zu erzielen, wird eine WAV-Datei mit den Werten 16 kHz, Mono, 16 Bit empfohlen.</span><span class="sxs-lookup"><span data-stu-id="26bfd-136">For the best performance of wave files, a 16 kHz, mono, 16-bit Wave file is recommended.</span></span>

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a><span data-ttu-id="26bfd-137">Unterstützte WMA-Dateiformate</span><span class="sxs-lookup"><span data-stu-id="26bfd-137">Supported Windows Media Audio File Formats</span></span>

<span data-ttu-id="26bfd-138">Bei Verwendung einer WMA-Datei sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems überprüfen, wenn dieses ausgelastet ist.</span><span class="sxs-lookup"><span data-stu-id="26bfd-138">If you use a Windows Media audio file, consider using low bit rates, and verify the performance of your system under load.</span></span>

<span data-ttu-id="26bfd-139">Sie können Microsoft Expression Encoder 4 verwenden, um eine Datei in das WMA-Format zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="26bfd-139">You can use the Microsoft Expression Encoder 4 to convert a file to the Windows Media Audio format.</span></span> <span data-ttu-id="26bfd-140">Informationen zum Herunterladen von Expression Encoder [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)4 finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="26bfd-140">To download Expression Encoder 4, see [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843).</span></span>

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a><span data-ttu-id="26bfd-141">Anforderungen des Konfigurationstools für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="26bfd-141">Response Group Configuration Tool Requirements</span></span>

<span data-ttu-id="26bfd-142">Das Reaktionsgruppen-Konfigurations Tool unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.</span><span class="sxs-lookup"><span data-stu-id="26bfd-142">The Response Group Configuration Tool supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26bfd-p107">32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26bfd-p107">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="26bfd-145">Unterstützte Betriebssysteme und Webbrowser</span><span class="sxs-lookup"><span data-stu-id="26bfd-145">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26bfd-146">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="26bfd-146">Operating system</span></span></th>
<th><span data-ttu-id="26bfd-147">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="26bfd-147">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26bfd-148">Windows Vista mit Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="26bfd-148">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="26bfd-149">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="26bfd-149">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="26bfd-150">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-150">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-151">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-151">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26bfd-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="26bfd-152">Windows 7</span></span></p>
<p><span data-ttu-id="26bfd-153">Windows 7 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="26bfd-153">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="26bfd-154">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-154">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-155">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-155">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26bfd-156">Windows Server 2008 mit Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="26bfd-156">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="26bfd-157">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="26bfd-157">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="26bfd-158">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-158">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-159">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-159">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26bfd-160">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="26bfd-160">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="26bfd-161">Windows Server 2008 R2 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="26bfd-161">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="26bfd-162">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-162">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-163">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-163">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a><span data-ttu-id="26bfd-164">Agentkonsole für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="26bfd-164">Response Group Agent Console</span></span>

<span data-ttu-id="26bfd-165">Die Agentkonsole unterstützt die in der folgenden Tabelle aufgeführten Kombinationen aus Betriebssystemen und Webbrowsern.</span><span class="sxs-lookup"><span data-stu-id="26bfd-165">The agent console supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26bfd-p108">32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26bfd-p108">32-bit or 64-bit versions of the operating systems are supported. Only 32-bit versions of Internet Explorer are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="26bfd-168">Unterstützte Betriebssysteme und Webbrowser</span><span class="sxs-lookup"><span data-stu-id="26bfd-168">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="26bfd-169">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="26bfd-169">Operating system</span></span></th>
<th><span data-ttu-id="26bfd-170">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="26bfd-170">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="26bfd-171">Windows Vista mit Service Pack (SP) 2</span><span class="sxs-lookup"><span data-stu-id="26bfd-171">Windows Vista with Service Pack (SP) 2</span></span></p></td>
<td><p><span data-ttu-id="26bfd-172">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="26bfd-172">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="26bfd-173">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-173">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-174">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-174">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26bfd-175">Windows 7</span><span class="sxs-lookup"><span data-stu-id="26bfd-175">Windows 7</span></span></p>
<p><span data-ttu-id="26bfd-176">Windows 7 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="26bfd-176">Windows 7 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="26bfd-177">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-177">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-178">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-178">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-179">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="26bfd-179">Firefox 10.0</span></span></p>
<p><span data-ttu-id="26bfd-180">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="26bfd-180">Chrome 18.0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="26bfd-181">Windows Server 2008 mit Service Pack 2</span><span class="sxs-lookup"><span data-stu-id="26bfd-181">Windows Server 2008 with Service Pack 2</span></span></p></td>
<td><p><span data-ttu-id="26bfd-182">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="26bfd-182">Internet Explorer 7</span></span></p>
<p><span data-ttu-id="26bfd-183">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-183">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-184">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-184">Internet Explorer 9 (native mode)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="26bfd-185">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="26bfd-185">Windows Server 2008 R2</span></span></p>
<p><span data-ttu-id="26bfd-186">Windows Server 2008 R2 mit Service Pack 1</span><span class="sxs-lookup"><span data-stu-id="26bfd-186">Windows Server 2008 R2 with Service Pack 1</span></span></p></td>
<td><p><span data-ttu-id="26bfd-187">Internet Explorer 8 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-187">Internet Explorer 8 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-188">Internet Explorer 9 (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="26bfd-188">Internet Explorer 9 (native mode)</span></span></p>
<p><span data-ttu-id="26bfd-189">Firefox 10.0</span><span class="sxs-lookup"><span data-stu-id="26bfd-189">Firefox 10.0</span></span></p>
<p><span data-ttu-id="26bfd-190">Chrome 18.0</span><span class="sxs-lookup"><span data-stu-id="26bfd-190">Chrome 18.0</span></span></p></td>
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

