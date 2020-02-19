---
title: Verhindern, dass neue Verbindungen für die Server Wartung lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06516c3d47a9ec5e491a5a16098dfae334ff4f4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a>Verhindern, dass neue Verbindungen für die Server Wartung lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Mit lync Server können Sie einen Server offline schalten (beispielsweise zum Anwenden von Software-oder Hardwareupgrades), ohne dass der Dienst für die Benutzer verloren geht.

Wenn Sie die Option zum Verhindern neuer Verbindungen oder Anrufe an einen Server innerhalb eines Pools angeben, werden keine neuen Verbindungen hergestellt oder Anrufe angenommen, sobald Sie diese Option aktivieren. Alle neuen Verbindungen und Anrufe werden an andere Server im Pool umgeleitet. Ein Server, der neue Verbindungen verhindert, ermöglicht die Fortsetzung von Sitzungen für bereits hergestellte Verbindungen, bis diese vom Benutzer beendet werden. Sobald alle vorhandenen Sitzungen beendet wurden, kann der Server offline geschaltet werden.

Wenn Sie neue Verbindungen mit einem Front-End-Server verhindern, beruhen einige lync Server-Features und-Dienste auf dem DNS-Lastenausgleich, um sicherzustellen, dass er ordnungsgemäß funktioniert. Wenn Sie keinen DNS-Lastenausgleich im Pool verwenden, werden Verbindungen über diese Dienste möglicherweise nicht an andere Server umgeleitet, während der Zeitraum, in dem der Server neue Verbindungen verhindert, und daher, wenn der Server offline geschaltet wird, einige Sitzungen und Anrufe möglicherweise unterbrochen. Die Funktionen, die DNS-Lastenausgleich verwenden, um sicherzustellen, dass diese Option ordnungsgemäß funktioniert, lauten wie folgt:

  - Telefonzentrale

  - Konferenzankündigungsanwendung

  - Reaktionsgruppenanwendung

  - Ankündigungsanwendung

  - Anwendung zum Parken von Anrufen

Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

Zusätzlich zur Verhinderung neuer Verbindungen für alle Dienste auf einem Server mit lync Server können Sie auch neue Verbindungen für einzelne lync Server Dienste verhindern. Diese Methode ist beispielsweise hilfreich in Situationen, in denen Sie ein lync Server-Update anwenden müssen, bei dem der gesamte Server nicht heruntergefahren werden muss. Hinweis: Wenn Sie Verbindungen für einen Dienst verhindern, müssen Sie den Dienst basierend auf der Gruppierung und Anzeige in der Windows-Liste von Diensten auswählen. Beispielsweise sind der lync Server-Front-End-Dienst und der Datenerfassungs-Agent für die Überwachung separate lync Server Dienste, in der Liste der Windows-Dienste werden Sie jedoch konsolidiert und als lync Server Front-End-Dienst angezeigt. Sie können neue Verbindungen für den lync Server-Front-End-Dienst verhindern, aber Sie können keine neuen Verbindungen für diese beiden einzelnen zugrunde liegenden lync Server Dienste separat verhindern.

<div>


> [!IMPORTANT]
> Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a>So verhindern Sie, dass neue Verbindungen lync Server:

1.  Melden Sie sich beim lokalen Computer als Mitglied der Gruppe Administratoren an.

2.  Öffnen Sie die Konsole Dienste-Snap-in: Klicken Sie auf **Start**, dann auf **Alle Programme**, dann auf **Verwaltung**, und klicken Sie dann auf **Dienste**.

3.  Doppelklicken Sie in der Liste auf den Lync Server-Windows-Dienst, für den Sie neue Verbindungen verhindern möchten.

4.  Klicken Sie im Eigenschaftendialogfeld unter **Dienststatus: Gestartet** auf **Anhalten**.

5.  Es empfiehlt sich, neben **Starttyp** auf **Manuell** zu klicken. Dies ist jedoch optional.
    
    <div>
    

    > [!IMPORTANT]
    > Wenn Sie einen Server so konfigurieren, dass neue Verbindungen verhindert werden, und diesen Server anschließend neu starten, lässt der Server standardmäßig sofort wieder neue Verbindungen zu. Um dies zu verhindern, konfigurieren Sie den Server vor dem Neustart so, dass der Dienst nur manuell angehalten und fortgesetzt wird.

    
    </div>

6.  Nachdem Sie die Eingabe beendet haben, klicken Sie auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

