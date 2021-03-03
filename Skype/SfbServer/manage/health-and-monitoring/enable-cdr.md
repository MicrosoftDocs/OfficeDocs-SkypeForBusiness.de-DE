---
title: Aktivieren der Aufzeichnung von Anrufdetails in Skype for Business Server
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
ms.assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie Aufzeichnungen von Anrufdetails (Call Detail Recording, CDR) in Skype for Business Server aktivieren.'
ms.openlocfilehash: 48d21be6d377df24e859c3ffa6bb8b7858076d29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816885"
---
# <a name="enable-call-detail-recording-in-skype-for-business-server"></a>Aktivieren der Aufzeichnung von Anrufdetails in Skype for Business Server

**Zusammenfassung:** Erfahren Sie, wie Sie Aufzeichnungen von Anrufdetailaufzeichnungen (Call Detail Recording, CDR) in Skype for Business Server aktivieren.

Bei der Aufzeichnung von Kommunikationsdatensätzen werden Nutzungs- und Diagnoseinformationen über Peer-zu-Peer-Aktivitäten aufgezeichnet, z. B. Chat, VoIP-Anrufe (Voice over Internet Protocol), Anwendungsfreigabe, Dateiübertragung und Besprechungen. Anhand der Nutzungsdaten kann die Rendite berechnet werden, und die Diagnosedaten können zur Problembehandlung bei Peer-zu-Peer-Aktivitäten und Besprechungen eingesetzt werden.

Verwenden Sie das folgende Verfahren, um die Aufzeichnung von Kommunikationsdatensätzen (KDS) in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.

> [!NOTE]
> Zur Aktivierung von KDS müssen Sie die Überwachung und eine Überwachungsdatenbank konfigurieren. Ausführliche Informationen finden Sie unter [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-cdr-with-skype-for-business-server-control-panel"></a>So aktivieren Sie die CdR mit der Skype for Business Server-Systemsteuerung

1.  Melden Sie sich über ein Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsServerAdministrator" oder "CsAdministrator" zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie Skype for Business Server bereitgestellt haben.

2. Öffnen Sie ein Browserfenster, und geben Sie dann die Admin-URL ein, um die Skype for Business Server-Systemsteuerung zu öffnen.

3. Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.

4. Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Aktion** und anschließend auf **KDS aktivieren**.

    > [!NOTE]
    > KDS ist standardmäßig aktiviert.

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a>Aktivieren von CDR mithilfe Windows PowerShell Cmdlets

Sie können KDS mithilfe Windows PowerShell und des **Cmdlets "Set-CsCdrConfiguration"** aktivieren. Sie können dieses Cmdlet entweder über die Skype for Business Server-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell. Weitere Informationen zur Verwendung von remote Windows PowerShell zum Herstellen einer Verbindung mit Skype for Business Server finden Sie im Blogartikel ["Schnellstart: Verwalten von Microsoft Lync Server 2010 mithilfe von Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). Der Prozess ist in Skype for Business Server identisch.

### <a name="to-enable-cdr-for-a-single-location"></a>So aktivieren Sie KDS für einen einzelnen Standort

 Sie können KDS aktivieren, indem Sie den Parameter EnableCDR auf True ($True) setzen.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True
  ```

### <a name="to-disable-cdr-for-a-single-location"></a>So deaktivieren Sie KDS für einen einzelnen Standort

 Sie können KDS deaktivieren, indem Sie den Parameter EnableCDR auf False ($False) setzen. Durch das Deaktivieren von CDR wird die Überwachung nicht deinstalliert. Es hält die Erfassung und Speicherung von CDR-Daten an.

  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a>So verwenden Sie einen einzelnen Befehl zum Aktivieren von KDS an mehreren Standorten

 Mit diesem Befehl wird KDS für alle derzeit in der Organisation verwendeten KDS-Einstellungen aktiviert.

  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration -EnableCDR $True
  ```

Weitere Informationen finden Sie im Hilfethema zum [Cmdlet "Set-CsCdrConfiguration".](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)

## <a name="see-also"></a>Siehe auch

[Planen der Überwachung](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Bereitstellen des Monitoring Servers](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)
