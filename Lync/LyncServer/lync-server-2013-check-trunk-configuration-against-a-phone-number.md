---
title: 'Lync Server 2013: Überprüfen der trunkkonfiguration anhand einer Telefonnummer'
description: 'Lync Server 2013: Überprüfen der trunkkonfiguration anhand einer Telefonnummer.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check trunk configuration against a phone number
ms:assetid: 0800d7a3-fc35-482b-a9a4-203d890bfa45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725206(v=OCS.15)
ms:contentKeyID: 63969574
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdfe1a2a9c5c87310ad561464960c5a01fea7b5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543541"
---
# <a name="check-trunk-configuration-against-a-phone-number-in-lync-server-2013"></a><span data-ttu-id="3e961-103">Überprüfen der trunkkonfiguration anhand einer Telefonnummer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e961-103">Check trunk configuration against a phone number in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e961-104">_**Letztes Änderungsstand des Themas:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="3e961-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e961-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="3e961-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="3e961-106">Monatlich</span><span class="sxs-lookup"><span data-stu-id="3e961-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e961-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="3e961-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="3e961-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e961-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e961-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="3e961-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="3e961-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="3e961-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="3e961-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsTrunkConfiguration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="3e961-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsTrunkConfiguration cmdlet.</span></span> <span data-ttu-id="3e961-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="3e961-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTrunkConfiguration&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="3e961-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e961-113">Description</span></span>

<span data-ttu-id="3e961-114">SIP-Trunks verbinden das lync Server interne Enterprise-VoIP-Netzwerk mit einem der folgenden:</span><span class="sxs-lookup"><span data-stu-id="3e961-114">SIP trunks connect the Lync Server internal Enterprise Voice network to any of the following:</span></span>

  - <span data-ttu-id="3e961-115">Das Telefon Festnetz (Public Switched Telephone Network, PSTN).</span><span class="sxs-lookup"><span data-stu-id="3e961-115">The Public Switched Telephone network (PSTN).</span></span>

  - <span data-ttu-id="3e961-116">Eine Nebenstellenanlage (IP-Public Branch Exchange, PBX).</span><span class="sxs-lookup"><span data-stu-id="3e961-116">An IP-public branch exchange (PBX).</span></span>

  - <span data-ttu-id="3e961-117">Einen Session Border Controller (SBC).</span><span class="sxs-lookup"><span data-stu-id="3e961-117">A Session Border Controller (SBC).</span></span>

<span data-ttu-id="3e961-118">Das Test-CsTrunkConfiguration-Cmdlet überprüft, ob eine Telefonnummer (wie von einem Benutzer gewählt) in das E. 164-Netzwerk konvertiert und über einen bestimmten SIP-Trunk weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3e961-118">The Test-CsTrunkConfiguration cmdlet verifies that a phone number (as dialed by a user) can be converted to the E.164 network and routed over a specified SIP trunk.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="3e961-119">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="3e961-119">Running the test</span></span>

<span data-ttu-id="3e961-120">Zum Ausführen des Test-CsTrunkConfiguration-Cmdlets müssen Sie zunächst das Get-CsTrunkConfiguration-Cmdlet verwenden, um eine Instanz Ihrer SIP-Trunk-Konfigurationseinstellungen abzurufen. Diese Instanz wird dann an Test-CsTrunkConfiguration umgeleitet:</span><span class="sxs-lookup"><span data-stu-id="3e961-120">To run the Test-CsTrunkConfiguration cmdlet you must first use the Get-CsTrunkConfiguration cmdlet to retrieve an instance of your SIP trunk configuration settings; that instance is then piped to Test-CsTrunkConfiguration:</span></span>

