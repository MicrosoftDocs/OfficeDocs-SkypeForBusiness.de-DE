---
title: Festlegen der in Einladungen enthaltenen Telefonnummern
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Führen Sie die folgenden Schritte aus, um eine Standardtelefonnummer für Anrufer zu erstellen, die an einer Microsoft Teams-Besprechung teilnehmen können.
ms.openlocfilehash: 476075ccf5e261695564b78ec084605af9e6898c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117173"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Audiokonferenzen in Microsoft 365 und Office 365 ermöglichen Benutzern in Ihrer Organisation, Microsoft Teams-Besprechungen zu erstellen und benutzern dann die Einwahl in diese Besprechungen über ein Telefon zu ermöglichen.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Erste Zuweisung von Telefonnummern, die in den Besprechungs-Einladungen für neue Benutzer enthalten sind

Die Telefonnummern, die in die Besprechungseinläge von Benutzern einbezogen werden, die für Audiokonferenzen aktiviert sind, werden durch die standardmäßige gebührenpflichtige Konferenznummer und die Standardeinstellungen der gebührenpflichtigen Konferenznummer des Benutzers definiert. Jede Einstellung gibt an, welche gebührenpflichtige und gebührenfreie Nummer in die Besprechungseinläge eines bestimmten Benutzers einbezogen wird. Wie oben erwähnt, enthält jede Besprechungsein einladung eine gebührenpflichtige Nummer, eine optionale gebührenfreie Nummer und einen Link, über den die vollständige Liste aller Einwahltelefonnummern geöffnet wird, die für die Teilnahme an einer bestimmten Besprechung verwendet werden können.

Für einen neuen Benutzer werden die Standardkonferenzgebührennummern basierend auf dem Nutzungsspeicherort zugewiesen, der im Microsoft 365-Verwaltungscenter des Benutzers festgelegt ist, wenn der Benutzer für den Audiokonferenzdienst aktiviert ist. Wenn die Konferenzbrücke eine Gebührennummer enthält, die dem Land des Benutzers entspricht, wird diese Nummer automatisch als Standardmautnummer des Benutzers zugewiesen. Wenn es keine gibt, wird die Nummer, die als Standardmautnummer der Konferenzbrücke definiert ist, als Standardmautnummer des Benutzers zugewiesen.  

Sobald der Benutzer für den Audiokonferenzdienst aktiviert ist, können die standardmäßigen gebührenpflichtigen und gebührenfreien Telefonnummern des Benutzers jederzeit vom Mandantenadministrator von den ursprünglichen Werten geändert werden.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer

![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Klicken Sie im linken Navigationsbereich auf **Benutzer**.

    ![Zeigt die Auswahl von Benutzern im Microsoft Teams Admin Center an.](media/Admin-users.png)

3. Klicken Sie in der Liste der verfügbaren Benutzer auf den Benutzernamen.

4. Klicken Sie **neben Audiokonferenzen** auf **Bearbeiten.**

    ![Klicken Sie neben Audiokonferenz auf Bearbeiten.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Verwenden Sie **die Felder** **"Gebührenfreie Nummer" oder "Gebührenfreie** Nummer", um die Nummern für den Benutzer ein eingeben zu können.

> [!IMPORTANT]
> Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen wiederkehrende und zukünftige Microsoft Teams-Besprechungen aktualisiert und an Teilnehmer gesendet werden.

## <a name="want-to-use-windows-powershell"></a>Verwenden von Windows PowerShell

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzelnen Verwaltungspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Weitere Informationen zu Windows PowerShell finden Sie in der [PowerShell-Referenz für Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)