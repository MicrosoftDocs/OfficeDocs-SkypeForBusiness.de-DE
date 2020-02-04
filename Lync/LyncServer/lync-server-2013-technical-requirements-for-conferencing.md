---
title: 'Lync Server 2013: Technische Anforderungen für Konferenzen'
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
ms.openlocfilehash: 3a275836b940cfe2c56b184d238bc12c432132e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Technische Anforderungen für Konferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-06-25_

Für lync Server 2013 können Einwahlkonferenzen, A/V-Konferenzen, Sofortnachrichten (im)-Konferenzen und Webkonferenzfunktionen immer auf Front-End-Servern ausgeführt werden.

In diesem Abschnitt werden die Hardware-und Softwareanforderungen für diese Server sowie die unterstützte Zusammensetzung erläutert.

Einwahlkonferenzen sind eine Funktion, die eine Vielzahl von Komponenten umfasst. Einige der Komponenten gelten speziell für Einwahlkonferenzen und einige sind Enterprise-VoIP-Komponenten. In diesem Abschnitt werden die Anforderungen für die Komponenten beschrieben, die für Einwahlkonferenzen spezifisch sind. Details zu den Anforderungen des Vermittlungsservers und des PSTN-Gateways (Public Switched Telephone Network) finden Sie in der Planning-Dokumentation unter [Mediation Server-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md) und [Komponenten und Topologien für Mediation Server in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) .

<div>

## <a name="hardware-requirements"></a>Hardware Anforderungen

Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server kombiniert werden, sind die Server Hardwareanforderungen identisch mit den Front-End-Servern. Details zu den Hardwareanforderungen finden Sie unter [Server Hardwareplattformen für lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Dokumentation zur Unterstützung. Die folgenden für Einwahlkonferenzen erforderlichen Komponenten haben auch die gleichen Hardwareanforderungen wie Front-End-Server:

  - Anwendungsdienst

  - Konferenzzentrale

  - Konferenzankündigungsanwendung

Die Hardwareanforderungen für den Front-End-Server entsprechen denen für viele andere Serverrollen in lync Server 2013, die in der folgenden Tabelle beschrieben sind.

</div>

<div>

## <a name="software-requirements"></a>Software Anforderungen

Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server kombiniert werden, sind die Server Softwareanforderungen identisch mit den Front-End-Servern. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

Für Webkonferenzen erfordert lync Server 2013 auch Office Web Apps und den Office Web Apps-Server (vormals als "The-Server" bezeichnet), um PowerPoint-Präsentationen zu verarbeiten. Ausführliche Informationen finden Sie unter [Konfigurieren der Integration in Office Web Apps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Für Einwahlkonferenzen, Anwendungsdienst, Konferenz Aufsichts Anwendung und Konferenz Ankündigungs Anwendung gelten dieselben Betriebssystemanforderungen wie für Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.

Die Anwendung für die Conferencing Attendant-Anwendung und die Konferenzankündigung erfordern, dass Windows Media Format Runtime auf Front-End-Servern installiert ist. Die Windows Media-Format Laufzeit ist erforderlich, um WMA-Dateien (Windows Media Audio) wiederzugeben, die für Musik in Wartestellung, aufgezeichnete Namen und Eingabeaufforderungen verwendet werden. Mit Ausnahme von Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media-Format Laufzeit automatisch als Teil der Windows-Desktop Umgebung installiert, wenn Sie Setup ausführen, aber möglicherweise müssen Sie den Computer neu starten. Daher empfiehlt es sich, die Installation als Teil der Windows-Desktop Umgebung zu installieren, die Windows Media Format Runtime umfasst, bevor Sie Setup ausführen. Für Windows Server 2012 und Windows Server 2012 R2 ist Microsoft Media Foundation erforderlich.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Port Anforderungen für Einwahlkonferenzen

In der folgenden Tabelle werden die Ports beschrieben, die von Einwahlkonferenzen verwendet werden. Wenn Sie ein Lastenausgleichsmodul verwenden, stellen Sie sicher, dass das Load Balancer für die Ports konfiguriert ist, die von allen Anwendungen verwendet werden, die im Pool ausgeführt werden.

Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Details zu diesem Cmdlet finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

<div>


> [!NOTE]  
> Alle Instanzen der gleichen Anwendung in einem Pool verwenden denselben SIP-Abhör-Port.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Ports, die von Einwahlkonferenzen verwendet werden

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Portnummer</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>Wird von der Konferenz Aufsichts Anwendung für SIP-Überwachungsanforderungen verwendet</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Wird von der Konferenz Ankündigungs Anwendung für SIP-Überwachungsanforderungen verwendet</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Unterstützte Clients für Einwahlkonferenzen

Sie können den folgenden Client verwenden, um lokale Konferenzen zu planen, die Einwahlzugriff unterstützen:

  - Online Besprechungs-Add-in für lync 2013 (automatisch installiert, wenn Sie lync 2013 oder Teilnehmer installieren)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Einstellungen für Einwahlkonferenzen, Seitenanforderungen

Auf der Seite Einstellungen für Einwahlkonferenzen werden die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern unterstützt.

<div>


> [!NOTE]  
> 32-Bit-und 64-Bit-Versionen der Betriebssysteme werden unterstützt.



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
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
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
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Audio-Dateianforderungen für Einwahlkonferenzen

Lync Server 2013 unterstützt keine Anpassung von Sprachansagen und Musik für Einwahlkonferenzen. Wenn Sie jedoch eine starke geschäftliche Anforderung haben, die erfordert, dass Sie die standardmäßigen Audiodateien ändern, lesen Sie den Microsoft Knowledge Base-Artikel 961177, [Anleitung zum Anpassen von Sprachansagen oder Musikdateien für Einwahlkonferenzen in Microsoft Office Communications Server 2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Sie können auch das Verwaltungsdienstprogramm für [benutzerdefinierte Sprachansagen der Microsoft lync Server-Konferenzzentrale](http://go.microsoft.com/fwlink/p/?linkid=396880) verwenden, das es Administratoren ermöglicht, die standardmäßigen Sprachaufforderungen zu ersetzen, die verwendet werden, wenn ein Telefon Anrufer eine lync-Besprechung mit benutzerdefinierten Ansagen annimmt, um eine andere Besprechungs Eingabe zu ermöglichen Die benutzerdefinierten Sprachansagen können auf einem Server mit lync Server 2010 oder lync Server 2013, entweder Enterprise oder Standard Edition, installiert werden.

Anwendung für die Conferencing Attendant-Anwendung und Konferenzankündigung gelten für die folgenden Voraussetzungen für Musik in Wartestellung, aufgezeichnete Namen und Audio-Ansagedateien:

  - WMA-Dateiformat (Windows Media Audio)

  - 16-Bit mono

  - Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

  - Sprachpegel: -24 dB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Enterprise-Benutzer (also Benutzer mit Anmeldeinformationen für Active Directory-Domänendienste und lync-Server Konten in Ihrer Organisation) geben Ihre Telefonnummer (oder Durchwahl) und eine persönliche Identifikationsnummer (PIN) ein, um sich in Konferenzen als authentifizierter Benutzer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

