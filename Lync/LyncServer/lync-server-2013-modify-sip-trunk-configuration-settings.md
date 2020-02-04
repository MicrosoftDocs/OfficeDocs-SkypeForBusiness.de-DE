---
title: 'Lync Server 2013: Ändern der SIP-Trunk-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>Ändern der SIP-Trunk-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

SIP Trunk-Konfigurationseinstellungen definieren die Beziehungen und Funktionen zwischen einem Vermittlungs Server und dem PSTN-Gateway (Public Switched Telephone Network), einer IP-Public Branch Exchange (PBX) oder einem Session Border Controller (SBC) beim Dienstanbieter. Diese Einstellungen geben unter anderem Folgendes an:

  - Ob Medienumgehung für die Trunks aktiviert werden soll.

  - Die Bedingungen, unter denen RTCP-Pakete (Real-Time Transport Control Protocol) gesendet werden.

  - Ob die SRTP-Verschlüsselung (Secure Real-Time Protocol) für jeden trunk erforderlich ist.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine globale Sammlung von SIP-Trunk-Konfigurationseinstellungen für Sie erstellt. Darüber hinaus können Administratoren benutzerdefinierte Auflistungen mit Einstellungen auf Standort- oder Dienstebene erstellen (nur für den PSTN-Gatewaydienst). Eine dieser Auflistungen kann später entweder mithilfe der lync Server-Systemsteuerung oder Windows PowerShell geändert werden.

