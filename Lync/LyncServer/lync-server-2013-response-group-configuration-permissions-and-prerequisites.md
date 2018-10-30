---
title: 'Lync Server 2013: Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen'
TOCTitle: Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204840(v=OCS.15)
ms:contentKeyID: 49293822
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Berechtigungen und Voraussetzungen für die Konfiguration von Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Reaktionsgruppe ist eine Enterprise-VoIP-Funktion für die Anrufverwaltung. In diesem Thema werden die Voraussetzungen für die Konfiguration von Reaktionsgruppe und die Administratoranmeldeinformationen und -berechtigungen zur Ausführung von Konfigurationsaufgaben beschrieben.

In diesem Abschnitt wird davon ausgegangen, dass Sie die für Reaktionsgruppe relevanten Abschnitte in der Planungsdokumentation gelesen haben. Ausführliche Informationen finden Sie unter [Planen der Anrufverwaltungsfunktionen in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) in der Planungsdokumentation.

## Konfigurationstools und Administratorrollen

Sie können Reaktionsgruppe mithilfe der folgenden Verwaltungstools konfigurieren:

  - Lync Server-Systemsteuerung

  - Konfigurationstool für Reaktionsgruppen

  - Lync Server-Verwaltungsshell

Für die Konfiguration von Reaktionsgruppen müssen Sie über mindestens eine der folgenden Administratorrollen verfügen:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Active Directory-Sicherheitsgruppe (1)</strong></p></td>
<td><p>Erstellen eines Workflows</p></td>
<td><p>Zuweisen eines Managers</p></td>
<td><p>Erstellen/Zuweisen von Agents und Warteschlangen</p></td>
<td><p>Erstellen/Verwalten von Feiertagen und Geschäftszeiten</p></td>
<td><p>Workflow aktivieren/deaktivieren</p></td>
<td><p>Workflow konfigurieren (IVR-Gruppe oder Sammelanschlüsse)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>v(2)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
<td><p>v(3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
<td><p>v</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
<td><p>v(4)</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <STRONG>(1)</STRONG> Ein Active Directory-Domänendienste-Benutzerobjekt muss Mitglied der spezifischen angegebenen Active Directory-Sicherheitsgruppe sein. Ein Administrator oder ein anderes delegiertes Mitglied der Active Directory-Gruppe mit entsprechenden Berechtigungen zum Hinzufügen von Benutzern zu einer Sicherheitsgruppe (beispielsweise Administratoren, Kontenoperatoren) muss ein Benutzerobjekt zur aufgeführten Gruppe oder Sicherheitsgruppe hinzufügen, damit der Benutzer die aufgeführten Funktionen nutzen kann. <STRONG>(2)</STRONG> Nur für Workflows, die der CsResponseGroupAdministrator dem CsResponseGroupManager zugewiesen hat. <STRONG>(3)</STRONG> Ein Reaktionsgruppe-Manager kann ein anderes Mitglied des CsResponseGroupManagers einem Workflow zuweisen, den der aktuelle Manager bereits verwaltet. <STRONG>(4)</STRONG> Der CsViewOnlyAdministrator kann nur Lync Server-Verwaltungsshell-Cmdlets mit der Zeichenfolge "Get" ausführen.



## Konfigurationsvoraussetzungen für Reaktionsgruppe

Für Reaktionsgruppe sind folgende Komponenten erforderlich:

  - Anwendungsdienst

  - Reaktionsgruppenanwendung

  - Sprachpakete

  - Dateispeicher (für Audiodateien)

  - Webdienste (diese umfassen das Konfigurationstool für Reaktionsgruppen sowie die Konsole zur An- und Abmeldung von Agents)

All diese Komponenten werden bei der Bereitstellung von Enterprise-VoIP standardmäßig installiert.

Vor der Konfiguration von Reaktionsgruppe müssen Sie möglicherweise die folgenden Aufgaben ausführen:

  - Aktivieren von Benutzern für Lync Server 2013 und Enterprise-VoIP.

  - Ändern einer Konfigurationsdatei für FIPS-Konformität (Federal Information Processing Standards).

  - Ändern der Datenbanksortierung für die Unterstützung von Yi-, Meng- und Zang-Zeichen für Warteschleifen- und Agentgruppennamen.

## Aktivieren von Benutzern

Der erste Schritt bei der Konfiguration von Reaktionsgruppe ist das Erstellen von Agentgruppen. Bevor Sie eine Agentgruppe erstellen können, müssen Sie die Benutzer aktivieren, die als Agents für Reaktionsgruppe für Lync Server 2013 und Enterprise-VoIP vorgesehen sind. Das Aktivieren von Benutzern für Lync Server 2013 ist typischerweise ein Schritt, der bei der Bereitstellung eines Enterprise Edition- oder Standard Edition-Servers ausgeführt wird. Ausführliche Informationen zum Aktivieren von Benutzern für Lync Server 2013 finden Sie unter [Aktivieren oder Reaktivieren von Benutzerkonten für Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Das Aktivieren von Benutzern für Enterprise-VoIP ist im Allgemeinen ein Schritt, der bei der Bereitstellung von Enterprise-VoIP ausgeführt wird. Ausführliche Informationen hierzu finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

## Erfüllen von FIPS-Anforderungen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation FIPS-Konformität (Federal Information Processing Standards) sicherstellen muss.

Zur Einhaltung von FIPS müssen Sie die Datei "Web.config" auf Anwendungsebene nach der Installation der Webdienste ändern, um einen anderen Kryptografiealgorithmus zu verwenden. Sie müssen angeben, dass ASP.NET zur Verarbeitung von Anzeigestatusdaten den 3DES-Algorithmus (Triple Data Encryption Standard) verwendet. Für die Reaktionsgruppenanwendung gilt diese Anforderung für das Konfigurationstool für Reaktionsgruppen und die Konsole zur An- und Abmeldung von Agents. Ausführliche Informationen zu dieser Anforderung finden Sie im Microsoft Knowledge Base-Artikel 911722, "Möglicherweise wird eine Fehlermeldung angezeigt, wenn Sie nach dem Upgrade von ASP.NET 1.1 auf ASP.NET 2.0 auf für ViewState aktivierte ASP.NET-Webseiten zugreifen" unter <http://go.microsoft.com/fwlink/?linkid=196183>.

Führen Sie zum Ändern der Datei "Web.config" die folgenden Schritte aus:

1.  Öffnen Sie in einem Text-Editor (z. B. Editor) die Datei "Web.config" auf Anwendungsebene.

2.  Wechseln Sie in der Datei "Web.config" zum Abschnitt `<system.web>`.

3.  Fügen Sie den folgenden Abschnitt `<machineKey>` zum Abschnitt `<system.web>` hinzu:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Speichern Sie die Datei "Web.config".

5.  Starten Sie den Internetinformationsdienste (Internet Information Services, IIS)-Dienst über den folgenden Befehl an einer Eingabeaufforderung neu:
    
        iisreset

## Unterstützen von Yi-, Meng- und Zang-Zeichen

Dieser Abschnitt ist nur relevant, wenn Ihre Organisation Yi-, Meng- oder Zang-Zeichen unterstützen muss.


> [!NOTE]
> Weitere Informationen zu Yi-, Meng- und Zang-Zeichen sowie zu ihrer möglichen Bedeutung für Ihre Bereitstellung finden Sie in den Informationen zu den GB18030-Zeichensätzen unter <A class=uri href="http://go.microsoft.com/fwlink/?linkid=240223">http://go.microsoft.com/fwlink/?linkid=240223</A>.



Um Yi-, Meng- oder Zang-Zeichen zu unterstützen, müssen Sie die Sortierung für die Rgsconfig-Datenbank ändern. Ändern Sie die Sortierung der Spalte **Name** in den folgenden Tabellen der einzelnen Rgsconfig-Datenbanken:

  - dbo.AgentGroups

  - dbo.BusinessHours

  - dbo.HolidaySets

  - dbo.Queues

  - dbo.Workflows

Verwenden Sie für SQL Server 2008 R2 und SQL Server 2012 die Sortierung "Latin\_General\_100" (Beachtung von Akzenten). Bei Verwendung dieser Sortierung wird die Groß-/Kleinschreibung bei Objektnamen nicht beachtet.

Die Sortierung kann über Microsoft SQL Server Management Studio geändert werden. Ausführliche Informationen zur Verwendung dieses Tools finden Sie unter "Verwenden von SQL Server Management Studio" unter <http://go.microsoft.com/fwlink/?linkid=196184>. Führen Sie die folgenden Schritte aus, um die Sortierung zu ändern:

1.  Stellen Sie sicher, dass SQL Server Management Studio zum Zulassen von Änderungen konfiguriert ist, für die Tabellen neu erstellt werden müssen. Ausführliche Informationen finden Sie unter "Dialogfeld 'Speichern (nicht zulässig)'" unter <http://go.microsoft.com/fwlink/?linkid=196186>. Ausführliche Informationen zum Festlegen einer Spaltensortierung finden Sie unter "Vorgehensweise: Festlegen der Spaltensortierreihenfolge (Visual Database Tools)" unter <http://go.microsoft.com/fwlink/?linkid=196185>.

2.  Stellen Sie unter Verwendung von Microsoft SQL Server Management Studio eine Verbindung mit der Rgsconfig-Datenbank her.

3.  Wechseln Sie in der Rgsconfig-Datenbank zu der Tabelle, die geändert werden soll, klicken Sie mit der rechten Maustaste auf die Tabelle, und klicken Sie auf **Entwerfen** .

4.  Ändern Sie die Sortierung der Spalte **Name** , und speichern Sie die Tabelle.

