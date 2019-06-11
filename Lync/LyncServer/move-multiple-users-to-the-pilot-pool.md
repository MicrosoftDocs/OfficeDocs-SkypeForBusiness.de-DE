---
title: Verschieben mehrerer Benutzer in den Pilot Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc3104566841cc70eeee489a4b8812a6b8039a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847082"
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

Mithilfe der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell können Sie mehrere Benutzer aus Ihrem lync Server 2010-Pool in ihren lync Server 2013-Pilot Pool verschieben.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Systemsteuerung

1.  Öffnen Sie die **Lync Server-Systemsteuerung**.

2.  Klicken Sie auf **Benutzer** und anschließend auf **Suchen**.

3.  Wählen Sie zwei Benutzer aus, die Sie in den lync Server 2013-Pool verschieben möchten. In diesem Beispiel werden die Benutzer Chen Yang und Claus Hansen verschoben.
    
    ![Verschieben von Benutzern in einen bestimmten Registrierungspool] (images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Verschieben von Benutzern in einen bestimmten Registrierungspool")  

4.  Wählen Sie im Menü **Aktion** die Option **ausgewählte Benutzer in Pool verschieben**aus.

5.  Wählen Sie in der Dropdownliste den lync Server 2013-Pool aus.

6.  Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie anschließend auf OK.
    
    ![Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '] (images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld ' Benutzer verschieben, Ziel Registrierungspool '")  

7.  Überprüfen Sie, ob die Spalte des **registrierungspools** für die Benutzer jetzt den lync Server 2013-Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>So verschieben Sie mehrere Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die lync Server 2013-Verwaltungsshell.

2.  Geben Sie in der Befehlszeile Folgendes ein, und ersetzen Sie **Benutzer1** und **User2** durch bestimmte Benutzernamen, die Sie verschieben möchten, und ersetzen Sie den **FQDN des Pools\_** durch den Namen des Ziel Pools. In diesem Beispiel werden die Benutzer Hao Chen und Katie Jordan verschoben.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Beispiel für ein PowerShell-Cmdlet "Get-CsUser] " (images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Beispiel für ein PowerShell-Cmdlet \"Get-CsUser") "  

3.  Geben Sie in der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "User1"

4.  Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweisen, den Sie im vorherigen Schritt als **Pool\_-FQDN** angegeben haben. Das vorhanden sein dieser Identität bestätigt, dass der Benutzer erfolgreich verschoben wurde. Wiederholen Sie den Schritt, um zu überprüfen, ob **User2** verschoben wurde.
    
    ![Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity] (images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe des PowerShell-Cmdlets Get-UsUser-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>So verschieben Sie alle Benutzer gleichzeitig mithilfe der lync Server 2013-Verwaltungsshell

In diesem Beispiel wurden alle Benutzer an den lync Server 2010 Pool (pool01.contoso.net) zurückgegeben. Mit der lync Server 2013-Verwaltungsshell werden alle Benutzer gleichzeitig in den lync Server 2013-Pool (pool02.contoso.net) verschoben.

1.  Öffnen Sie die **lync Server 2013-Verwaltungsshell**.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell] (images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell-Cmdlet und Ergebnisse in der Verwaltungsshell")  

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

