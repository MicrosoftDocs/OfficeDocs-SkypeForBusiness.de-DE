---
title: 'Lync Server 2013: technische Anforderungen für Reaktionsgruppen'
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
ms.openlocfilehash: 8b07ddfa11f23c7e5183c243020c441db7219660
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-response-group-in-lync-server-2013"></a>Technische Voraussetzungen für Reaktionsgruppen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-07_

In diesem Abschnitt werden die folgenden technischen Anforderungen für die Reaktionsgruppenanwendung beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Anforderungen für Audiodateien

  - Anforderungen an das Konfigurationstool für Reaktionsgruppen

<div>

## <a name="hardware-requirements"></a>Hardwareanforderungen

Die Reaktionsgruppenanwendung hat die gleichen Hardwareanforderungen wie Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

</div>

<div>

## <a name="software-requirements"></a>Softwareanforderungen

Das Reaktionsgruppenanwendung hat die gleichen Betriebssystemanforderungen und Softwarevoraussetzungen wie Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Wenn Sie Windows Media-Audiodateien (WMA) für Musik und Ankündigungen von Reaktionsgruppen verwenden, muss für alle Front-End-Server oder Standard Edition-Server, auf denen der Reaktionsgruppenanwendung ausgeführt wird, die Windows Media Format Runtime für Server mit Windows installiert sein. Server 2008 R2 oder Microsoft Media Foundation für Server, auf denen Windows Server 2012 oder Windows Server 2012 R2 ausführt. Für Windows Server 2008 R2 wird Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert.

Ausführliche Informationen zu Audioanforderungen finden Sie unter "Anforderungen an die Audiodateien" weiter unten in diesem Abschnitt.

</div>

<div>

## <a name="port-requirements"></a>Portanforderungen

Der Reaktionsgruppenanwendung verwendet die folgenden Ports:

  - **Port 5071**   wird für SIP-Überwachungsanforderungen verwendet

  - **Port 8404**   wird für die Kommunikation zwischen Servern verwendet
    
    <div>
    

    > [!NOTE]  
    > Dieser Port wird für den Übereinstimmungs Dienst verwendet und ist erforderlich, wenn die Reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.

    
    </div>

<div>


> [!NOTE]  
> Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.



</div>

</div>

<div>

## <a name="audio-file-requirements"></a>Anforderungen für Audiodateien

Das Reaktionsgruppenanwendung unterstützt das Wave-Dateiformat (WAV) und das Windows Media Audio-(WMA-) Dateiformat für Reaktionsgruppen Nachrichten, Wartemusik oder IVR-Fragen (Interactive Voice Response).

Das Windows Media Audiodateiformat erfordert, dass die Windows Media Format-Laufzeitkomponente auf Front-End-Servern installiert ist, auf denen Windows Server 2008 R2 und Windows Server 2008 läuft. Weitere Informationen finden Sie weiter oben in diesem Abschnitt unter "Software Anforderungen".

<div>

## <a name="supported-wave-file-formats"></a>Unterstützte WAV-Dateiformate

Alle Wavedateien müssen die folgenden Anforderungen erfüllen:

  - 8-Bit- oder 16-Bit-Datei

  - LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

  - Mono oder Stereo

  - 4 MB oder weniger

Für eine optimale Leistung bei Wavedateien wird eine Mono-WAV-Datei mit 16 kHz und 16 Bit empfohlen.

</div>

<div>

## <a name="supported-windows-media-audio-file-formats"></a>Unterstützte WMA-Dateiformate

Wenn Sie eine Windows Media Audiodatei verwenden, sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems unter Last überprüfen.

Sie können Microsoft Expression Encoder 4 verwenden, um einen Datei in das WMA-Format zu konvertieren. Informationen zum Herunterladen von Expression Encoder [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkid=202843)4 finden Sie unter.

</div>

</div>

<div>

## <a name="response-group-configuration-tool-requirements"></a>Anforderungen an das Konfigurations Tool für Reaktionsgruppen

Das Reaktionsgruppen-Konfigurations Tool unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.

<div>


> [!NOTE]  
> 32-Bit-oder 64-Bit-Versionen der Betriebssysteme werden unterstützt. Nur 32-Bit-Versionen von Internet Explorer werden unterstützt.



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
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 mit Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="response-group-agent-console"></a>Reaktionsgruppen-Agent-Konsole

Die Agent-Konsole unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.

<div>


> [!NOTE]  
> 32-Bit-oder 64-Bit-Versionen der Betriebssysteme werden unterstützt. Nur 32-Bit-Versionen von Internet Explorer werden unterstützt.



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
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p>
<p>Firefox 10,0</p>
<p>Chrome 18,0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 mit Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p>
<p>Firefox 10,0</p>
<p>Chrome 18,0</p></td>
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

