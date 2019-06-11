---
title: 'Lync Server 2013: Testen des Standard Edition-Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a960451ebdd1e6e8728bf3b6c7df6e267c49c3f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Testen des Standard Edition-Servers in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellungeines Standard Edition-Servers testen.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>So testen Sie die Bereitstellungeines Standard Edition-Servers

1.  Verwenden Sie Active Directory-Computer und-Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (auf der lync Server Control Panel installiert ist) zur **CSAdministrator** -Gruppe hinzuzufügen.

2.  Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    <div>
    

    > [!NOTE]  
    > Das Benutzerkonto kann nicht der lokale Administrator des Servers sein, auf dem lync Server 2013, Standard Edition, ausgeführt wird. Wenn Sie die entsprechenden Benutzer und Gruppen nicht zur CsAdministors-Gruppe hinzufügen, erhalten Sie eine Fehlermeldung, wenn Sie die lync Server 2013-Systemsteuerung öffnen, in der angegeben ist, dass "nicht autorisiert: der Zugriff verweigert wird aufgrund eines Autorisierungs Fehlers bei der rollenbasierten Zugriffssteuerung (Role-Based Access Control, RBAC)".

    
    </div>

3.  Verwenden Sie das Administratorkonto, um sich bei dem Computer anzumelden, auf dem die lync Server-Systemsteuerung installiert ist.

4.  Starten Sie die lync Server-Systemsteuerung, und geben Sie bei Aufforderung Anmeldeinformationen ein. Die lync Server 2013-Systemsteuerung zeigt Bereitstellungsinformationen an.

5.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und stellen Sie dann sicher, dass es sich bei dem Dienststatus um ein Computersymbol mit einem grünen Pfeil und ein grünes Häkchen neben jeder lync Server-Serverrolle handelt, die bereitgestellt und online geschaltet wurde.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und aktivieren Sie dann die beiden Benutzer für lync Server 2013.

7.  Melden Sie einen Benutzer an einem Computer, der mit der Domäne verbunden ist, und dem anderen Benutzer auf einem anderen Computer in der Domäne an.

8.  Installieren Sie lync Server 2013 auf jedem der beiden Clientcomputer, und stellen Sie dann sicher, dass sich beide Benutzer bei lync Server 2013 anmelden können und Sofortnachrichten senden können.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von Clients und Geräten in lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

