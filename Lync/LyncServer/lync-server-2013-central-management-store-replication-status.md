---
title: 'Lync Server 2013: Replikationsstatus des zentralen Verwaltungsspeichers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ce46b403e27d0a2b69f705b5bada026882eec7d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a>Replikationsstatus des zentralen Verwaltungsspeichers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-01-26_

Wenn ein Administrator eine Art Änderung an lync Server vornimmt (Wenn beispielsweise ein Administrator eine neue VoIP-Richtlinie erstellt oder die Konfigurationseinstellungen des Adressbuchservers ändert), wird diese Änderung im zentralen Verwaltungsspeicher aufgezeichnet. Die Änderung muss dann wiederum auf alle Computer repliziert werden, auf denen lync Server-Dienste oder Serverrollen ausgeführt werden.

Zum Replizieren der Daten erstellt der Master-Replikationsdienst (der auf dem zentralen Verwaltungsserver ausgeführt wird) eine Momentaufnahme der geänderten Konfigurationsdaten. Anschließend wird eine Kopie dieses Snapshots an jeden Computer gesendet, auf dem lync Server-Dienste oder Serverrollen ausgeführt werden. Auf diesen Computern erhält ein lokaler Replikations-Agent die Momentaufnahme und lädt die geänderten Daten hoch. Der Agent sendet dann dem Master-Replikationsdienst eine Nachricht mit dem aktuellen Replikationsstatus.

Mit dem Cmdlet Get-CsManagementStoreReplicationStatus können Sie den Replikationsstatus für alle (oder alle) lync Server-Computer in Ihrer Organisation überprüfen.

Wer kann dieses Cmdlet ausführen? Standardmäßig sind Mitglieder der folgenden Gruppen autorisiert, das Cmdlet "Get-CsManagementStoreReplicationStatus" lokal auszuführen: RTCUniversalUserAdmins, RTCUniversalServerAdmins.

Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen zurückzugeben, denen dieses Cmdlet zugewiesen wurde (einschließlich aller benutzerdefinierten RBAC-Rollen, die Sie selbst erstellt haben):

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

