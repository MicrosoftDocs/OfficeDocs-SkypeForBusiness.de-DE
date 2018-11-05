---
title: 'Lync Server 2013: Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013'
TOCTitle: Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg520966(v=OCS.15)
ms:contentKeyID: 49293474
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Bereitstellung eines Edgeservers oder Edgepools ist der erste Schritt zur Unterstützung externer Benutzer. Ausführliche Informationen zur Bereitstellung von Edgeservern finden Sie unter [Bereitstellen des Zugriffs durch externe Benutzer in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

Nach der Installation und Konfiguration Ihrer internen Lync Server 2013-Bereitstellung können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern zusammenarbeiten, die über SIP-Konten in den Active Directory-Domänendiensten (Active Directory Domain Services, AD DS) verfügen. Die Zusammenarbeit kann das Senden und Empfangen von Chatnachrichten, die Aktualisierung des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch als "Besprechungen" bezeichnet) umfassen. Sie aktivieren und konfigurieren den Zugriff durch externe Benutzer und steuern, ob unterstützte externe Benutzer mit internen Lync Server zusammenarbeiten können. Zu den externen Benutzern können Remotebenutzer in Ihrer Bereitstellung, Partnerbenutzer (einschließlich unterstützter Benutzer öffentlicher Instant Messaging-Dienstanbieter), sowie XMPP-Partnerverbund- und anonyme Teilnehmer an Konferenzen gehören.

Wenn Ihre Bereitstellung die Installation eines Lync Server 2013-Edgeservers oder -Edgepools umfasst, kann der Bereich der möglichen Kommunikationstypen durch eine Reihe von Optionen für den externen Benutzerzugriff, die Kommunikation mit Mitgliedern anderer SIP-Partnerverbunddomänen, SIP-Partnerverbundanbietern und XMPP-Partnerbenutzern erheblich erweitert werden. Nach der Einrichtung des Edgeservers oder Edgepools können Sie die Arten des externen Benutzerzugriffs aktivieren, die Sie bereitstellen möchten. Zudem können Sie die Richtlinien zum Steuern des externen Zugriffs konfigurieren. In Lync Server 2013 können Sie basierend auf den Aufgabenanforderungen den externen Benutzerzugriff und die dazugehörigen Richtlinien mit der Lync Server-Systemsteuerung, der Lync Server-Verwaltungsshell oder mit beiden aktivieren und konfigurieren. Detaillierte Informationen zu diesen Verwaltungstools finden Sie unter [Lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md) in der Betriebsdokumentation, [Lync Server-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation und [Installieren von Lync Server 2013-Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md) in der Betriebsdokumentation.


> [!IMPORTANT]
> Beim Entwerfen der Konfiguration und der Richtlinien für externen Benutzerzugriff müssen Sie die Rangfolge der Richtlinien verstehen und wissen, wie Richtlinien angewendet werden. Lync Server-Richtlinieneinstellungen, die auf einer bestimmten Richtlinienebene angewendet werden, können durch Einstellungen überschrieben werden, die auf einer anderen Richtlinienebene angewendet werden. Dabei gilt folgende Rangfolge: Benutzerrichtlinien (größter Einfluss) überschreiben Standortrichtlinien, und diese überschreiben wiederum globale Richtlinien (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.



Standardmäßig werden keine Richtlinien zur Unterstützung des Zugriffs durch externe Benutzer konfiguriert, einschließlich des Zugriffs durch Remotebenutzer und durch Partnerbenutzer, auch dann nicht, wenn Sie die Unterstützung für den Zugriff durch externe Benutzer bereits für Ihre Organisation aktiviert haben. Zur Steuerung des Zugriffs durch externe Benutzer müssen Sie eine oder mehrere Richtlinien konfigurieren und den für jede Richtlinie unterstützten Typ des externen Benutzerzugriffs angeben. Hierzu gehören die folgenden Richtlinien für den externen Zugriff:

  - **Globale Richtlinie :** Diese Richtlinie wird erstellt, wenn Sie Ihre Edge-Server bereitstellen. Optionen für den Zugriff durch externe Benutzer sind in der globalen Richtlinie zunächst nicht aktiviert. Um den Zugriff durch externe Benutzer auf globaler Ebene zu unterstützen, konfigurieren Sie die entsprechende Richtlinie, sodass eine oder mehrere Optionen für den Zugriff durch externe Benutzer unterstützt werden. Die globale Richtlinie wird für alle Benutzer in der Organisation verwendet. Sie kann jedoch durch Standortrichtlinien und Benutzerrichtlinien überschrieben werden. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt, sondern auf die Standardeinstellung zurückgesetzt.

  - **Standortrichtlinie :** Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um den Zugriff für externe Benutzer auf bestimmte Standorte zu beschränken. Die Konfiguration der Standortrichtlinie überschreibt die globale Richtlinie. Dies gilt jedoch nur für den in der entsprechenden Richtlinie angegebenen Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet. Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.

  - **Benutzerrichtlinie :** Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um den Remotebenutzerzugriff auf bestimmte Benutzer zu beschränken. Die Konfiguration der Benutzerrichtlinie überschreibt die globale Richtlinie und die Standortrichtlinie. Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen. Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.

Anhand der folgenden Entscheidungspunkte können Sie ermitteln, welche Konfigurationseinstellungen und Richtlinien Sie erstellen oder bearbeiten müssen:

**Möchten Sie internen und externen Benutzern Ihrer Domänen die Zusammenarbeit per Chat, Webkonferenzen und Audio/Video erlauben?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) und [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) erläutert.

**Möchten Sie zulassen, dass anonyme Benutzer an Konferenzen teilnehmen können, die von Benutzern in Ihrer Bereitstellung gehostet werden?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [Referenz zu den Konferenzrichtlinieneinstellungen](lync-server-2013-conferencing-policy-settings-reference.md) beschrieben.

**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbunddomänen-Kontakten erlauben?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md) beschrieben.

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie die Kommunikation mit XMPP-Verbundpartnerkontakten erlauben?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) und [Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) beschrieben.

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie die automatische Ermittlung des SIP-Partnerverbunds aktivieren?**

