---
title: Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

Damit Sie Best Practices Analyzer erfolgreich ausführen können, muss das Benutzerkonto, das Sie für die Anmeldung verwenden, Mitglied der Gruppe Administratoren auf dem lokalen Computer sein. Darüber hinaus muss das Benutzerkonto ein Mitglied der folgenden Gruppen sein, um Ihre Umgebung zu überprüfen:

  - **Domänenadministratoren**   zum Auflisten Active Directory-Domänendienste Informationen und zum Aufrufen der WMI-Anbieter (Windows Management Instrumentation) auf Domänencontrollern und globalen Katalogservern.

  - ****   Für jeden lync Server 2013 internen Computer und jede Edgeserver erforderliche Administratoren, um die WMI-Anbieter (Windows Management Instrumentation) aufzurufen und auf die Registrierung zuzugreifen.

  - **RTCUniversalReadOnlyAdmins**   vollständig oder delegiert schreibgeschützt lync Server 2013 Administratorrechte.

  - **Exchange-Administrator**   mit der Ansicht nur vollständig oder Delegierter Exchange-Administrator mit Ansicht für die Microsoft Exchange Organisation.

Wenn Ihr Benutzerkonto nicht über ausreichende Benutzerrechte verfügt, stehen Ihnen zwei Optionen zur Verfügung:

  - Verwenden Sie an einer Eingabeaufforderung den Befehl **runas** , um das Tool unter einem Konto auszuführen, das über ausreichende Benutzerrechte verfügt. Die Syntax lautet wie folgt:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Legen Sie auf der Seite mit **Active Directory verbinden** die Anmeldeinformationen für die Konten fest, die Sie zum Ausführen von Best Practices Analyzer verwenden möchten. Klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**. Sie können drei Konten eingeben: eine für die Verbindung mit Active Directory-Domänendienste, eine für die Verbindung mit lync Server 2013-Edgeserver und eine für die Verbindung mit den Exchange-Servern. Wenn Sie keines dieser Konten angeben, wird das Benutzerkonto verwendet, das Sie verwendet haben, um sich anzumelden und Best Practices Analyzer auszuführen.

</div>

<span> </span>

</div>

</div>

</div>

