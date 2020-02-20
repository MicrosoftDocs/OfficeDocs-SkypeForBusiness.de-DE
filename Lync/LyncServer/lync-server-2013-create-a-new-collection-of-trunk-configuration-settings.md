---
title: 'Lync Server 2013: Erstellen einer neuen Auflistung von trunkkonfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07e5dc814887a7304a48602e04f48a00137bf8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Erstellen Sie in lync Server 2013 eine neue Auflistung von trunkkonfigurationseinstellungen.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Mit SIP-Trunk-Konfigurationseinstellungen werden die Beziehung und die Funktionen zwischen einem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Nebenstellenanlage (Private Branch Exchange, PBX) oder einem SBC (Session Border Controller) des Dienstanbieters definiert. Mit diesen Einstellungen kann Folgendes angegeben werden:

  - Ob die Medienumgebung für Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control-Protokoll) gesendet werden.

  - Ob für jeden Trunk die SRTP-Verschlüsselung (Secure Real-Time-Protokoll) erforderlich ist.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-trunkkonfigurationseinstellungen für Sie erstellt. Außerdem können Administratoren benutzerdefinierte Einstellungssammlungen auf Standortebene oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst).

Wenn Sie SIP-Trunk-Konfigurationseinstellungen mit lync Server-Systemsteuerung erstellen, stehen Ihnen die folgenden Optionen zur Verfügung:


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
<td><p>Identität</p></td>
<td><p>Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung an Trunkkonfigurationseinstellungen nicht ändern.</p></td>
</tr>
<tr class="even">
<td><p>Beschreibung</p></td>
<td><p>Beschreibung</p></td>
<td><p>Bietet Administratoren eine Möglichkeit, zusätzliche Informationen zu den Einstellungen zu speichern (z. B. Zweck der Trunkkonfiguration).</p></td>
</tr>
<tr class="odd">
<td><p>Maximal unterstützte frühe Dialoge</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Die maximale Anzahl von gegabelten Antworten, die ein PSTN-Gateway, eine IP-Nebenstellenanlage oder ein SBC (Session Border Controller) des Dienstanbieters auf an den Vermittlungsserver gesendete Einladungen empfangen kann.</p></td>
</tr>
<tr class="even">
<td><p>Unterstützte Verschlüsselungsstufe</p></td>
<td><p>"Srtpmode"</p></td>
<td><p>Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung "EncryptionLevel" in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der Cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">setCsMediaConfiguration</a> festgelegt.</p>
<p>Gültige Werte sind:</p>
<ul>
<li><p>Required: Die SRTP-Verschlüsselung muss verwendet werden.</p></li>
<li><p>Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</p></li>
<li><p>Not Supported: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet.</p></li>
</ul>
<p>"SRTPMode" wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird "SRTPMode" intern auf "Not Supported" festgelegt.</p></td>
</tr>
<tr class="odd">
<td><p>Support melden</p></td>
<td><p>Enable3pccRefer</p>
<p>"Enablerefersupport"</p></td>
<td><p>Mit der Einstellung <strong>Refer-Anforderungen an das Gateway senden</strong> unterstützt der Trunk den Empfang von Refer-Anforderungen vom Vermittlungsserver.</p>
<p>Mit der Einstellung <strong>Refer-Anforderungen mit 3pcc senden</strong> kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3PCC wird auch als &quot;Drittanbieter-Steuerelement&quot; bezeichnet und tritt auf, wenn ein Drittanbieter verwendet wird, um ein paar von Anrufern zu verbinden (beispielsweise ein Operator, der einen Anruf von Person a an Person B abruft).</p></td>
</tr>
<tr class="even">
<td><p>Medienumgehung aktivieren</p></td>
<td><p>EnableBypass</p></td>
<td><p>Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch <strong>Zentrale Medienverarbeitung</strong> aktiviert ist.</p></td>
</tr>
<tr class="odd">
<td><p>Zentrale Medienverarbeitung</p></td>
<td><p>"Concentratedtopology"</p></td>
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
<td><p>Nicht zutreffend</p></td>
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
<td><p>Nicht zutreffend</p></td>
<td><p>Eine Telefonnummer, die für Ad-hoc-Tests der Übersetzungsregeln verwendet werden kann.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufende Nummer</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>Gibt an, dass die zu testende Telefonnummer die Telefonnummer des Anrufers ist.</p></td>
</tr>
<tr class="even">
<td><p>Angerufene Nummer</p></td>
<td><p>Nicht zutreffend</p></td>
<td><p>Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die lync Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die nicht in lync Server-Systemsteuerung angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration-</A> Cmdlet.



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>So erstellen Sie neue trunkkonfigurationseinstellungen mithilfe von lync Server-Systemsteuerung

1.  Klicken Sie in lync Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **trunk Konfiguration**.

2.  Klicken Sie auf der Registerkarte **Trunkkonfiguration** auf **Neu** und dann auf **Standorttrunk**, um die neuen Einstellungen auf Standortebene zu erstellen, oder klicken Sie auf **Pooltrunk**, um die neuen Einstellungen auf Dienstebene zu erstellen.

3.  Wählen Sie im Dialogfeld **Standort auswählen** oder im Dialogfeld **Dienst auswählen** (das angezeigte Dialogfeld ist abhängig davon, ob Sie Einstellungen auf Standort- oder auf Dienstebene vornehmen) den Standort für die neuen Konfigurationseinstellungen aus, und klicken Sie auf **OK**. Wenn das Dialogfeld leer ist, können Sie keine neuen Einstellungen erstellen. Wenn beispielsweise das Dialogfeld **Standort auswählen** leer ist, bedeutet dies, dass allen Standorten bereits eine Sammlung von Trunkkonfigurationsstandorten zugewiesen wurde. An jedem Standort (und in jedem Dienst) kann jedoch nur eine solche Sammlung gehostet werden. In diesem Fall können Sie die bestehende Sammlung löschen und eine neue erstellen, oder Sie können die bestehende Sammlung bearbeiten.

4.  Nehmen Sie im Dialogfeld **Neue Trunkkonfiguration** die gewünschten Einstellungen vor, und klicken Sie auf **OK**.

5.  Die Eigenschaft **Zustand** für die Sammlung wird aktualisiert und lautet jetzt **Ohne Commit**. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit** und dann auf **Commit für alle**.

6.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.

7.  Klicken Sie im Dialogfeld **Microsoft Lync Server 2013-Systemsteuerung** auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

