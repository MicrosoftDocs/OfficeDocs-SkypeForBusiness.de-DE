---
title: Mehrere Benutzer in den Pilot Pool migrieren
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81b5ad16b36063c217d90c4c8f1e8a2e7fa3c0ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Mehrere Benutzer in den Pilot Pool migrieren

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-02_

Sie können mehrere Benutzer aus dem lync Server 2010 Pool mithilfe lync Server 2013 Systemsteuerung oder lync Server 2013 Verwaltungsshell in den lync Server 2013-Pilot Pool migrieren.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>So können Sie mehrere Benutzer mithilfe der lync Server 2013-Systemsteuerung migrieren

1.  Öffnen Sie die **Lync Server-Systemsteuerung**.

2.  Klicken Sie auf **Benutzer**, dann auf die Suche und auf **Suchen**.

3.  Wählen Sie zwei Benutzer aus, die Sie in den lync Server 2013 Pool umlegen möchten. In diesem Beispiel werden wir die Benutzer Chen Yang und Claus Hansen verschieben.
    
    ![Migrieren von Benutzern zu einem bestimmten Register Pool](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Migrieren von Benutzern zu einem bestimmten Register Pool")  

4.  Wählen Sie im Menü **Aktion** die Option **Ausgewählte Benutzer in Pool verschieben** aus.

5.  Wählen Sie in der Dropdownliste den lync Server 2013 Pool aus.

6.  Klicken Sie auf **Aktion** und dann auf **Ausgewählte Benutzer in Pool verschieben**. Klicken Sie auf "OK".
    
    ![Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Dialogfeld zum Migrieren von Benutzern, Ziel registrierungsstellenpool")  

7.  Stellen Sie sicher, dass die Spalte **Registrierungspool** für die Benutzer jetzt den lync Server 2013 Pool enthält, der angibt, dass die Benutzer erfolgreich verschoben wurden.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>So migrieren Sie mehrere Benutzer mithilfe der lync Server 2013-Verwaltungsshell

1.  Öffnen Sie die lync Server 2013 Management-Shell.

2.  Geben Sie an der Befehlszeile Folgendes ein, und ersetzen Sie **User1** und **Benutzer2** durch bestimmte Benutzernamen, die Sie migrieren möchten, und ersetzen Sie den **Pool\_-FQDN** durch den Namen des Ziel Pools. In diesem Beispiel verschieben wir die Benutzer Hao Chen und Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Beispiel für das PowerShell Get-CsUser-Cmdlet](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Beispiel für das PowerShell Get-CsUser-Cmdlet")  

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsUser -Identity "User1"

4.  Die Identität des **Registrierungsstellen Pools** sollte nun auf den Pool verweist, den Sie im vorherigen Schritt als **Pool\_-FQDN** angegeben haben. Das Vorhandensein dieser Identität bestätigt, dass die Benutzer erfolgreich verschoben wurden. Wiederholen Sie den Schritt, um zu prüfen, ob **User2** verschoben wurde.
    
    ![Ausgabe des PowerShell Get-UsUser-Identity-Cmdlets](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Ausgabe des PowerShell Get-UsUser-Identity-Cmdlets")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>So führen Sie eine gleichzeitige Verlagerung aller Benutzer mithilfe der lync Server 2013 Management-Shell aus

In diesem Beispiel wurden alle Benutzer an den lync Server 2010 Pool (pool01.contoso.net) zurückgegeben. Mithilfe der lync Server 2013-Verwaltungsshell werden alle Benutzer gleichzeitig in den lync Server 2013 Pool (pool02.contoso.net) verlagert.

1.  Öffnen Sie die **lync Server 2013 Management-Shell**.

2.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![PowerShell-Cmdlet und Ergebnisse in der Verwaltungskonsole](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "PowerShell-Cmdlet und Ergebnisse in der Verwaltungskonsole")  

3.  Führen Sie dann für einen der Pilotbenutzer **Get-CsUser** aus.
    
        Get-CsUser -Identity "Hao Chen"

4.  Die Identität des **Registrierungsstellen Pools** für jeden Benutzer verweist nun auf den Pool, den Sie\_im vorherigen Schritt als Pool-FQDN angegeben haben. Das Vorhandensein dieser Identität zeigt, dass der Benutzer erfolgreich verschoben wurde.

5.  Darüber hinaus können wir die Liste der Benutzer in der lync Server 2013-Systemsteuerung anzeigen und überprüfen, ob der Wert des Registrierungsstellen Pools nun auf den lync Server 2013-Pool zeigt.
    
    ![Benutzerliste für lync Server 2013 Systemsteuerung](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Benutzerliste für lync Server 2013 Systemsteuerung")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

