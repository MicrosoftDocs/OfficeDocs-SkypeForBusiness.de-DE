---
title: 'Lync Server 2013: (optional) überprüfen von Einwahlkonferenzen'
description: 'Lync Server 2013: (optional) überprüfen von Einwahlkonferenzen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e8d3734e89555bf4b298ac68e1e3bd67b1d901
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572536"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>Optional Überprüfen von Einwahlkonferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2011-01-21_

Sie müssen die folgenden Aufgaben ausführen, um sicherzustellen, dass die Webseite mit den Einstellungen für Einwahlkonferenzen und die Zugriffsnummern für die Einwahl ordnungsgemäß funktionieren:

  - Testen Sie die Webseite mit Einstellungen für Einwahlkonferenzen, indem Sie sich über die einfache URL anmelden.

  - Testen Sie die Zugriffsnummern für einen bestimmten Pool, indem Sie das weiter unten in diesem Thema gezeigte Skript ausführen. Dieses Skript simuliert Anrufe bei Zugriffsnummern. Sie benötigen zur Verwendung dieses Skripts die SIP-Adresse und Anmeldeinformationen für einen Unified Communications-Client (UC), der im angegebenen Pool gehostet wird.

Dieser Schritt ist optional.

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>So testen Sie Zugriffsnummern für einen spezifischen Pool

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    In den Berichtergebnissen wird der Test entweder als erfolgreich oder mit Fehlern angezeigt, zusammen mit spezifischen Diagnoseinformationen. Mit dem Flag "–Verbose" werden detailliertere Informationen bereitgestellt, z. B. die Anzahl von ermittelten Zugriffsnummern sowie weitere Informationen zu den Zugriffsnummern.

</div>

</div>

<span> </span>

</div>

</div>

</div>

