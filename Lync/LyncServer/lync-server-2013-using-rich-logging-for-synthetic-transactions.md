---
title: 'Lync Server 2013: Verwenden der umfangreichen Protokollierung für synthetische Transaktionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using rich logging for synthetic transactions
ms:assetid: 32714a71-9f42-4d5b-a508-e176d8f08bbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204798(v=OCS.15)
ms:contentKeyID: 48183812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc43a38a1c6060827755c958ac071fa63608556f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-rich-logging-for-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="eccc4-102">Verwenden der umfangreichen Protokollierung für synthetische Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eccc4-102">Using rich logging for synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eccc4-103">_**Letztes Änderungsstand des Themas:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="eccc4-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="eccc4-104">Synthetische Transaktionen (in Microsoft lync Server 2010 eingeführt) bieten Administratoren die Möglichkeit zu überprüfen, ob Benutzer in der Lage sind, allgemeine Aufgaben wie das Anmelden am System, das Austauschen von Chatnachrichten oder das tätigen von Anrufen an ein Telefon erfolgreich abzuschließen. im Festnetz (Public Switched Telephone Network, PSTN).</span><span class="sxs-lookup"><span data-stu-id="eccc4-104">Synthetic transactions (introduced in Microsoft Lync Server 2010) provide a way for administrators to verify that users are able to successfully complete common tasks such as logging on to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="eccc4-105">Diese Tests (die als eine Gruppe von lync Server Windows PowerShell-Cmdlets verpackt sind) können manuell von einem Administrator ausgeführt werden, oder Sie können von einer Anwendung wie System Center Operations Manager automatisch durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eccc4-105">These tests (which are packaged as a set of Lync Server Windows PowerShell cmdlets) can be conducted manually by an administrator, or they can be automatically run by an application such as System Center Operations Manager.</span></span>

<span data-ttu-id="eccc4-106">In lync Server 2010 erwiesen sich synthetische Transaktionen als äußerst hilfreich bei der Unterstützung von Administratoren bei der Identifizierung von Problemen mit dem System.</span><span class="sxs-lookup"><span data-stu-id="eccc4-106">In Lync Server 2010, synthetic transactions proved extremely useful in helping administrators to identify problems with the system.</span></span> <span data-ttu-id="eccc4-107">Beispielsweise könnte das **Test-CsRegistration-** Cmdlet Administratoren darauf hinweisen, dass sich einige Benutzer bei der Registrierung bei lync Server Schwierigkeiten hatten.</span><span class="sxs-lookup"><span data-stu-id="eccc4-107">For example, the **Test-CsRegistration** cmdlet could alert administrators to the fact that some users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="eccc4-108">Die synthetischen Transaktionen waren jedoch etwas weniger hilfreich, um Administratoren bei der Entscheidung zu unterstützen, warum sich diese Benutzer bei der Registrierung bei lync Server Schwierigkeiten hatten.</span><span class="sxs-lookup"><span data-stu-id="eccc4-108">However, the synthetic transactions were somewhat less useful in helping administrators determine why these users were having difficulty registering with Lync Server.</span></span> <span data-ttu-id="eccc4-109">Dies liegt daran, dass die synthetischen Transaktionen keine detaillierten Protokollierungsinformationen bereitgestellt haben, die Administratoren bei der Behandlung von Problemen mit lync Server unterstützen könnten.</span><span class="sxs-lookup"><span data-stu-id="eccc4-109">This was due to the fact that the synthetic transactions did not provide detailed logging information that could help administrators troubleshoot problems with Lync Server.</span></span> <span data-ttu-id="eccc4-110">Bestenfalls enthielt die ausführliche Ausgabe einer synthetischen Transaktion Schritt-für-Schritt-Informationen, anhand derer ein Administrator aufgrund seiner Erfahrung Vermutungen darüber anstellen konnte, wo wahrscheinlich ein Problem aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="eccc4-110">At best, the verbose output from a synthetic transaction provided step-by-step information that might enable an administrator to make an educated guess as to where a problem likely occurred.</span></span>

