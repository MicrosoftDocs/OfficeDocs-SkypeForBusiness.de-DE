---
title: 'Lync Server 2013: Löschen eines Bereichs nicht zugewiesener Nummern'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an unassigned number range
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48185090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99d2578d90ef710c15b6120b9a05481a974a0117
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-unassigned-number-range-in-lync-server-2013"></a>Löschen eines Bereichs nicht zugewiesener Nummern in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-01_

Verwenden Sie eines der folgenden Verfahren, um einen nicht zugewiesenen Nummernbereich für Ankündigungen zu löschen.

<div>

## <a name="to-use-lync-server-control-panel-to-delete-an-unassigned-number-range"></a>So verwenden Sie lync Server-Systemsteuerung zum Löschen eines Bereichs nicht zugewiesener Nummern

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Funktionen** und dann auf **Nicht zugewiesene Nummer**.

4.  Geben Sie auf der Seite nicht **zugewiesene Nummer** im Suchfeld den vollständigen oder Teil des Namens des Bereichs nicht zugewiesener Nummern ein, den Sie löschen möchten.

5.  Klicken Sie in der resultierenden Liste der Nummernbereiche auf den Namen, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

6.  Klicken Sie auf **Commit für alle**.

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-an-unassigned-number-range"></a>So verwenden Sie Windows PowerShell zum Löschen eines Bereichs nicht zugewiesener Nummern

1.  Melden Sie sich an dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie in die Befehlszeile Folgendes ein:
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    Beispiel:
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    <div>
    

    > [!NOTE]  
    > Ausführliche Informationen zu weiteren Optionen finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Erstellen oder Ändern eines Bereichs nicht zugewiesener Nummern in lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  


[Remove-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

