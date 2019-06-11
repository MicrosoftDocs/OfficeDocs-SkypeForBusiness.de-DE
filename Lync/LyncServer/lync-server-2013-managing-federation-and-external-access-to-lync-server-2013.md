---
title: 'Lync Server 2013: Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8eb4dcf6a690e2bab7b834624fb0f695e3e770e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Verwalten von Partnerverbünden und externem Zugriff auf Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Die Bereitstellungeines Edgeserver oder eines Edge-Pools ist der erste Schritt zur Unterstützung externer Benutzer. Details zum Bereitstellen von Edge-Servern finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

Nach dem Installieren und Konfigurieren ihrer internen Bereitstellung von lync Server 2013 können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern zusammenarbeiten, die über SIP-Konten in Ihren Active Directory-Domänendiensten (AD DS) verfügen. Die Zusammenarbeit kann das Senden und empfangen von Sofortnachrichten sowie die Aktualisierung des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch bekannt als "Besprechungen") umfassen. Sie aktivieren und konfigurieren den Zugriff durch externe Benutzer, um zu steuern, ob unterstützte externe Benutzer mit internen lync Server-Benutzern zusammenarbeiten können. Externe Benutzer können Remotebenutzer Ihrer Bereitstellung, Verbundbenutzer (einschließlich unterstützter Benutzer von öffentlichen Instant Messaging (im)-Dienstanbietern), XMPP-Föderation und anonyme Teilnehmer an Konferenzen einbeziehen.

