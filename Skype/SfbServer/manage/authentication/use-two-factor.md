---
title: Verwenden der zweistufigen Authentifizierung mit dem Skype for Business-Client und Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 'Zusammenfassung: Verwenden Sie die zweistufige Authentifizierung mit Skype for Business Server und Skype for Business.'
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806539"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>Verwenden der zweistufigen Authentifizierung mit dem Skype for Business-Client und Skype for Business Server
 
**Zusammenfassung:** Verwenden Sie die zweistufige Authentifizierung mit Skype for Business Server und Skype for Business.
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Zum ersten Mal bei Skype for Business anmelden

Ihre Anmeldeinformationen werden in der Regel automatisch konfiguriert, wenn Skype for Business installiert wird. Bei der ersten Verwendung von Skype for Business müssen Sie den Client jedoch möglicherweise manuell starten.
  
### <a name="to-sign-in-for-the-first-time"></a>So melden Sie sich zum ersten Mal an

1. Melden Sie sich beim Netzwerk Ihrer Organisation an.
    
2. Wählen **Sie**  >  **"Alle Programme**  >  **starten" skype for Business aus.**
    
    Der Anmeldebildschirm sollte angezeigt werden.
    
    - Wenn das Anmeldeadressenfeld bereits ausgefüllt ist, vergewissern Sie sich, dass die angezeigte Adresse richtig ist.
    
    - Wenn dies nicht korrekt ist oder das Feld leer ist, geben Sie Ihre Anmeldeadresse ein (in der Regel identisch mit Ihrer E-Mail-Adresse).
    
    - Wenn ein leeres Kennwortfeld angezeigt wird, fügen Sie Ihr Kennwort hinzu.
    
3. Select **Sign-in**.
    
## <a name="sign-out-of-skype-for-business"></a>Abmelden bei Skype for Business

Wenn Sie Skype for Business verwendet haben, können Sie die Anzeige schließen, sich von Ihrer Sitzung abmelden oder das Programm beenden, alles über das Menü "Datei". In der folgenden Tabelle werden die Unterschiede in den Optionen erläutert.
  
|**Option**|**Funktion der Einstellung**|**So führen Sie dies aus**|
|:-----|:-----|:-----|
|Schließen  <br/> |Schließt Die Anzeige wird geschlossen, aber die Skype for Business-Sitzung, die mit Ihrer Benutzer-ID identifiziert wurde, kann weiterhin ausgeführt werden. Dies ist so, dass Sie weiterhin Benachrichtigungen erhalten und mit anderen interagieren können. <br/> <br/> Sie können die Anzeige jederzeit wieder anzeigen, indem Sie auf der Taskleiste auf das Skype for Business-Symbol oder den Benachrichtigungsbereich am unteren Rand des Bildschirms klicken.  <br/> | Führen Sie im Hauptfenster von Skype for Business eine der folgenden Schritte aus: <br/> 1. Wählen Sie die Schaltfläche **"Optionen"** und dann **"Datei**  >  **schließen" aus.**  <br/> 2. Klicken Sie **in** der oberen rechten Ecke des Fensters auf die Schaltfläche "Schließen" (X). <br/> |
|Abmelden  <br/> |Beendet die Ihrer Benutzer-ID zugeordnete Sitzung, Skype for Business wird jedoch weiterhin im Hintergrund ausgeführt. Wenn Sie sich abmelden, wird das Anmeldefenster angezeigt.  <br/> **Tipp:** Wählen **Sie "Meine Anmeldeinformationen löschen" aus,** wenn Sie sich abmelden, um den Eintrag Ihrer Anmelde-ID und des Kennworts vom Computer zu entfernen. Dies erleichtert support Personen möglicherweise die Problembehandlung bei der Anmeldung. Sie kann auch dazu beitragen, die Sicherheit Ihrer Anmeldeinformationen zu gewährleisten, da nicht autorisierte Benutzer sich mit Ihren Anmeldeinformationen nur schwer anmelden können. <br/> |Wählen Sie im Hauptfenster von Skype for Business die Schaltfläche **"Optionen"** und dann **"Datei**  >  **abmelden" aus.**  <br/> |
|Beenden  <br/> |Beendet Ihre Skype for Business-Sitzung und beendet Skype for Business auf Ihrem Computer. Wenn Sie nach dem Beenden einen Neustart wünschen, wählen Sie **"Alle**  >  **Programme >** Skype for Business starten" aus. <br/> |Wählen Sie im Hauptfenster von Skype for Business die Schaltfläche **"Optionen"** und dann **"Datei**  >  **beenden" aus.**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>Anmelden bei Skype for Business mit einer Smartcard

