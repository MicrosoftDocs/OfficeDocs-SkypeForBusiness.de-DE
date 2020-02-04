---
title: Verschieben eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8cb89fde2a62858c3bd9a402207f4b23fd51643
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756049"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Verschieben eines einzelnen Benutzers in den Pilot Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Sie können einen Benutzer aus Ihrem Office Communications Server 2007 R2-Pool in ihren lync Server 2013-Pilot Pool mithilfe der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell verschieben. Im folgenden Beispiel ist ** \<Office Communications\> ** Server in der Spalte Registrierungspool der Office Communications Server 2007 R2-Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Führen Sie die folgenden Verfahren aus, um einen Benutzer mithilfe der lync Server 2013-Systemsteuerung und der lync Server-Verwaltungsshell in ihren lync Server 2013-Pool zu verschieben.

![Suchen nach OCS-Benutzern in der lync Server-Systemsteuerung](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Suchen nach OCS-Benutzern in der lync Server-Systemsteuerung")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>So verschieben Sie einen Benutzer mithilfe der lync Server 2013-Systemsteuerung

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe „RTCUniversalServerAdmins“ oder der Administratorrolle „CsAdministrator“ oder „CsUserAdministrator“ ist, am Front-End-Server an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie auf **Benutzer**.

4.  Klicken Sie auf der Registerkarte **Benutzersuche** auf die Schaltfläche **Suchen** .

5.  Klicken Sie als nächstes auf **Filter hinzufügen**.

6.  Erstellen Sie einen Filter, bei dem **Office Communications Server-Benutzer** gleich **true**ist.

7.  Klicken Sie auf **Suchen** , um nach Legacy Office Communications Server 2007 R2-Benutzern zu suchen.
    
    ![Suchen nach OCS-Benutzern in der lync Server-Systemsteuerung](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Suchen nach OCS-Benutzern in der lync Server-Systemsteuerung")  

8.  Wählen Sie einen Benutzer aus, den Sie in den lync Server 2013-Pool verschieben möchten. In diesem Beispiel verschieben wir den Benutzer Sara Davis.

9.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.

10. Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.

11. Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf **OK**.
    
    ![Festlegen des Ziel Pools im Dialogfeld "Benutzer verschieben"](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Festlegen des Ziel Pools im Dialogfeld "Benutzer verschieben"")  

12. Überprüfen Sie, ob die Spalte des **registrierungspools** für den Benutzer jetzt den lync Server 2013-Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>So verschieben Sie einen Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

