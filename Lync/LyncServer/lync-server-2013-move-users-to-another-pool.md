---
title: 'Lync Server 2013: Verschieben von Benutzern in einen anderen Pool'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb716c0b551475a53cacf09be10ffdc039f5db8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Verschieben von Benutzern in einen anderen Pool in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2018-02-09_

Sie können die lync Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuweisen.

<div>


> [!TIP]  
> Das Verschieben aller vorhandenen Benutzer aus einem Quell Pool, auf dem lync Server 2010 oder früher ausgeführt wird, in einen lync Server 2013-Ziel Pool in einer komplexen Active Directory-Umgebung kann zu einer langsameren Active Directory-Replikation führen. Um dies zu vermeiden, können Sie mithilfe von Suchfiltern Benutzer aus Pools verschieben, auf denen lync Server 2010 oder früher separat ausgeführt wird, oder Sie können die lync Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verschieben. Darüber hinaus kann die Filterfunktionalität mit lync Server 2013-Benutzern verwendet werden.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>So verschieben Sie ausgewählte Benutzer auf einen anderen Server oder Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** den gesamten oder den ersten Teil des Anzeigenamens, des Vornamens, des Nachnamens, des SAM-Kontos (Security Accounts Manager), der SIP-Adresse oder des Uniform Resource Identifier (URI) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **suchen. **.

5.  Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer in der Liste aus.

6.  Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verschieben**.

7.  Wählen Sie in **Benutzer verschieben**den Pool aus, in den Sie die Benutzer in den **Ziel Registrierungspool**verschieben möchten.

8.  Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.

5.  Wählen Sie in **Benutzer verschieben**den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool**verschieben möchten.

6.  Wählen Sie im **Ziel Registrierungspool**den Pool aus, in den Sie die Benutzer verschieben möchten.

7.  Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>So verschieben Sie Benutzer mithilfe eines Filters aus einem Pool in einen anderen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie in der **Benutzersuche**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.

5.  Wählen Sie in den Suchkriterien den Eintrag **Registrierungspool**aus, wählen Sie **gleich**aus, wählen Sie **Aktueller Pool-FQDN**aus, und klicken Sie dann auf **Suchen**.

6.  Klicken Sie im Menü **Aktion** auf **alle Benutzer in Pool verschieben**.
    
    <div>
    

    > [!NOTE]  
    > Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, befindet sich die Option <STRONG>alle Benutzer in Pool verschieben</STRONG> im Kontext der gefilterten Teilmenge von Benutzern, nicht <STRONG><EM>aller</EM></STRONG> möglichen Benutzer.

    
    </div>

7.  Wählen Sie in **Benutzer verschieben**den Pool aus, der die Benutzerkonten enthält, die Sie im **Quell Registrierungspool**verschieben möchten.

8.  Wählen Sie im **Ziel Registrierungspool**den Pool aus, in den Sie die Benutzer verschieben möchten.

9.  Optional Aktivieren Sie das Kontrollkästchen **erzwingen** , wenn der Zielserver oder-Pool nicht verfügbar ist.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>So verschieben Sie Benutzer mithilfe von Windows PowerShell-Cmdlets aus einem Pool in einen anderen

1.  Je nachdem, wie Sie Windows PowerShell-Befehle ausführen (lokal oder Remote), müssen Sie sich wie folgt als Mitglied der richtigen lync Server 2013-Administratorrollen anmelden:
    
    1.  Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem die lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe installiert ist, oder mit den erforderlichen Benutzerrechten als unter Delegieren von [Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.
    
    2.  Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich bei Ihrem Computer an, und führen Sie die Befehle Remote auf einem Standard Edition-Front-End-Server aus): von einem Benutzerkonto, das der CsUserAdministrator-Rolle oder dem CsAdministrator zugewiesen ist. Rolle, melden Sie sich bei einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Verwenden Sie zum Verschieben einzelner Benutzer das Cmdlet Move-CsUser wie folgt:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Der Benutzer, der verschoben werden soll, ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem aktuell zugewiesenen privaten Pool in den Pool pool01.contoso.net

4.  Wenn Sie eine große Anzahl von Benutzern verschieben möchten, verwenden Sie Filter mit dem Cmdlet **Get-CsUser** , und übergeben Sie die resultierenden Benutzersätze an **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Die kombinierten Befehle von **Get-CsUser** und **Move-CsUser** können dazu führen:
    
        Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Ändern von Benutzerkontoeigenschaften in lync Server 2013](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

