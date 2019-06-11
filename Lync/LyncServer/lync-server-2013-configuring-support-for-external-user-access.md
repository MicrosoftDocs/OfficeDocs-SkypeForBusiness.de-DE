---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für den externen Benutzerzugriff'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring support for external user access
ms:assetid: f8424f8c-f965-4414-8485-30f07e10214a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413051(v=OCS.15)
ms:contentKeyID: 48185874
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f10e266674d102b25753aeb58c89a365e7bb8e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-external-user-access-in-lync-server-2013"></a>Konfigurieren der Unterstützung für den externen Benutzerzugriff in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Die Bereitstellungeines Edgeserver oder eines Edge-Pools ist der erste Schritt zur Unterstützung externer Benutzer. Details zum Bereitstellen von Edge-Servern finden Sie unter [Bereitstellen des Zugriffs auf externe Benutzer in lync Server 2013](lync-server-2013-deploying-external-user-access.md) in der Bereitstellungsdokumentation. Eine wichtige Überlegung bei der Konfiguration von Richtlinien besteht darin, den Vorrang von Richtlinien und die Anwendung der Richtlinien zu verstehen. Lync Server-Richtlinieneinstellungen, die auf einer Richtlinienebene angewendet werden, können Einstellungen außer Kraft setzen, die auf einer anderen Richtlinienebene angewendet werden. Die Priorität der lync Server-Richtlinie lautet: Benutzerrichtlinien (der meiste Einfluss) überschreibt eine Website Richtlinie, und eine Website Richtlinie überschreibt eine globale Richtlinie (geringster Einfluss). Mit anderen Worten: Je geringer der Abstand zwischen Richtlinieneinstellung und betroffenem Objekt, desto stärker der Einfluss auf das Objekt.

Nachdem Sie die Einrichtung eines Edge-Servers oder Edge-Pools abgeschlossen haben, müssen Sie die Typen des externen Benutzerzugriffs aktivieren, die Sie bereitstellen möchten, und die Einstellungen für den externen Zugriff konfigurieren. In lync Server 2013 aktivieren und konfigurieren Sie den Zugriff auf externe Benutzer und Richtlinien mithilfe der lync Server-Systemsteuerung, der lync Server-Verwaltungsshell oder beides, basierend auf den Aufgabenanforderungen.

