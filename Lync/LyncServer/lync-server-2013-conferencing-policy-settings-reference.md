---
title: Referenz zu den Konferenzrichtlinieneinstellungen
TOCTitle: Referenz zu den Konferenzrichtlinieneinstellungen
ms:assetid: ec8125f7-ef78-4a2b-8db0-4dd3cf5a4065
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg429724(v=OCS.15)
ms:contentKeyID: 49295804
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Referenz zu den Konferenzrichtlinieneinstellungen

 

_**Letztes Änderungsdatum des Themas:** 2014-04-22_

In den Tabellen des vorliegenden Themas werden alle Konferenzrichtlinieneinstellungen aufgeführt, die Sie mit der Systemsteuerung für Lync Server 2013 angeben können.

## Richtlinieneinstellungen für Organisatoren

In der folgenden Tabelle werden alle Konferenzrichtlinieneinstellungen aufgeführt, die Sie auf Konferenzorganisatoren anwenden können. Die neueste Liste der Konferenzrichtlinieneinstellungen finden Sie im Hilfethema zum Cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).

### Richtlinieneinstellungen für Organisatoren

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Einstellung</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Maximaler Besprechungsumfang</p></td>
<td><p>Legt die maximale Teilnehmeranzahl fest, die in einer Besprechung zulässig ist.</p></td>
</tr>
<tr class="even">
<td><p>Teilnehmer dürfen anonyme Benutzer einladen</p></td>
<td><p>Ermöglicht Besprechungsorganisatoren das Einladen nicht authentifizierter Benutzer zu Besprechungen.</p></td>
</tr>
<tr class="odd">
<td><p>Aufzeichnung aktivieren</p></td>
<td><p>Ermöglicht Referenten oder Teilnehmern das Aufzeichnen der Besprechung.</p></td>
</tr>
<tr class="even">
<td><p>Aufzeichnung durch Partnerteilnehmer und anonyme Teilnehmer zulassen</p></td>
<td><p>Ermöglicht externen und nicht authentifizierten Teilnehmern das Aufzeichnen der Besprechung.</p></td>
</tr>
<tr class="odd">
<td><p>IP-Audio aktivieren</p></td>
<td><p>Ermöglicht die Verwendung von Audio in einer Besprechung.</p></td>
</tr>
<tr class="even">
<td><p>IP-Audio/Video aktivieren</p></td>
<td><p>Ermöglicht die Verwendung von Audio und Video in einer Besprechung.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Einwahlkonferenzen aktivieren</p></td>
<td><p>Ermöglicht Benutzern die Teilnahme an einer Besprechung, indem sie sich über das Telefonfestnetz (Public Switched Telephone Network, PSTN) einwählen.</p></td>
</tr>
<tr class="even">
<td><p>Ausgehende Verbindung für anonyme Teilnehmer zulassen</p></td>
<td><p>Ermöglicht nicht authentifizierten Benutzern die Teilnahme an einer Besprechung über eine ausgehende Verbindung. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Besprechung teilzunehmen.</p></td>
</tr>
<tr class="odd">
<td><p>Maximal zulässige Videoauflösung für Besprechung</p></td>
<td><p>Legt die maximale Auflösung für Videokonferenzen fest. Gültige Werte sind <strong>640*480(VGA)</strong> und <strong>352*288(CIF)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Datenzusammenarbeit aktivieren</p></td>
<td><p>Ermöglicht Konferenzen oder Webkonferenzen mit Datenzusammenarbeit.</p></td>
</tr>
<tr class="odd">
<td><p>Download von Inhalten durch Partnerteilnehmer und anonyme Teilnehmer zulassen</p></td>
<td><p>Ermöglicht externen und nicht authentifizierten Teilnehmern das Herunterladen von Inhalten aus der Besprechung.</p></td>
</tr>
<tr class="even">
<td><p>Übertragen von Dateien durch Teilnehmer zulassen</p></td>
<td><p>Ermöglicht Besprechungsteilnehmern das Übertragen von Dateien während einer Besprechung.</p></td>
</tr>
<tr class="odd">
<td><p>Anmerkungen aktivieren</p></td>
<td><p>Ermöglicht Besprechungsteilnehmern, Anmerkungen in Inhalten zu erstellen.</p></td>
</tr>
<tr class="even">
<td><p>Abstimmungen aktivieren</p></td>
<td><p>Ermöglicht Besprechungsteilnehmern das Durchführen von Abstimmungen während einer Besprechung.</p></td>
</tr>
<tr class="odd">
<td><p>Anwendungsfreigabe aktivieren</p></td>
<td><p>Ermöglicht Benutzern das Planen von Besprechungen, in denen die Anwendungsfreigabe unterstützt wird.</p></td>
</tr>
<tr class="even">
<td><p>Übernahme der Steuerung durch Teilnehmer zulassen</p></td>
<td><p>Ermöglicht es Teilnehmern, die Steuerung der freigegebenen Anwendung eines anderen Benutzers zu übernehmen.</p></td>
</tr>
<tr class="odd">
<td><p>Steuerungsübernahme durch Partnerteilnehmer und anonyme Teilnehmer zulassen</p></td>
<td><p>Ermöglicht es externen und anonymen Teilnehmern, die Steuerung der freigegebenen Anwendung eines anderen Benutzers zu übernehmen.</p>
<div>

> [!NOTE]
> Wenn diese Einstellung aktiviert, die Einstellung <STRONG>Übernahme der Steuerung durch Teilnehmer zulassen</STRONG> jedoch deaktiviert ist, wird diese Einstellung außer Kraft gesetzt.


</div></td>
</tr>
</tbody>
</table>


## Richtlinieneinstellungen für Teilnehmer

In der folgenden Tabelle werden alle Konferenzrichtlinieneinstellungen aufgeführt, die Sie auf Konferenzteilnehmer anwenden können.

### Richtlinieneinstellungen für Teilnehmer

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Einstellung</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anwendungsfreigabe aktivieren</p></td>
<td><p>Ermöglicht Benutzern das Planen von Besprechungen, in denen die Anwendungsfreigabe unterstützt wird.</p></td>
</tr>
<tr class="even">
<td><p>Anwendungs- und Desktopfreigabe aktivieren</p></td>
<td><p>Ermöglicht Benutzern die Teilnahme an Besprechungen, in denen Anwendungsfreigabe und Desktopfreigabe unterstützt werden. In einer Konferenz wird der Wert dieser Einstellung, der für den Organisator der Konferenz gilt, auf alle ebenfalls teilnehmenden anonymen Endpunkte angewendet.</p></td>
</tr>
<tr class="odd">
<td><p>Peer-zu-Peer-Dateiübertragung aktivieren</p></td>
<td><p>Ermöglicht Teilnehmern das Durchführen von Peer-zu-Peer-Dateiübertragungen während einer Besprechung. Eine Peer-zu-Peer-Dateiübertragung betrifft nicht alle Besprechungsteilnehmer.</p></td>
</tr>
<tr class="even">
<td><p>Peer-zu-Peer-Aufzeichnung aktivieren</p></td>
<td><p>Ermöglicht Teilnehmern eine Peer-zu-Peer-Aufzeichnung von Konferenzsitzungen.</p></td>
</tr>
</tbody>
</table>

