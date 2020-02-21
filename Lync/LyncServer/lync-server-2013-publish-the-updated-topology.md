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
ms.openlocfilehash: 7b978d7a8d2cf05d4e9fa1b0a224bbef50e3fd7e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201685"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>Veröffentlichen der aktualisierten Topologie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Nach dem Aktualisieren der Topologie im Topologie-Generator müssen Sie die Topologie im zentralen Verwaltungsspeicher veröffentlichen, bevor Sie den Server für beständigen Chat Konfigurieren und verwenden können. Schreibgeschützte Kopien der Daten werden auf alle Server in der Topologie repliziert, sodass diese Server mit der Topologie und anderen Konfigurationsänderungen synchronisiert sind.

<div>

## <a name="to-publish-an-updated-topology"></a>So veröffentlichen Sie eine aktualisierte Topologie

Installieren Sie vor dem Veröffentlichen der Topologie die Datenbanken für den Server für beständigen Chat. Verwenden Sie den Topologie-Generator, um Datenbanken zu installieren, indem Sie **Aktion** auswählen und **Datenbank installieren**.

1.  Melden Sie sich auf einem Computer, auf dem lync Server 2013 oder auf dem die lync Server Verwaltungstools installiert sind, mit einem Konto an, das Mitglied der Gruppe " **Domänen-Admins** " und der **RTCUniversalServerAdmins** -Gruppe ist. und verfügt über Vollzugriff auf den Dateispeicher, der für den Dateispeicher für persistent Chat Server verwendet werden kann (also Lese-, Schreib-und Änderungsberechtigungen), sodass der Topologie-Generator die erforderlichen DACLs (Discretionary Access Control Lists) oder ein Konto mit gleichwertigen Benutzerrechten konfigurieren kann.

2.  Starten Sie den Topologie-Generator. Wählen Sie **Topologie aus einer vorhandenen Bereitstellung herunterladen** oder, wenn Sie die Topologie lokal gespeichert haben, **Topologie aus einer lokalen Datei öffnen** aus.

3.  Klicken Sie in der Konsolenstruktur mit der rechten Maustaste auf **lync Server 2013**, und klicken Sie dann auf **Topologie veröffentlichen**.

4.  Klicken Sie auf der Seite **Topologie veröffentlichen** auf **Weiter**.

5.  Vergewissern Sie sich auf der Seite **Veröffentlichungs-Assistent abgeschlossen**, dass die Topologie erfolgreich veröffentlicht wurde, und klicken Sie anschließend auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Nach dem Veröffentlichen der Topologie müssen Sie die Unterstützung für den Server für beständigen Chat konfigurieren, bevor Inhalte archiviert werden können.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

