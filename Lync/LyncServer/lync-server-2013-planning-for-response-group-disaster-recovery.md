---
title: 'Lync Server 2013: Planen der Notfallwiederherstellung für Reaktionsgruppen'
TOCTitle: Planen der Notfallwiederherstellung für Reaktionsgruppen
ms:assetid: 14e0f5dc-77cd-42cd-a9c9-4d0da38fb1cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204699(v=OCS.15)
ms:contentKeyID: 49293266
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planen der Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In diesem Abschnitt werden einige Methoden zum Vorbereiten von Reaktionsgruppen auf die Notfallwiederherstellung beschrieben. Außerdem enthält er eine Übersicht über den Notfallwiederherstellungsprozess.

## Vorbereiten der Anwendung zum Reaktionsgruppe für die Notfallwiederherstellung

Beachten Sie beim Vorbereiten und Ausführen von Notfallwiederherstellungsverfahren Folgendes.


> [!NOTE]
> In einer Koexistenzumgebung werden nur die Lync Server 2013-Reaktionsgruppen für die in diesem Dokument beschriebenen Verfahren zur Notfallwiederherstellung unterstützt.



  - Planen Sie die Notfallwiederherstellung gleichzeitig mit der Kapazitätsplanung. Für die Notfallwiederherstellungskapazität sollte jeder Pool in einem Poolpaar die Arbeitsauslastung aller Reaktionsgruppen in beiden Pools bewältigen können. Nähere Informationen zur Kapazitätsplanung für Reaktionsgruppen finden Sie unter [Kapazitätsplanung für Reaktionsgruppen in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md).

  - Erstellen Sie regelmäßig Sicherheitskopien aller Reaktionsgruppenkonfigurationen in allen Front-End-Pools, in denen Sie die Reaktionsgruppenanwendung bereitgestellt haben; wenden Sie dazu das in diesem Dokument beschriebene Verfahren an. Nähere Informationen finden Sie unter [Verfahren für die Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md). Bewahren Sie die Sicherungskopien an einem sicheren Ort auf.

  - Erstellen Sie eine separate Sicherungskopie aller originalen Audiodateien, die Sie für die Reaktionsgruppenanwendung Anwendung verwendet haben, einschließlich Aufnahmen und Wartemusikdateien. Bewahren Sie die Sicherungsdateien an einem sicheren Ort auf.

  - Für die Lync Server 2013-Notfallwiederherstellung müssen alle Reaktionsgruppeneinstellungen in der gesamten Bereitstellung eindeutige Namen haben. Diese Anforderung gilt für Workflows, Warteschlangen, Agentgruppen, Feiertagssätze und Geschäftszeiten. Überprüfen Sie, ob diese Anforderung erfüllt ist, wenn die primären Pools und Sicherungspools aktiv sind, bevor Sie ein Failoververfahren einleiten müssen. Wenn beim Importieren von Reaktionsgruppendaten in den Sicherungspool Namenskonflikte auftreten, schlägt der Import fehl. Zum Abschließen des Imports und des Failoververfahrens müssen Sie die Namenskonflikte lösen, indem Sie das Reaktionsgruppenobjekt im Sicherungspool ändern oder das Cmdlet **Import-CsRgsConfiguration** mit dem Parameter "-ResolveNameConflicts" ausführen, um den Konflikt automatisch zu lösen, indem eine eindeutige Identifikationsnummer an das Reaktionsgruppenobjekt angehängt wird.

  - Im Allgemeinen wird empfohlen, täglich eine Sicherung anzulegen. Wenn jedoch große Mengen von Daten innerhalb einer kurzen Zeit geändert werden, sollten Sie häufigere Sicherungen ansetzen. Die Menge an Informationen, die bei einem Notfall verloren gehen kann, hängt von der Häufigkeit Ihrer Sicherungen sowie von der Häufigkeit und Menge der Änderungen ab.

  - Das Importieren von Reaktionsgruppen in einen Sicherungspool vor dem Ausführen eines Notfallwiederherstellungs- oder Failoververfahrens ist möglich. Das Importieren von Reaktionsgruppen im Voraus reduziert die Downtime, da der Lync Server-Reaktionsgruppendienst im Sicherungspool wiederhergestellt werden kann, sobald Anrufe an den Sicherungspool weitergeleitet werden.
    

    > [!NOTE]
    > Die Reaktionsgruppenanwendung kann keine Agents erreichen, die in einem inaktiven Pool verwaltet werden, bis das Failover abgeschlossen ist. Währenddessen bearbeitet die Reaktionsgruppenanwendung Anrufe wie bei einer Nichtverfügbarkeit dieser Agents.



## Notfallwiederherstellungsprozess für Reaktionsgruppen

In einem Notfall können Sie Reaktionsgruppen mit einer der folgenden Methoden wiederherstellen:

  - Ausführen eines Failovers zu einem Sicherungspool und eines Failbacks zum ursprünglichen Pool.

  - Ausführen eines Failovers zu einem Sicherungspool, Erstellen eines neuen Pools mit einem anderen vollqualifizierten Domänennamen (FQDN) und anschließendes Importieren der Reaktionsgruppen in den neuen Pool.

