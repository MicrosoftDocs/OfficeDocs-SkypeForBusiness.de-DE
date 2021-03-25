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
description: Erfahren Sie, wie Sie die Konferenz-ID eines Benutzers in Microsoft Teams zurücksetzen und Links zu Tools für Besprechungsupdates und Migration erhalten.
ms.openlocfilehash: edccab5da883c1707ade75519e96615ed3524bf3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117643"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Zurücksetzen einer Konferenzkennung für einen Benutzer in Microsoft Teams

Eine dynamische Konferenz-ID ist am Ende der Besprechungseinladungen zusammen mit den Einwahltelefonnummern enthalten, die von Anrufern zum Einwählen in eine Besprechung verwendet werden können. Wenn der Benutzer die Telefonnummer wählt, fordert die automatische Telefonkonferenz für die Besprechung den Anrufer auf, diese Konferenz-ID ein eingeben, damit er an der Besprechung teilnehmen kann.
  
> [!NOTE]
> Konferenz-IDs werden automatisch generiert, liegen zwischen 7 und 9 Ziffern und werden festgelegt, wenn Sie Audiokonferenzen für einen Benutzer aktivieren. **Statische Konferenz-IDs werden nicht unterstützt.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Zurücksetzen der Konferenz-ID für einen Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie im linken Navigationsbereich auf **Benutzer**, und wählen Sie dann den Benutzer aus der Liste der verfügbaren Benutzer aus.

2. Klicken Sie **auf Bearbeiten**.

3. Klicken **Sie unter Audiokonferenzen** auf **Konferenz-ID zurücksetzen.**

2. Klicken Sie **im Fenster Konferenz-ID** zurücksetzen auf **Zurücksetzen.** Eine Konferenz-ID wird automatisch erstellt und eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Standardmäßig werden E-Mails an Benutzer gesendet, dies kann jedoch deaktiviert werden.   

    
> [!NOTE]
> Nachdem Sie die Konferenz-ID zurückgesetzt haben, wird eine E-Mail mit der neuen Konferenz-ID an den Benutzer gesendet. Diese E-Mail wird an die primäre E-Mail-Adresse gesendet, in vielen Fällen an ihr Microsoft 365- oder Office 365-Postfach. Die E-Mail enthält die neue Konferenz-ID, die Standardeinwahltelefonnummer(n) und Anweisungen zum Aktualisieren vorhandener Besprechungen. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Was sollte ich noch wissen?

- Sie können alle Konferenzinformationen in einer E-Mail, die konferenz-ID und Einwahltelefonnummern enthält, an den Benutzer senden, indem Sie im Abschnitt **Audiokonferenzen** auf Konferenzinformationen **per** E-Mail senden klicken. Die PIN wird nicht gesendet.
    
- Vom Dienst "Teams" wird eine 7-9-stellige Konferenz-ID erstellt. Sie können die Länge nicht ändern.
    
- Nach dem Zurücksetzen wird die neue Konferenz-ID unter **Konferenz-ID** aufgeführt.
    
- Nachdem eine neue Konferenz-ID generiert wurde, können Anrufer die alte Konferenz-ID nicht mehr verwenden. Sie sollten Benutzer benachrichtigen, dass sie ihre angesetzten Besprechungseinladungen neu planen, damit die neue Konferenz-ID den Einladungen hinzugefügt wird. 

## <a name="want-to-know-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 über einen einzigen Verwaltungspunkt verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Verwandte Themen

[Zurücksetzen der Audiokonferenz-PIN](reset-the-audio-conferencing-pin-in-teams.md)