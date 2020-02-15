---
title: 'Lync Server 2013: Konfigurieren der Unterstützung für blockierte externe Domänen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f34f620fe6f98053e40c5999bcde29d88b6371a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Konfigurieren der Unterstützung für blockierte externe Domänen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-08_

Wenn Sie die Unterstützung für Verbundpartner konfiguriert haben, können Sie verwalten, welche Domänen für die Zusammenführung mit Ihrer Organisation blockiert werden. Die Liste der blockierten Domänen fungiert als Sperrliste (Auflistung expliziter Einträge, die nicht zulässig sind) und wird bei der Ermittlung der Verbunddomäne angewendet, wenn diese Option aktiviert ist. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Blockieren Sie eine oder mehrere externe Domänen vom Herstellen einer Verbindung mit Ihrer Organisation. Fügen Sie hierzu die Domäne der Liste blockierter Domänen hinzu.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>So fügen Sie der Liste blockierter Domänen eine externe Domäne hinzu

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Zugriff durch externe Benutzer**.

4.  Klicken Sie auf **Partnerdomänen**, auf **Neu** und dann auf **Blockierte Domäne**.

5.  Führen Sie unter **Neue Partnerdomänen** die folgende Aktion aus:
    
      - Geben Sie im Feld **Domänenname (oder FQDN)** den Namen der Verbundpartnerdomäne ein, die blockiert werden soll.
        
        <div>
        

        > [!NOTE]  
        > Der Name darf maximal 256 Zeichen umfassen.<BR>Bei der Suche nach dem Namen der Verbundpartnerdomäne wird ein Suffixabgleich durchgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG> eingeben, wird als Suchergebnis auch die Domäne <STRONG>it.contoso.com</STRONG> zurückgegeben.<BR>Eine Verbundpartnerdomäne kann nicht gleichzeitig blockiert und zugelassen werden. Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.

        
        </div>
    
      - Im Feld **Kommentar** können Sie Informationen zur Konfiguration eingeben, die Sie mit anderen Systemadministratoren teilen möchten. Dieses Feld ist optional.

6.  Klicken Sie auf **Commit**.

7.  Wiederholen Sie die Schritte 4 bis 6 für jeden Verbundpartner, den Sie blockieren möchten.

Um den Zugriff durch Partnerbenutzer zu ermöglichen, müssen Sie auch die Unterstützung für den Partnerbenutzerzugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Zusätzlich müssen Sie die Richtlinie konfigurieren und auf Benutzer anwenden, die mit Partnerbenutzern zusammenarbeiten sollen. Ausführliche Informationen finden Sie unter [configure Policies to Control Federated User Access in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

