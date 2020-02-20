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
ms.openlocfilehash: f3b397e242a6188f9054810a2ce08521a9940717
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Technische Anforderungen für Konferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-06-25_

Für lync Server 2013 werden Einwahlkonferenzen, A/V-Konferenzen, Chat Konferenzen und Webkonferenzfunktionen immer auf Front-End-Servern ausgeführt.

In diesem Abschnitt werden die Hardware- und Softwareanforderungen für diese Server beschrieben, zusammen mit Informationen zur unterstützten gemeinsamen Ausführung.

Das Feature für Einwahlkonferenzen umfasst eine Vielzahl von Komponenten. Einige der Komponenten sind spezifisch für Einwahlkonferenzen und einige sind Enterprise-VoIP-Komponenten. In diesem Abschnitt werden die Anforderungen für diejenigen Komponenten beschrieben, die für das Feature für Einwahlkonferenzen spezifisch sind. Ausführliche Informationen zu Vermittlungsserver-und PSTN-Gateways (Public Switched Telephone Network) finden Sie unter [Vermittlungsserver-Komponente in lync Server 2013](lync-server-2013-mediation-server-component.md) und [Komponenten und Topologien für Vermittlungsserver in lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

<div>

## <a name="hardware-requirements"></a>Hardwareanforderungen

Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server zusammengestellt werden, sind die Server Hardwareanforderungen identisch mit den Front-End-Servern. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Server Hardware Platforms for lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation. Die folgenden Komponenten, die für Einwahlkonferenzen erforderlich sind, weisen auch die gleichen Hardwareanforderungen wie Front-End-Server auf:

  - Anwendungsdienst

  - Konferenzzentrale

  - Konferenzankündigungsanwendung

Die Hardwareanforderungen für Front-End-Server entsprechen denen für viele andere Server Rollen in lync Server 2013, die in der folgenden Tabelle aufgeführt sind.

</div>

<div>

## <a name="software-requirements"></a>Softwareanforderungen

Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server zusammengestellt werden, sind die Server Softwareanforderungen identisch mit den Front-End-Servern. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Für Webkonferenzen erfordert lync Server 2013 auch Office-Webanwendungen und den Office-webapps-Server (ehemals "AS-Server" genannt), um PowerPoint-Präsentationen zu behandeln. Ausführliche Informationen finden Sie unter [Konfigurieren der Integration mit Office-webapps Server und lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Für Einwahlkonferenzen haben Anwendungsdienst, Konferenzzentrale und Konferenzankündigungsanwendung dieselben Betriebssystemanforderungen wie Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Für Konferenzzentrale und Konferenzankündigungsanwendung muss Windows Media Format Runtime auf Front-End-Servern installiert sein. Die Windows Media Format-Laufzeitkomponente ist für die Wiedergabe von WMA-Dateien (Windows Media Audio) erforderlich, die für Wartemusik, aufgezeichnete Namen und Ansagen verwendet werden. Mit Ausnahme von Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format-Laufzeitkomponente beim Ausführen von Setup automatisch als Teil der Windows-Desktop Umgebung installiert, aber möglicherweise müssen Sie den Computer neu starten. Es wird daher empfohlen, die Windows Media Format-Laufzeitkomponente vor Ausführung des Setups als Teil der Windows-Desktoperfahrung zu installieren. Für Windows Server 2012 und Windows Server 2012 R2 ist Microsoft Media Foundation erforderlich.

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>Portanforderungen für Einwahlkonferenzen

In der folgenden Tabelle sind die Ports beschrieben, die von Einwahlkonferenzen verwendet werden. Wenn ein Gerät zum Lastenausgleich verwendet wird, stellen Sie sicher, dass dieses für die Ports konfiguriert ist, die von den im Pool ausgeführten Anwendungen verwendet werden.

Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Ausführliche Informationen zu diesem Cmdlet finden Sie in der lync Server-Verwaltungsshell Dokumentation.

<div>


> [!NOTE]  
> Alle Instanzen derselben Anwendung in einem Pool verwenden denselben SIP-Überwachungsport.



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>Von Einwahlkonferenzen verwendete Ports

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
<td><p>Wird von Konferenzzentrale für SIP-Überwachungsanforderungen verwendet</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>Wird von Konferenzankündigungsanwendung für SIP-Überwachungsanforderungen verwendet</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>Unterstützte Clients für Einwahlkonferenzen

Sie können den folgenden Client zur Planung von lokalen Konferenzen verwenden, die einen Zugriff per Einwahl unterstützen:

  - Online Besprechungs-Add-in für lync 2013 (wird bei der Installation von lync 2013 oder Teilnehmern automatisch installiert)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>Seite "Einstellungen für Einwahlkonferenzen" Anforderungen

Das Seite "Einstellungen für Einwahlkonferenzen" unterstützt die in der folgenden Tabelle beschriebenen Kombinationen aus Betriebssystemen und Webbrowsern.

<div>


> [!NOTE]  
> Es werden 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems unterstützt.



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
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
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
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
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

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>Audiodateianforderungen für Einwahlkonferenzen

Lync Server 2013 bietet keine Unterstützung für die Anpassung von Sprachansagen und Musik für Einwahlkonferenzen. Wenn Sie jedoch eine starke Geschäftsanforderungen haben, die Sie zum Ändern der Standard-Audiodateien benötigen, lesen Sie den Microsoft Knowledge Base-Artikel 961177, [wie Sie Sprachansagen oder Musikdateien für Einwahl-Audiokonferenzen in Microsoft Office Communications Server 2007 R2 anpassen](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Sie können auch das [benutzerdefinierte VoIP-Ansagen-Verwaltungsdienstprogramm Microsoft lync Server Conferencing Attendant](https://go.microsoft.com/fwlink/p/?linkid=396880) verwenden, das Administratoren die Möglichkeit bietet, die standardmäßigen Sprachansagen zu ersetzen, die verwendet werden, wenn ein Telefon Anrufer einer lync-Besprechung mit benutzerdefinierten Ansagen Beitritt, um eine andere Besprechungs Eingabe zu ermöglichen Die benutzerdefinierten Sprachansagen können auf einem Server mit lync Server 2010 oder lync Server 2013, entweder Enterprise oder Standard Edition, installiert werden.

Für Konferenzzentrale und Konferenzankündigungsanwendung gelten die folgenden Anforderungen für die Aufbewahrung von Musik, aufgezeichneten Namen und Audioansage Dateien:

  - WMA-Dateiformat (Windows Media Audio)

  - 16-Bit mono

  - Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

  - Sprachpegel: -24 DB

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Enterprise-Benutzer (Benutzer mit Active Directory-Domänendienste Anmeldeinformationen und lync Server Konten in Ihrer Organisation) geben Ihre Telefonnummer (oder Durchwahl) und eine persönliche Identifikationsnummer (PIN) für die Einwahl in Konferenzen als authentifizierter Benutzer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

