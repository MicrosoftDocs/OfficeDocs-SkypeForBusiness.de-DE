---
title: Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Lync Server 2013
TOCTitle: Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Lync Server 2013
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49890744
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Erstellen einer neuen Auflistung von Trunkkonfigurationseinstellungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Konfigurationseinstellungen des SIP-Trunks definieren die Beziehung und die Funktionen zwischen einem Vermittlungsserver und einem PSTN-Gateway (Public Switched Telephone Network, Telefonfestnetz), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Mit diesen Einstellungen wird u. a. Folgendes festgelegt:

  - Soll die Medienumgehung auf den Trunks aktiviert werden?

  - Unter welchen Bedingungen können RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden?

  - Ist eine sichere SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) auf jedem Trunk erforderlich?

Wenn Sie Microsoft Lync Server 2013 installieren, wird eine globale Sammlung von Konfigurationseinstellungen für SIP-Trunks für Sie erstellt. Darüber hinaus können Administratoren eigene Sammlungen mit Einstellungen auf Standort- oder Dienstebene erstellen. (Dies ist jedoch nur für PSTN-Gateway-Dienste möglich.)

Beim Erstellen der Konfigurationseinstellungen für einen SIP-Trunk mit Lync Server-Systemsteuerung stehen Ihnen folgende Optionen zur Verfügung:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzeroberflächeneinstellung</th>
<th>PowerShell-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identität</p></td>
<td><p>Eindeutiger Bezeichner für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Die Identität einer Sammlung von Konfigurationseinstellungen für Trunks kann nicht geändert werden.</p></td>
</tr>
<tr class="even">
<td><p>Beschreibung</p></td>
<td><p>Beschreibung</p></td>
<td><p>Ermöglicht Administratoren, zusätzliche Informationen über die Einstellungen (beispielsweise über den Zweck der Trunkkonfiguration) zu speichern.</p></td>
</tr>
<tr class="odd">
<td><p>Maximal unterstützte frühe Dialoge</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.</p></td>
</tr>
<tr class="even">
<td><p>Unterstützte Verschlüsselungsstufe</p></td>
<td><p>SRTPMode</p></td>
<td><p>Gibt den Umfang der Unterstützung für den Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC beim Dienstanbieter an. Bei Medienumgehungen muss dieser Wert mit der EncryptionLevel-Einstellung in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration erfolgt mithilfe des Cmdlets <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und des Cmdlets <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a>.</p>
<p>Zulässige Werte sind folgende:</p>
<ul>
<li><p>Required: Die SRTP-Verschlüsselung muss verwendet werden.</p></li>
<li><p>Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</p></li>
<li><p>Not Supported: Die SRTP-Verschlüsselung wird nicht unterstützt und daher nicht verwendet.</p></li>
</ul>
<p>&quot;SRTPMode&quot; wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird &quot;SRTPMode&quot; intern auf &quot;NotSupported&quot; festgelegt.</p></td>
</tr>
<tr class="odd">
<td><p>REFER-Unterstützung</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Wenn diese Einstellung auf <strong>REFER-Weiterleitung an das Gateway ermöglichen</strong> festgelegt ist, unterstützt der Trunk das Empfangen von Übergabeanforderungen vom Vermittlungsserver.</p>
<p>Wenn diese Einstellung auf <strong>REFER mit Drittanbieter-Anrufsteuerung ermöglichen</strong> festgelegt ist, kann das 3pcc-Protokoll verwendet werden, um übertragenen Anrufen das Umgehen des gehosteten Standorts zu ermöglichen. 3pcc wird auch als &quot;Drittanbietersteuerung&quot; bezeichnet. Sie kommt zum Einsatz, wenn die Verbindung zu einem Anruferpaar (z. B. ein Agent, der einen Anruf von Person A an Person B tätigt) hergestellt wird.</p></td>
</tr>
<tr class="even">
<td><p>Medienumgehung aktivieren</p></td>
<td><p>EnableBypass</p></td>
<td><p>Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn <strong>Zentralisierte Medienverarbeitung</strong> ebenfalls aktiviert wurde.</p></td>
</tr>
<tr class="odd">
<td><p>Zentralisierte Medienverarbeitung</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)</p></td>
</tr>
<tr class="even">
<td><p>RTP-Verbindungen aktivieren</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Gibt an, ob RTP-Verbindungen von SIP-Trunks unterstützt wird. Bei RTP-Verbindungen wird die RTP-/RTCP-Konnektivität über ein NAT-Gerät (Network Address Translation, Netzwerkadressenübersetzung) oder eine Firewall sichergestellt.</p></td>
</tr>
<tr class="odd">
<td><p>Weiterleitung des Anrufverlaufs aktivieren</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Gibt an, ob Informationen über den Anrufverlauf über den Trunk weitergeleitet werden.</p></td>
</tr>
<tr class="even">
<td><p>Weiterleitung von P-Asserted-Identity (PAI)-Daten aktivieren</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Gibt an, ob der PAI-Header zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header ermöglicht eine Überprüfung der Identität des Anrufers.</p></td>
</tr>
<tr class="odd">
<td><p>Failover-Timer für Ausgangsrouting aktivieren</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden sollen. Wenn keine weiteren Trunks vorhanden sind, wird der Anruf automatisch gelöscht. In einer Organisation mit langsamen Netzwerken und Gatewayantworten kann dies dazu führen, dass Anrufe u. U. gelöscht werden, obwohl dies nicht erwünscht bzw. nicht erforderlich ist.</p></td>
</tr>
<tr class="even">
<td><p>Zugeordnete PSTN-Verwendungen</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Sammlung weiterer PSTN-Nutzungsmöglichkeiten, die mit dem Trunk verbunden sind.</p></td>
</tr>
<tr class="odd">
<td><p>Übersetzte Nummer zum Testen</p></td>
<td><p>N/V</p></td>
<td><p>Telefonnummer, die für einen Ad-hoc-Test der Konfigurationseinstellungen des Trunks verwendet werden kann.</p></td>
</tr>
<tr class="even">
<td><p>Zugehörige Übersetzungsregeln</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Auflistung von Regeln für die Übersetzung von Telefonnummern von Anrufen, die per Ausgangsrouting verarbeitet werden (d. h., sie werden an Nebenstellenanlagen oder PSTN-Ziele geleitet).</p></td>
</tr>
<tr class="odd">
<td><p>Übersetzungsregeln für angerufene Nummer</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Sammlung von Übersetzungsregeln für Nummern ausgehender Anrufe, die dem Trunk zugewiesen wurden.</p></td>
</tr>
<tr class="even">
<td><p>Telefonnummer zum Testen</p></td>
<td><p>N/V</p></td>
<td><p>Telefonnummer, die für einen Ad-hoc-Test der Übersetzungsregeln des Trunks verwendet werden kann.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufende Nummer</p></td>
<td><p>N/V</p></td>
<td><p>Gibt an, dass die zum Testen verwendete Telefonnummer die Telefonnummer des Anrufers ist.</p></td>
</tr>
<tr class="even">
<td><p>Angerufene Nummer</p></td>
<td><p>N/V</p></td>
<td><p>Gibt an, dass die zum Testen verwendete Telefonnummer die Telefonnummer des Angerufenen ist.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Die Lync Server CsTrunkConfiguration-Cmdlets unterstützen weitere Eigenschaften, die nicht in Lync Server-Systemsteuerung angezeigt werden. Weitere Informationen finden Sie im Hilfethema für das <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A>-Cmdlet.