Während der Failoverphase der Notfallwiederherstellung befinden sich die Reaktionsgruppen in mehreren Pools: im (nicht verfügbaren) primären Pool und im Sicherungspool. Die Reaktionsgruppen in den beiden Pools haben denselben Namen und denselben Besitzer (den primären Pool), sie haben jedoch unterschiedliche übergeordnete Elemente.

Wenn Sie die Wiederherstellung durch das Erstellen eines neuen Pools mit einem anderen FQDN durchführen, müssen Sie den neuen Pool als Besitzer der Reaktionsgruppen zuordnen, wenn Sie diese importieren. Der Besitz von Reaktionsgruppen verbleibt beim ursprünglichen Pool, außer Sie ordnen den Besitz explizit neu zu, indem Sie das Cmdlet **Import-CsRgsConfiguration** mit dem Parameter "-OverwriteOwner" ausführen.


> [!NOTE]
> Sie müssen den Parameter "-OverwriteOwner" auch dann verwenden, wenn Sie den Pool während des Wiederherstellungsvorgangs neu erstellt haben (d.&nbsp;h. die Reaktionsgruppe-Datenbank ist leer), unabhängig davon, ob Sie denselben FQDN verwenden. Wenn Sie den Pool nicht neu erstellt haben, müssen Sie den Parameter "-OverwriteOwner" nicht verwenden, die Verwendung dieses Parameters ist jedoch zulässig, wenn Sie Reaktionsgruppen in den ursprünglichen Pool zurückimportieren.



Sie können nur einen Satz von Reaktionsgruppen-Konfigurationseinstellungen auf Anwendungsebene definieren. Diese Einstellungen umfassen die Standardkonfiguration für Wartemusik, die Standardaudiodatei für Wartemusik, die Kulanzfrist für Agentrückrufe und die Anrufkontextkonfiguration. Zum Anzeigen dieser Konfigurationseinstellungen führen Sie das Cmdlet **Get-CsRgsConfiguration** aus. Nähere Informationen zum Cmdlet **Get-CsRgsConfiguration** finden Sie unter [Get-CsRgsConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration).

Sie können diese Einstellungen auf Anwendungsebene mithilfe des Cmdlets **Import-CsRgsConfiguration** und dem Parameter "-ReplaceExistingSettings" von einem Pool auf einen anderen übertragen. Dadurch werden jedoch die Einstellungen im Zielpool überschrieben.


> [!IMPORTANT]
> Diese Einschränkung beim Übertragen von Einstellungen auf einen anderen Pool gilt nur für Einstellungen auf Anwendungsebene und die Standarddatei für die Wartemusik. Für Agentgruppen, Warteschlangen, Workflows, Geschäftszeiten und Feiertagssätze gilt die Einschränkung nicht.



Wenn Sie die Einstellungen auf Anwendungsebene im Sicherungspool während eines Notfalls nicht ersetzen möchten und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen auf Anwendungsebene des primären Pools verloren. Wenn Sie während der Wiederherstellung einen neuen Pool als Ersatz für den primären Pool erstellen - entweder mit demselben oder einem anderen FQDN - können Sie die ursprünglichen Einstellungen auf Anwendungsebene nicht wiederherstellen. In diesem Fall müssen Sie den neuen Pool mit diesen Einstellungen konfigurieren und die Wartemusik-Audiodatei hinzufügen.

Wenn Sie Einstellungen auf Anwendungsebene bei einem Notfall mithilfe des Cmdlets **Import-CsRgsConfiguration** vom primären Pool auf den Sicherungspool übertragen möchten, können Sie die Einstellungen vom Sicherungspool bei der Wiederherstellung auf die gleiche Weise auf den neuen Pool übertragen, wie vom primären Pool auf den Sicherungspool.

Die folgende Tabelle zeigt eine Übersicht über die Schritte beim Wiederherstellen von Reaktionsgruppen.

Nähere Informationen zum Ausführen dieser Schritte finden Sie unter [Verfahren für die Notfallwiederherstellung für Reaktionsgruppen in Lync Server 2013](lync-server-2013-response-group-disaster-recovery-procedures.md).

### Schritte der Notfallwiederherstellung für Reaktionsgruppen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Erforderliche Gruppen und Rollen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vor dem Ausfall</p></td>
<td><p>Führen Sie regelmäßig das Cmdlet <strong>Export-CsRgsConfiguration</strong> aus, um Sicherungen aller Reaktionsgruppe-Konfigurationen in allen Front-End-Pools zu erstellen, in denen Reaktionsgruppenanwendung bereitgestellt ist.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Während des Ausfalls</p></td>
<td><p>Führen Sie das Cmdlet <strong>Import-CsRgsConfiguration</strong> aus, um die Sicherung der Lync Server-Reaktionsgruppendienst-Konfiguration vom primären Pool auf den Sicherungspool zu übertragen.</p>
<div>

