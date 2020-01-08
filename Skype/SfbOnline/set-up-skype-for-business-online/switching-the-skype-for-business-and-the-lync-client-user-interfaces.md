---
title: Wechseln zwischen den Client-Benutzeroberflächen von Skype for Business- und Lync
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: None
ms.custom:
- Setup
description: 'Informationen zum Wechseln zwischen Skype for Business-und lync-Clientbenutzeroberflächen mithilfe von PowerShell in Office 365 '
ms.openlocfilehash: 0f24879c136c98db1a856765cb164d376417ad5a
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962883"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Wechseln zwischen den Client-Benutzeroberflächen von Skype for Business- und Lync

Für Skype for Business Online-Organisationen können Sie die Remote-PowerShell in Office 365 verwenden, um Skype for Business-Benutzern die Nutzung der Skype for Business-Client-oder der Skype for Business (lync)-Client-Benutzeroberfläche zu ermöglichen. Die Standardeinstellung ist, dass Benutzer die Skype for Business-Client-Benutzeroberfläche verwenden. Wenn Sie die lync-Clientumgebung lieber verwenden möchten, können Sie das erste Start Clientverhalten verwalten, um die lync-Benutzeroberfläche anzuzeigen, indem Sie die Schritte weiter unten in diesem Thema ausführen.
  
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion und stellen Sie sicher, dass sie nicht mit der Zahl 16 beginnt, z. B.: 16.x.x.x. 
  
> [!TIP]
> Wenn Sie die Benutzeroberfläche problemlos wechseln und die manuellen Schritte nicht ausführen möchten, lesen Sie das [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=532431) für ein PowerShell-Skript, um es einfacher zu machen.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>Wechseln der Skype for Business-Benutzeroberfläche für Benutzer

Mit dem Windows PowerShell-Modul für Skype for Business Online können Sie eine Windows PowerShell-Remotesitzung erstellen, die eine Verbindung zu Skype for Business Online herstellt. Dieses Modul, das nur von 64-Bit-Computern unterstützt wird, kann im Microsoft Download Center unter [Windows PowerShell-Modul für Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688) heruntergeladen werden. Weitere Informationen finden Sie unter[Konfigurieren Ihres Computers für die Verwaltung von Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=534539).
  
> [!IMPORTANT]
> Die  _Global_-Richtlinieneinstellungen für den Wechsel der Benutzeroberfläche, wird bei einem Benutzer, der bereits über eine benutzerdefinierter Richtlinie verfügt, nicht eingerichtet . Sie müssen für den Wechsel der Benutzeroberfläche für jeden Benutzer mit benutzerdefinierter Richtlinie folgende Schritte ausführen:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> Die  _ClientPolicyEnableSkypeUI_-Richtlinie ersetzt die vorhandene benutzerdefinierte Richtlinie des Benutzers.
  