Wenn Ihre Bereitstellung die Installation eines lync Server 2013-Edge-Servers oder eines Edge-Pools enthielt, wird der Umfang möglicher Kommunikationstypen erheblich erweitert, wobei eine Reihe von Optionen für den Zugriff durch externe Benutzer, die Kommunikation mit Mitgliedern anderer SIP-Verbunddomänen, SIP-Verbund Anbieter und XMPP-Verbundbenutzer. Nachdem Sie den Edgeserver oder den Edge-Pool eingerichtet haben, aktivieren Sie die Typen des Zugriffs auf externe Benutzer, die Sie bereitstellen möchten, und konfigurieren die Richtlinien für die Steuerung für den externen Zugriff. In lync Server 2013 aktivieren und konfigurieren Sie den Zugriff auf externe Benutzer und Richtlinien mithilfe der lync Server-Systemsteuerung, der lync Server-Verwaltungsshell oder beides, basierend auf den Aufgabenanforderungen. Details zu diesen Verwaltungstools finden Sie unter [lync Server 2013-Verwaltungstools](lync-server-2013-lync-server-administrative-tools.md) in der Betriebsdokumentation, [lync Server 2013-Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation und [Installieren von lync Server 2013-Verwaltungstools. ](lync-server-2013-install-lync-server-administrative-tools.md)in der Betriebsdokumentation.

<div>


> [!IMPORTANT]  
> Wenn Sie Ihre Konfiguration und Richtlinien für den Zugriff durch externe Benutzer entwerfen, müssen Sie die Rangfolge der Richtlinien und die Anwendung der Richtlinien kennen. Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.



</div>

Standardmäßig sind keine Richtlinien für die Unterstützung des Zugriffs externer Benutzer konfiguriert, einschließlich des Remotebenutzerzugriffs, des Zugriffs auf den Verbundbenutzer, auch wenn Sie die Unterstützung für den externen Benutzer Zugriff für Ihre Organisation bereits aktiviert haben. Um die Verwendung des Zugriffs auf externe Benutzer zu steuern, müssen Sie eine oder mehrere Richtlinien konfigurieren und den Typ des für jede Richtlinie unterstützten externen Benutzerzugriffs angeben. Dazu gehören die folgenden Richtlinien für den externen Zugriff:

  - **Globale Richtlinie**   die globale Richtlinie wird erstellt, wenn Sie Ihre Edgeserver bereitstellen. Standardmäßig sind keine Optionen für den externen Benutzer Zugriff in der globalen Richtlinie aktiviert. Zur Unterstützung des Zugriffs externer Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass eine oder mehrere Arten von Zugriffsoptionen für externe Benutzer unterstützt werden. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, aber Website Richtlinien und Benutzerrichtlinien überschreiben die globale Richtlinie. Wenn Sie die globale Richtlinie löschen, werden Sie nicht entfernt. Stattdessen setzen Sie Sie auf die Standardeinstellung zurück.

  - **Website Richtlinie**   Sie können eine oder mehrere Website Richtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff externer Benutzer auf bestimmte Websites zu begrenzen. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, geben Sie möglicherweise eine Website Richtlinie an, die den Remotebenutzerzugriff für eine bestimmte Website deaktiviert. Standardmäßig wird eine Website Richtlinie auf alle Benutzer dieser Website angewendet, aber Sie können einem Benutzer eine Benutzerrichtlinie zuweisen, um die Website Richtlinieneinstellung zu überschreiben.

  - **Benutzerrichtlinie**   Sie können eine oder mehrere Benutzerrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch Remotebenutzer auf bestimmte Benutzer zu begrenzen. Die Konfiguration in der Benutzerrichtlinie überschreibt die globale und die Website Richtlinie, jedoch nur für bestimmte Benutzer, denen die Benutzerrichtlinie zugewiesen ist. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und der Website Richtlinie aktivieren, geben Sie möglicherweise eine Benutzerrichtlinie an, die den Zugriff durch Remotebenutzer deaktiviert und diese Benutzerrichtlinie dann bestimmten Benutzern zuweist. Wenn Sie eine Benutzerrichtlinie erstellen, müssen Sie Sie auf einen oder mehrere Benutzer anwenden, bevor Sie wirksam wird.

Wenn Sie feststellen möchten, welche Konfigurationseinstellungen und welche Richtlinien Sie erstellen oder bearbeiten müssen, lesen Sie die folgenden Entscheidungspunkte:

**Möchten Sie zulassen, dass interne und externe Benutzer Ihrer Domäne in der Lage sind, mithilfe von Instant Messaging, Webkonferenzen und Audio/Video zusammenzuarbeiten?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)und [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Möchten Sie zulassen, dass anonyme Benutzer teilnehmen und zu Konferenzen eingeladen werden, die von Benutzern in Ihrer Bereitstellung gehostet werden?**

Konfigurieren Sie die Einstellungen wie im Thema [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [Referenz für konferenzrichtlinieneinstellungen für lync. Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbunddomänen Kontakten gestatten?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)und [Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

**Wenn Sie die Kommunikation mit SIP-Verbunddomänen aktiviert haben, möchten Sie die Kommunikation mit XMPP-Partner Kontakten aktivieren?**

Konfigurieren Sie die Einstellungen wie im Thema [Konfigurieren von Richtlinien zum Steuern des XMPP-Verbundbenutzer Zugriffs in lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) und [Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md).

**Wenn Sie die Kommunikation mit SIP-Verbunddomänen aktiviert haben, möchten Sie die automatische Erkennung von SIP-Föderationen aktivieren?**

Konfigurieren Sie die Einstellungen, wie im Thema [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)beschrieben.

**Wenn Sie die Kommunikation mit SIP-Föderationsdomänen aktiviert haben, möchten Sie das Senden einer Verzichtserklärung an Föderations Kontakte aktivieren, die Sie darüber informiert, dass Sie die Archivierung verwenden und die Kommunikation archiviert werden kann?**

Konfigurieren Sie die Einstellungen wie im Thema [Aktivieren oder Deaktivieren des Sendens von Archivierungs verzichten an Verbundpartner in lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)beschrieben.

**Möchten Sie Benutzern die Kommunikation mit SIP-Verbund Anbietern gestatten, die die Kommunikation mit öffentlichen Anbietern wie Windows Live Messenger, AOL und Yahoo\!ermöglichen?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs öffentlicher Benutzer in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md), und [erstellen oder Bearbeiten von öffentlichen SIP-Föderationen Anbieter in lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md).

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für die Föderation von lync Server oder Office Communications Server mit Yahoo! erforderlich ist. Messenger. Die Möglichkeit von Microsoft, diesen Dienst bereitzustellen, war von der Unterstützung durch Yahoo! abhängig, deren zugrunde liegende Vereinbarung abgewickelt wird.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen Organisationen und Personen in der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-und Gerätelizenzen außerhalb der lync-Standard CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt und ermöglicht es lync-Benutzern, Hunderte von Millionen von Personen mit Chat und Sprache zu erreichen.</P></LI></UL>



</div>

**Möchten Sie zulassen, dass Benutzer mit SIP-Verbund Anbietern kommunizieren, bei denen es sich um gehostete Anbieter mit Microsoft Office 365, Microsoft lync Online und Microsoft lync Online 2010 handelt?**

Konfigurieren Sie die Einstellungen wie in den Themen [erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern Lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**Ist Ihre Bereitstellung in einer geteilten (auch als Hybrid bezeichneten) Domäne konfiguriert, in der einige Benutzer über Ihren Homeserver in einer lokalen Bereitstellung verfügen und andere Benutzer mit einem Homeserver in einer Online Umgebung konfiguriert sind?**

Konfigurieren Sie die Einstellungen wie in den Themen [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen Chat Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [erstellen oder Bearbeiten einer gehosteten SIP-Föderation Anbieter lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

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
<th>Registerkarte in Föderations-und externer Zugriff (Across) Federation oder externer Zugriffstyp (nach unten)</th>
<th>Richtlinie für den externen Zugriff</th>
<th>Access-Edge-Konfiguration</th>
<th>SIP-Verbunddomänen</th>
<th>SIP-Partnerverbundanbieter</th>
<th>XMPP-Verbund Partner</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Remotebenutzer</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP-Verbund Kontakte</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Suche von Verbundpartnern in Lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Aktivieren oder Deaktivieren des Versands eines Archivierungshaftungsausschlusses an Verbundpartner in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP-Verbund Kontakte</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Partnerbenutzer in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Teilen von Domänen/Hybrid Benutzern</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Partnerbenutzerzugriffs in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbundanbietern in Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Kontakte im öffentlichen Chatdienst</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in Lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren des Partnerverbunds und der Konnektivität mit öffentlichen Chatdiensten in Lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Partnerverbundanbietern in Lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Anonymer Benutzer Zugriff auf Besprechungen und Konferenzen</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013</a></p>
<div>

> [!NOTE]  
> Darüber hinaus müssen Sie die folgenden Konfigurationseinstellungen unter Konferenzrichtlinien beachten: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013</A> und <A href="lync-server-2013-conferencing-policy-settings-reference.md">Konferenzrichtlinien Einstellungsreferenz für lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Sie können Einstellungen für den externen Benutzer Zugriff konfigurieren, einschließlich aller Richtlinien, die Sie zum Steuern des Zugriffs auf externe Benutzer verwenden möchten, auch wenn Sie den Zugriff auf externe Benutzer für Ihre Organisation nicht aktiviert haben. Die Richtlinien und anderen Einstellungen, die Sie konfigurieren, sind jedoch nur wirksam, wenn der Zugriff auf externe Benutzer für Ihre Organisation aktiviert ist. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der Zugriff auf externe Benutzer deaktiviert ist oder wenn keine Richtlinien für den externen Benutzer Zugriff für die Unterstützung konfiguriert sind.

Ihre Edge-Bereitstellung authentifiziert die Typen externer Benutzer (mit Ausnahme von anonymen Benutzern, die von der Konferenz-ID authentifiziert werden, und einem Kennwort, das an den anonymen Teilnehmer gesendet wird, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und Steuerelemente Access basiert auf der Konfiguration Ihrer Edge-Unterstützung. Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren und Einstellungen konfigurieren, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die standardmäßige globale Richtlinie für den Zugriff durch externe Benutzer sowie Website-und Benutzerrichtlinien, die Sie erstellen und konfigurieren können, um einen oder mehrere Typen von externen Benutzer Zugriff für bestimmte Websites oder Benutzer zu ermöglichen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Verwalten von Richtlinien für den externen Zugriff für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Verwalten der Konfiguration des Zugriffsedge für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Verwalten von SIP-Partnerdomänen für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Verwalten von SIP-Partnerverbundanbietern für eine Organisation in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Verwalten von XMPP-Verbundpartnern für Ihre Organisation in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Konfigurieren der Verbundunterstützung für einen lync Online-Kunden in lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

