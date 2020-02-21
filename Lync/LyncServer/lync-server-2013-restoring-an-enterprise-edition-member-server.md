---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Mitgliedsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48af9dd5b35676ee0141b771f8e50e1fbdedae6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-18_

Wenn ein Server mit einer der folgenden Serverrollen ausfällt, führen Sie das Verfahren in diesem Thema aus, um den Server wiederherzustellen. Sollten mehrere Server unabhängig voneinander ausfallen, führen Sie diese Schritte für jeden einzelnen Server aus.

  - Front-End-Server

  - Vermittlungsserver

  - Director

  - Server für beständigen Chat

  - Edgeserver

<div>


> [!TIP]  
> Es wird empfohlen, eine Abbild Kopie des Systems zu erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Argument verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem installiert und SQL Server und die Zertifikate wiederhergestellt oder erneut registriert haben.



</div>

<div>

## <a name="to-restore-a-member-server"></a>So stellen Sie einen Mitgliedsserver wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server mit dem gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) als fehlerhaften Server, installieren Sie das Betriebssystem, und stellen Sie dann die Zertifikate wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Gehen Sie nach den in Ihrer Organisation gültigen Verfahren für die Serverbereitstellung vor, um diesen Schritt durchzuführen.

    
    </div>

2.  Melden Sie sich von einem Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist, bei dem Server an, den Sie wiederherstellen.

3.  Wechseln Sie zum lync Server Installationsordner oder Medien, und starten Sie den lync Server-Bereitstellungs \\-\\Assistenten\\, der sich unter Setup amd64 Setup. exe befindet.

4.  Folgen Sie dem Bereitstellungs-Assistenten, um folgende Schritte auszuführen:
    
    1.  Führen Sie **Schritt 1: Lokalen Konfigurationsspeicher installieren** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server Komponenten** aus, um die lync Server-Server Rolle zu installieren.
    
    3.  Führen Sie **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** aus, um die Zertifikate zuzuweisen.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um die Dienste auf dem Server zu starten.
    
    Ausführliche Informationen zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

