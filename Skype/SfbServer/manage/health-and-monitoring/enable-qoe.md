---
title: Aktivieren der Benutzererfahrung in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Zusammenfassung: Erfahren Sie, wie Sie QoE (Quality of Experience) in Skype for Business Server aktivieren.'
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095209"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Aktivieren der Benutzererfahrung in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie QoE (Quality of Experience) in Skype for Business Server aktivieren.

Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben. Ausführliche Informationen finden Sie unter [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in der Planungsdokumentation.

Verwenden Sie das folgende Verfahren, um QoE für Ihre gesamte Organisation oder jede Website in Ihrer Organisation zu aktivieren.

> [!NOTE]
> Um QoE zu aktivieren, müssen Sie zuerst die Überwachung und eine Überwachungs-Back-End-Datenbank konfigurieren. Ausführliche Informationen finden Sie unter [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>So aktivieren Sie QoE mithilfe der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe RTCUniversalServerAdmins ist (oder über gleichwertige Benutzerrechte verfügt) oder der Rolle CsServerAdministrator oder CsAdministrator zugewiesen ist, bei jedem Computer an, der sich im Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4. Klicken Sie **auf der Seite** Daten zur Qualität der Erfahrung in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion,** und klicken Sie dann auf **QoE aktivieren.**

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Aktivieren von QoE mithilfe Windows PowerShell Cmdlets

Sie können QoE mithilfe Windows PowerShell und dem **Cmdlet Set-CsQoEConfiguration** aktivieren. Sie können dieses Cmdlet entweder über die Skype for Business Server Management Shell oder über eine Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-enable-qoe-for-a-single-location"></a>So aktivieren Sie QoE für einen einzelnen Speicherort

 Um QoE zu aktivieren, legen Sie den Parameter EnableQoE auf True ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>So deaktivieren Sie QoE für einen einzelnen Speicherort

 Um QoE zu deaktivieren, legen Sie den Parameter EnableQoE auf False ($False). Dadurch wird die Überwachung nicht deinstalliert. Es hält die Sammlung und Speicherung von QoE-Daten an.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>So verwenden Sie einen einzelnen Befehl zum Aktivieren von QoE an mehreren Speicherorten

 Mit diesem Befehl wird QoE für alle QoE-Konfigurationseinstellungen aktiviert, die derzeit in Ihrer Organisation verwendet werden.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Weitere Informationen finden Sie unter [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>Siehe auch

[Planen der Überwachung](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Bereitstellen des Monitoring Servers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)