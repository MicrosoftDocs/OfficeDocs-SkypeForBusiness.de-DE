---
title: Prüfliste für lync Server 2013-Bereitstellung für Einwahlkonferenzen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 084686c33482e4828378db76c2a5ca1c834bacf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Prüfliste für die Bereitstellung von Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-10-03_

Die für Einwahlkonferenzen erforderlichen Komponenten werden bei der Bereitstellung der Konferenzarbeitsauslastung bereitgestellt. Bevor Sie Einwahlkonferenzen konfigurieren können, müssen Sie entweder Enterprise-VoIP oder ein Vermittlungsserver und ein PSTN-Gateway (Public Switched Telephone Network) bereitstellen.

Alle Schritte in der folgenden Tabelle müssen durchgeführt werden, damit Benutzer sich über ein Telefonfestnetz einwählen und an einer Audio/Video-Konferenz teilnehmen können.

<div>


> [!NOTE]  
> Wenn Sie von Office Communications Server 2007 R2 migrieren, müssen Sie vor der Bereitstellung von Einwahlkonferenzen die neuesten Updates auf Ihre Office Communications Server 2007 R2 Umgebung anwenden.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>Verfahren zur Bereitstellung von Einwahlkonferenzen

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
<td><p><strong>Erstellen Sie eine Topologie, die die Konferenz Arbeitsauslastung einschließlich einer Vermittlungsserver und eines PSTN-Gateways umfasst, und stellen Sie die Front-End-Pool oder Standard Edition-Server</strong></p></td>
<td><ol>
<li><p>Führen Sie den Topologie-Generator aus, um die Topologie zu konfigurieren. Wählen Sie beim Konfigurieren der Topologie die Einwahlkonferenzoption aus.</p></li>
<li><p>Veröffentlichen Sie die Topologie, und stellen Sie die Front-End-Pool oder Standard Edition-Server bereit.</p></li>
<li><p>Erstellen Sie bei Bedarf einen eigenständigen Vermittlungsserver und ordnen Sie ihn einem PSTN-Gateway zu.</p>
<div>

> [!NOTE]  
> Dieser Schritt ist nur erforderlich, wenn Sie Enterprise-VoIP nicht bereitstellen und die Vermittlungsserver nicht mit dem collocate Enterprise-EditionFront-Server oder Standard Edition-Server. Wenn Sie Enterprise-VoIP bereitstellen, werden im Rahmen der Enterprise-VoIP-Bereitstellung Vermittlungsserver und PSTN-Gateways installiert und konfiguriert. Wenn Sie die Vermittlungsserver collocate, installieren und konfigurieren Sie die Vermittlungsserver im Rahmen der Front-End-Pool-oder Standard Edition-Server-Bereitstellung.


</div></li>
</ol></td>
<td><p>Domänen-Admins</p>
<p>RTCUniversalServerAdmins</p>
<p>Administrator</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Bereitstellen von Lync Server 2013</a></p></li>
<li><p>So erstellen Sie einen eigenständigen Vermittlungsserver Pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Wähleinstellungen</strong></p></td>
<td><p>Wähleinstellungen sind ein Satz von Rufnummernnormalisierungsregeln, die von einem bestimmten Standort aus gewählte Rufnummern in ein einziges Standardformat (E.164) übersetzen, um die Telefonautorisierung und das Anrufrouting zu ermöglichen. Eine von verschiedenen Standorten aus gewählte Rufnummer kann je nach Wähleinstellungen dem Standort entsprechend in unterschiedliche E.164-Nummern aufgelöst werden. Wenn Sie Enterprise-VoIP bereitstellen, richten Sie Wählpläne als Teil dieser Bereitstellung ein, und Sie müssen sicherstellen, dass die Wählpläne auch Einwahlkonferenzen unterstützen. Wenn Sie Enterprise-VoIP nicht bereitstellen, müssen Sie Wähleinstellungen für Einwahlkonferenzen einrichten.</p>
<p>Verwenden Sie die lync Server 2013-Systemsteuerung oder lync Server-Verwaltungsshell, um Wählpläne wie folgt einzurichten:</p>
<ol>
<li><p>Erstellen Sie einen oder mehrere Sätze mit Wähleinstellungen zum Routen von Zugriffsnummern für die Einwahl.</p></li>
<li><p>Weisen Sie jedem Pool einen Standardsatz mit Wähleinstellungen zu. Legen Sie die <strong>Region für Einwahlkonferenzen</strong> auf den geografischen Standort fest, für den die Wähleinstellungen gelten. Die Region ordnet die Wähleinstellungen den Zugriffsnummern für die Einwahl zu.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Konfigurieren von Wählplänen für Einwahlkonferenzen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Sicherstellen, dass Wählplänen Regionen zugewiesen werden</strong></p></td>
<td><p>Führen Sie die Cmdlets <strong>Get-CsDialPlan</strong> und <strong>CsDialPlan</strong> aus, um sicherzustellen, dass allen Wählplänen eine Region zugewiesen ist.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Sicherstellen, dass den Wählplänen lync Server 2013 zugewiesene Regionen zugewiesen sind</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Überprüfen oder ändern Sie die Anforderungen an die persönliche Identifikationsnummer (PIN) der Benutzer.</strong></p></td>
<td><p>Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um die Konferenz- <strong>PIN-Richtlinie</strong>anzuzeigen oder zu ändern. Sie können eine PIN-Mindestlänge, eine maximale Anzahl von Anmeldeversuchen, ein PIN-Ablaufdatum und die Zulässigkeit gängiger Muster festlegen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Optional Überprüfen der PIN-Richtlinieneinstellungen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren Sie die Konferenzrichtlinie so, dass Einwahlkonferenzen unterstützt werden.</strong></p></td>
<td><p>Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um <strong>Konferenzrichtlinien</strong> Einstellungen zu konfigurieren. Legen Sie folgende Einstellungen fest:</p>
<ul>
<li><p>Die PSTN-Konferenzeinwahl ist aktiviert.</p></li>
<li><p>Benutzer können anonyme Teilnehmer einladen.</p></li>
<li><p>Nicht authentifizierte Benutzer können über ausgehende Telefonverbindungen an einer Konferenz teilnehmen. Bei ausgehenden Telefonverbindungen ruft der Konferenzserver den Benutzer an, und der Benutzer nimmt das Gespräch an, um an der Konferenz teilzunehmen.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Konfigurieren von Konferenzrichtlinien für die Einwahl in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren von Zugriffsnummern für die Einwahl</strong></p></td>
<td><p>Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um Zugriffsnummern für Einwahlen einzurichten, die von Benutzern bei der Einwahl in eine Konferenz aufgerufen werden, und geben Sie die Regionen an, die die Zugriffsnummer den entsprechenden Wählplänen zuordnen. Die ersten drei Zugriffsnummern für die Region, die durch die Wähleinstellungen des Organisators festgelegt wird, sind in der Konferenzeinladung enthalten. Alle Zugriffsnummern stehen im Seite "Einstellungen für Einwahlkonferenzen" zur Verfügung.</p>
<div>

