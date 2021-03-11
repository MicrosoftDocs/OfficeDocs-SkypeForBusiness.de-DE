---
title: Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 91089761-cb87-4119-885b-3713840dd9f7
ms.tgt.pltfrm: cloud
audience: admin
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Erfahren Sie, wie Sie Eine Geschäftstelefonnummer für Ihre Teams-Benutzer zuweisen, ändern oder entfernen, damit sich externe Unternehmen und Kunden ein- und auswechseln können.
ms.openlocfilehash: e606885aee1e87dfdfc9b36a5247eedba225a185
ms.sourcegitcommit: 91fbc7c9cd43c2a5b7e6dfedf2388939f2f77d57
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2021
ms.locfileid: "50589619"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer (Anrufpläne)

Wenn Sie Anrufpläne einrichten, weisen Sie Ihren Benutzern Telefonnummern zu. In Microsoft Teams wird die von Ihnen zugewiesene Telefonnummer aufgelistet, wenn ein Benutzer auf Anrufe **klickt.** Anweisungen zum Zuweisen, Ändern oder Entfernen einer Telefonnummer von einem Benutzer in einem Direct Routing-Szenario finden Sie unter Aktivieren von Benutzern für Direct [Routing, Voicemail und Voicemail.](https://docs.microsoft.com/microsoftteams/direct-routing-enable-users)

![Telefonnummer des Benutzers, die in Teams angezeigt wird.](media/teams-phone-number.png)

Wenn Sie Benutzer so einrichten, dass sie Telefonanrufe machen und empfangen können, müssen Sie zuerst das Microsoft Teams Admin Center verwenden und eine Telefonnummer zuweisen. Sie können die Telefonnummer bei Bedarf ändern oder entfernen.
  
Informationen dazu, wie Sie Anrufpläne in Teams erhalten und wie viel sie kosten, finden Sie unter [Teams-Add-On-Lizenzierung.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
  
> [!NOTE]
> Eine Möglichkeit, um festzustellen, ob einem Benutzer eine Lizenz zugewiesen wurde, besteht im Microsoft Teams Admin Center > **Benutzer.** Wenn eine Lizenz zugewiesen ist, wird sie auf der Seite angezeigt.  Sie können auch das Microsoft 365 Admin Center verwenden.
  
## <a name="assign-a-phone-number-to-a-user"></a>Zuweisen einer Telefonnummer zu einem Benutzer
 
![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**
    
1. Klicken Sie im linken Navigationsbereich auf **Voice**  >  **phone numbers**.
2. Wählen Sie **auf der Seite** Telefonnummern in der Liste eine nicht zugewiesene Nummer aus, und klicken Sie dann auf **Bearbeiten.**  
3. Suchen Sie **im** Bereich Bearbeiten unter **Zugewiesen an** nach dem Benutzer nach Anzeigename oder Benutzername, und klicken Sie dann auf **Zuweisen.**
4. Um den zugeordneten Notfallstandort zuzuordnen oder zu ändern, suchen Sie unter Notfallstandort nach dem Ort, und wählen Sie dann den Ort aus.
5. Je nachdem, ob Sie dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie E-Mail-Benutzer mit **Telefonnummerninformationen.** Standardmäßig ist dies aktiviert. 
6. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

    > [!NOTE]
    > Because of the latency between Microsoft 365 or Office 365 and Teams, it can take up to 24 hours for users to be enabled. If the phone number isn't assigned correctly after 24 hours, [contact support for business products - Admin Help](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products). We're here to help!

  
## <a name="change-a-phone-number-for-a-user"></a>Ändern einer Telefonnummer für einen Benutzer
 
![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**
    
1. Klicken Sie in der linken Navigationsleiste auf **Benutzer,** suchen Sie den benutzer, und doppelklicken Sie darauf, klicken Sie auf Konto **,** und notieren Sie sich dann unter Allgemeine Informationen die Telefonnummer, die dem Benutzer zugewiesen ist.
2. Klicken Sie im linken Navigationsbereich auf **Voice**  >  **phone numbers**.
3. Wählen Sie **auf der Seite** Telefonnummern die Nummer aus, die Sie in Schritt 1 identifiziert haben, und klicken Sie dann auf **Bearbeiten.**  
4. Klicken Sie **im** Bereich Bearbeiten unter **Zugewiesen an** auf **das X,** um den Benutzer zu entfernen.
5. Klicken Sie auf **Speichern**.
6. Wählen Sie **auf der Seite** Telefonnummern in der Liste eine nicht zugewiesene Nummer aus, und klicken Sie dann auf **Bearbeiten.**  
7. Suchen Sie **im** Bereich Bearbeiten unter **Zugewiesen an** nach dem Benutzer nach Anzeigename oder Benutzername, und klicken Sie dann auf **Zuweisen.**
8. Um den zugeordneten Notfallstandort zuzuordnen oder zu ändern, suchen Sie unter Notfallstandort nach dem Ort, und wählen Sie dann den Ort aus.
9. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="remove-a-phone-number-from-a-user"></a>Entfernen einer Telefonnummer von einem Benutzer
 
![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer,** suchen Sie den benutzer, und doppelklicken Sie darauf, klicken Sie auf Konto **,** und notieren Sie sich dann unter Allgemeine Informationen die Telefonnummer, die dem Benutzer zugewiesen ist.
2. Klicken Sie im linken Navigationsbereich auf **Voice**  >  **phone numbers**.
3. Wählen Sie **auf der Seite** Telefonnummern die Nummer aus, die Sie in Schritt 2 identifiziert haben, und klicken Sie dann auf **Bearbeiten.**  
4. Klicken Sie **im** Bereich Bearbeiten unter **Zugewiesen an** auf **das X,** um den Benutzer zu entfernen.
5. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps).

## <a name="related-topics"></a>Verwandte Themen

[Was ist Adressvalidierung?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Haftungsausschlussetikett für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

[Anrufpläne für Microsoft 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365)
