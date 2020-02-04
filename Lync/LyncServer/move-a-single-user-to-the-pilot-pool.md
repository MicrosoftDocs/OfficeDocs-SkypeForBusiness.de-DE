---
title: Verschieben eines einzelnen Benutzers in den Pilot Pool
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
ms.openlocfilehash: c14c4a772ced3939d979bd8d4cd053207b0c5613
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Verschieben eines einzelnen Benutzers in den Pilot Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Sie können einen Benutzer aus Ihrem lync Server 2010-Pool in ihren lync Server 2013-Pilot Pool mithilfe der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell verschieben. Im folgenden Beispiel wird in der Spalte Registrierungspool **pool01.contoso.net** der lync Server 2010-Pool angezeigt, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Führen Sie die folgenden Verfahren aus, um einen Benutzer mithilfe der lync Server 2013-Systemsteuerung und der lync Server-Verwaltungsshell in ihren lync Server 2013-Pool zu verschieben.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>So verschieben Sie einen Benutzer mithilfe der lync Server 2013-Systemsteuerung

**Liste der Benutzer in der lync Server 2013-Systemsteuerung**

![Lync Server-Systemsteuerung, Dialogfeld ' Benutzer verschieben '](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Lync Server-Systemsteuerung, Dialogfeld ' Benutzer verschieben '")

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.

2.  Öffnen Sie die **Lync Server-Systemsteuerung**.

3.  Klicken Sie auf **Benutzer** und anschließend auf **Suchen**.

4.  Wählen Sie einen Benutzer aus, den Sie in den lync Server 2013-Pool verschieben möchten. In diesem Beispiel verschieben wir den Benutzer Sara Davis.

5.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.

6.  Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.

7.  Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf **OK**.
    
    ![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '")  

8.  Überprüfen Sie, ob die Spalte des **registrierungspools** für den Benutzer jetzt den lync Server 2013-Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>So verschieben Sie einen Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Geben Sie als nächstes in der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "David Pelton"

4.  Die **RegistrarPool** -Identität verweist nun auf den lync Server 2013-Pool. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.
    
    ![Ausgabe vom Cmdlet "Get-CsUser" mit dem Identitäts Filter](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Ausgabe vom Cmdlet "Get-CsUser" mit dem Identitäts Filter")  
    
    <div>
    

    > [!NOTE]  
    > Details zum Cmdlet " <STRONG>Get-CsUser</STRONG> " finden Sie unter <STRONG>Get-Help Get-CsUser – detailed</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

