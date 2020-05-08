---
title: Einrichten der in Einladungen enthaltenen Telefonnummern in Skype for Business Online
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
description: 'Führen Sie die Schritte zum Erstellen einer Standardtelefonnummer für Anrufer aus, um an einer Skype for Business Online-Besprechung teilzunehmen. '
ms.openlocfilehash: b7a4ee991ff8a8e41401b3b2d2dc20aa20708b88
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163934"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Einrichten der in Einladungen enthaltenen Telefonnummern in Skype for Business Online

> [!Note]
> Informationen zum Einladen von Telefonnummern für Besprechungen in Microsoft Teams finden Sie unter [Einrichten der Telefonnummern, die in Einladungen in Microsoft Teams enthalten sind](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Audiokonferenzen in Microsoft 365 oder Office 365 ermöglichen es Benutzern in Ihrer Organisation, Skype for Business-Besprechungen zu erstellen und Benutzern dann das Einwählen in diese Besprechungen mithilfe eines Telefons zu ermöglichen. In Microsoft 365 und Office 365 haben Sie die Möglichkeit, eine Microsoft-Audiokonferenz-Brücke oder eine Audio-Konferenzbrücke eines Drittanbieters zu verwenden, die von einem zugelassenen Audiokonferenz-Anbieter (ACP) gehostet wird.
  
> [!NOTE]
> Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält. Wenn Sie feststellen möchten, ob Einwahlnummern in Ihrem Land/Ihrer Region verfügbar sind, verwenden Sie die **Skype for Business Admin Center** > **-sprach** > **Nummern**, klicken Sie auf **neue Service Nummern** **Hinzufügen** . Verwenden Sie die Listen für **Land/Region**, **Bundesland/Region** und **Ort** , um Ihre Suche zu filtern. > auch wenn Sie nach gebührenfreien Servicenummern suchen, wählen Sie **gebührenfrei** in der Liste **Bundesland/Region** .
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Festlegen der standardmäßigen Einwahl Telefonnummer für einen Besprechungsorganisator

1. Mit Ihrem Firmen-oder Schulkonto anmelden
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie **Benutzer** aus.
    
    ![Zeigt das Auswählen von Benutzern im Skype for Business Admin Center](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Wählen Sie die Benutzer aus, die Sie bearbeiten möchten:
    
   - Wenn Sie einen einzelnen Benutzer auswählen möchten, wählen Sie den Namen des Benutzers aus.
    
   - Um alle Benutzer auf der Seite auszuwählen, aktivieren Sie das Kontrollkästchen neben **Anzeigename** oben in der Liste.
    
   - Wenn Sie mehrere Benutzer auswählen möchten, aktivieren Sie das Kontrollkästchen neben dem Namen der einzelnen Benutzer.
    
5. Wählen Sie im rechten Bereich **Bearbeiten** aus.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Wählen Sie **Audiokonferenzen**aus.
    
7. Wählen Sie auf der Seite **Eigenschaften** in der Liste **Anbietername** den Anbieter für den Benutzer aus. Füllen Sie je nach Anbieter die folgenden Felder aus.
    
   - **Microsoft ist der Anbieter**: Verwenden Sie die standardmäßige **gebührenpflichtige Nummer** und die Standard **mäßige gebührenfreie** Nummernliste, um die Standardnummern für den Benutzer auszuwählen.
    
     > [!NOTE]
     > Ihrer Konferenzbrücke muss mindestens eine gebührenfreie Nummer zugewiesen werden, bevor diese als gebührenfreie Standardnummer für einen Benutzer konfiguriert werden kann. Informationen zum Abrufen einer gebührenfreien Nummer finden Sie unter [Abrufen von Service-Telefonnummern für Skype for Business](/microsoftteams/getting-service-phone-numbers). 
  
   - **Eine Drittpartei ist der Anbieter**: Verwenden Sie die Felder **gebührenpflichtige Nummer** und **gebührenfreie Nummer** , um die Nummern für den Benutzer einzugeben.


## <a name="reset-audio-conferencing-phone-numbers"></a>Zurücksetzen von Audiokonferenz-Telefonnummern

1. Wählen Sie im **Skype for Business Admin Center**die Option **Audio conferencing** (Audiokonferenz) aus.
    
2. Wählen Sie oben auf der Seite die Option **Benutzer** aus.
    
3. Wählen Sie die Benutzer aus, die Sie zurücksetzen möchten, und klicken Sie dann im Bereich "Aktion" auf **Löschen**.
    
Wenn Sie die Konferenzeinstellungen eines Benutzers ändern, wird standardmäßig eine e-Mail-Nachricht an den Benutzer gesendet. Wie Sie diese Einstellung ändern können, erfahren Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Wenn Sie die Einstellungen für die Audiokonferenz eines Benutzers ändern, müssen wiederkehrende und zukünftige Skype for Business-Besprechungen aktualisiert und an die Teilnehmer gesendet werden. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) nutzen.
    
- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.
    
    Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.
    
    > [!NOTE]
    > Verwenden Sie das Cmdlet **Get-CsOnlineDialInConferencingBridge** , um die Brücke zu finden.
  
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
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Möchten Sie mehr über Windows PowerShell erfahren?
- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Gründe für die Verwendung von Microsoft 365 oder Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell bietet zahlreiche Vorteile in Geschwindigkeit, Einfachheit und Produktivität, wenn Sie nur das Microsoft 365 Admin Center verwenden, beispielsweise wenn Sie für viele Benutzer gleichzeitig Einstellungsänderungen vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Microsoft 365 oder Office 365 mit Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder kaufen von Audiokonferenzen in Microsoft 365 oder Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
