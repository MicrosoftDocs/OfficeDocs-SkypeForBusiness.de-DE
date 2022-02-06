---
title: Verwenden der zweistufigen Authentifizierung mit Skype for Business Client und Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Zusammenfassung: Verwenden Sie die zweistufige Authentifizierung mit Skype for Business Server und Skype for Business.'
---

# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Verwenden der zweistufigen Authentifizierung mit Skype for Business Client und Skype for Business Server
 
**Zusammenfassung:** Verwenden Sie die zweistufige Authentifizierung mit Skype for Business Server und Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Erstmalige Anmeldung bei Skype for Business

Ihre Anmeldeinformationen werden in der Regel automatisch konfiguriert, wenn Skype for Business installiert wird. Wenn Sie jedoch Skype for Business zum ersten Mal verwenden, müssen Sie den Client möglicherweise manuell starten.
  
### <a name="to-sign-in-for-the-first-time"></a>So melden Sie sich zum ersten Mal an

1. Melden Sie sich beim Netzwerk Ihrer Organisation an.
    
2. Wählen Sie **"Alle Programme** >  **starten** >  **Skype for Business**.
    
    Der Anmeldebildschirm sollte angezeigt werden.
    
    - Wenn das Anmeldeadressenfeld bereits ausgefüllt ist, vergewissern Sie sich, dass die angezeigte Adresse korrekt ist.
    
    - Wenn dies nicht korrekt ist oder das Feld leer ist, geben Sie Ihre Anmeldeadresse ein (dies entspricht normalerweise Ihrer E-Mail-Adresse).
    
    - Wenn ein leeres Kennwortfeld angezeigt wird, fügen Sie Ihr Kennwort hinzu.
    
3. Wählen Sie **"Anmelden" aus**.
    
## <a name="sign-out-of-skype-for-business"></a>Abmelden von Skype for Business

Wenn Sie die Verwendung von Skype for Business abgeschlossen haben, können Sie die Anzeige schließen, sich von Ihrer Sitzung abmelden oder das Programm beenden, alles über das Menü "Datei". In der folgenden Tabelle werden die Unterschiede bei den Optionen erläutert.
  
|**Option**|**Funktion der Einstellung**|**So führen Sie dies aus**|
|:-----|:-----|:-----|
|Schließen  <br/> |Schließt die Anzeige, lässt die mit Ihrer Benutzer-ID identifizierte Skype for Business Sitzung jedoch weiter ausgeführt werden. Auf diese Weise können Sie weiterhin Benachrichtigungen erhalten und mit anderen interagieren. <br/> <br/> Sie können die Anzeige jederzeit wieder abrufen, indem Sie auf der Taskleiste oder im Benachrichtigungsbereich am unteren Rand des Bildschirms auf das symbol Skype for Business klicken.  <br/> | Führen Sie im Skype for Business Hauptfenster eine der folgenden Aktionen aus: <br/> 1. Wählen Sie die Schaltfläche **"Optionen**" und dann **"****FileClose** > " aus.  <br/> 2. Klicken Sie auf die Schaltfläche " **Schließen** " (X) in der oberen rechten Ecke des Fensters. <br/> |
|Abmelden  <br/> |Beendet die Sitzung, die Ihrer Benutzer-ID zugeordnet ist, aber Skype for Business wird weiterhin im Hintergrund ausgeführt. Wenn Sie sich abmelden, wird das Anmeldefenster angezeigt.  <br/> **Tipp:** Wählen Sie **"Meine Anmeldeinformationen löschen** " aus, wenn Sie sich abmelden, um den Datensatz Ihrer Anmelde-ID und ihres Kennworts vom Computer zu entfernen. Auf diese Weise kann es für Supportmitarbeiter einfacher sein, Anmeldeprobleme zu beheben. Es kann auch dazu beitragen, dass Ihre Anmeldeinformationen sicherer sind, indem es nicht autorisierten Benutzern erschwert wird, sich mit Ihren Anmeldeinformationen anzumelden. <br/> |Wählen Sie im Skype for Business Hauptfenster die Schaltfläche **"Optionen**" und dann "**FileSign** >  **Out" aus**.  <br/> |
|Beenden  <br/> |Beendet die Skype for Business Sitzung und beendet Skype for Business auf Ihrem Computer. Wenn Sie nach dem Beenden neu starten möchten, wählen Sie **"StartAll** >  Programs > Skype for Business" **aus**. <br/> |Wählen Sie im Skype for Business Hauptfenster die Schaltfläche **"Optionen"** und dann **"****FileExit** > " aus.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Anmelden bei Skype for Business mit einer Smartcard

