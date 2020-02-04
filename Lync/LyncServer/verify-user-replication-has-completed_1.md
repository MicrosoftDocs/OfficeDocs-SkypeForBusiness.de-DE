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
ms.openlocfilehash: bc6d8100a7bd0d348c3414da627584bae8697a1c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730775"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Bei der Ausführung des Cmdlets **Move-CsLegacyUser** tritt möglicherweise ein Fehler auf, da die Benutzerinformationen zwischen den Active Directory-Domänendiensten (AD DS) und den lync Server 2013-Datenbanken nicht synchronisiert werden, da die anfängliche Replikation unvollständig ist. Die Zeit, die für den erfolgreichen Abschluss der ersten Synchronisierung des lync Server 2013-Benutzerreplikationsdiensts benötigt wird, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory-Gesamtstruktur gehostet werden, die den lync Server 2013-Pool hostet. Der erst Synchronisierungsvorgang des lync Server 2013-Benutzerreplikationsdiensts erfolgt, wenn der lync Server 2013-Front-End-Server zum ersten Mal gestartet wird. Danach basiert die Synchronisierung auf dem Intervall des Benutzerreplikationsdiensts. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation abgeschlossen ist, bevor Sie das Cmdlet **Move-CsLegacyUser** ausführen.

<div>

## <a name="to-verify-that-user-replication-has-completed"></a>So überprüfen Sie, ob die Benutzerreplikation abgeschlossen ist

1.  Klicken Sie auf dem lync Server 2013-Front-End-Server auf das **Startmenü** , und klicken Sie dann auf **Ausführen**.

2.  Geben Sie **eventvwr. exe** ein, und klicken Sie dann auf **OK**.

3.  Klicken Sie in der Ereignisanzeige auf **Anwendungen und Dienstprotokolle** , um Sie zu erweitern, und wählen Sie dann lync Server aus.

4.  Klicken Sie im Bereich **Aktionen** auf **Aktuelles Protokoll filtern**.

5.  Klicken Sie in der Liste **Ereignisquellen** auf **ls-Benutzer Replikations**Dienst.

6.  Geben Sie in ** \<alle\> Ereignis-IDs** **30024** ein, und klicken Sie dann auf **OK**.

7.  Suchen Sie in der Liste Gefilterte Ereignisse auf der Registerkarte **Allgemein** nach einem Eintrag, der besagt, dass die Benutzerreplikation erfolgreich abgeschlossen wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

