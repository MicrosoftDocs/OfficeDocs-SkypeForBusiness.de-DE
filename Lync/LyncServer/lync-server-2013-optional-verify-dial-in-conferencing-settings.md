---
title: 'Lync Server 2013: (optional) Überprüfen der Einstellungen für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c43646572171a93880dd5013c87a08a2051ab2a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530792"
---
# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>Optional Überprüfen der Einstellungen für Einwahlkonferenzen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2010-11-02_

Als abschließende Überprüfung ihrer Einwahlkonferenz Konfiguration können Sie nach Wählplänen suchen, die über eine Region für Einwahlkonferenzen verfügen, die von keiner Zugriffsnummer verwendet wird, und für Zugriffsnummern, die keinen Bereich für Einwahlkonferenzen angegeben haben. Dieser Schritt ist optional.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>So suchen Sie nach Wählplänen mit einer Region für Einwahlkonferenzen, die nicht von einer Zugriffsnummer verwendet wird

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    Dieses Cmdlet gibt alle Wählpläne mit einer Region für Einwahlkonferenzen zurück, die von keiner Zugriffsnummer verwendet wird.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>So suchen Sie Zugriffsnummern ohne zugewiesene Regionen

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    Dieses Cmdlet gibt alle Zugriffsnummern für Einwahlkonferenzen zurück, die keiner Region zugeordnet sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

