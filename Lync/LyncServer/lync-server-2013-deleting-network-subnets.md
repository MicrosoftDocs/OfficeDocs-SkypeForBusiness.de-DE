---
title: 'Lync Server 2013: Löschen von Netzwerk-Subnetzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network subnets
ms:assetid: c1850f38-40a3-48c9-b6f1-f181c5e63b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721873(v=OCS.15)
ms:contentKeyID: 49733806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c87ca1cfd91344d8f8cbb0b320c70def47bf5ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-subnets-in-lync-server-2013"></a>Löschen von Netzwerk-Subnetzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Sie können das folgende Verfahren verwenden, um ein Subnetz zu löschen. In der lync Server-Systemsteuerung können Sie ein Netzwerk-Subnetz erstellen, ändern oder löschen. Details zum Erstellen oder Ändern von Netzwerk-Subnetzen finden Sie unter Erstellen oder Ändern von Netzwerk-Subnetzen [in lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md).

In den meisten Bereitstellungen von Microsoft lync Server 2013, bei denen die Anrufannahme Steuerung (Call Admission Control, CAC) implementiert ist, gibt es in der Regel eine große Anzahl von Subnetzen. Aus diesem Grund ist es am besten, Subnets aus der lync Server-Verwaltungsshell zu konfigurieren. Von dort aus können Sie **New-CsNetworkSubnet** in Verbindung mit dem Windows PowerShell **-Cmdlet Import-CSV**aufrufen. Wenn Sie diese Cmdlets zusammen verwenden, können Sie die subneteinstellungen aus einer CSV-Datei (Comma-Separated Values) lesen und gleichzeitig mehrere Subnetze erstellen. Beispiele zum Erstellen von Subnetzen aus einer CSV-Datei finden Sie unter [New-CsNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSubnet).

<div>

## <a name="to-delete-a-network-subnet"></a>So löschen Sie ein Netzwerk-Subnetz

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Subnetz**.

4.  Klicken Sie auf der Seite **Subnetz** auf das Subnetz, das Sie löschen möchten.
    
    <div>
    

    > [!NOTE]  
    > Sie können mehr als ein Subnetz gleichzeitig löschen. Drücken Sie dazu STRG, und wählen Sie mehrere Subnetze aus, während Sie die STRG-Taste gedrückt halten. Wenn Sie alle Subnetze auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alles auswählen</STRONG> .

    
    </div>

5.  Klicken Sie im Menü **Bearbeiten** auf **Löschen**.

6.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern von Netzwerk-Subnetzen in lync Server 2013](lync-server-2013-create-or-modify-network-subnets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

