---
title: Lync Server 2013 technische Anforderungen für Konferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc548446120ae4088d90acb45c258f3f736063d0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="b96c8-102">Technische Anforderungen für Konferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b96c8-102">Technical requirements for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b96c8-103">_**Letztes Änderungsstand des Themas:** 2014-06-25_</span><span class="sxs-lookup"><span data-stu-id="b96c8-103">_**Topic Last Modified:** 2014-06-25_</span></span>

<span data-ttu-id="b96c8-104">Für lync Server 2013 werden Einwahlkonferenzen, A/V-Konferenzen, Chat Konferenzen und Webkonferenzfunktionen immer auf Front-End-Servern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b96c8-104">For Lync Server 2013, dial-in conferencing, A/V conferencing, instant messaging (IM) conferencing and web conferencing capabilities always run on Front End Servers.</span></span>

<span data-ttu-id="b96c8-105">In diesem Abschnitt werden die Hardware- und Softwareanforderungen für diese Server beschrieben, zusammen mit Informationen zur unterstützten gemeinsamen Ausführung.</span><span class="sxs-lookup"><span data-stu-id="b96c8-105">This section details the hardware and software requirements for these servers, along with the supported collocation.</span></span>

<span data-ttu-id="b96c8-106">Das Feature für Einwahlkonferenzen umfasst eine Vielzahl von Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b96c8-106">Dial-in conferencing is a feature that includes a variety of components.</span></span> <span data-ttu-id="b96c8-107">Einige der Komponenten sind spezifisch für Einwahlkonferenzen und einige sind Enterprise-VoIP-Komponenten.</span><span class="sxs-lookup"><span data-stu-id="b96c8-107">Some of the components are specific to dial-in conferencing and some are Enterprise Voice components.</span></span> <span data-ttu-id="b96c8-108">In diesem Abschnitt werden die Anforderungen für diejenigen Komponenten beschrieben, die für das Feature für Einwahlkonferenzen spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="b96c8-108">This section describes the requirements for the components that are specific to dial-in conferencing.</span></span> <span data-ttu-id="b96c8-109">Ausführliche Informationen zu Vermittlungsserver-und PSTN-Gateways (Public Switched Telephone Network) finden Sie unter [Vermittlungsserver-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md) und [Komponenten und Topologien für Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96c8-109">For details about Mediation Server and public switched telephone network (PSTN) gateway requirements, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md) and [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

<div>

## <a name="hardware-requirements"></a><span data-ttu-id="b96c8-110">Hardwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="b96c8-110">Hardware Requirements</span></span>

<span data-ttu-id="b96c8-111">Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server zusammengestellt werden, sind die Server Hardwareanforderungen identisch mit den Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="b96c8-111">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server hardware requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="b96c8-112">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96c8-112">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="b96c8-113">Die folgenden Komponenten, die für Einwahlkonferenzen erforderlich sind, weisen auch die gleichen Hardwareanforderungen wie Front-End-Server auf:</span><span class="sxs-lookup"><span data-stu-id="b96c8-113">The following components required for dial-in conferencing also have the same hardware requirements as Front End Servers:</span></span>

  - <span data-ttu-id="b96c8-114">Anwendungsdienst</span><span class="sxs-lookup"><span data-stu-id="b96c8-114">Application service</span></span>

  - <span data-ttu-id="b96c8-115">Konferenzzentrale</span><span class="sxs-lookup"><span data-stu-id="b96c8-115">Conferencing Attendant application</span></span>

  - <span data-ttu-id="b96c8-116">Konferenzankündigungsanwendung</span><span class="sxs-lookup"><span data-stu-id="b96c8-116">Conferencing Announcement application</span></span>

<span data-ttu-id="b96c8-117">Die Hardwareanforderungen für Front-End-Server entsprechen denen für viele andere Server Rollen in lync Server 2013, die in der folgenden Tabelle aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="b96c8-117">The hardware requirements for Front End Server are the same as for many other server roles in Lync Server 2013 are outlined in the following table.</span></span>

</div>

<div>

## <a name="software-requirements"></a><span data-ttu-id="b96c8-118">Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="b96c8-118">Software Requirements</span></span>

<span data-ttu-id="b96c8-119">Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server zusammengestellt werden, sind die Server Softwareanforderungen identisch mit den Front-End-Servern.</span><span class="sxs-lookup"><span data-stu-id="b96c8-119">Because web conferencing and A/V conferencing are collocated with the Front End Server, the server software requirements are the same as for the Front End Servers.</span></span> <span data-ttu-id="b96c8-120">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96c8-120">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b96c8-121">Für Webkonferenzen erfordert lync Server 2013 auch Office-Webanwendungen und den Office-webapps-Server (ehemals "AS-Server" genannt), um PowerPoint-Präsentationen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="b96c8-121">For web conferencing, Lync Server 2013 also requires Office Web Apps and the Office Web Apps Server (formerly known as WAC Server) to handle PowerPoint presentations.</span></span> <span data-ttu-id="b96c8-122">Ausführliche Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="b96c8-122">For details, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

<span data-ttu-id="b96c8-123">Für Einwahlkonferenzen haben Anwendungsdienst, Konferenzzentrale und Konferenzankündigungsanwendung dieselben Betriebssystemanforderungen wie Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="b96c8-123">For dial-in conferencing, Application service, Conferencing Attendant application, and Conferencing Announcement application have the same operating system requirements as Front End Servers.</span></span> <span data-ttu-id="b96c8-124">Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96c8-124">For details about software requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<span data-ttu-id="b96c8-125">Für Konferenzzentrale und Konferenzankündigungsanwendung muss Windows Media Format Runtime auf Front-End-Servern installiert sein.</span><span class="sxs-lookup"><span data-stu-id="b96c8-125">Conferencing Attendant application and Conferencing Announcement application require that Windows Media Format Runtime is installed on Front End Servers.</span></span> <span data-ttu-id="b96c8-126">Die Windows Media Format-Laufzeitkomponente ist für die Wiedergabe von WMA-Dateien (Windows Media Audio) erforderlich, die für Wartemusik, aufgezeichnete Namen und Ansagen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b96c8-126">The Windows Media Format Runtime is required to play Windows Media audio (WMA) files that are used for music on hold, recorded names, and prompts.</span></span> <span data-ttu-id="b96c8-127">Mit Ausnahme von Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format-Laufzeitkomponente beim Ausführen von Setup automatisch als Teil der Windows-Desktop Umgebung installiert, aber möglicherweise müssen Sie den Computer neu starten.</span><span class="sxs-lookup"><span data-stu-id="b96c8-127">Except for Windows Server 2012 and Windows Server 2012 R2, the Windows Media Format Runtime is installed automatically as part of the Windows Desktop Experience when you run Setup, but you might need to restart the computer.</span></span> <span data-ttu-id="b96c8-128">Es wird daher empfohlen, die Windows Media Format-Laufzeitkomponente vor Ausführung des Setups als Teil der Windows-Desktoperfahrung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b96c8-128">Therefore, we recommend that you install as part of the Windows Desktop Experience, which includes Windows Media Format Runtime before you run Setup.</span></span> <span data-ttu-id="b96c8-129">Für Windows Server 2012 und Windows Server 2012 R2 ist Microsoft Media Foundation erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b96c8-129">Windows Server 2012 and Windows Server 2012 R2 requires Microsoft Media Foundation.</span></span>

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a><span data-ttu-id="b96c8-130">Portanforderungen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b96c8-130">Port Requirements for dial-in conferencing</span></span>

<span data-ttu-id="b96c8-p107">In der folgenden Tabelle sind die Ports beschrieben, die von Einwahlkonferenzen verwendet werden. Wenn ein Gerät zum Lastenausgleich verwendet wird, stellen Sie sicher, dass dieses für die Ports konfiguriert ist, die von den im Pool ausgeführten Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b96c8-p107">The following table describes the ports that are used by dial-in conferencing. If you use a load balancer, ensure that the load balancer is configured for the ports used by any applications that will run in the pool.</span></span>

<span data-ttu-id="b96c8-133">Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können.</span><span class="sxs-lookup"><span data-stu-id="b96c8-133">These ports are default settings that you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="b96c8-134">Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="b96c8-134">For details about this cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b96c8-135">Alle Instanzen derselben Anwendung in einem Pool verwenden denselben SIP-Überwachungsport.</span><span class="sxs-lookup"><span data-stu-id="b96c8-135">All instances of the same application in a pool use the same SIP listening port.</span></span>



</div>

### <a name="ports-used-by-dial-in-conferencing"></a><span data-ttu-id="b96c8-136">Von Einwahlkonferenzen verwendete Ports</span><span class="sxs-lookup"><span data-stu-id="b96c8-136">Ports used by dial-in conferencing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b96c8-137">Portnummer</span><span class="sxs-lookup"><span data-stu-id="b96c8-137">Port number</span></span></th>
<th><span data-ttu-id="b96c8-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b96c8-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b96c8-139">5072</span><span class="sxs-lookup"><span data-stu-id="b96c8-139">5072</span></span></p></td>
<td><p><span data-ttu-id="b96c8-140">Wird von Konferenzzentrale für SIP-Überwachungsanforderungen verwendet</span><span class="sxs-lookup"><span data-stu-id="b96c8-140">Used by Conferencing Attendant application for SIP listening requests</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c8-141">5073</span><span class="sxs-lookup"><span data-stu-id="b96c8-141">5073</span></span></p></td>
<td><p><span data-ttu-id="b96c8-142">Wird von Konferenzankündigungsanwendung für SIP-Überwachungsanforderungen verwendet</span><span class="sxs-lookup"><span data-stu-id="b96c8-142">Used by Conferencing Announcement application for SIP listening requests</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a><span data-ttu-id="b96c8-143">Unterstützte Clients für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b96c8-143">Supported Clients for Dial-In Conferencing</span></span>

<span data-ttu-id="b96c8-144">Sie können den folgenden Client zur Planung von lokalen Konferenzen verwenden, die einen Zugriff per Einwahl unterstützen:</span><span class="sxs-lookup"><span data-stu-id="b96c8-144">You can use the following client to schedule on-premises conferences that support dial-in access:</span></span>

  - <span data-ttu-id="b96c8-145">Online Besprechungs-Add-in für lync 2013 (wird bei der Installation von lync 2013 oder Teilnehmern automatisch installiert)</span><span class="sxs-lookup"><span data-stu-id="b96c8-145">Online Meeting Add-in for Lync 2013 (installed automatically when you install Lync 2013 or Attendee)</span></span>

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a><span data-ttu-id="b96c8-146">Seite "Einstellungen für Einwahlkonferenzen" Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b96c8-146">Dial-in Conferencing Settings page Requirements</span></span>

<span data-ttu-id="b96c8-147">Das Seite "Einstellungen für Einwahlkonferenzen" unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.</span><span class="sxs-lookup"><span data-stu-id="b96c8-147">The Dial-in Conferencing Settings page supports the combinations of operating systems and web browsers described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b96c8-148">Es werden 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b96c8-148">32-bit and 64-bit versions of the operating systems are supported.</span></span>



</div>

### <a name="supported-operating-systems-and-web-browsers"></a><span data-ttu-id="b96c8-149">Unterstützte Betriebssysteme und Webbrowser</span><span class="sxs-lookup"><span data-stu-id="b96c8-149">Supported Operating Systems and Web Browsers</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b96c8-150">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="b96c8-150">Operating system</span></span></th>
<th><span data-ttu-id="b96c8-151">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="b96c8-151">Web browser</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b96c8-152">Windows 7</span><span class="sxs-lookup"><span data-stu-id="b96c8-152">Windows 7</span></span></p></td>
<td><p><span data-ttu-id="b96c8-153">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="b96c8-153">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="b96c8-154">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="b96c8-154">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="b96c8-155">Firefox</span><span class="sxs-lookup"><span data-stu-id="b96c8-155">Firefox</span></span></p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b96c8-156">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b96c8-156">Windows Server 2008 R2</span></span></p></td>
<td><p><span data-ttu-id="b96c8-157">Internet Explorer 9</span><span class="sxs-lookup"><span data-stu-id="b96c8-157">Internet Explorer 9</span></span></p>
<p><span data-ttu-id="b96c8-158">Internet Explorer 8</span><span class="sxs-lookup"><span data-stu-id="b96c8-158">Internet Explorer 8</span></span></p>
<p><span data-ttu-id="b96c8-159">Internet Explorer 7</span><span class="sxs-lookup"><span data-stu-id="b96c8-159">Internet Explorer 7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b96c8-160">Mac OS</span><span class="sxs-lookup"><span data-stu-id="b96c8-160">Mac OS</span></span></p></td>
<td><p><span data-ttu-id="b96c8-161">Firefox</span><span class="sxs-lookup"><span data-stu-id="b96c8-161">Firefox</span></span></p>
<p><span data-ttu-id="b96c8-162">Safari</span><span class="sxs-lookup"><span data-stu-id="b96c8-162">Safari</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a><span data-ttu-id="b96c8-163">Audiodateianforderungen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b96c8-163">Audio File Requirements for dial-in conferencing</span></span>

<span data-ttu-id="b96c8-164">Lync Server 2013 bietet keine Unterstützung für die Anpassung von Sprachansagen und Musik für Einwahlkonferenzen.</span><span class="sxs-lookup"><span data-stu-id="b96c8-164">Lync Server 2013 does not support customization of voice prompts and music for dial-in conferencing.</span></span> <span data-ttu-id="b96c8-165">Wenn Sie jedoch eine starke Geschäftsanforderungen haben, die Sie zum Ändern der Standard-Audiodateien benötigen, lesen Sie den Microsoft Knowledge Base-Artikel 961177, [wie Sie Sprachansagen oder Musikdateien für Einwahl-Audiokonferenzen in Microsoft Office Communications Server 2007 R2 anpassen](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span><span class="sxs-lookup"><span data-stu-id="b96c8-165">However, if you have a strong business need that requires you to change the default audio files, see Microsoft Knowledge Base article 961177, [How to customize voice prompts or music files for dial-in audio conferencing in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).</span></span>

<span data-ttu-id="b96c8-166">Sie können auch das [benutzerdefinierte VoIP-Ansagen-Verwaltungsdienstprogramm Microsoft lync Server Conferencing Attendant](http://go.microsoft.com/fwlink/p/?linkid=396880) verwenden, das Administratoren die Möglichkeit bietet, die standardmäßigen Sprachansagen zu ersetzen, die verwendet werden, wenn ein Telefon Anrufer einer lync-Besprechung mit benutzerdefinierten Ansagen Beitritt, um eine andere Besprechungs Eingabe zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="b96c8-166">You can also use the [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) management utility, which enables administrators to replace the default voice prompts used when a phone caller joins a Lync meeting with custom prompts to provide a different meeting entry experience.</span></span> <span data-ttu-id="b96c8-167">Die benutzerdefinierten Sprachansagen können auf einem Server mit lync Server 2010 oder lync Server 2013, entweder Enterprise oder Standard Edition, installiert werden.</span><span class="sxs-lookup"><span data-stu-id="b96c8-167">The custom voice prompts can be installed on a server that is running Lync Server 2010 or Lync Server 2013, either Enterprise or Standard Edition.</span></span>

<span data-ttu-id="b96c8-168">Für Konferenzzentrale und Konferenzankündigungsanwendung gelten die folgenden Anforderungen für die Aufbewahrung von Musik, aufgezeichneten Namen und Audioansage Dateien:</span><span class="sxs-lookup"><span data-stu-id="b96c8-168">Conferencing Attendant application and Conferencing Announcement application have the following requirements for music on hold, recorded name, and audio prompt files:</span></span>

  - <span data-ttu-id="b96c8-169">WMA-Dateiformat (Windows Media Audio)</span><span class="sxs-lookup"><span data-stu-id="b96c8-169">Windows Media Audio (WMA) file format</span></span>

  - <span data-ttu-id="b96c8-170">16-Bit mono</span><span class="sxs-lookup"><span data-stu-id="b96c8-170">16-bit mono</span></span>

  - <span data-ttu-id="b96c8-171">Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe</span><span class="sxs-lookup"><span data-stu-id="b96c8-171">48 kbps 2-pass CBR (constant bit rate)</span></span>

  - <span data-ttu-id="b96c8-172">Sprachpegel: -24 DB</span><span class="sxs-lookup"><span data-stu-id="b96c8-172">Speech level at -24DB</span></span>

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a><span data-ttu-id="b96c8-173">Benutzeranforderungen für Einwahlkonferenzen</span><span class="sxs-lookup"><span data-stu-id="b96c8-173">User Requirements for Dial-In Conferencing</span></span>

<span data-ttu-id="b96c8-174">Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="b96c8-174">Dial-in conferencing users must have a unique phone number or extension assigned to their account.</span></span> <span data-ttu-id="b96c8-175">Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz.</span><span class="sxs-lookup"><span data-stu-id="b96c8-175">This requirement supports authentication during dial-in conferencing.</span></span> <span data-ttu-id="b96c8-176">Enterprise-Benutzer (Benutzer mit Active Directory-Domänendienste Anmeldeinformationen und lync Server Konten in Ihrer Organisation) geben Ihre Telefonnummer (oder Durchwahl) und eine persönliche Identifikationsnummer (PIN) für die Einwahl in Konferenzen als authentifizierter Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b96c8-176">Enterprise users (that is, users who have Active Directory Domain Services credentials and Lync Server accounts within your organization) enter their phone number (or extension) and a personal identification number (PIN) to dial in to conferences as an authenticated user.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

