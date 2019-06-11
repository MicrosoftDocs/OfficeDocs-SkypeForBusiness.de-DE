---
title: 'Lync Server 2013: Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Zurücksetzen der globalen Richtlinie für den externen Benutzerzugriff in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Es ist nicht möglich, eine globale Richtlinie vollständig zu löschen. Wenn Sie die Option " **Löschen** " in der globalen Richtlinie verwenden, wird die globale Richtlinie nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen beinhalten.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>So setzen Sie die globale Richtlinie auf die Standardeinstellungen zurück

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **externer Benutzer Zugriff**, und klicken Sie auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die globale Richtlinie, klicken Sie auf **Bearbeiten**und dann auf **Löschen**.

5.  Wenn Sie aufgefordert werden, den Löschvorgang zu bestätigen, klicken Sie auf **OK**. Oben auf der Seite wird eine Meldung angezeigt, in der Sie darüber informiert werden, dass die globale Richtlinie zurückgesetzt wurde.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Zurücksetzen der globalen Richtlinie für den externen Zugriff mithilfe von Windows PowerShell-Cmdlets

Die globale Richtlinie für den externen Zugriff kann mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy zurückgesetzt werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Windows PowerShell-Remotesitzung ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>So setzen Sie die globale Richtlinie für den externen Zugriff zurück

  - Mit diesem Befehl wird die globale Richtlinie für den externen Zugriff zurückgesetzt:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

