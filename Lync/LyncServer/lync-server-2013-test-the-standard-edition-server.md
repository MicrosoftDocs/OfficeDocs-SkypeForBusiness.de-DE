---
title: 'Lync Server 2013: Testen der Standard Edition-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4145740f09557c8f39830dce689fa122456a28f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Testen der Standard Edition-Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Im folgenden Verfahren wird beschrieben, wie Sie die Bereitstellungeines Standard Edition-Server testen.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>So testen Sie die Bereitstellung eines Standard Edition-Servers

1.  Verwenden Sie Active Directory Computer und Benutzer, um das Active Directory-Benutzerobjekt der Administratorrolle für die lync Server 2013-Bereitstellung (auf dem lync Server-Systemsteuerung installiert ist) zur Gruppe **CSAdministrator** hinzuzufügen.

2.  Wenn das Benutzerobjekt derzeit angemeldet ist, melden Sie es ab und wieder an, um die neue Gruppenzuweisung zu registrieren.
    
    <div>
    

    > [!NOTE]  
    > Das Benutzerkonto kann nicht der lokale Administrator des Servers sein, auf dem lync Server 2013 Standard Edition installiert ist. Wenn Sie der Gruppe CsAdministors die entsprechenden Benutzer und Gruppen nicht hinzufügen, wird beim Öffnen lync Server 2013 Systemsteuerung eine Fehlermeldung angezeigt, die besagt, dass "nicht autorisiert: der Zugriff aufgrund eines RBAC-Autorisierungs Fehlers (Role-Based Access Control) verweigert wird."

    
    </div>

3.  Melden Sie sich mit dem Administratorkonto bei dem Computer an, auf dem lync Server-Systemsteuerung installiert ist.

4.  Wenn Sie dazu aufgefordert werden, starten Sie lync Server-Systemsteuerung und geben Sie Anmeldeinformationen an. In lync Server 2013 Systemsteuerung werden Bereitstellungsinformationen angezeigt.

5.  Klicken Sie in der linken Navigationsleiste auf **Topologie**, und vergewissern Sie sich, dass der Dienststatus ein Computersymbol mit einem grünen Pfeil ist und neben jeder lync Server Server Rolle, die bereitgestellt und online geschaltet wurde, ein grünes Häkchen angezeigt wird.

6.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**, und aktivieren Sie dann die beiden Benutzer für lync Server 2013.

7.  Melden Sie einen Benutzer bei einem Computer, der Teil der Domäne ist, und den anderen Benutzer bei einem anderen Computer in der Domäne an.

8.  Installieren Sie lync Server 2013 auf den beiden Clientcomputern, und stellen Sie dann sicher, dass sich beide Benutzer bei lync Server 2013 anmelden und Sofortnachrichten miteinander senden können.

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

