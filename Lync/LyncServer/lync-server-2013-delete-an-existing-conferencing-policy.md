---
title: 'Lync Server 2013: Löschen einer vorhandenen konferenzrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing conferencing policy
ms:assetid: 709ed771-790f-4bf1-a4de-b37ca5168688
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688089(v=OCS.15)
ms:contentKeyID: 49733688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bcdbb4ec3c7ea59b17fed97990190881997e6602
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154467"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-conferencing-policy-in-lync-server-2013"></a>Löschen einer vorhandenen konferenzrichtlinie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Führen Sie die folgenden Schritte aus, um eine Konferenzrichtlinie auf Benutzer- oder Standortebene zu löschen.

<div>


> [!NOTE]  
> Die globale Konferenzrichtlinie kann nicht gelöscht werden.



</div>

<div>

## <a name="to-delete-a-site-or-user-conferencing-policy"></a>So löschen Sie eine Konferenzrichtlinie auf Benutzer- oder Standortebene

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Konferenz** und dann auf **Konferenzrichtlinie**.

4.  Klicken Sie in der Liste der Konferenzrichtlinien auf die Standort-oder Benutzerrichtlinie, die Sie löschen möchten, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

</div>

<div>

## <a name="removing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von Konferenzrichtlinien mithilfe von Windows PowerShell-Cmdlets

Sie können Konferenzrichtlinien mit lync Server-Verwaltungsshell und dem Cmdlet **Remove-CsConferencingPolicy** löschen. Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-conferencing-policy"></a>So entfernen Sie eine angegebene Konferenzrichtlinie

  - Mit dem folgenden Befehl wird die Konferenzrichtlinie mit dem Identitätswert "RedmondConferencingPolicy" entfernt:
    
        Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-policies-applied-to-the-per-user-scope"></a>So entfernen Sie alle auf Benutzerebene angewendeten Konferenzrichtlinien

  - Mit dem folgenden Befehl werden alle Konferenzrichtlinien entfernt, die auf Benutzerebene konfiguriert sind:
    
        Get-CsConferencingPolicy -Filter "tag:*" | Remove-CsConferencingPolicy

</div>

<div>

## <a name="to-remove-all-of-the-conferencing-polices-that-allow-recording-by-external-users"></a>So entfernen Sie alle Konferenzrichtlinien, die Aufzeichnungen durch externe Benutzer zulassen

  - Mit dem folgenden Befehl werden alle Konferenzrichtlinien gelöscht, die externen Benutzern das Aufzeichnen der Konferenz erlauben:
    
        Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy

</div>

Ausführliche Informationen finden Sie unter [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsConferencingPolicy).

</div>

</div>

<span> </span>

</div>

</div>

</div>

