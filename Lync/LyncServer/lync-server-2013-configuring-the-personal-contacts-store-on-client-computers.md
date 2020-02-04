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
ms.openlocfilehash: 77e6e48593bb3dc7a11375b13346ad59b2f40c0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734625"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-personal-contacts-store-on-client-computers-for-lync-server-2013"></a>Konfigurieren des Speichers für persönliche Kontakte auf Clientcomputern für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Wenn Sie Microsoft lync Server 2013 und Microsoft Exchange Server 2013 integrieren, wird empfohlen, den persönlichen Kontaktspeicher auf allen Clientcomputern zu konfigurieren, auf denen Microsoft lync 2010 ausgeführt wird. Insbesondere sollten Sie lync so konfigurieren, dass Exchange als persönlicher Kontaktspeicher verwendet wird, und gleichzeitig sicherstellen, dass Benutzer diese Entscheidung nicht außer Kraft setzen können. Dies ist nur dann möglich, wenn Sie auf jedem Clientcomputer einen Registrierungswert erstellen und konfigurieren.

Beachten Sie, dass dies auf Computern, auf denen lync 2013 ausgeführt wird, nicht erforderlich ist.

Zum Konfigurieren dieses Werts auf einem einzelnen Computer führen Sie die folgenden Schritte aus:

1.  Klicken Sie auf dem Clientcomputer im Menü **Start** auf **Ausführen**.

2.  Geben Sie im Dialogfeld **Ausführen** den Befehl regedit ein und drücken Sie dann die EINGABETASTE.

3.  Erweitern Sie im Registrierungs- **Editor\_HKEY\_lokaler Computer**, erweitern Sie **Software**, erweitern Sie **Richtlinien**, erweitern Sie **Microsoft**, und erweitern Sie dann **Communicator**.

4.  Klicken Sie mit der rechten Maustaste auf **Communicator**, zeigen Sie auf **Neu** und klicken Sie auf **DWORD-Wert (32-Bit)**.

5.  Geben Sie nach dem Erstellen des neuen Werts **PersonalContactStoreOverride** ein und drücken Sie die EINGABETASTE, um den Wert umzubenennen.

6.  Stellen Sie sicher, dass der Wert von PersonalContactStoreOverride 0 ist, und schließen Sie dann den Registrierungs-Editor.

Wenn Sie die gleiche Änderung auf mehreren Computern durchführen müssen, können Sie dazu ein benutzerdefiniertes Gruppenrichtlinienobjekt erstellen. Ausführliche Informationen finden Sie in [http://go.microsoft.com/fwlink/p/?LinkId=268543](http://go.microsoft.com/fwlink/p/?linkid=268543)der Gruppenrichtlinien-Dokumentation unter.

</div>

<span> </span>

</div>

</div>

</div>

