---
title: Verschieben mehrerer Benutzer in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ffc3e01df30f4a8e1b9c9b9aeca2b2013003980
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Verschieben mehrerer Benutzer in den Pilot Pool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-02_

Sie können mehrere Benutzer aus Ihrem Office Communications Server 2007 R2-Pool in ihren lync Server 2013-Pilot Pool mithilfe der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell verschieben.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Systemsteuerung

1.  Öffnen Sie die **Lync Server-Systemsteuerung**.

2.  Klicken Sie auf der Registerkarte **Benutzersuche** auf die Schaltfläche **Suchen** .

3.  Klicken Sie als nächstes auf **Filter hinzufügen**.

4.  Erstellen Sie einen Filter, bei dem **Office Communications Server-Benutzer** gleich **true**ist.

5.  Klicken Sie auf **Suchen** , um nach Legacy Office Communications Server 2007 R2-Benutzern zu suchen.

6.  Wählen Sie zwei Benutzer aus, die Sie in den lync Server 2013-Pool verschieben möchten. In diesem Beispiel werden die Benutzer Chen Yang und Claus Hansen verschoben.
    
    ![Von der Suche nach OCS-Benutzern angezeigte Benutzerliste] (images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Von der Suche nach OCS-Benutzern angezeigte Benutzerliste")  

7.  Wählen Sie im Menü **Aktion** die Option **ausgewählte Benutzer in Pool verschieben**aus.

8.  Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.

9.  Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf OK.
    
    ![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '")  

10. Überprüfen Sie, ob die Spalte des **registrierungspools** für die Benutzer jetzt den lync Server 2013-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die lync Server 2013-Verwaltungsshell.

2.  Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **Benutzer1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie den **FQDN des Pools\_** durch den Namen des Ziel Pools. In diesem Beispiel werden die Benutzer Hao Chen und Katie Jordan verschoben.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Beispiel-Cmdlet zum Verschieben eines Legacy Benutzers] (images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Beispiel-Cmdlet zum Verschieben eines Legacy Benutzers")  

3.  Geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "User1"

4.  Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweisen, den Sie im vorherigen Schritt als **Pool\_-FQDN** angegeben haben. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. Wiederholen Sie den Schritt, um zu überprüfen, ob **User2** verschoben wurde.
    
    ![Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>So verschieben Sie alle Benutzer gleichzeitig mithilfe der lync Server 2013-Verwaltungsshell

In diesem Beispiel wurden alle Benutzer an den Office Communications Server 2007 R2-Pool (pool01.contoso.net) zurückgegeben. Mit der lync Server 2013-Verwaltungsshell werden alle Benutzer gleichzeitig in den lync Server 2013-Pool (pool02.contoso.net) verschoben.

1.  Öffnen Sie die **lync Server 2013-Verwaltungsshell**.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Beispiel-Cmdlet zum Verschieben aller Legacy Benutzer in einem Pool] (images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Beispiel-Cmdlet zum Verschieben aller Legacy Benutzer in einem Pool")  

3.  Führen Sie als nächstes " **Get-CsUser** " für einen der Pilotbenutzer aus.
    
        Get-CsUser -Identity "Hao Chen"

4.  Die Identität des **registrierungspools** für jeden Benutzer verweist nun auf den Pool, den Sie im\_vorherigen Schritt als "Pool-FQDN" angegeben haben. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde.

5.  Darüber hinaus können wir die Liste der Benutzer in der lync Server 2013-Systemsteuerung anzeigen und überprüfen, ob der Wert des registrierungspools nun auf den lync Server 2013-Pool verweist.
    
    ![Benutzerliste der lync Server 2013-System] Steuerung (images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Benutzerliste der lync Server 2013-System") Steuerung  

</div>

</div>

<span> </span>

</div>

</div>

</div>

