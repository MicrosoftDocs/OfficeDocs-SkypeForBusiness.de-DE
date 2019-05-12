---
title: Verwenden Sie zweistufige Authentifizierung mit Skype für Business Client- und Skype für Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Zusammenfassung: Verwenden Sie zweistufige Authentifizierung mit Skype für Business Server und Skype für Unternehmen.'
ms.openlocfilehash: c1d67682f229a22f4674e5643ccf8d3a99a59f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919458"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Verwenden Sie zweistufige Authentifizierung mit Skype für Business Client- und Skype für Business Server
 
**Zusammenfassung:** Verwenden Sie zweistufige Authentifizierung mit Skype für Business Server und Skype für Unternehmen.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Erstmaliges Anmelden bei Skype for Business

Ihre Anmeldeinformationen wird bei der Installation von Skype für Unternehmen in der Regel automatisch konfiguriert. Jedoch zum ersten Mal, das Sie Skype für Unternehmen, verwenden, Sie möglicherweise müssen Sie den Client manuell zu starten.
  
### <a name="to-sign-in-for-the-first-time"></a>So melden Sie sich erstmalig an

1. Melden Sie sich beim Netzwerk Ihrer Organisation an.
    
2. Wählen Sie **Start** > **Programme** > **Skype für Unternehmen**.
    
    Der Anmeldebildschirm wird angezeigt.
    
    - Wenn das Feld mit der Anmeldeadresse bereits ausgefüllt ist, überprüfen Sie, ob die angezeigte Adresse richtig ist.
    
    - Wenn es nicht korrekt ist oder wenn das Feld leer ist, geben Sie Ihre Anmeldeadresse ein (Dies ist in der Regel Ihre e-Mail-Adresse identisch).
    
    - Wenn ein leeres Kennwortfeld angezeigt wird, geben Sie Ihr Kennwort ein.
    
3. Wählen Sie **Anmelden** aus.
    
## <a name="sign-out-of-skype-for-business"></a>Abmelden von Skype for Business

Wenn Sie die Verwendung von Skype für Unternehmen haben, können Sie die Anzeige schließen Ihre Sitzung abmelden, oder beenden Sie das Programm, alle aus dem Menü Datei. In der folgenden Tabelle werden die Unterschiede zwischen diesen Optionen erläutert.
  
|**Option**|**Zweck**|**Vorgehensweise**|
|:-----|:-----|:-----|
|Schließen  <br/> |Schließt die Anzeige, aber die Skype für Business-Sitzung identifiziert mit Ihrer Benutzer ID weiterhin ausgeführt werden können. Dies hat den Sinn, dass Sie weiterhin Benachrichtigungen erhalten und sich mit anderen austauschen können. <br/> <br/> Sie können die Anzeige jederzeit wieder durch Klicken auf die Skype Business-Symbol auf der Taskleiste oder im Infobereich am unteren Bildschirmrand abrufen.  <br/> | Führen Sie einen der folgenden Schritte aus, auf die Skype für Business-Hauptfenster: <br/> 1. Wählen Sie die Schaltfläche **Optionen** und dann wählen Sie **Datei** > **Schließen**.  <br/> 2. Klicken Sie in der oberen rechten Ecke des Fensters auf die Schaltfläche **Schließen** (X). <br/> |
|Abmelden  <br/> |Enden wird weiterhin die Sitzung mit Ihrer Benutzer-ID, aber Skype für Unternehmen im Hintergrund ausgeführt. Wenn Sie sich abmelden, wird das Abmeldefenster angezeigt.  <br/> **Tipp:** Wählen Sie **Meine Anmeldeinformationen löschen** beim Anmelden um den Datensatz Ihrer Anmelde-ID und das Kennwort vom Computer zu entfernen. Dies vereinfacht möglicherweise den Support bei der Behandlung von Anmeldeproblemen. Außerdem trägt es dazu bei, Ihre Anmeldeinformationen zu sichern, da es nicht autorisierten Benutzern so erschwert wird, sich mit Ihren Anmeldeinformationen anzumelden. <br/> |Klicken Sie auf die Skype für Business-Hauptfenster, wählen Sie die Schaltfläche **Optionen** , und wählen Sie **Datei** > **Abmelden**.  <br/> |
|Beenden  <br/> |Ihre Skype für Business-Sitzung beendet und Skype für Unternehmen auf Ihrem Computer Herunterfahren. Nach dem Beenden, wenn Sie neu starten möchten, wählen Sie **Start** > **Programme** > Skype für Unternehmen. <br/> |Klicken Sie auf die Skype für Business-Hauptfenster, wählen Sie die Schaltfläche **Optionen** , und wählen Sie **Datei** > **Beenden**.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Anmelden bei Skype for Business mit einer SmartCard

