---
title: 'Lync Server 2013: sicherstellen, dass den Wählplänen Regionen zugewiesen wurden'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1982a3625fce40eee9b46036fa4e294ed75edd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>Sicherstellen, dass den Wählplänen lync Server 2013 zugewiesene Regionen zugewiesen sind

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2010-11-02_

Wähleinstellungen, die für Einwahlkonferenzen verwendet werden, müssen eine **Region für Einwahlkonferenzen** enthalten, um Zugriffsnummern für Einwahlkonferenzen den entsprechenden Wähleinstellungen zuzuordnen. Wenn Sie einen Satz mit Wähleinstellungen einrichten, geben Sie die Region für Einwahlkonferenzen an, die für diese Wähleinstellungen gilt. Wenn Sie anschließend die Zugriffsnummern für Einwahlkonferenzen erstellen, wählen Sie die Regionen aus, welche die Zugriffsnummern den geeigneten Wähleinstellungen zuordnen.

Da es wichtig ist, eine Region für alle Wähleinstellungen anzugeben, wird empfohlen, mit diesem Verfahren das Vorhandensein von Regionen für alle Wähleinstellungen zu überprüfen. Dieser Schritt ist optional.

Verwenden Sie das Cmdlet **Get-CsDialPlan** um zu überprüfen, ob für alle Wähleinstellungen eine Region festgelegt wurde. Wenn die Region in einem Satz mit Wähleinstellungen fehlt, können Sie die Region mit dem Cmdlet **Set-CsDialPlan** festlegen. Sie können auch lync Server-Systemsteuerung verwenden, um die Region in vorhandenen Wählplänen zu aktualisieren. Ausführliche Informationen zur Verwendung von lync Server-Systemsteuerung finden Sie unter [Modify a Dial Plan in lync Server 2013](lync-server-2013-modify-a-dial-plan.md).

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>So überprüfen Sie, ob für Wähleinstellungen die Region festgelegt wurde

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie den folgenden Befehl an der Eingabeaufforderung aus:
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    Zum Beispiel:
    
        Get-CsDialPlan
    
    In diesem Beispiel werden alle für Ihre Organisation konfigurierten Wähleinstellungen zurückgegeben.

4.  Überprüfen Sie die zurückgegebenen Wähleinstellungen, um fehlende Regionen für Einwahlkonferenzen zu ermitteln. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>So legen Sie die Region für einen Satz mit Wähleinstellungen fest

1.  Melden Sie sich beim Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** oder **CsAdministrator** an.

2.  Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.

3.  Führen Sie für alle Wähleinstellungen, in denen die Region für Einwahlkonferenzen fehlt, den folgenden Befehl aus:
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    Beispiel:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    In diesem Beispiel wird die Eigenschaft "DialinConferencingRegion" in den Wähleinstellungen mit der Identität "Redmond" in den Wert "US West Coast" geändert. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

