---
title: Konfigurieren der Clientumgebung mit Skype for Business 2015
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
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Clientumgebung für Skype for Business Benutzer konfigurieren.'
ms.openlocfilehash: 4cdfc0a44f07de5488d9b6a27019af0cd9fc03a74476367367b9e23170313fb6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54332067"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Konfigurieren der Clientumgebung mit Skype for Business 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Clientumgebung für Skype for Business 2015-Benutzer konfigurieren.
  
Skype for Business 2015 bietet eine neue Benutzererfahrung, die auf der Skype Produkterfahrung für Verbraucher basiert. Zusätzlich zu allen Features von Lync bietet Skype for Business neue Features mit vereinfachten Steuerelementen und vertrauten Symbolen. Ausführliche Informationen zur neuen Clientumgebung finden Sie unter [Explore Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype for Business Server unterstützt die neue Skype for Business Clientumgebung sowie die Lync-Clientumgebung. Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen. Sie können z. B. die Lync-Clientumgebung bereitstellen, bis Die Benutzer in Ihrer Organisation vollständig in der neuen Skype for Business-Umgebung geschult sind. Wenn Sie noch nicht alle Benutzer auf Skype for Business Server aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer dieselbe Clientumgebung haben, bis alle auf den neuen Server aktualisiert werden.
  
> [!IMPORTANT]
> Wenn in Ihrer Organisation sowohl Skype for Business Server als auch Lync Server bereitgestellt wurde, unterscheidet sich die Standardclientumgebung je nach Serverversion und Benutzeroberflächeneinstellungen. Wenn Benutzer Skype for Business zum ersten Mal starten, wird ihnen immer die Skype for Business Benutzeroberfläche angezeigt – auch wenn Sie die Lync-Clientumgebung ausgewählt haben. Nach einigen Minuten werden die Benutzer aufgefordert, in den Lync-Modus zu wechseln. Weitere Informationen finden Sie weiter unten in diesem Thema unter **"Clientverhalten beim ersten Start".**
  
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen oder höher. Bevor Sie versuchen, Ihre Clientumgebung für die Verwendung des Lync 2013-Clients zu konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass sie nicht mit der Nummer 16 beginnt. Beispiel: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Konfigurieren der Clienterfahrung

Sie können die Clientumgebung angeben, die den Benutzern in Ihrer Organisation angezeigt wird, indem Sie das Cmdlet **"Set-CSClientPolicy"** mit dem Parameter "EnableSkypeUI" verwenden:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

dabei bezieht sich XdsIdentity auf die globale Richtlinie oder eine benannte Standortrichtlinie.
  
Der folgende Befehl wählt die Skype for Business Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass standort- oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Der nächste Befehl wählt die Lync-Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Der nächste Befehl wählt die Skype for Business Clientumgebung für alle Benutzer innerhalb des Standorts Redmond aus:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Wenn Sie die Clientumgebung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des Cmdlets **"New-CsClientPolicy"** eine neue Benutzerrichtlinie erstellen und die Richtlinie dann bestimmten Benutzern mithilfe des **Cmdlets Grant-CsClientPolicy** zuweisen.
  
Der folgende Befehl erstellt beispielsweise eine neue Clientrichtlinie, SalesClientUI, die die Skype for Business Clientumgebung auswählt:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Mit dem nächsten Befehl wird die Richtlinie SalesClientUI allen Mitgliedern der Vertriebsabteilung zugewiesen:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Clientverhalten beim ersten Start

Wenn Benutzer Skype for Business 2015 zum ersten Mal starten, wird standardmäßig immer die Skype for Business Benutzeroberfläche angezeigt – auch wenn Sie die Lync-Clientumgebung ausgewählt haben, indem Sie den Wert des EnableSkypeUI-Parameters auf $False festlegen, wie zuvor beschrieben. Nach einigen Minuten werden die Benutzer aufgefordert, in den Lync-Modus zu wechseln.
  
Wenn Sie die Lync-Benutzeroberfläche anzeigen möchten, wenn Benutzer den Skype for Business Client zum ersten Mal starten, führen Sie die folgenden Schritte aus, bevor der Client zum ersten Mal nach der Aktualisierung gestartet wird:
  
1. Vergewissern Sie sich, dass der Wert von  `EnableSkypeUI` auf $False in der Richtlinie festgelegt ist, die Sie wie zuvor beschrieben verwenden.
    
2. Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten dies tun, bevor Benutzer den Skype for Business-Client zum ersten Mal starten, und Sie sollten dies nur einmal tun. Informationen zum Erstellen eines Gruppenrichtlinienobjekts zum Aktualisieren der Registrierung auf einem Computer, der einer Domäne beigetreten ist, finden Sie im Abschnitt weiter unten in diesem Thema.
    
    Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** einen neuen **Binärwert.**
    
    Der **Wertname** muss **EnableSkypeUI** sein, und die **Wertdaten** müssen auf **00 00 00 00** festgelegt werden.
    
    Der Schlüssel sollte wie folgt aussehen:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

Die Lync-Benutzeroberfläche wird jetzt angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms zur Willkommensseite

Wenn Benutzer den Skype for Business-Client öffnen, wird standardmäßig eine Willkommensseite angezeigt, die *7 Quickinfos* enthält, die von den meisten Personen angefordert werden. Sie können die Anzeige der Willkommensseite deaktivieren, benutzern aber dennoch den Zugriff auf das Lernprogramm ermöglichen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:
  
Erstellen Sie im **Schlüssel [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit).** Der **Wertname** muss **IsBasicTutorialSeenByUser** sein, und die **Wertdaten** müssen auf **1** festgelegt werden.
  
Der Schlüssel sollte wie folgt aussehen:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Deaktivieren des Clientlernprogramms

Wenn Sie nicht möchten, dass Ihre Benutzer auf das Lernprogramm zugreifen können, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert deaktivieren:
  
Erstellen Sie im **Schlüssel [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit).** Der **Wertname** muss **"TutorialFeatureEnabled"** sein, und die **Wertdaten** müssen auf **0** festgelegt sein.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.
  
## <a name="default-client-behaviors"></a>Standardverhalten des Clients

Wenn in Ihrer Organisation sowohl Skype for Business Server als auch Lync Server bereitgestellt wurde, unterscheidet sich die Clientumgebung je nach Serverversion und Skype Ui-Einstellung. Die folgende Tabelle zeigt die anfängliche Clientumgebung basierend auf der Serverversion und der Ui-Einstellung:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Clientumgebung**|
|:-----|:-----|:-----|
|Skype for Business Server |Standard  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Wahr  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falsch  <br/> |Benutzer, der aufgefordert wird, in den Lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Ui-Einstellung in $true ändern)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Standard  <br/> |Benutzer, der aufgefordert wird, in den Lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Ui-Einstellung in $true ändern)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Wahr  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Falsch  <br/> |Benutzer, der aufgefordert wird, in den Lync-Modus zu wechseln (Benutzer kann später zu Skype for Business wechseln, wenn Sie die Ui-Einstellung in $true ändern)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Benutzer, der zum Wechseln in den Lync-Modus aufgefordert wird (Benutzer kann später nicht zu Skype for Business wechseln)  <br/> |
   
