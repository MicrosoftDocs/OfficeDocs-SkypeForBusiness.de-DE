---
title: 'Konferenzen: Allgemeine Konzepte'
TOCTitle: 'Konferenzen: Allgemeine Konzepte'
ms:assetid: a21d4987-1c0a-44c8-8a39-9c17ffb57f3c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688158(v=OCS.15)
ms:contentKeyID: 49890868
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konferenzen: Allgemeine Konzepte

 

_**Letztes Änderungsdatum des Themas:** 2012-09-19_

Es gibt mehrere Konzepte, die für sämtliche Konferenztypen verwendet werden. Diese werden in den folgenden Abschnitten beschrieben.

## Richtlinien und Bandbreitenverwaltung

Lync Server 2013 ermöglicht Administratoren das Festlegen von Richtlinien für die Besprechungstypen, die die Benutzer organisieren können. Auf diese Weise können Sie die in Ihrer Organisation geltenden Richtlinien durchsetzen und die Bandbreitennutzung steuern. Sie können eine Vielzahl von Besprechungsrichtlinien definieren und diese einzelnen Benutzern und Benutzergruppen zuweisen. Ferner können Sie Richtlinien festlegen, die Peer-zu-Peer-Unterhaltungen steuern. Ausführliche Informationen zum Festlegen von Konferenzrichtlinien finden Sie unter [Konferenzrichtlinien in Lync Server 2013](lync-server-2013-conferencing-policies.md) in der Betriebsdokumentation. Einzelheiten zur Bandbreitenverwaltung finden Sie unter [Übersicht über die Anrufsteuerung in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md) und [Konfigurieren der Videobandbreite in Lync Server 2013](lync-server-2013-configuring-video-bandwidth.md).

## Funktionen zur Archivierung und Einhaltung von Bestimmungen

Lync Server 2013 bietet Funktionen, mit denen Ihre Organisation rechtliche Vorschriften einhalten kann, sofern dies erforderlich ist. Mithilfe der Archivierungsfunktionen können Sie in Besprechungen präsentierte Inhalte sowie die Inhalte von Sofortnachrichtenunterhaltungen und Sofortnachrichtenkonferenzen archivieren. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation. Mit den Funktionen zur Einhaltung von Bestimmungen des dauerhaften Chatservers können Sie themenbasierte Konversationen mit mehreren Teilnehmern archivieren, die im Verlauf erhalten bleiben. Ausführliche Informationen dazu finden Sie unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md) in der Planungsdokumentation.

## Überwachungsfunktion

Die Monitoring Server-Funktion kann Kommunikationsdatensätze (KDS) erfassen, mit deren Hilfe Sie nachverfolgen können, welche Benutzer sich mit Lync Server 2013 mit welchen anderen Benutzern unterhalten. Einzelheiten zum Bereitstellen und Konfigurieren der Überwachung finden Sie unter [Bereitstellen des Monitoring Servers](lync-server-2013-deploying-monitoring.md).

## Aktivieren der Konferenzteilnahme durch externe Benutzer

Sie können Ihre Investition in die Lync Server 2013-Konferenzfunktion maximieren, indem Sie die Besprechungsteilnahme durch externe Benutzer zulassen, wenn diese zu Konferenzen eingeladen werden. Bei externen Benutzern handelt es sich u. a. um folgende Benutzertypen:

  - **Remotebenutzer** Benutzer Ihrer Organisation, die außerhalb der Organisationsfirewalls arbeiten und Laptops oder andere Lync Server 2013-Geräte verwenden.

  - **Partnerbenutzer** Benutzer aus Unternehmen, mit denen Sie zusammenarbeiten und die Lync Server 2013 ebenfalls ausführen. Damit Ihre Benutzer diese Benutzer problemlos kontaktieren können, erstellen Sie Partnerverbundbeziehungen mit diesen Unternehmen.

  - **Anonyme Benutzer** Alle anderen externen Benutzer, die von Ihren Benutzern zur Teilnahme an bestimmten Konferenzen eingeladen werden. Der Organisator einer Besprechung in Ihrem Unternehmen kann eine E-Mail-Einladung für eine Konferenz an einen externen Benutzer senden. Diese E-Mail enthält einen Link, über den der externe Benutzer an der Konferenz teilnehmen kann.

Zum Aktivieren eines oder aller dieser Szenarien müssen Sie einen Edgeserver für die sichere Kommunikation zwischen Ihrer Lync Server 2013-Bereitstellung und externen Benutzern bereitstellen. Die Lync Server 2013-Lösung mit Edgeservern bietet eine höhere Medienqualität als andere Lösungen (wie z. B. virtuelle private Netzwerke). Ausführliche Informationen finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).

Unabhängig davon, ob Sie Edgeserver bereitstellen oder nicht, können Sie für Benutzer (innerhalb oder außerhalb Ihrer Organisationen) zudem die Einwahl über standardmäßige Festnetztelefone zulassen, um an lokalen Audiokonferenzen teilzunehmen. Zu diesem Zweck werden Lync Server 2013-Einwahlkonferenzen bereitgestellt.

## Kompatibilität zwischen Besprechungstypen und Clientversionen

Wenn Sie Lync Server 2013 mit vorherigen Versionen von Office Communications Server und den zugehörigen Clients interagieren lassen möchten, müssen Sie Folgendes beachten:

  - Benutzer, die Lync Server 2013 verwenden, können keine Live Meeting-Konferenzen planen oder migrierte Besprechungen dieses Typs ändern.

  - Benutzer, die Lync Server 2013 verwenden und an Live Meeting-Konferenzen teilnehmen müssen, die auf Servern mit Office Communications Server 2007 R2 gehostet werden, müssen den Live Meeting-Client auf ihrem Computer installiert haben (zusäztlich zu Lync Server 2013), um an diesen Besprechungen teilnehmen zu können.

  - Beim Migrieren von Live Meeting-Konferenzen nach Lync Server 2013 werden die Besprechungsinhalte nicht migriert. Wenn diese Inhalte benötigt werden, müssen sie erneut hochgeladen werden.

