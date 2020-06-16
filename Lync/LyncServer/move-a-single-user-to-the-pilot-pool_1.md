---
title: Verlagern eines einzelnen Benutzers in den Pilot Pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 200e929cb7dff4006ffe776504220618e5e7b570
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Verlagern eines einzelnen Benutzers in den Pilot Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Sie können einen Benutzer aus dem Office Communications Server 2007 R2 Pool mithilfe lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell in den lync Server 2013 Pilot Pool migrieren. Im Beispiel unten in der Spalte registrierungsstellenpool befindet sich **\<Office Communications Server\>** der Office Communications Server 2007 R2 Pool, und alle sechs dieser Benutzer sind mit diesem Pool verbunden. Verwenden Sie die folgenden Verfahren, um einen Benutzer mithilfe lync Server 2013 Systemsteuerung und lync Server-Verwaltungsshell in ihren lync Server 2013 Pool zu versetzen.

![Suchen nach OCS-Benutzern in lync Server-Systemsteuerung](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Suchen nach OCS-Benutzern in lync Server-Systemsteuerung")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>So können Sie einen Benutzer mithilfe der lync Server 2013-Systemsteuerung migrieren

1.  Melden Sie sich über ein Konto, das Mitglied der Gruppe "RTCUniversalServerAdmins" oder der Administratorrolle "CsAdministrator" oder "CsUserAdministrator" ist, am Front-End-Server an.

2.  Öffnen Sie die Lync Server-Systemsteuerung.

3.  Klicken Sie auf **Benutzer**.

4.  Klicken Sie auf der Registerkarte **Benutzersuche** auf **Suchen**.

5.  Klicken Sie anschließend auf **Filter hinzufügen**.

6.  Erstellen Sie einen Filter, wobei der Wert für den Office Communications Server-Benutzer**** dem Wert **True** entspricht.

7.  Klicken Sie auf **Suchen** , um nach Legacy Office Communications Server 2007 R2 Benutzern zu suchen.
    
    ![Suchen nach OCS-Benutzern in lync Server-Systemsteuerung](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Suchen nach OCS-Benutzern in lync Server-Systemsteuerung")  

8.  Wählen Sie einen Benutzer aus, den Sie in den lync Server 2013 Pool umlegen möchten. In diesem Beispiel verschieben wir Sara Davis.

9.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben**.

10. Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.

11. Klicken Sie auf **Aktion**, und klicken Sie anschließend auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf **OK**.
    
    ![Festlegen des Ziel Pools im Dialogfeld "Benutzer migrieren"](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Festlegen des Ziel Pools im Dialogfeld "Benutzer migrieren"")  

12. Stellen Sie sicher, dass die Spalte **Registrierungspool** für den Benutzer jetzt den lync Server 2013 Pool enthält, der angibt, dass der Benutzer erfolgreich verschoben wurde.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>So migrieren Sie einen Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die Lync Server-Verwaltungsshell.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

