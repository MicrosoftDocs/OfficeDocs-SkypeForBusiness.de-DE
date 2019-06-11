---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Prüfliste zur Bereitstellung für Einwahlkonferenzen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-10-03_

Die für Einwahlkonferenzen erforderlichen Komponenten werden bereitgestellt, wenn Sie die Konferenz Arbeitsauslastung bereitstellen. Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder einen Vermittlungs Server und ein PSTN-Gateway (Public Switched Telephone Network) bereitstellen.

Alle Schritte in der folgenden Tabelle müssen ausgeführt werden, bevor Benutzer sich vom PSTN aus anrufen können, um an einer Audio/Video-Konferenz teilzunehmen.

<div>


> [!NOTE]  
> Wenn Sie von Office Communications Server 2007 R2 migrieren, müssen Sie die neuesten Updates auf Ihre Office Communications Server 2007 R2-Umgebung anwenden, bevor Sie Einwahlkonferenzen bereitstellen.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Bereitstellungsprozess für Einwahlkonferenzen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Berechtigungen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Erstellen einer Topologie mit der Konferenz Arbeitsauslastung, einschließlich eines Vermittlungsservers und eines PSTN-Gateways, und Bereitstellen des Front-End-Pools oder des Standard Edition-Servers</strong></p></td>
<td><ol>
<li><p>Führen Sie den Topologie-Generator aus, um Ihre Topologie zu konfigurieren. Wählen Sie beim Konfigurieren der Topologie die Einwahlkonferenzoption aus.</p></li>
<li><p>Veröffentlichen der Topologie und Bereitstellen des Front-End-Pools oder des Standard Edition-Servers</p></li>
<li><p>Erstellen Sie bei Bedarf einen eigenständigen Vermittlungs Server, und ordnen Sie ihn einem PSTN-Gateway zu.</p>
<div>

> [!NOTE]  
> Dieser Schritt ist nur erforderlich, wenn Sie Enterprise-VoIP nicht bereitstellen und den Vermittlungsserver nicht mit dem Enterprise EditionFront-collocate oder dem Standard Edition-Server abgleichen. Wenn Sie Enterprise-VoIP bereitstellen, installieren und konfigurieren Sie Vermittlungsserver und PSTN-Gateways als Teil der Enterprise-VoIP-Bereitstellung. Wenn Sie den Vermittlungsserver collocate, installieren und konfigurieren Sie den Vermittlungsserver als Teil des Front-End-Pools oder der Standard Edition-Server Bereitstellung.


</div></li>
</ol></td>
<td><p>Domänen-Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrator</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></p></li>
<li><p>So erstellen Sie einen eigenständigen vermittlungsserverpool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial plans</strong></p></td>
<td><p>Bei Wähleinstellungen handelt es sich um einen Satz Rufnummernormalisierungsregeln, die von einem bestimmten Standort aus gewählte Rufnummern in ein einziges Standardformat (E.164) übersetzen, um die Telefonautorisierung und das Anrufrouting zu ermöglichen. Eine von verschiedenen Standorten aus gewählte Rufnummer kann je nach Wähleinstellungen dem Standort entsprechend in unterschiedliche E.164-Nummern aufgelöst werden. Wenn Sie Enterprise-VoIP bereitstellen, richten Sie Wählpläne als Teil dieser Bereitstellung ein, und Sie müssen sicherstellen, dass die Wählpläne auch Einwahlkonferenzen unterstützen. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie Wählpläne für Einwahlkonferenzen einrichten.</p>
<p>Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell zum Einrichten von Wählplänen wie folgt:</p>
<ol>
<li><p>Erstellen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl.</p></li>
<li><p>Weisen Sie jedem Pool einen Standardsatz mit Wähleinstellungen zu. Legen Sie die <strong>Region für Einwahlkonferenzen</strong> auf den geografischen Standort fest, für den die Wähleinstellungen gelten. Die Region ordnet die Wähleinstellungen den Zugriffsnummern für die Einwahl zu.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Konfigurieren von Wählplänen für Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Sicherstellen, dass den Wähleinstellungen Regionen zugeordnet werden</strong></p></td>
<td><p>Führen Sie die Cmdlets <strong>Get-CsDialPlan</strong> und <strong>Set-CsDialPlan</strong> aus, um sicherzustellen, dass allen Wähleinstellungen eine Region zugeordnet wird.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Sicherstellen, dass die Wähleinstellungen lync Server 2013 Regionen zugewiesen haben</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Überprüfen oder Ändern der Anforderungen an die persönliche Identifikationsnummer (PIN) der Benutzer.</strong></p></td>
<td><p>Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell zum Anzeigen oder Ändern der Konferenz- <strong>PIN-Richtlinie</strong>. Sie können eine PIN-Mindestlänge, eine maximale Anzahl von Anmeldeversuchen, ein PIN-Ablaufdatum und die Zulässigkeit gängiger Muster festlegen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Überprüfen der PIN-Richtlinieneinstellungen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren Sie die Konferenzrichtlinie so, dass Einwahlkonferenzen unterstützt werden.</strong></p></td>
<td><p>Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell zum Konfigurieren von <strong>Konferenzrichtlinien</strong> Einstellungen. Legen Sie folgende Einstellungen fest:</p>
<ul>
<li><p>Die PSTN-Konferenzeinwahl ist aktiviert.</p></li>
<li><p>Benutzer können anonyme Teilnehmer einladen.</p></li>
<li><p>Nicht authentifizierte Benutzer können über ausgehende Telefonverbindungen an einer Konferenz teilnehmen. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Konfigurieren von Konferenzrichtlinien für die Einwahl in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Configure dial-in access numbers</strong></p></td>
<td><p>Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell zum Einrichten von Einwahl Zugriffsnummern, die Benutzer anrufen, um sich in eine Konferenz einzuwählen, und geben Sie die Regionen an, die die Zugriffsnummer mit den entsprechenden Wählplänen verknüpfen. Die ersten drei Zugriffsnummern für die Region, die durch die Wähleinstellungen des Organisators festgelegt wird, sind in der Konferenzeinladung enthalten. Alle Zugriffsnummern sind auf der Seite Einstellungen für Einwahlkonferenzen verfügbar.</p>
<div>

