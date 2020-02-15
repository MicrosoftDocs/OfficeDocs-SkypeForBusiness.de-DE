---
title: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d411733712cf274760a45cd4e315b4f02a66e0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Replikationsstatus des zentralen Verwaltungsspeichers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-01-26_

Wenn ein Administrator eine Art Änderung an lync Server vornimmt (beispielsweise wenn ein Administrator eine neue VoIP-Richtlinie erstellt oder die Konfigurationseinstellungen für den Adressbuch Server ändert), wird diese Änderung im zentralen Verwaltungsspeicher aufgezeichnet. Die Änderung muss wiederum auf alle Computer repliziert werden, auf denen lync Server Dienste oder Server Rollen ausführt.

Zum Replizieren von Daten erstellt der Haupt Replikationsdienst (auf dem zentralen Verwaltungs Server ausgeführt) eine Momentaufnahme der geänderten Konfigurationsdaten. Eine Kopie dieses Snapshots wird dann an jeden Computer gesendet, auf dem lync Server Dienste oder Server Rollen ausgeführt wird. Auf diesen Computern empfängt ein Replikations-Agent den Snapshot und lädt die geänderten Daten hoch. Der Agent sendet dann dem Haupt Replikationsdienst eine Nachricht, die den neuesten Replikationsstatus meldet.

Mit dem Cmdlet Get-CsManagementStoreReplicationStatus können Sie den Replikationsstatus für alle (oder alle) lync Server Computer in Ihrer Organisation überprüfen.

Wer kann dieses Cmdlet ausführen? Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Get-CsManagementStoreReplicationStatus-Cmdlet lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben), führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a>Siehe auch


[Get-CsManagementStoreReplicationStatus](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

