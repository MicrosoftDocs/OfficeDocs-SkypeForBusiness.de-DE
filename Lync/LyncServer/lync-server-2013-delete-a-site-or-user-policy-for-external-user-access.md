---
title: 'Lync Server 2013: Löschen einer Standort-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b7cadad0e914104a8392d1f6b36167780a2b759
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Löschen einer Standort-oder Benutzerrichtlinie für den Zugriff durch externe Benutzer in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-22_

Sie können eine beliebige Website oder Benutzerrichtlinie löschen, die in lync Server-Systemsteuerung auf der Seite **Richtlinie für den externen Zugriff** aufgeführt ist. Wenn Sie die globale Richtlinie löschen, wird Sie nicht tatsächlich gelöscht, sondern nur auf die Standardeinstellungen zurückgesetzt, die keine Unterstützung für externe Benutzerzugriffsoptionen enthalten. Ausführliche Informationen zum Zurücksetzen der globalen Richtlinie finden Sie unter [Zurücksetzen der globalen Richtlinie für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>So löschen Sie eine Standort- oder Benutzerrichtlinie für den externen Benutzerzugriff

1.  Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Externer Benutzerzugriff** und dann auf **Richtlinie für den externen Zugriff**.

4.  Klicken Sie auf der Registerkarte **Richtlinie für den externen Zugriff** auf die zu löschende Standort- oder Benutzerrichtlinie, klicken Sie auf **Bearbeiten** und dann auf **Löschen**.

5.  Klicken Sie zum Bestätigen des Löschvorgangs auf **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von PIN-Richtlinien mithilfe von Windows PowerShell-Cmdlets

Richtlinien für den externen Zugriff können mithilfe von Windows PowerShell und dem Cmdlet Remove-CsExternalAccessPolicy gelöscht werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>So entfernen Sie eine bestimmte Richtlinie für den externen Zugriff

  - Dieser Befehl entfernt die Richtlinie für den externen Zugriff, die auf den Standort "Redmond" angewendet werden:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>So entfernen Sie alle auf Benutzerebene angewendeten Richtlinien für den externen Zugriff

  - Dieser Befehl entfernt alle Richtlinien für den externen Zugriff, die auf Benutzerbasis konfiguriert wurden:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>So entfernen Sie alle externen Zugriffsrichtlinien, bei denen der Zugriff außerhalb des Benutzers deaktiviert ist

  - Dieser Befehl löscht alle Richtlinien für den externen Zugriff, für die der externe Benutzerzugriff deaktiviert ist:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

