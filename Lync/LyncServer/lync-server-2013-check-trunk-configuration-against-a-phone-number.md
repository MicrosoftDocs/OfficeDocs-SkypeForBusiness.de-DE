---
title: 'Lync Server 2013: Überprüfen der trunk-Konfiguration für eine Telefonnummer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b667f43e430b5047f72e2d8352f57337f0849055
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="ca756-102">Überprüfen der trunk-Konfiguration für eine Telefonnummer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca756-102">Check trunk configuration against a phone number in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca756-103">_**Letztes Änderungsdatum des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="ca756-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca756-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="ca756-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ca756-105">Monatlich</span><span class="sxs-lookup"><span data-stu-id="ca756-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca756-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="ca756-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ca756-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca756-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca756-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ca756-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ca756-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="ca756-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ca756-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsTrunkConfiguration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="ca756-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="ca756-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="ca756-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ca756-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca756-112">Description</span></span>

<span data-ttu-id="ca756-113">SIP-Trunks verbinden das interne lync Server Enterprise-VoIP-Netzwerk mit einer der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="ca756-113">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="ca756-114">Das öffentlich geschaltete Telefonnetz (PSTN).</span><span class="sxs-lookup"><span data-stu-id="ca756-114">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="ca756-115">Eine IP-Public Branch Exchange (PBX).</span><span class="sxs-lookup"><span data-stu-id="ca756-115">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="ca756-116">Ein Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="ca756-116">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="ca756-117">Das Cmdlet Test-CsTrunkConfiguration überprüft, ob eine Telefonnummer (wie von einem Benutzer gewählt) in das E. 164-Netzwerk konvertiert und über einen angegebenen SIP-Stamm weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ca756-117">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ca756-118">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="ca756-118">Running the test</span></span>

<span data-ttu-id="ca756-119">Zum Ausführen des Cmdlets "Test-CsTrunkConfiguration" müssen Sie zuerst das Cmdlet "Get-CsTrunkConfiguration" verwenden, um eine Instanz Ihrer SIP-Trunk-Konfigurationseinstellungen abzurufen. Diese Instanz wird dann an Test-CsTrunkConfiguration umgeleitet:</span><span class="sxs-lookup"><span data-stu-id="ca756-119">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="ca756-120">Das Ausführen von Test-CsTrunkConfiguration ohne erste Ausführung von Get-CsTrunkConfiguration funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="ca756-120">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="ca756-121">Dieser Befehl schlägt beispielsweise fehl, ohne dass Daten zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="ca756-121">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="ca756-122">Wenn Sie über mehrere Sammlungen von SIP Trunk-Konfigurationseinstellungen verfügen, können Sie einen Befehl wie den folgenden verwenden, um gleichzeitig jede Sammlung mit derselben Telefonnummer zu testen:</span><span class="sxs-lookup"><span data-stu-id="ca756-122">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="ca756-123">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ca756-123">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ca756-124">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="ca756-124">Determining success or failure</span></span>

<span data-ttu-id="ca756-125">Wenn Test-CsTrunkConfiguration die gewählte Nummer anrufen kann, wird die übersetzte Telefonnummer (im E. 164-Format) und die für die Übersetzung dieser Rufnummer verwendete Regel auf dem Bildschirm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="ca756-125">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="ca756-126">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="ca756-126">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="ca756-127">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="ca756-127"></span></span>

<span data-ttu-id="ca756-128">\+12065551219 Global/Redmond</span><span class="sxs-lookup"><span data-stu-id="ca756-128">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="ca756-129">Wenn der Test fehlschlägt, gibt Test-CsTrunkConfiguration leere Eigenschaftswerte zurück:</span><span class="sxs-lookup"><span data-stu-id="ca756-129">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="ca756-130">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="ca756-130">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="ca756-131">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="ca756-131"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ca756-132">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="ca756-132">Reasons why the test might have failed</span></span>

<span data-ttu-id="ca756-133">Wenn Test-CsTrunkConfiguration keine Übereinstimmung zurückgibt, die in der Regel bedeutet, dass die zu testenden trunk-Konfigurationseinstellungen keine Übersetzungen für ausgehende Rufnummern enthalten, die die gewählte Nummer in das E. 164-Format konvertieren können.</span><span class="sxs-lookup"><span data-stu-id="ca756-133">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="ca756-134">Um die Übersetzungsregeln abzurufen, die einer Sammlung von trunk-Konfigurationseinstellungen zugewiesen wurden, können Sie eine Syntax verwenden, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="ca756-134">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="ca756-135">Damit werden für jede Übersetzungsregel ähnliche Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="ca756-135">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="ca756-136">Beschreibung: Telefonnummern ohne Landesvorwahl oder Ortsvorwahl.</span><span class="sxs-lookup"><span data-stu-id="ca756-136">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="ca756-137">Muster: ^\\+ (\\d\*) $</span><span class="sxs-lookup"><span data-stu-id="ca756-137">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="ca756-138">Name: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="ca756-138">Name : NoAreaCode</span></span>

<span data-ttu-id="ca756-139">An diesem Punkt überprüfen Sie den Wert der Pattern-Eigenschaft (die eine [reguläre Ausdrucks](http://go.microsoft.com/fwlink/?linkid=400464) Zeichenfolge ist), um festzustellen, ob eine der Übersetzungsregeln für die Behandlung der gewählten Nummer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="ca756-139">At that point, you check the value of the Pattern property (which is a [regular expression](http://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="ca756-140">Wenn dies nicht der Fall ist, müssen Sie entweder eine der vorhandenen Regeln ("CsOutboundTranslationRule") ändern oder das Cmdlet "New-CsOutboundTranslationRule" verwenden, um der Sammlung eine neue Regel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="ca756-140">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca756-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca756-141">See Also</span></span>


[<span data-ttu-id="ca756-142">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="ca756-142">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

