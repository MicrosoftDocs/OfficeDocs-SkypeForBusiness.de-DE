---
title: 'Lync Server 2013: Aktivieren der Richtlinie für den Server für beständigen Chat'
TOCTitle: Aktivieren der Richtlinie für den Server für beständigen Chat
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205056(v=OCS.15)
ms:contentKeyID: 49294645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Aktivieren der Richtlinie für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-06_

In Systemsteuerung für Lync Server 2013 können Sie die Seite **Beständiger Chat Richtlinie** der **Beständiger Chat**-Gruppe verwenden, um Richtlinien auf globaler, Pool-, Standort- oder Benutzerebene zu verwalten. Hierzu gehört auch die Konfiguration der globalen Standardrichtlinie sowie die Erstellung einer oder mehrerer zusätzlicher Benutzer- und Standortrichtlinien für Ihre Bereitstellung. Wenn ein Benutzer durch Richtlinien für Server für beständigen Chat aktiviert wurde, wird die Server für beständigen Chat-Umgebung in deren Lync 2013-Client angezeigt.


> [!NOTE]
> In der Topologie werden die Standortrichtlinien für Server für beständigen Chat entweder pro Pool des Benutzers oder pro Standort des Benutzers oder pro Benutzer global angewendet.



Die globale Richtlinie wird automatisch bei der Bereitstellung von Server für beständigen Chat erstellt und kann konfiguriert, jedoch nicht gelöscht. Da die globale Richtlinie bei allen Benutzern angewendet wird, muss sie nicht für jeden Benutzer einzeln festgelegt werden.

Sie können mehrere Standort- und Benutzerrichtlinien erstellen und konfigurieren, die, zusammen mit der globalen Richtlinie, Benutzer für Server für beständigen Chat aktiviert. Pool- und Standortrichtlinien von Server für beständigen Chat setzen die globale Server für beständigen Chat-Richtlinie außer Kraft, wenn auch nur für Benutzer an diesem Standort. Benutzerrichtlinien setzen sowohl die globale als auch die Pool- und Standortrichtlinien für diejenigen Benutzer außer Kraft, denen die Benutzerrichtlinie zugewiesen wird.


> [!NOTE]
> Wenn Sie den Server für beständigen Chat konfigurieren und verwenden möchten, müssen Sie zunächst mit dem Topologie-Generator die Server für beständigen Chat-Unterstützung der Topologie hinzufügen und die Topologie anschließend veröffentlichen. Einzelheiten dazu finden Sie unter <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Hinzufügen eines Servers für beständigen Chat zu einer Bereitstellung in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## In diesem Abschnitt

  - [Konfigurieren der globalen Richtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Erstellen einer Standortrichtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Erstellen einer Benutzerrichtlinie für beständigen Chat in Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Anwenden einer Richtlinie für beständigen Chat auf einen Benutzer oder eine Benutzergruppe in Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

