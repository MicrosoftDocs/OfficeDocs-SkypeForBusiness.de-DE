---
title: Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: davelick, roykuntz, jastark
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
ms.openlocfilehash: 5e8041ce0a8cc95549a9dc75c0c8d74cd2438e1c
ms.sourcegitcommit: b57e19e20900ff02f3196c811bf1dd1acd149c79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2021
ms.locfileid: "60579515"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer

Wenn Sie Anrufpläne oder Anbieter Verbinden, weisen Sie Ihren Benutzern Telefonnummern zu. In Microsoft Teams wird die von Ihnen zugewiesene Telefonnummer aufgelistet, wenn ein Benutzer auf **Anrufe** klickt. 

Dieser Artikel bezieht sich auf Anrufpläne und Verbinden. Informationen zum Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer in einem Direct Routing-Szenario finden Sie unter Aktivieren von Benutzern für [Direct-Routing,](./direct-routing-enable-users.md)Sprache und Voicemail.

Bevor Sie eine Nummer für einen Anrufplan- oder Verbinden Benutzer zuweisen können, müssen Sie Telefonnummern für Ihre Benutzer erhalten. Weitere Informationen finden Sie unter [Erhalten von Nummern für Anrufplanbenutzer](getting-phone-numbers-for-your-users.md) oder Einrichten von Nummern für Verbinden [Anrufer.](operator-connect-configure.md#set-up-phone-numbers)

  
> [!NOTE]
> Eine Möglichkeit, um festzustellen, ob einem Benutzer eine Lizenz zugewiesen wurde, besteht darin, im Microsoft Teams Admin Center **Benutzer** aufzurufen. Wenn eine Lizenz zugewiesen ist, wird es auf der Seite angezeigt.  Sie können auch das Microsoft 365 Admin Center verwenden.

> [!NOTE]
> Diese Notiz gilt für Kunden, die über eine Hybridbereitstellung mit einem lokalen Active Directory verfügen. Wenn Sie einem Benutzer- oder Ressourcenkonto eine Anrufplan- oder Operator-Verbinden-Telefonnummer zuweisen möchten, müssen Sie sicherstellen, dass die Telefonnummer im lokalen Active Directory entfernt und die Änderung mit Microsoft 365.
  
## <a name="assign-a-phone-number-to-a-user"></a>Einem Benutzer eine Telefonnummer zuweisen

Stellen Sie beim Zuweisen einer Telefonnummer zu einem Benutzer sicher, dass sich die Telefonnummer und der Nutzungsstandort des Benutzers im selben Land befinden.

So weisen Sie eine Nummer über das Teams Admin Center zu:
    
1. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.

2. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  

3. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.

4. Um den zugehörigen Notfallstandort zuzuweisen oder zu ändern, suchen Sie unter **Notfallstandort** nach dem Standort und wählen Sie ihn aus.

   > [!NOTE]
   > Wenn Sie Dem Netzbetreibern und Benutzern Nummern Verbinden, können Sie den zugeordneten Notfallstandort möglicherweise zuweisen oder ändern. Diese Funktionalität hängt von Ihrem Operator ab. Wenden Sie sich an Ihren Netzbetreiber, um weitere Informationen zu erhalten.

5. Je nachdem, ob Sie dem Benutzer eine E-Mail mit seinen Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie **Dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden**. Standardmäßig ist dies aktiviert. 

6. Klicken Sie auf **Speichern**.

Verwenden Sie zum Zuweisen von Nummern mithilfe von PowerShell das [Cmdlet Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser) wie folgt:


''PowerShell Set-CsOnlineVoiceUser -Identity <user>   -TelephoneNumber <phone number> 
```

For example:

```PowerShell
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

> [!NOTE]
> Aufgrund der Latenz zwischen Microsoft 365 und Teams kann die Aktivierung von Benutzern bis zu 24 Stunden dauern. Wenn die Telefonnummer nach 24 Stunden nicht ordnungsgemäß zugewiesen wurde, lesen Sie Telefon [Number Service Center.](https://pstnsd.powerappsportals.com/) 

  
## <a name="change-a-phone-number-for-a-user"></a>Ändern der Telefonnummer für einen Benutzer

So ändern Sie eine Telefonnummer für einen Benutzer mithilfe des Teams Admin Centers:
    
1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen und doppelklicken Sie den gewünschten Benutzer, klicken Sie auf **Konto** und dann erstellen Sie unter **Allgemeine Informationen** eine Notiz mit der dem Benutzer zugewiesenen Telefonnummer.

2. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.

3. Wählen Sie auf der Seite **Telefonnummern** die im Schritt 1 identifizierte Nummer aus, und klicken Sie dann auf **Bearbeiten**.  

4. Klicken Sie im Bereich **Bearbeiten** unter **Zugewiesen zu** auf **X**, um den Benutzer zu entfernen.

5. Klicken Sie auf **Speichern**.

6. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  

7. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.

8. Um den zugehörigen Notfallstandort zuzuweisen oder zu ändern, suchen Sie unter **Notfallstandort** nach dem Standort und wählen Sie ihn aus.

      > [!NOTE]
      > Wenn Sie Die Nummern der Netzbetreiber und Verbinden ändern, können Sie den zugeordneten Notfallstandort möglicherweise zuweisen oder ändern. Diese Funktionalität hängt von Ihrem Operator ab. Wenden Sie sich an Ihren Netzbetreiber, um weitere Informationen zu erhalten.

9. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser).

## <a name="remove-a-phone-number-from-a-user"></a>Entfernen einer Telefonnummer von einem Benutzer

So entfernen Sie eine Telefonnummer über das Teams Admin Center:

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

