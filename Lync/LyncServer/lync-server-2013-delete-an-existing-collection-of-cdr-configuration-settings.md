---
title: 'Lync Server 2013: Löschen einer vorhandenen Sammlung von CDR-Konfigurationseinstellungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d15f224d7e3aa4b43b20925a4efd4007a0c6c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a>Löschen einer vorhandenen Sammlung von CDR-Konfigurationseinstellungen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-23_

Die Funktion zum Aufzeichnen von Kommunikationsdatensätzen (KDS) ermöglicht das Nachverfolgen von Peer-to-Peer-, VoIP- und Konferenzanrufen. Diese Nutzungsdaten umfassen Informationen wie z. B. Anrufer, Angerufener, Anrufzeitpunkt und Anrufdauer.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzige globale Sammlung von CDR-Konfigurationseinstellungen für Sie erstellt. Administratoren haben außerdem die Möglichkeit, benutzerdefinierte Auflistungen von Einstellungen zu erstellen, die auf einzelne Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie die Einstellungen auf Standortebene entfernen, werden die KDS-Daten (Kommunikationsdatensätze) an diesem Standort mithilfe von globalen Einstellungen verwaltet.

Beachten Sie, dass Sie auch die globalen Einstellungen löschen können. Diese globalen Einstellungen werden jedoch tatsächlich nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist in der Auflistung von KDS-Konfigurationseinstellungen standardmäßig die Löschung aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. Das bedeutet in diesem Fall, dass die Löschung wieder aktiviert wurde.

Sie können die CDR-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung oder des Cmdlets [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) entfernen.

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a>So entfernen Sie CDR-Konfigurationseinstellungen mit der lync Server-Systemsteuerung

1.  Klicken Sie in der lync Server-Systemsteuerung auf **Überwachung und Archivierung**.

2.  Wählen Sie auf der Registerkarte **Aufzeichnung von Kommunikationsdatensätzen** die Auflistung (oder Auflistungen) der zu entfernenden KDS-Einstellungen aus. Zum Auswählen mehrerer Auflistungen klicken Sie auf die erste Auflistung, halten Sie die Strg-Taste gedrückt und klicken Sie dann auf weitere Auflistungen.

3.  Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.

4.  Klicken Sie im Dialogfeld lync Server-Systemsteuerung auf **OK**.

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von CDR-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können die Konfigurationseinstellungen für die Anrufdetailaufzeichnung mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsCdrConfiguration** löschen. Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen. Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von KDS-Konfigurationseinstellungen

  - Mit diesem Befehl werden die KDS-Konfigurationseinstellungen entfernt, die auf den Standort „Redmond“ angewendet wurden:
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle KDS-Konfigurationseinstellungen, die auf Standortebene angewendet wurden

  - Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, die auf Standortebene angewendet wurden:
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a>So entfernen Sie alle KDS-Konfigurationseinstellungen, die die Aufzeichnung von Kommunikationsdatensätzen deaktivieren

  - Mit diesem Befehl werden alle KDS-Konfigurationseinstellungen entfernt, bei denen die Aufzeichnung von Kommunikationsdatensätzen deaktiviert wurde:
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

