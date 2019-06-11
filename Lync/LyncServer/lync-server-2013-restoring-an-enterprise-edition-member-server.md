---
title: 'Lync Server 2013: Wiederherstellen eines Enterprise Edition-Mitgliedsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Wiederherstellen eines Enterprise Edition-Mitgliedsservers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-18_

Wenn auf einem Server, auf dem eine der folgenden Serverrollen ausgeführt wird, ein Fehler auftritt, führen Sie die Schritte in diesem Thema aus, um den Server wiederherzustellen. Wenn mehrere Server unabhängig voneinander auftreten, führen Sie das Verfahren für jeden Server aus.

  - Front-End-Server

  - Vermittlungsserver

  - Director

  - Server für beständigen Chat

  - Edgeserver

<div>


> [!TIP]  
> Wir empfehlen, dass Sie eine Image-Kopie des Systems erstellen, bevor Sie mit der Wiederherstellung beginnen. Sie können dieses Bild als Rollback-Punkt verwenden, falls während der Wiederherstellung etwas schief geht. Möglicherweise möchten Sie das Abbild kopieren, nachdem Sie das Betriebssystem und SQL Server installiert haben, und die Zertifikate wiederherstellen oder erneut registrieren.



</div>

<div>

## <a name="to-restore-a-member-server"></a>So stellen Sie einen Mitgliedsserver wieder her

1.  Beginnen Sie mit einem sauberen oder neuen Server, der den gleichen vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) wie der fehlerhafte Server aufweist, installieren Sie das Betriebssystem, und stellen Sie die Zertifikate dann wieder her oder registrieren Sie Sie erneut.
    
    <div>
    

    > [!NOTE]  
    > Befolgen Sie die Server Bereitstellungsverfahren Ihrer Organisation, um diesen Schritt ausführen zu können.

    
    </div>

2.  Melden Sie sich von einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist, bei dem Server an, den Sie wiederherstellen möchten.

3.  Navigieren Sie zum lync Server-Installationsordner oder-Medium, und starten Sie den lync Server- \\Bereitstellungs-Assistenten unter Setup\\amd64\\Setup. exe.

4.  Folgen Sie dem Bereitstellungs-Assistenten, um folgende Aktionen auszuführen:
    
    1.  Führen Sie **Schritt 1: Installieren des lokalen Konfigurationsspeichers** aus, um die lokalen Konfigurationsdateien zu installieren.
    
    2.  Führen **Sie Schritt 2: Einrichten oder Entfernen von lync Server-Komponenten** aus, um die lync Server-Serverrolle zu installieren.
    
    3.  Führen Sie **Schritt 3 aus: anfordern, installieren oder Zuweisen von Zertifikaten** zum Zuweisen der Zertifikate.
    
    4.  Führen Sie **Schritt 4: Dienste starten** aus, um Dienste auf dem Server zu starten.
    
    Details zum Ausführen des Bereitstellungs-Assistenten finden Sie in der Bereitstellungsdokumentation für die Serverrolle, die Sie wiederherstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

