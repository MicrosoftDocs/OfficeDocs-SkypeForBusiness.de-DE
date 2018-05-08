---
title: Installieren von Skype for Business Server 2015 auf Servern in der Topologie
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Zusammenfassung: Erfahren Sie, wie die Skype für Business Server 2015 Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 810e08cc6844f29d12536f89f3b877e7a2be8bce
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="install-skype-for-business-server-2015-on-servers-in-the-topology"></a>Installieren von Skype for Business Server 2015 auf Servern in der Topologie
 
**Zusammenfassung:** Erfahren Sie, wie die Skype für Business Server 2015 Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine kostenlose Testversion von Skype für Business Server 2015 aus dem [Microsoft-Evaluierungscenter](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Sobald die Topologie in den zentralen Verwaltungsspeicher geladen wird und Active Directory bekannt ist, welche Server die Rollen ausgeführt werden, müssen Sie die Skype für Business Server-System auf jedem Server in der Topologie installieren. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 der Reihe nach ausführen, und zwar nach den Schritten 1 bis 5, wie im Diagramm beschrieben. Installieren der Skype für Business Server-System ist Schritt 7 von 8.
  
![Übersichtsdiagramm.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Skype für Business Server-System installieren

Nachdem Sie eine Topologie veröffentlicht haben, können Sie die Skype für Business Server-Komponenten auf jedem Server in der Topologie installieren. Dieser Abschnitt führt Sie durch Skype für Business Server installieren und Einrichten von die Serverrollen für den Front-End-Pool und alle Serverrollen, die gemeinsam mit den Front-End-Servern ausgeführt werden. Führen Sie zum Installieren und Einrichten von Serverrollen, die Skype für Business Server Bereitstellungs-Assistenten auf jedem Computer, auf dem Sie eine Server-Rolle installieren aus. Verwenden Sie den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte, einschließlich den lokale Konfigurationsspeicher installieren, den Front-End-Servern installieren, Konfigurieren von Zertifikaten und Starten von Diensten abzuschließen.
  
> [!IMPORTANT]
> Sie müssen die Topologie-Generator verwenden, abschließen und die Topologie veröffentlichen, bevor Sie Skype für Business Server auf Servern installieren können. 
  
> [!NOTE]
> Dieses Verfahren muss für alle Server in der Topologie abgeschlossen werden. 
  
> [!CAUTION]
> Nach der Installation von Skype für Business Server auf einem Front-End-Server müssen beim ersten Starten von Diensten, Sie sicherstellen, dass der Windows-Firewall-Dienst auf dem Server ausgeführt wird. 
  
> [!CAUTION]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie auf dem Server mit einem Benutzerkonto der Domäne angemeldet sind, die ein lokaler Administrator und Mitglied der Gruppe RTCUniversalServerAdmins ist. 
  
> [!NOTE]
> Wenn Sie Skype für Business Server-Setup auf diesem Server vor nicht ausgeführt haben, werden Sie für ein Laufwerk und den Pfad für die Installation aufgefordert werden. Auf diese Weise können Sie ein anderes Laufwerk als das Systemlaufwerk verwenden, sofern dies von Ihrem Unternehmen vorgeschrieben oder nicht ausreichend Speicherplatz vorhanden ist. Sie können den Pfad zum Speicherort für die Skype für Business Server-Dateien in das Dialogfeld **Setup** in ein neues, verfügbaren Laufwerk ändern. Bei der Installation der Setupdateien an diesem Pfad, einschließlich OCSCore.msi, werden die restlichen der Skype für Business Server-Dateien vorhanden sowie bereitstellen.
  
> [!IMPORTANT]
> Bevor Sie die Installation beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Skype für Business Server-System installieren

1. Legen Sie die Skype für Business Server 2015-Installationsmedien. Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.
    
2. Das Installationsmedium erfordert die Ausführung von Microsoft Visual C++. Es wird ein Dialogfenster geöffnet, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **Ja.**
    
3. Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**. 
    
4. Intelligente Setup ist ein Feature in Skype für Business Server 2015, in dem Sie mit dem Internet nach Updates von Microsoft Update (MU) während des Installationsvorgangs suchen verbinden können wie in der Abbildung dargestellt. Diese Funktion verbessert die Benutzerfreundlichkeit, da sichergestellt ist, dass Sie die neuesten Updates für das Produkt verwenden. Klicken Sie auf **Installieren**, um die Installation zu starten.
    
    > [!NOTE]
    > Viele Unternehmen stellen Windows Server Update Services (WSUS) in ihrer Unternehmensumgebung bereit. In WSUS können Administratoren die komplette Verteilung von Updates verwalten, die durch Microsoft Update auf Computern ihres Netzwerks freigegeben werden. Im Rahmen der Kumulatives Update 1 Version eingeführt Skype für Business Server Support für die intelligente Installation WSUS entwickelt. Kunden mit WSUS, die Skype für Business Server zum ersten Mal bereitstellen oder Aktualisieren von der Lync Server 2013-Umgebung mithilfe der In-Place Upgrade-Funktion müssen Smart Setup Abrufen von Skype für Windows-Updates von WSUS im Gegensatz zu Abrufen von updates aus MU. Kunden, die Skype verwenden möchten, müssen auf allen Geräten „SmartSetupWithWSUS.psq“ ausführen, bevor „ Setup.exe“ ausgeführt werden kann. 
  
     ![Screenshot des intelligenten Setup.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Klicken Sie auf der Seite Bereitstellungs-Assistenten auf **installieren oder aktualisieren Skype für Business Server-System**.
    
6. Führen Sie die Verfahren in den folgenden Verfahren, wenn Sie sie abgeschlossen haben, klicken Sie auf **Beenden** , um den Bereitstellungs-Assistenten zu schließen. Wiederholen Sie die Verfahren für alle Front End-Server im Pool.
    
### <a name="step-1-install-local-configuration-store"></a>Schritt 1: Installieren des lokalen Konfigurationsspeichers

1. Überprüfen Sie die Voraussetzungen und klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen**.
    
    > [!NOTE]
    > Beim lokalen Konfigurationsspeicher handelt es sich um eine schreibgeschützte Kopie des zentralen Verwaltungsspeichers. In einer Standard Edition-Bereitstellung wird der zentrale Verwaltungsspeicher mithilfe einer lokalen Kopie von SQL Server Express Edition auf dem Front-End-Server erstellt. Dies erfolgt, wenn Sie das Verfahren zur Vorbereitung des ersten Standard Edition-Servers ausführen. In einer Enterprise Edition-Bereitstellung wird der zentrale Verwaltungsspeicher erstellt, wenn Sie die Topologie, zu der ein Enterprise Edition-Front-End-Pool gehört, veröffentlichen. 
  
2. Vergewissern Sie sich auf der Seite **Lokalen Konfigurationsspeicher installieren**, dass die Option **Direkt vom zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.
    
    SQL Server Express Edition wird auf dem lokalen Server installiert. SQL Server Express Edition ist für den lokalen Konfigurationsspeicher erforderlich.
    
3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Schritt 2: Einrichten oder Entfernen von Skype für Business Server-Komponenten

1. Überprüfen die erforderlichen Komponenten, und klicken Sie dann auf **Ausführen** als Nächstes **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**.
    
2. Klicken Sie auf der Seite **Festlegen von Skype für Business Server-Komponenten** auf **Weiter** , um die Komponenten einzurichten gemäß Definition in Ihrer veröffentlichten Topologie einzurichten.
    
3. Auf der Seite **Befehle ausführen** wird während der Ausführung des Vorgangs eine Zusammenfassung der Befehle und Installationsinformationen angezeigt. Wenn es abgeschlossen ist, können Sie mithilfe der Liste Wählen Sie ein Protokoll anzeigen, und klicken Sie dann auf **Protokoll anzeigen**.
    
4. Skype für Business Server-Komponenten Setup abgeschlossen ist, und Sie haben die Protokolle nach Bedarf überprüft, klicken Sie auf **Fertig stellen** , um diesen Schritt bei der Installation abzuschließen.
    
    > [!NOTE]
    > Starten Sie den Server neu, wenn Sie dazu aufgefordert werden (dies ist der Fall, wenn Windows Desktop Experience installiert werden musste). Wenn der Computer wieder betriebsbereit ist, müssen Sie dieses Beispiel ausführen möchten (Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten) Verfahren erneut aus. 
  
    > [!NOTE]
    > Wenn das Installationsprogramm Voraussetzungen erkennt, die nicht erfüllt werden, wird wie in der Abbildung dargestellt die Meldung „Die Voraussetzung wurde nicht erfüllt.“ angezeigt. Die erforderliche erforderlichen erfüllen, und starten Sie dies (Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten) Verfahren erneut aus. 
  
     ![Erforderliche Voraussetzung](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vergewissern Sie sich, dass die ersten zwei Schritte erwartungsgemäß ausgeführt wurden. Prüfen Sie, ob neben dem Wort **Abgeschlossen** wie in der Abbildung dargestellt ein grünes Häkchen angezeigt wird.
    
     ![Die ersten beiden beim Installieren von Komponenten abgeschlossenen Schritte](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Führen Sie **Windows Update** erneut, um zu überprüfen, ob Updates nach der Installation der Skype für Business Server-Komponenten vorhanden sind.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Schritt3: Anfordern, Installieren und Zuweisen von Zertifikaten

1. Überprüfen Sie die Voraussetzungen und klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**.
    
    > [!NOTE]
    > Skype für Business Server bietet Unterstützung für die SHA-2-Suite (SHA-2 verwendet digest-Längen von 224, 256, 384 oder 512 Bits) der Digesthash und die signierenden Algorithmen für Verbindungen von Clients, auf denen die Windows-10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2-Betriebssysteme. Damit der externe Zugriff über die SHA-2-Suite unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit einem Digest gleicher Bitlänge ausstellen kann. 
  
    > [!IMPORTANT]
    > Die Auswahl des verwendeten Hashdigests und Signaturalgorithmus hängt von den Clients und Servern ab, die das Zertifikat verwenden sollen, sowie von den anderen Computern und Geräten, mit denen Clients und Server kommunizieren sollen, die ebenfalls imstande sein müssen, die im Zertifikat enthaltenen Algorithmen zu verwenden. Informationen auf welche Digest Längen in das Betriebssystem und einige-Clientanwendungen unterstützt werden, finden Sie unter [Windows-PKI-Blog - SHA2 und Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Für jeden Standard Edition- oder Front-End-Server werden bis zu vier Zertifikate benötigt: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat. Sie können jedoch ein einzelnes Standardzertifikat mit geeigneten Einträgen für alternative Antragstellernamen sowie das oAuthTokenIssuer-Zertifikat anfordern und zuweisen. Ausführliche Informationen zu den zertifikatanforderungen finden Sie unter [umgebungsanforderungen für Skype für Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
    
    > [!IMPORTANT]
    > Im folgenden Verfahren wird beschrieben, wie die Zertifikate von einer internen auf Active Directory-Zertifikatsdiensten basierenden Zertifizierungsstelle konfiguriert werden. 
  
2. Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern**.
    
3. Geben Sie auf der Seite **Zertifikatsanforderung** die relevanten Daten ein und wählen Sie die SIP-Domäne. Klicken Sie anschließend auf **Weiter**.
    
4. Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Bei Auswahl dieser Option muss die interne Zertifizierungsstelle mit automatischer Onlineregistrierung verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Anschließend müssen Sie die Zertifikatantwort importieren und der entsprechenden Zertifikatrolle zuweisen.
    
5. Klicken Sie auf der Seite **Wählen Sie eine Zertifizierungsstelle (Certificate Authority, CA)** wählen Sie die Option **Wählen Sie eine Zertifizierungsstelle aus der Liste in Ihrer Umgebung erkannt** , und wählen Sie dann auf einen bekannten (über die Registrierung in Active Directory Domain Services) Zertifizierungsstelle aus der Liste. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.
    
6. Auf der Seite **Zertifizierungsstellenkonto** werden Sie zur Eingabe von Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatsanforderung bei der Zertifizierungsstelle aufgefordert. Sie müssen vorab festlegen, ob zum Anfordern eines Zertifikats ein Benutzername und ein Kennwort erforderlich sind. Der Zertifizierungsstellenadministrator verfügt über die benötigten Informationen und kann Ihnen ggf. bei diesem Schritt helfen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie einen Benutzernamen und ein Kennwort in die Textfelder ein und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben. 
  
8. Geben Sie auf der Seite **Namens- und Sicherheitseinstellungen** einen **Anzeigenamen**ein. Ein Anzeigename verwenden, können Sie schnell das Zertifikat und den Zweck identifizieren. Wenn Sie es leer lassen, wird automatisch ein Name generiert werden. Legen Sie die **Bitlänge** des Schlüssels, oder übernehmen Sie den Standardwert 2.048 Bit lang. Wählen Sie den **den privaten Schlüssel als exportierbar markieren** , wenn Sie feststellen, dass das Zertifikat und der private Schlüssel muss verschoben oder in andere Systeme kopiert werden soll, und klicken Sie dann auf **Weiter**.
    
    > [!NOTE]
    > Skype für Business Server verfügt über die Mindestanforderungen für einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet. 
  
9. Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an und klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an und klicken Sie dann auf **Weiter**.
    
11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.
    
12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne** und klicken Sie dann auf **Weiter**.
    
13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an und klicken Sie auf **Weiter**.
    
14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.
    
15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.
    
16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Wenn wird gemeldet, wie ausgestellt und installiert haben, aber es nicht zulässig ist, stellen Sie sicher, dass das Stammzertifikat der Zertifizierungsstelle installiert wurde in der Server-Speicher für vertrauenswürdige Stammzertifizierungsstelle. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das angeforderte Zertifikat anzeigen möchten. Standardmäßig ist das Kontrollkästchen für **weisen Sie das Zertifikat zu Skype für zertifikatverwendungen Business Server** aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen und klicken Sie dann auf **Fertig stellen**.
    
17. Wenn Sie das Kontrollkästchen für **weisen Sie das Zertifikat zu Skype für zertifikatverwendungen Business Server** auf die vorherige Seite deaktiviert haben, wird mit der Seite **Zertifikatzuweisung** angezeigt werden. Klicken Sie auf **Weiter**.
    
18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    > [!NOTE]
    > Wenn auf der Seite **Status der Onlinezertifikatsanforderung** ein Problem mit dem Zertifikat gemeldet wird (wenn das Zertifikat beispielsweise als ungültig angezeigt wird), kann das Anzeigen des tatsächlichen Zertifikats bei der Lösung des Problems helfen. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.
  
19. Überprüfen Sie anhand der Informationen auf der Seite **Zusammenfassung der Zertifikatzuweisung**, dass es sich um das zuzuweisende Zertifikat handelt, und klicken Sie dann auf **Weiter**.
    
20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.
    
21. Überprüfen Sie auf der Seite **Zertifikat-Assistent**, ob alle Dienste mit einem grünen Häkchen versehen sind. Dies gibt an, dass sie alle einem Zertifikat zugewiesen wurden, u. a. wie in der Abbildung dargestellt dem OAuthTokenIssuer-Zertifikat. Klicken Sie dann auf **Schließen**.
    
     ![Installierte und ordnungsgemäß zugewiesene Zertifikate](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Wenn Sie die Installation in einer Laborumgebung ausführen und soeben mithilfe der Active Directory-Zertifikatdienste die Zertifizierungsstelle eingerichtet haben, müssen Sie sowohl den Server, auf dem die Zertifikatdienste ausgeführt werden, als auch den Front-End-Server neu starten, damit die Zertifikatzuweisung erfolgreich ausgeführt werden kann. 
  
    > [!TIP]
    >  Weitere Informationen zu Zertifikaten in Active Directory-Zertifikatdienste finden Sie unter [Active Directory-Zertifikatdienste](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Schritt 4: Dienste starten

1. Überprüfen Sie die Anforderungen für den **Schritt 4: Dienste starten**.
    
2. Ist dies ein Enterprise Edition-Front-End-Pool mit mindestens drei Servern, Windows Fabric wird verwendet, und Sie müssen das **Start-CsPool** -Cmdlet verwenden. Wenn ein einzelner Server verwendet wird, die immer der Fall mit Standard Edition ist, muse Sie verwenden das Cmdlet **Start-CsWindowsService** . Öffnen Sie in diesem Beispiel, dass wir Enterprise Edition mit drei Front-End-Servern im Pool verwenden die **Skype für Business Server-Verwaltungsshell** , und führen Sie das Cmdlet **Start-CsPool** , wie in der Abbildung dargestellt. Für alle anderen Rollen, einschließlich der Standard Edition-Server müssen Sie die **Start-CsWindowsService**verwenden. Zum Bereitstellen von Rollen außer der Front-End-Rolle finden Sie in der Dokumentation für die bestimmten Rollen.
    
     ![Starten der Skype for Business-Dienste](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine Best-Effort-Methode, um anzuzeigen, dass die Dienste wirklich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des jeweiligen Diensts wider. Es wird empfohlen, mithilfe des Schritts **Dienststatus (optional)** wie in der Abbildung dargestellt die Microsoft Management Console (MMC) zu öffnen und zu überprüfen, ob die Dienste erfolgreich gestartet wurden. Wenn Skype für Business Server-Dienst nicht gestartet wurde, können Sie mit der rechten Maustaste dieses Diensts in der MMC, und klicken Sie dann auf **Starten**. 
  
     ![Start der Dienste sicherstellen](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

