---
title: 'Lync Server 2013: Technische Anforderungen für Reaktionsgruppen'
TOCTitle: Technische Anforderungen für Reaktionsgruppen
ms:assetid: 477488bd-124f-437b-9327-732a0d7271ca
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204863(v=OCS.15)
ms:contentKeyID: 49293875
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Technische Anforderungen für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In diesem Abschnitt werden die folgenden technischen Anforderungen für die Reaktionsgruppenanwendung beschrieben:

  - Hardwareanforderungen

  - Softwareanforderungen

  - Portanforderungen

  - Anforderungen für Audiodateien

  - Anforderungen des Konfigurationstools für Reaktionsgruppe

## Hardwareanforderungen

Für die Reaktionsgruppenanwendung gelten die gleichen Hardwareanforderungen wie für den Front-End-Server. Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter [Serverhardwareplattformen für Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in der Unterstützungsdokumentation.

## Softwareanforderungen

Für die Reaktionsgruppenanwendung gelten die gleichen Anforderungen hinsichtlich Betriebssystem und erforderliche Komponenten wie für Front-End-Server. Ausführliche Informationen zu den Softwareanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.

Wenn Sie WMA (Windows Media Audio)-Dateien für Musik und Ansagen von Reaktionsgruppe verwenden, müssen alle Front-End-Server- oder alle Standard Edition-Server mit der Reaktionsgruppenanwendung die Windows Media Format-Laufzeitkomponente für Server mit Windows Server 2008 R2 installiert haben. Bei Servern mit Windows Server 2012 oder Windows Server 2012 R2 muss Microsoft Media Foundation installiert sein. Die Windows Media Format-Laufzeitkomponente für Windows Server 2008 R2 wird im Rahmen der Windows Desktop Experience installiert.

Nähere Informationen zu den Audioanforderungen finden Sie weiter unten in diesem Abschnitt unter "Audiodateianforderungen".

## Portanforderungen

Reaktionsgruppenanwendung verwendet die folgenden Ports:

  - **Port 5071**   Wird für SIP-Überwachungsanforderungen verwendet

  - **Port 8404**   Dieser Port wird für die Kommunikation zwischen Servern verwendet.
    

    > [!NOTE]
    > Dieser Port wird für den Matchmakingdienst verwendet und ist erforderlich, wenn die Reaktionsgruppenanwendung in einem Pool mit mehr als einem Front-End-Server bereitgestellt wird.




> [!NOTE]
> Diese Ports sind Standardeinstellungen, die Sie mit dem Cmdlet <STRONG>Set-CsApplicationServer</STRONG> ändern können. Weitere Informationen zu diesem Cmdlet finden Sie in der Dokumentation zu Lync Server-Verwaltungsshell.



## Anforderungen für Audiodateien

Die Reaktionsgruppenanwendung unterstützt das WAV- (Wave) und das WMA-Dateiformat (Windows Media Audio) für Reaktionsgruppennachrichten, Wartemusik oder interaktive Sprachantworten.

Das Windows Media-Audiodateiformat erfordert die Installation der Windows Media Format-Laufzeitkomponente auf den Front-End-Server mit Windows Server 2008 R2 und Windows Server 2008. Nähere Informationen dazu finden Sie weiter oben in diesem Thema unter "Softwareanforderungen".

## Unterstützte WAV-Dateiformate

WAV-Dateien müssen folgenden Anforderungen entsprechen:

  - 8- oder 16-Bit-Datei

  - LPCM- (Linear Pulse Code Modulation), A-Law- oder µ-Law-Format

  - Mono oder Stereo

  - Maximal 4 MB

Um die beste Leistung zu erzielen, wird eine WAV-Datei mit den Werten 16 kHz, Mono, 16 Bit empfohlen.

## Unterstützte WMA-Dateiformate

Bei Verwendung einer WMA-Datei sollten Sie niedrige Bitraten verwenden und die Leistung Ihres Systems überprüfen, wenn dieses ausgelastet ist.

Sie können Microsoft Expression Encoder 4 verwenden, um eine Datei in das WMA-Format zu konvertieren. Expression Encoder 4 kann unter der folgenden Adresse heruntergeladen werden: [http://go.microsoft.com/fwlink/?linkid=202843\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=202843%26clcid=0x407).

## Anforderungen des Konfigurationstools für Reaktionsgruppen

Das Konfigurationstool für Reaktionsgruppen unterstützt die in der nachstehenden Tabelle aufgeführten Kombinationen aus Betriebssystemen und Webbrowsern.


> [!NOTE]
> 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.



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
<td><p>Windows Vista mit Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 mit Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p></p>
<p></p>
<p></p>
<p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
</tbody>
</table>


## Agentkonsole für Reaktionsgruppe

Die Agentkonsole unterstützt die in der folgenden Tabelle aufgeführten Kombinationen aus Betriebssystemen und Webbrowsern.


> [!NOTE]
> 32-Bit- und 64-Bit-Versionen des jeweiligen Betriebssystems werden unterstützt. Für Internet Explorer werden nur 32-Bit-Versionen unterstützt.



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
<td><p>Windows Vista mit Service Pack (SP) 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows 7</p>
<p>Windows 7 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p>Windows Server 2008 mit Service Pack 2</p></td>
<td><p>Internet Explorer 7</p>
<p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p></td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p>
<p>Windows Server 2008 R2 mit Service Pack 1</p></td>
<td><p>Internet Explorer 8 (einheitlicher Modus)</p>
<p>Internet Explorer 9 (einheitlicher Modus)</p>
<p>Firefox 10.0</p>
<p>Chrome 18.0</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td></td>
</tr>
</tbody>
</table>

