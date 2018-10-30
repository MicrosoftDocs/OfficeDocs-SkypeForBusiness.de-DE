---
title: 'Lync Server 2013: Technische Anforderungen für Konferenzen'
TOCTitle: Technische Anforderungen für Konferenzen
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425889(v=OCS.15)
ms:contentKeyID: 49293741
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Für Lync Server 2013 werden Funktionen für Einwahlkonferenz, A/V-Konferenz, Chatkonferenz und Webkonferenz immer auf Front-End-Servern ausgeführt.

In diesem Abschnitt werden die Hardware- und Softwareanforderungen für diese Server beschrieben, zusammen mit Informationen zur unterstützten gemeinsamen Ausführung.

Das Feature für Einwahlkonferenzen umfasst eine Vielzahl von Komponenten. Einige dieser Komponenten sind spezifisch für das Feature für Einwahlkonferenzen, andere sind Enterprise-VoIP-Komponenten. In diesem Abschnitt werden die Anforderungen für diejenigen Komponenten beschrieben, die für das Feature für Einwahlkonferenzen spezifisch sind. Ausführliche Informationen zu den Anforderungen für Vermittlungsserver und PSTN-Gateways finden Sie unter [Vermittlungsserverkomponente in Lync Server 2013](lync-server-2013-mediation-server-component.md) und [Komponenten und Topologien für den Vermittlungsserver in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in der Planungsdokumentation.

## Hardwareanforderungen

Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server verbunden sind, sind die Serverhardwareanforderungen dieselben wie für die Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation. Für die folgenden Komponenten, die für Einwahlkonferenzen erforderlich sind, gelten auch dieselben Hardwareanforderungen wie für Front-End-Server:

  - Anwendungsdienst

  - Konferenzzentrale

  - Konferenzankündigungsanwendung

Die in der folgenden Tabelle aufgelisteten Hardwareanforderungen für Front-End-Server sind dieselben wie für viele weitere Serverrollen in Lync Server 2013.

## Softwareanforderungen

Da Webkonferenzen und A/V-Konferenzen mit dem Front-End-Server verbunden sind, sind die Serversoftwareanforderungen dieselben wie für die Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Für Webkonferenzen sind für Lync Server 2013 zudem Office Web Apps und Office Web Apps-Server (früher als WAC-Server bezeichnet) erforderlich, um PowerPoint-Präsentationen zu behandeln. Ausführliche Informationen finden Sie unter [Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

Für Einwahlkonferenzen gelten für Anwendungsdienst, Konferenzzentrale und Konferenzankündigungsanwendung dieselben Betriebssystemanforderungen wie für Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Für die Konferenzzentrale und die Konferenzankündigungsanwendung muss die Windows Media Format-Laufzeitkomponente auf den Front-End-Servern installiert sein. Die Windows Media Format-Laufzeitkomponente ist für die Wiedergabe von WMA-Dateien (Windows Media Audio) erforderlich, die für Wartemusik, aufgezeichnete Namen und Ansagen verwendet werden. Außer bei Windows Server 2012 und bei Windows Server 2012 R2 wird die Windows Media Format-Laufzeitkomponente automatisch als Teil der Windows-Desktoperfahrung installiert, wenn Sie Setup ausführen, aber möglicherweise müssen Sie den Computer neu starten. Es wird daher empfohlen, die Windows Media Format-Laufzeitkomponente vor Ausführung des Setups als Teil der Windows-Desktoperfahrung zu installieren. Windows Server 2012 und Windows Server 2012 R2 erfordern Microsoft Media Foundation.

## Portanforderungen für Einwahlkonferenzen

In der folgenden Tabelle sind die Ports beschrieben, die von Einwahlkonferenzen verwendet werden. Wenn ein Gerät zum Lastenausgleich verwendet wird, stellen Sie sicher, dass dieses für die Ports konfiguriert ist, die von den im Pool ausgeführten Anwendungen verwendet werden.

Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet **Set-CsApplicationServer** ändern können. Weitere Informationen zu diesem Cmdlet finden Sie in der Dokumentation zu Lync Server-Verwaltungsshell.


> [!NOTE]
> Alle Instanzen derselben Anwendung in einem Pool verwenden denselben SIP-Überwachungsport.



### Von Einwahlkonferenzen verwendete Ports

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


## Unterstützte Clients für Einwahlkonferenzen

Sie können den folgenden Client zur Planung von lokalen Konferenzen verwenden, die einen Zugriff per Einwahl unterstützen:

  - Onlinebesprechungs-Add-In für Lync 2013 (wird bei der Installation von Lync 2013 oder Teilnehmer automatisch installiert)

## Seite "Einstellungen für Einwahlkonferenz"-Anforderungen

Das Seite "Einstellungen für Einwahlkonferenz" unterstützt die in der nachstehenden Tabelle aufgeführten Kombinationen aus Betriebssystemen und Webbrowsern.


> [!NOTE]
> Es werden 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems unterstützt.



### Unterstützte Betriebssysteme und Webbrowser

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
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


## Audiodateianforderungen für Einwahlkonferenzen

Lync Server 2013 unterstützt keine Anpassung von Ansagen und Musik für Einwahlkonferenzen. Wenn Sie die Standardaudiodateien jedoch aufgrund geschäftlicher Anforderungen ändern müssen, finden Sie Informationen hierzu im Microsoft Knowledge Base-Artikel 961177, ["Anpassen von Ansagen oder Musikdateien für Einwahlkonferenzen in Microsoft Office Communications Server 2007 R2"](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177).

Sie können auch das Verwaltungsdienstprogramm [Microsoft Lync Server Conferencing Attendant Custom Voice Prompts](http://go.microsoft.com/fwlink/p/?linkid=396880) verwenden. Mit ihm können Administratoren die Standardsprachansagen, die erfolgen, wenn ein Anrufer an einer Lync-Konferenz teilnimmt, durch eigene Sprachansagen ersetzen, um das Benutzererlebnis individuell zu gestalten. Die benutzerdefinierten Sprachansagen können auf einem Server installiert werden, auf dem Lync Server 2010 oder Lync Server 2013 entweder in der Enterprise oder Standard Edition ausgeführt wird.

Für Konferenzzentrale und Konferenzankündigungsanwendung gelten die folgenden Anforderungen in Bezug auf Wartemusik, aufgezeichnete Namen und Dateien mit Audioansagen:

  - WMA-Dateiformat (Windows Media Audio)

  - 16-Bit mono

  - Konstante Bitrate (Constant Bit Rate), 48 KBit/s, 2 Durchläufe

  - Sprachpegel: -24 DB

## Benutzeranforderungen für Einwahlkonferenzen

Dem Konto eines Einwahlkonferenzbenutzers muss eine eindeutige Rufnummer oder Durchwahl zugewiesen sein. Diese Anforderung unterstützt die Authentifizierung während der Einwahlkonferenz. Unternehmensbenutzer (also diejenigen Benutzer, die in Ihrer Organisation über Anmeldeinformationen in Active Directory-Domänendienste sowie Lync Server-Konten verfügen) geben ihre Rufnummer (oder Durchwahl) und eine persönliche Identifikationsnummer (PIN) ein, um sich als authentifizierte Benutzer in Konferenzen einzuwählen.

