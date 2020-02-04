---
title: 'Lync Server 2013: Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a new trusted application server
ms:assetid: a7233db7-fac3-43ff-972e-3bc29a56adb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg617964(v=OCS.15)
ms:contentKeyID: 48185085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dae7e02d7642fed5fea60235283eaa0d7d7e1e35
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-new-trusted-application-server-in-lync-server-2013"></a>Konfigurieren eines neuen vertrauenswürdigen Anwendungsservers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Bei einer vertrauenswürdigen Anwendung handelt es sich um eine Anwendung, die auf dem Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK basiert, das von Microsoft lync Server 2013 als vertrauenswürdig eingestuft wird. Ausführliche Informationen zu UCMA-Anwendungen finden Sie unter "Unified Communications Managed API 3,0 Core SDK Documentation [http://go.microsoft.com/fwlink/p/?linkId=210320](http://go.microsoft.com/fwlink/p/?linkid=210320)" unter.

Informationen zum Konfigurieren von Microsoft Outlook Web Access (OWA) und lync Server 2013 finden Sie unter "Konfigurieren der Integration von Outlook Web App und lync Server 2010" in der Microsoft Exchange Server 2013-Dokumentation.

Um eine Topologie beim Hinzufügen oder Entfernen einer Serverrolle erfolgreich zu veröffentlichen, zu aktivieren oder zu deaktivieren, sollten Sie als Benutzer angemeldet sein, der Mitglied der Gruppen RTCUniversalServerAdmins und Domänenadministratoren ist. Es ist auch möglich, die richtigen Administratorberechtigungen und-Rechte für das Hinzufügen von Serverrollen zu delegieren. Ausführliche Informationen finden Sie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md) in der Bereitstellungsdokumentation. Bei anderen Konfigurationsänderungen ist nur die Mitgliedschaft in der RTCUniversalServerAdmins-Gruppe erforderlich.

<div>

## <a name="to-configure-a-trusted-application-server"></a>So konfigurieren Sie einen vertrauenswürdigen Anwendungsserver

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

3.  Wählen Sie **Topologie aus vorhandener Bereitstellung herunterladen aus**, und klicken Sie dann auf **OK**.

4.  Klicken Sie im Dialogfeld **Topologie speichern** unter auf die Topologie-Generator-Datei, die Sie verwenden möchten, und klicken Sie dann auf **Speichern**.

5.  Klicken Sie im linken Bereich mit der rechten Maustaste auf **Vertrauenswürdige Anwendungsserver**, und klicken Sie dann auf **neuer vertrauenswürdiger Anwendungs Pool**.

6.  Geben Sie den **Pool-FQDN** des vertrauenswürdigen Anwendungspools ein, wählen Sie aus, ob es sich um einen Einzelserver-oder mehrere Server handelt, und klicken Sie dann auf **weiter**.

7.  Wählen Sie auf der Seite **Nächster Hop auswählen** in der Liste den lync Server 2013-Front-End-Pool aus.

8.  Klicken Sie auf **Fertig stellen**.

9.  Wählen Sie den obersten Knoten **lync Server 2013**aus, und klicken Sie dann im Menü **Aktionen** auf **Topologie veröffentlichen**.
    
    Der **Vertrauenswürdige Anwendungspool** sollte erfolgreich erstellt und dem richtigen Front-End-Pool zugeordnet sein.

</div>

</div>

<span> </span>

</div>

</div>

</div>

