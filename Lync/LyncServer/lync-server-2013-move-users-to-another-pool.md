---
title: 'Lync Server 2013: Benutzer in einen anderen Pool verlegen'
description: 'Lync Server 2013: verschiebt Benutzer in einen anderen Pool.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to another pool
ms:assetid: e7b4968c-0e9d-4d56-b5f1-9edf0f7206f8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182600(v=OCS.15)
ms:contentKeyID: 48185879
ms.date: 02/09/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21012e0df7567a79bca018d194878c85b8653ae4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566391"
---
# <a name="move-users-to-another-pool-in-lync-server-2013"></a>Migrieren von Benutzern in einen anderen Pool in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2018-02-09_

Sie können lync Server-Systemsteuerung verwenden, um Benutzer einem bestimmten Server oder Pool zuzuweisen.

<div>


> [!TIP]  
> Wenn Sie alle vorhandenen Benutzer aus einem Quell Pool verschieben, der lync Server 2010 oder früher in einem lync Server 2013 Ziel Pool in einer komplexen Active Directory Umgebung ausgeführt wird, kann dies zu einer langsameren Active Directory Replikation führen. Um dies zu vermeiden, können Sie Suchfilter verwenden, um Benutzer aus Pools zu migrieren, die lync Server 2010 oder früher separat ausführen, oder Sie können lync Server-Verwaltungsshell verwenden, um Benutzer mit Cmdlets zu verlagern. Außerdem kann die Filterfunktionalität mit lync Server 2013-Benutzern verwendet werden.



</div>

<div>

## <a name="to-move-selected-users-to-a-different-server-or-pool"></a>So migrieren Sie ausgewählte Benutzer zu einem anderen Server oder Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des gewünschten Benutzerkontos ein, und klicken Sie dann auf **Suchen**.

5.  Wählen Sie in der Tabelle einen bestimmten Benutzer oder Benutzer aus der Liste aus.

6.  Klicken Sie im Menü **Aktion** auf **ausgewählte Benutzer in Pool verlagern**.

7.  Wählen Sie unter **Benutzer migrieren**den Pool aus, in den Sie die Benutzer in den **Ziel registrierungsstellenpool**verlagern möchten.

8.  (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.

    
    </div>

</div>

<div>

## <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a>So verschieben Sie alle Benutzer von einem Server oder Pool auf einen anderen Server oder in einen anderen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.

5.  Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.

6.  Wählen Sie unter **Zielregistrierungspool** den Pool aus, in den Sie die Benutzer verschieben möchten.

7.  (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a>So verschieben Sie Benutzer mithilfe eines Filters von einem Pool in einen anderen Pool

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Klicken Sie in der **Benutzersuche**auf **Suchen**, und klicken Sie dann auf **Filter hinzufügen**.

5.  Wählen Sie in den Suchkriterien **Registrierungspool**, **Gleich** und **FQDN des aktuellen Pools** aus, und klicken Sie auf **Suchen**.

6.  Klicken Sie im Menü **Aktion** auf **Alle Benutzer in Pool verschieben**.
    
    <div>
    

    > [!NOTE]  
    > Wenn ein Filter auf eine vorhandene Gruppe von Benutzern angewendet wird, ist die Option <STRONG>alle Benutzer zu Pool verlagern</STRONG> im Kontext der gefilterten Teilmenge von Benutzern, nicht <STRONG><EM>aller</EM></STRONG> möglichen Benutzer.

    
    </div>

7.  Wählen Sie im Abschnitt **Benutzer verschieben** unter **Quellregistrierungspool** den Pool aus, der die zu verschiebenden Benutzerkonten enthält.

8.  Wählen Sie im **Ziel registrierungsstellenpool**den Pool aus, in den Sie die Benutzer migrieren möchten.

9.  (Optional) Falls der Zielserver oder -pool nicht verfügbar ist, aktivieren Sie das Kontrollkästchen **Erzwingen**.
    
    <div>
    

    > [!Caution]  
    > Wenn Sie <STRONG>erzwingen</STRONG>auswählen, wird das Benutzerkonto verschoben, aber zugeordnete Benutzerdaten wie geplante Konferenzen und Kontakte werden nicht verschoben.

    
    </div>

</div>

<div>

## <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a>So migrieren Sie Benutzer mithilfe von Windows PowerShell-Cmdlets von einem Pool in einen anderen

1.  Je nachdem, wie Sie Windows PowerShell-Befehle (lokal oder Remote) ausführen, müssen Sie sich wie folgt als Mitglied der korrekten lync Server 2013 Administratorrolle anmelden:
    
    1.  Wenn Sie die Befehle auf dem lokalen Computer ausführen (beispielsweise melden Sie sich direkt bei einem Front-End-Server an): Melden Sie sich bei dem Computer an, auf dem lync Server-Verwaltungsshell als Mitglied der RTCUniversalServerAdmins-Gruppe oder mit den erforderlichen Benutzerrechten installiert ist, wie unter [Delegieren von Setup Berechtigungen in lync Server 2013](lync-server-2013-delegate-setup-permissions.md)beschrieben.
    
    2.  Wenn Sie die Befehle Remote auf einem anderen Computer ausführen (beispielsweise melden Sie sich an Ihrem Computer an, und führen Sie die Befehle Remote auf einem Standard Edition-Front-End-Server) aus: Melden Sie sich über ein Benutzerkonto, das der CsUserAdministrator-Rolle oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Zum Verschieben einzelner Benutzer verwenden Sie das Move-CsUser-Cmdlet wie folgt:
    
        Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    
    Der Benutzer, der verschoben werden soll, ist der Benutzer Pilar Ackerman, und der Benutzer wird aus dem derzeit zugewiesenen Home-Pool in den Pool pool01.contoso.net

4.  Zum Verschieben einer großen Zahl von Benutzern verwenden Sie das **Get-CsUser**-Cmdlet mit Filtern und übergeben Sie den daraus resultierenden Benutzersatz an **Move-CsUser**:
    
        Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    
    Zusammen können die Befehle **Get-CsUser** und **Move-CsUser** Folgendes ergeben:
    
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

