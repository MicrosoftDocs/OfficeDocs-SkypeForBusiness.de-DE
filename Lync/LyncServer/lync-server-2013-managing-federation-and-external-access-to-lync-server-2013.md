---
title: 'Lync Server 2013: Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing federation and external access to Lync Server 2013
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 155ee98a7386368d90fd549d920cdfe77c05cb6e
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-federation-and-external-access-to-lync-server-2013"></a>Verwalten des Verbunds und des externen Zugriffs auf lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-10-07_

Die Bereitstellung eines Edgeservers oder Edgepools ist der erste Schritt zur Unterstützung externer Benutzer. Ausführliche Informationen zum Bereitstellen von Edge-Servern finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation.

Nach der Installation und Konfiguration Ihrer internen Bereitstellung von lync Server 2013 können interne Benutzer in Ihrer Organisation mit anderen internen Benutzern mit SIP-Konten in Ihrem Active Directory-Domänendienste (AD DS) zusammenarbeiten. Die Zusammenarbeit kann das Senden und Empfangen von Chatnachrichten, die Aktualisierung des Anwesenheitsstatus und die Teilnahme an Konferenzen (auch als "Besprechungen" bezeichnet) umfassen. Sie aktivieren und konfigurieren den Zugriff durch externe Benutzer, um zu steuern, ob unterstützte externe Benutzer mit internen lync Server Benutzern zusammenarbeiten können. Zu den externen Benutzern können Remotebenutzer in Ihrer Bereitstellung, Partnerbenutzer (einschließlich unterstützter Benutzer öffentlicher Chatdienstanbieter), sowie XMPP-Partnerverbund- und anonyme Teilnehmer an Konferenzen gehören.

Wenn Ihre Bereitstellung die Installation eines lync Server 2013 Edgeserver oder eines Edgepool umfasste, wird der Umfang möglicher Kommunikationstypen mit einer Reihe von Optionen für den Zugriff durch externe Benutzer, die Kommunikation mit Mitgliedern anderer SIP-Verbunddomänen, SIP-Verbund Anbietern und XMPP-Verbundbenutzern erheblich erweitert. Nachdem Sie die Edgeserver oder Edgepool eingerichtet haben, aktivieren Sie die Typen des externen Benutzerzugriffs, den Sie bereitstellen möchten, und konfigurieren Sie die Richtlinien für die Steuerung für den externen Zugriff. In lync Server 2013 aktivieren und konfigurieren Sie den Zugriff und die Richtlinien für externe Benutzer mithilfe der lync Server-Systemsteuerung, der lync Server-Verwaltungsshell oder beider basierend auf den Aufgabenanforderungen. Ausführliche Informationen zu diesen Verwaltungstools finden Sie unter [lync Server 2013 Administrative Tools](lync-server-2013-lync-server-administrative-tools.md) in der Betriebsdokumentation [lync Server 2013 Verwaltungsshell](lync-server-2013-lync-server-management-shell.md) in der Betriebsdokumentation und Installieren von [lync Server 2013 Verwaltungstools](lync-server-2013-install-lync-server-administrative-tools.md) in der Betriebsdokumentation.

<div>


> [!IMPORTANT]  
> Beim Entwerfen der Konfiguration und der Richtlinien für externen Benutzerzugriff müssen Sie die Rangfolge der Richtlinien verstehen und wissen, wie Richtlinien angewendet werden. Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft. Dies bedeutet Folgendes: Je näher sich die Richtlinieneinstellung am betroffenen Objekt befindet, umso mehr Einfluss auf das Objekt hat sie.



</div>

