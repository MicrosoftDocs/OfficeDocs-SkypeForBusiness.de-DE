---
title: 'Lync Server 2013: Starten von Diensten auf Servern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Starten von Diensten auf Servern für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-09-03_

Um dieses Verfahren erfolgreich abzuschließen, sollten Sie als Benutzer angemeldet sein, der ein Mitglied der RTCUniversalServerAdmins-Gruppe ist oder über die richtigen Berechtigungen delegiert wurde. Details zum Delegieren von Berechtigungen finden Sie im Thema [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Nachdem Sie den lokalen Konfigurationsspeicher auf Ihren Servern installiert, die lync Server 2013-Komponenten installiert und Zertifikate auf einem Front-End-Server oder Front-End-Server konfiguriert haben, müssen Sie die lync Server 2013-Dienste auf dem Server starten. Gehen Sie wie folgt vor, um Dienste auf jedem Front-End-Server in Ihrer Bereitstellung zu starten.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>So starten Sie Dienste auf einer Standard Edition oder einem Front-End-Server

1.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf der **lync Server 2013** -Seite neben **Schritt 4: Starten von Diensten**auf **Ausführen** .

2.  Klicken Sie auf der Seite **Dienste starten** auf **weiter** , um die lync Server-Dienste auf dem Server zu starten.

3.  Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Befehl zum Starten der Dienste auf dem Server ist die beste Methode, um zu melden, dass die Dienste tatsächlich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des jeweiligen Diensts wider. Wir empfehlen, dass Sie den Schritt <STRONG>Dienst Status (optional)</STRONG> unmittelbar nach dem <STRONG>Start der Dienste</STRONG> verwenden, um die Microsoft Management Console (MMC) zu öffnen und zu bestätigen, dass die Dienste erfolgreich gestartet wurden. Wenn ein lync Server-Dienst nicht gestartet wurde, können Sie mit der rechten Maustaste auf diesen Dienst in der MMC klicken, und klicken Sie dann auf <STRONG>Start</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

