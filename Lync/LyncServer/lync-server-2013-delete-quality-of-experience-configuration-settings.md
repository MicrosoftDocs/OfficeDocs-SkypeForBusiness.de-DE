---
title: 'Lync Server 2013: Quality of Experience-Konfigurationseinstellungen löschen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete Quality of Experience configuration settings
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182613(v=OCS.15)
ms:contentKeyID: 48185954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ab6d90109d177fde84f8693cb4d14b5d8a6fdb9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525542"
---
# <a name="delete-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Löschen von Konfigurationseinstellungen für die Quality of Experience in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-23_

QoE (Quality of Experience)-Metriken dienen der Überwachung der Qualität von Audio- und Videoanrufen in Ihrer Organisation, z. B. der Anzahl der verloren gegangenen Netzwerkpakete, von Hintergrundgeräuschen und der Unterschiede bei Paketverzögerung (Jitter). Diese Metriken werden in einer Datenbank getrennt von anderen Daten (z. B. den Kommunikationsdatensätzen) gespeichert, sodass QoE unabhängig von anderen Datenaufzeichnungen aktiviert und deaktiviert werden kann.

Wenn Sie Microsoft lync Server 2013 installieren, wird eine einzelne globale Auflistung von QoE-Konfigurationseinstellungen für Sie erstellt. Administratoren können darüber hinaus Auflistungen mit benutzerdefinierten Einstellungen erstellen, die auf die einzelnen Standorte angewendet werden können. Prinzipiell haben Einstellungen auf Standortebene Vorrang vor globalen Einstellungen. Wenn Sie Einstellungen auf Standortebene löschen, wird QoE auf dieser Website mithilfe der globalen Einstellungen verwaltet.

Beachten Sie, dass Sie auch die globalen Einstellungen löschen können. Diese globalen Einstellungen werden jedoch tatsächlich nicht entfernt. Stattdessen werden alle Eigenschaften in dieser Auflistung auf die Standardwerte zurückgesetzt. Beispielsweise ist die Bereinigung standardmäßig in einer Auflistung von QoE-Konfigurationseinstellungen aktiviert. Angenommen, Sie ändern die globalen Einstellungen, sodass die Löschung deaktiviert wurde. Wenn Sie später die globalen Einstellungen löschen, werden alle Eigenschaften auf ihre Standardwerte zurückgesetzt. Das bedeutet in diesem Fall, dass die Löschung wieder aktiviert wurde.

Sie können QoE-Konfigurationseinstellungen mithilfe der lync Server-Systemsteuerung oder mithilfe des Cmdlets [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration) entfernen.

<div>

## <a name="to-delete-qoe-configuration-settings-by-using-lync-server-control-panel"></a>So löschen Sie QoE-Konfigurationseinstellungen mithilfe von lync Server-Systemsteuerung

1.  Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an. Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen. Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4.  Klicken Sie auf der Seite **Quality of Experience-Daten** auf die gewünschte Richtlinie, klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Löschen**.

5.  Klicken Sie auf **OK**.

</div>

<div>

## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Entfernen von QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell-Cmdlets

Sie können QoE-Konfigurationseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsQoEConfiguration** löschen. Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a>So entfernen Sie eine angegebene Auflistung von QoE-Konfigurationseinstellungen

  - Mit diesem Befehl werden die QoE-Konfigurationseinstellungen entfernt, die auf den Standort "Redmond" angewendet wurden:
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a>So entfernen Sie alle QoE-Konfigurationseinstellungen, die auf den Website Bereich angewendet werden

  - Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, die auf den Standortbereich angewendet wurden:
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>So entfernen Sie alle QoE-Konfigurationseinstellungen, bei denen die QoE-Überwachung deaktiviert ist

  - Mit diesem Befehl werden alle QoE-Konfigurationseinstellungen entfernt, bei denen die QoE-Überwachung deaktiviert wurde:
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

</div>

Ausführliche Informationen finden Sie unter [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsQoEConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

