---
title: Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Wenn Sie eine Sammlung von Einstellungen für Geräte, auf denen lync Phone Edition ausgeführt wird, nicht mehr verwenden möchten, löschen Sie Sie. Wenn Sie eine Sammlung für eine Website löschen, gelten die globalen Einstellungen für die Telefone auf dieser Website. Sie können die globale Sammlung nicht löschen.

<div>


> [!NOTE]
> Anstatt eine Sammlung zu löschen, möchten Sie möglicherweise nur einige Einstellungen ändern. Ausführliche Informationen hierzu finden Sie unter <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">erstellen oder Ändern einer Sammlung von lync Phone Edition-Konfigurationseinstellungen in lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>So löschen Sie eine Sammlung von lync Phone Edition-Konfigurationseinstellungen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Gerätekonfiguration** .

4.  Klicken Sie auf der Seite **Device Configuration** auf die Sammlung, die Sie löschen möchten, klicken Sie auf das Menü **Bearbeiten** , und klicken Sie dann auf **Löschen**.
    
    <div>
    

    > [!NOTE]
    > Wenn Sie die globale Sammlung löschen, werden die Einstellungen einfach auf die Standardeinstellungen zurückgesetzt. Die Sammlung verschwindet nicht.

    
    </div>

5.  Klicken Sie im Bestätigungsfeld auf **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen der lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsUCConfiguration** löschen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>So entfernen Sie eine bestimmte Sammlung von lync Phone Edition-Konfigurationseinstellungen

  - Mit diesem Befehl werden die auf die Redmond-Website angewendeten UC-Telefon Konfigurationseinstellungen gelöscht:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten lync Phone Edition-Konfigurationseinstellungen

  - Mit diesem Befehl werden alle auf den Dienstbereich angewendeten UC-Telefon Konfigurationseinstellungen entfernt:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>So entfernen Sie alle lync Phone Edition-Konfigurationseinstellungen, bei denen die Telefon Sperrung deaktiviert ist

  - Dieser Befehl löscht eine beliebige Sammlung von UC-Telefon Konfigurationseinstellungen, bei denen die Telefon Sperrung deaktiviert wurde:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Ausführliche Informationen finden Sie unter [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

