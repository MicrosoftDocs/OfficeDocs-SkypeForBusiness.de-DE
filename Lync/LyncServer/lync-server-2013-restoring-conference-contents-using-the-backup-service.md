---
title: 'Lync Server 2013: Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Wiederherstellen von Konferenzinhalten mithilfe des Sicherungsdiensts in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Wenn die Konferenz Informationen, die im Dateispeicher eines Front-End-Pools gespeichert sind, nicht mehr zur Verfügung stehen. Sie müssen diese Informationen so wiederherstellen, dass Benutzer, die im Pool verwaltet werden, ihre Konferenzdaten beibehalten. Wenn der Front-End-Pool, in dem Konferenzdaten verloren gegangen sind, mit einem anderen Front-End-Pool gekoppelt ist, können Sie die Daten mithilfe des Sicherungsdiensts wiederherstellen.

Sie müssen diese Aufgabe auch ausführen, wenn ein gesamter Pool fehlgeschlagen ist und Sie die Benutzer nicht mit einem Sicherungspool durchführen müssen. Wenn diese Benutzer wieder in ihren ursprünglichen Pool zurückgekehrt sind, müssen Sie diese Vorgehensweise verwenden, um Ihre Konferenzinhalte wieder in ihren ursprünglichen Pool zu kopieren.

Gehen Sie davon aus, dass pool1 mit Pool2 gekoppelt ist und die Konferenzdaten in pool1 verloren gehen. Sie können das folgende Cmdlet verwenden, um den Sicherungsdienst aufzurufen, um den Inhalt wiederherzustellen:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Das Wiederherstellen der Konferenzinhalte kann je nach Größe einige Zeit in Anspruch nehmen. Sie können das folgende Cmdlet verwenden, um den Prozessstatus zu überprüfen:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Der Vorgang erfolgt, wenn dieses Cmdlet den Wert des Steady-State-Werts für das Datenkonferenz Modul zurückgibt.

</div>

<span> </span>

</div>

</div>

</div>

