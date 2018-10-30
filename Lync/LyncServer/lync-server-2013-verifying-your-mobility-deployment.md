---
title: 'Lync Server 2013: Überprüfen der Mobilitätsbereitstellung'
TOCTitle: Überprüfen der Mobilitätsbereitstellung
ms:assetid: 72f9b4d3-57b0-4705-9480-cfdca313a70c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690024(v=OCS.15)
ms:contentKeyID: 49294392
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Mobilitätsbereitstellung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-12_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Führen Sie nach der Bereitstellung des Lync Server-Mobilitätsdiensts und des Lync Server-AutoErmittlungsdiensts eine Testtransaktion aus, um sicherzustellen, dass die Bereitstellung ordungsgemäß funktioniert. Sie können **Test-CsUcwaConference** ausführen, um zu testen, ob zwei Benutzer, die Lync 2013 Mobile-Clients verwenden, eine Konferenz erstellen, daran teilnehmen und darin kommunizieren können. Zum Verwenden dieser Testtransaktion benötigen Sie zwei tatsächliche Benutzer oder Testbenutzer und deren vollständige Anmeldeinformationen.

Sie verwenden **Test-CsMcxP2PIM**, um das Senden einer Chatnachricht zwischen zwei Benutzern zu testen, die Lync 2010 Mobile verwenden. Ähnlich wie bei **Test-CsUcwaConference** verwenden Sie dabei zwei tatsächliche Benutzer oder zwei vordefinierte Testbenutzer.

## So testen Sie Konferenzen für Lync 2013 Mobile-Clients

1.  Melden Sie sich als Benutzer mit der Rolle "CsAdministrator" an einem Computer an, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    Sie können die Anmeldeinformationen in einem Skript festlegen und diese dann an das Test-Cmdlet übergeben. Beispiel:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

## So testen Sie Chatnachrichten von Person zu Person für Lync 2010 Mobile

1.  Melden Sie sich als Benutzer mit der Rolle "CsAdministrator" an einem Computer an, auf dem Lync Server-Verwaltungsshell und Ocscore installiert sind.

2.  Starten der Lync Server-Verwaltungsshell: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

3.  Geben Sie an der Befehlszeile Folgendes ein:
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    Sie können die Anmeldeinformationen in einem Skript festlegen und diese dann an das Test-Cmdlet übergeben. Beispiel:
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

## Siehe auch

#### Weitere Ressourcen

[Test-CsMcxP2PIM](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxP2PIM)  
[Test-CsUcwaConference](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUcwaConference)

