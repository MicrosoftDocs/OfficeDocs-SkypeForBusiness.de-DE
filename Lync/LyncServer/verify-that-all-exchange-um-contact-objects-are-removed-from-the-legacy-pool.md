---
title: Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7815f78dfa5f2b4aab3f09102a9948498c20cf10
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Verwenden Sie entweder das **OCSUmUtil** -Tool oder das Cmdlet **Get-CsExumContact** , um sicherzustellen, dass Exchange um Kontaktobjekte aus dem Legacy Office Communications Server 2007 R2-Pool entfernt wurden. **OCSUmUtil** ist im folgenden Ordner gespeichert:

% Programmdateien%\\allgemeine Dateien\\lync Server 2013\\unter\\stützen OCSUMUtil. exe

**OCSUmUtil** muss von einem Benutzerkonto mit folgenden Eigenschaften ausgeführt werden:

  - Mitgliedschaft in den Gruppen RTCUniversalServerAdmins und RTCUniversalUserAdmins (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen)

  - Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen OU-Container (Organizational Unit, Organisationseinheit)

Ausführliche Informationen zur Verwendung des **Get-CsExumContact** -Cmdlets finden Sie unter [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in der lync Server-Verwaltungsshell Dokumentation.

</div>

<span> </span>

</div>

</div>

</div>