Einige Organisationen verwenden jetzt einen mehrstufigen Anmeldevorgang, der als zweistufige Authentifizierung bezeichnet wird, um die Sicherheit für ihre Benutzer zu erhöhen. Wenn Sie diese Option verwenden möchten, benötigen Sie eine "Smartcard", um sich bei Skype for Business anmelden zu können. Smartcards können entweder physisch oder virtuell sein:
  
- **Physisch** Informationen zur Größe einer Kreditkarte. Sie fügen sie bei der Anmeldung in ein Smartcardlesegerät ein.
    
- **Virtuell** Kein physisches Objekt, sondern eine elektronische ID, die auf einen speziellen Chip auf Ihrem Computer geschrieben wird, der im Wesentlichen die Smartcard in Ihren Computer einschleiert. Nur für die Verwendung mit Windows 8, die den TPM (Trusted Platform Module)-Chip enthalten.
    
### <a name="enroll-your-smart-card"></a>Registrieren Ihrer Smartcard

Bevor Sie sich mit einer Smartcard anmelden können, muss die Karte "registriert" werden, d. h., Ihre Benutzeranmeldeinformationen müssen mit der Karte identifiziert werden. Dies ist der Fall, unabhängig davon, ob die Karte physisch oder virtuell ist. Dieser Vorgang wurde möglicherweise bereits von Ihrem Skype for Business Server-Administrator ausgeführt. Überprüfen Sie diese, wenn Sie nicht sicher sind, ob dies geschehen ist.
  
> [!NOTE]
> Da jede virtuelle Smartcard nur dem Gerät zugeordnet ist, auf dem sie installiert ist, muss für jeden verwendeten Windows 8 eine separate Karte registriert werden. 
  
### <a name="to-manually-enroll-your-smart-card"></a>So registrieren Sie Ihre Smartcard manuell

1. Melden Sie sich an dem Computer an, auf dem Skype for Business ausgeführt wird.
    
2. Navigieren Sie mithilfe von Internet Explorer zur Seite "Registrierung der Zertifizierungsstelle". 
    
    Fragen Sie Ihren Skype for Business Server-Administrator nach der Webadresse dieser Ressource, wenn Sie sie noch nicht haben. Die URL sieht in etwa wie die folgende aus: https://MyCA .[ yourcompanyname].com/certsrv.
    
    > [!NOTE]
    > Wenn Sie ein Internet Explorer 10, müssen Sie diese Website möglicherweise im Kompatibilitätsmodus anzeigen. 
  
3. Wenn Sie aufgefordert werden, sich bei der Zertifizierungsseite zu anmelden, melden Sie sich mit Ihrem Domänenkonto an (und nicht als Administrator Ihres Computers).
    
4. Wählen Sie auf der Willkommensseite der Website **"Zertifikat anfordern" aus.**
    
5. Select **Advanced Request**.
    
6. Wählen **Sie "Erstellen" aus, und senden Sie eine Anforderung an diese Zertifizierungsstelle,** und klicken Sie dann auf **"Weiter".**
    
