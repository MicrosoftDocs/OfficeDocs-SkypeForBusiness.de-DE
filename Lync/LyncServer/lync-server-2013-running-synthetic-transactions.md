---
title: 'Lync Server 2013: synthetische Transaktionen werden ausgeführt'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 476223c1c81f6927a1b5f96a78091e0f3c57ea12
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="b023d-102">Durchführen synthetischer Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b023d-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b023d-103">_**Letztes Änderungsstand des Themas:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="b023d-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="b023d-104">Synthetische Transaktionen werden in der Regel auf zwei Arten ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b023d-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="b023d-105">Sie können die CsHealthMonitoringConfiguration-Cmdlets verwenden, um Testbenutzer für jeden Ihrer Registrierungsstellen Pools einzurichten.</span><span class="sxs-lookup"><span data-stu-id="b023d-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="b023d-106">Bei diesen Testbenutzern handelt es sich um ein paar von Benutzern, die für die Verwendung mit synthetischen Transaktionen vorkonfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="b023d-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="b023d-107">(In der Regel handelt es sich um Testkonten und nicht um Konten, die tatsächlichen Benutzern angehören.) Mit Testbenutzern, die für einen Pool konfiguriert sind, können Sie eine synthetische Transaktion für diesen Pool ausführen, ohne die Identitäten von (und die Anmeldeinformationen für) der an dem Test beteiligten Benutzerkonten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b023d-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="b023d-108">Oder Sie können eine synthetische Transaktion mithilfe von tatsächlichen Benutzerkonten ausführen.</span><span class="sxs-lookup"><span data-stu-id="b023d-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="b023d-109">Wenn beispielsweise zwei Benutzer keine Chatnachrichten austauschen können, können Sie eine synthetische Transaktion mit diesen beiden Benutzerkonten (anstelle eines paar Testkonten) ausführen und dann versuchen, das Problem zu diagnostizieren und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="b023d-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="b023d-110">Wenn Sie eine synthetische Transaktion mithilfe von tatsächlichen Benutzerkonten durchführen möchten, müssen Sie die Anmeldenamen und Kennwörter für jeden Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="b023d-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b023d-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b023d-111">See Also</span></span>


[<span data-ttu-id="b023d-112">Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b023d-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="b023d-113">Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b023d-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

