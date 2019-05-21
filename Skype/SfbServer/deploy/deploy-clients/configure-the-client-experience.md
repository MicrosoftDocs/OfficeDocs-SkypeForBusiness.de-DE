---
title: Konfigurieren der Clientumgebung mit Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Zusammenfassung: Lesen Sie dieses Thema, um zu erfahren, wie Sie die Clientumgebung für Skype for Business-Benutzer konfigurieren.'
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298284"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Konfigurieren der Clientumgebung mit Skype for Business 2015
 
**Zusammenfassung:** In diesem Thema erfahren Sie, wie Sie die Clientumgebung für Skype for Business 2015-Benutzer konfigurieren.
  
Skype for Business 2015 bietet eine neue Benutzererfahrung, die auf der Skype-Consumer-Produkterfahrung basiert. Neben allen Funktionen von lync bietet Skype for Business neue Funktionen mit vereinfachten Steuerelementen und vertrauten Symbolen. Detaillierte Informationen zur neuen Clientumgebung finden Sie unter [erkunden von Skype for Business](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype for Business Server unterstützt die neue Skype for Business-Clientumgebung sowie die lync-Clientumgebung. Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen. So können Sie beispielsweise die lync-Clientumgebung so lange bereitstellen, bis die Benutzer in Ihrer Organisation in der neuen Skype for Business-Benutzeroberfläche umfassend geschult sind. Wenn Sie noch nicht alle Benutzer auf Skype for Business Server aktualisiert haben, möchten Sie möglicherweise, dass alle Benutzer die gleiche Clientumgebung haben, bis alle auf den neuen Server aktualisiert wurden.
  
> [!IMPORTANT]
> Wenn in Ihrer Organisation sowohl Skype for Business Server als auch lync Server bereitgestellt sind, unterscheidet sich die standardmäßige Clientumgebung je nach Server Versionen und UI-Einstellungen. Wenn Benutzer Skype for Business zum ersten Mal starten, sehen Sie immer die Benutzeroberfläche von Skype for Business – auch wenn Sie die lync-Clientumgebung ausgewählt haben. Nach einigen Minuten werden die Benutzer aufgefordert, in den lync-Modus zu wechseln. Weitere Informationen entnehmen Sie dem **Abschnitt zum Clientverhalten beim ersten Start**.
  
> [!NOTE]
> Die lync 2013-Clientumgebung ist keine Option für Skype for Business 2016-Clientversionen oder höher. Bevor Sie versuchen, ihre Clientumgebung für die Verwendung des lync 2013-Clients zu konfigurieren, überprüfen Sie die Client Version, um sicherzustellen, dass Sie nicht mit der Zahl 16 beginnt; Beispiel: 16. x.x.x. 
  
## <a name="configure-the-client-experience"></a>Konfigurieren der Client-Erfahrung

Sie können die Client-Erfahrung Ihres Unternehmens, die den Benutzern angezeigt wird, angeben, indem Sie das Cmdlet **Set-CSClientPolicy** mit dem Parameter EnableSkypeUI verwenden:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

wobei sich XdsIdentity auf die globale Richtlinie oder eine benannte Standortrichtlinie bezieht.
  
Mit dem folgenden Befehl wird die Skype for Business-Clientumgebung für alle Benutzer in Ihrer Organisation ausgewählt, die von der globalen Richtlinie betroffen sind (denken Sie daran, dass Website-oder benutzerspezifische Richtlinien die globale Richtlinie außer Kraft setzen): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Der nächste Befehl wählt die lync-Clientumgebung für alle Benutzer in Ihrer Organisation aus, die von der globalen Richtlinie betroffen sind:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Mit dem folgenden Befehl wird die Skype for Business-Clientumgebung für alle Benutzer auf der Website "Redmond" ausgewählt:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Wenn Sie die Clientumgebung für bestimmte Benutzer in Ihrer Organisation konfigurieren möchten, können Sie mithilfe des Cmdlets **New-CsClientPolicy** eine neue Benutzerrichtlinie erstellen und dann die Richtlinie bestimmten Benutzern zuweisen, indem Sie die **Grant-CsClientPolicy** Cmdlet.
  
Mit dem folgenden Befehl wird beispielsweise eine neue Clientrichtlinie, SalesClientUI, erstellt, die die Skype for Business-Clientumgebung auswählt:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Der nächste Befehl weist die Richtlinie „SalesClientUI“ allen Mitgliedern der Verkaufsabteilung zu:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Verhalten beim ersten Start des Clients

Wenn Benutzer Skype for Business 2015 zum ersten Mal starten, wird standardmäßig immer die Benutzeroberfläche von Skype for Business angezeigt, auch wenn Sie die lync-Clientumgebung ausgewählt haben, indem Sie den Wert des EnableSkypeUI-Parameters auf $false wie beschrieben festlegen. zuvor. Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.
  
Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:
  
1. Vergewissern Sie sich, dass `EnableSkypeUI` der Wert von in der von Ihnen verwendeten Richtlinie auf $false festgesetzt ist, wie zuvor beschrieben.
    
2. Aktualisieren Sie die Systemregistrierung auf dem Computer des Benutzers. Sie sollten diesen Schritt ausführen, bevor der Benutzer den Skype for Business-Client erstmalig startet und Sie sollten diesen Schritt nur einmal ausführen. Informationen zum Erstellen eines GPO (Group Policy Object, Gruppenrichtlinienobjekt) für die Aktualisierung der Systemregistrierung auf einem Computer in einer Domäne finden Sie weiter unten in diesem Thema.
    
    Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]** einen neuen **Binärwert**.
    
    Der **Wertname** muss **EnableSkypeUI** sein und die **Wertdaten** müssen auf **00 00 00 00** festgelegt sein.
    
    Der Schlüssel sollte wie folgt aussehen:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

