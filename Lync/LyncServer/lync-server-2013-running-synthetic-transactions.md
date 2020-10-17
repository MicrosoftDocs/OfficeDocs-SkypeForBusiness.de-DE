---
title: 'Lync Server 2013: synthetische Transaktionen werden ausgeführt'
description: 'Lync Server 2013: synthetische Transaktionen werden ausgeführt.'
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
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569351"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Durchführen synthetischer Transaktionen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-18_

Synthetische Transaktionen werden in der Regel auf zwei Arten ausgeführt. Sie können die CsHealthMonitoringConfiguration-Cmdlets verwenden, um Testbenutzer für jeden Ihrer Registrierungsstellen Pools einzurichten. Bei diesen Testbenutzern handelt es sich um ein paar von Benutzern, die für die Verwendung mit synthetischen Transaktionen vorkonfiguriert wurden. (In der Regel handelt es sich um Testkonten und nicht um Konten, die tatsächlichen Benutzern angehören.) Mit Testbenutzern, die für einen Pool konfiguriert sind, können Sie eine synthetische Transaktion für diesen Pool ausführen, ohne die Identitäten von (und die Anmeldeinformationen für) der an dem Test beteiligten Benutzerkonten anzugeben.

Oder Sie können eine synthetische Transaktion mithilfe von tatsächlichen Benutzerkonten ausführen. Wenn beispielsweise zwei Benutzer keine Chatnachrichten austauschen können, können Sie eine synthetische Transaktion mit diesen beiden Benutzerkonten (anstelle eines paar Testkonten) ausführen und dann versuchen, das Problem zu diagnostizieren und zu beheben. Wenn Sie eine synthetische Transaktion mithilfe von tatsächlichen Benutzerkonten durchführen möchten, müssen Sie die Anmeldenamen und Kennwörter für jeden Benutzer angeben.

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von Testbenutzern und Konfigurationseinstellungen für Watcher-Knoten in lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Spezielle Einrichtungsanweisungen für synthetische Transaktionen in lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

