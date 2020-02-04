---
title: Löschen einer vorhandenen Sammlung von Konfigurationseinstellungen für Clientversionen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of client version configuration settings
ms:assetid: 70bf1216-d0d2-45ce-881f-b8edadf3cec7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898480(v=OCS.15)
ms:contentKeyID: 50873760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf3015358c27786b03b505e580acd599e26d4f3a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Sammlung von Konfigurationseinstellungen für Clientversionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie die Clientkonfigurationseinstellungen entfernen möchten, die zuvor für eine Website konfiguriert wurden, können Sie die Einstellungen aus der lync Server 2013-Systemsteuerung oder der lync Server 2013-Verwaltungsshell entfernen.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>So entfernen Sie Clientkonfigurationseinstellungen mithilfe der lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .

4.  Wählen Sie die Website aus, klicken Sie auf **Bearbeiten**, klicken Sie auf **Löschen**, und klicken Sie dann auf **OK**.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Client Versions Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Mithilfe des Cmdlets **Remove-CsClientVersionConfiguration** können Sie Konfigurationseinstellungen für Clientversionen löschen. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>So entfernen Sie eine angegebene Sammlung von Konfigurationseinstellungen für Clientversionen

  - Mit dem folgenden Befehl werden die auf die Redmond-Website angewendeten Konfigurationseinstellungen für Clientversionen entfernt:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten Konfigurationseinstellungen für Clientversionen

  - Mit diesem Befehl werden alle Konfigurationseinstellungen für Clientversionen entfernt, die für den Website Bereich konfiguriert sind:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>So entfernen Sie alle Konfigurationseinstellungen für Clientversionen basierend auf dem Wert der standardmäßigen Eigenschaft

  - Und dieser Befehl entfernt alle Konfigurationseinstellungen für Clientversionen, bei denen die Standardaktion auf "blockieren" gesetzt wurde:
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg425925(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

