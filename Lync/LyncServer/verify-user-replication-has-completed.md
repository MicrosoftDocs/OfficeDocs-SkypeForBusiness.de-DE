---
title: Überprüfen, ob die Benutzerreplikation abgeschlossen wurde
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 35e6cde338c4469cc7a04452cdf03fe87077d89f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a>Überprüfen, ob die Benutzerreplikation abgeschlossen wurde

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-17_

Beim Ausführen des Cmdlets " **CsUser** " kann ein Fehler auftreten, da die Benutzerinformationen zwischen Active Directory-Domänendienste (AD DS) und den lync Server 2013-Datenbanken nicht mehr synchron sind, da die anfängliche Replikation unvollständig ist. Die Zeit, die für den erfolgreichen Abschluss der anfänglichen Synchronisierung des lync Server 2013 Benutzerreplikationsdiensts erforderlich ist, hängt von der Anzahl der Domänencontroller ab, die in der Active Directory Gesamtstruktur gehostet werden, die den lync Server 2013 Pool hostet. Der anfängliche Synchronisierungsprozess für den lync Server 2013 Benutzerreplikationsdienst tritt auf, wenn die lync Server 2013 Front-End-Server zum ersten Mal gestartet wird. Danach wird die Synchronisierungshäufigkeit durch das Benutzerreplikationsintervall bestimmt. Führen Sie die folgenden Schritte aus, um zu überprüfen, ob die Benutzerreplikation erfolgreich abgeschlossen wurde, bevor Sie das Cmdlet **Move-CsUser** ausführen.

<div>

## <a name="to-verify-user-replication-has-completed"></a>So überprüfen Sie, ob die Benutzerreplikation abgeschlossen wurde

1.  Melden Sie sich auf dem Computer, auf dem der Topologie-Generator installiert ist, als Mitglied der Gruppe "Domänen-Admins" oder "RTCUniversalServerAdmins" an.

2.  Klicken Sie auf das Menü **Start** und anschließend auf **Ausführen**.

3.  Geben Sie **eventvwr.exe** ein, und klicken Sie dann auf **OK**.

4.  Klicken Sie in der Ereignisanzeige auf **Anwendungs- und Dienstprotokolle**, um die Ansicht zu erweitern, und wählen Sie dann "Lync Server".

5.  Klicken Sie im Bereich **Aktion** auf **Aktuelles Protokoll filtern**.

6.  Klicken Sie in der Liste **Ereignisquellen** auf **LS User Replicator**.

7.  Geben Sie in ** \<alle\> Ereignis-IDs** **30024** ein, und klicken Sie dann auf **OK**.

8.  Suchen Sie auf der Registerkarte **Allgemein** in der Liste der gefilterten Ereignisse einen Eintrag, der angibt, dass die Benutzerreplikation erfolgreich ausgeführt wurde.

</div>

</div>

<span> </span>

</div>

</div>

</div>

