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
ms.openlocfilehash: b9561736fc6dce1649d0a3dd29e15a7d88500a38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Gruppenmitgliedschaften und Benutzerrechte Anforderungen für Best Practices Analyzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Damit Sie Best Practices Analyzer erfolgreich ausführen können, muss das Benutzerkonto, das Sie für die Anmeldung verwenden, ein Mitglied der Gruppe Administratoren auf dem lokalen Computer sein. Darüber hinaus muss das Benutzerkonto ein Mitglied der folgenden Gruppen sein, um die Umgebung zu überprüfen:

  - **Domänenadministratoren**   , um Informationen zu Active Directory-Domänendiensten aufzulisten und die WMI-Anbieter (Windows Management Instrumentation) auf Domänencontrollern und globalen Katalogservern aufzurufen.

  - **Administratoren**   , die für jeden lync Server 2013-internen Computer und jeden Edgeserver erforderlich sind, um die WMI-Anbieter (Windows Management Instrumentation) anzurufen und auf die Registrierung zuzugreifen.

  - **RTCUniversalReadOnlyAdmins**   vollständig oder delegiert lesen Sie nur lync Server 2013-Administratorrechte.

  - **Exchange-Administrator**   "nur anzeigen" vollständiger oder Delegierter Exchange-Administrator "nur anzeigen" für die Microsoft Exchange-Organisation.

Wenn Ihr Benutzerkonto nicht über ausreichende Benutzerrechte verfügt, haben Sie zwei Möglichkeiten:

  - Verwenden Sie an einer Eingabeaufforderung den Befehl **runas** , um das Tool unter einem Konto auszuführen, das über genügend Benutzerrechte verfügt. Die Syntax lautet wie folgt:
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - Setzen Sie auf der Seite **mit Active Directory verbinden** die Anmeldeinformationen für die Konten, die Sie zum Ausführen von Best Practices Analyzer verwenden möchten. Klicken Sie auf **Erweiterte Anmeldeoptionen anzeigen**. Sie können drei Konten eingeben: eine zum Herstellen einer Verbindung mit Active Directory-Domänendiensten, eine zum Herstellen einer Verbindung mit lync Server 2013-Edgeserver und eine für die Verbindung zu den Exchange-Servern. Wenn Sie keines dieser Konten angeben, wird das Benutzerkonto verwendet, das Sie für die Anmeldung und die Ausführung von Best Practices Analyzer verwendet haben.

</div>

<span> </span>

</div>

</div>

</div>