Wenn Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung ändern, stehen Ihnen die folgenden Optionen zur Verfügung:


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
<td><p>Eindeutige ID für die Sammlung. Diese Eigenschaft ist schreibgeschützt. Sie können die Identität einer Sammlung von Trunkkonfigurationseinstellungen nicht ändern.</p></td>
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
<td><p>SRTPMode</p></td>
<td><p>Legt den Umfang der Unterstützung zum Schutz von Mediendatenverkehr zwischen dem Vermittlungsserver und dem PSTN-Gateway, der IP-Nebenstellenanlage oder dem SBC (Session Border Controller) des Dienstanbieters fest. Bei der Medienumgehung muss dieser Wert mit der Einstellung „EncryptionLevel“ in der Medienkonfiguration kompatibel sein. Die Medienkonfiguration wird mithilfe der Cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> und <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">CsMediaConfiguration</a> gesetzt.</p>
<p>Zulässige Werte:</p>
<ul>
<li><p>Erforderlich: Die SRTP-Verschlüsselung muss verwendet werden.</p></li>
<li><p>Optional: SRTP wird verwendet, wenn es vom Gateway unterstützt wird.</p></li>
<li><p>Nicht unterstützt: Die SRTP-Verschlüsselung wird nicht unterstützt und daher auch nicht verwendet.</p></li>
</ul>
<p>„SRTPMode“ wird nur verwendet, wenn das Gateway zur Verwendung von TLS (Transport Layer Security) konfiguriert ist. Wenn das Gateway mit dem Transportprotokoll TCP (Transmission Control Protocol) konfiguriert ist, wird „SRTPMode“ intern auf „Nicht unterstützt“ festgelegt.</p></td>
</tr>
<tr class="odd">
<td><p>Support melden</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Mit der Einstellung <strong>Senden der Weiterleitung an Gateway aktivieren</strong> unterstützt der Trunk den Empfang von Weiterleitungsanforderungen vom Vermittlungsserver.</p>
<p>Mit der Einstellung <strong>Weiterleitung mithilfe von Drittanbieteranrufsteuerung aktivieren</strong> kann das 3pcc-Protokoll verwendet werden, damit weitergeleitete Anrufe den gehosteten Standort umgehen können. 3PCC wird auch als &quot;Steuerung von Drittanbietern bezeichnet&quot; und tritt auf, wenn eine Drittpartei verwendet wird, um ein paar von Anrufern zu verbinden (beispielsweise einen Operator, der einen Anruf von Person a an Person B anlegt).</p></td>
</tr>
<tr class="even">
<td><p>Medienumgehung aktivieren</p></td>
<td><p>EnableBypass</p></td>
<td><p>Gibt an, ob die Medienumgehung für diesen Trunk aktiviert ist. Die Medienumgehung kann nur aktiviert werden, wenn auch <strong>Zentralisierte Medienverarbeitung</strong> aktiviert ist.</p></td>
</tr>
<tr class="odd">
<td><p>Zentralisierte Medienverarbeitung</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Gibt an, ob ein bekannter Medienendpunkt vorhanden ist. (Ein Beispiel für einen bekannten Medienendpunkt ist ein PSTN-Gateway, bei dem der Medienendpunkt dieselbe IP-Adresse hat wie der Signaldatenverkehrendpunkt.)</p></td>
</tr>
<tr class="even">
<td><p>RTP-Verriegelung aktivieren</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Gibt an, ob SIP-Trunks die RTP-Verriegelung unterstützen oder nicht. Die RTP-Verriegelung ist eine Technologie, die RTP-/RTCP-Verbindungen über NAT (Network Address Translator, Netzwerkadressenübersetzung) oder eine Firewall ermöglicht.</p></td>
</tr>
<tr class="odd">
<td><p>Weiterleitung der Anrufliste aktivieren</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Gibt an, ob Informationen zum Anrufverlauf durch den Trunk weitergeleitet werden.</p></td>
</tr>
<tr class="even">
<td><p>Weiterleitung von P-Asserted-Identity-Daten aktivieren</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Gibt an, ob der PAI-Header (P-Asserted-Identity) zusammen mit dem Anruf weitergeleitet wird. Der PAI-Header bietet eine Möglichkeit, die Identität des Anrufers zu überprüfen.</p></td>
</tr>
<tr class="odd">
<td><p>Failovertimer für Ausgangsrouting aktivieren</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Gibt an, ob ausgehende Anrufe, die vom Gateway nicht innerhalb von 10 Sekunden beantwortet werden, an den nächsten verfügbaren Trunk weitergeleitet werden. Wenn keine weiteren Trunks verfügbar sind, wird der Anruf automatisch beendet. In einer Organisation mit langsamen Netzwerk- und Gatewayreaktionen könnte dies dazu führen, dass Anrufe unnötigerweise beendet werden.</p></td>
</tr>
<tr class="even">
<td><p>Zugeordnete PSTN-Verwendungen</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Dem Trunk zugewiesene Auflistung von PSTN-Verwendungen.</p></td>
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
<td><p>Übersetzungsregeln für die gewählte Nummer</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Dem Trunk zugewiesene Auflistung von ausgehenden Übersetzungsregeln für Telefonnummern.</p></td>
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
<td><p>-</p></td>
<td><p>Gibt an, dass die zu testende Telefonnummer die Telefonnummer der Person ist, die angerufen wird.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Die lync Server CsTrunkConfiguration-Cmdlets unterstützen zusätzliche Eigenschaften, die in der lync Server-Systemsteuerung nicht angezeigt werden. Weitere Informationen finden Sie im Hilfethema zum Cmdlet " <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Satz-CsTrunkConfiguration</A> ".



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>So ändern Sie die SIP-Trunk-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung

1.  Klicken Sie in der lync Server-Systemsteuerung auf **VoIP-Routing**, und klicken Sie dann auf **trunk-Konfiguration**.

2.  Doppelklicken Sie auf der Registerkarte **Trunkkonfiguration** auf die Trunkkonfigurationseinstellungen, die Sie ändern möchten. Beachten Sie, dass Sie immer nur eine Einstellung bearbeiten können. Wenn Sie die gleichen Änderungen an mehreren Sammlungen vornehmen möchten, verwenden Sie Windows PowerShell.

3.  Nehmen Sie im Dialogfeld **Trunkkonfiguration bearbeiten** die gewünschten Einstellungen vor und klicken Sie auf **OK**.

4.  Die Eigenschaft **State** für die Sammlung wird als **Commit nicht ausgeführt** angezeigt. Um die Änderungen zu übernehmen und die Sammlung zu löschen, klicken Sie auf **Commit ausführen** und anschließend auf **Commit für alle Elemente ausführen**.

5.  Klicken Sie im Dialogfeld **VoIP-Konfigurationseinstellungen, für die kein Commit ausgeführt wurde** auf **OK**.

6.  Klicken Sie im Dialogfeld **Microsoft lync Server 2013-System** Steuerung auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

