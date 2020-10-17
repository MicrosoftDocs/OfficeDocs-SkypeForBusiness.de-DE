---
title: 'Lync Server 2013: Überprüfen der Mobilitätsbereitstellung'
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
ms.openlocfilehash: 8fefcdaf1fc84151fd37d7ff29acf66d742425d7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527608"
---
# <a name="verifying-your-mobility-deployment-in-lync-server-2013"></a><span data-ttu-id="6c38e-102">Überprüfen der Mobilitätsbereitstellung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c38e-102">Verifying your mobility deployment in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c38e-103">_**Letztes Änderungsstand des Themas:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="6c38e-103">_**Topic Last Modified:** 2013-02-12_</span></span>

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="6c38e-104">Nachdem Sie den lync Server Mobilitätsdienst und lync Server AutoErmittlungsdienst bereitgestellt haben, führen Sie eine Testtransaktion aus, um zu überprüfen, ob die Bereitstellung ordnungsgemäß funktioniert.</span><span class="sxs-lookup"><span data-stu-id="6c38e-104">After you deploy the Lync Server Mobility Service and Lync Server Autodiscover Service, run a test transaction to verify that your deployment works correctly.</span></span> <span data-ttu-id="6c38e-105">Sie können **Test-CsUcwaConference** ausführen, um die Fähigkeit von zwei Benutzern zu testen, die lync 2013 Mobile Clients verwenden, um eine Konferenz zu erstellen, zu verbinden und zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="6c38e-105">You can run **Test-CsUcwaConference** to test the ability of two users who are using Lync 2013 Mobile clients to create, join and communicate in a conference.</span></span> <span data-ttu-id="6c38e-106">Um diese Testtransaktion verwenden zu können, benötigen Sie zwei tatsächliche Benutzer oder Testbenutzer und die vollständigen Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="6c38e-106">To use this test transaction, you need two actual users or test users, and their full credentials.</span></span>

<span data-ttu-id="6c38e-107">Verwenden Sie **Test-CsMcxP2PIM** , um das Senden einer Sofortnachricht zwischen zwei Benutzern zu testen, die lync 2010 Mobile verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c38e-107">You use **Test-CsMcxP2PIM** to test sending an instant message between two users who are using Lync 2010 Mobile.</span></span> <span data-ttu-id="6c38e-108">Ähnlich wie bei **Test-CsUcwaConference**verwenden Sie zwei tatsächliche Benutzer oder zwei vordefinierte Testbenutzer.</span><span class="sxs-lookup"><span data-stu-id="6c38e-108">Similar to **Test-CsUcwaConference**, you use two actual users or two predefined test users.</span></span>

<div>

## <a name="to-test-conferencing-for-lync-2013-mobile-clients"></a><span data-ttu-id="6c38e-109">So testen Sie Konferenzen für lync 2013 Mobile Clients</span><span class="sxs-lookup"><span data-stu-id="6c38e-109">To test conferencing for Lync 2013 Mobile clients</span></span>

1.  <span data-ttu-id="6c38e-110">Melden Sie sich als Mitglied der CsAdministrator-Rolle auf einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c38e-110">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="6c38e-111">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6c38e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6c38e-112">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6c38e-112">At the command line, type:</span></span>
    
        Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
    
    <span data-ttu-id="6c38e-p103">Sie können die Anmeldeinformationen in einem Skript festlegen und diese dann an das Test-Cmdlet übergeben. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6c38e-p103">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v

</div>

<div>

## <a name="to-test-person-to-person-instant-messaging-im-for-lync-2010-mobile"></a><span data-ttu-id="6c38e-115">So testen Sie Chatnachrichten für Personen mit lync 2010 Mobile</span><span class="sxs-lookup"><span data-stu-id="6c38e-115">To test person-to-person instant messaging (IM) for Lync 2010 Mobile</span></span>

1.  <span data-ttu-id="6c38e-116">Melden Sie sich als Mitglied der CsAdministrator-Rolle auf einem beliebigen Computer an, auf dem lync Server-Verwaltungsshell und OCSCore installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6c38e-116">Log on as a member of the CsAdministrator role on any computer where Lync Server Management Shell and Ocscore are installed.</span></span>

2.  <span data-ttu-id="6c38e-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="6c38e-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="6c38e-118">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6c38e-118">At the command line, type:</span></span>
    
        Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
    
    <span data-ttu-id="6c38e-p104">Sie können die Anmeldeinformationen in einem Skript festlegen und diese dann an das Test-Cmdlet übergeben. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6c38e-p104">You can set credentials in a script and pass them to the test cmdlet. For example:</span></span>
    
        $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
        $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
        $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
        $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
        Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c38e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c38e-121">See Also</span></span>


[<span data-ttu-id="6c38e-122">Test-CsMcxP2PIM</span><span class="sxs-lookup"><span data-stu-id="6c38e-122">Test-CsMcxP2PIM</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM)  
[<span data-ttu-id="6c38e-123">Test-CsUcwaConference</span><span class="sxs-lookup"><span data-stu-id="6c38e-123">Test-CsUcwaConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