<span data-ttu-id="eccc4-111">In Microsoft lync Server 2013 wurden synthetische Transaktionen neu entworfen, um eine umfangreiche Protokollierung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="eccc4-111">In Microsoft Lync Server 2013, synthetic transactions have been re-architected to provide rich logging.</span></span> <span data-ttu-id="eccc4-112">"Umfassende Protokollierung" bedeutet, dass für jede Aktivität, die eine synthetische Transaktion unternimmt, Informationen wie die folgenden aufgezeichnet werden:</span><span class="sxs-lookup"><span data-stu-id="eccc4-112">"Rich logging" means that, for each activity that a synthetic transaction undertakes, information such as this will be recorded:</span></span>

  - <span data-ttu-id="eccc4-113">Die Uhrzeit, zu der die Aktivität begann</span><span class="sxs-lookup"><span data-stu-id="eccc4-113">The time that the activity started</span></span>

  - <span data-ttu-id="eccc4-114">Die Uhrzeit, zu der die Aktivität endetet</span><span class="sxs-lookup"><span data-stu-id="eccc4-114">The time that the activity finished</span></span>

  - <span data-ttu-id="eccc4-115">Die Aktion, die ausgeführt wurde (beispielsweise erstellen, hinzufügen oder verlassen einer Konferenz; Anmelden bei lync Server; senden einer Sofortnachricht; usw.)</span><span class="sxs-lookup"><span data-stu-id="eccc4-115">The action that was performed (for example, creating, joining, or leaving a conference; signing on to Lync Server; sending an instant message; and so on)</span></span>

  - <span data-ttu-id="eccc4-116">Informative oder ausführliche Meldungen bzw. Warn- oder Fehlermeldungen, die beim Ausführen der Aktivität generiert wurden</span><span class="sxs-lookup"><span data-stu-id="eccc4-116">Informational, verbose, warning, or error messages generated when the activity ran</span></span>

  - <span data-ttu-id="eccc4-117">Meldungen zur SIP-Registrierung</span><span class="sxs-lookup"><span data-stu-id="eccc4-117">SIP registration messages</span></span>

  - <span data-ttu-id="eccc4-118">Ausnahmedatensätze oder Diagnosecodes, die beim Ausführen der Aktivität generiert wurden</span><span class="sxs-lookup"><span data-stu-id="eccc4-118">Exception records or diagnostic codes generated when the activity ran</span></span>

  - <span data-ttu-id="eccc4-119">Das Resultat der Aktivitätsausführung</span><span class="sxs-lookup"><span data-stu-id="eccc4-119">The net result of running the activity</span></span>

<span data-ttu-id="eccc4-120">Diese Informationen werden jedes Mal automatisch generiert, wenn eine synthetische Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eccc4-120">This information is automatically generated each time a synthetic transaction is run.</span></span> <span data-ttu-id="eccc4-121">Die Informationen werden jedoch nicht automatisch in einer Protokolldatei angezeigt oder gespeichert.</span><span class="sxs-lookup"><span data-stu-id="eccc4-121">However, the information is not automatically displayed or saved to a log file.</span></span> <span data-ttu-id="eccc4-122">Stattdessen können Administratoren, die eine synthetische Transaktion manuell durchführen, den Parameter OutLoggerVariable verwenden, um eine Windows PowerShell Variable anzugeben, in der die Informationen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="eccc4-122">Instead, administrators who are manually running a synthetic transaction can use the OutLoggerVariable parameter to specify a Windows PowerShell variable in which the information will be stored.</span></span> <span data-ttu-id="eccc4-123">Von dort aus können Administratoren dann ein paar Methoden verwenden, mit denen Sie das umfangreiche Protokoll im XML-oder HTML-Format speichern und/oder anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="eccc4-123">From there, administrators can then use a pair of methods that enable them to save and/or view the rich log in either XML or HTML format.</span></span>

<span data-ttu-id="eccc4-124">Beispielsweise können lync Server 2010 Administratoren das Cmdlet **Test-CsRegistration** ausführen, indem Sie einen Befehl wie den folgenden verwenden:</span><span class="sxs-lookup"><span data-stu-id="eccc4-124">For example, Lync Server 2010 administrators might run the **Test-CsRegistration** cmdlet by using a command similar to the following:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com

