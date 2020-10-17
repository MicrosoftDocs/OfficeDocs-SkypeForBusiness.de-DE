---
title: 'Lync Server 2013: Löschen einer Archivierungsrichtlinie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 387c7dcbf1d53b99bb3dd31b308ff4786f8f5803
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525422"
---
# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Löschen einer Archivierungsrichtlinie in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

Benutzer- und Standortrichtlinien können gelöscht werden. Die globale Richtlinie kann nicht entfernt werden. Wenn Sie versuchen, die globale Richtlinie zu löschen, setzt lync Server 2013 die Richtlinie automatisch auf die Standardwerte zurück.

<div>


> [!NOTE]  
> Wenn Sie Microsoft Exchange Integration für Ihre Bereitstellung aktiviert haben, Steuern Exchange-Richtlinien, ob die Archivierung für die Benutzer aktiviert ist, die in Exchange 2013 verwaltet werden, und lassen ihre Postfächer In-Place halten. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Einrichten von Richtlinien für die Archivierung in lync Server 2013 bei Verwendung Exchange Server Integration</A> in die Bereitstellungsdokumentation.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>So löschen Sie eine Benutzer- oder Standortrichtlinie für die Archivierung

1.  Melden Sie sich von einem Benutzerkonto, das der CsArchivingAdministrator- oder der CsAdministrator-Rolle zugeordnet ist, auf einem beliebigen Computer Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Archivierungsrichtlinie**.

4.  Klicken Sie in der Liste der Archivierungsrichtlinien auf die zu löschende Benutzer- oder Standortrichtlinie, auf **Bearbeiten** und dann auf **Löschen**.

5.  Klicken Sie auf **Commit**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Entfernen von Archivierungsrichtlinien mithilfe von Windows PowerShell-Cmdlets

Archivierungsrichtlinien können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsArchivingPolicy** gelöscht werden. Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>So entfernen Sie eine angegebene Archivierungsrichtlinie

  - **Remove-CsArchivingPolicy** löscht beispielsweise die Richtlinie mit der Identität "site:Redmond". Wenn Sie eine auf Standortebene konfigurierte Richtlinie löschen, werden Benutzer, die zuvor durch die Standortrichtlinie verwaltet wurden, automatisch durch die globale Archivierungsrichtlinie verwaltet. Mit dem folgenden Befehl wird die Archivierung für den Standort "Redmond" entfernt:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>So entfernen Sie alle auf Benutzerebene angewendeten Archivierungsrichtlinien

  - Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, die auf der Benutzerbasis festgelegt wurden:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>So entfernen Sie alle Archivierungsrichtlinien, die die interne Archivierung deaktivieren

  - Mit diesem Befehl werden alle Archivierungsrichtlinien entfernt, bei denen die interne Archivierung deaktiviert wurde:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Verwalten der Archivierung von interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

