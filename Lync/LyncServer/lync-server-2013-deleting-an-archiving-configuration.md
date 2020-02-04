---
title: 'Lync Server 2013: Löschen einer Archivierungskonfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e4a0c1acf9f605fc927d7006ff50b1f4470c68d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Löschen einer Archivierungskonfiguration in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Sie können eine Websitekonfiguration oder Poolkonfiguration löschen. Die globale Konfiguration kann nicht entfernt werden. Wenn Sie die globale Konfiguration löschen, wird sie automatisch auf die Standardwerte zurückgesetzt. Ausführliche Informationen zur Implementierung von Archivierungs Konfigurationen, einschließlich der Optionen, die Sie angeben können, und der Hierarchie der Archivierungs Konfigurationen finden Sie unter [Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md) in der Planungsdokumentation, Bereitstellungsdokumentation oder in der Betriebsdokumentation.

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>So löschen Sie eine Website-oder Poolkonfiguration für die Archivierung

1.  Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsArchivingAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.

2.  Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen. Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf der linken Navigationsleiste auf **Überwachung und Archivierung** und anschließend auf **Archivierungskonfiguration**.

4.  Klicken Sie in der Liste der Archivierungskonfigurationen auf die zu löschende Standort- oder Poolkonfiguration, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Klicken Sie auf **Commit ausführen**.

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von Archivierungs Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Die Archivierungs Konfigurationseinstellungen können mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsArchivingConfiguration** gelöscht werden. Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>So entfernen Sie eine bestimmte Sammlung von Archivierungs Konfigurationseinstellungen

  - Mit dem folgenden Befehl werden die auf die Redmond-Website angewendeten Archivierungs Konfigurationseinstellungen entfernt:
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle auf den Website Bereich angewendeten Archivierungs Konfigurationseinstellungen

  - Mit diesem Befehl werden alle auf den Dienstbereich angewendeten Archivierungs Konfigurationseinstellungen entfernt:
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>So entfernen Sie Archivierungs Konfigurationseinstellungen auf Grundlage eines angegebenen Eigenschaftswerts

  - Mit diesem Befehl werden alle Archivierungs Konfigurationseinstellungen entfernt, bei denen die Exchange-Archivierung deaktiviert wurde:
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Funktionsweise der Archivierung in lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Verwalten der Archivierung interner und externer Kommunikation in lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

