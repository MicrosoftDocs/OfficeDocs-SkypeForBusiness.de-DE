---
title: "Wechseln zwischen den Client-Benutzeroberflächen von Skype for Business- und Lync"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 6/1/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom: Adm_O365_FullSet
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
description: "Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 "
---

# Wechseln zwischen den Client-Benutzeroberflächen von Skype for Business- und Lync

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den Haftungsausschluss.  
  
Skype for Business Online-Organisationen können mit Remote-PowerShell in Office 365 für Benutzer von Skype for Business die Verwendung des Skype for Business-Clients oder der Clientbenutzeroberfläche von Skype for Business (Lync) aktivieren. Die Standardeinstellung sieht für Benutzer die Verwendung der Clientbenutzeroberfläche von Skype for Business vor. Wenn Sie die Lync-Clientumgebung bevorzugen, können Sie das Clientverhalten beim ersten Start so steuern, dass die Lync-Benutzeroberfläche angezeigt wird. Befolgen Sie dazu die später in diesem Abschnitt beschriebenen Schritte.
  
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion und stellen Sie sicher, dass sie nicht mit der Zahl 16 beginnt, z. B.: 16.x.x.x. 
  
> [!TIP]
> Wenn Sie, wechseln Sie einfach auf die Benutzeroberfläche möchten und nicht die manuelle Schritte ausführen möchten, finden Sie im [Microsoft Download Center ](https://go.microsoft.com/fwlink/?LinkId=532431) für ein PowerShell-Skript zu erleichtern.
  
## Wechseln der Skype for Business-Benutzeroberfläche für Benutzer

Das Windows PowerShell-Modul für Skype für Business Online können Sie eine remote Windows PowerShell-Sitzung zu erstellen, die mit Skype für Business Online verbindet. Dieses Modul, das nur unter 64-Bit-Computern unterstützt wird, kann vom Microsoft Download Center bei [Windows PowerShell-Modul für Skype für Business Online](https://go.microsoft.com/fwlink/?LinkId=294688)heruntergeladen werden. Weitere Informationen finden Sie unter [Konfigurieren von Ihrem Computer für Skype für Business Online Management](https://go.microsoft.com/fwlink/?LinkId=534539).
  
> [!IMPORTANT]
> Die  _Global_-Richtlinieneinstellungen für den Wechsel der Benutzeroberfläche, wird bei einem Benutzer, der bereits über eine benutzerdefinierter Richtlinie verfügt, nicht eingerichtet . Sie müssen für den Wechsel der Benutzeroberfläche für jeden Benutzer mit benutzerdefinierter Richtlinie folgende Schritte ausführen: 
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> Die  _ClientPolicyEnableSkypeUI_-Richtlinie ersetzt die vorhandene benutzerdefinierte Richtlinie des Benutzers. 
  
Öffnen Sie Remote-PowerShell, um für alle Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Öffnen Sie Remote-PowerShell, um für alle Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Öffnen Sie Remote-PowerShell, um für einen einzelnen Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![Skype for Business Online - Benutzeroberfläche aktivieren](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.gif)
  
Öffnen Sie Remote-PowerShell, um für einen einzelnen Benutzern Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Wenn Sie die Richtlinie richtig eingerichtet haben, wird dies folgendermaßen angezeigt:
  
![Skype for Business Online - Benutzeroberfläche deaktiviert](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.gif)
  
Öffnen Sie Remote-PowerShell, um für mehrere Benutzer Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
> 
  ```
  $users = @("sip:bob@contoso.com","sip:fred@contoso.com")
  ```

> 
  ```
  $users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
  ```

Öffnen Sie Remote-PowerShell, um für mehrere Benutzer Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
> 
  ```
  $users = @("sip:bob@contoso.com","sip:fred@contoso.com")
  ```

> 
  ```
  $users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
  ```

Öffnen Sie Remote-PowerShell, um für eine Benutzergruppe Ihrer Organisation die Verwendung des Skype for Business-Clients zu aktivieren. Tippen Sie Folgendes ein:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Öffnen Sie Remote-PowerShell, um für eine Benutzergruppe Ihrer Organisation die Verwendung des Skype for Business-Clients (Lync) zu aktivieren. Tippen Sie Folgendes ein:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  Der Benutzername ist der Name des Benutzerkontos, dem die Richtlinie zugeordnet sein muss. Der Name des Benutzerkontos kann in einem der folgenden Formate eingegeben werden:>  SIP-Adresse des Benutzers>  Benutzerprinzipalname (UPN) des Benutzers>  Domäne\\Benutzername des Benutzers>  Anzeigename des Active Directory des Benutzers
  
[Verwenden von Windows PowerShell zum Verwalten von Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## Richtlinieneinstellungen für Skype for Business Online

Diese Tabelle zeigt die Installationsoptionen für Benutzer, denen die Richtlinie zum ersten Mal zugewiesen wird:
  
|**Administrator-Richtlinieneinstellung**|**Angezeigte Benutzeroberfläche**|
|:-----|:-----|
|Die Richtlinie ist nicht eingerichtet.  <br/> |Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

|Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

|Der Benutzer wird aufgefordert die Client-Benutzeroberfläche von Skype for Business (Lync) zu wechseln. Sie können den Wechsel später ausführen.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

|Der Benutzer wird die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |
|
```
Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

|Der Benutzer wird aufgefordert die Client-Benutzeroberfläche von Skype for Business (Lync) zu wechseln. Ein Administrator kann die Einstellung in Zukunft ändern, damit Benutzer auf die Client-Benutzeroberfläche von Skype for Business wechseln können.  <br/> |
   
Diese Tabelle zeigt die Installationsoptionen für Benutzer, bei denen die Richtlinie geändert wird:
  
|**Administrator-Richtlinieneinstellung**|**Benutzeroberfläche von Skype for Business (Lync)**|**Skype for Business-Benutzeroberfläche**|
|:-----|:-----|:-----|
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

|Der Benutzer wird aufgefordert die Client-Benutzeroberfläche von Skype for Business zu wechseln.  <br/> |Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

|Der Benutzer wird weiterhin die Skype for Business-Benutzeroberfläche (Lync) verwenden.  <br/> |Der Benutzer wird aufgefordert die Client-Benutzeroberfläche von Skype for Business (Lync) zu wechseln.  <br/> |
|Die Richtlinie ist nicht eingerichtet.  <br/> |Benutzer können die Client-Benutzeroberfläche von Skype for Business (Lync) nicht anzeigen, wenn die Richtlinie nicht eingerichtet ist. Sie werden immer die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |Der Benutzer wird weiterhin die Client-Benutzeroberfläche von Skype for Business verwenden.  <br/> |
   
Diese Tabelle enthält alle verfügbaren benutzerdefinierten Online-Richtlinien. Es gibt neue Richtlinien, die den Administratoren beim Wechsel zwischen den EnableSkypeUI-Flags mehr Flexibilität bei der Nutzung alter benutzerdefinierter Richtlinien bieten sollen. Mit den obigen Cmdlets können Sie Ihren Benutzern eine der nachstehenden Richtlinien übergeben.
  
|**Richtlinienname**|**EnableSkypeUI**|
|:-----|:-----|
|
```
ClientPolicyDefaultPhoto
```

||
|
```
ClientPolicyDefaultPhotoDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoIMURL
```

||
|
```
ClientPolicyNoIMURLDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoIMURLPhoto
```

||
|
```
ClientPolicyNoIMURLPhotoDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingI
```

||
|
```
ClientPolicyNoSaveIMNoArchivingDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURL
```

||
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto
```

||
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI
```

|False  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingPhoto
```

||
|
```
ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI
```

|False  <br/> |
   
Siehe folgende Themen, um Windows PowerShell zu verwenden:
  
- [Sechs Gründe, warum Sie Windows PowerShell zum Verwalten von Office 365 verwenden sollten]( https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Bewährte Methoden zum Verwalten von Office 365 mit Windows PowerShell]( https://go.microsoft.com/fwlink/?LinkId=525142)
    
## Verhalten beim ersten Start des Clients

Wenn der Benutzer Skype for Business erstmalig startet, sieht er standardmäßig immer die Skype for Business-Benutzeroberfläche, auch wenn Sie die Lync-Clientumgebung ausgewählt haben, indem Sie die Clientrichtlinie wie oben beschrieben auf die Lync-Clientumgebung festgelegt haben ( `Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`). Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.
  
Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:
  
1. Führen Sie die weiter oben in diesem Thema dargestellten Schritte aus und bestätigen Sie, dass die Clientrichtlinie für die Deaktivierung der Skype for Business-Benutzeroberfläche festgelegt wurde.
    
2. Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.
    
    Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** einen neuen **Binärwert**. 
    
    Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.
    
    Der Schlüssel sollte wie folgt aussehen:
    
> [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab"=dword:00000001
    
    "CanShareOneNoteInCollab"=dword:00000001
    
    "CanAppShareInCollab"=dword:00000001
    
    "EnableSkypeUI"=hex:00,00,00,00
    
Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.
  
### Steuern der Anzeige des Lernprogramms auf der Willkommensseite

Wenn Benutzer den Skype for Business-Client öffnen, wird standardmäßig die Willkommensseite angezeigt, die  *7 Tipps für die am häufigsten gestellten Fragen*  enthält. Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** einen neuen **DWORD-(32-Bit-)Wert**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt sein.
  
Der Schlüssel sollte wie folgt aussehen:
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### Ausschalten des Client-Lernprogramms

Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** einen neuen **DWORD-(32-Bit-)Wert**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt sein.
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.
  
## Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne

Die Aktualisierung der Registrierung zur Anzeige der Lync-Clientumgebung beim ersten Start des Skype for Business-Clients durch einen Benutzer sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0.
  
Das nachstehende Verfahren beschreibt, wie die Registrierung geändert werden kann, damit die Lync-Clientumgebung beim ersten Start von Skype for Business auf dem Computer des Benutzers angezeigt wird. Sie haben damit auch die Möglichkeit, die Registrierung für die Deaktivierung des Lernprogramms auf der Willkommensseite zu aktualisieren.
  
 **So erstellen Sie das Gruppenrichtlinienobjekt**
  
1. Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole**.
    
    Informationen darüber, wie Sie die Gruppenrichtlinien-Verwaltungskonsole verwenden finden Sie unter [Gruppenrichtlinien-Verwaltungskonsole](https://go.microsoft.com/fwlink/?LinkId=532759).
    
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
|**Schlüsselpfad** <br/> |Software\\Microsoft\\Office\\Lync  <br/> |
|**Wertname** <br/> |EnableSkypeUI  <br/> |
|**Werttyp** <br/> |REG_BINARY  <br/> |
|**Wertdaten** <br/> |00000000  <br/> |
   
8. Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.
    
Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.
  
 **Verwenden Sie das Gruppenrichtlinienobjekt die Richtlinie zuweisen**
  
1. Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.
    
2. Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.
    
3. Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:
    
    **gpupdate /target:user**
    
    Die Meldung „Richtlinie wird aktualisiert..." wird angezeigt, während das GPO angewendet wird. Wenn der Vorgang abgeschlossen ist, erscheint die Meldung „Die Aktualisierung der Benutzerrichtlinie wurde abgeschlossen".
    
4. Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult /r**
    
    Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.
    
Um festzustellen, ob das GPO die Registrierung auf dem Computer des Benutzers erfolgreich aktualisiert hat, überprüfen Sie die Registrierung entsprechend. Öffnen Sie dazu den Registrierungs-Editor und navigieren Sie zum Schlüssel **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Wenn das GPO die Registrierung erfolgreich aktualisiert hat, erscheint unter „EnableSkypeUI" der Wert „0".
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

