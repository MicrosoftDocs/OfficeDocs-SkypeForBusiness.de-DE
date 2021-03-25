---
title: Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online enthalten sind
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Hier finden Sie die Schritte zum Erstellen einer Standardtelefonnummer für Anrufer, die an einer Skype for Business Online-Besprechung teilnehmen können. '
ms.openlocfilehash: 956c2fa23f61f0c0e24cd1c2a0802bd3f1397bb1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113221"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Festlegen der Telefonnummern, die in Einladungen in Skype for Business Online enthalten sind

> [!Note]
> Informationen zu Telefonnummern für Besprechungs einladen in Microsoft Teams finden Sie unter Festlegen der Telefonnummern, die in [Einladungen in Microsoft Teams enthalten sind.](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams)

Audiokonferenzen in Microsoft 365 oder Office 365 ermöglichen Benutzern in Ihrer Organisation, Skype for Business-Besprechungen zu erstellen und benutzern dann die Einwahl in diese Besprechungen über ein Telefon zu ermöglichen. In Microsoft 365 und Office 365 haben Sie die Möglichkeit, eine Microsoft-Audiokonferenzbrücke oder eine Audiokonferenzbrücke eines Drittanbieters zu verwenden, die von einem genehmigten Audiokonferenzanbieter (ACP) gehostet wird.
  
> [!NOTE]
> Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält. Wenn Sie sehen möchten, ob in Ihrer Region oder Ihrem Land/Ihrer Region Einwahlnummern verfügbar sind, verwenden Sie **das Skype for Business Admin Center** Voice Phone Numbers , klicken Sie auf Hinzufügen und dann auf Neue  >    >   **Servicenummern**.  Verwenden Sie die Listen für **Land/Region,**  Bundesland/Region und Ort, um Ihre Suche zu filtern.> Wenn Sie nach gebührenfreien Servicenummern suchen, wählen Sie in der Liste   **Bundesland/Region** die Option Gebührenfrei aus.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Festlegen der Standardeinwahltelefonnummer für einen Besprechungsorganisator

1. Melden Sie sich mit Ihrem Arbeits-, Schul- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie **Benutzer** aus.
    
    ![Zeigt die Auswahl von Benutzern im Skype for Business Admin Center an](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Wählen Sie die Benutzer aus, die Sie bearbeiten möchten:
    
   - Um einen einzelnen Benutzer auszuwählen, wählen Sie den Namen des Benutzers aus.
    
   - Wenn Sie alle Benutzer auf der Seite auswählen möchten, wählen Sie das Feld neben Anzeigename **oben** in der Liste aus.
    
   - Um mehrere Benutzer auszuwählen, wählen Sie das Feld neben dem Namen der einzelnen Benutzer aus.
    
5. Wählen Sie im rechten Bereich **Bearbeiten** aus.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Wählen **Sie Audiokonferenz aus.**
    
7. Wählen Sie **auf der** Seite Eigenschaften in der Liste **Anbietername** den Anbieter für den Benutzer aus. Füllen Sie je nach Anbieter die folgenden Felder aus.
    
   - **Microsoft ist der Anbieter:** Verwenden Sie die Listen **Standardmautnummer** und **gebührenfreie** Standardnummer, um die Standardnummern für den Benutzer auszuwählen.
    
     > [!NOTE]
     > Ihrer Konferenzbrücke muss mindestens eine gebührenfreie Nummer zugewiesen werden, bevor diese als gebührenfreie Standardnummer für einen Benutzer konfiguriert werden kann. Informationen zum Abrufen einer gebührenfreien Nummer finden Sie unter [Abrufen von Servicetelefonnummern für Skype for Business.](/microsoftteams/getting-service-phone-numbers) 
  
   - **Ein Drittanbieter ist der** Anbieter: Verwenden  Sie die Felder **"Gebührenfreie** Nummer" und "Gebührenfreie Nummer", um die Nummern für den Benutzer ein eingeben.


## <a name="reset-audio-conferencing-phone-numbers"></a>Zurücksetzen von Audiokonferenz-Telefonnummern

1. Wählen Sie im **Skype for Business Admin Center** die Option **Audio conferencing** (Audiokonferenz) aus.
    
2. Wählen Sie oben auf der Seite die Option **Benutzer** aus.
    
3. Wählen Sie die Benutzer aus, die Sie zurücksetzen möchten, und klicken Sie dann im Aktionsbereich auf **Löschen.**
    
Wenn Sie die Konferenzeinstellungen eines Benutzers ändern, wird standardmäßig eine E-Mail an den Benutzer gesendet. Wie Sie diese Einstellung ändern können, erfahren Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Wenn Sie die Audiokonferenzeinstellungen eines Benutzers ändern, müssen besprechungsserien- und zukünftige Skype for Business-Besprechungen aktualisiert und an Teilnehmer gesendet werden. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) nutzen.
    
- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.
    
    Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.
    
    > [!NOTE]
    > Um die BridgeID zu finden, verwenden Sie **das Cmdlet Get-CsOnlineDialInConferencingBridge.**
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer für alle Benutzer bis auf einen auf +18005551234 festzulegen:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer, deren standardmäßige gebührenfreie Telefonnummer +18005551234 lautet, in +18005551239 zu ändern:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer in den USA auf +18005551234 festzulegen:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell?
- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Warum Sie Microsoft 365 oder Office 365 PowerShell verwenden müssen](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell hat gegenüber der Verwendung des Microsoft 365 Admin Centers viele Vorteile in Geschwindigkeit, Einfachheit und Produktivität, z. B. wenn Sie Einstellungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Optimale Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)