---
title: Installieren von Lync für Windows Phone
TOCTitle: Installieren von Lync für Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Hh690996(v=OCS.15)
ms:contentKeyID: 52056449
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installieren von Lync für Windows Phone

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Lync 2013 für Windows Phone ist im Windows Phone-Marketplace verfügbar und kann von Benutzern heruntergeladen und installiert werden.

## Installieren von Lync für Windows Mobile

Sie können die Benutzer auffordern, Lync 2013 für Windows Phone vom Windows Phone-Marketplace unter <http://go.microsoft.com/fwlink/?linkid=231901> auf ihre Geräten zu installieren.

## Wenn Sie einen DNS SRV-Datensatz für die Veröffentlichung von Exchange-Webdiensten verwenden

Um die Exchange-Integration für Lync-Clients zu aktivieren, veröffentlichen einige Organisationen die Exchange-Webdienste-URL, indem sie einen DNS SRV-Datensatz verwenden. In dem Dokument "Grundlegendes zur Microsoft Exchange Server-Integration und Problembehandlung ", das im Microsoft Download Center unter [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095) verfügbar ist, werden Szenarien beschrieben, in denen dies möglicherweise erforderlich ist. Allerdings wird die Exchange-Integration für Windows Phone-Benutzer in diesem Szenario nicht funktionieren, da die Windows Phone-Plattform SRV-Abfragen nicht unterstützt. Sie müssen Windows Phone-Benutzer anweisen, die Exchange-Webdienste-URL anzugeben, statt das Telefon automatisch den Server erkennen zu lassen.

Weisen Sie Ihre Benutzer an, die Lync-Einstellungen auf Ihren Windows Phones wie folgt zu konfigurieren:

1.  Wählen Sie in Windows Phone bei den Lync-Einstellungen den Bildschirm **Exchange** aus.

2.  Verschieben Sie **Server automatisch erkennen** auf **Aus**.

3.  Tippen Sie auf das leere Feld und geben Sie den vollqualifizierten Domänennamen (FQDN) oder die URL für Exchange-Webdienste ein.
    

    > [!NOTE]
    > Sie können entweder den FQDN oder die volle URL Ihres Exchange-Webdiensteservers angeben. Wenn Sie den FQDN angeben, werden das Protokoll (https://) und der Exchange-Webdienstepfad (/ews/exchange.asmx) automatisch hinzugefügt. Wenn Ihr Exchange-Webdienstepfad anders lautet, können Sie die volle URL angeben.



4.  Schließen Sie den Bildschirm.

## Überprüfen der Installation des mobilen Clients

Nachdem Sie den Client konfiguriert und sich erfolgreich angemeldet haben, können Sie mithilfe der folgenden Tests überprüfen, ob die Lync 2013-Installation auf dem mobilen Gerät ordnungsgemäß funktioniert.

**Suchen nach einem Kontakt im Unternehmensverzeichnis**

1.  Tippen Sie in der Kontaktliste unten auf die Schaltfläche **Suchen**.

2.  Suchen Sie einen Kontakt, der nur in der globalen Adressliste vorhanden ist.

3.  Stellen Sie sicher, dass der Kontaktname in den Suchergebnissen angezeigt wird.

**Testen der Chat- und Anwesenheitsfunktionen**

1.  Tippen Sie in der Kontaktliste auf einen Kontakt.

2.  Tippen Sie in der Visitenkarte auf das Symbol **IM**.

3.  Stellen Sie sicher, dass ein Chatfenster zum Eingeben und Senden einer Chatnachricht angezeigt wird.

**Testen der Dial-Out-Konferenz**

1.  Planen Sie in Outlook eine Lync-Besprechung.

2.  Öffnen Sie auf dem mobilen Gerät die Besprechungseinladung.

3.  Klicken Sie in der Besprechung auf den Link, um an der Besprechung teilzunehmen.

4.  Nehmen Sie den Anruf vom Konferenzdienst entgegen, und stellen Sie sicher, dass Sie mit dem Besprechungsaudio verbunden sind.

**Testen von Pushbenachrichtigungen**

1.  Melden Sie sich auf dem mobilen Gerät von Benutzer A bei Lync mit dem Konto des Benutzers A an.

2.  Öffnen Sie eine andere Anwendung auf dem mobilen Gerät.

3.  Melden Sie sich in einem anderen Client mit dem Konto von Benutzer B bei Lync an.

4.  Senden Sie eine Sofortnachricht von Benutzer B an Benutzer A.

5.  Stellen Sie sicher, dass die Sofortnachricht auf dem mobilen Gerät von Benutzer A erscheint.

