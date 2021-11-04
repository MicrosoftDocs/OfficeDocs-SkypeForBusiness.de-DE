---
title: Installieren Skype for Business Server auf Servern in der Topologie
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
description: 'Zusammenfassung: Erfahren Sie, wie Sie die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem Microsoft Evaluation Center herunter: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: bcf2645e6f33865da0f1ad6bbc985e581950693b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745301"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installieren Skype for Business Server auf Servern in der Topologie
 
**Zusammenfassung:** Erfahren Sie, wie Sie die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Nachdem die Topologie in die zentrale Verwaltungs Store geladen wurde und Active Directory weiß, welche Server welche Rollen ausführen, müssen Sie das Skype for Business Server System auf jedem Server in der Topologie installieren. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge und nach den Schritten 1 bis 5 ausführen, wie im Diagramm beschrieben. Die Installation des Skype for Business Server Systems ist Schritt 7 von 8.
  
![Übersichtsdiagramm.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installieren Skype for Business Server Systems

Nachdem Sie eine Topologie veröffentlicht haben, können Sie die Skype for Business Server Komponenten auf jedem Server in der Topologie installieren. Dieser Abschnitt führt Sie durch das Installieren Skype for Business Server und Einrichten der Serverrollen für den Front-End-Pool und alle Serverrollen, die mit den Front-End-Servern verbunden sind. Um Serverrollen zu installieren und einzurichten, führen Sie den Skype for Business Server Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren. Mit dem Bereitstellungs-Assistenten führen Sie alle vier Bereitstellungsschritte aus, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, dem Konfigurieren von Zertifikaten und dem Starten von Diensten.
  
> [!IMPORTANT]
> Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie Skype for Business Server auf Servern installieren können. 
  
> [!NOTE]
> Dieses Verfahren muss für alle Server in der Topologie abgeschlossen werden. 
  
> [!CAUTION]
> Nachdem Sie Skype for Business Server auf einem Front-End-Server installiert haben, müssen Sie beim ersten Starten der Dienste sicherstellen, dass der Windows Firewalldienst auf dem Server ausgeführt wird. 
  
> [!CAUTION]
> Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie mit einem Domänenbenutzerkonto, das ein lokaler Administrator und Mitglied der Gruppe "RTCUniversalServerAdmins" ist, auf dem Server angemeldet sind. 
  
> [!NOTE]
> Wenn Sie Skype for Business Server Setup auf diesem Server noch nicht ausgeführt haben, werden Sie zur Eingabe eines Laufwerks und Pfads für die Installation aufgefordert. Dies bietet die Möglichkeit, auf einem anderen Laufwerk als dem Systemlaufwerk zu installieren, wenn Ihre Organisation dies erfordert oder wenn Sie Bedenken hinsichtlich des Speicherplatzes haben. Sie können den Installationspfad für die Skype for Business Server Dateien im Dialogfeld **"Setup"** in ein neues, verfügbares Laufwerk ändern. Wenn Sie die Setupdateien unter diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen Skype for Business Server-Dateien dort bereitgestellt.
  
> [!IMPORTANT]
> Bevor Sie mit der Installation beginnen, stellen Sie mithilfe von Windows Update sicher, dass Windows Server auf dem neuesten Stand ist. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installieren Skype for Business Server Systems

1. Fügen Sie das Skype for Business Server Installationsmedium ein. Wenn das Setup nicht automatisch beginnt, doppelklicken Sie auf **Setup**.
    
2. Das Installationsmedium erfordert Microsoft Visual C++, um ausgeführt zu werden. Es wird ein Dialogfeld angezeigt, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **"Ja".**
    
3. Überprüfen Sie den Lizenzvertrag sorgfältig, und wenn Sie damit einverstanden sind, wählen Sie **"Ich stimme den Bedingungen im Lizenzvertrag zu,** und klicken Sie auf **OK."** 
    
4. Smart Setup ist ein Feature in Skype for Business Server, bei dem Sie während des Installationsvorgangs eine Verbindung mit dem Internet herstellen können, um während des Installationsvorgangs nach Updates von Microsoft Update (MU) zu suchen, wie in der Abbildung dargestellt. Dies bietet eine bessere Benutzererfahrung, indem sichergestellt wird, dass Sie über die neuesten Updates für das Produkt verfügen. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
    > [!NOTE]
    > Viele Organisationen haben Windows Server Update Services (WSUS) in ihren Unternehmensumgebungen bereitgestellt. Mit WSUS können Administratoren die Verteilung von Updates, die über Microsoft Update veröffentlicht werden, vollständig auf Computern in ihrem Netzwerk verwalten. Im Rahmen der kumulativen Update 1-Version wurde Skype for Business Server Unterstützung für smartes Setup eingeführt, um mit WSUS zu arbeiten. Kunden mit WSUS, die Skype for Business Server zum ersten Mal bereitstellen oder ein Upgrade von der Lync Server 2013-Umgebung mithilfe der Funktion In-Place Upgrade durchführen, verfügen über smartes Setup, das Skype für Windows Updates von WSUS abruft, im Gegensatz zum Abrufen von Updates von MU. Kunden, die Smart Setup verwenden möchten, müssen smartSetupWithWSUS.psq auf allen Computern ausführen, bevor sie Setup.exe ausführen. 
  
     ![Smart Setup-Screenshot.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Klicken Sie auf der Seite des Bereitstellungs-Assistenten auf **"Installieren" oder "Aktualisieren Skype for Business Server System".**
    
6. Führen Sie die Verfahren in den folgenden Prozeduren aus. Klicken Sie nach Abschluss auf **"Beenden",** um den Bereitstellungs-Assistenten zu schließen. Wiederholen Sie die Prozeduren für jeden Front-End-Server im Pool.
    
### <a name="step-1-install-local-configuration-store"></a>Schritt 1: Installieren der lokalen Konfiguration Store

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **"Ausführen"** neben **Schritt 1: Installieren der lokalen Konfiguration Store.**
    
    > [!NOTE]
    > Das Store "Lokale Konfiguration" ist eine schreibgeschützte Kopie der zentralen Verwaltungs Store. In einer Standard Edition Bereitstellung wird die zentrale Store mithilfe einer lokalen Kopie von SQL Server Express Edition auf dem Front-End-Server erstellt. Dies geschieht, wenn Sie die Prozedur "Erste Standard Edition Server vorbereiten" ausführen. In einer Enterprise Edition Bereitstellung wird der zentrale Verwaltungsspeicher erstellt, wenn Sie die Topologie veröffentlichen, die einen Enterprise Edition Front-End-Pool enthält. 
  
2. Stellen Sie auf der Seite **"Lokale Konfiguration installieren" Store** sicher, dass die Option **"Direkt aus dem zentralen Verwaltungsspeicher abrufen"** ausgewählt ist, und klicken Sie dann auf **"Weiter".**
    
    SQL Server Express Die Edition wird auf dem lokalen Server installiert. SQL Server Express Edition ist für den lokalen Konfigurationsspeicher erforderlich.
    
3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **"Ausführen"** neben **Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten.**
    
2. Klicken Sie auf der Seite **"Einrichten Skype for Business Server Komponenten"** auf **"Weiter",** um Komponenten wie in Ihrer veröffentlichten Topologie definiert einzurichten.
    
3. Auf der Seite **"Befehle ausführen"** wird während der Einrichtung eine Zusammenfassung der Befehle und Installationsinformationen angezeigt. Wenn sie fertig ist, können Sie die Liste verwenden, um ein anzuzeigende Protokoll auszuwählen, und klicken Sie dann auf **"Protokoll anzeigen".**
    
4. Wenn Skype for Business Server Komponenten eingerichtet ist und Sie die Protokolle nach Bedarf überprüft haben, klicken Sie auf **Fertig stellen,** um diesen Schritt in der Installation abzuschließen.
    
    > [!NOTE]
    > Starten Sie den Server neu, wenn Sie dazu aufgefordert werden (dies kann passieren, wenn Windows Desktopdarstellung installiert werden muss). Wenn der Computer wieder betriebsbereit ist, müssen Sie dieses Verfahren (Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten) erneut ausführen. 
  
    > [!NOTE]
    > Wenn das Installationsprogramm Voraussetzungen findet, die nicht erfüllt wurden, werden Sie mit der Meldung "Voraussetzung nicht erfüllt" benachrichtigt, wie in der Abbildung dargestellt. Erfüllen Sie die erforderlichen Voraussetzungen, und starten Sie die Prozedur (Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten) erneut. 
  
     ![Voraussetzung erforderlich.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Stellen Sie sicher, dass die ersten beiden Schritte wie erwartet abgeschlossen wurden. Vergewissern Sie sich, dass ein grünes Häkchen mit dem Wort **"Abgeschlossen"** vorhanden ist, wie in der Abbildung dargestellt.
    
     ![Die ersten beiden Schritte wurden mit der Installation von Komponenten abgeschlossen.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob nach der Installation der Skype for Business Server-Komponenten Updates vorhanden sind.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **"Ausführen"** neben **Schritt 3: Anfordern, Installieren oder Zuweisen von Zertifikaten.**
    
    > [!NOTE]
    > Skype for Business Server unterstützt die SHA-2-Suite (SHA-2 verwendet Digestlängen von 224, 256, 384 oder 512 Bit) von Digesthash- und Signaturalgorithmen für Verbindungen von Clients, die die Betriebssysteme Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 ausführen. Um den externen Zugriff mit der SHA-2-Suite zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit dem gleichen Bitlängendigest ausstellen kann. 
  
    > [!IMPORTANT]
    > Die Auswahl des Hashdigests und Signaturalgorithmus hängt von den Clients und den Servern ab, die das Zertifikat verwenden, sowie von anderen Computern und Geräten, mit denen Clients und Server kommunizieren, die auch wissen müssen, wie die im Zertifikat verwendeten Algorithmen verwendet werden sollen. Informationen dazu, welche Digestlängen im Betriebssystem und in einigen Clientanwendungen unterstützt werden, finden Sie unter [Windows PKI-Blog SHA2 und Windows.](/archive/blogs/pki/sha2-and-windows) 
  
    Jeder Standard Edition- oder Front-End-Server benötigt bis zu vier Zertifikate: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein internes Webzertifikat und ein externes Webzertifikat. Sie können jedoch ein einzelnes Standardzertifikat mit entsprechenden einträgen alternativen Antragstellernamen sowie das oAuthTokenIssuer-Zertifikat anfordern und zuweisen. Ausführliche Informationen zu den Zertifikatsanforderungen finden Sie unter ["Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019".](../../../SfBServer2019/plan/system-requirements.md)
    
    > [!IMPORTANT]
    > Im folgenden Verfahren wird beschrieben, wie Zertifikate von einer internen Active Directory-Zertifikatdienste-basierten Zertifizierungsstelle konfiguriert werden. 
  
2. Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.
    
3. Geben Sie auf der Seite **"Zertifikatanforderung"** die relevanten Daten ein, einschließlich der Auswahl der SIP-Domäne, und klicken Sie auf **"Weiter".**
    
4. Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Die interne Zertifizierungsstelle mit automatischer Onlineregistrierung muss bei Auswahl dieser Option verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Sie müssen anschließend die Zertifikatantwort importieren und sie der entsprechenden Zertifikatrolle zuweisen.
    
5. Wählen Sie auf der Seite **"Zertifizierungsstelle auswählen"** die Option "Zertifizierungsstelle auswählen" aus der Liste aus, die **in Ihrer Umgebungsoption erkannt wurde,** und wählen Sie dann eine bekannte Zertifizierungsstelle (über die Registrierung in Active Directory Domain Services) aus der Liste aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.
    
6. Auf der Seite **"Zertifizierungsstellenkonto"** werden Sie aufgefordert, Anmeldeinformationen zum Anfordern und Verarbeiten der Zertifikatanforderung bei der Zertifizierungsstelle einzugeben. Sie sollten ermittelt haben, ob ein Benutzername und ein Kennwort erforderlich sind, um vorab ein Zertifikat anzufordern. Ihr Zertifizierungsstellenadministrator verfügt über die erforderlichen Informationen und muss Sie bei diesem Schritt unterstützen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie einen Benutzernamen und ein Kennwort in den Textfeldern an, und klicken Sie dann auf **"Weiter".**
    
7. Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage für zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen, und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben. 
  
8. Geben Sie auf der Seite **Name und Sicherheit Einstellungen** einen **Anzeigenamen** an. Mithilfe eines Anzeigenamens können Sie das Zertifikat und den Zweck schnell identifizieren. Wenn Sie ihn leer lassen, wird automatisch ein Name generiert. Legen Sie die **Bitlänge** des Schlüssels fest, oder übernehmen Sie den Standardwert von 2048 Bit. Wählen Sie den **privaten Schlüssel des Zertifikats als exportierbar markieren,** wenn Sie feststellen, dass das Zertifikat und der private Schlüssel in andere Systeme verschoben oder kopiert werden müssen, und klicken Sie dann auf **"Weiter".**
    
    > [!NOTE]
    > Skype for Business Server hat minimale Anforderungen für einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet. 
  
9. Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an, und klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an, und klicken Sie dann auf **Weiter**.
    
11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.
    
12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne**, und klicken Sie dann auf **Weiter**.
    
13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.
    
14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.
    
15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.
    
16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Wenn gemeldet wird, dass es ausgestellt und installiert wurde, aber ungültig ist, stellen Sie sicher, dass das Stammzertifikat der Zertifizierungsstelle im Speicher der vertrauenswürdigen Stammzertifizierungsstelle des Servers installiert wurde. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das angeforderte Zertifikat anzeigen möchten. Standardmäßig ist das Kontrollkästchen zum **Zuweisen des Zertifikats zu Skype for Business Server Zertifikatverwendungen** aktiviert. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.
    
17. Wenn Sie das Kontrollkästchen zum **Zuweisen des Zertifikats zu Skype for Business Server Zertifikatverwendungen** auf der vorherigen Seite deaktiviert haben, wird die Seite **"Zertifikatzuweisung"** angezeigt. Klicken Sie auf **Weiter**.
    
18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    > [!NOTE]
    > Wenn auf der Seite "Status der **Onlinezertifikatanforderung"** ein Problem mit dem Zertifikat gemeldet wurde, z. B. wenn das Zertifikat ungültig ist, zeigen Sie das eigentliche Zertifikat an, um Hilfe bei der Behebung des Problems zu finden. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.
  
19. Überprüfen Sie auf der Seite "Zusammenfassung der **Zertifikatzuweisung"** die angezeigten Informationen, um sicherzustellen, dass dies das Zertifikat ist, das zugewiesen werden soll, und klicken Sie dann auf **"Weiter".**
    
20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.
    
21. Vergewissern Sie sich auf der Seite des **Zertifikat-Assistenten,** dass alle Dienste über eine grüne Überprüfung verfügen, um anzugeben, dass allen ein Zertifikat zugewiesen wurde, einschließlich OAuthTokenIssuer ,wie in der Abbildung dargestellt, und klicken Sie dann auf **"Schließen".**
    
     ![Ordnungsgemäß installierte und zugewiesene Zertifikate.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Wenn Sie in einer Testumgebung installieren und die Zertifizierungsstelle gerade mithilfe von Active Directory-Zertifikatdiensten eingerichtet haben, müssen Sie sowohl den Server, auf dem Zertifikatdienste ausgeführt werden, als auch den Front-End-Server neu starten, bevor die Zertifikatzuweisung erfolgreich durchlaufen werden kann. 
  
    > [!TIP]
    >  Weitere Informationen zu Zertifikaten in Active Directory-Zertifikatdiensten finden Sie unter [Active Directory-Zertifikatdienste.](/windows/deployment/deploy-whats-new) 
  
### <a name="step-4-start-services"></a>Schritt 4: Dienste starten

1. Überprüfen Sie die Voraussetzungen für **Schritt 4: Dienste starten.**
    
2. Wenn es sich um einen Enterprise Edition Front-End-Pool mit mindestens drei Servern handelt, wird Windows Fabric verwendet, und Sie müssen das Cmdlet **"Start-CsPool"** verwenden. Wenn ein einzelner Server verwendet wird, was bei Standard Edition immer der Fall ist, verwenden Sie das Cmdlet **"Start-CsWindowsService".** In diesem Beispiel verwenden wir Enterprise Edition mit drei Front-End-Servern im Pool, öffnen die **Skype for Business Server Verwaltungsshell,** und führen Sie das Cmdlet **"Start-CsPool"** aus, wie in der Abbildung dargestellt. Für alle anderen Rollen, einschließlich Standard Edition Servers, müssen Sie **Start-CsWindowsService** verwenden. Informationen zum Bereitstellen anderer Rollen als der Front-End-Rolle finden Sie in der Dokumentation zu diesen bestimmten Rollen.
    
     ![Starten Sie Skype for Business Dienste.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine Best Effort-Methode, um zu melden, dass die Dienste tatsächlich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider. Es wird empfohlen, den Schritt **"Dienststatus (Optional)** zu verwenden, um die Microsoft Management Console (MMC) zu öffnen und zu bestätigen, dass die Dienste erfolgreich gestartet wurden(siehe Abbildung). Wenn ein Skype for Business Server Dienst nicht gestartet wurde, können Sie im MMC mit der rechten Maustaste auf diesen Dienst klicken und dann auf **"Start"** klicken. 
  
     ![Überprüfen Sie, ob Dienste gestartet wurden.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