Einige Organisationen verwenden mittlerweile einen mehrstufigen Anmeldevorgang, der als zweistufige Authentifizierung bezeichnet wird, um die Sicherheit für ihre Benutzer zu erhöhen. Wenn Sie diese Option verwenden erwartet sind, benötigen Sie eine "Smartcard" zur Anmeldung bei Skype für Unternehmen. Smart-Karten können physische oder virtuelle werden:
  
- **Physische** Über die Größe einer Kreditkarte. Sie setzen sie für die Anmeldung in ein SmartCard-Lesegerät ein.
    
- **Virtuelle** Kein physisches Objekt, aber ein elektronisches Bezeichner, der in einem speziellen Chip auf Ihrem Computer geschrieben dient zum Abrufen der im Wesentlichen die Smartcard an Ihrem Computer erstellt. Verfügbar nur für die Verwendung mit Windows 8-Computer, auf denen den Chip TPM (Trusted Platform Module) enthalten.
    
### <a name="enroll-your-smart-card"></a>Registrieren Ihrer SmartCard

Bevor Sie sich mit einer Smartcard anmelden können, die Karte muss "registriert" – d. h., Ihre Anmeldeinformationen haben, mit der Karte identifiziert werden. Dies muss unabhängig davon erfolgen, ob es sich um eine physische oder um eine virtuelle Karte handelt. Dieser Prozess kann bereits wurde skalieren durch Ihre Skype für Business Server-Administrator ausgeführt. Wenn Sie nicht sicher sind, ob, ausgeführt wurde, überprüfen Sie mit diesen.
  
> [!NOTE]
> Da jede virtuelle Smartcard nur mit dem Gerät verbunden ist auf installiert ist, eine andere Karte für jeden Computer Windows 8 registriert werden, den Sie verwenden müssen. 
  
### <a name="to-manually-enroll-your-smart-card"></a>So registrieren Sie Ihre SmartCard

1. Melden Sie sich an dem Computer, den Sie Skype für Unternehmen auf ausgeführt werden, werden.
    
2. Navigieren Sie mithilfe von Internet Explorer auf Ihrer Organisation Certificate Authority Web-Registrierung. 
    
    Bitten Sie Ihre Skype für Business Server-Administrator für die Webadresse dieser Ressource, wenn Sie noch nicht vorhanden ist. Die URL sieht in etwa so aussehen: https://MyCA. [Yourcompanyname] .com/certsrv ein.
    
    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website im Kompatibilitätsmodus anzeigen. 
  
3. Wenn Sie aufgefordert werden, melden Sie sich auf der Seite Zertifizierungsstelle, melden Sie sich über die Verwendung von Ihr Domänenkonto ein (nicht als Administrator des Computers).
    
4. Wählen Sie auf der Begrüßungsseite die Option **Zertifikat anfordern** aus.
    
5. Wählen Sie **Erweiterte Anforderung** aus.
    
6. Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** und klicken Sie dann auf **Weiter**.
    