Konfigurieren Sie die Einstellungen, so wie im Thema [Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md) erläutert.

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie das Senden eines Haftungsausschlusses an die Partnerverbundkontakte aktivieren, um sie über eine mögliche Archivierung der Kommunikation zu informieren?**

Konfigurieren Sie die Einstellungen, so wie im Thema [Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md) erläutert.

**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbundanbietern erlauben, die die Kommunikation mit öffentlichen Anbietern ermöglichen, z. B. Windows Live Messenger, AOL und Yahoo\!?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md) beschrieben.


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbundanbietern erlauben, bei denen es sich um gehostete Anbieter handelt, die Microsoft Office 365, Microsoft Lync Online und Microsoft Lync Online 2010 ausführen?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) beschrieben.

**Ist Ihre Domäne als geteilte Domäne (auch als Hybridomäne bezeichnet) konfiguriert, in der einige Benutzer einen Homeserver in einer lokalen Bereitstellung haben und für andere Benutzer ein Homeserver in einer Onlineumgebung konfiguriert ist?**

Konfigurieren Sie die Einstellungen, so wie in den Themen [Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) beschrieben.

Wenn Sie eine Tabelle bevorzugen, in der die Anforderungen aufgelistet sind:


<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Registerkarte für Partnerverbund und externen Zugriff (quer) Verbund- oder externer Zugriffstyp (senkrecht)</th>
<th>Richtlinie für den externen Zugriff</th>
<th>Konfiguration für Zugriffsedge</th>
<th>SIP-Partnerverbunddomänen</th>
<th>SIP-Partnerverbundanbieter</th>
<th>XMPP-Verbundpartner</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Remotebenutzer</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>SIP-Partnerverbundkontakte</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</a></p>
<p></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>XMPP-Partnerverbundkontakte</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Geteilte Domäne/Hybridbenutzer</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Kontakte für öffentlichen Instant Messaging-Dienst</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Anonymer Benutzerzugriff auf Besprechungen und Konferenzen</p></td>
<td><p></p></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013</a></p>
<div>

> [!NOTE]
> Zudem müssen Sie die folgenden Konfigurationseinstellungen unter <STRONG>Konferenzrichtlinien</STRONG> beachten: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">Erstellen oder Ändern einer Konferenzrichtlinie in Lync Server 2013</A> und <A href="lync-server-2013-conferencing-policy-settings-reference.md">Referenz zu den Konferenzrichtlinieneinstellungen</A>


</div></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


Sie können auch dann Einstellungen für den Zugriff externer Benutzer konfigurieren, wenn Sie den externen Benutzerzugriff für Ihre Organisation nicht aktiviert haben. Hierzu gehören auch Richtlinien, die Sie zum Steuern des externen Benutzerzugriffs verwenden möchten. Die von Ihnen konfigurierten Richtlinien und anderen Einstellungen treten jedoch erst in Kraft, wenn der externe Benutzerzugriff für Ihre Organisation aktiviert wird. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der externe Benutzerzugriff deaktiviert ist oder wenn keine Richtlinien für den externen Benutzerzugriff konfiguriert wurden.

Ihre Edgebereitstellung authentifiziert die Typen externer Benutzer (außer Benutzer, die mit der Konferenz-ID und dem an den anonymen Teilnehmer übermittelten Hauptschlüssel identifiziert werden, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und steuert den Zugriff basierend auf der Konfiguration der Edgeunterstützung. Zum Steuern der Kommunikation können Sie eine oder mehrere Richtlinien sowie Einstellungen konfigurieren, durch die definiert wird, wie Benutzer innerhalb und außerhalb der Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die globale Standardrichtlinie für den externen Benutzerzugriff sowie Richtlinien auf Standort- und Benutzerebene, die Sie zum Aktivieren eines oder mehrerer Typen des externen Benutzerzugriffs für bestimmte Standorte oder Benutzer erstellen und konfigurieren können.

## In diesem Abschnitt

  - [Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Konfigurieren der Unterstützung für einen Partnerverbund mit einem Lync Online-Kunden](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

