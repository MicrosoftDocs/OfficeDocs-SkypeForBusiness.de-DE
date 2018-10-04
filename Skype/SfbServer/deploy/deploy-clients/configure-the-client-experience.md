---
title: Konfigurieren der Clientumgebung mit Skype für Business 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Zusammenfassung: Lesen Sie dieses Thema, um Informationen zum Konfigurieren der Clientumgebung für Skype für Geschäftsbenutzer.'
ms.openlocfilehash: 9e2a7d53788eda36fc18cb9094cde096864ce2ba
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375358"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Konfigurieren der Clientumgebung mit Skype für Business 2015
 
**Zusammenfassung:** Lesen Sie in diesem Thema erfahren, wie die Client-Erfahrung für Skype Business 2015 Benutzer konfigurieren.
  
Skype für Business 2015 bietet eine neue Benutzeroberfläche, die auf Benutzerfunktionen Product Skype basiert. Zusätzlich zu den Features von Lync bietet Skype für Unternehmen neue Features mit vereinfachte-Steuerelementen und Symbole vertraut. Ausführliche Informationen zu den neuen Client gewohnt sind finden Sie unter [Erforschen Skype für Unternehmen](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype für Business Server unterstützt die neue Skype für Business Clientumgebung als auch das Lync-Clientumgebung. Als Administrator können Sie die bevorzugte Clientumgebung für Ihre Benutzer auswählen. Sie möchten beispielsweise die Lync-Client-Erfahrung bereitstellen, bis der Benutzer in Ihrer Organisation vollständig in die neue Skype Business wünschen geschult sind. Oder, wenn Sie für Business Server noch nicht alle Benutzer auf Skype aktualisiert haben, sollten Sie alle Benutzer können die gleichen Clientumgebung haben, bis alle auf dem neuen Server aktualisiert werden.
  
> [!IMPORTANT]
> Wenn Ihre Organisation sowohl Skype für Business Server und Lync Server bereitgestellt wurde, wird der Default Clientbenutzeroberfläche je nach Server-Versionen und Benutzeroberflächeneinstellungen davon abweichen. Wenn Benutzer Skype für Unternehmen zum ersten Mal starten, wird immer die Skype Business-Benutzeroberfläche – angezeigt, auch wenn Sie die Lync-Clientumgebung ausgewählt haben. Nach einigen Minuten werden Benutzer aufgefordert werden, auf den Lync-Modus wechseln. Weitere Informationen entnehmen Sie dem **Abschnitt zum Clientverhalten beim ersten Start**.
  
> [!NOTE]
> Die Lync 2013-Clientumgebung ist keine Option für Skype für Business 2016 Clientversionen oder höher. Bevor Sie versuchen, die Clientumgebung um die Verwendung des Lync 2013-Clients konfigurieren, überprüfen Sie die Clientversion, um sicherzustellen, dass es nicht mit der Nummer 16 gestartet wird; Beispiel: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Konfigurieren der Client-Erfahrung

Sie können die Client-Erfahrung Ihres Unternehmens, die den Benutzern angezeigt wird, angeben, indem Sie das Cmdlet **Set-CSClientPolicy** mit dem Parameter EnableSkypeUI verwenden:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

wobei sich XdsIdentity auf die globale Richtlinie oder eine benannte Standortrichtlinie bezieht.
  
Der folgende Befehl werden die Skype Business Client wünschen für alle Benutzer in Ihrer Organisation, die von der globalen Richtlinie betroffenen markiert (Denken Sie daran, Standort oder Benutzer-spezifische Richtlinien außer Kraft setzen die globale Richtlinie): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

Der nächste Befehl wählt die Lync-Client-Erfahrung für alle Benutzer in Ihrer Organisation, die von der globalen Richtlinie betroffen:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

Der nächste Befehl wählt die Skype Business Client wünschen für alle Benutzer in den Standort Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Wenn Sie die Clientumgebung für bestimmte Benutzer innerhalb Ihrer Organisation konfigurieren möchten, können Sie eine neue Richtlinie erstellen, mit dem Cmdlet **New-CsClientPolicy** und weisen Sie die Richtlinie auf bestimmte Benutzer mithilfe der **Grant-CsClientPolicy** Cmdlet.
  
Der folgende Befehl wird beispielsweise erstellt eine neue Clientrichtlinie SalesClientUI, die die Skype Business Client wünschen auswählt:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

Der nächste Befehl weist die Richtlinie „SalesClientUI“ allen Mitgliedern der Verkaufsabteilung zu:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Verhalten beim ersten Start des Clients

In der Standardeinstellung Wenn Benutzer Skype für Business 2015 zum ersten Mal starten sehen immer die Skype Business-Benutzeroberfläche – sie, auch wenn Sie die Lync-Clientumgebung ausgewählt haben, durch den Wert des Parameters EnableSkypeUI auf $False festlegen, wie beschrieben zuvor. Nach einigen Minuten wird der Benutzer aufgefordert, in den Lync-Modus zu wechseln.
  
Wenn beim ersten Start des Skype for Business-Clients die Lync-Benutzeroberfläche angezeigt werden soll, führen Sie die folgenden Schritte aus, bevor der Client nach der Aktualisierung zum ersten Mal gestartet wird:
  
1. Überprüfen Sie, ob der Wert der `EnableSkypeUI` ist auf $False in der Richtlinie, die Sie verwenden, wie oben beschrieben festlegen.
    
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
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Steuern der Anzeige des Lernprogramms auf der Willkommensseite

Wenn Benutzer die Skype für Business-Client öffnen, ist das Standardverhalten Willkommen angezeigt, die *meisten Benutzer des Clientcomputers fordern 7 Tipps*enthält. Sie können die Anzeige der Willkommensseite ausschalten, Benutzern aber die Möglichkeit geben, dennoch auf das Lernprogramm zuzugreifen, indem Sie den folgenden Registrierungswert auf dem Clientcomputer hinzufügen:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **IsBasicTutorialSeenByUser** sein und die **Wertdaten** müssen auf **1** festgelegt werden.
  
Der Schlüssel sollte wie folgt aussehen:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Ausschalten des Client-Lernprogramms

Wenn Sie nicht möchten, dass die Benutzer auf das Lernprogramm zugreifen, können Sie das Client-Lernprogramm mit dem folgenden Registrierungswert ausschalten:
  
Erstellen Sie im Schlüssel **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]** einen neuen **DWORD-Wert (32-Bit)**. Der **Wertname** muss **TutorialFeatureEnabled** sein und die **Wertdaten** müssen auf **0** festgelegt werden.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Sie können das Lernprogramm wieder aktivieren, indem Sie die **Wertdaten** auf **1** festlegen.
  
