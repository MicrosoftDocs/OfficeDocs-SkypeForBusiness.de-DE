---
title: Zuweisen oder Ändern des Notfallstandorts für einen Benutzer
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 2d5d3c87-af1e-487e-b86c-261f2e5a0661
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 'Erfahren Sie, wie Sie den Notfallort für Ihre Benutzer ändern können. Mit einer unbegrenzten Anzahl von Standorten können Sie Notfallorte ändern, wenn Mitarbeiter Stockwerke oder Gebäude wechseln. '
ms.openlocfilehash: 49410b0ba98e6d193749b558e479d98de1f4ef29
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303834"
---
# <a name="assign-or-change-the-emergency-location-for-a-user"></a>Zuweisen oder Ändern des Notfallstandorts für einen Benutzer

Jede aktive Telefonnummer muss über eine zugehörige Notfalladresse verfügen, wenn Sie die Telefonnummer einem Benutzer zuweisen. (Sie ordnen die Adresse zu, wenn Sie in Office 365 eine Telefonnummer erhalten oder wenn Sie eine Telefonnummer übertragen.) Wenn Sie die Nummer mit einer Notfalladresse verknüpfen, können Sie auch einen Notfall Standort hinzufügen, um eine genauere Position innerhalb eines physikalischen Standorts bereitzustellen. Ein Notfallstandort kann ein Stockwerk, ein Gebäudeflügel oder die Nummer eines Büros sein, in dem sich der Benutzer befindet. Sie können eine unbegrenzte Anzahl von Standorten für eine bestimmte Notfalladresse haben, und Sie können den Notfallort ändern, wenn der Benutzer in ein anderes Büro oder Gebäude umzieht - zum Beispiel, wenn der Benutzer von Stockwerk 34 in Stockwerk 35 wechselt.
  
Wenn Sie wissen möchten, wie Sie Anrufpläne in Office 365 erhalten und was diese kosten, lesen Sie [Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
## <a name="assign-or-change-the-emergency-location"></a>Zuweisen oder Ändern des Notfall Standorts

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wechseln Sie zum **Microsoft Teams Admin Center** > **Legacy-Portal**.
    
3. Navigieren Sie in der linken Navigationsleiste zu **VoIP** > -**Benutzer**.
    
    > [!IMPORTANT]
    > Damit Sie in der linken Navigationsleiste des Skype for Business admin Centers die Option **Stimme** sehen können, müssen Sie zunächst mindestens eine **Enterprise E5-Lizenz**, eine Lizenz für ein **Telefon System** -Add-on oder eine Lizenz für das Add-on **Audio Conferencing** kaufen.
    
4. Suchen Sie auf der Seite **VoIP-Benutzer** den Benutzer, für den Sie den Notfall Standort ändern möchten, und wählen Sie ihn aus.
    
5. Klicken Sie im Bereich „Aktion" unter **Notfallstandort** auf **Ändern**.
    
6. Klicken Sie auf der Seite **Nummer zuweisen** auf **Standort ändern**. 
    
7. Geben Sie unter **Notfalladresse ändern**in den Namen des Orts in das Feld ein, und klicken Sie auf **Suchen**.

8. Wählen Sie in der Dropdownliste nach **Ort suchen** aus, geben Sie einen Teil Namen für den Speicherort ein (geben Sie beispielsweise **Floor**ein), und klicken Sie dann auf **Suchen**. 
    
8. Wählen Sie den Notfall Standort in der Liste aus, und klicken Sie auf **Speichern**.
    
    Wenn Sie einen neuen Notfall Standort hinzufügen möchten, der in der Liste angezeigt wird, lesen Sie [hinzufügen, ändern oder Entfernen eines Notfall Standorts für Ihre Organisation](add-change-or-remove-an-emergency-location-for-your-organization.md).
    
## <a name="related-topics"></a>Verwandte Themen

[Zuweisen von Notfall Speicherorten über PowerShell](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsOnlineVoiceUser.md)

[Hinzufügen oder Löschen einer Notfalladresse für Ihr Unternehmen](add-or-remove-an-emergency-address-for-your-organization.md)

[Hinzufügen, Ändern oder Entfernen eines Notfallstandorts für Ihre Organisation](add-change-or-remove-an-emergency-location-for-your-organization.md)

[Was ist Adressvalidierung?](what-is-address-validation.md)

[Verwalten von Telefonnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization)

[Nutzungsbedingungen für Notrufe](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

[Cmdlet "Satz-CsOnlineVoiceUser"](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinevoiceuser?view=skype-ps)

  
 