Einige Organisationen verwenden jetzt einen mehrstufigen Anmeldeprozess, der als zweistufige Authentifizierung bezeichnet wird, um die Sicherheit für ihre Benutzer zu erhöhen. Wenn Sie diese Option verwenden sollten, benötigen Sie eine "Smartcard", um sich bei Skype for Business anzumelden. Smartcards können entweder physisch oder virtuell sein:
  
- **Physischen** Informationen zur Größe einer Kreditkarte. Sie fügen sie bei der Anmeldung in einen Smartcardleser ein.
    
- **Virtuellen** Kein physisches Objekt, sondern ein elektronischer Bezeichner, der auf einen speziellen Chip auf Ihrem Computer geschrieben wird, der im Wesentlichen die Smartcard in Ihren Computer einfügt. Nur für die Verwendung mit Windows 8 Computern verfügbar, die den TPM-Chip (Trusted Platform Module) enthalten.
    
### <a name="enroll-your-smart-card"></a>Registrieren Ihrer Smartcard

Bevor Sie sich mit einer Smartcard anmelden können, muss die Karte "registriert" sein, d. h., Ihre Benutzeranmeldeinformationen müssen mit der Karte identifiziert werden. Dies ist der Fall, unabhängig davon, ob die Karte physisch oder virtuell ist. Dieser Vorgang wurde möglicherweise bereits von Ihrem Skype for Business Server-Administrator ausgeführt. Wenden Sie sich an sie, wenn Sie nicht sicher sind, ob dies geschehen ist.
  
> [!NOTE]
> Da jede virtuelle Smartcard nur dem Gerät zugeordnet ist, auf dem sie installiert ist, muss für jeden verwendeten Windows 8 Computer eine separate Karte registriert werden. 
  
### <a name="to-manually-enroll-your-smart-card"></a>So registrieren Sie Ihre Smartcard manuell

1. Melden Sie sich bei dem Computer an, auf dem Sie Skype for Business ausführen.
    
2. Navigieren Sie mit Internet Explorer zur Registrierungsseite der Zertifizierungsstelle Ihrer Organisation. 
    
    Fragen Sie Ihren Skype for Business Server-Administrator nach der Webadresse dieser Ressource, wenn Sie sie noch nicht haben. Die URL sieht ungefähr wie folgt aus: https://MyCA.[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen. 
  
3. Wenn Sie aufgefordert werden, sich bei der Zertifizierungsseite anzumelden, melden Sie sich mit Ihrem Domänenkonto an (statt als Administrator Ihres Computers).
    
4. Wählen Sie auf der Willkommensseite der Website die Option **"Zertifikat anfordern**" aus.
    
5. Wählen Sie **"Erweiterte Anforderung**" aus.
    
6. Wählen Sie **"Erstellen" aus, und senden Sie eine Anforderung an diese Zertifizierungsstelle**, und klicken Sie dann auf **"Weiter**".
    
