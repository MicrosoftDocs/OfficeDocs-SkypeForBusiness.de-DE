---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c9dadf9de1b1e15a789c84eaa76c59bee237f45
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154297"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Konfigurieren der Unterstützung für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Die Bereitstellung eines Edgeservers oder Edgepools ist der erste Schritt zur Unterstützung externer Benutzer. Ausführliche Informationen zum Bereitstellen von Edge-Servern finden Sie unter [Deploying External User Access in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation. Ein wichtiger Aspekt bei der Konfiguration von Richtlinien ist das Verständnis der Priorität von Richtlinien und der Anwendung der Richtlinien. Lync Server Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Lync Server Vorrang vor der Richtlinie: Benutzerrichtlinie (der meiste Einfluss) setzt eine Standortrichtlinie außer Kraft, und eine Standortrichtlinie setzt eine globale Richtlinie (am wenigsten Einfluss) außer Kraft. Dies bedeutet, dass je näher die Richtlinieneinstellung auf das Objekt zutrifft, das die Richtlinie betrifft, desto mehr Einfluss hat Sie auf das Objekt.

Nachdem Sie das Setup eines Edgeserver oder Edgepool abgeschlossen haben, müssen Sie die Typen des externen Benutzerzugriffs aktivieren, den Sie bereitstellen möchten, und die Einstellungen für den externen Zugriff konfigurieren. In lync Server 2013 aktivieren und konfigurieren Sie den Zugriff und die Richtlinien für externe Benutzer mithilfe der lync Server-Systemsteuerung, der lync Server-Verwaltungsshell oder beider basierend auf den Aufgabenanforderungen.

