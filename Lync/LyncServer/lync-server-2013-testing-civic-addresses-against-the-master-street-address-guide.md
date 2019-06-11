---
title: Testen von Civic addresses mit dem Master Street Address Guide
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa4dd28ec05546366e029b6fb9fdf1c4b3ae310
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="8da05-102">Testen von bürgerlichen Adressen mit dem Leitfaden zur Master Street-Adresse in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8da05-102">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8da05-103">_**Letztes Änderungsdatum des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8da05-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8da05-104">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="8da05-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8da05-105">Täglich</span><span class="sxs-lookup"><span data-stu-id="8da05-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8da05-106">Test Tool</span><span class="sxs-lookup"><span data-stu-id="8da05-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8da05-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8da05-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8da05-108">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8da05-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8da05-109">Wenn Benutzer lokal mit der lync Server-Verwaltungsshell ausgeführt werden, müssen Sie Mitglied der RTCUniversalServerAdmins-Sicherheitsgruppe sein.</span><span class="sxs-lookup"><span data-stu-id="8da05-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8da05-110">Beim Ausführen mithilfe einer Remoteinstanz von Windows PowerShell muss Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsRegistration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="8da05-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="8da05-111">Führen Sie den folgenden Befehl in der Windows PowerShell-Eingabeaufforderung aus, um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können:</span><span class="sxs-lookup"><span data-stu-id="8da05-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8da05-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8da05-112">Description</span></span>

<span data-ttu-id="8da05-113">Das Cmdlet Test-CsLisCivicAddress wird verwendet, um die Speicherorte zu überprüfen, die Ihrer Datenbank für den standortinformationsdienst (LIS) hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="8da05-113">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="8da05-114">Das Cmdlet vergleicht Speicherorte mit den Speicherorten im Master Street Address Guide (MSAG), die zu Ihrem E9-1-1-Netzwerk Routing Anbieter gehören.</span><span class="sxs-lookup"><span data-stu-id="8da05-114">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="8da05-115">Wenn Sie nicht über einen Netzwerkrouting Anbieter verfügen oder der Anbieter nicht erreicht werden kann, treten bei den Tests Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="8da05-115">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="8da05-116">Wenn Sie den optionalen Schalterparameter UpdateValidationStatus zu Ihrem Befehl hinzufügen, wird die entsprechende MSAGValid-Datenbankeigenschaft für jede Adresse, die den Test übergibt, auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8da05-116">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8da05-117">Ausführen des Tests</span><span class="sxs-lookup"><span data-stu-id="8da05-117">Running the test</span></span>

<span data-ttu-id="8da05-118">Das Cmdlet Test-CsLisCivicAddress kann verwendet werden, um einzelne Adressen zu testen oder mehrere Adressen zu testen.</span><span class="sxs-lookup"><span data-stu-id="8da05-118">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="8da05-119">Dieser Befehl testet beispielsweise eine einzelne Adresse, die sich in Redmond, WA befindet:</span><span class="sxs-lookup"><span data-stu-id="8da05-119">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="8da05-120">Im Vergleich dazu testet dieser Befehl alle Adressen, die sich derzeit in ihrer LIS-Datenbank befinden:</span><span class="sxs-lookup"><span data-stu-id="8da05-120">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="8da05-121">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="8da05-121">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8da05-122">Ermitteln von Erfolg oder Misserfolg</span><span class="sxs-lookup"><span data-stu-id="8da05-122">Determining success or failure</span></span>

<span data-ttu-id="8da05-123">Test-CsLisCivicAddress meldet den Erfolg oder Misserfolg der angegebenen Adressen zurück.</span><span class="sxs-lookup"><span data-stu-id="8da05-123">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="8da05-124">Bei einem Adress Test tritt ein Fehler auf, wenn die Adresse nicht gefunden werden kann oder wenn der Dienstanbieter nicht kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8da05-124">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8da05-125">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="8da05-125">Reasons why the test might have failed</span></span>

<span data-ttu-id="8da05-126">Nachfolgend finden Sie einige häufige Gründe, warum Test-CsLisCivicAddress möglicherweise fehlschlägt:</span><span class="sxs-lookup"><span data-stu-id="8da05-126">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="8da05-127">Der LIS-Dienstanbieter steht möglicherweise nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="8da05-127">The LIS service provider might not be available.</span></span> <span data-ttu-id="8da05-128">Sie können die URL Ihres LIS-Dienstanbieters abrufen, indem Sie das Cmdlet "Get-CsLisConfiguration" ausführen:</span><span class="sxs-lookup"><span data-stu-id="8da05-128">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="8da05-129">Anschließend können Sie die URL anpingen, um zu überprüfen, ob der Dienstanbieter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="8da05-129">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

