---
title: 'Lync Server 2013: Löschen einer Zugriffsnummer für Einwahlkonferenzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a dial-in conferencing access number
ms:assetid: 199c5d9c-0489-4ad5-a7f1-ca59fe0e6ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520956(v=OCS.15)
ms:contentKeyID: 48183522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef5d0e51486ed6dca7c9ac17a991b0154c2f1135
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Zugriffsnummer für Einwahlkonferenzen zu löschen.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>So löschen Sie eine Zugriffsnummer für Einwahlkonferenzen

1.  Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.

4.  Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.

5.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Entfernen von Zugriffsnummern für Einwahlkonferenzen mithilfe von Windows PowerShell-Cmdlets

Zugriffsnummern für Einwahlkonferenzen können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsDialInConferencingAccessNumber** gelöscht werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>So entfernen Sie eine bestimmte Zugriffsnummer für Einwahlkonferenzen

  - Mit diesem Befehl wird die Zugriffsnummer für Einwahlkonferenzen mit der Identität "sip:RedmondDialInAccess@litwareinc.com" gelöscht:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>So entfernen Sie alle Zugriffsnummern für Einwahlkonferenzen, die einer bestimmten Region zugewiesen sind

  - Mit diesem Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, die der Region "Northwest" zugeordnet sind:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>So entfernen Sie Zugriffsnummern für Einwahlkonferenzen basierend auf der primären Sprache

  - Mit diesem Befehl werden alle Zugriffsnummern für Einwahlkonferenzen gelöscht, wobei Italienisch die primäre Sprache ist:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

