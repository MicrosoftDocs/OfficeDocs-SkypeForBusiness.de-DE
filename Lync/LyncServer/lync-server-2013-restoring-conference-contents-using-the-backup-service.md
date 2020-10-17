---
title: 'Lync Server 2013: Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 252cdf6713db7fcb3c4658cc4adb0eb51905c1ff
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511448"
---
# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Wiederherstellen von Konferenz Inhalten mithilfe des Sicherungsdiensts in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Wenn die im Dateispeicher eines Front-End-Pools gespeicherten Informationen zu Konferenzen nicht mehr verfügbar sind, müssen Sie diese Informationen wiederherstellen, sodass die Konferenzdaten von Benutzern, die in diesem Pool verwaltet werden, erhalten bleiben. Wenn der Front-End-Pool, der Konferenzdaten verloren hat, mit einem anderen Front-End-Pool kombiniert wird, können Sie den Sicherungsdienst zur Wiederherstellung der Daten nutzen.

Sie müssen diese Aufgabe auch ausführen, wenn ein ganzer Pool ausfällt und Sie einen Failover seiner Benutzer in einen Sicherungspool durchführen müssen. Wenn für diese Benutzer ein Failover zurück in den ursprünglichen Pool durchgeführt wird, müssen Sie dieses Verfahren nutzen, um ihre Konferenzinhalte ebenfalls zurück in ihren ursprünglichen Pool zu kopieren.

Es wird davon ausgegangen, dass Pool1 mit Pool2 kombiniert wird und die Konferenzdaten in Pool1 verlorengehen. Sie können das folgende Cmdlet verwenden, um den Sicherungsdienst aufzurufen, um den Inhalt wiederherzustellen:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Die Wiederherstellung der Konferenzinhalte kann je nach ihrer Größe einige Zeit dauern. Sie können den Status des Vorgangs mithilfe des folgenden Cmdlets prüfen:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang ist abgeschlossen, wenn das Cmdlet für das Datenkonferenzmodul einen Wert für ein stabiles System anzeigt.

</div>

<span> </span>

</div>

</div>

</div>

