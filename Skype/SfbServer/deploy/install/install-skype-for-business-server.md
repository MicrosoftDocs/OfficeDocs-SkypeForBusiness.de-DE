---
title: Installieren von Skype for Business Server auf Servern in der Topologie
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Skype for Business Server-Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center unter herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 9ead15e0fd80d92d366eea5fd197516e9991b4a3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104861"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installieren von Skype for Business Server auf Servern in der Topologie
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Skype for Business Server-Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center herunter.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Sobald die Topologie in den zentralen Verwaltungsspeicher geladen wurde und Active Directory weiß, welche Server welche Rollen ausführen, müssen Sie das Skype for Business Server-System auf jedem Server in der Topologie installieren. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Installation des Skype for Business Server-Systems ist Schritt 7 von 8.
  
![Übersichtsdiagramm.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installieren des Skype for Business Server-Systems

Nachdem Sie eine Topologie veröffentlicht haben, können Sie die Skype for Business Server-Komponenten auf jedem Server in der Topologie installieren. Dieser Abschnitt führt Sie durch die Installation von Skype for Business Server und das Einrichten der Serverrollen für den Front-End-Pool und alle Serverrollen, die mit den Front-End-Servern zusammenarbeiten. Zum Installieren und Einrichten von Serverrollen führen Sie den Skype for Business Server-Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren. Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte zu ausführen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, dem Konfigurieren von Zertifikaten und dem Starten von Diensten.
  
> [!IMPORTANT]
> Sie müssen den Topologie-Generator verwenden, um die Topologie fertig zu machen und zu veröffentlichen, bevor Sie Skype for Business Server auf Servern installieren können. 
  
> [!NOTE]
> Dieses Verfahren muss für alle Server in der Topologie abgeschlossen sein. 
  
> [!CAUTION]
> Nachdem Sie Skype for Business Server auf einem Front-End-Server installiert haben, müssen Sie beim ersten Starten von Diensten sicherstellen, dass der Windows-Firewalldienst auf dem Server ausgeführt wird. 
  
> [!CAUTION]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie mit einem Domänenbenutzerkonto am Server angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der Gruppe "RTCUniversalServerAdmins" ist. 
  
> [!NOTE]
> Wenn Sie das Skype for Business Server-Setup noch nicht auf diesem Server ausgeführt haben, werden Sie zur Eingabe eines Laufwerks und Pfads für die Installation aufgefordert. Dies bietet die Möglichkeit, auf einem anderen Laufwerk als dem Systemlaufwerk zu installieren, wenn Es in Ihrer Organisation erforderlich ist oder Wenn Sie Platzbedenken haben. Sie können den Installationsspeicherortpfad für die Skype for Business Server-Dateien im Dialogfeld **Setup** in ein neues, verfügbares Laufwerk ändern. Wenn Sie die Setupdateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien dort bereitgestellt.
  
> [!IMPORTANT]
> Bevor Sie mit der Installation beginnen, stellen Sie sicher, dass Windows Server mit Windows Update auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installieren des Skype for Business Server-Systems

1. Fügen Sie das Skype for Business Server-Installationsmedium ein. Wenn das Setup nicht automatisch beginnt, doppelklicken Sie auf **Setup**.
    
2. Für das Installationsmedium muss Microsoft Visual C++ ausgeführt werden. Es wird ein Dialogfeld angezeigt, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie **auf Ja.**
    
3. Überprüfen Sie sorgfältig den Lizenzvertrag, und wenn Sie zustimmen, wählen Sie Ich stimme den Bedingungen **im** Lizenzvertrag zu, und klicken Sie auf **OK**. 
    
4. Smart Setup ist ein Feature in Skype for Business Server, mit dem Sie eine Verbindung mit dem Internet herstellen können, um während des Installationsprozesses nach Updates von Microsoft Update (MU) zu suchen, wie in der Abbildung dargestellt. Dies bietet eine bessere Erfahrung, indem Sie sicherstellen, dass Sie über die neuesten Updates für das Produkt verfügen. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
    > [!NOTE]
    > In vielen Organisationen werden Windows Server Update Services (WSUS) in ihren Unternehmensumgebungen bereitgestellt. Mit WSUS können Administratoren die Verteilung von Updates, die über Microsoft Update auf Computer in ihrem Netzwerk veröffentlicht werden, vollständig verwalten. Im Rahmen der kumulativen Version von Update 1 wurde von Skype for Business Server Unterstützung für das Smart Setup für die Arbeit mit WSUS eingeführt. Kunden mit WSUS, die Skype for Business Server zum ersten Mal bereitstellen oder ein Upgrade von der Lync Server 2013-Umgebung mithilfe des In-Place-Upgradefeatures durchführen, verfügen über smartes Setup, das Skype for Windows-Updates von WSUS abruft, statt Updates von MU zu erhalten. Kunden, die Smart Setup verwenden möchten, müssen smartSetupWithWSUS.psq auf allen Computern ausführen, bevor sie Setup.exe. 
  
     ![Screenshot des smarten Setups.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Klicken Sie auf der Seite Bereitstellungs-Assistent auf **Installieren oder Aktualisieren von Skype for Business Server System**.
    
6. Führen Sie die Verfahren in den folgenden Verfahren aus, wenn Sie sie abgeschlossen haben, klicken Sie auf **Beenden,** um den Bereitstellungs-Assistenten zu schließen. Wiederholen Sie die Verfahren für jeden Front-End-Server im Pool.
    
### <a name="step-1-install-local-configuration-store"></a>Schritt 1: Installieren des lokalen Konfigurationsspeichers

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 1: Installieren des lokalen Konfigurationsspeichers**.
    
    > [!NOTE]
    > Der lokale Konfigurationsspeicher ist eine schreibgeschützte Kopie des zentralen Verwaltungsspeichers. In einer Standard Edition-Bereitstellung wird der zentrale Verwaltungsspeicher mithilfe einer lokalen Kopie von SQL Server Express Edition auf dem Front-End-Server erstellt. Dies geschieht, wenn Sie die Prepare First Standard Edition Server-Prozedur ausführen. In einer Enterprise Edition-Bereitstellung wird der zentrale Verwaltungsspeicher erstellt, wenn Sie die Topologie veröffentlichen, die einen Enterprise Edition-Front-End-Pool enthält. 
  
2. Stellen Sie **auf der Seite Lokaler Konfigurationsspeicher** installieren sicher, dass die Option Direkt aus dem zentralen **Verwaltungsspeicher** abrufen ausgewählt ist, und klicken Sie dann auf **Weiter**.
    
    SQL Server Express Edition ist auf dem lokalen Server installiert. SQL Server Express Edition ist für den lokalen Konfigurationsspeicher erforderlich.
    
3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**.
    
2. Klicken Sie **auf der Seite Skype for Business Server-Komponenten** einrichten auf **Weiter,** um Komponenten wie in Der veröffentlichten Topologie definiert einrichten.
    
3. Auf **der Seite Befehle ausführen** wird eine Zusammenfassung der Befehle und Installationsinformationen angezeigt, während die Einrichtung stattfindet. Wenn sie fertig ist, können Sie die Liste verwenden, um ein zu zeigendes Protokoll auszuwählen, und dann auf **Protokoll anzeigen klicken.**
    
4. Wenn das Setup der Skype for Business Server-Komponenten abgeschlossen ist und Sie die Protokolle bei Bedarf überprüft haben, klicken Sie auf **Fertig** stellen, um diesen Schritt in der Installation abzuschließen.
    
    > [!NOTE]
    > Starten Sie den Server neu, wenn Sie dazu aufgefordert werden (dies kann vorkommen, wenn Windows Desktop Experience installiert werden muss). Wenn der Computer wieder ausgeführt wird, müssen Sie dieses Verfahren (Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten) erneut ausführen. 
  
    > [!NOTE]
    > Wenn das Installationsprogramm Voraussetzungen findet, die nicht erfüllt wurden, werden Sie mit der Meldung "Voraussetzung nicht erfüllt" benachrichtigt, wie in der Abbildung dargestellt. Erfüllen Sie die erforderliche Voraussetzung, und starten Sie dann das Verfahren (Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten) erneut. 
  
     ![Erforderliche Voraussetzung.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Stellen Sie sicher, dass die ersten beiden Schritte wie erwartet abgeschlossen wurden. Vergewissern Sie sich, dass es ein grünes Häkchen mit dem Wort **Complete** gibt, wie in der Abbildung dargestellt.
    
     ![Die ersten beiden Schritte wurden nach der Installation von Komponenten abgeschlossen.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Führen **Sie Windows Update** erneut aus, um nach der Installation der Skype for Business Server-Komponenten zu überprüfen, ob Updates vorhanden sind.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten**.
    
    > [!NOTE]
    > Skype for Business Server bietet Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digestlängen von 224, 256, 384 oder 512 Bit) von Digesthash- und Signaturalgorithmen für Verbindungen von Clients unter Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2. Um den externen Zugriff mithilfe der SHA-2-Suite zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit derselben Bitlänge für digests aus ausgestellt werden kann. 
  
    > [!IMPORTANT]
    > Die Auswahl des Hashdaugests und des Signaturalgorithmus hängt von den Clients und Servern ab, auf denen das Zertifikat verwendet wird, sowie von anderen Computern und Geräten, mit denen Clients und Server kommunizieren, die auch wissen müssen, wie die im Zertifikat verwendeten Algorithmen verwendet werden. Informationen dazu, welche Digestlängen im Betriebssystem und einigen Clientanwendungen unterstützt werden, finden Sie im [Windows PKI-Blog SHA2 und Windows](/archive/blogs/pki/sha2-and-windows). 
  
    Jeder Standard Edition- oder Front-End-Server benötigt bis zu vier Zertifikate: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein webinternes Zertifikat und ein externes Webzertifikat. Sie können jedoch ein einzelnes Standardzertifikat mit entsprechenden alternativen Betreffnameneinträgen sowie das oAuthTokenIssuer-Zertifikat anfordern und zuweisen. Weitere Informationen zu den Zertifikatanforderungen finden Sie unter [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype for Business Server [2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > Im folgenden Verfahren wird beschrieben, wie Zertifikate von einer internen Active Directory Certificate Services-basierten Zertifizierungsstelle konfiguriert werden. 
  
2. Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.
    
3. Geben Sie **auf der Seite Zertifikatanforderung** die relevanten Daten ein, einschließlich auswahl der SIP-Domäne, und klicken Sie auf **Weiter**.
    
4. Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Die interne Zertifizierungsstelle mit automatischer Onlineregistrierung muss bei Auswahl dieser Option verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Sie müssen anschließend die Zertifikatantwort importieren und sie der entsprechenden Zertifikatrolle zuweisen.
    
5. Wählen  Sie auf der Seite Zertifizierungsstelle auswählen die Option Zertifizierungsstelle aus der Liste auswählen aus, die **in** Ihrer Umgebung erkannt wurde, und wählen Sie dann eine bekannte Zertifizierungsstelle (durch Registrierung in Active Directory Domain Services) aus der Liste aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.
    
6. Auf der **Seite Zertifizierungsstellenkonto** werden Sie aufgefordert, Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatanforderung bei der Zertifizierungsstelle ein. Sie sollten bestimmt haben, ob ein Benutzername und ein Kennwort erforderlich sind, um ein Zertifikat im Voraus anantragen zu können. Ihr Zertifizierungsstellenadministrator hat die erforderlichen Informationen und muss Sie möglicherweise bei diesem Schritt unterstützen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie in den Textfeldern einen Benutzernamen und ein Kennwort ein, und klicken Sie dann auf **Weiter**.
    
7. Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage für zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen, und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben. 
  
8. Geben Sie auf der Seite Name **und Sicherheitseinstellungen** einen **Anzeigenamen an.** Mithilfe eines Anzeigenamens können Sie das Zertifikat und den Zweck schnell identifizieren. Wenn Sie ihn leer lassen, wird automatisch ein Name generiert. Legen Sie **die Bitlänge** des Schlüssels oder den Standardwert von 2048 Bit an. Wählen Sie den privaten Schlüssel des Zertifikats als **exportierbar** markieren aus, wenn Sie feststellen, dass das Zertifikat und der private Schlüssel verschoben oder in andere Systeme kopiert werden müssen, und klicken Sie dann auf **Weiter**.
    
    > [!NOTE]
    > Skype for Business Server hat minimale Anforderungen an einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet. 
  
9. Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an, und klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an, und klicken Sie dann auf **Weiter**.
    
11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.
    
12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne**, und klicken Sie dann auf **Weiter**.
    
13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.
    
14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.
    
15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.
    
16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Wenn gemeldet wird, dass es ausgestellt und installiert wurde, es jedoch ungültig ist, stellen Sie sicher, dass das Stammzertifikat der Zertifizierungsstelle im vertrauenswürdigen Stammzertifizierungsstellenspeicher des Servers installiert wurde. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das angeforderte Zertifikat anzeigen möchten. Standardmäßig ist das Kontrollkästchen Zertifikatverwendungen **von Skype for Business Server** zuweisen aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.
    
17. Wenn Sie das Kontrollkästchen Zertifikat skype **for Business Server-Zertifikatverwendungen** auf der vorherigen Seite zuweisen nicht aktivieren, wird ihnen die Seite **Zertifikatzuweisung** angezeigt. Klicken Sie auf **Weiter**.
    
18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    > [!NOTE]
    > Wenn auf **der Seite Onlinezertifikatsanforderungsstatus** ein Problem mit dem Zertifikat gemeldet wurde, z. B. wenn das Zertifikat ungültig ist, zeigen Sie das tatsächliche Zertifikat an, um Hilfe bei der Lösung des Problems zu erhalten. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.
  
19. Überprüfen Sie **auf** der Seite Zusammenfassung der Zertifikatzuweisung die angezeigten Informationen, um sicherzustellen, dass dies das Zertifikat ist, das zugewiesen werden soll, und klicken Sie dann auf **Weiter**.
    
20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.
    
21. Vergewissern  Sie sich auf der Seite Zertifikat-Assistent, dass alle Dienste über eine grüne Überprüfung verfügen, um anzugeben, dass allen ein Zertifikat zugewiesen wurde, einschließlich OAuthTokenIssuer , wie in der Abbildung dargestellt, und klicken Sie dann auf **Schließen**.
    
     ![Zertifikate ordnungsgemäß installiert und zugewiesen.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Wenn Sie in einer Laborumgebung installieren und gerade die Zertifizierungsstelle mithilfe von Active Directory Certificate Services eingerichtet haben, müssen Sie sowohl den Server mit Zertifikatdiensten als auch den Front-End-Server neu starten, bevor die Zertifikatzuweisung erfolgreich durchgeführt werden kann. 
  
    > [!TIP]
    >  Weitere Informationen zu Zertifikaten in Active Directory Certificate Services finden Sie unter [Active Directory Certificate Services](/windows/deployment/deploy-whats-new). 
  
### <a name="step-4-start-services"></a>Schritt 4: Starten von Diensten

1. Überprüfen Sie die Voraussetzungen für **Schritt 4: Starten von Diensten**.
    
2. Wenn es sich um einen Enterprise Edition-Front-End-Pool mit mindestens drei Servern handelt, wird Windows Fabric verwendet, und Sie müssen das **Cmdlet Start-CsPool** verwenden. Wenn ein einzelner Server verwendet wird, was bei Standard Edition immer der Fall ist, verwenden Sie das **Cmdlet Start-CsWindowsService.** In diesem Beispiel verwenden wir Enterprise Edition mit drei **Front-End-Servern** im Pool, öffnen die **Skype for Business Server-Verwaltungsshell** und führen das Cmdlet Start-CsPool aus, wie in der Abbildung dargestellt. Für alle anderen Rollen, einschließlich Standard Edition-Server, müssen Sie **Start-CsWindowsService verwenden.** Informationen zum Bereitstellen anderer Rollen als der Front-End-Rolle finden Sie in der Dokumentation zu diesen bestimmten Rollen.
    
     ![Starten Sie Skype for Business-Dienste.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine optimale Methode, um zu melden, dass die Dienste tatsächlich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider. Es wird empfohlen, den Schritt **Dienststatus (Optional)** zu verwenden, um die Microsoft Management Console (MMC) zu öffnen und zu bestätigen, dass die Dienste erfolgreich gestartet wurden, wie in der Abbildung dargestellt. Wenn kein Skype for Business Server-Dienst gestartet wurde, können Sie im MMC mit der rechten Maustaste auf diesen Dienst klicken und dann auf **Starten klicken.** 
  
     ![Überprüfen, ob Dienste gestartet wurden.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