`Get-CsTrunkConfiguration -Identity "Global" | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="3e961-121">Das Durchführen von Test-CsTrunkConfiguration ohne vorherige Ausführung Get-CsTrunkConfiguration funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="3e961-121">Running Test-CsTrunkConfiguration without first running Get-CsTrunkConfiguration won't work.</span></span> <span data-ttu-id="3e961-122">Beispielsweise schlägt dieser Befehl fehl, ohne dass Daten zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="3e961-122">For example, this command will fail without returning any data:</span></span>

`Test-CsTrunkConfiguration -DialedNumber "12065551219" -TrunkConfiguration "Global"`

<span data-ttu-id="3e961-123">Wenn Sie über mehrere Sammlungen von SIP-Trunk-Konfigurationseinstellungen verfügen, können Sie einen Befehl wie den folgenden verwenden, um gleichzeitig jede Sammlung anhand derselben Telefonnummer zu testen:</span><span class="sxs-lookup"><span data-stu-id="3e961-123">If you have multiple collections of SIP trunk configuration settings, you can use a command similar to the following to at the same time test each collection against the same phone number:</span></span>

`Get-CsTrunkConfiguration | Test-CsTrunkConfiguration -DialedNumber "12065551219"`

<span data-ttu-id="3e961-124">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet Test-CsTrunkConfiguration.</span><span class="sxs-lookup"><span data-stu-id="3e961-124">For more information, see the Help documentation for the Test-CsTrunkConfiguration cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="3e961-125">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="3e961-125">Determining success or failure</span></span>

<span data-ttu-id="3e961-126">Wenn Test-CsTrunkConfiguration einen Anruf an die gewählte Nummer senden können, dann wird die übersetzte Telefonnummer (im E. 164-Format) und die für die Übersetzung dieser Telefonnummer verwendete Regel auf dem Bildschirm angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3e961-126">If Test-CsTrunkConfiguration can place a call to the dialed number then the translated phone number (in the E.164 format) and the rule used to translate that phone number will both be displayed on screen:</span></span>

<span data-ttu-id="3e961-127">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="3e961-127">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="3e961-128">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="3e961-128">\---------------- ------------</span></span>

<span data-ttu-id="3e961-129">\+12065551219 Global/Redmond</span><span class="sxs-lookup"><span data-stu-id="3e961-129">\+12065551219 Global/Redmond</span></span>

<span data-ttu-id="3e961-130">Wenn der Test fehlschlägt, gibt Test-CsTrunkConfiguration leere Eigenschaftswerte zurück:</span><span class="sxs-lookup"><span data-stu-id="3e961-130">If the test fails, Test-CsTrunkConfiguration will return empty property values:</span></span>

<span data-ttu-id="3e961-131">TranslatedNumber MatchingRule</span><span class="sxs-lookup"><span data-stu-id="3e961-131">TranslatedNumber MatchingRule</span></span>

<span data-ttu-id="3e961-132">\---------------- ------------</span><span class="sxs-lookup"><span data-stu-id="3e961-132">\---------------- ------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="3e961-133">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="3e961-133">Reasons why the test might have failed</span></span>

<span data-ttu-id="3e961-134">Wenn Test-CsTrunkConfiguration keine Übereinstimmung zurückgibt, die in der Regel bedeutet, dass die trunkkonfigurationseinstellungen, die getestet werden, keine Übersetzungsregel für ausgehende Rufnummern haben, die die gewählte Nummer in das E. 164-Format konvertieren kann.</span><span class="sxs-lookup"><span data-stu-id="3e961-134">If Test-CsTrunkConfiguration does not return a match that typically means that the trunk configuration settings being test do not have an outgoing calling number translation rule capable to converting the dialed number to the E.164 format.</span></span> <span data-ttu-id="3e961-135">Wenn Sie die Übersetzungsregeln abrufen möchten, die einer Auflistung von trunkkonfigurationseinstellungen zugewiesen sind, können Sie eine ähnliche Syntax wie die folgende verwenden:</span><span class="sxs-lookup"><span data-stu-id="3e961-135">To retrieve the translation rules assigned to a collection of trunk configuration settings, you can use syntax similar to this:</span></span>

`Get-CsTrunkConfiguration -Identity "global" | Select-Object -ExpandProperty OutboundTranslationRulesList`

<span data-ttu-id="3e961-136">Dadurch werden für jede Übersetzungsregel ähnliche Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="3e961-136">That returns information similar to this for each translation rule:</span></span>

<span data-ttu-id="3e961-137">Beschreibung: Telefonnummern ohne Landesvorwahl oder Vorwahl.</span><span class="sxs-lookup"><span data-stu-id="3e961-137">Description : Phone numbers without a country code or area code.</span></span>

<span data-ttu-id="3e961-138">Muster: ^ \\ + ( \\ d \* ) $</span><span class="sxs-lookup"><span data-stu-id="3e961-138">Pattern : ^\\+(\\d\*)$</span></span>

`Translation : $1`

<span data-ttu-id="3e961-139">Name: NoAreaCode</span><span class="sxs-lookup"><span data-stu-id="3e961-139">Name : NoAreaCode</span></span>

<span data-ttu-id="3e961-140">An diesem Punkt überprüfen Sie den Wert der Pattern-Eigenschaft (bei der es sich um eine [reguläre Ausdrucks](https://go.microsoft.com/fwlink/?linkid=400464) Zeichenfolge handelt), um festzustellen, ob eine der Übersetzungsregeln für die Verarbeitung der gewählten Nummer konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="3e961-140">At that point, you check the value of the Pattern property (which is a [regular expression](https://go.microsoft.com/fwlink/?linkid=400464) string) to see whether any of the translation rules are configured to handle the dialed number.</span></span> <span data-ttu-id="3e961-141">Wenn dies nicht der Fall ist, müssen Sie entweder eine der vorhandenen Regeln ändern ("CsOutboundTranslationRule") oder das Cmdlet "New-CsOutboundTranslationRule" verwenden, um der Auflistung eine neue Regel hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="3e961-141">If not, you'll either have to change one of the existing rules (Set-CsOutboundTranslationRule) or use the New-CsOutboundTranslationRule cmdlet to add a new rule to the collection.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3e961-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e961-142">See Also</span></span>


[<span data-ttu-id="3e961-143">Test-CsTrunkConfiguration</span><span class="sxs-lookup"><span data-stu-id="3e961-143">Test-CsTrunkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsTrunkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

