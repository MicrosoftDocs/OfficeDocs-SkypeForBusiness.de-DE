---
title: 'Lync Server 2013: (Optional) Überprüfen der Einwahlkonferenzeinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing settings
ms:assetid: a85efdda-97b0-4f3b-bd26-04416bee8ef5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412789(v=OCS.15)
ms:contentKeyID: 48185027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 177d8516dcb91272eca2a70b89026fc0e175a73a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-settings-in-lync-server-2013"></a>(Optional) Überprüfen der Einwahlkonferenzeinstellungen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2010-11-02_

Zur endgültigen Bestätigung der Einwahlkonferenzkonfiguration können Sie nach Wähleinstellungen suchen, die eine Region für Einwahlkonferenzen aufweisen, die von keiner Zugriffsnummer verwendet wird, und nach Zugriffsnummern suchen, für die keine Region für Einwahlkonferenzen angegeben ist. Dieser Schritt ist optional.

<div>

## <a name="to-find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a>So suchen Sie nach Wählplänen mit einem Bereich für Einwahlkonferenzen, der nicht von einer Zugriffsnummer verwendet wird

1.  Melden Sie sich bei dem Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingAccessNumber -EmptyRegion
    
    Dieses Cmdlet gibt alle Sätze mit Wähleinstellungen mit einer Region für Einwahlkonferenzen zurück, die von keiner Zugriffsnummer verwendet wird.

</div>

<div>

## <a name="to-find-access-numbers-without-assigned-regions"></a>So suchen Sie nach Zugriffsnummern ohne zugewiesene Regionen

1.  Melden Sie sich bei dem Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der Rolle **CS-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialinConferencingAccessNumber -Region NULL
    
    Dieses Cmdlet gibt alle Zugriffsnummern für Einwahlkonferenzen zurück, die keiner Region zugeordnet sind.

</div>

</div>

<span> </span>

</div>

</div>

</div>

