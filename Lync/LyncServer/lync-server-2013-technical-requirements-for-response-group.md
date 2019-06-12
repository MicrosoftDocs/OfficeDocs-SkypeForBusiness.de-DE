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

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Technische Anforderungen für Reaktionsgruppen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-07_

In diesem Abschnitt werden die folgenden technischen Voraussetzungen für die reaktionsgruppenanwendung beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Audiodatei-Anforderungen

  - Anforderungen für das Konfigurationstool für Reaktionsgruppen

<div>

## <a name="hardware-requirements"></a>Hardware Anforderungen

Die Antwortgruppen Anwendung hat die gleichen Hardwareanforderungen wie Front-End-Server. Details zu den Hardwareanforderungen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung.

</div>

<div>

## <a name="software-requirements"></a>Software Anforderungen

Die reaktionsgruppenanwendung hat dieselben Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

Wenn Sie Windows Media Audio (WMA)-Dateien für die Musik und Ankündigungen von Reaktionsgruppen verwenden, muss für alle Front-End-Server oder Standard Edition-Server, auf denen die reaktionsgruppenanwendung ausgeführt wird, die Windows Media-Format Laufzeit für Server unter Windows installiert sein. Server 2008 R2 oder Microsoft Media Foundation für Server mit Windows Server 2012 oder Windows Server 2012 R2. Für Windows Server 2008 R2 wird die Windows Media-Format Laufzeit als Teil der Windows-Desktop Oberfläche installiert.

Weitere Informationen zu Audioanforderungen finden Sie unter "Anforderungen an die Audiodateien" weiter unten in diesem Abschnitt.

</div>

<div>

## <a name="port-requirements"></a>Portanforderungen

Die Antwortgruppen Anwendung verwendet die folgenden Ports:

  - **Port 5071**   für SIP-Abhör Anforderungen

  - **Port 8404**   , der für die Kommunikation zwischen Servern verwendet wird
    
    <div>
    

    > [!NOTE]  
    > Dieser Port wird für den Übereinstimmungs Dienst verwendet und ist erforderlich, wenn die reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.

    
    </div>

<div>


> [!NOTE]  
> Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können. Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Die Antwortgruppen Anwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-Dateiformat (WMA) für Reaktionsgruppen Nachrichten, Warteschleife-Musik oder IVR-Fragen (Interactive Voice Response).

Das Windows Media-Audiodateiformat setzt voraus, dass die Windows Media-Format Laufzeit auf Front-End-Servern mit Windows Server 2008 R2 und Windows Server 2008 installiert ist. Nähere Informationen dazu finden Sie weiter oben in diesem Abschnitt unter „Softwareanforderungen“.

<div>

## <a name="supported-wave-file-formats"></a>Unterstützte WAV-Dateiformate

WAV-Dateien müssen folgenden Anforderungen entsprechen:

  - 8- oder 16-Bit-Datei

  - LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

  - Mono oder Stereo

  - Maximal 4 MB

Um die beste Leistung zu erzielen, wird eine WAV-Datei mit den Werten 16 kHz, Mono, 16 Bit empfohlen.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Unterstützte WMA-Dateiformate

Bei Verwendung einer WMA-Datei sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems überprüfen, wenn dieses ausgelastet ist.

Sie können Microsoft Expression Encoder 4 verwenden, um eine Datei in das WMA-Format zu konvertieren. Informationen zum Herunterladen von Expression Encoder [http://go.microsoft.com/fwlink/p/?linkId=202843](http://go.microsoft.com/fwlink/p/?linkid=202843)4 finden Sie unter.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Anforderungen des Konfigurationstools für Reaktionsgruppen

Das Reaktionsgruppen-Konfigurations Tool unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.

<div>


> [!NOTE]  
> 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Unterstützte Betriebssysteme und Webbrowser

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Betriebssystem</th>
<th>Webbrowser</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista mit Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 mit Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Agentkonsole für Reaktionsgruppen

Die Agentkonsole unterstützt die in der folgenden Tabelle aufgeführten Kombinationen aus Betriebssystemen und Webbrowsern.

<div>


> [!NOTE]  
> 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>Unterstützte Betriebssysteme und Webbrowser

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Betriebssystem</th>
<th>Webbrowser</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows Vista mit Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 mit Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
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

