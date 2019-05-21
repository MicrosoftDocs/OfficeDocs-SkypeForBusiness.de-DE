---
title: Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Beibehaltung von QoE-Daten in Skype for Business Server angeben.'
ms.openlocfilehash: 89e20b18aa285bd4ee61df12c822e487dd6b37a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280005"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a>Ändern der Einstellungen für die Qualität der Benutzerfreundlichkeit in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie die Aufbewahrung von QoE-Daten in Skype for Business Server angeben.

In der Standardeinstellung werden QoE-Daten (Quality of Experience, Erlebnisqualität) nach 60 Tagen gelöscht. Sie können die Einstellungen auf der Seite **QoE-Daten** verwenden, um die Daten für einen längeren oder kürzeren Zeitraum zu speichern. Wenn Sie QoE deaktivieren, werden auch Daten gelöscht, die bei aktivierter QoE-Datenerfassung aufgezeichnet wurden.

> [!NOTE]
> Sie sollten die Aufzeichnung von Kommunikationsdatensätzen (KDS) und QoE-Daten so konfigurieren, dass Daten für die gleiche Anzahl von Tagen gespeichert werden. Die Berichte zu den aufgezeichneten Kommunikationsdatensätzen (KDS), verfügbar auf der Webseite für Überwachungsberichte, umfassen KDS- und QoE-Informationen zu jedem Anruf. Wenn die Zeit bis zum Löschen für KDS und QoE abweicht, umfassen einige Anrufe möglicherweise nur KDS-Daten, während andere ausschließlich QoE-Daten aufweisen.

Das nachfolgende Verfahren beschreibt, wie Sie die Löscheinstellungen für QoE-Daten konfigurieren.

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a>So legen Sie die Beibehaltung von QoE-Daten mithilfe der Skype for Business Server-Systemsteuerung fest

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter **Delegate Setup Permissions**.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um das Skype for Business Server Control Panel zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.

4. Klicken Sie auf der Seite **QoE-Daten** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Bearbeiten** und anschließend auf **Details anzeigen**.

5. Wählen Sie die Option **Löschen für QoE aktivieren** aus, um die Löschung zu aktivieren.

6. Wählen Sie unter **Maximale Speicherdauer für die QuE-Aufzeichnung (Tage)** die maximale Anzahl von Tagen aus, für die QoE-Daten gespeichert werden sollen.

7. Klicken Sie auf **Commit ausführen**.

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a>Angeben der QoE-Aufbewahrung mithilfe von Windows PowerShell-Cmdlets

Sie können QoE-Aufbewahrungseinstellungen mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsQoEConfiguration** " erstellen. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausführen. Details zur Verwendung der Remote-Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blog-Artikel ["schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Vorgang ist in Skype for Business Server identisch.

### <a name="to-specify-qoe-retention-for-a-specific-location"></a>So geben Sie die QoE-Aufbewahrung für einen speziellen Standort an

- Dieser Befehl ermöglicht das Löschen von QoE-Daten für den Standort Redmond. Zudem wird damit für die QoE-Daten eine Aufbewahrungsdauer von 20 Tagen konfiguriert.

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a>So geben Sie die QoE-Aufbewahrung für mehrere Standorte an

- Mit diesem Befehl wird die Beibehaltung von QoE-Daten für alle in einer Organisation verwendeten QoE-Konfigurationseinstellungen konfiguriert.

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [Satz-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) ".

## <a name="see-also"></a>Siehe auch

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