Die Lync-Benutzeroberfläche wird nun angezeigt, wenn Benutzer den Skype for Business-Client zum ersten Mal starten.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms auf der Willkommenseite

Wenn Benutzer den Skype for Business-Client öffnen, besteht das Standardverhalten darin, einen Begrüßungsbildschirm anzuzeigen, der *7 schnelle Tipps enthält, nach denen die meisten Personen Fragen*. Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt werden.
  
Der Schlüssel sollte wie folgt aussehen:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Ausschalten des Client-Lernprogramms

Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Clientlernprogramm mit dem folgenden Registrierungswert ausschalten:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt werden.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.
  
## <a name="default-client-behaviors"></a>Standardmäßiges Client-Verhalten

Wenn in Ihrer Organisation sowohl Skype for Business Server als auch lync Server bereitgestellt werden, unterscheidet sich die Clientumgebung je nach Server Version und der Skype-Benutzeroberflächeneinstellung. Die folgende Tabelle zeigt die anfängliche Clientumgebung basierend auf der Serverversion und der Benutzeroberflächeneinstellung:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Client-Erfahrung**|
|:-----|:-----|:-----|
|Skype for Business Server |Standard  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |Falsch  <br/> |Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)  <br/> |
|Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)  <br/> |Standard  <br/> |Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)  <br/> |
|Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)  <br/> |Falsch  <br/> |Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später zu Skype for Business wechseln, wenn Sie die UI-Einstellung auf $true ändern)  <br/> |
|Lync Server 2010 oder lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Der Benutzer hat gebeten, in den lync-Modus zu wechseln (der Benutzer kann später nicht mehr zu Skype for Business wechseln)  <br/> |
   