> [!NOTE]  
> Nachdem Sie Einwahl Zugriffsnummern erstellt haben, können Sie das Cmdlet " <STRONG>festlegen-CsDialInConferencingAccessNumber</STRONG> " verwenden, um den Anzeigenamen der Active Directory-Kontaktobjekte zu ändern, damit Benutzer die richtige Zugriffsnummer leichter identifizieren können.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Konfigurieren von Einwahlnummern für Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Optional) Überprüfen der Einwahlkonferenzeinstellungen</strong></p></td>
<td><p>Suchen Sie mithilfe des Cmdlets <strong>Get-CsDialinConferencingAccessNumber</strong> nach Wähleinstellungen, deren Einwahlkonferenzregion von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern, denen keine Region zugeordnet ist.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Überprüfen der Einwahlkonferenzeinstellungen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Ändern der Tastenzuordnung von DTMF-Befehlen</strong></p></td>
<td><p>Verwenden Sie das Cmdlet " <strong>CsDialinConferencingDtmfConfiguration</strong> ", um die Tasten zu ändern, die für DTMF-Befehle (Dual Tone MultiFrequency) verwendet werden, mit denen die Teilnehmer Konferenzeinstellungen steuern können (wie Stummschaltung und Aufheben der Stummschaltung oder sperren und entsperren).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Ändern der Tastenzuordnung für DTMF-Befehle in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Optional) Ändern des Ankündigungsverhaltens beim Beitreten oder Verlassen einer Konferenz</strong></p></td>
<td><p>Ändern Sie mit dem Cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> die Funktionsweise von Ankündigungen, wenn Teilnehmer einer Konferenz beitreten bzw. diese verlassen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Aktivieren und Deaktivieren von Konferenzankündigungen beim Beitreten und Verlassen in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Überprüfen von Einwahlkonferenzen</strong></p></td>
<td><p>Testen Sie mithilfe des Cmdlets <strong>Test-CsDialInConferencing</strong>, ob die Zugriffsnummern für den angegebenen Pool ordnungsgemäß funktionieren.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Überprüfen von Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</strong></p></td>
<td><p>Stellen Sie das Online Besprechungs-Add-in für lync 2013 bereit, damit Benutzer Konferenzen planen können, die Einwahlkonferenzen unterstützen. Das Online Besprechungs-Add-in für lync 2013 wird automatisch installiert, wenn Sie lync 2013 installieren.</p></td>
<td><p>Administratoren</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren der Benutzerkontoeinstellungen</strong></p></td>
<td><p>Verwenden Sie die lync Server 2013-Systemsteuerung oder die lync Server-Verwaltungsshell, um den URI der Telefon <strong>Leitung</strong> als eindeutige, normalisierte Telefonnummer zu konfigurieren (beispielsweise Tel: + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Konfigurieren der Benutzerkontoeinstellungen  in Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>(Empfohlen) Konfigurieren von Konferenzverzeichnissen</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>New-CsConferenceDirectory</strong>, um ein Konferenzverzeichnis pro 999 Benutzer im Pool zu erstellen.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Anforderungen für Einwahlkonferenzen in lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Empfohlen) Erstellen von Konferenz Verzeichnissen</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Einladen von Benutzern zu Einwahlkonferenzen und Festlegen der anfänglichen PIN</strong></p></td>
<td><p>Verwenden Sie das <strong>CsPinSendCAWelcomeMail-</strong> Skript, um die anfänglichen Pins der Benutzer festzulegen und eine Willkommens-e-Mail zu senden, die die ursprüngliche PIN und einen Link zur Seite Einstellungen für Einwahlkonferenzen enthält.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Einladen von Benutzern zu Einwahlkonferenzen in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

