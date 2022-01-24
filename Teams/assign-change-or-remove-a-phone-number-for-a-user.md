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
ms.openlocfilehash: 1836de6997f2e917e599efc091b689877856c4c7
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2022
ms.locfileid: "62181078"
---
# <a name="assign-change-or-remove-a-phone-number-for-a-user"></a>Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer

Wenn Sie Anrufpläne oder Anbieter Verbinden, weisen Sie Ihren Benutzern Telefonnummern zu. In Microsoft Teams wird die von Ihnen zugewiesene Telefonnummer aufgelistet, wenn ein Benutzer auf **Anrufe** klickt. 

Dieser Artikel bezieht sich auf Anrufpläne und Verbinden. Informationen zum Zuweisen, Ändern oder Entfernen einer Telefonnummer für einen Benutzer in einem Direct Routing-Szenario finden Sie unter Aktivieren von Benutzern für [Direct-Routing,](./direct-routing-enable-users.md)Sprache und Voicemail.

Bevor Sie eine Nummer für einen Anrufplan- oder Netzbetreiber Verbinden, müssen Sie Telefonnummern für Ihre Benutzer erhalten. Weitere Informationen finden Sie unter [Erhalten von Nummern für Anrufplanbenutzer](getting-phone-numbers-for-your-users.md) oder Einrichten von Nummern für Verbinden [Benutzer.](operator-connect-configure.md#set-up-phone-numbers)

  
> [!NOTE]
> Eine Möglichkeit, um festzustellen, ob einem Benutzer eine Lizenz zugewiesen wurde, besteht darin, im Microsoft Teams Admin Center **Benutzer** aufzurufen. Wenn eine Lizenz zugewiesen ist, wird es auf der Seite angezeigt.  Sie können auch das Microsoft 365 Admin Center verwenden.

> [!NOTE]
> Diese Notiz gilt für Kunden, die über eine Hybridbereitstellung mit einem lokalen Active Directory verfügen. Wenn Sie einem Benutzer- oder Ressourcenkonto eine Anrufplan- oder Operator-Verbinden-Telefonnummer zuordnen möchten, müssen Sie sicherstellen, dass die Telefonnummer im lokalen Active Directory entfernt und die Änderung mit Microsoft 365 synchronisiert wurde.
  
## <a name="assign-a-phone-number-to-a-user"></a>Einem Benutzer eine Telefonnummer zuweisen

Stellen Sie beim Zuweisen einer Telefonnummer zu einem Benutzer sicher, dass sich die Telefonnummer und der Nutzungsstandort des Benutzers im selben Land befinden.

So weisen Sie eine Nummer über das Teams Admin Center zu:
    
1. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.

2. Wählen Sie auf der Seite **Telefonnummern** eine nicht zugewiesene Nummer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.  

3. Suchen Sie im Bereich **Bearbeiten** unter **Zugewiesen an** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, und klicken Sie dann auf **Zuweisen**.

4. Um den zugehörigen Notfallstandort zuzuweisen oder zu ändern, suchen Sie unter **Notfallstandort** nach dem Standort und wählen Sie ihn aus.

   > [!NOTE]
   > Wenn Sie Nummern der Netzbetreiber-Verbinden zuweisen, können Sie den zugeordneten Notfallstandort möglicherweise zuweisen oder ändern. Diese Funktionalität hängt von Ihrem Operator ab. Wenden Sie sich an Ihren Netzbetreiber, um weitere Informationen zu erhalten.

5. Je nachdem, ob Sie dem Benutzer eine E-Mail mit seinen Telefonnummerninformationen senden möchten, deaktivieren oder aktivieren Sie **Dem Benutzer eine E-Mail mit den Telefonnummerninformationen senden**. Standardmäßig ist dies aktiviert. 

6. Klicken Sie auf **Speichern**.

Verwenden Sie zum Zuweisen von Zahlen mithilfe von PowerShell das [Cmdlet Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) wie folgt:

Anrufplannummern
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType CallingPlan
```

Operatoren Verbinden Zahlen
```PowerShell
Set-CsPhoneNumberAssignment -Identity <user>  -PhoneNumber <phone number> -PhoneNumberType OperatorConnect
```

Zum Beispiel: 

```PowerShell
Set-CsPhoneNumberAssignment -Identity john@contoso.com -PhoneNumber "+14255550101" -PhoneNumberType CallingPlan
Set-CsPhoneNumberAssignment -Identity jack@contoso.com -PhoneNumber "+14255550102" -PhoneNumberType OperatorConnect
```

> [!NOTE]
> Aufgrund der Latenz zwischen Microsoft 365 und Teams kann die Aktivierung von Benutzern bis zu 24 Stunden dauern. Wenn die Telefonnummer nach 24 Stunden nicht ordnungsgemäß zugewiesen wurde, lesen Sie Telefon [Number Service Center.](https://pstnsd.powerappsportals.com/) 

  
## <a name="change-a-phone-number-for-a-user"></a>Ändern der Telefonnummer für einen Benutzer

So ändern Sie eine Telefonnummer für einen Benutzer über das Teams Admin Center:
    
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

Ein PowerShell-Beispiel finden Sie unter [Set-CsPhoneNumberAssignment.](/powershell/module/teams/set-csphonenumberassignment)

## <a name="remove-a-phone-number-from-a-user"></a>Entfernen einer Telefonnummer von einem Benutzer

So entfernen Sie eine Telefonnummer über das Teams Admin Center:

1. Klicken Sie in der linken Navigationsleiste auf **Benutzer**, suchen und doppelklicken Sie den gewünschten Benutzer, klicken Sie auf **Konto** und dann erstellen Sie unter **Allgemeine Informationen** eine Notiz mit der dem Benutzer zugewiesenen Telefonnummer.

2. Navigieren Sie in der linken Navigationsleiste zu **Sprache** > **Telefonnummern**.

3. Wählen Sie auf der Seite **Telefonnummern** die im Schritt 2 identifizierte Nummer aus, und klicken Sie dann auf **Bearbeiten**.  

4. Klicken Sie im Bereich **Bearbeiten** unter **Zugewiesen zu** auf **X**, um den Benutzer zu entfernen.

5. Klicken Sie auf **Speichern**.

Ein PowerShell-Beispiel finden Sie unter [Remove-CsPhoneNumberAssignment.](/powershell/module/teams/remove-csphonenumberassignment)

## <a name="related-topics"></a>Verwandte Themen

[Was ist die Adressprüfung?](/skypeforbusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](./emergency-calling-terms-and-conditions.md)

[Haftungsausschlussbezeichnung für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment)

[Remove-CsPhoneNumberAssignment](/powershell/module/teams/remove-csphonenumberassignment)

