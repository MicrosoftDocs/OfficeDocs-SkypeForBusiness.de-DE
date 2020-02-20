---
title: Entfernen eines autorisierten Hosteintrags
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove an authorized host entry
ms:assetid: 56a04140-347e-4eef-bede-0e858534f71e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204902(v=OCS.15)
ms:contentKeyID: 48184177
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26a3308c741a201650592e4e04d4518aba75a640
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-an-authorized-host-entry"></a>Entfernen eines autorisierten Hosteintrags

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

In diesem Thema wird beschrieben, wie Sie einen autorisierten Legacyhost Eintrag (als *vertrauenswürdiger Anwendungseintrag* in lync Server 2013 bezeichnet) entfernen. Sie müssen vorhandene autorisierte Hosteinträge für alle SIP/CSTA-Gateways in Ihrer Office Communications Server 2007 R2-Bereitstellung entfernen, wenn Sie die Remoteanrufsteuerung zu einer lync Server 2013-Bereitstellung migrieren. Sie müssen die in Office Communications Server 2007 R2 enthaltenen Verwaltungstools verwenden, um die vorhandenen autorisierten Hosteinträge zu entfernen.

<div>

## <a name="to-remove-an-authorized-host-entry-in-an-office-communications-server-2007-r2-deployment"></a>So entfernen Sie einen Eintrag für einen autorisierten Host aus einer Office Communications Server 2007 R2-Bereitstellung

1.  Öffnen Sie die Office Communications Server 2007 R2 Verwaltungskonsole.

2.  Erweitern Sie die Struktur, und klicken Sie mit der rechten Maustaste auf den Pool, in dem der autorisierte Host erstellt wurde.

3.  Klicken Sie auf **Eigenschaften** und dann auf **Front-End-Eigenschaften**.

4.  Klicken Sie auf die Registerkarte **Hostautorisierung**.

5.  Wählen Sie einen Server aus, und klicken Sie dann auf **Entfernen**.

6.  Klicken Sie im Dialogfeld **Eigenschaften** auf **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

