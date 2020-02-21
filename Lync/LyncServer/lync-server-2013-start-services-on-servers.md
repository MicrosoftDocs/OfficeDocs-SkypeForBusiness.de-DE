---
title: 'Lync Server 2013: Starten von Diensten auf Servern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cab7d2e53b981cc971284cfad37f89ca4749590
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a>Starten von Diensten auf Servern für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-09-03_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie als Mitglied der Gruppe "RTCUniversalServerAdmins" angemeldet sein, oder an Sie müssen geeignete Berechtigungen delegiert worden sein. Ausführliche Informationen zum Delegieren von Berechtigungen finden Sie im Thema [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

Nachdem Sie den lokalen Konfigurationsspeicher auf Ihren Servern installiert, die lync Server 2013 Komponenten installiert und Zertifikate auf einem Front-End-Server oder Front-End-Server konfiguriert haben, müssen Sie die lync Server 2013 Dienste auf dem Server starten. Verwenden Sie das folgende Verfahren, um Dienste auf jeder Front-End-Server in Ihrer Bereitstellung zu starten.

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a>So starten Sie Dienste auf einer Standard Edition oder Front-End-Server

1.  Klicken Sie im lync Server-Bereitstellungs-Assistenten auf der Seite **lync Server 2013** auf **Ausführen** neben **Schritt 4: Dienste starten**.

2.  Klicken Sie auf der Seite **Dienste starten** auf **weiter** , um die lync Server Dienste auf dem Server zu starten.

3.  Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    <div>
    

    > [!IMPORTANT]  
    > Der Befehl zum Starten der Dienste auf dem Server ist eine Best-Effort-Methode zum Anzeigen, dass die Dienste wirklich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider. Es wird empfohlen, den Schritt <STRONG>Dienststatus (optional)</STRONG> unmittelbar nach Ausführung des Schritts <STRONG>Dienste starten</STRONG> auszuführen und mithilfe der Microsoft Management Console (MMC) zu bestätigen, dass die Dienste erfolgreich gestartet wurden. Wenn lync Server Dienst noch nicht gestartet wurde, können Sie in der MMC mit der rechten Maustaste auf diesen Dienst klicken, und klicken Sie dann auf <STRONG>starten</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