Zur Unterstützung des Zugriffs externer Benutzer müssen Sie die beiden folgenden Schritte ausführen:

  - **Aktivieren Sie die Unterstützung für Ihre Organisation**   , um die Unterstützung für den Zugriff durch externe Benutzer in Ihrer Bereitstellung zu aktivieren, und aktivieren Sie die einzelnen externen Zugriffstypen, die Sie unterstützen möchten. Sie können die Unterstützung für den Zugriff durch externe Benutzer aktivieren und deaktivieren, indem Sie die globalen Einstellungen bearbeiten oder eine Website-oder Benutzerrichtlinie auf der Seite " **Richtlinien für den externen Zugriff** " in der Gruppe " **Föderation und externer Zugriff** " der lync Server-Systemsteuerung erstellen und konfigurieren. oder mithilfe der lync Server-Verwaltungsshell und zugehörigen Cmdlets. Cmdlets für die Verwaltung der **Richtlinie für den externen Zugriff** finden Sie im Thema [Föderation und externe Zugriffs-Cmdlets in lync Server 2013](https://docs.microsoft.com/powershell/module/skype/). Durch Aktivieren der Unterstützung für externen Zugriff wird angegeben, dass Ihre Server, auf denen der lync Server Access Edge-Dienst ausgeführt wird, die Kommunikation mit externen Benutzern und Servern unterstützen. Interne und externe Benutzer können nicht kommunizieren, während der Zugriff auf externe Benutzer deaktiviert ist oder wenn Richtlinien noch nicht für die Unterstützung konfiguriert wurden.

  - **Konfigurieren und Zuweisen einer oder mehrerer Richtlinien**   zur Unterstützung des Zugriffs durch externe Benutzer konfigurieren Sie Richtlinien für die Behebung von Anforderungen, die Folgendes umfassen:
    
      - ****   Mit einem Website-oder Benutzerbereich erstellte Richtlinien für den externen Zugriff (eine globale Richtlinie ist standardmäßig vorhanden und hat keine aktivierten Einstellungen). Sie erstellen und konfigurieren Richtlinien, um die Verwendung von einem oder mehreren Typen des Zugriffs auf externe Benutzer zu steuern, einschließlich des Zugriffs auf den Verbundbenutzer (einschließlich, wenn ausgewählt, Federated-XMPP-Domänen), Benutzer Zugriff für Remotebenutzer und unterstützte öffentliche Chatdienst Anbieter. Sie konfigurieren externe Richtlinien in der lync Server-Systemsteuerung unter Verwendung der globalen Richtlinie oder einer oder mehrerer administrativ erstellter Website-und Benutzerrichtlinien auf der Seite " **externe Zugriffsrichtlinie** " in der Gruppe " **Föderation und externer Zugriff** ". Die globale Richtlinie kann nicht gelöscht werden. Sie erstellen und konfigurieren alle Website-und Benutzerrichtlinien, die Sie verwenden möchten, um den Zugriff externer Benutzer auf bestimmte Websites oder Benutzer zu begrenzen. Globale und Website Richtlinien werden automatisch zugewiesen. Wenn Sie eine Benutzerrichtlinie erstellen und konfigurieren, müssen Sie diese den jeweiligen Benutzern über die Seite Benutzerkonfiguration in der lync Server-Systemsteuerung auf der Seite **Benutzer** zuweisen. Suchen Sie den Benutzer, für den diese Richtlinie gelten soll, und weisen Sie die Richtlinie zu. an wen Sie Sie anwenden möchten. Informationen zum Zuweisen einer konfigurierten Benutzerrichtlinie zu einem Benutzer finden Sie unter [Zuweisen einer Zugriffsrichtlinie für einen externen Benutzer zu einem lync-aktivierten Benutzer in lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md). Jede Richtlinie für den externen Benutzer Zugriff kann eine oder mehrere der folgenden Aktionen unterstützen: Remotebenutzerzugriff, SIP-Verbundbenutzer Zugriff, XMPP-Verbundbenutzer Zugriff und öffentliche Chat Verbindungen.
    
      - **Konferenzrichtlinien**   Sie erstellen und konfigurieren Richtlinien zum Steuern von Konferenzen in Ihrer Organisation, einschließlich der Benutzer in Ihrer Organisation, die anonyme Benutzer zu Konferenzen einladen können, die Sie hosten. Auf der lync Server Control Panel- **Konferenz** Seite sind Richtlinieneinstellungen auf globaler, Website-und Benutzerebene, mit denen die Einstellungen für die eigentlichen Konferenzen gesteuert werden. Ausführliche Informationen finden Sie unter [Verwalten von Besprechungen und Konferenzen in lync Server 2013](lync-server-2013-managing-meetings-and-conferences.md). Sie aktivieren anonyme Benutzer für Konferenzen, Remotebenutzer und Verbundbenutzer auf der Seite **Access Edge-Konfiguration** . Die Richtlinie für die **Access-Edge-Konfiguration** ist im Bereich Global. Es gibt keine Optionen zum Definieren einer Website-oder Benutzerrichtlinie. Der Bereich wird auf der Seite mit den **Richtlinien für den externen Zugriff** durch die Verwendung globaler, Website-oder Benutzerrichtlinieneinstellungen gesteuert.
        
        Wenn Sie beispielsweise Benutzern das Erstellen, einladen und Verwalten von Konferenzen mit Remotebenutzern gestatten möchten, müssen Sie in der globalen, Website-oder Benutzerrichtlinie für **externe Zugriffsrichtlinien** die **Option Kommunikation mit Remotebenutzern aktivieren** festlegen und die **Kommunikation aktivieren. mit Remotebenutzern** auf der Seite " **Zugriffs-Edge-Konfiguration** ". Um Konferenzen mit anonymen Benutzern oder Verbundpartnern zu ermöglichen, mit denen Sie eine definierte Beziehung haben (wie etwa konfigurierte Federated-SIP-Domänen und-Anbieter – die XMPP-Föderation unterstützt keine Konferenzen), wird die **Option "Kommunikation aktivieren" festgelegt. mit öffentlichen Benutzern** und **ermöglichen Sie die Kommunikation mit Verbundbenutzern** in der globalen Richt **Linie für externe Zugriffsrichtlinien** , Website-oder Benutzerrichtlinien. Wählen Sie dann ﻿kostenlose globale Richtlinieneinstellungen aktivieren Sie den **anonymen Benutzer Zugriff auf Konferenzen,** und aktivieren Sie die **Konnektivität für Verbund-und öffentliche Chats** auf der Seite **Access-Edge-Konfiguration** .

Sie können Einstellungen für den externen Benutzer Zugriff konfigurieren, einschließlich aller Richtlinien, die Sie zum Steuern des Zugriffs auf externe Benutzer verwenden möchten, auch wenn Sie den Zugriff auf externe Benutzer für Ihre Organisation nicht aktiviert haben. Die Richtlinien und anderen Einstellungen, die Sie konfigurieren, sind jedoch nur wirksam, wenn der Zugriff auf externe Benutzer für Ihre Organisation aktiviert ist. Externe Benutzer können nicht mit Benutzern Ihrer Organisation kommunizieren, wenn der Zugriff auf externe Benutzer deaktiviert ist oder wenn keine Richtlinien für den externen Benutzer Zugriff für die Unterstützung konfiguriert sind.

Ihre Edge-Bereitstellung authentifiziert die Typen externer Benutzer (mit Ausnahme von anonymen Benutzern, die von der Konferenz-ID authentifiziert werden, und einem Kennwort, das an den anonymen Teilnehmer gesendet wird, wenn Sie die Konferenz erstellen und Teilnehmer einladen) und Steuerelemente Access basiert auf der Konfiguration Ihrer Edge-Unterstützung. Um die Kommunikation zu steuern, können Sie eine oder mehrere Richtlinien konfigurieren und Einstellungen konfigurieren, die definieren, wie Benutzer innerhalb und außerhalb Ihrer Bereitstellung miteinander kommunizieren. Zu den Richtlinien und Einstellungen gehören die standardmäßige globale Richtlinie für den Zugriff durch externe Benutzer sowie Website-und Benutzerrichtlinien, die Sie erstellen und konfigurieren können, um einen oder mehrere Typen von externen Benutzer Zugriff für bestimmte Websites oder Benutzer zu ermöglichen.

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Richtlinien zur Steuerung des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Zugriffs durch Remotebenutzer in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [Aktivieren oder Deaktivieren des Zugriffs durch anonyme Benutzer in Lync Server 2013](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [Zuweisen von Konferenzrichtlinien zur Unterstützung anonymer Benutzer in Lync Server 2013](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

