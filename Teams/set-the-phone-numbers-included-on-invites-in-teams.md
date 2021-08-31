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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Führen Sie die folgenden Schritte aus, um eine Standardtelefonnummer für Anrufer zu erstellen, die an einer Besprechung Microsoft Teams teilnehmen können.
ms.openlocfilehash: 4c740147e551dade443852a98c5cdafac047815f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732714"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Festlegen der in Einladungen in Microsoft Teams enthaltenen Telefonnummern

Mit Audiokonferenzen in Microsoft 365 und Office 365 können Benutzer in Ihrer Organisation Microsoft Teams-Besprechungen erstellen und benutzern anschließend die telefonische Einwahl in diese Besprechungen ermöglichen.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Erstmalige Zuweisung von Telefonnummern, die in den Besprechungs-Einladungen für neue Benutzer enthalten sind

Die Telefonnummern, die in den Besprechungseinrufen von Benutzern enthalten sind, die für Audiokonferenzen aktiviert sind, sind durch die gebührenpflichtige Standardtelefonnummer für Konferenzen und die Einstellungen des Benutzers für die gebührenfreie Standardtelefonnummer für Konferenzen definiert. Jede Einstellung gibt an, welche gebührenpflichtige und gebührenfreie Nummer in der Besprechungseinstellung eines bestimmten Benutzers enthalten sein soll. Wie oben erwähnt, enthält jede Besprechungs-Einladung eine gebührenpflichtige Nummer, eine optionale gebührenfreie Nummer und einen Link, über den eine vollständige Liste aller Einwahltelefonnummern geöffnet wird, die für die Teilnahme an einer bestimmten Besprechung verwendet werden können.

Für einen neuen Benutzer werden die gebührenpflichtigen Standardkonferenznummern basierend auf dem Verwendungsstandort zugewiesen, der im Microsoft 365-Verwaltungscenter des Benutzers festgelegt wird, wenn der Benutzer für den Audiokonferenzdienst aktiviert ist. Wenn die Konferenzbrücke eine gebührenpflichtige Nummer enthält, die dem Land des Benutzers entspricht, wird diese Nummer automatisch als gebührenpflichtige Standardnummer des Benutzers zugewiesen. Wenn es keine Telefonnummer gibt, wird die Nummer, die als gebührenpflichtige Standardnummer der Konferenzbrücke definiert ist, als gebührenpflichtige Standardnummer des Benutzers zugewiesen.  

Nachdem der Benutzer für den Audiokonferenzdienst aktiviert wurde, können die gebührenpflichtigen und gebührenfreien Standardtelefonnummern des Benutzers jederzeit vom Mandantenadministrator von den ursprünglichen Werten geändert werden.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Festlegen oder Ändern der Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder -benutzer

![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

Sie müssen ein Teams-Dienstadministrator sein, um diese Änderungen machen zu können. Informationen zum Erhalten von Administratorrollen und -Berechtigungen finden Sie unter [Teams-Administratorrollen verwenden, um Teams zu verwalten](./using-admin-roles.md).

1. Melden Sie sich beim Microsoft Teams Admin Center an.

2. Klicken Sie im linken Navigationsbereich auf **Benutzer**.

    ![Zeigt die Auswahl von Benutzern im Microsoft Teams Admin Center.](media/Admin-users.png)

3. Klicken Sie in der Liste der verfügbaren Benutzer auf den Benutzernamen.

4. Klicken Sie **neben Audiokonferenz** auf **Bearbeiten**.

    ![Klicken Sie neben Audiokonferenzen auf Bearbeiten.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Geben Sie **in den Feldern** **Gebührenpflichtige** Nummer oder Gebührenfreie Nummer die Nummern für den Benutzer ein.

> [!IMPORTANT]
> Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen Besprechungsserien und zukünftige Microsoft Teams müssen aktualisiert und an die Teilnehmer gesendet werden.

## <a name="want-to-use-windows-powershell"></a>Verwenden von Windows PowerShell

Bei Windows PowerShell dreht sich alles um das Verwalten von Benutzern und Funktionen, die Benutzer verwenden oder nicht verwenden können. Mit Windows PowerShell können Sie Microsoft 365 oder Office 365 mithilfe eines einzigen Administrationspunkts verwalten, der Ihre tägliche Arbeit vereinfachen kann, wenn Sie mehrere Aufgaben ausführen müssen. Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:

- [Warum Sie Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Wenn Sie die Standardtelefonnummer für Audiokonferenzen für einen Besprechungsorganisator oder Benutzer mit [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps)festlegen oder ändern möchten, legen Sie die Parameter oder des **`ServiceNumber`** **`TollFreeServiceNumber`** [Cmdlets Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) auf eine der verfügbaren Nummern fest.

## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Ändern der Telefonnummern in Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