Die nächste Tabelle zeigt die Clientumgebung, wenn der Administrator die anfängliche Einstellung für das Skype-UI-Erlebnis ändert:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Client-UI = lync**|**Client-Benutzeroberfläche = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |Benutzer hat gebeten, zu Skype for Business zu wechseln  <br/> |Skype for Business  <br/> |
|Skype for Business Server |Falsch  <br/> |Lync-Modus  <br/> |Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln  <br/> |
|Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)  <br/> |True  <br/> |Benutzer hat gebeten, zu Skype for Business zu wechseln  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder lync Server 2013 (mit den richtigen Patches)  <br/> |Falsch  <br/> |Lync-Modus  <br/> |Der Benutzer hat aufgefordert, in den lync-Modus zu wechseln  <br/> |
|Lync Server 2010 oder lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Lync-Modus (kann nicht zu Skype for Business wechseln)  <br/> |Lync-Modus (kann nicht zu Skype for Business wechseln)  <br/> |
   
Die für die Verwaltung der Konfiguration des Skype for Business-Clients erforderlichen Patch-Versionen sind:
  
- Lync Server 2010-Februar 2015 Kumulatives Update (4.0.7577.710) für lync Server 2010. Informationen finden Sie unter [Updates für lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-Dezember 2014 Kumulatives Update (5.0.8308.857) für lync Server 2013. Informationen finden Sie unter [Updates für lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne

Das Registrierungsupdate zur Anzeige der lync-Clientumgebung, wenn ein Benutzer zum ersten Mal den Skype for Business 2015-Client startet, sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0. 
  
Im folgenden Verfahren wird beschrieben, wie Sie die Registrierung so ändern, dass die lync-Clientumgebung angezeigt wird, wenn ein Benutzer zum ersten Mal den Skype for Business 2015-Client startet. Mit diesem Verfahren können Sie auch die Registrierung aktualisieren, um das Lernprogramm der Willkommenseite zu deaktivieren (wie weiter oben beschrieben).
  
### <a name="to-create-the-gpo"></a>So erstellen Sie das Gruppenrichtlinienobjekt

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
   |**Schlüsselpfad** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Wertname** <br/> |EnableSkypeUI  <br/> |
   |**Werttyp** <br/> |REG_BINARY  <br/> |
   |**Wertdaten** <br/> |00000000  <br/> |
   
8. Klicken Sie zum Speichern der Änderungen auf **OK** und schließen Sie dann das Gruppenrichtlinienobjekt.
    
Anschließend müssen Sie das erstellte Gruppenrichtlinienobjekt mit der Gruppe der Benutzer (beispielsweise einer Organisationseinheit) verbinden, denen Sie die Richtlinie zuweisen möchten.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>So verwenden Sie das Gruppenrichtlinienobjekt zum Zuweisen der Richtlinie

1. Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole mit der rechten Maustaste auf die Organisationseinheit, der Sie die Richtlinie zuweisen möchten, und wählen Sie dann **Verknüpfung mit einem vorhandenen Gruppenrichtlinienobjekt** aus.
    
2. Wählen Sie im Dialogfeld **Gruppenrichtlinienobjekt auswählen** das von Ihnen erstellte Gruppenrichtlinienobjekt und anschließend **OK** aus.
    
3. Öffnen Sie auf dem Computer des Zielbenutzers eine Eingabeaufforderung und geben Sie den folgenden Befehl ein:
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. Geben Sie an der Eingabeaufforderung den folgenden Befehl ein:
    
    **gpresult /r**
    
    Ihnen sollte nun „Zugewiesene Gruppenrichtlinienobjekte“ mit dem Namen des von Ihnen erstellten Gruppenrichtlinienobjekts darunter angezeigt werden.
    
Sie können auch überprüfen, ob das Gruppenrichtlinienobjekt die Registrierung auf dem Computer eines Benutzers ordnungsgemäß aktualisiert hat, indem Sie die Registrierung untersuchen. Öffnen Sie den Registrierungs-Editor und navigieren Sie zum Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Wenn das Gruppenrichtlinienobjekt die Registrierung aktualisiert hat, wird der Wert „EnableSkypeUI“ mit dem Wert „0“ angezeigt.
  

