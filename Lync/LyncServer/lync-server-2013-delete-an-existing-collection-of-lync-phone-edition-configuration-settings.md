---
title: Löschen einer vorhandenen Sammlung von lync Phone Edition-Konfigurationseinstellungen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5c601726cfc18d230519741ebcc7561da54d73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Wenn Sie eine Sammlung von Einstellungen für Geräte, die lync Phone Edition ausführen, nicht mehr verwenden möchten, löschen Sie Sie. Wenn Sie eine Auflistung für einen Standort löschen, gelten die globalen Einstellungen für die Telefone an diesem Standort. Die globale Auflistung kann nicht gelöscht werden.

<div>


> [!NOTE]
> Anstatt eine Auflistung zu löschen, können Sie auch nur einige der Einstellungen ändern. Ausführliche Informationen zur Vorgehensweise finden Sie unter <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">erstellen oder Ändern einer Sammlung von lync Phone Edition Konfigurationseinstellungen in lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>So löschen Sie eine Sammlung von lync Phone Edition-Konfigurationseinstellungen

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Clients** und dann auf die Navigationsschaltfläche **Gerätekonfiguration**.

4.  Klicken Sie auf der Seite **Gerätekonfiguration** auf die Auflistung, die Sie löschen möchten, klicken Sie auf das Menü **Bearbeiten** und dann auf **Löschen**.
    
    <div>
    

    > [!NOTE]
    > Wenn Sie die globale Auflistung löschen, werden die Einstellungen lediglich auf die Standardeinstellungen zurückgesetzt. Die Auflistung verschwindet nicht.

    
    </div>

5.  Klicken Sie im Bestätigungsfeld auf **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können lync Phone Edition-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsUCConfiguration** löschen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von lync Phone Edition-Konfigurationseinstellungen

  - Mit diesem Befehl werden die UC-Telefonkonfigurationseinstellungen gelöscht, die am Standort Redmond angewendet werden:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten lync Phone Edition-Konfigurationseinstellungen

  - Mit diesem Befehl werden alle UC-Telefoneinstellungen entfernt, die auf Dienstebene angewendet werden:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>So entfernen Sie alle lync Phone Edition-Konfigurationseinstellungen, bei denen die Telefonsperre deaktiviert ist

  - Mit diesem Befehl werden alle Auflistungen von UC-Telefonkonfigurationseinstellungen gelöscht, für die die Telefonsperre deaktiviert wurde:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Ausführliche Informationen finden Sie unter [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

