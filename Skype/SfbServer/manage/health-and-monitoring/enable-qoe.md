---
title: Aktivieren der Erlebnisqualität in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Zusammenfassung: Erfahren Sie, wie Sie QoE (Quality of Experience) in Skype for Business Server aktivieren.'
ms.openlocfilehash: 3edd7aa136499dcc4b1fd423a1369dcff33f0968
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014749"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Aktivieren der Erlebnisqualität in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie QoE (Quality of Experience) in Skype for Business Server aktivieren.

Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben. Ausführliche Informationen finden Sie unter ["Planen der Überwachung"](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in der Planungsdokumentation.

Verwenden Sie das folgende Verfahren, um QoE für Die gesamte Organisation oder jeden Standort in Ihrer Organisation zu aktivieren.

> [!NOTE]
> Um QoE zu aktivieren, müssen Sie zuerst die Überwachung und eine Back-End-Überwachungsdatenbank konfigurieren. Ausführliche Informationen finden Sie unter [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>So aktivieren Sie QoE mithilfe Skype for Business Server Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4. Klicken Sie auf der Seite **"Quality of Experience Data"** in der Tabelle auf die entsprechende Sammlung, klicken Sie auf **"Aktion"** und dann auf **"QoE aktivieren".**

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Aktivieren von QoE mithilfe Windows PowerShell Cmdlets

Sie können QoE mit Windows PowerShell und dem Cmdlet **"Set-CsQoEConfiguration"** aktivieren. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-enable-qoe-for-a-single-location"></a>So aktivieren Sie QoE für einen einzelnen Speicherort

 Um QoE zu aktivieren, legen Sie den Parameter EnableQoE auf "True" ($True) fest.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>So deaktivieren Sie QoE für einen einzelnen Speicherort

 Um QoE zu deaktivieren, legen Sie den Parameter "EnableQoE" auf "False" ($False) fest. Dadurch wird die Überwachung nicht deinstalliert. Die Erfassung und Speicherung von QoE-Daten wird angehalten.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>So verwenden Sie einen einzelnen Befehl, um QoE an mehreren Speicherorten zu aktivieren

 Dieser Befehl aktiviert QoE für alle QoE-Konfigurationseinstellungen, die derzeit in Ihrer Organisation verwendet werden.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Ausführliche Informationen finden Sie unter ["Set-CsQoEConfiguration".](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>Weitere Informationen

[Planen der Überwachung](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Bereitstellen des Monitoring Servers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)