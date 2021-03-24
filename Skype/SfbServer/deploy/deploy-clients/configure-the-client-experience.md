---
title: Konfigurieren der Clienterfahrung mit Skype for Business 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Zusammenfassung: In diesem Thema erfahren Sie, wie Sie die Clienterfahrung für Skype for Business-Benutzer konfigurieren.'
ms.openlocfilehash: 1816ff9af6c8c6e28ca72420f843d224587b2c70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096009"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Konfigurieren der Clienterfahrung mit Skype for Business 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Clienterfahrung für Skype for Business 2015-Benutzer konfigurieren.
  
Skype for Business 2015 bietet eine neue Benutzeroberfläche, die auf der Produkterfahrung von Skype Consumer basiert. Zusätzlich zu allen Features von Lync bietet Skype for Business neue Features mit vereinfachten Steuerelementen und vertrauten Symbolen. Ausführliche Informationen zur neuen Clienterfahrung finden Sie unter [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype for Business Server unterstützt die neue Skype for Business-Clienterfahrung sowie die Lync-Clienterfahrung. Als Administrator können Sie die bevorzugte Clienterfahrung für Ihre Benutzer auswählen. Sie können beispielsweise die Lync-Clienterfahrung bereitstellen, bis die Benutzer in Ihrer Organisation vollständig in der neuen Skype for Business-Erfahrung geschult sind. Wenn Sie noch nicht alle Benutzer auf Skype for Business Server aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer dieselbe Clienterfahrung haben, bis alle auf den neuen Server aktualisiert wurden.
  
> [!IMPORTANT]
> Wenn in Ihrer Organisation sowohl Skype for Business Server als auch Lync Server bereitgestellt sind, unterscheidet sich die Standardclientoberfläche je nach Serverversionen und Benutzeroberflächeneinstellungen. Wenn Benutzer Skype for Business zum ersten Mal starten, wird ihnen immer die Skype for Business-Benutzeroberfläche angezeigt – auch wenn Sie die Lync-Clientoberfläche ausgewählt haben. Nach einigen Minuten werden Benutzer aufgefordert, in den Lync-Modus zu wechseln. Weitere Informationen finden Sie unter **Erstes Starten des Clientverhaltens** weiter unten in diesem Thema.
  
> [!NOTE]
> Die Lync 2013-Clienterfahrung ist keine Option für Skype for Business 2016-Clientversionen oder höher. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass sie nicht mit der Nummer 16 beginnt. Beispiel: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Konfigurieren der Clienterfahrung

Sie können die Clienterfahrung angeben, die Benutzern in Ihrer Organisation angezeigt wird, indem Sie das **Cmdlet Set-CSClientPolicy** mit dem Parameter EnableSkypeUI verwenden:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

wobei XdsIdentity auf die globale Richtlinie oder eine benannte Websiterichtlinie verweist.
  
Mit dem folgenden Befehl wird die Skype for Business-Clienterfahrung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass website- oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Mit dem nächsten Befehl wird die Lync-Clienterfahrung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Mit dem nächsten Befehl wird die Skype for Business-Clienterfahrung für alle Benutzer am Standort Redmond ausgewählt:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Wenn Sie die Clienterfahrung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des **Cmdlets New-CsClientPolicy** eine neue Benutzerrichtlinie erstellen und die Richtlinie dann bestimmten Benutzern mithilfe des **Grant-CsClientPolicy-Cmdlets** zuweisen.
  
Mit dem folgenden Befehl wird beispielsweise eine neue Clientrichtlinie, SalesClientUI, erstellt, die die Skype for Business-Clienterfahrung auswählt:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Mit dem nächsten Befehl wird die Richtlinie SalesClientUI allen Mitgliedern der Vertriebsabteilung zugewiesen:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Verhalten des ersten Startclients

Wenn Benutzer Skype for Business 2015 zum ersten Mal starten, wird standardmäßig immer die Skype for Business-Benutzeroberfläche angezeigt – auch wenn Sie die Lync-Clienterfahrung ausgewählt haben, indem Sie den Wert des Parameters EnableSkypeUI auf $False festlegen, wie zuvor beschrieben. Nach einigen Minuten werden die Benutzer aufgefordert, in den Lync-Modus zu wechseln.
  
Wenn Sie die Lync-Benutzeroberfläche anzeigen möchten, wenn Benutzer den Skype for Business-Client zum ersten Mal starten, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:
  
1. Vergewissern Sie sich, dass der Wert von auf $False in der richtlinie festgelegt ist,  `EnableSkypeUI` die Sie wie zuvor beschrieben verwenden.
    
2. Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten dies tun, bevor Benutzer den Skype for Business-Client zum ersten Mal starten, und sie sollten dies nur einmal tun. Informationen zum Erstellen eines Gruppenrichtlinienobjekts zum Aktualisieren der Registrierung auf einem Computer, dem eine Domäne beigetreten ist, finden Sie im Abschnitt weiter unten im Thema.
    
    Erstellen Sie **im Schlüssel [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** einen neuen **Binary-Wert.**
    
    Der **Wertname** muss **EnableSkypeUI** sein, und die **Wertdaten** müssen auf **00 00 00 00 festgelegt werden.**
    
    Der Schlüssel sollte wie folgt aussehen:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms zum Willkommensbildschirm

Wenn Benutzer den Skype for Business-Client öffnen, besteht das Standardverhalten in der Anzeige eines Willkommensbildschirms, der  *7 Schnelltipps* enthält, nach denen die meisten Benutzer fragen. Sie können die Anzeige des Willkommensbildschirms deaktivieren, benutzern aber dennoch den Zugriff auf das Lernprogramm ermöglichen, indem Sie auf dem Clientcomputer den folgenden Registrierungswert hinzufügen:
  
Erstellen Sie **in der** HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync einen neuen **DWORD -Wert (32-Bit).** Der **Wertname** muss **IsBasicTutorialSeenByUser** sein, und die **Value-Daten** müssen auf **1 festgelegt sein.**
  
Der Schlüssel sollte wie folgt aussehen:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Deaktivieren des Client-Lernprogramms

Wenn Sie nicht möchten, dass Ihre Benutzer auf das Lernprogramm zugreifen können, können Sie das Clientlernprogramm mit dem folgenden Registrierungswert deaktivieren:
  
Erstellen Sie **in der** HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync einen neuen **DWORD -Wert (32-Bit).** Der **Wertname** muss **TutorialFeatureEnabled** sein, und die **Wertdaten** müssen auf **0 festgelegt werden.**
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten auf** **1 festlegen.**
  
## <a name="default-client-behaviors"></a>Standardverhalten des Clients

Wenn in Ihrer Organisation sowohl Skype for Business Server als auch Lync Server bereitgestellt sind, unterscheidet sich die Clienterfahrung je nach Serverversionen und der Einstellung für die Skype-Benutzeroberfläche. Die folgende Tabelle zeigt die anfängliche Clienterfahrung basierend auf der Serverversion und der Einstellung der Benutzeroberfläche:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Clienterfahrung**|
|:-----|:-----|:-----|
|Skype for Business Server |Standard  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Wahr  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falsch  <br/> |Benutzer zum Wechseln in den Lync-Modus aufgefordert (Benutzer können später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Standard  <br/> |Benutzer zum Wechseln in den Lync-Modus aufgefordert (Benutzer können später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Wahr  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Falsch  <br/> |Benutzer zum Wechseln in den Lync-Modus aufgefordert (Benutzer können später zu Skype for Business wechseln, wenn Sie die Benutzeroberflächeneinstellung in $true)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Benutzer zum Wechseln in den Lync-Modus aufgefordert (Benutzer kann später nicht zu Skype for Business wechseln)  <br/> |
   
Die nächste Tabelle zeigt die Clienterfahrung, wenn der Administrator die anfängliche Einstellung für die Skype-Benutzeroberfläche ändert:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Clientbenutzeroberfläche = Lync**|**Clientbenutzeroberfläche = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |Wahr  <br/> |Benutzer zum Wechseln zu Skype for Business aufgefordert  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falsch  <br/> |Lync-Modus  <br/> |Benutzer zum Wechseln in den Lync-Modus aufgefordert  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Wahr  <br/> |Benutzer zum Wechseln zu Skype for Business aufgefordert  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Falsch  <br/> |Lync-Modus  <br/> |Benutzer zum Wechseln in den Lync-Modus aufgefordert  <br/> |
|Lync Server 2010 oder Lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Lync-Modus (kann nicht zu Skype for Business wechseln)  <br/> |Lync-Modus (kann nicht zu Skype for Business wechseln)  <br/> |
   
Die erforderlichen Patchversionen zum Verwalten der Konfiguration des Skype for Business-Clients sind:
  
- Lync Server 2010 – Kumulatives Update vom Februar 2015 (4.0.7577.710) für Lync Server 2010. Weitere Informationen finden Sie [unter Updates for Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 – Kumulatives Update vom Dezember 2014 (5.0.8308.857) für Lync Server 2013. Weitere Informationen finden Sie [unter Updates for Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer, dem eine Domäne beigetreten ist

Das Registrierungsupdate zum Anzeigen der Lync-Clienterfahrung beim ersten Starten des Skype for Business 2015-Clients sollte nur einmal ausgeführt werden. Wenn Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) zum Aktualisieren der Registrierung verwenden, müssen Sie das Objekt definieren, um einen neuen Wert zu erstellen, anstatt die Value-Daten zu aktualisieren. Wenn das Gruppenrichtlinienobjekt angewendet wird und der neue Wert nicht vorhanden ist, erstellt das Gruppenrichtlinienobjekt es und setzt die Wertdaten auf 0. 
  
Im folgenden Verfahren wird beschrieben, wie Sie die Registrierung so ändern, dass die Lync-Clienterfahrung angezeigt wird, wenn ein Benutzer den Skype for Business 2015-Client zum ersten Mal startet. Sie können dieses Verfahren auch verwenden, um die Registrierung zu aktualisieren, um das Willkommensbildschirm-Lernprogramm wie zuvor beschrieben zu deaktivieren.
  
### <a name="to-create-the-gpo"></a>So erstellen Sie das Gruppenrichtlinienobjekt

1. Starten Sie **die Gruppenrichtlinienverwaltungskonsole**.
    
    Informationen zur Verwendung der Gruppenrichtlinienverwaltungskonsole finden Sie unter [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).
    
2. Klicken Sie mit der rechten Maustaste auf den Knoten **Gruppenrichtlinienobjekte,** und wählen **Sie im** Menü Neu aus.
    
3. Geben Sie **im Dialogfeld** Neues Gruppenrichtlinienobjekt einen Namen für das Gruppenrichtlinienobjekt ein, z. B. MakeLyncDefaultUI, und klicken Sie dann auf **OK**.
    
4. Klicken Sie mit der rechten Maustaste auf das neue Gruppenrichtlinienobjekt, das Sie gerade erstellt haben, und wählen Sie dann **im** Menü Bearbeiten aus.
    
5. Erweitern Sie **im Gruppenrichtlinienverwaltungs-Editor** die Option **Benutzerkonfiguration,** erweitern Sie Einstellungen, erweitern Sie **Windows-Einstellungen,** und wählen Sie dann den Knoten **Registrierung** aus. 
    
6. Klicken Sie mit der rechten Maustaste auf den Knoten **Registrierung,** und wählen Sie **dann Neues**  >  **Registrierungselement aus.**
    
7. Aktualisieren Sie **im Dialogfeld** Neue Registrierungseigenschaften Folgendes:
    
   |**Field**|**Wert, der ausgewählt oder eingeben werden soll**|
   |:-----|:-----|
   |**Aktion** <br/> |**Create** <br/> |
   |**Struktur** <br/> | HKEY_CURRENT_USER <br/> |
   |**Schlüsselpfad** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Wertname** <br/> |EnableSkypeUI  <br/> |
   |**Werttyp** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. Klicken **Sie auf OK,** um Ihre Änderungen zu speichern, und schließen Sie dann das Gruppenrichtlinienobjekt.
    
Als Nächstes müssen Sie das von Ihnen erstellte Gruppenrichtlinienobjekt mit der Gruppe von Benutzern verknüpfen, der Sie die Richtlinie zuweisen möchten, z. B. einer Organisationseinheit.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie

1. Klicken Sie in der Gruppenrichtlinienverwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann Link zu einem vorhandenen **Gruppenrichtlinienobjekt aus.**
    
2. Wählen Sie **im Dialogfeld Gruppenrichtlinienobjekt** auswählen das erstellte Gruppenrichtlinienobjekt aus, und wählen Sie dann **OK aus.**
    
3. Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung, und geben Sie den folgenden Befehl ein:
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult /r**
    
    Sie sollten "Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des gruppenrichtlinienobjekts, das Sie erstellt haben, unten angezeigt werden.
    
Sie können auch überprüfen, ob das Gruppenrichtlinienobjekt die Registrierung auf dem Computer eines Benutzers erfolgreich aktualisiert hat, indem Sie die Registrierung untersuchen. Öffnen Sie den Registrierungs-Editor, und navigieren Sie **zum [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]-Schlüssel.** Wenn das Gruppenrichtlinienobjekt die Registrierung erfolgreich aktualisiert hat, wird ein Wert namens EnableSkypeUI mit dem Wert 0 sehen.
