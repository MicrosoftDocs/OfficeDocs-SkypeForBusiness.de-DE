---
title: Einrichten des Telefons, die Zahlen enthalten auf invites in Skype für Business-Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: c78a3fb140431dd46b3850e1d01e7fb29fb29210
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "32229414"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Einrichten des Telefons, die Zahlen enthalten auf invites in Skype für Business-Online

> [!Note]
> Informationen zur Besprechung Laden Sie Telefonnummern in Microsoft-Teams ein, finden Sie unter [Einrichten des Telefons, die Zahlen auf enthalten in Microsoft-Teams, lädt](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Audiokonferenzen in Office 365 ermöglicht Benutzern in Ihrer Organisation Skype für Business Besprechungen erstellen, und klicken Sie dann zulassen, dass Benutzer in diesen treffen mit einem Telefon einwählen. In Office 365 verfügen Sie über die Möglichkeit, eine audiokonferenzbrücke von Microsoft oder einem Drittanbieter-audiokonferenzbrücke, die von einem Provider genehmigte Audiokonferenzen (ACP) gehostet wird.
  
> [!NOTE]
> Es gibt keine Ressource, die eine Liste aller Einwahlnummern für Audiokonferenzen enthält. Wenn Sie suchen, um festzustellen, ob in Ihrer Stadt oder Land/Region-Einwahl Telefonnummern vorhanden sind, verwenden Sie die **Skype für Business Administrationscenter** > **VoIP** > **Telefonnummern**, klicken Sie auf neue Dienst Nummern **dann **Hinzufügen** **. Verwenden Sie die Listen für **Land/Region**, Bundesland/Kanton **** und **Ort** Ihrer Search.> filtern auch, wenn Sie gebührenpflichtige kostenlosen Service Nummern Suchen wählen **gebührenfreie Rufnummer** aus **Bundesland/Kanton** Liste.
  
Eine Konferenzbrücke bietet Ihnen eine Reihe von Einwahlnummern für Ihre Organisation. All diese Nummern können verwendet werden, um an den Besprechungen teilzunehmen, die ein Besprechungsorganisator erstellt hat. Sie können aber auch eine Auswahl treffen, die bei den Einladungen zur jeweiligen Besprechung berücksichtigt werden sollen.
  
> [!NOTE]
> Für einen Besprechungsorganisator kann maximal eine gebührenpflichtige und eine gebührenfreie Telefonnummer in der Besprechungseinladung angegeben werden. Im unteren Bereich jeder Besprechungseinladung befindet sich jedoch auch ein Link, über den eine vollständige Liste aller Einwahlnummern aufgerufen werden kann, über die Benutzer an einer Besprechung teilnehmen können. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Festlegen der Zugriffsnummer für Einwahl Standardrufnummer für Organisator einer Besprechung

1. Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.
    
2. Wählen Sie **Admin Center** > **Skype for Business** aus.
    
3. Wählen Sie **Benutzer** aus.
    
    ![Zeigt die Auswahl von Benutzern in der Skype für Business Administrationscenter](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Wählen Sie die Benutzer, den, die Sie bearbeiten möchten:
    
   - Um einen einzelnen Benutzer auszuwählen, wählen Sie den Namen des Benutzers ein.
    
   - Wenn alle Benutzer auf der Seite auswählen möchten, aktivieren Sie das neben **Anzeigename** am Anfang der Liste.
    
   - Um mehrere Benutzer auszuwählen, wählen Sie das Kontrollkästchen neben dem Namen des Benutzers.
    
5. Wählen Sie im rechten Bereich **Bearbeiten** aus.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Wählen Sie **Audiokonferenzen**.
    
7. Wählen Sie auf der Seite **Eigenschaften** in der Liste **ProviderName** den Anbieter für den Benutzer ein. Füllen Sie je nach Anbieter die folgenden Felder aus.
    
   - **Microsoft ist der Dienstanbieter**: Verwenden Sie die **Standardnummer gebührenpflichtige** und **gebührenfreie Standardnummer** enthält, um die Standard-Zahlen für den Benutzer auszuwählen.
    
     > [!NOTE]
     > Ihrer Konferenzbrücke muss mindestens eine gebührenfreie Nummer zugewiesen werden, bevor diese als gebührenfreie Standardnummer für einen Benutzer konfiguriert werden kann. Wenn eine gebührenfreie Telefonnummer erhalten möchten, finden Sie unter [Getting Service Rufnummern für Skype für Unternehmen](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
   - **Ein Drittanbieter ist der Dienstanbieter**: Verwenden Sie die Felder **die gebührenpflichtige Telefonnummer** und **gebührenfreie Nummer** die Zahlen für den Benutzer eingeben.


## <a name="reset-audio-conferencing-phone-numbers"></a>Zurücksetzen von Audiokonferenz-Telefonnummern

1. Wählen Sie im **Skype for Business Admin Center**die Option **Audio conferencing** (Audiokonferenz) aus.
    
2. Wählen Sie oben auf der Seite die Option **Benutzer** aus.
    
3. Wählen Sie die Benutzer, den, die Sie zurücksetzen möchten, und klicken Sie dann im Bereich Aktion auf **Löschen**.
    
Standardmäßig wird beim Ändern von Einstellungen für einen Benutzer, eine e-Mail an den Benutzer gesendet. Wie Sie diese Einstellung ändern können, erfahren Sie unter [Aktivieren Sie oder deaktivieren Sie beim Senden von e-Mails aus, wenn Audio Konferenzen Einstellungen ändern](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Wenn Sie einen Benutzer Audiokonferenzen Einstellungen ändern, muss sich wiederholenden und zukünftigen Skype für Business Besprechungen aktualisiert und an die Teilnehmer gesendet werden. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Möchten Sie wissen, wie Sie die Verwaltung mit Windows PowerShell organisieren?

- Um Zeit zu sparen bzw. den Vorgang zu automatisieren, können Sie das Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) nutzen.
    
- Mit dem Cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) können Sie die gebührenpflichtige oder gebührenfreie Standardnummer für spezifische Benutzer ändern.
    
    Führen Sie Folgendes aus, um die gebührenfreie Standardnummer für einen Benutzer zu ändern:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Ändern Sie mit dem Cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** die gebührenpflichtige oder gebührenfreie Nummer für Benutzer auf Basis ihrer ursprünglichen Standardnummer oder ihres Standorts.
    
    > [!NOTE]
    > Um die BridgeID zu suchen, verwenden Sie das Cmdlet **Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer für alle Benutzer bis auf einen auf +18005551234 festzulegen:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer, deren standardmäßige gebührenfreie Telefonnummer +18005551234 lautet, in +18005551239 zu ändern:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Führen Sie Folgendes aus, um die standardmäßige gebührenfreie Telefonnummer aller Benutzer in den USA auf +18005551234 festzulegen:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Weitere Informationen zu Windows PowerShell finden möchten?
- In Bezug auf Windows PowerShell geht es um das Verwalten von Benutzern und darum, was Benutzer tun dürfen und was nicht. Mit Windows PowerShell können Sie Office 365 und Skype for Business Online zentral verwalten. Dies kann Ihre tägliche Arbeit vereinfachen, wenn Sie mehrere Aufgaben ausführen müssen. Informationen zu den ersten Schritten mit Windows PowerShell finden Sie unter den folgenden Themen:
    
  - [Einführung in Windows PowerShell und Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell verfügt im Vergleich zur ausschließlichen Verwendung des Office 365 Admin Centers über viele Vorteile in puncto Geschwindigkeit, Einfachheit und Produktivität, beispielsweise wenn Sie Einstellungsänderungen für viele Benutzer gleichzeitig vornehmen. Informationen zu diesen Vorteilen finden Sie unter den folgenden Themen:
    
  - [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Verwenden von Windows PowerShell zum Verwalten von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Verwenden von Windows PowerShell für die Durchführung gängiger Verwaltungsaufgaben von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Verwandte Themen

[Testen oder Kaufen des Audiokonferenz-Add-Ons in Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