7. Jetzt wird eine Seite mit dem Namen Smartcard-Registrierungsstation angezeigt. Genehmigen Sie die Anforderung zum Installieren des ActiveX-Steuerelements, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    a. Wählen Sie in der Dropdownliste "**Zertifikatvorlage**" den **Smartcard-Benutzer** aus.
    
    b. Wählen Sie **"Neuen Schlüsselsatz erstellen" aus**.
    
    c. Suchen Sie die Herstellerinformationen auf der Bezeichnung Ihrer Smartcard, und wählen Sie diesen Hersteller aus der **CSP-Dropdownliste** aus.
    
    d. Wählen Sie **CSP** als Anforderungsformat aus, wenn es noch nicht ausgewählt ist.
    
    e. Wählen Sie **sha1** aus der Dropdownliste "Hashalgorithmus" aus, wenn sie noch nicht ausgewählt ist.
    
    f. Geben Sie Ihrem Zertifikat einen Namen, den Sie erkennen werden, und klicken Sie auf **"Absenden**".
    
8. Fügen Sie nun Ihre leere Smartcard in den Kartenleser ein, der an die Registrierungsstation angefügt ist, und klicken Sie auf **"Registrieren**".
    
9. Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **"OK**".
    
    > [!NOTE]
    > Wenn Ihr technischer Supportmitarbeiter Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard gegeben hat, verwenden Sie den Standardmäßige Smartcard-PIN-Wert, der 12345678 ist. 
  
10. Wählen Sie die Option aus, um zu erzwingen, dass der Benutzer (Sie) die PIN bei der ersten Verwendung der Smartcard ändert.
    
11. Fügen Sie nun Ihre leere Smartcard in den Kartenleser ein, der an die Registrierungsstation angefügt ist, und klicken Sie auf **"Registrieren**".
    
12. Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **"OK**".
    
    > [!NOTE]
    > Wenn Ihr technischer Supportmitarbeiter Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard gegeben hat, verwenden Sie den Standardmäßige Smartcard-PIN-Wert, der 12345678 ist. 
  
13. Wählen Sie die Option aus, um zu erzwingen, dass der Benutzer (Sie) die PIN bei der ersten Verwendung der Smartcard ändert.
    
14. Klicken Sie auf **"OK** ", um zu bestätigen, dass das angezeigte Zertifikat Ihre Informationen enthält.
    
15. Nachdem Sie den Hinweis angezeigt haben, dass das Zertifikat ausgestellt wurde, klicken Sie auf **"Dieses Zertifikat installieren** ", um den Registrierungsprozess abzuschließen.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Melden Sie sich mit Ihren Smartcard-Anmeldeinformationen bei Skype for Business an.

Bevor Sie Ihre Smartcard zum ersten Mal verwenden, sollten Sie auf der Anmeldeseite Skype for Business auf **"Meine Anmeldeinformationen löschen**" klicken. Dadurch werden alle anmeldeinformationen gelöscht, die auf Ihrem Computer gespeichert sind, und eine mögliche Fehlerquelle wird eliminiert.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>So melden Sie sich mit Ihren Smartcard-Anmeldeinformationen bei Skype for Business an

1. Starten Sie den Skype for Business-Client.
    
2. Geben Sie auf dem Anmeldebildschirm den Benutzernamen des Anmeldebenutzerkontos in das **Feld "Anmeldeadresse** " ein, und klicken Sie dann auf **"Anmelden**".
    
3. Wenn Sie eine virtuelle Smartcard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische Smartcard verwenden, fügen Sie die Smartcard in Ihren Smartcardleser ein, und klicken Sie dann auf **"OK** ", wenn die Karte erkannt wird.
    
4. Geben Sie die PIN-Nummer für Ihre Smartcard ein, und klicken Sie dann auf **"OK**".
    
    > [!NOTE]
    > Wenn Ihrem Supportmitarbeiter keine Smartcard-PIN-Nummer zugewiesen wurde, verwenden Sie den Standardwert, der 12345678 ist. 
  
## <a name="see-also"></a>Siehe auch

[Verwalten der zweistufigen Authentifizierung in Skype for Business Server](two-factor-authentication.md)
  
[Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server](configure-two-factor.md)
