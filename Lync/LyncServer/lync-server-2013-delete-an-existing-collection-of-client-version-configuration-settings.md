---
title: Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Clientversionen
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
ms.openlocfilehash: 00b594254b4ecac166be8e639dd8e7d437fcdffc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Auflistung von Konfigurationseinstellungen für Clientversionen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Wenn Sie die Clientkonfigurationseinstellungen entfernen möchten, die zuvor für einen Standort konfiguriert wurden, können Sie die Einstellungen aus lync Server 2013 Systemsteuerung oder aus lync Server 2013 Verwaltungsshell entfernen.

<div>

## <a name="to-remove-client-configuration-settings-by-using-lync-server-control-panel"></a>So entfernen Sie Clientkonfigurationseinstellungen mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Client Versions Konfiguration** .

4.  Wählen Sie die Website aus, klicken Sie auf **Bearbeiten**, dann auf **Löschen**und dann auf **OK**.

</div>

<div>

## <a name="removing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Konfigurationseinstellungen für Client Versionen mithilfe von Windows PowerShell-Cmdlets

Sie können Konfigurationseinstellungen für Clientversionen mithilfe des Cmdlets **Remove-CsClientVersionConfiguration** löschen. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-collection-of-client-version-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von Konfigurationseinstellungen für die Client Version

  - Mit dem folgenden Befehl werden die Client Versions-Konfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden:
    
        Remove-CsClientVersionConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten Konfigurationseinstellungen für die Client Version

  - Mit diesem Befehl werden alle Client Versions Konfigurationseinstellungen entfernt, die auf Standortebene konfiguriert wurden:
    
        Get-CsClientVersionConfiguration -Filter site:* | Remove-CsClientVersionConfiguration

</div>

<div>

## <a name="to-remove-all-the-client-version-configuration-settings-based-on-the-value-of-the-defaultaction-property"></a>So entfernen Sie alle Konfigurationseinstellungen für Clientversionen basierend auf dem Wert der Eigenschaft "Default"

  - Und mit diesem Befehl werden alle Client Versions Konfigurationseinstellungen entfernt, bei denen die Standardaktion auf "blockieren" festgelegt wurde:
    
        Get-CsClientVersionConfiguration | Where-Object {$_.DefaultAction -eq "Block" | Remove-CsClientVersionConfiguration

</div>

Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg425925(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

