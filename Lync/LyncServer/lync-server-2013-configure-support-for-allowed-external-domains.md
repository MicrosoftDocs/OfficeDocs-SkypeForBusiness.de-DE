---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für zugelassene externe Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51190fd787fde408913b71d4a5ce6f1d002a6d28
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Konfigurieren der Unterstützung für zugelassene externe Domänen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-19_

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche spezifischen Domänen einen Partnerverbund mit Ihrer Organisation eingehen können. Konfigurieren Sie eine oder mehrere spezifische externe Domänen als zulässige Partnerdomänen. Fügen Sie hierzu jede Domäne der Liste zulässiger Domänen hinzu. Selbst wenn die Suche von Verbundpartnern für Ihre Organisation aktiviert ist, führen Sie diesen Schritt aus, wenn es sich bei der Domäne um einen Verbundpartner handelt, der mit mehr als 1.000 Ihrer Benutzer kommunizieren oder mehr als 20 Nachrichten pro Sekunde senden muss. Ist die Suche von Verbundpartnern für Ihre Organisation nicht aktiviert, können nur Benutzer aus externen Domänen am Instant Messaging und an Konferenzen mit Benutzern Ihrer Organisation teilnehmen, die Sie der Liste zulässiger Domänen hinzugefügt haben. Wenn Sie den Zugriff einer Partnerdomäne auf einen bestimmten Server beschränken möchten, auf dem der Zugriffs-Edgedienst des Verbundpartners ausgeführt wird, können Sie für jede Domäne in der Liste zulässiger Domänen den Domänennamen des Servers angeben, auf dem der Zugriffs-Edgedienst ausgeführt wird.

<div>


> [!NOTE]  
> In diesem Verfahren wird beschrieben, wie Sie die Unterstützung für bestimmte Domänen konfigurieren, aber die Implementierung der Unterstützung für Partnerverbund Benutzer erfordert auch, dass Sie die Unterstützung für Partnerverbund Benutzer für Ihre Organisation aktivieren und Richtlinien konfigurieren und anwenden, um zu steuern, welche Benutzer Zusammenarbeit mit Partnerverbund Benutzern. Ausführliche Informationen zum Aktivieren der Unterstützung für Partnerverbund Benutzer finden Sie unter <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013</A>. Ausführliche Informationen zum Konfigurieren von Richtlinien zur Steuerung des Verbunds finden Sie unter <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">configure Policies to Control Federated User Access in lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>So fügen Sie eine externe Domäne der Liste zulässiger Domänen hinzu

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer** und dann auf **Partnerdomänen**.

4.  Klicken Sie auf der Seite **Partnerdomänen** auf **Neu** und anschließend auf **Zulässige Domäne**.

5.  Führen Sie unter **Neue Partnerdomänen** die folgenden Aktionen aus:
    
      - Geben Sie unter **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein.
        
        <div>
        

        > [!NOTE]  
        > Dieser Name muss eindeutig sein und darf noch nicht als zulässige Domäne für diesen Server vorliegen, auf dem der Zugriffs-Edgedienst ausgeführt wird. Der Name darf höchstens 256 Zeichen lang sein.<BR>Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG> eingeben, wird als Suchergebnis auch die Domäne <STRONG>it.contoso.com</STRONG> zurückgegeben.<BR>Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden. Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.

        
        </div>
    
      - Wenn Sie den Zugriff für diese Partnerdomäne auf Benutzer eines bestimmten Servers beschränken möchten, auf dem der Zugriffs-Edgedienst ausgeführt wird, geben Sie unter **Zugriffs-Edgedienst (FQDN)** den FQDN des Servers der Partnerdomäne ein, auf dem der Zugriffs-Edgedienst ausgeführt wird.
    
      - Wenn Sie zusätzliche Informationen bereitstellen möchten, geben Sie unter **Kommentar** Informationen ein, die Sie anderen Systemadministratoren über diese Konfiguration mitteilen möchten.

6.  Klicken Sie auf **Commit**.

7.  Wiederholen Sie die Schritte 4 bis 6 für jede Verbundpartnerdomäne, die Sie zulassen möchten.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

