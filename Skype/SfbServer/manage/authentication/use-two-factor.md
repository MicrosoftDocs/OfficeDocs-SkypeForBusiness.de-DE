---
title: Verwenden der zweistufigen Authentifizierung mit Skype for Business-Client und Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Zusammenfassung: Verwenden Sie die zweistufige Authentifizierung mit Skype for Business Server und Skype for Business.'
ms.openlocfilehash: 532e7567444b78dd30d053cf91aef1c10f0970bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286109"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Verwenden der zweistufigen Authentifizierung mit Skype for Business-Client und Skype for Business Server
 
**Zusammenfassung:** Verwenden Sie die zweistufige Authentifizierung mit Skype for Business Server und Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Erstmaliges Anmelden bei Skype for Business

Ihre Anmeldeinformationen werden in der Regel automatisch konfiguriert, wenn Skype for Business installiert ist. Wenn Sie Skype for Business zum ersten Mal verwenden, müssen Sie den Client möglicherweise manuell starten.
  
### <a name="to-sign-in-for-the-first-time"></a>So melden Sie sich erstmalig an

1. Melden Sie sich beim Netzwerk Ihrer Organisation an.
    
2. Wählen Sie**Alle Programme** >  **starten** > **Skype for Business**aus.
    
    Der Anmeldebildschirm wird angezeigt.
    
    - Wenn das Feld mit der Anmeldeadresse bereits ausgefüllt ist, überprüfen Sie, ob die angezeigte Adresse richtig ist.
    
    - Wenn dies nicht der Fall ist, oder wenn das Feld leer ist, geben Sie Ihre Anmeldeadresse ein (Dies ist in der Regel identisch mit Ihrer e-Mail-Adresse).
    
    - Wenn ein leeres Kennwortfeld angezeigt wird, geben Sie Ihr Kennwort ein.
    
3. Wählen Sie **Anmelden** aus.
    
## <a name="sign-out-of-skype-for-business"></a>Abmelden von Skype for Business

Wenn Sie mit der Verwendung von Skype for Business fertig sind, können Sie die Anzeige schließen, sich von Ihrer Sitzung abmelden oder das Programm beenden, und zwar alle aus dem Menü "Datei". In der folgenden Tabelle werden die Unterschiede zwischen diesen Optionen erläutert.
  
|**Option**|**Zweck**|**Vorgehensweise**|
|:-----|:-----|:-----|
|Schließen  <br/> |Schließt die Anzeige, lässt aber die Skype for Business-Sitzung, die mit Ihrer Benutzer-ID identifiziert wurde, weiterhin ausgeführt. Dies hat den Sinn, dass Sie weiterhin Benachrichtigungen erhalten und sich mit anderen austauschen können. <br/> <br/> Sie können die Anzeige jederzeit wiederherstellen, indem Sie auf das Skype for Business-Symbol in der Taskleiste oder im Infobereich am unteren Rand des Bildschirms klicken.  <br/> | Führen Sie im Hauptfenster von Skype for Business eine der folgenden Aktionen aus: <br/> 1. Wählen Sie die Schaltfläche **Optionen** und dann **Datei** > **Schließen**aus.  <br/> 2. Klicken Sie in der oberen rechten Ecke des Fensters auf die Schaltfläche **Schließen** (X). <br/> |
|Abmelden  <br/> |Beendet die mit Ihrer Benutzer-ID verknüpfte Sitzung, aber Skype for Business wird weiterhin im Hintergrund ausgeführt. Wenn Sie sich abmelden, wird das Abmeldefenster angezeigt.  <br/> **Tipp:** Wählen Sie **Meine Anmeldeinformationen löschen** aus, wenn Sie sich abmelden, um den Eintrag Ihrer Anmelde-ID und Ihres Kennworts vom Computer zu entfernen. Dies vereinfacht möglicherweise den Support bei der Behandlung von Anmeldeproblemen. Außerdem trägt es dazu bei, Ihre Anmeldeinformationen zu sichern, da es nicht autorisierten Benutzern so erschwert wird, sich mit Ihren Anmeldeinformationen anzumelden. <br/> |Wählen Sie im Hauptfenster von Skype for Business die Schaltfläche **Optionen** und dann **Datei** > **Abmelden aus**.  <br/> |
|Beenden  <br/> |Beendet Ihre Skype for Business-Sitzung und beendet Skype for Business auf Ihrem Computer. Wenn Sie nach dem Beenden erneut starten möchten, wählen Sie **** > **Alle Programme** > Skype for Business starten aus. <br/> |Wählen Sie im Hauptfenster von Skype for Business die Schaltfläche **Optionen** und dann **Datei** > **Beenden**aus.  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Anmelden bei Skype for Business mit einer SmartCard

Einige Organisationen verwenden mittlerweile einen mehrstufigen Anmeldevorgang, der als zweistufige Authentifizierung bezeichnet wird, um die Sicherheit für ihre Benutzer zu erhöhen. Wenn Sie davon ausgehen, dass Sie diese Option verwenden, benötigen Sie eine "Smartcard", um sich bei Skype for Business anmelden zu können. Smartcards können entweder physisch oder virtuell sein:
  
