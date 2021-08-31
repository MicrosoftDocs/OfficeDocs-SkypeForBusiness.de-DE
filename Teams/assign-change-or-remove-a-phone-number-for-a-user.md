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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Erfahren Sie, wie Sie Ihren Teams-Benutzern eine geschäftliche Telefonnummer zuweisen oder diese ändern oder entfernen können, damit Unternehmen und Kunden von außerhalb anrufen können.
ms.openlocfilehash: 44254c8d8c8886e72b699c3890017a2b817cd135
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727504"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user-calling-plans"></a>Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer (Anrufpläne)

Wenn Sie Anrufpläne einrichten, weisen Sie Ihren Benutzern Telefonnummern zu. In Microsoft Teams wird die von Ihnen zugewiesene Telefonnummer aufgelistet, wenn ein Benutzer auf **Anrufe** klickt. Anweisungen zum Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer in einem Direct Routing-Szenario finden Sie unter [Aktivieren von Benutzern für Direct Routing, Sprache und Voicemail](./direct-routing-enable-users.md).

![Telefonnummer des Benutzers, die in Microsoft Teams angezeigt wird.](media/teams-phone-number.png)

Wenn Sie Benutzer einrichten, damit sie Anrufe tätigen und empfangen können, müssen Sie zuerst das Microsoft Teams Admin Center verwenden und eine Telefonnummer zuweisen. Falls notwendig können Sie Telefonnummer ändern oder entfernen.
  
Wenn Sie wissen möchten, wie Sie Anrufpläne in Teams erhalten und was diese kosten, lesen Sie [Add-On-Lizenzierung für Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).
  
> [!NOTE]
> Eine Möglichkeit, um festzustellen, ob einem Benutzer eine Lizenz zugewiesen wurde, besteht darin, im Microsoft Teams Admin Center **Benutzer** aufzurufen. Wenn eine Lizenz zugewiesen ist, wird es auf der Seite angezeigt.  Sie können auch das Microsoft 365 Admin Center verwenden.
  
## <a name="assign-a-phone-number-to-a-user"></a>Einem Benutzer eine Telefonnummer zuweisen
 
![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**
    
1. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.
2. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  
3. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.
4. Um den zugehörigen Notfallstandort zuzuweisen oder zu ändern, suchen Sie unter **Notfallstandort** nach dem Standort und wählen Sie ihn aus.
5. Je nachdem, ob Sie dem Benutzer eine E-Mail mit seinen Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie **Dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden**. Standardmäßig ist dies aktiviert. 
6. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

> [!NOTE]
> Aufgrund der Latenz zwischen Microsoft 365 oder Office 365 und Teams kann die Aktivierung von Benutzern bis zu 24 Stunden dauern. Wenn die Telefonnummer nach 24 Stunden nicht ordnungsgemäß zugewiesen wurde, wenden Sie sich an den Support für Business-Produkte [– Administratorhilfe](/microsoft-365/admin/contact-support-for-business-products). Wir helfen Ihnen gerne weiter!

  
## <a name="change-a-phone-number-for-a-user"></a>Ändern der Telefonnummer für einen Benutzer
 
![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**
    
1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen und doppelklicken Sie den gewünschten Benutzer, klicken Sie auf **Konto** und dann erstellen Sie unter **Allgemeine Informationen** eine Notiz mit der dem Benutzer zugewiesenen Telefonnummer.
2. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.
3. Wählen Sie auf der Seite **Telefonnummern** die im Schritt 1 identifizierte Nummer aus, und klicken Sie dann auf **Bearbeiten**.  
4. Klicken Sie im Bereich **Bearbeiten** unter **Zugewiesen zu** auf **X**, um den Benutzer zu entfernen.
5. Klicken Sie auf **Speichern**.
6. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  
7. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.
8. Um den zugehörigen Notfallstandort zuzuweisen oder zu ändern, suchen Sie unter **Notfallstandort** nach dem Standort und wählen Sie ihn aus.
9. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="remove-a-phone-number-from-a-user"></a>Entfernen einer Telefonnummer von einem Benutzer
 
![Ein Symbol mit dem Microsoft Teams Logo.](media/teams-logo-30x30.png) **Verwenden des Microsoft Teams Admin Centers**

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen und doppelklicken Sie den gewünschten Benutzer, klicken Sie auf **Konto** und dann erstellen Sie unter **Allgemeine Informationen** eine Notiz mit der dem Benutzer zugewiesenen Telefonnummer.
2. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.
3. Wählen Sie auf der Seite **Telefonnummern** die im Schritt 2 identifizierte Nummer aus, und klicken Sie dann auf **Bearbeiten**.  
4. Klicken Sie im Bereich **Bearbeiten** unter **Zugewiesen zu** auf **X**, um den Benutzer zu entfernen.
5. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="related-topics"></a>Verwandte Themen

[Was ist die Adressprüfung?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser)

[Anrufpläne für Microsoft 365](./calling-plans-for-office-365.md)