## <a name="default-client-behaviors"></a>Standardmäßiges Client-Verhalten

Wenn Ihre Organisation sowohl Skype für Business Server und Lync Server bereitgestellt wurde, wird die Clientumgebung je nach Server-Versionen und die Skype UI Einstellung davon abweichen. Die folgende Tabelle zeigt die anfängliche Clientumgebung basierend auf der Serverversion und der Benutzeroberflächeneinstellung:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Clientumgebung**|
|:-----|:-----|:-----|
|Skype for Business Server |Standard  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |True  <br/> |Skype for Business  <br/> |
|Skype for Business Server  |False  <br/> |Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann zu wechseln Skype für Unternehmen später, wenn Sie die UI-Einstellung auf $true ändern)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)  <br/> |Standard  <br/> |Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann zu wechseln Skype für Unternehmen später, wenn Sie die UI-Einstellung auf $true ändern)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)  <br/> |True  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)  <br/> |False  <br/> |Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann zu wechseln Skype für Unternehmen später, wenn Sie die UI-Einstellung auf $true ändern)  <br/> |
|Lync Server 2010 oder Lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Benutzer aufgefordert werden, auf den Lync-Modus wechseln (Benutzer kann keine wechseln Sie zu Skype für Unternehmen weiter unten)  <br/> |
   
Die folgende Tabelle zeigt die Clientumgebung, wenn der Administrator die ursprüngliche Einstellung für die Erfahrung Skype UI ändert:
  

|**Serverversion**|**EnableSkypeUI-Einstellung**|**Client-Benutzeroberfläche = Lync**|**Client-Benutzeroberfläche = Skype for Business**|
|:-----|:-----|:-----|:-----|
|Skype for Business Server |True  <br/> |Benutzer aufgefordert werden, wechseln Sie zu Skype für Unternehmen  <br/> |Skype for Business  <br/> |
|Skype for Business Server |False  <br/> |Lync-Modus  <br/> |Benutzer aufgefordert werden, auf den Lync-Modus wechseln  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)  <br/> |True  <br/> |Benutzer aufgefordert werden, wechseln Sie zu Skype für Unternehmen  <br/> |Skype for Business  <br/> |
|Lync Server 2010 oder Lync Server 2013 (mit der richtigen Patches)  <br/> |False  <br/> |Lync-Modus  <br/> |Benutzer aufgefordert werden, auf den Lync-Modus wechseln  <br/> |
|Lync Server 2010 oder Lync Server 2013 (ohne Patches)  <br/> |Standard  <br/> |Lync-Modus (kann nicht wechseln zu Skype für Unternehmen)  <br/> |Lync-Modus (kann nicht wechseln zu Skype für Unternehmen)  <br/> |
   
Die Patch-Versionen erforderlich, um die Konfiguration der Skype für Business Client verwalten sind:
  
- Lync Server 2010 – Februar 2015 Kumulatives Update (4.0.7577.710) für Lync Server 2010. Informationen finden Sie unter [Updates für Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 – Dezember 2014 Kumulatives Update (5.0.8308.857) für Lync Server 2013. Informationen finden Sie unter [Updates für Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Erstellen eines Gruppenrichtlinienobjekts zum Ändern der Registrierung auf einem Computer in einer Domäne

Das Update der Registrierung die Lync-Client-Erfahrung beim ersten anzeigen ein Benutzer die Skype für Business 2015 Client startet sollte nur einmal ausgeführt werden. Wenn Sie für die Aktualisierung der Registrierung ein Gruppenrichtlinienobjekt (GPO) verwenden, müssen Sie das Objekt für die Erstellung eines neuen Werts definieren, anstatt die Wertdaten lediglich zu aktualisieren. Wenn das GPO ohne einen neuen Wert zugewiesen wird, erstellt das GPO einen neuen Wert und setzt die Wertdaten auf 0. 
  
Das folgende Verfahren beschreibt, wie Sie die Registrierung ändern, damit die Lync-Client-Erfahrung beim ersten angezeigt wird, die ein Benutzer die Skype für Business 2015-Client startet. Mit diesem Verfahren können Sie auch die Registrierung aktualisieren, um das Lernprogramm der Willkommenseite zu deaktivieren (wie weiter oben beschrieben).
  
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
  

