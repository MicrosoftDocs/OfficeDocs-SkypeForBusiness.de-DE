---
title: 'Lync Server 2013: Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the personal contacts store on client computers
ms:assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721922(v=OCS.15)
ms:contentKeyID: 49733857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d791943f8d4057c173851e5d6eedb4a713b3cdf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Konfigurieren des persönlichen Kontaktspeichers auf Clientcomputern für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-02-05_

Wenn Sie Microsoft lync Server 2013 und Microsoft Exchange Server 2013 integrieren, wird empfohlen, den persönlichen Kontaktspeicher auf allen Clientcomputern zu konfigurieren, auf denen Microsoft lync 2010 läuft. Insbesondere sollten Sie lync so konfigurieren, dass Exchange als persönlicher Kontaktspeicher verwendet wird, und gleichzeitig sicherstellen, dass Benutzer diese Entscheidung nicht außer Kraft setzen können. Dies kann durch Erstellen und Konfigurieren eines Registrierungswerts auf jedem Clientcomputer erfolgen.

Beachten Sie, dass dies auf Computern mit lync 2013 nicht erforderlich ist.

Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:

1.  Klicken Sie auf dem Clientcomputer auf **Start** , und klicken Sie dann auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein, und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs- **Editor\_den\_Knoten HKEY lokaler Computer**, erweitern Sie **Software**, **Richtlinien**und dann **Microsoft**, und erweitern Sie dann **Communicator**.

4.  Klicken Sie mit der rechten Maustaste auf **Communicator**, dann auf **neu**, und klicken Sie dann auf **DWORD-Wert (32-Bit)**.

5.  Nachdem der neue Wert erstellt wurde, geben Sie **PersonalContactStoreOverride** ein, und drücken Sie dann die EINGABETASTE, um den Wert umzubenennen.

6.  Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Ausführliche Informationen finden Sie in [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?linkid=268543)der Dokumentation zur Gruppenrichtlinie unter.

</div>

<span> </span>

</div>

</div>

</div>

