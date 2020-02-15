---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6433c1e88edf69b957047b9dc405df392e5ec104
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-28_

Beim Ausführen des Cmdlets " **CsLegacyUser** " kann ein Fehler auftreten, da Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und den lync Server 2013 Datenbanken nicht mehr synchron sind, da die anfängliche Replikation unvollständig ist. Die Zeit, die für den erfolgreichen Abschluss der anfänglichen Synchronisierung des lync Server 2013 Benutzerreplikationsdiensts erforderlich ist, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory Gesamtstruktur gehostet werden, die den lync Server 2013 Pool hostet. Der anfängliche Synchronisierungsprozess für den lync Server 2013 Benutzerreplikationsdienst tritt auf, wenn die lync Server 2013 Front-End-Server zum ersten Mal gestartet wird. Danach wird die Synchronisierungshäufigkeit durch das Benutzerreplikationsintervall bestimmt. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet **Move-CsLegacyUser** ausführen.

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>So überprüfen Sie, dass die Benutzerreplikation abgeschlossen wurde

1.  Klicken Sie auf dem lync Server 2013-Front-End-Server auf das **Startmenü** , und klicken Sie dann auf **Ausführen**.

2.  Geben Sie **eventvwr.exe** ein, und klicken Sie dann auf **OK**.

3.  Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle**, um die Ansicht zu erweitern, und wählen Sie dann "Lync Server".

4.  Klicken Sie im Bereich **Aktion** auf **Aktuelles Protokoll filtern**.

5.  Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.

6.  Geben Sie in ** \<alle\> Ereignis-IDs** **30024** ein, und klicken Sie dann auf **OK**.

7.  Suchen Sie auf der Registerkarte **Allgemein** in der Liste der gefilterten Ereignisse einen Eintrag, der angibt, dass die Benutzerreplikation erfolgreich ausgeführt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

