---
title: Installieren von Skype for Business Server auf Servern in der Topologie
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installieren.'
ms.openlocfilehash: 7aea6d25edcd28ba611b81d33eceed4172019bee
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860616"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installieren von Skype for Business Server auf Servern in der Topologie
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installieren.
  
Sobald die Topologie in die zentrale Verwaltungs-Store geladen wurde und Active Directory weiß, welche Server welche Rollen ausführen werden, müssen Sie das Skype for Business Server System auf jedem server in der Topologie installieren. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm dargestellt. Die Installation des Skype for Business Server Systems ist Schritt 7 von 8.
  
![Übersichtsdiagramm.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installieren Skype for Business Server Systems

Nachdem Sie eine Topologie veröffentlicht haben, können Sie die Skype for Business Server Komponenten auf jedem Server in der Topologie installieren. In diesem Abschnitt werden Sie durch die Installation von Skype for Business Server und das Einrichten der Serverrollen für den Front-End-Pool und aller Serverrollen, die mit den Front-End-Servern verbunden sind, geleitet. Zum Installieren und Einrichten von Serverrollen führen Sie den Skype for Business Server Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren. Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte auszuführen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, des Konfigurierens von Zertifikaten und des Startens von Diensten.
  
> [!IMPORTANT]
> Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie Skype for Business Server auf Servern installieren können. 
  
> [!NOTE]
> Dieses Verfahren muss für alle Server in der Topologie abgeschlossen sein. 
  
> [!CAUTION]
> Nachdem Sie Skype for Business Server auf einem Front-End-Server installiert haben, müssen Sie beim ersten Starten der Dienste sicherstellen, dass der Windows Firewalldienst auf dem Server ausgeführt wird. 
  
> [!CAUTION]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie auf dem Server mit einem Domänenbenutzerkonto angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der Gruppe "RTCUniversalServerAdmins" ist. 
  
> [!NOTE]
> Wenn Sie Skype for Business Server Setup auf diesem Server noch nicht ausgeführt haben, werden Sie aufgefordert, ein Laufwerk und einen Pfad für die Installation einzugeben. Dies bietet die Möglichkeit, auf einem anderen Laufwerk als dem Systemlaufwerk zu installieren, wenn dies in Ihrer Organisation erforderlich ist oder wenn Sie Bedenken hinsichtlich des Speicherplatzes haben. Sie können den Installationsspeicherortpfad für die Skype for Business Server Dateien im Dialogfeld **"Setup**" auf ein neues, verfügbares Laufwerk ändern. Wenn Sie die Setupdateien unter diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien dort bereitgestellt.
  
> [!IMPORTANT]
> Bevor Sie mit der Installation beginnen, stellen Sie sicher, dass Windows Server mithilfe von Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installieren Skype for Business Server Systems

1. Fügen Sie das Skype for Business Server Installationsmedium ein. Wenn das Setup nicht automatisch beginnt, doppelklicken Sie auf **"Setup"**.
    
2. Für das Installationsmedium muss Microsoft Visual C++ ausgeführt werden. Es wird ein Dialogfeld angezeigt, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **"Ja".**
    
3. Überprüfen Sie sorgfältig den Lizenzvertrag, und wenn Sie zustimmen, wählen Sie **"Ich akzeptiere die Bedingungen im Lizenzvertrag**" aus, und klicken Sie auf **"OK**". 
    
4. Smart Setup ist ein Feature in Skype for Business Server, mit dem Sie während des Installationsvorgangs eine Verbindung mit dem Internet herstellen können, um nach Updates von Microsoft Update (MU) zu suchen, wie in der Abbildung dargestellt. Dies bietet eine bessere Erfahrung, indem Sie sicherstellen, dass Sie über die neuesten Updates für das Produkt verfügen. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
    > [!NOTE]
    > Viele Organisationen haben Windows Server Update Services (WSUS) in ihren Unternehmensumgebungen bereitgestellt. Mit WSUS können Administratoren die Verteilung von Updates, die über Microsoft Update veröffentlicht werden, auf Computern in ihrem Netzwerk vollständig verwalten. Im Rahmen des kumulativen Updates 1 Skype for Business Server Unterstützung für smartes Setup für die Arbeit mit WSUS eingeführt. Kunden mit WSUS, die Skype for Business Server zum ersten Mal bereitstellen oder ein Upgrade aus der Lync Server 2013-Umgebung mithilfe der In-Place Upgrade-Funktion durchführen, verfügen über smartes Setup, das Skype für Windows Updates von WSUS abruft, anstatt Updates von MU abzurufen. Kunden, die Smart Setup verwenden möchten, müssen die SmartSetupWithWSUS.psq auf allen Computern ausführen, bevor sie Setup.exe ausführen. 
  
     ![Screenshot "Intelligentes Setup".](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Klicken Sie auf der Seite des Bereitstellungs-Assistenten auf **"Skype for Business Server System installieren oder aktualisieren"**.
    
6. Führen Sie die Verfahren in den folgenden Verfahren aus. Wenn Sie diese abgeschlossen haben, klicken Sie auf **"Beenden** ", um den Bereitstellungs-Assistenten zu schließen. Wiederholen Sie die Verfahren für jeden Front-End-Server im Pool.
    
### <a name="step-1-install-local-configuration-store"></a>Schritt 1: Installieren der lokalen Store

1. Überprüfen Sie die voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 1: Installieren der lokalen Konfiguration Store**.
    
    > [!NOTE]
    > Die Store für die lokale Konfiguration ist eine schreibgeschützte Kopie der zentralen Verwaltungs-Store. In einer Standard Edition Bereitstellung wird die zentrale Verwaltungs-Store mithilfe einer lokalen Kopie von SQL Server Express Edition auf dem Front-End-Server erstellt. Dies geschieht, wenn Sie die Prozedur "Erste Standard Edition Server vorbereiten" ausführen. In einer Enterprise Edition Bereitstellung wird der zentrale Verwaltungsspeicher erstellt, wenn Sie die Topologie veröffentlichen, die einen Enterprise Edition Front-End-Pool enthält. 
  
2. Stellen Sie auf der Seite **"Lokale Konfiguration installieren" Store** sicher, dass die Option "**Direkt aus dem zentralen Verwaltungsspeicher abrufen**" ausgewählt ist, und klicken Sie dann auf **"Weiter**".
    
    SQL Server Express Edition wird auf dem lokalen Server installiert. SQL Server Express Edition ist für den lokalen Konfigurationsspeicher erforderlich.
    
3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.
    
### <a name="step-2-set-up-or-remove-skype-for-business-server-components"></a>Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann neben **Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten** auf **Ausführen**.
    
2. Klicken Sie auf der Seite **"Skype for Business Server Komponenten** einrichten" auf **"Weiter**", um Komponenten wie in Ihrer veröffentlichten Topologie definiert einzurichten.
    
3. Auf der Seite **"Befehle ausführen** " wird während der Einrichtung eine Zusammenfassung der Befehle und Installationsinformationen angezeigt. Wenn sie fertig ist, können Sie die Liste verwenden, um ein anzuzeigenden Protokoll auszuwählen, und dann auf " **Protokoll anzeigen"** klicken.
    
4. Wenn Skype for Business Server Komponenteneinrichtung abgeschlossen ist und Sie die Protokolle nach Bedarf überprüft haben, klicken Sie auf **"Fertig stellen**", um diesen Schritt in der Installation abzuschließen.
    
    > [!NOTE]
    > Starten Sie den Server neu, wenn Sie dazu aufgefordert werden (was passieren kann, wenn Windows Desktopdarstellung installiert werden musste). Wenn der Computer wieder ausgeführt wird, müssen Sie dieses Verfahren (Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten) erneut ausführen. 
  
    > [!NOTE]
    > Wenn das Installationsprogramm nicht erfüllte Voraussetzungen findet, werden Sie mit der Meldung "Voraussetzung nicht erfüllt" benachrichtigt, wie in der Abbildung dargestellt. Erfüllen Sie die erforderlichen Voraussetzungen, und starten Sie dann das Verfahren (Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten) erneut. 
  
     ![Voraussetzung erforderlich.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Vergewissern Sie sich, dass die ersten beiden Schritte wie erwartet abgeschlossen wurden. Vergewissern Sie sich, dass ein grünes Häkchen mit dem Wort **"Vollständig**" vorhanden ist, wie in der Abbildung dargestellt.
    
     ![Die ersten beiden Schritte nach der Installation von Komponenten wurden abgeschlossen.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob nach der Installation der Skype for Business Server-Komponenten Updates vorhanden sind.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **"Ausführen** " neben **Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten**.
    
    > [!NOTE]
    > Skype for Business Server unterstützt die SHA-2-Suite (SHA-2 verwendet Digestlängen von 224, 256, 384 oder 512 Bit) von Digesthash- und Signaturalgorithmen für Verbindungen von Clients, die die Windows 10, Windows 8, Windows 7, Windows Server 2012 R2 ausführen, Windows Server 2012 oder Windows Server 2008 R2-Betriebssysteme. Um den externen Zugriff mithilfe der SHA-2-Suite zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit der gleichen Bitlänge ausstellen kann. 
  
    > [!IMPORTANT]
    > Die Auswahl des Hashdigest- und Signaturalgorithmus hängt von den Clients und Servern ab, die das Zertifikat verwenden werden, sowie von anderen Computern und Geräten, mit denen Clients und Server kommunizieren, die auch wissen müssen, wie die im Zertifikat verwendeten Algorithmen verwendet werden. Informationen dazu, welche Digestlängen im Betriebssystem und einigen Clientanwendungen unterstützt werden, finden Sie [Windows PKI-Blog SHA2 und Windows](/archive/blogs/pki/sha2-and-windows). 
  
    Jeder Standard Edition- oder Front-End-Server benötigt bis zu vier Zertifikate: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat. Sie können jedoch ein einzelnes Standardzertifikat mit entsprechenden Einträgen für alternative Antragstellernamen sowie das oAuthTokenIssuer-Zertifikat anfordern und zuweisen. Ausführliche Informationen zu den Zertifikatanforderungen finden Sie unter [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > Im folgenden Verfahren wird beschrieben, wie Zertifikate von einer internen, auf Active Directory-Zertifikatdiensten basierenden Zertifizierungsstelle konfiguriert werden. 
  
2. Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.
    
3. Geben Sie auf der Seite **"Zertifikatanforderung** " die relevanten Daten ein, einschließlich der Auswahl der SIP-Domäne, und klicken Sie auf **"Weiter**".
    
4. Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Die interne Zertifizierungsstelle mit automatischer Onlineregistrierung muss bei Auswahl dieser Option verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Sie müssen anschließend die Zertifikatantwort importieren und sie der entsprechenden Zertifikatrolle zuweisen.
    
5. Wählen Sie auf der Seite "**Zertifizierungsstelle auswählen"** die Option "**Zertifizierungsstelle auswählen" aus der Liste aus, die in Ihrer Umgebung erkannt wurde**, und wählen Sie dann eine bekannte Zertifizierungsstelle (durch Registrierung in Active Directory Domain Services) aus der Liste aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.
    
6. Auf der Seite **"Konto der Zertifizierungsstelle"** werden Sie aufgefordert, Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatanforderung bei der Zertifizierungsstelle einzugeben. Sie sollten ermittelt haben, ob ein Benutzername und ein Kennwort erforderlich sind, um ein Zertifikat im Voraus anzufordern. Ihr Zertifizierungsstellenadministrator verfügt über die erforderlichen Informationen und muss Sie möglicherweise in diesem Schritt unterstützen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie einen Benutzernamen und ein Kennwort in die Textfelder ein, und klicken Sie dann auf **"Weiter**".
    
7. Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage für zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen, und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben. 
  
8. Geben Sie auf der Seite **"Name und Sicherheit Einstellungen**" einen **Anzeigenamen** an. Mithilfe eines Anzeigenamens können Sie das Zertifikat und den Zweck schnell identifizieren. Wenn Sie ihn leer lassen, wird automatisch ein Name generiert. Legen Sie die **Bitlänge** des Schlüssels fest, oder übernehmen Sie den Standardwert von 2048 Bit. Wählen Sie den **privaten Schlüssel des Zertifikats als exportierbar** markieren, wenn Sie feststellen, dass das Zertifikat und der private Schlüssel in andere Systeme verschoben oder kopiert werden müssen, und klicken Sie dann auf **"Weiter**".
    
    > [!NOTE]
    > Skype for Business Server hat minimale Anforderungen für einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet. 
  
9. Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an, und klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an, und klicken Sie dann auf **Weiter**.
    
11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.
    
12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne**, und klicken Sie dann auf **Weiter**.
    
13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.
    
14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.
    
15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.
    
16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Wenn gemeldet wird, dass es ausgestellt und installiert, aber ungültig ist, stellen Sie sicher, dass das Zertifizierungsstellenstammzertifikat im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Servers installiert wurde. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das angeforderte Zertifikat anzeigen möchten. Standardmäßig ist das Kontrollkästchen zum **Zuweisen des Zertifikats zu Skype for Business Server Zertifikatverwendungen** aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.
    
17. Wenn Sie das Kontrollkästchen zum **Zuweisen des Zertifikats zu Skype for Business Server Zertifikatverwendungen auf der vorherigen** Seite deaktiviert haben, wird ihnen die Seite "**Zertifikatzuweisung**" angezeigt. Klicken Sie auf **Weiter**.
    
18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    > [!NOTE]
    > Wenn auf der Seite " **Status der Onlinezertifikatanforderung** " ein Problem mit dem Zertifikat gemeldet wurde, z. B. das Zertifikat ungültig ist, zeigen Sie das tatsächliche Zertifikat an, um Hilfe bei der Lösung des Problems zu erhalten. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.
  
19. Überprüfen Sie auf der Seite " **Zertifikatzuweisungszusammenfassung** " die angezeigten Informationen, um sicherzustellen, dass es sich um das Zertifikat handelt, das zugewiesen werden soll, und klicken Sie dann auf **"Weiter**".
    
20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.
    
21. Vergewissern Sie sich auf der Seite " **Zertifikat-Assistent** ", dass alle Dienste über eine grüne Prüfung verfügen, um anzugeben, dass allen ein Zertifikat zugewiesen wurde, einschließlich der OAuthTokenIssuer (siehe Abbildung), und klicken Sie dann auf **"Schließen**".
    
     ![Zertifikate installiert und ordnungsgemäß zugewiesen.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Wenn Sie die Installation in einer Laborumgebung durchführen und soeben die Zertifizierungsstelle mithilfe der Active Directory-Zertifikatdienste eingerichtet haben, müssen Sie sowohl den Server, auf dem Zertifikatdienste ausgeführt werden, als auch den Front-End-Server neu starten, bevor die Zertifikatzuweisung erfolgreich durchlaufen werden kann. 
  
    > [!TIP]
    >  Weitere Informationen zu Zertifikaten in Active Directory-Zertifikatdiensten finden Sie unter [Active Directory-Zertifikatdienste](/windows/deployment/deploy-whats-new). 
  
### <a name="step-4-start-services"></a>Schritt 4: Dienste starten

1. Überprüfen Sie die Voraussetzungen für **Schritt 4: Dienste starten**.
    
2. Wenn es sich um einen Enterprise Edition **Front-End-Pool** mit mindestens drei Servern handelt, wird Windows Fabric verwendet, und Sie müssen das Start-CsPool-Cmdlet verwenden. Wenn ein einzelner Server verwendet wird, was bei Standard Edition immer der Fall ist, verwenden Sie das **Cmdlet Start-CsWindowsService**. In diesem Beispiel verwenden wir Enterprise Edition mit drei Front-End-Servern im Pool, öffnen die **Skype for Business Server-Verwaltungsshell** und führen das **Start-CsPool-Cmdlet** aus, wie in der Abbildung dargestellt. Für alle anderen Rollen, einschließlich Standard Edition Servers, müssen Sie **Start-CsWindowsService** verwenden. Informationen zum Bereitstellen von anderen Rollen als der Front-End-Rolle finden Sie in der Dokumentation zu diesen bestimmten Rollen.
    
     ![Starten Sie Skype for Business Dienste.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine bewährte Methode, um zu melden, dass die Dienste tatsächlich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider. Es wird empfohlen, den Schritt **Dienststatus (Optional)** zu verwenden, um die Microsoft Management Console (MMC) zu öffnen und zu bestätigen, dass die Dienste erfolgreich gestartet wurden, wie in der Abbildung dargestellt. Wenn Skype for Business Server Dienst noch nicht gestartet wurde, können Sie im MMC mit der rechten Maustaste auf diesen Dienst klicken und dann auf **"Start**" klicken. 
  
     ![Überprüfen Sie, ob die Dienste gestartet wurden.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
