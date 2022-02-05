---
title: Installieren und Testen Skype for Business für Windows Phone
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 'Zusammenfassung: Erfahren Sie, wie Sie Skype for Business auf Ihrem Windows Phone installieren und testen.'
---

# <a name="install-and-test-skype-for-business-for-windows-phone"></a>Installieren und Testen Skype for Business für Windows Phone
 
**Zusammenfassung:** Erfahren Sie, wie Sie Skype for Business auf Ihrem Windows Phone installieren und testen.
  
Die Skype for Business für Windows Phone-App bietet Skype for Business Anwesenheits-, Chat- und Sprach- und Videoanrufe auf Windows mobilen Geräten. Benutzer mit Lync 2013 erhalten die aktualisierte App entweder automatisch oder werden je nach Benutzereinstellungen aufgefordert, sie manuell zu aktualisieren. Neue Benutzer können es aus dem [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901) herunterladen. Die Skype for Business für Windows Phone-App ist nur ab Windows Phone Version 8.1 verfügbar.
  
Bevor Sie Benutzer in Ihrer Organisation zum Herunterladen der App anweist, sollten Sie die folgenden Tests ausführen, um sicherzustellen, dass sie ordnungsgemäß in Ihre Umgebung integriert ist. 
  
## <a name="install-skype-for-business-windows-phone-81"></a>Installieren Skype for Business Windows Phone 8.1

1. Navigieren Sie zu [Windows Phone 8 Update Central](https://www.windowsphone.com/en-us/how-to/wp8/update-central), um Ihr Telefon auf Windows Phone 8.1 zu aktualisieren.
    
2. Wechseln Sie von Ihrem Telefon zum **Store**, und suchen Sie nach **Skype for Business**.
    
3. Tippen Sie auf **Installieren**. 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>Erstmalige Anmeldung bei Skype for Business

1. Wischen Sie auf dem **Startbildschirm** nach links, um die installierten Apps anzuzeigen, suchen Sie nach Skype for Business für Windows Phone, und tippen Sie dann auf das Symbol, um die App zu öffnen.
    
2. Geben Sie Ihre Anmeldeadresse (z. B. user@domain.com) und ihr Kennwort ein, und tippen Sie dann auf **"Fertig**".
    
     Möglicherweise werden Sie sowohl nach einem Benutzernamen als auch nach einer Anmeldeadresse gefragt. Der Benutzername wird verwendet, um sich beim Netzwerk Ihrer Organisation anzumelden, entweder user@domain.com oder Domäne\Benutzername.
    
3. Tippen Sie auf dem Bildschirm " **Programm zur Verbesserung der Benutzerfreundlichkeit** " auf **"Teilnehmen** ", um anonyme Daten zu App-Problemen und der Nutzung an Microsoft zu senden, oder **nein,** wenn Sie nicht teilnehmen möchten.
    
4. Geben Sie auf dem Bildschirm **"Ihre Geschäftlichen Anrufe nie verpassen** " Ihre Mobiltelefonnummer mit Länder- und Regionscodes ein. Wenn Skype for Business für Windows Phone kein Wi-Fi- oder Mobilfunkdatennetzwerk verwenden können, um einen Audio- oder Videoanruf zu tätigen, werden Sie bei dieser Nummer automatisch angerufen und mit dem Audioteil des Anrufs verbunden.
    
5. Tippen Sie auf **"Weiter"** , und überprüfen Sie die Benachrichtigungs- und Telefonbuchzugriffseinstellungen:
    
   - **Pushbenachrichtigungen** Erhalten Sie eine Benachrichtigung, wenn Sie eine neue Chatnachricht oder einen neuen Anruf erhalten. Normal **eingeschaltet** (empfohlen).
    
     > [!IMPORTANT]
     > Wenn Sie diese Einstellung deaktivieren, werden Sie nicht über IMs, Anrufe oder andere Skype for Business für Windows Phone Warnungen benachrichtigt, es sei denn, die App ist aktiv. 
  
   - **Zulassen des Telefonbuchzugriffs** Suchen Sie nach Kontakten auf Ihrem Mobiltelefon, wenn Sie in Skype for Business für Windows Phone nach Kontakten suchen.
    
6. Tippen Sie **auf "Weiter**", um mit der Verwendung von Skype for Business für Windows Phone zu beginnen.
    
    [Verhindern, dass Skype for Business bei jeder Anmeldung auf dem Computer automatisch gestartet wird](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>Überprüfen der Installation mobiler Clients

Nachdem Sie den Client konfiguriert und sich erfolgreich angemeldet haben, überprüfen Sie anhand der folgenden Tests, ob die Installation von Skype for Business für Windows Phone auf Ihrem mobilen Gerät ordnungsgemäß funktioniert.
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>Suchen nach einem Kontakt im Unternehmensverzeichnis

1. Tippen Sie in der Kontaktliste auf **"Suchen**".
    
2. Suchen Sie einen Kontakt, der nur in der globalen Adressliste vorhanden ist.
    
3. Stellen Sie sicher, dass der Kontaktname in den Suchergebnissen angezeigt wird.
    
### <a name="test-instant-messaging-and-presence"></a>Chat und Anwesenheit testen

1. Tippen Sie in der Kontaktliste auf einen Kontakt.
    
2. Tippen Sie auf der Visitenkarte auf die Chatnachricht. ![Symbol für Chatnachrichten in Skype for Business.](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)aus.
    
3. Stellen Sie sicher, dass ein Chatfenster angezeigt wird und Sie eine Chatnachricht eingeben und senden können.
    
### <a name="test-dial-out-conferencing"></a>Testen der Dial-Out-Konferenz

1. Planen Sie in Outlook eine Skype for Business Besprechung.
    
2. Öffnen Sie in Ihrem Windows Phone die Besprechungseinladung.
    
3. Klicken Sie in der Besprechung auf den Link, um an der Besprechung teilzunehmen.
    
4. Nehmen Sie den Anruf vom Konferenzdienst entgegen, und stellen Sie sicher, dass Sie mit dem Besprechungsaudio verbunden sind.
    
### <a name="test-push-notifications"></a>Testen von Pushbenachrichtigungen

1. Wählen Sie zwei verschiedene Benutzerkonten für diesen Test aus. 
    
2. Melden Sie sich im Windows Phone von Benutzer A mit dem Konto von Benutzer A bei Skype for Business für Windows Phone an.
    
3. Öffnen Sie eine andere Anwendung auf dem Gerät.
    
4. Melden Sie sich auf einem anderen Client, z. B. dem Desktopclient, bei Skype for Business mit dem Konto von Benutzer B an.
    
5. Senden Sie eine Sofortnachricht von Benutzer B an Benutzer A.
    
6. Stellen Sie sicher, dass die Benachrichtigung über Chatnachrichten auf dem mobilen Gerät von Benutzer A angezeigt wird.
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>Entfernen von Skype for Business aus Ihrem Windows Phone

So entfernen Sie die Skype for Business für Windows Phone-App von Ihrem mobilen Gerät: 
  
1. Wischen Sie vom Startbildschirm aus, um die Anwendungsliste anzuzeigen. 
    
2. Tippen und halten Sie die Skype for Business für Windows Phone Anwendung, und wählen Sie dann **"Deinstallieren" aus**.
    


