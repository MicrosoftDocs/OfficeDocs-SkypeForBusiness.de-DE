---
title: 'Lync Server 2013: Überprüfen der Mobilitätsbereitstellung'
description: 'Lync Server 2013: Überprüfen der Mobilitätsbereitstellung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying your mobility deployment
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690024(v=OCS.15)
ms:contentKeyID: 48184477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eadda35438961e469fdd5fa7976762141b26a385
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564441"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a>Überprüfen der Mobilitätsbereitstellung in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Nachdem Sie den lync Server Mobilitätsdienst und lync Server AutoErmittlungsdienst bereitgestellt haben, führen Sie eine Testtransaktion aus, um zu überprüfen, ob die Bereitstellung ordnungsgemäß funktioniert. Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit von zwei Benutzern zu testen, die lync 2013 Mobile Clients verwenden, um eine Konferenz zu erstellen, zu verbinden und zu kommunizieren. Um diese Testtransaktion verwenden zu können, benötigen Sie zwei tatsächliche Benutzer oder Testbenutzer und die vollständigen Anmeldeinformationen.

Verwenden Sie **Test-CsMcxP2PIM** , um das Senden einer Sofortnachricht zwischen zwei Benutzern zu testen, die lync 2010 Mobile verwenden. Ähnlich wie bei **Test-CsUcwaConference**verwenden Sie zwei tatsächliche Benutzer oder zwei vordefinierte Testbenutzer.

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a>So testen Sie Konferenzen für lync 2013 Mobile Clients

1.  Melden Sie sich als Mitglied der CsAdministrator-Rolle auf einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    Sie können die Anmeldeinformationen in einem Skript festlegen und diese dann an das Test-Cmdlet übergeben. Beispiel:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a>So testen Sie Chatnachrichten für Personen mit lync 2010 Mobile

1.  Melden Sie sich als Mitglied der CsAdministrator-Rolle auf einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore installiert sind.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    Sie können die Anmeldeinformationen in einem Skript festlegen und diese dann an das Test-Cmdlet übergeben. Beispiel:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