Öffnen Sie Remote-PowerShell, um für alle Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Öffnen Sie Remote-PowerShell, um für alle Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein: 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Öffnen Sie Remote-PowerShell, um für einen einzelnen Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![Skype for Business Online - Benutzeroberfläche aktivieren](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
Öffnen Sie Remote-PowerShell, um für einen einzelnen Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![Skype for Business Online - Benutzeroberfläche deaktiviert](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
Öffnen Sie Remote-PowerShell, um für mehrere Benutzer Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Öffnen Sie Remote-PowerShell, um für mehrere Benutzer Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Öffnen Sie Remote-PowerShell, um für eine Benutzergruppe Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Öffnen Sie Remote-PowerShell, um für eine Benutzergruppe Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  Der Benutzername ist der Name des Benutzerkontos, dem die Richtlinie zugeordnet sein muss. Der Name des Benutzerkontos kann in einem der folgenden Formate eingegeben werden:>  SIP-Adresse des Benutzers>  Benutzerprinzipalname (UPN) des Benutzers>  Domäne\\Benutzername des Benutzers>  Anzeigename des Active Directory des Benutzers
  
[Verwenden von Windows PowerShell zum Verwalten von Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## <a name="skype-for-business-online-policy-settings"></a>Richtlinieneinstellungen für Skype for Business Online

Diese Tabelle zeigt die Installationsoptionen für Benutzer, denen die Richtlinie zum ersten Mal zugewiesen wird:
  
|**Administrator-Richtlinieneinstellung**|**Angezeigte Benutzeroberfläche**|
|:-----|:-----|
|Die Richtlinie ist nicht eingerichtet. |Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|Der Benutzer wird aufgefordert, zur Client-Benutzeroberfläche von Skype for Business (lync) zu wechseln. Sie können den Wechsel später ausführen.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|Der Benutzer wird die Skype for Business-Client-Benutzeroberfläche verwenden. |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|Der Benutzer wird aufgefordert, zur Client-Benutzeroberfläche von Skype for Business (lync) zu wechseln. Ein Administrator kann die Einstellung in Zukunft ändern, damit Benutzer auf die Client-Benutzeroberfläche von Skype for Business wechseln können. |
   
Diese Tabelle zeigt die Installationsoptionen für Benutzer, bei denen die Richtlinie geändert wird:
  
|**Administrator-Richtlinieneinstellung**|**Benutzeroberfläche von Skype for Business (Lync)**|**Skype for Business-Benutzeroberfläche**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|Der Benutzer wird aufgefordert, zur Skype for Business-Client-Benutzeroberfläche zu wechseln.  <br/> |Der Benutzer wird weiterhin die Skype for Business-Client-Benutzeroberfläche verwenden.  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|Der Benutzer wird weiterhin die Skype for Business (lync)-Schnittstelle verwenden.  <br/> |Der Benutzer wird aufgefordert, zur Client-Benutzeroberfläche von Skype for Business (lync) zu wechseln.  <br/> |
|Die Richtlinie ist nicht eingerichtet.  <br/> |Benutzer können die Client-Benutzeroberfläche von Skype for Business (lync) nie sehen, wenn die Richtlinie nicht festgesetzt ist. Sie werden immer die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |Der Benutzer wird weiterhin die Skype for Business-Client-Benutzeroberfläche verwenden.  <br/> |
   
Diese Tabelle enthält alle verfügbaren benutzerdefinierten Online-Richtlinien. Es gibt neue Richtlinien, die den Administratoren beim Wechsel zwischen den EnableSkypeUI-Flags mehr Flexibilität bei der Nutzung alter benutzerdefinierter Richtlinien bieten sollen. Mit den obigen Cmdlets können Sie Ihren Benutzern eine der nachstehenden Richtlinien übergeben.
  
|**Richtlinienname**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |Falsch|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |Falsch|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |Falsch|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |Falsch|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |Falsch|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|Falsch|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |Falsch|

   
Informieren Sie sich in den folgenden Themen über die Verwendung von Windows PowerShell:
  
- [Warum Sie Office 365 PowerShell verwenden müssen](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Beste Möglichkeiten zum Verwalten von Office 365 mit der Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
## <a name="first-launch-client-behaviors"></a>Verhalten beim ersten Start des Clients

Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie standardmäßig immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie die Clientrichtlinie wie zuvor beschrieben auf die lync-`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`Clientumgebung () festlegen. Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.
  
Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:
  
1. Führen Sie die weiter oben in diesem Thema dargestellten Schritte aus und bestätigen Sie, dass die Clientrichtlinie für die Deaktivierung der Skype for Business-Benutzeroberfläche festgelegt wurde.
    
2. Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.
    
    Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** einen neuen **Binärwert**.
    
    Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.
    
    Der Schlüssel sollte wie folgt aussehen:
    
    [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\lync]
    
    "CanSharePptInCollab" = DWORD: 00000001
    
    "CanShareOneNoteInCollab" = DWORD: 00000001
    
    "CanAppShareInCollab" = DWORD: 00000001
    
    "EnableSkypeUI" = Hex: 00, 00, 00, 00
    
Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms auf der Willkommenseite

Wenn Benutzer den Skype for Business-Client öffnen, besteht das Standardverhalten darin, einen Begrüßungsbildschirm anzuzeigen, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*. Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** einen neuen **DWORD-(32-Bit-)Wert**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt sein.
  
Der Schlüssel sollte wie folgt aussehen:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Ausschalten des Client-Lernprogramms

Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** einen neuen **DWORD-(32-Bit-)Wert**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt sein.
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne

Die Aktualisierung der Registrierung zur Anzeige der Lync-Clientumgebung beim ersten Start des Skype for Business-Clients durch einen Benutzer sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0.
  
Das nachstehende Verfahren beschreibt, wie die Registrierung geändert werden kann, damit die Lync-Clientumgebung beim ersten Start von Skype for Business auf dem Computer des Benutzers angezeigt wird. Sie haben damit auch die Möglichkeit, die Registrierung für die Deaktivierung des Lernprogramms auf der Willkommensseite zu aktualisieren.
  
 **So erstellen Sie das Gruppenrichtlinienobjekt**
  
1. Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.
    
    Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](https://go.microsoft.com/fwlink/?LinkId=532759).
    
2. Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte** und wählen Sie im Menü **Neu** aus.
    
3. Geben Sie im Dialogfeld **Neues Gruppenrichtlinienobjekt** einen Namen für das Gruppenrichtlinienobjekt (z. B.MakeLyncDefaultUI) ein und klicken Sie dann auf **OK**.
    
4. Klicken Sie mit der rechten Maustaste auf das soeben erstellte neue Gruppenrichtlinienobjekt und wählen Sie dann im Menü **Bearbeiten** aus.
    
5. Im **Gruppenrichtlinienverwaltungs-Editor** erweitern Sie **Benutzerkonfiguration**, dann **Einstellungen** und dann **Windows-Einstellungen** und wählen Sie anschließend den Knoten **Registrierung** aus.
    
6. Klicken Sie mit der rechten Maustaste auf den Knoten **Registrierung** und wählen Sie dann **Neu** > **Registrierungselement** aus.
    
7. Aktualisieren Sie im Dialogfeld **Neue Registrierungseigenschaften** die folgenden Angaben:
    
|**Feld**|**Auszuwählender oder einzugebender Wert**|
|:-----|:-----|
|**Aktion** <br/> |**Erstellen** <br/> |
|**Struktur** <br/> | HKEY_CURRENT_USER <br/> |
|**Schlüsselpfad** <br/> |Software\\Microsoft\\Office\\lync  <br/> |
|**Wertname** <br/> |EnableSkypeUI  <br/> |
|**Werttyp** <br/> |REG_BINARY  <br/> |
|**Wertdaten** <br/> |00000000  <br/> |
   
Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.
    
Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.
  
 **So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie**
  
1. Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.
    
2. Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.
    
3. Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:
    
    **gpupdate /target:user**
    
    Die Meldung „Richtlinie wird aktualisiert..." wird angezeigt, während das GPO angewendet wird. Wenn der Vorgang abgeschlossen ist, erscheint die Meldung „Die Aktualisierung der Benutzerrichtlinie wurde abgeschlossen".
    
4. Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult /r**
    
    Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.
    
Um festzustellen, ob das GPO die Registrierung auf dem Computer des Benutzers erfolgreich aktualisiert hat, überprüfen Sie die Registrierung entsprechend. Öffnen Sie dazu den Registrierungs-Editor und navigieren Sie zum Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Wenn das GPO die Registrierung erfolgreich aktualisiert hat, erscheint unter „EnableSkypeUI" der Wert „0".
  
## <a name="related-topics"></a>Verwandte Themen
[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)

[Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md)

  
 
