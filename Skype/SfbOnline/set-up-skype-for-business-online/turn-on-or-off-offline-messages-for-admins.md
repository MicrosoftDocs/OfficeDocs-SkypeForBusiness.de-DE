---
title: Offline-Nachrichten für Administratoren ein- oder ausschalten
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Erfahren Sie, wie Sie Skype for Business-Chatnachrichten senden, auch wenn Ihre Kontakte nicht mit PowerShell angemeldet sind.
ms.openlocfilehash: ec5aad56ef7557c9b7854c6844d65ff3799d1d1c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568755"
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Offline-Nachrichten für Administratoren ein- oder ausschalten

Sie können Skype for Business-Chatnachrichten an Ihre Kontakte senden, selbst wenn sie nicht angemeldet sind. Mit dieser Funktion informieren Sie Ihre Kontakte, dass Sie versucht haben, sie zu erreichen. Sie müssen nicht warten, bis jemand online ist, um eine Nachricht zu senden.

Wichtige Informationen zu Offline-Nachrichten:

- Offline-Nachrichten werden nicht im Postfach des Benutzers archiviert.

- Offlinenachrichten werden an das Postfach des Benutzers gesendet, und der Benutzer wird benachrichtigt, wenn er sich bei Skype for Business anmeldet.

- Falls der Status des Nachrichtenempfängers **Nicht stören** oder **Hält Präsentation** lautet, erhält er eine Benachrichtigung über die verpasste Nachricht, die über seinen Skype for Business-Client gesendet wird.

Weitere Informationen finden Sie unter [Offline-Messaging in Skype for Business verwenden](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).

## <a name="to-get-you-started"></a>Erste Schritte

> [!NOTE]
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls. Wenn Sie die neueste öffentliche Version von Teams PowerShell verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.
1. Installieren Sie [das Teams PowerShell-Modul.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
    
2. Öffnen Sie eine Windows PowerShell Eingabeaufforderung, und führen Sie die folgenden Befehle aus: 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
Weitere Informationen zum Starten von Windows PowerShell finden Sie unter Herstellen einer Verbindung mit allen [Office 365-Diensten in](https://technet.microsoft.com/library/dn568015.aspx) einem einzigen Windows PowerShell-Fenster oder Einrichten Ihres Computers [für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

## <a name="turning-on-or-off-offline-im"></a>Die Offline-Chatfunktion ein- oder ausschalten

> [!NOTE]
> Offlinenachrichten sind **nur** in der aktuellen Klick-und-Los-Version des Skype for Business-Clients verfügbar. Sie sind nicht verfügbar, wenn eine ältere Klick-und-Los-Version von Skype for Business verwendet wird oder der Skype for Business-Client über eine MSI-Datei installiert wurde.

Um das Senden von Offlinenachrichten für Benutzer in Ihrer Organisation zu aktivieren oder zu deaktivieren, legen Sie  _EnableIMAutoArchiving_ auf `True` oder `False` fest. Standardmäßig ist dies auf `True` festgelegt.

Um die Funktion zu deaktivieren, verwenden Sie das **Set-CsClientPolicy** -Cmdlet, und führen Sie den folgenden Befehl aus:

```PowerShell
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Um das Senden von Offlinenachrichten für einen Benutzer zu aktivieren oder zu deaktivieren, legen Sie  _EnableIMAutoArchiving_ auf `True` oder `False` fest. Standardmäßig ist diese Option auf `True` festgelegt. Sie können eine vorhandene Richtlinie verwenden oder eine wie im folgenden Beispiel erstellen.


  ```PowerShell
  New-CsClientPolicy -Identity OfflineIM
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

- Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 und Skype for Business Online über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:

  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Sechs Gründe, warum Sie microsoft Windows PowerShell Office 365 oder Office 365 verwalten möchten](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:

  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)