> [!NOTE]  
> Nachdem Sie Zugriffsnummern für die Einwahl erstellt haben, können Sie das Cmdlet " <STRONG>CsDialInConferencingAccessNumber</STRONG> " verwenden, um den Anzeigenamen der Active Directory Contact-Objekte zu ändern, sodass Benutzer die richtige Zugriffsnummer einfacher identifizieren können.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Konfigurieren von Zugriffsnummern für Einwahlkonferenzen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Optional) Überprüfen der Einwahlkonferenzeinstellungen</strong></p></td>
<td><p>Suchen Sie mithilfe des Cmdlets <strong>Get-CsDialinConferencingAccessNumber</strong> nach Wähleinstellungen, deren Einwahlkonferenzregion von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern, denen keine Region zugeordnet ist.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p>
<p>"Cshelpdesk"</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Optional Überprüfen der Einstellungen für Einwahlkonferenzen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Ändern der Tastenzuordnung von DTMF-Befehlen</strong></p></td>
<td><p>Ändern Sie mithilfe des Cmdlets <strong>Set-CsDialinConferencingDtmfConfiguration</strong> die Tasten für DTMF-Befehle (Dual-Tone Multifrequency, Tonwahlverfahren), mit denen Teilnehmer Konferenzeinstellungen steuern können (z. B. die Stummschaltung bzw. Aufhebung der Stummschaltung oder die Sperre bzw. Aufheben der Sperre).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Optional Ändern der Tastenzuordnung für DTMF-Befehle in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(Optional) Ändern Sie das Ankündigungsverhalten beim Beitreten oder Verlassen einer Konferenz</strong></p></td>
<td><p>Ändern Sie mit dem Cmdlet <strong>Set-CsDialinConferencingConfiguration</strong> die Funktionsweise von Ankündigungen, wenn Teilnehmer einer Konferenz beitreten bzw. diese verlassen.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Optional Aktivieren und Deaktivieren von Konferenz Anmeldungen und Abwesenheits Ankündigungen in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Überprüfen von Einwahlkonferenzen</strong></p></td>
<td><p>Testen Sie mithilfe des Cmdlets <strong>Test-CsDialInConferencing</strong>, ob die Zugriffsnummern für den angegebenen Pool ordnungsgemäß funktionieren.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Optional Überprüfen von Einwahlkonferenzen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</strong></p></td>
<td><p>Stellen Sie das Online Besprechungs-Add-in für lync 2013 bereit, damit Benutzer Konferenzen planen können, die Einwahlkonferenzen unterstützen. Das Online Besprechungs-Add-in für lync 2013 wird automatisch installiert, wenn Sie lync 2013 installieren.</p></td>
<td><p>Administratoren</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Bereitstellen des Onlinebesprechungs-Add-Ins für Lync 2013</a></p></td>
</tr>
<tr class="even">
<td><p><strong>Konfigurieren der Benutzerkontoeinstellungen</strong></p></td>
<td><p>Verwenden Sie lync Server 2013 Systemsteuerung oder lync Server-Verwaltungsshell, um den URI der Telefon <strong>Leitung</strong> als eindeutige, normalisierte Telefonnummer zu konfigurieren (beispielsweise Tel: + 14255550200).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Konfigurieren von Benutzerkontoeinstellungen in lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Empfohlen Konfigurieren von Konferenz Verzeichnissen</p></td>
<td><p>Verwenden Sie das Cmdlet <strong>New-CsConferenceDirectory</strong> , um ein Konferenzverzeichnis für jeden 999-Benutzer im Pool zu erstellen.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Anforderungen für Einwahlkonferenzen in lync Server 2013</a> <a href="recommended-create-conference-directories.md">(empfohlen) Erstellen von Konferenz Verzeichnissen</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(Optional) Einladen von Benutzern zu Einwahlkonferenzen und Festlegen der anfänglichen PIN</strong></p></td>
<td><p>Verwenden Sie das Skript " <strong>CsPinSendCAWelcomeMail</strong> ", um die anfänglichen Pins der Benutzer festzulegen und eine Willkommens-e-Mail zu senden, die die anfängliche PIN und einen Link zum Seite "Einstellungen für Einwahlkonferenzen" enthält.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">Optional Begrüßen von Benutzern für Einwahlkonferenzen in lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

