---
title: Verhindern neuer Verbindungen mit lync Server für die Serverwartung
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db3838af59a6a91699fa6d38b8aa2912e2b30012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Verhindern neuer Verbindungen mit lync Server 2013 für die Server Wartung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Mit lync Server können Sie einen Server offline schalten (beispielsweise um Software-oder Hardwareupgrades anzuwenden), ohne dass der Dienst für die Benutzer verloren geht.

Wenn Sie die Option zum verhindern neuer Verbindungen oder Aufrufe an einen Server in einem Pool angeben, werden alle neuen Verbindungen und Anrufe nicht mehr Unternehmen, sobald Sie diese Option implementieren. Diese neuen Verbindungen und Anrufe werden über andere Server im Pool weitergeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht, dass seine Sitzungen an vorhandenen Verbindungen fortgesetzt werden, bis Sie natürlich enden. Wenn alle vorhandenen Sitzungen beendet sind, kann der Server offline geschaltet werden.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, Vertrauen einige lync Server-Features und-Dienste auf den DNS-Lastenausgleich, um sicherzustellen, dass Sie ordnungsgemäß funktioniert. Wenn Sie keinen DNS-Lastenausgleich für den Pool verwenden, werden Verbindungen über diese Dienste möglicherweise während des Zeitraums, in dem der Server neue Verbindungen verhindert, nicht an andere Server umgeleitet, und wenn der Server offline geschaltet wird, werden einige Sitzungen und Anrufe möglicherweise unterbrochen. Die Features, die vom DNS-Lastenausgleich abhängig sind, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, sind wie folgt:

  - Vermittlung

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ansageanwendung

  - Anwendung zum Parken von Anrufen

Details zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

Zusätzlich zum verhindern neuer Verbindungen für alle Dienste auf einem Server, auf dem lync Server ausgeführt wird, können Sie auch neue Verbindungen für einzelne lync Server-Dienste verhindern. Diese Methode ist beispielsweise hilfreich in einer Situation, in der Sie ein lync Server-Update anwenden müssen, das nicht erfordert, dass der gesamte Server beendet wird. Beachten Sie, dass Sie einen Dienst auswählen müssen, wenn Sie Verbindungen für einen Dienst verhindern, indem Sie ihn gruppieren und in der Windows-Liste der Dienste angezeigt werden. Beispielsweise sind der lync Server-Front-End-Dienst und der Daten Sammlungs-Agent für die Überwachung separate lync Server-Dienste, in der Liste der Windows-Dienste werden Sie jedoch konsolidiert und als der lync Server-Front-End-Dienst angezeigt. Sie können neue Verbindungen für den lync Server-Front-End-Dienst verhindern, jedoch können Sie keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden lync Server-Dienste separat verhindern.

<div>


> [!IMPORTANT]
> Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren. Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>So verhindern Sie neue Verbindungen mit lync Server:

1.  Melden Sie sich auf dem lokalen Computer als Mitglied der Gruppe "Administratoren" an.

2.  Öffnen Sie die Snap-In-Konsole Dienste: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme**, zeigen Sie auf **Verwaltung**, und klicken Sie dann auf **Dienste**.

3.  Doppelklicken Sie in der Liste auf den lync Server-Windows-Dienst, auf den Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im DialogfeldEigenschaften unter **Dienststatus: gestartet**auf **Anhalten**.

5.  Optional, aber empfohlen, klicken Sie **** neben Starttyp auf **manuell**.
    
    <div>
    

    > [!IMPORTANT]
    > Wenn Sie einen Server so einrichten, dass neue Verbindungen verhindert werden, und den Server dann neu starten, wird der Server standardmäßig unmittelbar nach dem Start neue Verbindungen akzeptieren. Um dies zu verhindern, müssen Sie den Server so einrichten, dass er vor dem Neustart des Servers nur manuell angehalten und fortgesetzt wird.

    
    </div>

6.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