## Erstellen neuer Trunkkonfigurationseinstellungen mit Lync Server-Systemsteuerung

1.  Klicken Sie in Lync Server-Systemsteuerung auf **VoIP-Routing** und dann auf **VoIP-Routing testen**.

2.  Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen auf Standortebene zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen auf Dienstebene zu erstellen.

3.  Wählen Sie im Dialogfeld **Standort auswählen** oder im Dialogfeld **Dienst auswählen** (das angezeigte Dialogfeld ist abhängig davon, ob Sie Einstellungen auf Standort- oder auf Dienstebene vornehmen) den Standort für die neuen Konfigurationseinstellungen aus, und klicken Sie auf **OK**. Wenn das Dialogfeld leer ist, können Sie keine neuen Einstellungen erstellen. Wenn beispielsweise das Dialogfeld **Standort auswählen** leer ist, bedeutet dies, dass allen Standorten bereits eine Sammlung von Trunkkonfigurationsstandorten zugewiesen wurde. An jedem Standort (und in jedem Dienst) kann jedoch nur eine solche Sammlung gehostet werden. In diesem Fall können Sie die bestehende Sammlung löschen und eine neue erstellen, oder Sie können die bestehende Sammlung bearbeiten.

4.  Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor, und klicken Sie auf **OK**.

5.  Die Eigenschaft **Zustand** für die Sammlung wird aktualisiert und lautet jetzt **Ohne Commit**. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit** und dann auf **Commit für alle**.

6.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen ohne Commit** auf **OK**.

7.  Klicken Sie im Dialogfeld **Microsoft Lync Server 2013-Systemsteuerung** auf **OK**.