- **Physisch** Über die Größe einer Kreditkarte. Sie setzen sie für die Anmeldung in ein SmartCard-Lesegerät ein.
    
- **Virtuelles** Kein physikalisches Objekt, sondern ein elektronischer Bezeichner, der auf einen speziellen Chip auf dem Computer geschrieben wird, der im Wesentlichen die Smartcard auf Ihren Computer aufbaut. Nur für die Verwendung mit Windows 8-Computern verfügbar, die den TPM-Chip (Trusted Platform Module) enthalten.
    
### <a name="enroll-your-smart-card"></a>Registrieren Ihrer SmartCard

Bevor Sie sich mit einer Smartcard anmelden können, muss die Karte "registriert" sein, d. h., Ihre Benutzeranmeldeinformationen müssen mit der Karte identifiziert werden. Dies muss unabhängig davon erfolgen, ob es sich um eine physische oder um eine virtuelle Karte handelt. Dieser Vorgang wurde möglicherweise bereits von Ihrem Skype for Business Server-Administrator durchgeführt. Wenn Sie sich nicht sicher sind, ob dies geschehen ist, wenden Sie sich an Sie.
  
> [!NOTE]
> Da jede virtuelle Smartcard nur dem Gerät zugeordnet ist, auf dem Sie installiert ist, muss für jeden Windows 8-Computer, den Sie verwenden, eine separate Karte registriert werden. 
  
### <a name="to-manually-enroll-your-smart-card"></a>So registrieren Sie Ihre SmartCard

1. Melden Sie sich bei dem Computer an, auf dem Sie Skype for Business ausführen.
    
2. Navigieren Sie in Internet Explorer zur Seite Zertifizierungsstellen-Webregistrierung Ihrer Organisation. 
    
    Bitten Sie Ihren Skype for Business Server-Administrator um die Webadresse dieser Ressource, wenn Sie Sie nicht bereits haben. Die URL sieht ungefähr wie folgt aus: https://MyCA [YourCompanyName]. com/certsrv.
    
    > [!NOTE]
    > Wenn Sie Internet Explorer 10 verwenden, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen. 
  
3. Wenn Sie aufgefordert werden, sich bei der Zertifizierungsseite anzumelden, melden Sie sich mit Ihrem Domänenkonto an (und nicht als Administrator Ihres Computers).
    
4. Wählen Sie auf der Begrüßungsseite die Option **Zertifikat anfordern** aus.
    
5. Wählen Sie **Erweiterte Anforderung** aus.
    
6. Wählen Sie **Eine Anforderung an diese Zertifizierungsstelle erstellen und einreichen** und klicken Sie dann auf **Weiter**.
    
7. Nun wird eine Seite mit der Bezeichnung Smartcard-Registrierungsstelle angezeigt. Genehmigen Sie die Anfrage, das ActiveX-Steuerelement zu installieren, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    a. Wählen Sie in der Dropdownliste **Zertifikatvorlage** den Eintrag **SmartCard-Benutzer** aus.
    
    b. Wählen Sie **Neuen Schlüsselsatz erstellen** aus.
    
    c. Suchen Sie die Herstellerinformationen auf dem Etikett Ihrer SmartCard und wählen Sie dann den betreffenden Hersteller in der **CSP**-Dropdownliste aus.
    
    d. Wählen Sie **CSP** als Anforderungs Format aus, falls es noch nicht ausgewählt ist.
    
    e. Wählen Sie in der Dropdownliste Hash Algorithmus die Option **SHA1** aus, wenn diese noch nicht ausgewählt ist.
    
    f. Geben Sie Ihrem Zertifikat einen Namen, den Sie erkennen, **** und klicken Sie auf Absenden.
    
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

Bevor Sie Ihre Smartcard zum ersten Mal verwenden, sollten Sie auf der Skype for Business-Anmeldeseite auf **Meine Anmeldeinformationen löschen** klicken. Dadurch werden alle eventuell auf dem Computer gespeicherten Anmeldeinformationen gelöscht und eine mögliche Fehlerquelle ausgeschaltet.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>So melden Sie sich bei Skype for Business mit Ihren SmartCard-Anmeldeinformationen an

1. Starten Sie den Skype for Business-Client.
    
2. Geben Sie auf dem Anmeldebildschirm Ihren Benutzerkontonamen für die Anmeldung im Feld **Anmeldeadresse** ein und klicken Sie dann auf **Anmelden**.
    
3. Wenn Sie eine virtuelle SmartCard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische SmartCard verwenden, legen Sie die SmartCard in Ihr SmartCard-Lesegerät ein, wenn Sie dazu aufgefordert werden, und klicken dann auf **OK**, wenn die Karte erkannt wird.
    
4. Geben Sie die PIN-Nummer für Ihre SmartCard ein und klicken Sie dann auf **OK**.
    
    > [!NOTE]
    > Wenn Ihnen keine SmartCard-PIN von Ihrem Supportmitarbeiter zugewiesen wurde, verwenden Sie den Standardwert, nämlich 12345678. 
  
## <a name="see-also"></a>Siehe auch

[Verwalten der zweistufigen Authentifizierung in Skype for Business Server](two-factor-authentication.md)
  
[Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server](configure-two-factor.md)
