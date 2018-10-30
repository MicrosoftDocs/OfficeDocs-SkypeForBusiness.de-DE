---
title: Ändern von SIP-Trunk-Konfigurationseinstellungen in Lync Server 2013
TOCTitle: Ändern von SIP-Trunk-Konfigurationseinstellungen in Lync Server 2013
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49890806
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Ändern von SIP-Trunk-Konfigurationseinstellungen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die SIP-Trunkkonfiguration enthält Einstellungen, die Beziehung und Funktionen zwischen dem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definieren. Diese Einstellungen konfigurieren beispielsweise die folgenden Punkte:

  - Ob die Medienumgehung auf den Trunks aktiviert werden muss.

  - Unter welchen Bedingungen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.

  - Ob die sichere SRTP-Verschlüsselung (Secure Real-Time Transport Protocol) auf den einzelnen Trunks erforderlich ist oder nicht.

Bei der Installation von Microsoft Lync Server 2013 wird eine globale Sammlung an SIP-Trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Alle diese Sammlungen können später über die Lync Server-Systemsteuerung oder die Windows PowerShell bearbeitet werden.

Beim Bearbeiten der SIP-Trunkkonfigurationseinstellungen über die Lync Server-Systemsteuerung stehen Ihnen die folgenden Optionen zur Verfügung:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI-Einstellung</th>
<th>PowerShell-Parameter</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Identity</p></td>
<td><p>Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.</p></td>
</tr>
<tr class="even">
<td><p>Beschreibung</p></td>
<td><p>Description</p></td>
<td><p>Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).</p></td>
</tr>
<tr class="odd">
<td><p>Maximal unterstützte frühe Dialoge</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.</p></td>
</tr>
<tr class="even">
<td><p>Unterstützte Verschlüsselungsstufe</p></td>
<td><p>SRTPMode</p></td>
<td><p>Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung &quot;EncryptionLevel&quot; in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mit den Cmdlets <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> festgelegt.</p>
<p>Gültige Werte sind:</p>
<ul>
<li><p>Required: Die SRTP-Verschlüsselung muss verwendet werden.</p></li>
<li><p>Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</p></li>
<li><p>Not Supported: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet.</p></li>
</ul>
<p>&quot;SRTPMode&quot; wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird &quot;SRTPMode&quot; intern auf &quot;Not Supported&quot; festgelegt.</p></td>
</tr>
<tr class="odd">
<td><p>Support melden</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Mit der Einstellung <strong>Refer-Anforderungen an das Gateway senden</strong> unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.</p>
<p>Mit der Einstellung <strong>Refer-Anforderungen mit 3pcc senden</strong> kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3pcc ist auch unter dem Namen &quot;Third Party Call Control&quot; bekannt und tritt auf, wenn ein Drittanbieter verwendet wird, um zwei Anrufer miteinander zu verbinden (z. B. wenn ein Anruf von Person A an Person B über eine Telefonzentrale durchgestellt wird).</p></td>
</tr>
<tr class="even">
<td><p>Medienumgehung aktivieren</p></td>
<td><p>EnableBypass</p></td>
<td><p>Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch <strong>Zentrale Medienverarbeitung</strong> aktiviert ist.</p></td>
</tr>
<tr class="odd">
<td><p>Zentrale Medienverarbeitung</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt die gleiche IP-Adresse hat wie der Signaldatenverkehr-Endpunkt.)</p></td>
</tr>
<tr class="even">
<td><p>RTP-Latching aktivieren</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Gibt an, ob SIP-Trunks RTP-Latching unterstützen oder nicht. RTP-Latching ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.</p></td>
</tr>
<tr class="odd">
<td><p>Weiterleiten der Anrufliste aktivieren</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Gibt an, ob Informationen zum Anruferverlauf durch den Trunk weitergeleitet werden.</p></td>
</tr>
<tr class="even">
<td><p>Weiterleiten von P-Asserted-Identity-Daten aktivieren</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</p></td>
</tr>
<tr class="odd">
<td><p>Timer für Ausgangsroutingfailover aktivieren</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gateway-Reaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.</p></td>
</tr>
<tr class="even">
<td><p>Zugeordnete PSTN-Verwendungen</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Eine Sammlung von dem Trunk zugewiesenen PSTN-Verwendungen.</p></td>
</tr>
<tr class="odd">
<td><p>Übersetzte Nummer zum Testen</p></td>
<td><p>N/V</p></td>
<td><p>Eine Telefonnummer, die für Ad-hoc-Tests der Trunkkonfigurationseinstellungen verwendet werden kann.</p></td>
</tr>
<tr class="even">
<td><p>Zugehörige Übersetzungsregeln</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Sammlung an Regeln für die Telefonnummernübersetzung für Anrufe, die per Ausgangsrouting verarbeitet werden (Anrufe, die an Ziele in Nebenstellenanlagen oder im Telefonfestnetz weitergeleitet werden).</p></td>
</tr>
<tr class="odd">
<td><p>Übersetzungsregeln für angerufene Nummern</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Sammlung an Regeln für die Nummernübersetzung für ausgehende Anrufe, die dem Trunk zugewiesen sind.</p></td>
</tr>
<tr class="even">
<td><p>Testtelefonnummer</p></td>
<td><p>N/V</p></td>
<td><p>Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufende Nummer</p></td>
<td><p>N/V</p></td>
<td><p>Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.</p></td>
</tr>
<tr class="even">
<td><p>Angerufene Nummer</p></td>
<td><p>N/V</p></td>
<td><p>Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> Die CsTrunkConfiguration-Cmdlets von Lync Server unterstützen weitere Eigenschaften, die in der Lync Server-Systemsteuerung nicht angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A>-Cmdlet.



## Bearbeiten von SIP-Trunkkonfigurationseinstellungen über die Lync Server-Systemsteuerung

1.  Klicken Sie in der Lync Server-Systemsteuerung auf **VoIP-Routing** und anschließend auf **Trunkkonfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.

3.  Nehmen Sie im Dialogfeld **Trunkkonfiguration bearbeiten** die gewünschten Einstellungen vor, und klicken Sie auf **OK**.

4.  Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit**, und klicken Sie anschließend auf **Commit für alle**.

5.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen ohne Commit** auf **OK**.

6.  Klicken Sie im Dialogfeld **Microsoft Lync Server 2013-Systemsteuerung** auf **OK**.