> [!NOTE]
> Verwenden Sie den Parameter "-ReplaceExistingSettings", wenn Sie die Reaktionsgruppe-Einstellungen auf Anwendungsebene im Sicherungspool durch die Einstellungen aus dem primären Pool ersetzen möchten. Wenn Sie die Einstellungen auf Anwendungsebene nicht vom primären Pool auf den Sicherungspool übertragen und der primäre Pool nicht wiederhergestellt werden kann, gehen die Einstellungen aus dem primären Pool verloren.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="odd">
<td><p>Nach dem Importieren</p></td>
<td><p>Führen Sie Reaktionsgruppe-Cmdlets entweder mit dem Parameter &quot;-ShowAll&quot; (um alle Reaktionsgruppen anzuzeigen) oder dem Parameter &quot;-Owner&quot; (um nur importierte Reaktionsgruppen anzuzeigen) aus, um zu überprüfen, ob alle Reaktionsgruppenkonfigurationen in den Sicherungspool importiert wurden.</p>
<div>

> [!IMPORTANT]
> Wenn Sie weder den Parameter "-ShowAll" noch den Parameter "-Owner" verwenden, werden die in den Sicherungspool importierten Reaktionsgruppen nicht in den von den Cmdlets zurückgegebenen Ergebnissen aufgeführt.


</div>
<p>Führen Sie die folgenden Cmdlets aus:</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Nach dem Failover</p></td>
<td><ul>
<li><p>Führen Sie einen Testanruf an eine in den Sicherungspool importierte Reaktionsgruppe durch, und überprüfen Sie, ob der Anruf ordnungsgemäß verarbeitet wird.</p></li>
<li><p>Alle formellen Agents müssen sich bei ihren formellen Gruppen im Sicherungspool erneut anmelden.</p></li>
<li><p>Verwalten von Konfigurationsänderungen:</p>
<p>Reaktionsgruppen im Sicherungspool können unabhängig davon, ob sie in den Sicherungspool importiert wurden oder im Besitz des Sicherungspools sind, während des Ausfalls normal geändert werden.</p>
<div>

> [!IMPORTANT]
> Verwenden Sie die Lync Server-Verwaltungsshell zum Verwalten der Reaktionsgruppen, die Sie in den Sicherungspool importiert haben. Sie können diese Reaktionsgruppen nicht mithilfe der Lync Server-Systemsteuerung verwalten, während sie sich im Sicherungspool befinden.


</div></li>
</ul></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Nach der Wiederherstellung, vor dem Failback</p></td>
<td><p>Führen Sie das Cmdlet <strong>Export-CsRgsConfiguration</strong> aus, und geben Sie dabei den Parameter &quot;-Source&quot; als Sicherungspool und den Parameter &quot;-Owner&quot; als primären Pool an, in den die Reaktionsgruppen im Besitz des primären Pools aus dem Sicherungspool importiert werden sollen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
<tr class="even">
<td><p>Nach dem Failback</p></td>
<td><ul>
<li><p>Führen Sie das Cmdlet <strong>Import-CsRgsConfiguration</strong> aus, um die Reaktionsgruppen zurück in den primären Pool zu importieren.</p>
<div>

> [!NOTE]
> Wenn der primäre Pool nicht wiederhergestellt werden kann und Sie einen neuen Pool als Ersatz bereitstellen, verwenden Sie den Parameter "-ReplaceExistingSettings", um die Einstellungen auf Anwendungsebene vom Sicherungspool auf den neuen Pool zu übertragen. Wenn Sie die Einstellungen aus dem Sicherungspool nicht übertragen, verwendet der neue Pool die Standardeinstellungen.


</div></li>
<li><p>Führen Sie die folgenden -Cmdlets entweder mit dem Parameter &quot;-ShowAll&quot; (um alle Reaktionsgruppen anzuzeigen) oder dem Parameter &quot;-Owner&quot; (um nur importierte Reaktionsgruppen anzuzeigen) aus, um zu überprüfen, ob alle Reaktionsgruppenkonfigurationen erfolgreich zurück in den Sicherungspool importiert wurden.</p>
<ul>
<li><p><strong>Get-CsRgsWorkflow</strong></p></li>
<li><p><strong>Get-CsRgsQueue</strong></p></li>
<li><p><strong>Get-CsRgsAgentGroup</strong></p></li>
<li><p><strong>Get-CsRgsHoursOfBusiness</strong></p></li>
<li><p><strong>Get-CsRgsHolidaySet</strong></p></li>
</ul></li>
<li><p>Führen Sie einen Testanruf an eine in den primären Pool zurückimportierte Reaktionsgruppe durch, und überprüfen Sie, ob der Anruf ordnungsgemäß verarbeitet wird.</p></li>
<li><p>Führen Sie optional das Cmdlet <strong>Export-CsRgsConfiguration</strong> auf mit dem Parameter &quot;-RemoveExportedConfiguration&quot; auf dem Sicherungspool aus, um die Reaktionsgruppen im Besitz des primären Pool aus dem Sicherungspool zu entfernen.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsResponseGroupAdministrator</p></td>
</tr>
</tbody>
</table>