Standardmäßig werden keine Richtlinien zur Unterstützung des Zugriffs durch externe Benutzer konfiguriert, einschließlich des Zugriffs durch Remotebenutzer und durch Partnerbenutzer, auch dann nicht, wenn Sie die Unterstützung für den Zugriff durch externe Benutzer bereits für Ihre Organisation aktiviert haben. Zur Steuerung des Zugriffs durch externe Benutzer müssen Sie eine oder mehrere Richtlinien konfigurieren und den für jede Richtlinie unterstützten Typ des externen Benutzerzugriffs angeben. Hierzu gehören die folgenden Richtlinien für den externen Zugriff:

  - **Globale Richtlinie**   Die globale Richtlinie wird bei der Bereitstellung der Edgeserver erstellt. Standardmäßig sind in der globalen Richtlinie keine Optionen für den externen Benutzerzugriff aktiviert. Zur Unterstützung des Zugriffs durch externe Benutzer auf globaler Ebene konfigurieren Sie die globale Richtlinie so, dass mindestens ein Typ des externen Benutzerzugriffs unterstützt wird. Die globale Richtlinie gilt für alle Benutzer in Ihrer Organisation, wird jedoch durch Standort- und Benutzerrichtlinien außer Kraft gesetzt. Wenn Sie die globale Richtlinie löschen, wird diese nicht entfernt. Stattdessen wird sie auf die Standardeinstellung zurückgesetzt.

  - **Standortrichtlinie**   Sie können eine oder mehrere Standortrichtlinien erstellen und konfigurieren, um die Unterstützung für den Zugriff durch externe Benutzer auf bestimmte Standorte einzuschränken. Die Konfiguration in der Standortrichtlinie setzt die globale Richtlinie außer Kraft, jedoch nur für den durch die Standortrichtlinie abgedeckten Standort. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie aktivieren, können Sie eine Standortrichtlinie festlegen, die den Remotebenutzerzugriff für einen bestimmten Standort deaktiviert. Standardmäßig wird eine Standortrichtlinie auf alle Benutzer des jeweiligen Standorts angewendet, Sie können jedoch einem Benutzer eine Benutzerrichtlinie zuweisen, um die Standortrichtlinieneinstellung außer Kraft zu setzen.

  - **Benutzerrichtlinie**   Die Konfiguration der Benutzerrichtlinie überschreibt die globale Richtlinie und die Standortrichtlinie. Dies gilt jedoch nur für die von der entsprechenden Richtlinie betroffenen Benutzer. Wenn Sie beispielsweise den Remotebenutzerzugriff in der globalen Richtlinie und in der Standardrichtlinie aktivieren, können Sie eine Benutzerrichtlinie festlegen, die den Remotebenutzerzugriff deaktiviert, und diese Richtlinie bestimmten Benutzern zuweisen. Benutzerrichtlinien werden erst mit der Zuweisung zu bestimmten Benutzern wirksam.

Anhand der folgenden Entscheidungspunkte können Sie ermitteln, welche Konfigurationseinstellungen und Richtlinien Sie erstellen oder bearbeiten müssen:

**Möchten Sie internen und externen Benutzern Ihrer Domänen die Zusammenarbeit per Chat, Webkonferenzen und Audio/Video erlauben?**

