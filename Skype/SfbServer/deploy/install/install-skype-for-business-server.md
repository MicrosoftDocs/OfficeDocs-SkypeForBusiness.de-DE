---
title: Installieren von Skype for Business Server auf Servern in der Topologie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Systemkomponenten von Skype for Business Server auf jedem Server in der Topologie installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverCenter unter: herunter.'
ms.openlocfilehash: 8ecf298809a6c4c37b5c075e7ac16623f1669ff9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791753"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installieren von Skype for Business Server auf Servern in der Topologie
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Systemkomponenten von Skype for Business Server auf jedem Server in der Topologie installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Nachdem die Topologie in den zentralen Verwaltungsspeicher geladen wurde und Active Directory weiß, welche Server welche Rollen ausführen sollen, müssen Sie das Skype for Business Server-System auf jedem der Server in der Topologie installieren. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 der Reihe nach ausführen, und zwar nach den Schritten 1 bis 5, wie im Diagramm beschrieben. Die Installation des Skype for Business-Server Systems ist Schritt 7 von 8.
  
![Übersichtsdiagramm.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installieren von Skype for Business Server System

Nachdem Sie eine Topologie veröffentlicht haben, können Sie die Skype for Business Server-Komponenten auf jedem Server in der Topologie installieren. Dieser Abschnitt führt Sie durch die Installation von Skype for Business Server und das Einrichten der Serverrollen für den Front-End-Pool und alle Serverrollen, die mit den Front-End-Servern zusammengesetzt sind. Zum Installieren und Einrichten von Serverrollen führen Sie den Skype for Business Server-Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren. Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte abzuschließen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, der Konfiguration von Zertifikaten und dem Starten von Diensten.
  
> [!IMPORTANT]
> Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie Skype for Business Server auf Servern installieren können. 
  
> [!NOTE]
> Dieses Verfahren muss für alle Server in der Topologie abgeschlossen werden. 
  
> [!CAUTION]
> Nachdem Sie Skype for Business Server auf einem Front-End-Server installiert haben, müssen Sie beim erstmaligen Starten von Services sicherstellen, dass der Windows-Firewalldienst auf dem Server ausgeführt wird. 
  
> [!CAUTION]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie mit einem Domänenbenutzerkonto am Server angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der RTCUniversalServerAdmins-Gruppe ist. 
  
> [!NOTE]
> Wenn Sie Skype for Business Server-Setup noch nicht auf diesem Server ausgeführt haben, werden Sie aufgefordert, ein Laufwerk und einen Pfad für die Installation einzugeben. Auf diese Weise können Sie ein anderes Laufwerk als das Systemlaufwerk verwenden, sofern dies von Ihrem Unternehmen vorgeschrieben oder nicht ausreichend Speicherplatz vorhanden ist. Sie können den Pfad für den Installationspfad für die Skype for Business Server-Dateien im Dialogfeld " **Einrichten** " auf ein neues, verfügbares Laufwerk ändern. Wenn Sie die Setup Dateien in diesem Pfad, einschließlich OCSCore. msi, installieren, werden die restlichen Skype for Business Server-Dateien ebenfalls bereitgestellt.
  
> [!IMPORTANT]
> Bevor Sie mit der Installation beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installieren von Skype for Business Server System

1. Legen Sie das Skype for Business Server-Installationsmedium ein. Wenn das Setup nicht automatisch startet, doppelklicken Sie auf **Setup**.
    
2. Das Installationsmedium erfordert die Ausführung von Microsoft Visual C++. Es wird ein Dialogfenster geöffnet, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **Ja.**
    
3. Lesen Sie die Lizenzbedingungen sorgfältig durch und klicken Sie auf **Ich stimme den Lizenzbedingungen zu**, wenn Sie diesen zustimmen. Klicken Sie dann auf **OK**. 
    
4. Smart Setup ist eine Funktion in Skype for Business Server, auf der Sie während des Installationsvorgangs eine Verbindung mit dem Internet herstellen können, um nach Updates von Microsoft Update (MU) zu suchen, wie in der Abbildung zu sehen ist. Diese Funktion verbessert die Benutzerfreundlichkeit, da sichergestellt ist, dass Sie die neuesten Updates für das Produkt verwenden. Klicken Sie auf **Installieren**, um die Installation zu starten.
    
    > [!NOTE]
    > Viele Unternehmen stellen Windows Server Update Services (WSUS) in ihrer Unternehmensumgebung bereit. In WSUS können Administratoren die komplette Verteilung von Updates verwalten, die durch Microsoft Update auf Computern ihres Netzwerks freigegeben werden. Im Rahmen des kumulativen Updates 1 wurde in Skype for Business Server die Unterstützung für Smart Setup für die Zusammenarbeit mit WSUS eingeführt. Kunden mit WSUS, die Skype for Business Server zum ersten Mal bereitstellen oder ein Upgrade von der lync Server 2013-Umgebung mithilfe des in-Place-Upgrades durchführen, haben intelligentes Setup, das Skype für Windows-Updates von WSUS abruft, anstatt Updates abzurufen. von Mu. Kunden, die Skype verwenden möchten, müssen auf allen Geräten „SmartSetupWithWSUS.psq“ ausführen, bevor „ Setup.exe“ ausgeführt werden kann. 
  
     ![Screenshot des intelligenten Setup.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Klicken Sie auf der Seite Deployment-Assistent auf **Skype for Business Server System installieren oder aktualisieren**.
    
6. Führen Sie die Verfahren in den folgenden Verfahren aus, wenn Sie sie abgeschlossen haben, klicken Sie auf **Beenden** , um den Bereitstellungs-Assistenten zu schließen. Wiederholen Sie die Verfahren für alle Front End-Server im Pool.
    
### <a name="step-1-install-local-configuration-store"></a>Schritt 1: Installieren des lokalen Konfigurationsspeichers

1. Überprüfen Sie die Voraussetzungen und klicken Sie neben **Schritt 1: Lokalen Konfigurationsspeicher installieren** auf **Ausführen**.
    
    > [!NOTE]
    > Beim lokalen Konfigurationsspeicher handelt es sich um eine schreibgeschützte Kopie des zentralen Verwaltungsspeichers. In einer Standard Edition-Bereitstellung wird der zentrale Verwaltungsspeicher mithilfe einer lokalen Kopie von SQL Server Express Edition auf dem Front-End-Server erstellt. Dies erfolgt, wenn Sie das Verfahren zur Vorbereitung des ersten Standard Edition-Servers ausführen. In einer Enterprise Edition-Bereitstellung wird der zentrale Verwaltungsspeicher erstellt, wenn Sie die Topologie, zu der ein Enterprise Edition-Front-End-Pool gehört, veröffentlichen. 
  
2. Vergewissern Sie sich auf der Seite **Lokalen Konfigurationsspeicher installieren**, dass die Option **Direkt vom zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **Weiter**.
    
    SQL Server Express Edition wird auf dem lokalen Server installiert. SQL Server Express Edition ist für den lokalen Konfigurationsspeicher erforderlich.
    
3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann neben **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**auf **Ausführen** .
    
2. Klicken Sie auf der Seite **Skype for Business Server-Komponenten einrichten** auf **weiter** , um Komponenten gemäß der Definition in ihrer veröffentlichten Topologie einzurichten.
    
3. Auf der Seite **Befehle ausführen** wird während der Ausführung des Vorgangs eine Zusammenfassung der Befehle und Installationsinformationen angezeigt. Wenn Sie fertig sind, können Sie die Liste verwenden, um ein anzuzeigende Protokoll auszuwählen, und klicken Sie dann auf **Protokoll anzeigen**.
    
4. Wenn die Einrichtung von Skype for Business Server-Komponenten abgeschlossen ist und Sie die Protokolle nach Bedarf überprüft haben, klicken Sie auf **Fertig stellen** , um diesen Schritt in der Installation abzuschließen.
    
    > [!NOTE]
    > Starten Sie den Server neu, wenn Sie dazu aufgefordert werden (dies ist der Fall, wenn Windows Desktop Experience installiert werden musste). Wenn der Computer wieder in Betrieb ist, müssen Sie diesen Vorgang (Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten) erneut ausführen. 
  
    > [!NOTE]
    > Wenn das Installationsprogramm Voraussetzungen erkennt, die nicht erfüllt werden, wird wie in der Abbildung dargestellt die Meldung „Die Voraussetzung wurde nicht erfüllt.“ angezeigt. Erfüllen Sie die erforderlichen Voraussetzungen, und starten Sie dann das Verfahren (Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten) erneut. 
  
     ![Erforderliche Voraussetzung](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vergewissern Sie sich, dass die ersten zwei Schritte erwartungsgemäß ausgeführt wurden. Prüfen Sie, ob neben dem Wort **Abgeschlossen** wie in der Abbildung dargestellt ein grünes Häkchen angezeigt wird.
    
     ![Die ersten beiden beim Installieren von Komponenten abgeschlossenen Schritte](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob nach der Installation der Skype for Business Server-Komponenten Updates vorhanden sind.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Schritt3: Anfordern, Installieren und Zuweisen von Zertifikaten

1. Überprüfen Sie die Voraussetzungen und klicken Sie neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen** auf **Ausführen**.
    
    > [!NOTE]
    > Skype for Business Server bietet Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digest-Längen von 224-, 256-, 384-oder 512-Bits) von Digest-Hash-und-Signaturalgorithmen für Verbindungen von Clients, auf denen Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2-Betriebssysteme. Damit der externe Zugriff über die SHA-2-Suite unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit einem Digest gleicher Bitlänge ausstellen kann. 
  
    > [!IMPORTANT]
    > Die Auswahl des verwendeten Hashdigests und Signaturalgorithmus hängt von den Clients und Servern ab, die das Zertifikat verwenden sollen, sowie von den anderen Computern und Geräten, mit denen Clients und Server kommunizieren sollen, die ebenfalls imstande sein müssen, die im Zertifikat enthaltenen Algorithmen zu verwenden. Informationen dazu, welche Digest-Längen im Betriebssystem und einigen Clientanwendungen unterstützt werden, finden Sie unter [Windows-PKI-Blog-SHA2 und Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Für jeden Standard Edition- oder Front-End-Server werden bis zu vier Zertifikate benötigt: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat. Sie können jedoch ein einzelnes Standardzertifikat mit geeigneten Einträgen für alternative Antragstellernamen sowie das oAuthTokenIssuer-Zertifikat anfordern und zuweisen. Details zu den Zertifikatanforderungen finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) -oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > Im folgenden Verfahren wird beschrieben, wie die Zertifikate von einer internen auf Active Directory-Zertifikatsdiensten basierenden Zertifizierungsstelle konfiguriert werden. 
  
2. Klicken Sie auf der Seite **Zertifikat-Assistent** auf **Anfordern**.
    
3. Geben Sie auf der Seite **Zertifikatsanforderung** die relevanten Daten ein und wählen Sie die SIP-Domäne. Klicken Sie anschließend auf **Weiter**.
    
4. Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Bei Auswahl dieser Option muss die interne Zertifizierungsstelle mit automatischer Onlineregistrierung verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Anschließend müssen Sie die Zertifikatantwort importieren und der entsprechenden Zertifikatrolle zuweisen.
    
5. Wählen Sie auf der Seite Zertifizierungs **Stelle auswählen** die Option **eine Zertifizierungsstelle in der Liste in Ihrer Umgebung gefunden** auswählen aus, und wählen Sie dann in der Liste eine bekannte Zertifizierungsstelle (durch Registrierung in Active Directory-Domänendienste) aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.
    
6. Auf der Seite **Zertifizierungsstellenkonto** werden Sie zur Eingabe von Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatsanforderung bei der Zertifizierungsstelle aufgefordert. Sie müssen vorab festlegen, ob zum Anfordern eines Zertifikats ein Benutzername und ein Kennwort erforderlich sind. Der Zertifizierungsstellenadministrator verfügt über die benötigten Informationen und kann Ihnen ggf. bei diesem Schritt helfen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie einen Benutzernamen und ein Kennwort in die Textfelder ein und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben. 
  
8. Geben Sie auf der Seite **Name und Sicherheitseinstellungen** einen **Anzeigenamen**ein. Mithilfe eines Anzeigenamens können Sie das Zertifikat und den Zweck schnell identifizieren. Wenn Sie das Feld leer lassen, wird automatisch ein Name generiert. Stellen Sie die **Bit-Länge** des Schlüssels ein, oder übernehmen Sie den Standardwert von 2048-Bits. Wählen Sie den **privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aus, wenn Sie feststellen, dass das Zertifikat und der private Schlüssel verschoben oder auf andere Systeme kopiert werden müssen, und klicken Sie dann auf **weiter**.
    
    > [!NOTE]
    > Skype for Business Server bietet minimale Anforderungen für einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet. 
  
9. Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an und klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an und klicken Sie dann auf **Weiter**.
    
11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.
    
12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne** und klicken Sie dann auf **Weiter**.
    
13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an und klicken Sie auf **Weiter**.
    
14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.
    
15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.
    
16. Überprüfen Sie auf der Seite **Status der Online Zertifikatanforderung** die zurückgegebenen Informationen. Beachten Sie, dass das Zertifikat ausgestellt und im lokalen Zertifikatspeicher installiert wurde. Wenn die Meldung als ausgestellt und installiert, aber ungültig gemeldet wird, stellen Sie sicher, dass das Zertifizierungsstellen-Stammzertifikat im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Servers installiert wurde. Informationen zum Abrufen eines vertrauenswürdigen Stammzertifizierungsstellen-Zertifikats finden Sie in ihrer Zertifizierungsstellen-Dokumentation. Wenn Sie das abgerufene Zertifikat anzeigen müssen, klicken Sie auf **Zertifikat Details anzeigen**. Standardmäßig ist das Kontrollkästchen zum **Zuweisen der Zertifikate zu den Skype for Business Server-Zertifikat Verwendungen** aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.
    
17. Wenn Sie das Kontrollkästchen für **die Verwendung des Zertifikats für Skype for Business Server-Zertifikate** auf der vorherigen Seite deaktiviert haben, wird die Seite " **zertifikatzuweisung** " angezeigt. Click **Next**.
    
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
    >  Weitere Informationen zu Zertifikaten in den Active Directory-Zertifikatdiensten finden Sie unter [Active Directory-Zertifikatdienste](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Schritt 4: Dienste starten

1. Überprüfen Sie die Anforderungen für den **Schritt 4: Dienste starten**.
    
2. Wenn es sich um einen Enterprise Edition-Front-End-Pool mit mindestens drei Servern handelt, wird Windows Fabric verwendet, und Sie müssen das Cmdlet **Start-CsPool** verwenden. Wenn ein einzelner Server verwendet wird, was bei der Standard Edition immer der Fall ist, verwenden Sie Muse das Cmdlet **Start-CsWindowsService** . In diesem Beispiel verwenden wir Enterprise Edition mit drei Front-End-Servern im Pool, öffnen Sie die **Skype for Business Server-Verwaltungsshell** , und führen Sie das Cmdlet **Start-CsPool** aus, wie in der Abbildung dargestellt. Für alle anderen Rollen, einschließlich des Standard Edition-Servers, müssen Sie **Start-CsWindowsService**verwenden. Informationen zum Bereitstellen von anderen Rollen als der Front-End-Rolle finden Sie unter Dokumentation für diese bestimmten Rollen.
    
     ![Starten der Skype for Business-Dienste](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine Best-Effort-Methode, um anzuzeigen, dass die Dienste wirklich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des jeweiligen Diensts wider. Es wird empfohlen, mithilfe des Schritts **Dienststatus (optional)** wie in der Abbildung dargestellt die Microsoft Management Console (MMC) zu öffnen und zu überprüfen, ob die Dienste erfolgreich gestartet wurden. Wenn ein Skype for Business Server-Dienst nicht gestartet wurde, können Sie mit der rechten Maustaste auf diesen Dienst in der MMC klicken und dann auf **Start**klicken. 
  
     ![Start der Dienste sicherstellen](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

