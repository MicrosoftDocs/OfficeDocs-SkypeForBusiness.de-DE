---
title: 'Lync Server 2013: Sicherstellen, dass Wählplänen Regionen zugewiesen wurden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5aa91470accf0f25478b9233e1efb90357251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Sicherstellen, dass die Wähleinstellungen lync Server 2013 Regionen zugewiesen haben

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2010-11-02_

Für Wählpläne, die für Einwahlkonferenzen verwendet werden, muss ein **Bereich für Einwahlkonferenzen** angegeben werden, um Zugriffsnummern für Einwahlkonferenzen mit den entsprechenden Wähleinstellungen zu verknüpfen. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie die Einwahl Zugriffsnummer erstellen, wählen Sie dann die Regionen aus, die die Zugriffsnummer den entsprechenden Wählplänen zuordnen.

Da es wichtig ist, einen Bereich für alle Wählpläne anzugeben, empfehlen wir, dass Sie diese Vorgehensweise verwenden, um zu überprüfen, ob alle Wählpläne Regionen aufweisen. Dieser Schritt ist optional.

Verwenden Sie das Cmdlet **Get-CsDialPlan** , um zu überprüfen, ob der Bereich für alle Wählpläne für Einwahlkonferenzen festgesetzt ist. Wenn die Region in bestimmten Wählplänen nicht vorhanden ist, können Sie die Region über das Cmdlet **Set-CsDialPlan** festlegen. Sie können auch die lync Server-Systemsteuerung verwenden, um den Bereich in vorhandenen Wählplänen zu aktualisieren. Ausführliche Informationen zur Verwendung der lync Server-Systemsteuerung finden Sie unter [Ändern von Wähleinstellungen in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde

1.  Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Beispiel:
    
        Get-CsDialPlan
    
    In diesem Beispiel werden alle für Ihre Organisation konfigurierten Wähleinstellungen zurückgegeben.

4.  Überprüfen Sie die zurückgegebenen Wähleinstellungen, um fehlende Regionen für Einwahlkonferenzen zu ermitteln. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>So legen Sie die Region für einen Satz mit Wähleinstellungen fest

1.  Melden Sie sich beim Computer als Mitglied der Gruppe „RTCUniversalServerAdmins“ oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Beispiel:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert. Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