Die nächste Tabelle zeigt die Clientumgebung, wenn der Administrator die anfängliche Einstellung für die Skype Ui ändert:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Client-Benutzeroberfläche = Lync**|**Client ui = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |Wahr  <br/> |Benutzer, der aufgefordert wird, zu Skype for Business zu wechseln  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falsch  <br/> |Lync-Modus  <br/> |Benutzer, der aufgefordert wird, in den Lync-Modus zu wechseln  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Wahr  <br/> |Benutzer, der aufgefordert wird, zu Skype for Business zu wechseln  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit korrekten Patches)  <br/> |Falsch  <br/> |Lync-Modus  <br/> |Benutzer, der aufgefordert wird, in den Lync-Modus zu wechseln  <br/> |
|Lync Server 2010 oder Lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Lync-Modus (kann nicht zu Skype for Business wechseln)  <br/> |Lync-Modus (kann nicht zu Skype for Business wechseln)  <br/> |
   
Die zum Verwalten der Konfiguration des Skype for Business-Clients erforderlichen Patchversionen sind:
  
- Lync Server 2010 – Kumulatives Update vom Februar 2015 (4.0.7577.710) für Lync Server 2010. Weitere Informationen finden Sie unter [Updates für Lync Server 2010.](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 – Kumulatives Update vom Dezember 2014 (5.0.8308.857) für Lync Server 2013. Weitere Informationen finden Sie unter [Updates für Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer, der einer Domäne beigetreten ist

Das Registrierungsupdate zum Anzeigen der Lync-Clientumgebung beim ersten Starten des Skype for Business 2015-Clients durch einen Benutzer sollte nur einmal durchgeführt werden. Wenn Sie ein Gruppenrichtlinienobjekt (Group Policy Object, GPO) zum Aktualisieren der Registrierung verwenden, müssen Sie das Objekt definieren, um einen neuen Wert zu erstellen, anstatt die Wertdaten zu aktualisieren. Wenn das Gruppenrichtlinienobjekt angewendet wird und der neue Wert nicht vorhanden ist, erstellt das Gruppenrichtlinienobjekt ihn und legt die Wertdaten auf 0 fest. 
  
Im folgenden Verfahren wird beschrieben, wie Sie die Registrierung so ändern, dass die Lync-Clientumgebung angezeigt wird, wenn ein Benutzer den Skype for Business 2015-Client zum ersten Mal startet. Sie können dieses Verfahren auch verwenden, um die Registrierung zu aktualisieren, um das Lernprogramm zur Willkommensseite wie zuvor beschrieben zu deaktivieren.
  
### <a name="to-create-the-gpo"></a>So erstellen Sie das Gruppenrichtlinienobjekt

1. Starten Sie die **Gruppenrichtlinien-Verwaltungskonsole.**
    
    Informationen zur Verwendung der Gruppenrichtlinien-Verwaltungskonsole finden Sie unter ["Gruppenrichtlinien-Verwaltungskonsole".](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11))
    
2. Klicken Sie mit der rechten Maustaste auf den Knoten **"Gruppenrichtlinienobjekte",** und wählen Sie im Menü **"Neu"** aus.
    
3. Geben Sie im Dialogfeld **"Neues Gruppenrichtlinienobjekt"** einen Namen für das Gruppenrichtlinienobjekt ein, z. B. MakeLyncDefaultUI, und klicken Sie dann auf **"OK".**
    
4. Klicken Sie mit der rechten Maustaste auf das soeben erstellte neue Gruppenrichtlinienobjekt, und wählen Sie dann im Menü **"Bearbeiten"** aus.
    
5. Erweitern Sie im **Gruppenrichtlinienverwaltungs-Editor** die **Option "Benutzerkonfiguration",** **"Einstellungen",** **"Windows Einstellungen",** und wählen Sie dann den **Registrierungsknoten** aus.
    
6. Klicken Sie mit der rechten Maustaste auf den **Registrierungsknoten,** und wählen Sie dann **neues**  >  **Registrierungselement aus.**
    
7. Aktualisieren Sie im Dialogfeld **"Neue Registrierungseigenschaften"** Folgendes:
    
   |**Field**|**Zu markierende oder einzugebende Wert**|
   |:-----|:-----|
   |**Aktion** <br/> |**Create** <br/> |
   |**Struktur** <br/> | Hkey_current_user <br/> |
   |**Schlüsselpfad** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Wertname** <br/> |EnableSkypeUI  <br/> |
   |**Werttyp** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. Klicken Sie auf **"OK",** um die Änderungen zu speichern, und schließen Sie dann das Gruppenrichtlinienobjekt.
    
Als Nächstes müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe von Benutzern verknüpfen, denen Sie die Richtlinie zuweisen möchten, z. B. eine ORGANISATIONSEINHEIT.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie

1. Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die OU, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.
    
2. Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das erstellte Gruppenrichtlinienobjekt aus, und wählen Sie dann **OK** aus.
    
3. Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung, und geben Sie den folgenden Befehl ein:
       
   ```console
   pupdate /target:user
   ```
     Die Meldung "Richtlinie aktualisieren..." wird angezeigt, während das Gruppenrichtlinienobjekt angewendet wird. Wenn sie abgeschlossen ist, wird die Meldung "Aktualisierung der Benutzerrichtlinie wurde erfolgreich abgeschlossen" angezeigt.
    
4. Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult /r**
    
    Unten sollte "Zugewiesene Gruppenrichtlinienobjekte" mit dem Namen des erstellten Gruppenrichtlinienobjekts angezeigt werden.
    
Sie können auch überprüfen, ob das Gruppenrichtlinienobjekt die Registrierung auf dem Computer eines Benutzers erfolgreich aktualisiert hat, indem Sie die Registrierung überprüfen. Öffnen Sie den Registrierungs-Editor, und navigieren Sie zum Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].** Wenn das Gruppenrichtlinienobjekt die Registrierung erfolgreich aktualisiert hat, wird der Wert "EnableSkypeUI" mit dem Wert 0 angezeigt.