Konfigurieren Sie die Einstellungen wie in den Themen [configure Policies to Control Remote User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)beschrieben, und [Aktivieren oder deaktivieren Sie die Verbund-und Public Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

**Möchten Sie zulassen, dass anonyme Benutzer an Konferenzen teilnehmen können, die von Benutzern in Ihrer Bereitstellung gehostet werden?**

Konfigurieren Sie die Einstellungen wie im Thema [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md), [erstellen oder Ändern einer konferenzrichtlinie unter lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md) und [konferenzrichtlinieneinstellungen (Referenz für lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md) ) beschrieben.

**Möchten Sie Benutzern die Kommunikation mit SIP-Partnerverbunddomänen-Kontakten erlauben?**

Konfigurieren Sie die Einstellungen wie in den Themen [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und Public-Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)und [Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md) beschrieben.

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie die Kommunikation mit XMPP-Verbundpartnerkontakten erlauben?**

Konfigurieren Sie die Einstellungen wie im Thema [configure Policies to Control XMPP Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md) und [Manage XMPP Federated Partners in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)beschrieben.

**Wenn Sie die Kommunikation mit SIP-Verbunddomänen aktiviert haben, möchten Sie die automatische Erkennung für den SIP-Verbund aktivieren?**

Konfigurieren Sie die Einstellungen wie im Thema [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)beschrieben.

**Wenn Sie die Kommunikation mit SIP-Partververbunddomänen aktiviert haben, möchten Sie das Senden eines Haftungsausschlusses an die Partnerverbundkontakte aktivieren, um sie über eine mögliche Archivierung der Kommunikation zu informieren?**

Konfigurieren Sie die Einstellungen wie im Thema [Aktivieren oder Deaktivieren des Sendens eines Archivierungs Disclaimers an Verbundpartner in lync Server 2013](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)beschrieben.

**Möchten Sie, dass Benutzer mit SIP-Verbund Anbietern kommunizieren können, die die Kommunikation mit öffentlichen Anbietern wie Windows Live Messenger, AOL und Yahoo ermöglichen \! ?**

Konfigurieren Sie die Einstellungen wie in den Themen [configure Policies to Control Public User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-public-user-access.md)[Aktivieren oder Deaktivieren von Verbund-und Public Chat-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)und [erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)beschrieben.

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P>
> <LI>
> <P>Bei der PIC-USL handelt es sich um eine Abonnementlizenz pro Benutzer pro Monat, die für lync Server oder Office Communications Server für die Zusammensetzung mit Yahoo! erforderlich ist. Messenger. Die Fähigkeit von Microsoft, diesen Dienst bereitzustellen, wurde von der Unterstützung von Yahoo! abhängig gemacht, die zugrunde liegende Vereinbarung, für die die Rückabwicklung erfolgt.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsfähiges Tool für die Verbindung zwischen verschiedenen Organisationen und mit Einzelpersonen auf der ganzen Welt. Für den Verbund mit Windows Live Messenger sind keine zusätzlichen Benutzer-/Gerätelizenzen außerhalb der lync-Standard-CAL erforderlich. Skype Federation wird dieser Liste hinzugefügt, sodass lync-Benutzer Hunderte Millionen von Benutzern mit Chat und VoIP erreichen können.</P></LI></UL>



</div>

**Möchten Sie, dass Benutzer mit SIP-Verbund Anbietern kommunizieren können, die gehostete Anbieter mit Microsoft 365, Microsoft lync Online und Microsoft lync Online 2010 sind?**

Konfigurieren Sie die Einstellungen wie in den Themen [erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)beschrieben, [Aktivieren oder deaktivieren Sie die Verbund-und öffentliche Instant Messaging-Konnektivität in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) , und [erstellen oder bearbeiten Sie gehostete SIP-Verbund Anbieter lync Server 2013](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md)

**Ist Ihre Domäne als geteilte Domäne (auch als Hybridomäne bezeichnet) konfiguriert, in der einige Benutzer einen Homeserver in einer lokalen Bereitstellung haben und für andere Benutzer ein Homeserver in einer Onlineumgebung konfiguriert ist?**

Konfigurieren Sie die Einstellungen wie in den Themen [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md), [Aktivieren oder Deaktivieren von Verbund-und öffentlichen im-Verbindungen in lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) und [erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern](lync-server-2013-create-or-edit-hosted-sip-federated-providers.md) detailliert beschrieben lync Server 2013

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
<th>Registerkarte im Verbund und externem Zugriff (Across) oder externem Zugriffstyp (unten)</th>
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
<td><p><a href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Remotebenutzerzugriffs in lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</a></p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>SIP-Partnerverbundkontakte</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-discovery-of-federation-partners.md">Aktivieren oder Deaktivieren der Ermittlung von Partnerverbund Partnern in lync Server 2013</a></p>
<p><a href="lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md">Aktivieren oder Deaktivieren des Sendens von Archivierungs Haftungsausschlüssen an Verbundpartner in lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013</a></p></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>XMPP-Partnerverbundkontakte</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch XMPP-Verbundbenutzer in lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></td>
<td></td>
<td></td>
<td><p><a href="lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md">Verwalten von XMPP-Verbundpartnern in lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Geteilte Domäne/Hybridbenutzer</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Konfigurieren von Richtlinien zur Steuerung des Zugriffs von Verbundbenutzern in lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-hosted-sip-federated-providers.md">Erstellen oder Bearbeiten von gehosteten SIP-Verbund Anbietern lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Kontakte für öffentlichen Chatdienst</p></td>
<td><p><a href="lync-server-2013-configure-policies-to-control-public-user-access.md">Konfigurieren von Richtlinien zur Steuerung des öffentlichen Benutzerzugriffs in lync Server 2013</a></p></td>
<td><p><a href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">Aktivieren oder Deaktivieren der Verbund-und Public Chat-Konnektivität in lync Server 2013</a></p></td>
<td></td>
<td><p><a href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">Erstellen oder Bearbeiten von öffentlichen SIP-Verbund Anbietern in lync Server 2013</a></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Anonymer Benutzerzugriff auf Besprechungen und Konferenzen</p></td>
<td></td>
<td><p><a href="lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md">Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013</a></p>
<div>

> [!NOTE]  
> Außerdem müssen Sie die folgenden Konfigurationseinstellungen unter Konferenzrichtlinien beachten: <A href="lync-server-2013-create-or-modify-a-conferencing-policy.md">erstellen oder Ändern einer konferenzrichtlinie in lync Server 2013</A> <A href="lync-server-2013-conferencing-policy-settings-reference.md">Referenz für konferenzrichtlinieneinstellungen für lync Server 2013</A>


</div></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


Sie können auch dann Einstellungen für den Zugriff externer Benutzer konfigurieren, wenn Sie den externen Benutzerzugriff für Ihre Organisation nicht aktiviert haben. Hierzu gehören auch Richtlinien, die Sie zum Steuern des externen Benutzerzugriffs verwenden möchten. Die von Ihnen konfigurierten Richtlinien und anderen Einstellungen treten jedoch erst in Kraft, wenn der externe Benutzerzugriff für Ihre Organisation aktiviert wird. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der externe Benutzerzugriff deaktiviert ist oder wenn keine Richtlinien für den externen Benutzerzugriff konfiguriert wurden.

Ihre Edgebereitstellung authentifiziert die Typen externer Benutzer (außer Benutzer, die mit der Konferenz-ID und dem an den anonymen Teilnehmer übermittelten Hauptschlüssel identifiziert werden, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und steuert den Zugriff basierend auf der Konfiguration der Edgeunterstützung. Zum Steuern der Kommunikation können Sie eine oder mehrere Richtlinien sowie Einstellungen konfigurieren, durch die definiert wird, wie Benutzer innerhalb und außerhalb der Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die globale Standardrichtlinie für den externen Benutzerzugriff sowie Richtlinien auf Standort- und Benutzerebene, die Sie zum Aktivieren eines oder mehrerer Typen des externen Benutzerzugriffs für bestimmte Standorte oder Benutzer erstellen und konfigurieren können.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Verwalten von Richtlinien für den externen Zugriff in lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md)

  - [Verwalten der Zugriffs-Edge-Konfiguration für Ihre Organisation in lync Server 2013](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)

  - [Verwalten von SIP-Verbunddomänen für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)

  - [Verwalten von SIP-Verbund Anbietern für Ihre Organisation in lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

  - [Verwalten von XMPP-Verbundpartnern in lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)

  - [Konfigurieren der Verbundunterstützung für einen lync Online Kunden in lync Server 2013](lync-server-2013-configuring-federation-support-for-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