7. Jetzt wird die Seite "Smart Card Enrollment Station" angezeigt. Genehmigen Sie die Anforderung zum Installieren ActiveX Steuerelements, und füllen Sie dann das Formular für die erweiterte Zertifikatanforderung wie folgt aus:
    
    a. Wählen **Sie in der Dropdownliste** **"Zertifikatvorlage" den Smartcardbenutzer** aus.
    
    b. Wählen Sie **"Neuen Schlüsselsatz erstellen" aus.**
    
    c. Suchen Sie die Herstellerinformationen auf der Bezeichnung Ihrer Smartcard, und wählen Sie diesen Hersteller aus der **#A0** aus.
    
    d. Wählen **Sie CSP** als Anforderungsformat aus, wenn es noch nicht ausgewählt ist.
    
    e. Wählen **Sie "sha1"** aus der Dropdownliste "Hashalgorithmus" aus, falls noch nicht ausgewählt.
    
    f. Geben Sie Ihrem Zertifikat einen Namen, den Sie erkennen, und klicken Sie auf **"Absenden".**
    
8. Fügen Sie nun Ihre leere Smartcard in den Kartenleser ein, der der Registrierungsstation zugeordnet ist, und klicken Sie auf **"Registrieren".**
    
9. Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **"OK".**
    
    > [!NOTE]
    > Wenn Ihr Technischer Support Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard zur Verfügung steht, verwenden Sie den standardmäßigen Smartcard-PIN-Wert, der 12345678 ist. 
  
10. Wählen Sie die Option aus, um den Benutzer (Sie) zu zwingen, die PIN bei der ersten Verwendung der Smartcard zu ändern.
    
11. Fügen Sie nun Ihre leere Smartcard in den Kartenleser ein, der der Registrierungsstation zugeordnet ist, und klicken Sie auf **"Registrieren".**
    
12. Wenn Sie dazu aufgefordert werden, geben Sie Ihre persönliche Identifikationsnummer (PIN) ein, und klicken Sie dann auf **"OK".**
    
    > [!NOTE]
    > Wenn Ihr Technischer Support Ihnen keine spezielle PIN für die Registrierung Ihrer Smartcard zur Verfügung steht, verwenden Sie den standardmäßigen Smartcard-PIN-Wert, der 12345678 ist. 
  
13. Wählen Sie die Option aus, um den Benutzer (Sie) zu zwingen, die PIN bei der ersten Verwendung der Smartcard zu ändern.
    
14. Klicken **Sie auf "OK",** um zu bestätigen, dass das angezeigte Zertifikat Ihre Informationen enthält.
    
15. Sobald Der Hinweis angezeigt wird, dass das Zertifikat ausgestellt wurde, klicken Sie auf "Dieses **Zertifikat installieren",** um den Registrierungsprozess abzuschließen.
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>Melden Sie sich mit Ihren Smartcardanmeldeinformationen bei Skype for Business an.

Bevor Sie Ihre Smartcard zum ersten Mal verwenden, empfiehlt es sich, auf der Skype for **Business-Anmeldeseite** auf "Meine Anmeldeinformationen löschen" zu klicken. Dadurch werden alle anmeldeinformationen, die auf Ihrem Computer gespeichert sind, entfernt und eine mögliche Fehlerquelle beseitigt.
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>So melden Sie sich mit Ihren Smartcardanmeldeinformationen bei Skype for Business an

1. Starten Sie den Skype for Business-Client.
    
2. Geben Sie auf dem Anmeldebildschirm den Namen Ihres Anmeldebenutzerkontos in das Feld **"Anmeldeadresse"** ein, und klicken Sie dann **auf "Anmelden".**
    
3. Wenn Sie eine virtuelle Smartcard verwenden, überspringen Sie diesen Schritt.
    
    Wenn Sie eine physische Smartcard verwenden, fügen Sie die Smartcard in Das Smartcardleser ein, und klicken Sie dann auf **OK,** wenn die Karte erkannt wird.
    
4. Geben Sie die PIN ein, die Sie für Ihre Smartcard verwenden möchten, und klicken Sie dann auf **"OK".**
    
    > [!NOTE]
    > Wenn Ihnen von Ihrer Supportperson keine Smartcard-PIN-Nummer zugewiesen wurde, verwenden Sie den Standardwert 12345678. 
  
## <a name="see-also"></a>Weitere Informationen

[Verwalten der zweistufigen Authentifizierung in Skype for Business Server](two-factor-authentication.md)
  
[Konfigurieren der zweistufigen Authentifizierung in Skype for Business Server](configure-two-factor.md)
