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
ms.openlocfilehash: 3fe73985687e7a1d6fcd2bbf615127c0757a5307
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Konfigurieren der Unterstützung für blockierte externe Domänen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Wenn Sie die Unterstützung für Federated-Partner konfiguriert haben, können Sie verwalten, welche Domänen von der Föderation mit Ihrer Organisation blockiert werden. Die Liste der blockierten Domänen fungiert als Sperrliste (Auflistung expliziter Einträge, die nicht zulässig sind) und wird in der Föderationsdomänen Erkennung angewendet, wenn diese Option aktiviert ist. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren der Ermittlung von Verbundpartnern in lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Blockieren Sie eine oder mehrere externe Domänen, um eine Verbindung mit Ihrer Organisation herzustellen. Fügen Sie dazu die Domäne zur Liste der blockierten Domänen hinzu.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>So fügen Sie eine externe Domäne zur Liste der blockierten Domänen hinzu

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**.

4.  Klicken Sie auf **Verbunddomänen**, dann auf **neu**und dann auf **Blockierte Domäne**.

5.  Führen Sie in **neuen Föderationsdomänen**die folgenden Aktionen aus:
    
      - Geben Sie in **Domänenname (oder FQDN)** den Namen der Partnerdomäne ein, die Sie blockieren möchten.
        
        <div>
        

        > [!NOTE]  
        > Der Name darf nicht mehr als 256 Zeichen lang sein.<BR>Bei der Suche nach dem Domänennamen des Partner Partners wird eine Übereinstimmung mit dem Suffix ausgeführt. Wenn Sie beispielsweise <STRONG>contoso.com</STRONG>eingeben, gibt die Suche auch die Domäne <STRONG>IT.contoso.com</STRONG>zurück.<BR>Eine Föderationspartner-Domäne kann nicht gleichzeitig blockiert und zugelassen werden. Lync Server 2013 verhindert, dass dies geschieht, damit Sie Ihre Listen nicht synchronisieren müssen.

        
        </div>
    
      - Optional Geben Sie in **Kommentar**Informationen ein, die Sie für andere Systemadministratoren über diese Konfiguration freigeben möchten.

6.  Klicken Sie auf **Commit ausführen**.

7.  Wiederholen Sie die Schritte 4 bis 6 für jeden Föderationspartner, den Sie blockieren möchten.

Zum Aktivieren des Zugriffs auf den Verbundbenutzer müssen Sie auch die Unterstützung für den Verbundbenutzer Zugriff in Ihrer Organisation aktivieren. Ausführliche Informationen finden Sie unter [Aktivieren oder Deaktivieren des Remotebenutzerzugriffs in lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Darüber hinaus müssen Sie die Richtlinie für Benutzer konfigurieren und anwenden, die in der Lage sein sollen, mit Verbundbenutzern zusammenzuarbeiten. Ausführliche Informationen finden Sie unter [Konfigurieren von Richtlinien zum Steuern des Zugriffs von Verbundbenutzern in lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

