---
title: Testen von Civic addresses anhand der Master Street Address Guide
description: Testen von Civic addresses anhand des Master Street Address Guides.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16e0d721b70e3db175b2d23ddee6f59d13a13c4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560701"
---
# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a><span data-ttu-id="ffb1f-103">Testen von Civic addresses anhand der Master Street Address Guide in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ffb1f-103">Testing civic addresses against the master street address guide in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffb1f-104">_**Letztes Änderungsstand des Themas:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="ffb1f-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffb1f-105">Überprüfungszeitplan</span><span class="sxs-lookup"><span data-stu-id="ffb1f-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ffb1f-106">Täglich</span><span class="sxs-lookup"><span data-stu-id="ffb1f-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffb1f-107">Test Tool</span><span class="sxs-lookup"><span data-stu-id="ffb1f-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ffb1f-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffb1f-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffb1f-109">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ffb1f-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ffb1f-110">Bei der lokalen Ausführung mit dem lync Server-Verwaltungsshell müssen Benutzer Mitglieder der Sicherheitsgruppe RTCUniversalServerAdmins sein.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ffb1f-111">Bei der Ausführung mit einer Remoteinstanz von Windows PowerShell müssen Benutzern eine RBAC-Rolle zugewiesen werden, die über die Berechtigung zum Ausführen des Test-CsRegistration-Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="ffb1f-112">Um eine Liste aller RBAC-Rollen anzuzeigen, die dieses Cmdlet verwenden können, führen Sie den folgenden Befehl an der Eingabeaufforderung von Windows PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ffb1f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ffb1f-113">Description</span></span>

<span data-ttu-id="ffb1f-114">Mit dem Test-CsLisCivicAddress-Cmdlet werden die Speicherorte überprüft, die ihrer Standortinformationsdienst Datenbank (LIS) hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-114">The Test-CsLisCivicAddress cmdlet is used to verify locations that were added to your Location Information service (LIS) database.</span></span> <span data-ttu-id="ffb1f-115">Das Cmdlet funktioniert durch Vergleichen von Speicherorten mit den in der Master Street Address Guide (MSAG), die zu Ihrem E9-1-1-Netzwerk Routing Anbieter gehört gefunden.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-115">The cmdlet works by comparing locations against the locations found in the Master Street Address Guide (MSAG) that belongs to your E9-1-1 Network Routing Provider.</span></span> <span data-ttu-id="ffb1f-116">Wenn Sie nicht über einen Netzwerkrouting Anbieter verfügen oder der Anbieter nicht erreicht werden kann, treten bei Ihren Tests Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-116">If you do not have a network routing provider or if the provider cannot be reached, then your tests will fail.</span></span>

<span data-ttu-id="ffb1f-117">Wenn Sie den optionalen Switch-Parameter UpdateValidationStatus zu Ihrem Befehl hinzufügen, wird die entsprechende MSAGValid-Datenbankeigenschaft für jede Adresse, die den Test übergibt, auf true festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-117">If you add the optional switch parameter UpdateValidationStatus to your command, then the corresponding MSAGValid database property will be set to True for each address passing the test.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ffb1f-118">Durchführen des Tests</span><span class="sxs-lookup"><span data-stu-id="ffb1f-118">Running the test</span></span>

<span data-ttu-id="ffb1f-119">Das Test-CsLisCivicAddress-Cmdlet kann zum Testen einzelner Adressen oder zum Testen mehrerer Adressen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-119">The Test-CsLisCivicAddress cmdlet can be used to test individual addresses or to test multiple addresses.</span></span> <span data-ttu-id="ffb1f-120">Beispielsweise testet dieser Befehl eine einzelne Adresse, die sich in Redmond, WA befindet:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-120">For example, this command tests a single address located in Redmond, WA:</span></span>

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

<span data-ttu-id="ffb1f-121">Im Vergleich dazu testet dieser Befehl alle Adressen, die sich derzeit in ihrer LIS-Datenbank befinden:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-121">By comparison, this command tests all the addresses currently in your LIS database:</span></span>

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

<span data-ttu-id="ffb1f-122">Weitere Informationen finden Sie in der Hilfedokumentation zum Cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="ffb1f-122">For more information, see the Help documentation for the [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ffb1f-123">Bestimmen des Erfolgs oder Fehlers</span><span class="sxs-lookup"><span data-stu-id="ffb1f-123">Determining success or failure</span></span>

<span data-ttu-id="ffb1f-124">Test-CsLisCivicAddress meldet den Erfolg oder Misserfolg für die angegebenen Adressen zurück.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-124">Test-CsLisCivicAddress will report back Success or Failure for the supplied addresses.</span></span> <span data-ttu-id="ffb1f-125">Ein Adress Test schlägt fehl, wenn die Adresse nicht gefunden wird oder wenn der Dienstanbieter nicht kontaktiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-125">An address test will fail if the address cannot be found or if the service provider cannot be contacted.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ffb1f-126">Gründe, warum der Test fehlgeschlagen ist</span><span class="sxs-lookup"><span data-stu-id="ffb1f-126">Reasons why the test might have failed</span></span>

<span data-ttu-id="ffb1f-127">Im folgenden werden einige häufige Gründe aufgeführt, aus denen Test-CsLisCivicAddress Fehler auftreten können:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-127">Here are some common reasons why Test-CsLisCivicAddress might fail:</span></span>

  - <span data-ttu-id="ffb1f-128">Der LIS-Dienstanbieter ist möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-128">The LIS service provider might not be available.</span></span> <span data-ttu-id="ffb1f-129">Sie können die URL Ihres LIS-Dienstanbieters abrufen, indem Sie das Get-CsLisConfiguration-Cmdlet ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffb1f-129">You can retrieve the URL of your LIS service provider by running the Get-CsLisConfiguration cmdlet:</span></span>
    
        Get-CsLisConfiguration 
    
    <span data-ttu-id="ffb1f-130">Anschließend können Sie eine Ping-URL durchführen, um zu überprüfen, ob der Dienstanbieter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ffb1f-130">You can then ping that URL to verify that the service provider is available.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

