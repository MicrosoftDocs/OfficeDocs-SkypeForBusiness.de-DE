---
title: 'Lync Server 2013: Veröffentlichen der aktualisierten Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747065"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Veröffentlichen der aktualisierten Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Nachdem Sie Ihre Topologie im Topologie-Generator aktualisiert haben, müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie den Server für beständigen Chat Konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.

<div>

## <a name="to-publish-an-updated-topology"></a>So veröffentlichen Sie eine aktualisierte Topologie

Bevor Sie Ihre Topologie veröffentlichen, installieren Sie die Datenbanken für beständigen Chat Server. Mithilfe des Topologie-Generators können Sie Datenbanken installieren, indem Sie **Aktion** und **Datenbank installieren**auswählen.

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 ausgeführt wird oder auf dem die lync Server-Verwaltungstools installiert sind, mit einem Konto an, das Mitglied sowohl der Gruppe der **Domänenadministratoren** als auch der **RTCUniversalServerAdmins** -Gruppe ist. und die über die Berechtigung "Vollzugriff" (also lesen, schreiben und ändern) im Dateispeicher für den Dateispeicher für beständigen Chat Server verfügt (damit der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) oder ein Konto mit entsprechenden Benutzerrechten konfigurieren kann.

2.  Starten Sie den Topologie-Generator. Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen**aus, oder **Öffnen Sie die Topologie aus einer lokalen Datei** , wenn Sie Sie lokal gespeichert haben.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Nachdem Sie die Topologie veröffentlicht haben, müssen Sie die Unterstützung für beständigen Chat Server konfigurieren, bevor Inhalte archiviert werden können.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