Um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie die folgenden Schritte ausführen:

  - **Aktivieren Sie Unterstützung für Ihre Organisation**   , um die Unterstützung für den externen Benutzer Zugriff in Ihrer Bereitstellung zu aktivieren, und aktivieren Sie jede Art von externem Zugriff, die Sie unterstützen möchten. Sie können die Unterstützung für den Zugriff durch externe Benutzer aktivieren und deaktivieren, indem Sie die globalen Einstellungen bearbeiten oder eine Standort-oder Benutzerrichtlinie auf der Seite **Richtlinie für externe Zugriffsrichtlinien** in der Gruppe **Verbund und externer Zugriff** des lync Server-Systemsteuerung oder mithilfe der lync Server-Verwaltungsshell und der zugeordneten Cmdlets erstellen und konfigurieren. Cmdlets zum Verwalten der **Richtlinie für den externen Zugriff** finden Sie im Thema [Verbund-und externer Zugriffs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Durch Aktivieren der Unterstützung für den externen Zugriff wird angegeben, dass Ihre Server, auf denen der lync Server läuft, die Kommunikation mit externen Benutzern und Servern Zugriffs-Edgedienst unterstützen. Interne und externe Benutzer können nicht kommunizieren, während der externe Benutzer Zugriff deaktiviert ist oder wenn Richtlinien noch nicht für die Unterstützung konfiguriert wurden.

  - **Konfigurieren und Zuweisen einer oder mehrerer Richtlinien**   zur Unterstützung des Zugriffs durch externe Benutzer konfigurieren Sie Richtlinien zur Behebung von Anforderungen, die Folgendes umfassen:
    
      - ****   Mit einem Standort-oder Benutzerbereich erstellte Richtlinien für den externen Zugriff (globale Richtlinie ist standardmäßig vorhanden und hat keine aktivierten Einstellungen). Sie erstellen und konfigurieren Richtlinien zum Steuern der Verwendung eines oder mehrerer Arten von externem Benutzer Zugriff, einschließlich des Zugriffs auf Verbundbenutzer (einschließlich, falls ausgewählt, Verbund-XMPP-Domänen) Remotebenutzer Benutzer Zugriff und unterstützte öffentliche Sofortnachrichten-Dienstanbieter. Sie konfigurieren externe Richtlinien in lync Server-Systemsteuerung mithilfe der globalen Richtlinie oder einer oder mehreren administrativ erstellten Standort-und Benutzerrichtlinien auf der Seite **externe Zugriffsrichtlinie** in der Gruppe **Verbund und externer Zugriff** . Die globale Richtlinie kann nicht gelöscht werden. Sie erstellen und konfigurieren alle Standort-und Benutzerrichtlinien, die Sie verwenden möchten, um den Zugriff durch externe Benutzer für bestimmte Websites oder Benutzer einzuschränken. Globale und Standortrichtlinien werden automatisch zugewiesen. Wenn Sie eine Benutzerrichtlinie erstellen und konfigurieren, müssen Sie diese den bestimmten Benutzern zuweisen, indem Sie die Seite Benutzerkonfiguration im lync Server-Systemsteuerung auf der Seite **Benutzer** verwenden. Suchen Sie nach den Benutzern, auf die diese Richtlinie angewendet werden soll, und weisen Sie die Richtlinie zu. an wen Sie es anwenden möchten. Informationen zum Zuweisen einer konfigurierten Benutzerrichtlinie zu einem Benutzer finden Sie unter [Zuweisen einer externen Benutzerzugriffs Richtlinie zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Jede Richtlinie für den externen Benutzer Zugriff kann eine oder mehrere der folgenden unterstützen: Remotebenutzerzugriff, SIP-Verbundbenutzer Zugriff, XMPP-Verbundbenutzer Zugriff und Verbindungen mit öffentlichen Instant Messaging-Diensten.
    
      - **Konferenzrichtlinien**   Sie erstellen und konfigurieren Richtlinien zur Steuerung von Konferenzen in Ihrer Organisation, einschließlich der Benutzer in Ihrer Organisation, die anonyme Benutzer zu Konferenzen einladen können, die Sie hosten. Auf der Seite "lync Server-Systemsteuerung **Konferenz** " befinden sich Richtlinieneinstellungen auf globaler, Standort-und Benutzerebene, mit denen Einstellungen für die tatsächlichen Konferenzen gesteuert werden. Ausführliche Informationen finden Sie unter [Managing Meetings and Konferenzen in lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Sie aktivieren anonyme Benutzer für Konferenzen, Remotebenutzer und Verbundbenutzer auf der Seite **Access Edge Configuration** . Die Richtlinie für die **Zugriffs-Edge-Konfiguration** ist global im Bereich. Es gibt keine Optionen zum Definieren einer Website-oder Benutzerrichtlinie. Der Bereich wird auf der Seite **Richtlinie für den externen Zugriff** durch die Verwendung von Einstellungen für globale, Standort-oder Benutzerrichtlinien gesteuert.
        
        Wenn Sie beispielsweise Benutzern das Erstellen, einladen und Verwalten von Konferenzen mit Remotebenutzern gestatten möchten, müssen Sie die **Option Kommunikation mit Remotebenutzern** auf der globalen **Richtlinie für den externen Zugriff** , Standort oder Benutzerrichtlinie aktivieren und die **Kommunikation mit Remotebenutzern** auf der Seite **Zugriffs-Edge-Konfiguration** aktivieren festlegen. Um Konferenzen mit anonymen Benutzern oder Verbundpartnern zuzulassen, mit denen Sie eine definierte Beziehung haben (beispielsweise konfigurierte Partner SIP-Domänen und-Anbieter – XMPP-Verbund unterstützt keine Konferenzen), legen Sie die **Option Kommunikation mit öffentlichen Benutzern aktivieren** und **Kommunikation mit Verbundbenutzern** in der globalen **Richtlinie für den externen Zugriff** , Standort oder Benutzerrichtlinie aktivieren fest. Anschließend wählen Sie ﻿kostenlose globale Richtlinieneinstellungen **Aktivieren des Zugriffs anonymer Benutzer auf Konferenzen** und **Aktivieren der Konnektivität von Verbund-und öffentlichen Chat** Diensten auf der Seite **Access Edge Configuration** .

Sie können auch dann Einstellungen für den Zugriff externer Benutzer konfigurieren, wenn Sie den externen Benutzerzugriff für Ihre Organisation nicht aktiviert haben. Hierzu gehören auch Richtlinien, die Sie zum Steuern des externen Benutzerzugriffs verwenden möchten. Die von Ihnen konfigurierten Richtlinien und anderen Einstellungen treten jedoch erst in Kraft, wenn der externe Benutzerzugriff für Ihre Organisation aktiviert wird. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der externe Benutzerzugriff deaktiviert ist oder wenn keine Richtlinien für den externen Benutzerzugriff konfiguriert wurden.

Ihre Edgebereitstellung authentifiziert die Typen externer Benutzer (außer Benutzer, die mit der Konferenz-ID und dem an den anonymen Teilnehmer übermittelten Hauptschlüssel identifiziert werden, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und steuert den Zugriff basierend auf der Konfiguration der Edgeunterstützung. Zum Steuern der Kommunikation können Sie eine oder mehrere Richtlinien sowie Einstellungen konfigurieren, durch die definiert wird, wie Benutzer innerhalb und außerhalb der Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die globale Standardrichtlinie für den externen Benutzerzugriff sowie Richtlinien auf Standort- und Benutzerebene, die Sie zum Aktivieren eines oder mehrerer Typen des externen Benutzerzugriffs für bestimmte Standorte oder Benutzer erstellen und konfigurieren können.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Richtlinien zur Steuerung des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Zugriffs anonymer Benutzer in lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

