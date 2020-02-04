---
title: Überprüfen, ob alle Exchange um-Kontaktobjekte aus dem Legacy Pool entfernt wurden
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
ms.openlocfilehash: 0e49aa2fdef3731a34de05e04b8195cb8aa32cd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-that-all-exchange-um-contact-objects-are-removed-from-the-legacy-pool"></a>Überprüfen, ob alle Exchange um-Kontaktobjekte aus dem Legacy Pool entfernt wurden

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-26_

Verwenden Sie entweder das **OCSUmUtil** -Tool oder das Cmdlet " **Get-CsExumContact** ", um zu überprüfen, ob Exchange um-Kontaktobjekte aus dem Legacy Office Communications Server 2007 R2-Pool entfernt wurden. **OCSUmUtil** befindet sich im folgenden Ordner:

% Programmdateien%\\allgemeine Dateien\\lync Server 2013\\unter\\stützt OCSUMUtil. exe

**OCSUmUtil** muss von einem Benutzerkonto ausgeführt werden, das Folgendes hat:

  - Mitgliedschaft in der Gruppe "RTCUniversalServerAdmins" und "RTCUniversalUserAdmins" (die Rechte zum Lesen von Exchange Server Unified Messaging-Einstellungen umfasst)

  - Domänenrechte zum Erstellen von Kontaktobjekten im angegebenen Organisationseinheitscontainer (OU)

Ausführliche Informationen zur Verwendung des Cmdlets **Get-CsExumContact** finden Sie unter [Get-CsExumContact](https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact) in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<span> </span>

</div>

</div>

</div>