7. Jetzt sehen Sie eine Seite mit dem Namen Smartcard-Registrierungsstelle. Genehmigen Sie die Anfrage, das ActiveX-Steuerelement zu installieren, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    a. Wählen Sie in der Dropdownliste **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus.
    
    b. Wählen Sie **Neuen Schlüsselsatz erstellen** aus.
    
    c. Suchen Sie die Herstellerinformationen auf dem Etikett Ihrer SmartCard und wählen Sie dann den betreffenden Hersteller in der **CSP**-Dropdownliste aus.
    
    d. Wählen Sie **CSP** als das Format anfordern, wenn er nicht bereits ausgewählt ist.
    
    e. Wählen Sie aus der Dropdownliste Hashalgorithmus **sha1** aus, wenn es nicht bereits ausgewählt ist.
    
    f. Benennen Sie Ihr Zertifikat Sie erkennen, und klicken Sie auf **Absenden**.
    
8. Legen Sie jetzt Ihre leere SmartCard in das an die Registrierungsstelle angeschlossene SmartCard-Lesegerät und klicken Sie auf **Registrieren**.
    
9. Wenn Sie dazu aufgefordert werden, geben Sie Ihre PIN (Personal Identification Number) ein und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Wenn der für Sie zuständige Mitarbeiter des technischen Supports Ihnen keine besondere PIN für die Registrierung Ihrer SmartCard gegeben hat, verwenden Sie die Standard-PIN für SmartCards, nämlich 12345678. 
  
10. Aktivieren Sie die Option, die den Benutzer (Sie) zwingt, die PIN bei der ersten Verwendung der SmartCard zu ändern.
    
11. Legen Sie jetzt Ihre leere SmartCard in das an die Registrierungsstelle angeschlossene SmartCard-Lesegerät und klicken Sie auf **Registrieren**.
    
12. Wenn Sie dazu aufgefordert werden, geben Sie Ihre PIN (Personal Identification Number) ein und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Wenn der für Sie zuständige Mitarbeiter des technischen Supports Ihnen keine besondere PIN für die Registrierung Ihrer SmartCard gegeben hat, verwenden Sie die Standard-PIN für SmartCards, nämlich 12345678. 
  
13. Aktivieren Sie die Option, die den Benutzer (Sie) zwingt, die PIN bei der ersten Verwendung der SmartCard zu ändern.
    
14. Klicken Sie auf **OK**, um zu bestätigen, dass das angezeigte Zertifikat Ihre Informationen enthält.
    
15. Sobald der Hinweis angezeigt wird, dass das Zertifikat ausgestellt wurde, klicken Sie auf **Dieses Zertifikat installieren**, um den Registrierungsvorgang abzuschließen.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Anmelden bei Skype for Business mit Ihren SmartCard-Anmeldeinformationen

Bevor Sie die Smartcard zum ersten Mal verwenden, wird empfohlen, dass Sie auf die Skype für Business-Anmeldeseite **Meine Info - Anmeldung löschen** klicken. Dadurch werden alle eventuell auf dem Computer gespeicherten Anmeldeinformationen gelöscht und eine mögliche Fehlerquelle ausgeschaltet.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>So melden Sie sich bei Skype for Business mit Ihren SmartCard-Anmeldeinformationen an

1. Starten Sie die Skype für Business-Client.
    
2. Geben Sie auf dem Anmeldebildschirm Ihren Benutzerkontonamen für die Anmeldung im Feld **Anmeldeadresse** ein und klicken Sie dann auf **Anmelden**.
    
3. Wenn Sie eine virtuelle SmartCard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische SmartCard verwenden, legen Sie die SmartCard in Ihr SmartCard-Lesegerät ein, wenn Sie dazu aufgefordert werden, und klicken dann auf **OK**, wenn die Karte erkannt wird.
    
4. Geben Sie die PIN-Nummer für Ihre SmartCard ein und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Wenn Ihnen keine SmartCard-PIN von Ihrem Supportmitarbeiter zugewiesen wurde, verwenden Sie den Standardwert, nämlich 12345678. 
  
## <a name="see-also"></a>Siehe auch

[Verwalten der zweistufigen Authentifizierung in Skype für Business Server](two-factor-authentication.md)
  
[Konfigurieren der zweistufigen Authentifizierung in Skype für Business Server](configure-two-factor.md)
