---
title: Ändern von Quality of Experience-Einstellungen in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Aufbewahrung von QoE-Daten in Skype for Business Server angeben.'
ms.openlocfilehash: 7960f7c89ce16a7105cf24cc89d5efd660fe260b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855522"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Ändern von Quality of Experience-Einstellungen in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Aufbewahrung von QoE-Daten in Skype for Business Server angeben.

In der Standardeinstellung werden QoE-Daten (Quality of Experience, Erlebnisqualität) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **QoE-Daten** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie QoE deaktivieren, werden auch Daten gelöscht, die bei aktivierter QoE-Datenerfassung aufgezeichnet wurden.

> [!NOTE]
> Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Überwachungsberichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen.

Das nachfolgende Verfahren beschreibt, wie Sie die Löscheinstellungen für QoE-Daten konfigurieren.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>So geben Sie die Aufbewahrung von QoE-Daten mithilfe Skype for Business Server Systemsteuerung an

1.  Melden Sie sich am Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Mitglied der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4. Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5. Wählen Sie die Option **Löschen für QoE aktivieren** aus, um die Löschung zu aktivieren.

6. Wählen Sie unter **Maximale Speicherdauer für die QuE-Aufzeichnung (Tage)** die maximale Anzahl von Tagen aus, für die QoE-Daten gespeichert werden sollen.

7. Klicken Sie auf **Commit**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Angeben der QoE-Aufbewahrung mithilfe Windows PowerShell Cmdlets

Sie können QoE-Aufbewahrungseinstellungen mithilfe von Windows PowerShell und dem Cmdlet **"Set-CsQoEConfiguration"** erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Ausführliche Informationen zur Verwendung von Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie unter [Microsoft Lync Remote PowerShell Administration.](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/) Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>So geben Sie die QoE-Aufbewahrung für einen speziellen Standort an

- Dieser Befehl ermöglicht das Löschen von QoE-Daten für den Standort Redmond. Zudem wird damit für die QoE-Daten eine Aufbewahrungsdauer von 20 Tagen konfiguriert.

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>So geben Sie die QoE-Aufbewahrung für mehrere Standorte an

- Mithilfe dieses Befehls wird die QoE-Aufbewahrung für alle QoE-Konfigurationseinstellungen konfiguriert, die in einer Organisation verwendet werden.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsQoEConfiguration".](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>Siehe auch

[Bereitstellen des Monitoring Servers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)