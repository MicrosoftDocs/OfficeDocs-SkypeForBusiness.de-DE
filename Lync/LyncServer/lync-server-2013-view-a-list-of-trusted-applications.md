---
title: 'Lync Server 2013: Anzeigen einer Liste vertrauenswürdiger Anwendungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a>Anzeigen einer Liste vertrauenswürdiger Anwendungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Sie können die lync Server 2013-Systemsteuerung verwenden, um eine Liste der vertrauenswürdigen Anwendungen anzuzeigen, die Sie in ihrer lync Server 2013-Umgebung bereitgestellt haben. Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von lync Server 2013 als vertrauenswürdig eingestuft wird. Diese Vertrauensstellung wird in der folgenden Liste zusammengefasst:

  - Vertrauenswürdige Anwendungen werden für die Authentifizierung durch lync Server nicht in Frage gestellt.

  - Vertrauenswürdige Anwendungen werden nicht von lync Server für SIP-Transaktionen, Verbindungen oder ausgehende VoIP-Anrufe (Voice over Internet Protocol) gedrosselt.

  - Vertrauenswürdige Anwendungen können sich als alle Benutzer erweisen und können an Konferenzen teilnehmen, ohne dass Sie in Dienstplänen angezeigt werden.

  - Vertrauenswürdige Anwendungen sind hochgradig verfügbar und widerstandsfähig.

In der lync Server-Systemsteuerung können Sie den Namen der Anwendungen, den Pool, in dem Sie ausgeführt werden, und den von Ihnen verwendeten Port sehen.

<div>

## <a name="to-view-a-list-of-trusted-applications"></a>So zeigen Sie eine Liste vertrauenswürdiger Anwendungen an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle „CsServerAdministrator“, „CsAdministrator“, „CsHelpDesk“ oder „CsViewOnlyAdministrator“ zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an. Details zu den vordefinierten Administratorrollen, die in lync Server 2013 zur Verfügung stehen, finden Sie unter [Planen der rollenbasierten Zugriffssteuerung in lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Topologie** , und klicken Sie auf **vertrauenswürdige Anwendung**.

4.  Klicken Sie auf der Seite **vertrauenswürdige Anwendung** auf eine Spaltenüberschrift, um die Anwendungen bei Bedarf zu sortieren.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der Lync Server 2013-Topologie](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

