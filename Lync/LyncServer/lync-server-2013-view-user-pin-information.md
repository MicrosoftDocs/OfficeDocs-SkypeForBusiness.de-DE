---
title: 'Lync Server 2013: Anzeigen von Benutzer-PIN-Informationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View user PIN information
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49733661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18f2e9a8c5013a17a35a6f13cf67d9924a9fed78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-user-pin-information-in-lync-server-2013"></a>Anzeigen von Benutzer-PIN-Informationen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Um an einer Einwahlkonferenz als authentifizierter Benutzer teilzunehmen, benötigt ein lync Server 2013 Benutzer mit Active Directory-Domänendienste (AD DS) Anmeldeinformationen eine persönliche Identifikationsnummer (PIN). Sie können die PIN-Informationen eines Benutzers in lync Server 2013 Systemsteuerung anzeigen.

<div>


> [!NOTE]  
> Sie können Informationen zum Pin-Status anzeigen, beispielsweise, ob die PIN festgelegt wurde oder wann die PIN zuletzt geändert wurde, aber Sie können die aktuelle PIN nicht sehen, indem Sie den PIN-Status betrachten. Wenn ein Benutzer seine PIN verloren hat, können Sie ihn zurücksetzen, indem Sie die Verfahren unter <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Festlegen der Einwahlkonferenz-PIN eines Benutzers in lync Server 2013</A>



</div>

<div>

## <a name="to-view-a-users-pin-in-lync-server-control-panel"></a>So zeigen Sie die PIN eines Benutzers in lync Server-Systemsteuerung an

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Benutzer**.

4.  Verwenden Sie eine der folgenden Methoden, um nach einem Benutzer zu suchen:
    
      - Geben Sie im Feld **Benutzer suchen** einen Teil oder den vollständigen Anzeigenamen, Vornamen, Nachnamen, SAM-Kontonamen (Security Accounts Manager), die SIP-Adresse oder den Anschluss-URI (Uniform Resource Identifier) des Benutzerkontos ein, und klicken Sie dann auf **Suchen**.
    
      - Wenn Sie über eine gespeicherte Abfrage verfügen, klicken Sie auf das Symbol **Abfrage öffnen**, verwenden Sie das Dialogfeld **Öffnen**, um die Abfrage abzurufen (eine USF-Datei), und klicken Sie dann auf **Suchen**.

5.  (Optional) Geben Sie zusätzliche Suchkriterien ein, um die Ergebnisse zu beschränken:
    
    1.  Klicken Sie auf **Filter hinzufügen**.
    
    2.  Geben Sie die Benutzereigenschaft ein, indem Sie sie eingeben oder auf den Pfeil in der Dropdownliste klicken, um die Eigenschaft auszuwählen.
    
    3.  Klicken Sie in der Dropdownliste **Gleich** auf den Operator (beispielsweise **Gleich** oder **Ungleich**).
    
    4.  Geben Sie je nach ausgewählter Benutzereigenschaft entweder das Kriterium für die Filterung der Suchergebnisse ein, oder klicken Sie auf den Pfeil in der Dropdownliste.
        
        <div>
        

        > [!TIP]  
        > Klicken Sie auf <STRONG>Filter hinzufügen</STRONG>, um zusätzliche Suchklauseln einzugeben.

        
        </div>
    
    5.  Klicken Sie auf **Suchen**.
    
    <div>
    

    > [!NOTE]  
    > Ist die PIN gesperrt, müssen Sie die Sperre zunächst aufheben, bevor Sie die PIN festlegen können. Klicken Sie zum Aufheben der Sperre auf den Benutzer, dann auf <STRONG>Aktion</STRONG> und auf <STRONG>PIN entsperren</STRONG>.

    
    </div>

6.  Klicken Sie auf einen Benutzer in den Suchergebnissen und dann auf **Aktion** und auf **PIN-Status anzeigen**.

</div>

<div>

## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Anzeigen von Benutzer-PIN-Informationen mithilfe von Windows PowerShell-Cmdlets

Sie können die PIN-Informationen für Benutzer mit dem Get-CsClientPinInfo-Cmdlet anzeigen. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-view-user-pin-information"></a>So zeigen Sie die PIN-Informationen von Benutzern an

  - Um PIN-Informationen für einen Benutzer anzuzeigen, geben Sie einen Befehl wie den folgenden in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/Get-CsConferenceDisclaimer) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Festlegen der Einwahlkonferenz-PIN eines Benutzers in lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Sperren oder Entsperren einer Benutzer-PIN in lync Server 2013](lync-server-2013-lock-or-unlock-a-user-pin.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

