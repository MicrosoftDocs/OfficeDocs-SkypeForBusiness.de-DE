---
title: Verlagern eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 187b0b3055710f89b8c16d8167c1b6692d5eaac2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Verlagern eines einzelnen Benutzers in den Pilot Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Sie können einen Benutzer aus dem lync Server 2010 Pool mithilfe lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell in den lync Server 2013 Pilot Pool migrieren. Im Beispiel unten in der Spalte registrierungsstellenpool ist **pool01.contoso.net** der lync Server 2010 Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer mithilfe lync Server 2013 Systemsteuerung und lync Server-Verwaltungsshell in ihren lync Server 2013 Pool zu versetzen.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>So können Sie einen Benutzer mithilfe der lync Server 2013-Systemsteuerung migrieren

**Liste der Benutzer in der lync Server 2013-Systemsteuerung**

![Lync Server-Systemsteuerung, Dialogfeld "Benutzer Verschiebe"](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server-Systemsteuerung, Dialogfeld "Benutzer Verschiebe"")

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.

2.  Öffnen Sie die **Lync Server-Systemsteuerung**.

3.  Klicken Sie auf **Benutzer**, dann auf die Suche und auf **Suchen**.

4.  Wählen Sie einen Benutzer aus, den Sie in den lync Server 2013 Pool umlegen möchten. In diesem Beispiel verschieben wir Sara Davis.

5.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.

6.  Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.

7.  Klicken Sie auf **Aktion**, und klicken Sie anschließend auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
    
    ![Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool")  

8.  Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den lync Server 2013 Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>So migrieren Sie einen Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Geben Sie anschließend an der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "David Pelton"

4.  Die **RegistrarPool** -Identität verweist nun auf den lync Server 2013-Pool. Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.
    
    ![Ausgabe von Get-CsUser-Cmdlet mit Identitäts Filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Ausgabe von Get-CsUser-Cmdlet mit Identitäts Filter")  
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen zum Cmdlet <STRONG>Get-CsUser</STRONG> erhalten Sie, indem Sie Folgendes ausführen: <STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