<span data-ttu-id="eccc4-125">Administratoren können den Parameter OutLoggerVariable gefolgt von einem Variablennamen ihrer Wahl einfügen:</span><span class="sxs-lookup"><span data-stu-id="eccc4-125">Administrators have the option of including the OutLoggerVariable parameter followed by a variable name of their choosing:</span></span>

    Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest

> [!NOTE]  
> <span data-ttu-id="eccc4-p105">Stellen Sie dem Variablennamen kein $-Zeichen voran. Verwenden Sie einen Variablennamen wie RegistrationTest und nicht $RegistrationTest.</span><span class="sxs-lookup"><span data-stu-id="eccc4-p105">Do not preface the variable name with the $ character. Use a variable name like RegistrationTest and not $RegistrationTest.</span></span>

<span data-ttu-id="eccc4-128">Die Ausgabe des obigen Befehls ist ähnlich wie die folgende:</span><span class="sxs-lookup"><span data-stu-id="eccc4-128">The preceding command outputs content similar to the following:</span></span>

    Target Fqdn   : atl-cs-001.litwareinc.com
    Result        : Failure
    Latency       : 00:00:00
    Error Message : This machine does not have any assigned certificates.
    Diagnosis     :

<span data-ttu-id="eccc4-p106">Für diesen Fehler sind jedoch viel ausführlichere Informationen verfügbar, als nur die obige Fehlermeldung. Sie können einen ähnlichen Befehl wie den folgenden verwenden, um auf diese Informationen im HTML-Format zuzugreifen und die in der Variablen RegistrationTest gespeicherten Informationen in einer HTML-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="eccc4-p106">However, much more detailed information is available for this failure than just the error message shown above. To access that information in HTML format, use a command similar to this in order to save the information stored in the variable RegistrationTest to an HTML file:</span></span>

    $RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html

<span data-ttu-id="eccc4-131">Alternativ können Sie die XML()-Methode verwenden, um Dateien in einer XML-Datei zu speichern:</span><span class="sxs-lookup"><span data-stu-id="eccc4-131">Alternatively, you can use the ToXML() method to save the data to an XML file:</span></span>

    $RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml

<span data-ttu-id="eccc4-132">Diese Dateien können dann mit Internet Explorer, Visual Studio oder einer beliebigen anderen Anwendung angezeigt werden, die HTML/XML-Dateien öffnen kann.</span><span class="sxs-lookup"><span data-stu-id="eccc4-132">These files can then be viewed using Internet Explorer, Visual Studio, or any other application capable of opening HTML/XML files.</span></span>

<span data-ttu-id="eccc4-133">Synthetische Transaktionen, die von innerhalb von System Center Operations Manager ausgeführt werden, generieren diese Protokolldateien automatisch für Fehler.</span><span class="sxs-lookup"><span data-stu-id="eccc4-133">Synthetic transactions run from inside of System Center Operations Manager will automatically generate these log files for failures.</span></span> <span data-ttu-id="eccc4-134">Diese Protokolle werden jedoch nicht generiert, wenn die Ausführung fehlschlägt, bevor Windows PowerShell die synthetische Transaktion laden und ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="eccc4-134">However, these logs will not be generated if the execution fails before Windows PowerShell is able to load and run the synthetic transaction.</span></span>

> [!IMPORTANT]  
> <span data-ttu-id="eccc4-135">Standardmäßig speichert lync Server 2013 Protokolldateien in einem Ordner, der nicht freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="eccc4-135">By default, Lync Server 2013 saves log files to a folder that is not shared.</span></span> <span data-ttu-id="eccc4-136">Damit diese Protokolle leicht zugänglich sind, sollten Sie diesen Ordner freigeben (beispielsweise \\ \\ATL-Watcher-001. litwareinc. com\WatcherNode.</span><span class="sxs-lookup"><span data-stu-id="eccc4-136">To make these logs readily accessible, you should share this folder (for example, \\\\atl-watcher-001.litwareinc.com\WatcherNode.</span></span>


</div>

</div>

</div>

</div>

