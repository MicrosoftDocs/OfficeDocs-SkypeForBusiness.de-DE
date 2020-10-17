---
title: Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden
description: Stellen Sie sicher, dass alle Exchange um Kontaktobjekte aus dem vorversionspool entfernt werden.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify that all Exchange UM Contact objects are removed from the legacy pool
ms:assetid: 5a813169-0ed7-4f84-a242-ed2cd4ea5c43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688068(v=OCS.15)
ms:contentKeyID: 49733664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af5dea6cf746c55d8fecf074e132f721c380de1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555511"
---
# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Überprüfen, ob alle Exchange um Kontaktobjekte aus dem Legacy Pool entfernt wurden

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-26_

Verwenden Sie entweder das **OCSUmUtil** -Tool oder das Cmdlet **Get-CsExumContact** , um sicherzustellen, dass Exchange um Kontaktobjekte aus dem Legacy Office Communications Server 2007 R2-Pool entfernt wurden. **OCSUmUtil** ist im folgenden Ordner gespeichert:

% Programmdateien% \\ Allgemeine Dateien \\ lync Server 2013 \\ Support \\OcsUMUtil.exe

**OCSUmUtil** muss von einem Benutzerkonto mit folgenden Eigenschaften ausgeführt werden:

  - Mitgliedschaft in den Gruppen RTCUniversalServerAdmins und RTCUniversalUserAdmins (mit der Berechtigung zum Lesen von Exchange Server Unified Messaging-Einstellungen)

  - Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen OU-Container (Organizational Unit, Organisationseinheit)

Ausführliche Informationen zur Verwendung des **Get-CsExumContact** -Cmdlets finden Sie unter [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in der lync Server-Verwaltungsshell Dokumentation.

</div>

<span> </span>

</div>

</div>

</div>

