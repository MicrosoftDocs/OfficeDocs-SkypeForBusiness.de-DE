---
title: Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Erfahren Sie die Schritte zum Zurücksetzen der Konferenz-ID eines Benutzers in Microsoft Teams und erhalten Sie Links zu Tools für Besprechungsaktualisierungen und -migration.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117643"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams

Am Ende der Besprechungseinladungen finden Sie eine dynamische Konferenz-ID sowie die Einwahltelefonnummern, mit deren Hilfe sich Anrufer in eine Besprechung einwählen können. Wenn der Benutzer die Telefonnummer wählt, wird der Anrufer von der automatischen Telefonkonferenz zur Eingabe dieser Konferenz-ID eingeladen, damit er an der Besprechung teilnehmen kann.
  
> [!NOTE]
> Konferenz-IDs werden automatisch generiert, liegen zwischen sieben und neun Ziffern und werden festgelegt, wenn Sie Audiokonferenzen für einen Benutzer aktivieren. **Statische Konferenz-IDs werden nicht unterstützt.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenz-ID für einen Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **auf Bearbeiten**.

3. Klicken **Sie unter Audiokonferenzen** auf **Konferenz-ID zurücksetzen**.

2. Klicken Sie **im Fenster Konferenz-ID** zurücksetzen auf **Zurücksetzen**. Es wird automatisch eine Konferenz-ID erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Standardmäßig werden E-Mails an Benutzer gesendet, dies kann jedoch deaktiviert werden.   

    
> [!NOTE]
> Nachdem Sie die Konferenz-ID zurückgesetzt haben, wird dem Benutzer eine E-Mail mit der neuen Konferenz-ID gesendet. Diese E-Mail wird an die primäre E-Mail-Adresse gesendet, in vielen Fällen an deren Microsoft 365 oder Office 365 Postfach. Die E-Mail enthält die neue Konferenz-ID, die Standardeinwahlnummer(n) und Anweisungen zum Aktualisieren vorhandener Besprechungen. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können dem Benutzer alle Konferenzinformationen per E-Mail senden, die konferenz-ID und Einwahltelefonnummern enthält, indem Sie im Abschnitt **Audiokonferenzen** auf Konferenzinformationen **per** E-Mail senden klicken. Die PIN wird nicht gesendet.
    
- Der Konferenzdienst erstellt eine 7- bis 9-stellige Konferenz-ID Teams Konferenz-ID. Sie können die Länge nicht ändern.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. 

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie ihre Microsoft 365 oder Office 365 über einen einzigen Administrationspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)