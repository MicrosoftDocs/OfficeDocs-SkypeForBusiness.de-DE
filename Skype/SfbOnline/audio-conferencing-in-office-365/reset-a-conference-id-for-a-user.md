---
title: Zurücksetzen einer Konferenz-ID für einen Benutzer in Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Erfahren Sie die Schritte zum Zurücksetzen der Konferenz-ID eines Benutzers in Skype for Business Online sowie Links zu Tools für Besprechungsaktualisierungen und -migration. '
ms.openlocfilehash: b2f816cf423a25016a67176d6b1479f585ee14e9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58586133"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Zurücksetzen einer Konferenz-ID für einen Benutzer in Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]
> Informationen zum Zurücksetzen des Konferenz-ID in Microsoft Teams, finden Sie unter [Zurücksetzen eine Konferenz-ID für einen Benutzer in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Am Ende der Besprechungseinladungen finden Sie eine dynamische Konferenz-ID sowie die Einwahltelefonnummern, mit deren Hilfe sich Anrufer in eine Besprechung einwählen können. Wenn der Benutzer die Telefonnummer wählt, wird der Anrufer von der automatischen Telefonkonferenz zur Eingabe dieser Konferenz-ID eingeladen, damit er an der Besprechung teilnehmen kann.
  
> [!NOTE]
> Wenn Microsoft Ihr Konferenzanbieter ist, werden die Konferenz-IDs Ihrer Benutzer auf Nur dynamisch festgelegt. Dies kann nicht geändert werden. Konferenz-IDs werden automatisch nur für Skype for Business-Benutzer festgelegt, die für Audiokonferenzen aktiviert sind. 

## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenz-ID für einen Benutzer
   
1. Klicken Sie **Skype for Business Admin Center** auf Benutzer für **Audiokonferenzen**, wählen Sie einen Benutzer aus, und klicken Sie dann im Aktionsbereich unter  >   **Konferenz-ID** auf **Zurücksetzen**.
    
2. Klicken Sie **im Fenster Konferenz-ID zurücksetzen?** auf **Ja.** Es wird automatisch eine Konferenz-ID erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Standardmäßig werden E-Mails an Benutzer gesendet, dies kann jedoch deaktiviert werden.
    
> [!NOTE]
> Nachdem Sie die Konferenz-ID zurückgesetzt haben, wird dem Benutzer eine E-Mail mit der neuen Konferenz-ID gesendet. Diese E-Mail wird an die primäre E-Mail-Adresse gesendet, in vielen Fällen an deren Microsoft 365 oder Office 365 Postfach. Die E-Mail enthält die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen zum Aktualisieren vorhandener Besprechungen mit dem Skype for Business Meeting Update Tool. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können dem Benutzer alle Konferenzinformationen per E-Mail senden, die konferenz-ID und Einwahltelefonnummern enthält, indem Sie im Aktionsbereich auf Konferenzinformationen per E-Mail senden klicken.  Die PIN wird nicht gesendet.
    
- Eine Konferenz-ID enthält sieben Ziffern, und Sie können die Länge nicht im Skype for Business Admin Center oder mithilfe von Windows PowerShell.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Die Konferenz-ID für einen Benutzer für Audiokonferenzen kann unten im Aktionsbereich unter **Audiokonferenz angezeigt** werden, wenn Sie den Benutzer auf der Seite **Benutzer** auswählen.
    
- Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. Die Benutzer können Skype for Business Besprechungstool verwenden, um ihre vorhandenen Besprechungen zu aktualisieren. Informationen zum Herunterladen, Installieren und Ausführen des Skype for Business Meeting Update Tool finden Sie unter:
    
  - [Skype for Business (Lync) Meeting Update Tool](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype for Business Online, Meeting Migration Tool (64 Bit)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype for Business Online, Meeting Migration Tool (32 Bit)](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Wenn es um Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen oder was nicht. Mit Windows PowerShell können Sie Microsoft 365, Office 365 und Skype for Business Online über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Artikeln über die Verwendung von Windows PowerShell:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
 
- Windows PowerShell hat gegenüber der ausschließlichen Verwendung des Microsoft 365 Admin Center beispielsweise, wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen, viele Vorteile in der Geschwindigkeit, Einfachheit und Produktivität. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin.md)
