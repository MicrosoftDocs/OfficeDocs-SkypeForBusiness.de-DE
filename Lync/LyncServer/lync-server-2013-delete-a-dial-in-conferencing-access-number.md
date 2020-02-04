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
ms.openlocfilehash: 65d461aafd4f111484faf295bef2dd50685e41e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765223"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>Löschen einer Zugriffsnummer für Einwahlkonferenzen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Zugriffsnummer für Einwahlkonferenzen zu löschen.

<div>

## <a name="to-delete-a-dial-in-conferencing-access-number"></a>So löschen Sie eine Zugriffsnummer für Einwahlkonferenzen

1.  Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Zugriffsnummer für Einwahl**.

4.  Klicken Sie auf der Seite auf die Einwahlnummer, die Sie aus der Liste löschen möchten, dann auf **Bearbeiten** und schließlich auf **Löschen**.

5.  Klicken Sie anschließend auf **OK**.

</div>

<div>

## <a name="removing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Entfernen von Einwahlkonferenz-Zugriffsnummern mithilfe von Windows PowerShell-Cmdlets

Zugriffsnummern für Einwahlkonferenzen können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsDialInConferencingAccessNumber** gelöscht werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-dial-in-conferencing-access-number"></a>So entfernen Sie eine bestimmte Zugriffsnummer für Einwahlkonferenzen

  - Dieser Befehl löscht die Zugriffsnummer für Einwahlkonferenzen mit Identity SIP:RedmondDialInAccess@litwareinc.com:
    
        Remove-CsDialInConferencingAccessNumber -Identity "sip:RedmondDialInAccess@litwareinc.com"

</div>

<div>

## <a name="to-remove-all-the-dial-in-conferencing-access-numbers-assigned-to-a-specific-region"></a>So entfernen Sie alle Zugriffsnummern für Einwahlkonferenzen, die einem bestimmten Bereich zugewiesen sind

  - Dieser Befehl löscht alle Zugriffsnummern für Einwahlkonferenzen, die mit der Nordwest-Region verbunden sind:
    
        Get-CsDialInConferencingAccessNumber -Region "Northwest" | Remove-CsDialInConferencingAccessNumber

</div>

<div>

## <a name="to-remove-dial-in-conferencing-access-numbers-based-on-primary-language"></a>So entfernen Sie Zugriffsnummern für Einwahlkonferenzen basierend auf der primären Sprache

  - Dieser Befehl löscht alle Einwahlkonferenz-Zugriffsnummern, wobei Italienisch die primäre Sprache ist:
    
        Get-CsDialInConferencingAccessNumber | Where-Object {$_.PrimaryLanguage -eq "it-IT"} | Remove-CsDialInConferencingAccessNumber

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Remove-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

