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
description: 'Zusammenfassung: Hier erfahren Sie, wie Sie die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server vom Microsoft Evaluation Center https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serverunter: herunter.'
ms.openlocfilehash: 0fe1c7b6088732932457d25c68a8fd6476a1bfbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018246"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Installieren von Skype for Business Server auf Servern in der Topologie
 
**Zusammenfassung:** Hier erfahren Sie, wie Sie die Skype for Business Server Systemkomponenten auf jedem Server in der Topologie installieren. Laden Sie eine ﻿kostenlose Testversion von Skype for Business Server aus dem [Microsoft Evaluation Center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)herunter.
  
Nachdem die Topologie in den zentraler Verwaltungsspeicher geladen wurde und Active Directory weiß, welche Server die Rollen ausführen, müssen Sie das Skype for Business Server System auf jedem Server in der Topologie installieren. Sie können die Schritte 1 bis 5 in beliebiger Reihenfolge ausführen. Sie müssen jedoch die Schritte 6, 7 und 8 in der Reihenfolge ausführen, und nach den Schritten 1 bis 5, wie im Diagramm dargestellt. Die Installation des Skype for Business Server Systems erfolgt Schritt 7 von 8.
  
![Overview-Diagramm.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Installieren Skype for Business Server Systems

Nachdem Sie eine Topologie veröffentlicht haben, können Sie die Skype for Business Server Komponenten auf jedem Server in der Topologie installieren. Dieser Abschnitt führt Sie durch die Installation von Skype for Business Server und das Einrichten der Serverrollen für die Front-End-Pool und alle Serverrollen, die mit den Front-End-Servern zusammengesetzt sind. Zum Installieren und Einrichten von Serverrollen führen Sie den Skype for Business Server-Bereitstellungs-Assistenten auf jedem Computer aus, auf dem Sie eine Serverrolle installieren. Sie verwenden den Bereitstellungs-Assistenten, um alle vier Bereitstellungsschritte abzuschließen, einschließlich der Installation des lokalen Konfigurationsspeichers, der Installation der Front-End-Server, der Konfiguration von Zertifikaten und dem Starten von Diensten.
  
> [!IMPORTANT]
> Sie müssen den Topologie-Generator verwenden, um die Topologie abzuschließen und zu veröffentlichen, bevor Sie Skype for Business Server auf Servern installieren können. 
  
> [!NOTE]
> Dieses Verfahren muss für alle Server in der Topologie ausgeführt werden. 
  
> [!CAUTION]
> Nachdem Sie Skype for Business Server auf einem Front-End-Server installiert haben, müssen Sie beim erstmaligen Starten von Diensten sicherstellen, dass der Windows-Firewalldienst auf dem Server läuft. 
  
> [!CAUTION]
> Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie bei dem Server mit einem Domänenbenutzerkonto angemeldet sind, das sowohl ein lokaler Administrator als auch ein Mitglied der RTCUniversalServerAdmins-Gruppe ist. 
  
> [!NOTE]
> Wenn Sie Skype for Business Server-Setup noch nicht auf diesem Server ausgeführt haben, werden Sie aufgefordert, ein Laufwerk und einen Pfad für die Installation einzugeben. Dies bietet die Möglichkeit, auf einem anderen Laufwerk als dem Systemlaufwerk zu installieren, wenn es für Ihre Organisation erforderlich ist, oder wenn Sie über Platzprobleme verfügen. Sie können den Pfad des Installationspfads für die Skype for Business Server Dateien im Dialogfeld **Setup** in ein neues verfügbares Laufwerk ändern. Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen Skype for Business Server Dateien bereitgestellt.
  
> [!IMPORTANT]
> Bevor Sie mit der Installation beginnen, stellen Sie sicher, dass Windows Server auf dem neuesten Stand ist, indem Sie Windows Update verwenden. 
  
![Windows Server auf dem neuesten Stand.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Installieren Skype for Business Server Systems

1. Legen Sie das Skype for Business Server Installationsmedium ein. Wenn das Setup nicht automatisch gestartet wird, doppelklicken Sie auf **Setup**.
    
2. Für die Installationsmedien muss Microsoft Visual C++ ausgeführt werden. Es wird ein Dialogfeld eingeblendet, in dem Sie gefragt werden, ob Sie es installieren möchten. Klicken Sie auf **Ja.**
    
3. Überprüfen Sie den Lizenzvertrag sorgfältig, und wenn Sie zustimmen, wählen Sie **Ich stimme den Bedingungen des Lizenzvertrags**zu, und klicken Sie auf **OK**. 
    
4. Smart Setup ist ein Feature in Skype for Business Server, in dem Sie während des Installationsvorgangs eine Verbindung mit dem Internet herstellen können, um nach Updates von Microsoft Update (MU) zu suchen, wie in der Abbildung dargestellt. Dies bietet eine bessere Erfahrung, indem Sie sicherstellen, dass Sie über die neuesten Updates für das Produkt verfügen. Klicken Sie auf **Installieren**, um mit der Installation zu beginnen.
    
    > [!NOTE]
    > Viele Organisationen verfügen über Windows Server Update Services (WSUS), die in ihrer Unternehmensumgebung bereitgestellt werden. Mit WSUS können Administratoren die Verteilung von Updates, die über Microsoft Update veröffentlicht werden, vollständig auf Computer in Ihrem Netzwerk verwalten. Im Rahmen des kumulativen Update 1-Releases Skype for Business Server die Unterstützung für Smart Setup für die Zusammenarbeit mit WSUS eingeführt. Kunden mit WSUS, die Skype for Business Server zum ersten Mal bereitstellen oder ein Upgrade von der lync Server 2013-Umgebung mithilfe des in-Place-Upgrades durchführen, haben intelligentes Setup für das Abrufen von Skype for Windows-Updates von WSUS im Gegensatz zum Abrufen von Updates. von Mu. Kunden, die Smart Setup verwenden möchten, müssen das SmartSetupWithWSUS. PSQ-System auf allen Computern ausführen, bevor Sie Setup. exe ausführen. 
  
     ![Screenshot von Smart Setup.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. Klicken Sie auf der Seite Bereitstellungs-Assistent auf **Skype for Business Server System installieren oder aktualisieren**.
    
6. Führen Sie die Verfahren in den folgenden Verfahren aus, wenn Sie diese abgeschlossen haben, klicken Sie auf **Beenden** , um den Bereitstellungs-Assistenten zu schließen. Wiederholen Sie die Verfahren für jeden Front-End-Server im Pool.
    
### <a name="step-1-install-local-configuration-store"></a>Schritt 1: Installieren des lokalen Konfigurationsspeichers

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 1: Installieren des lokalen Konfigurationsspeichers**.
    
    > [!NOTE]
    > Der lokale Konfigurationsspeicher ist eine schreibgeschützte Kopie der zentraler Verwaltungsspeicher. In einer Standard Edition-Bereitstellung wird das zentraler Verwaltungsspeicher mithilfe einer lokalen Kopie von SQL Server Express Edition auf dem Front-End-Server erstellt. Dies geschieht, wenn Sie das Verfahren zum Vorbereiten des ersten Standard Edition-Server ausführen. In einer Enterprise Edition-Bereitstellung wird der zentrale Verwaltungsspeicher erstellt, wenn Sie die Topologie veröffentlichen, die eine Enterprise Edition-Front-End-Pool enthält. 
  
2. Stellen Sie auf der Seite **lokalen Konfigurationsspeicher installieren** sicher, dass die Option **direkt aus dem zentralen Verwaltungsspeicher abrufen** ausgewählt ist, und klicken Sie dann auf **weiter**.
    
    SQL Server Express Edition ist auf dem lokalen Server installiert. SQL Server Express Edition ist für den lokalen Konfigurationsspeicher erforderlich.
    
3. Klicken Sie nach Abschluss der Installation der lokalen Serverkonfiguration auf **Fertig stellen**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Schritt 2: Einrichten oder Entfernen von Skype for Business Server Komponenten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen**.
    
2. Klicken Sie auf der Seite **Skype for Business Server Komponenten einrichten** auf **weiter** , um Komponenten gemäß der Definition in der veröffentlichten Topologie einzurichten.
    
3. Auf der Seite **Befehle werden ausgeführt** wird eine Zusammenfassung der Befehle und Installationsinformationen angezeigt, wenn die Einrichtung stattfindet. Anschließend können Sie die Liste zum Auswählen eines anzuzeigenden Protokolls verwenden und dann auf **Protokoll anzeigen**klicken.
    
4. Wenn Skype for Business Server-Komponenten-Setup abgeschlossen ist und Sie die Protokolle nach Bedarf überprüft haben, klicken Sie auf **Fertig stellen** , um diesen Schritt in der Installation abzuschließen.
    
    > [!NOTE]
    > Starten Sie den Server neu, wenn Sie dazu aufgefordert werden (was möglicherweise geschieht, wenn die Windows-Desktop Umgebung installiert werden muss). Wenn der Computer wieder betriebsbereit ist, müssen Sie diesen Vorgang (Schritt 2: Setup oder Entfernen von Skype for Business Server Komponenten) erneut ausführen. 
  
    > [!NOTE]
    > Wenn der Installer alle Voraussetzungen ermittelt, die nicht erfüllt wurden, werden Sie mit der Meldung "Voraussetzungs nicht erfüllt" benachrichtigt, wie in der Abbildung dargestellt. Erfüllen Sie die erforderliche Voraussetzung, und starten Sie dieses Verfahren erneut (Schritt 2: Einrichten oder Entfernen von Skype for Business Server Komponenten). 
  
     ![Erforderliche Voraussetzungen.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Stellen Sie sicher, dass die ersten beiden Schritte wie erwartet abgeschlossen wurden. Stellen Sie sicher, dass ein grünes Häkchen mit dem Wort **Complete**vorhanden ist, wie in der Abbildung dargestellt.
    
     ![Die ersten beiden Schritte wurden für die Installation von Komponenten abgeschlossen.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Führen Sie **Windows Update** erneut aus, um zu überprüfen, ob nach dem Installieren der Skype for Business Server-Komponenten Updates vorhanden sind.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Schritt 3: anfordern, installieren oder Zuweisen von Zertifikaten

1. Überprüfen Sie die Voraussetzungen, und klicken Sie dann auf **Ausführen** neben **Schritt 3: Zertifikate anfordern, installieren oder zuweisen**.
    
    > [!NOTE]
    > Skype for Business Server enthält Unterstützung für die SHA-2-Suite (SHA-2 verwendet Digest-Längen von 224, 256, 384 oder 512 Bits) von Digest-Hash-und Signaturalgorithmen für Verbindungen von Clients, auf denen die Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 Betriebssystemen. Um den externen Zugriff mithilfe der SHA-2-Suite zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die auch ein Zertifikat mit demselben Bit-Längen-Digest ausgeben kann. 
  
    > [!IMPORTANT]
    > Die Auswahl des Hash Digest-und Signaturalgorithmus hängt von den Clients und den Servern ab, auf denen das Zertifikat verwendet wird, sowie von anderen Computern und Geräten, mit denen Clients und Server kommunizieren, die auch wissen müssen, wie die in der Anwendung verwendeten Algorithmen verwendet werden sollen. Zertifikat. Informationen darüber, welche Digest-Längen im Betriebssystem und in einigen Clientanwendungen unterstützt werden, finden Sie unter [Windows PKI Blog-SHA2 und Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Jeder Standard Edition-oder Front-End-Server erfordert bis zu vier Zertifikate: das oAuthTokenIssuer-Zertifikat, ein Standardzertifikat, ein webinternes Zertifikat und ein webbasiertes externes Zertifikat. Sie können jedoch ein einzelnes Standardzertifikat mit entsprechenden Einträgen für alternative Antragstellernamen sowie das oAuthTokenIssuer-Zertifikat anfordern und zuweisen. Ausführliche Informationen zu den Zertifikatanforderungen finden Sie unter [Umgebungsanforderungen für Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) oder [Server Anforderungen für Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > Im folgenden Verfahren wird beschrieben, wie Sie Zertifikate von einer internen Active Directory Zertifikatdienst basierten Zertifizierungsstelle konfigurieren. 
  
2. Klicken Sie auf der Seite **Zertifizierungs-Assistent** auf **Anfordern**.
    
3. Geben Sie auf der Seite **Zertifikatanforderung** die relevanten Daten ein, einschließlich der Auswahl der SIP-Domäne, und klicken Sie auf **weiter**.
    
4. Sie können auf der Seite **Verzögerte oder sofortige Anforderungen** die Standardoption **Anforderung unmittelbar an eine Onlinezertifizierungsstelle senden** akzeptieren, indem Sie auf **Weiter** klicken. Die interne Zertifizierungsstelle mit automatischer Onlineregistrierung muss bei Auswahl dieser Option verfügbar sein. Wenn Sie die Option zur verzögerten Anforderung auswählen, werden Sie aufgefordert, einen Namen und einen Speicherort zur Speicherung der Zertifikatanforderungsdatei anzugeben. Die Zertifikatanforderung muss entweder von einer Zertifizierungsstelle in Ihrer Organisation oder von einer öffentlichen Zertifizierungsstelle bereitgestellt und verarbeitet werden. Sie müssen anschließend die Zertifikatantwort importieren und sie der entsprechenden Zertifikatrolle zuweisen.
    
5. Wählen Sie auf der Seite Zertifizierungs **Stelle** auswählen in der Liste **in Ihrer Umgebung erkannte Liste eine Zertifizierungsstelle auswählen aus** , und wählen Sie dann eine bekannte Zertifizierungsstelle (über die Registrierung in Active Directory-Domänendienste) aus der Liste aus. Alternativ können Sie die Option **Andere Zertifizierungsstelle angeben** auswählen, den Namen einer anderen Zertifizierungsstelle in das Feld eingeben und auf **Weiter** klicken.
    
6. Auf der Seite **zertifizierungsstellenkonto** werden Sie zur Eingabe von Anmeldeinformationen aufgefordert, um die Zertifikatanforderung bei der Zertifizierungsstelle anzufordern und zu verarbeiten. Sie sollten festgestellt haben, ob ein Benutzername und ein Kennwort erforderlich sind, um ein Zertifikat vorab anzufordern. Der Zertifizierungsstellenadministrator verfügt über die erforderlichen Informationen und kann Sie in diesem Schritt unterstützen. Wenn Sie alternative Anmeldeinformationen angeben müssen, aktivieren Sie das Kontrollkästchen, geben Sie in den Textfeldern einen Benutzernamen und ein Kennwort ein, und klicken Sie dann auf **weiter**.
    
7. Klicken Sie auf der Seite **Alternative Zertifikatvorlage angeben** auf **Weiter**, um die standardmäßige Webservervorlage zu verwenden.
    
    > [!NOTE]
    > Falls Ihre Organisation eine Vorlage für zur Nutzung als Alternative für die Standardvorlage für die Webserver-Zertifizierungsstelle erstellt hat, aktivieren Sie das Kontrollkästchen, und geben Sie den Namen der alternativen Vorlage ein. Sie müssen den vom Zertifizierungsstellenadministrator angegebenen Vorlagennamen eingeben. 
  
8. Geben Sie auf der Seite **namens-und Sicherheitseinstellungen** einen **Anzeigenamen**an. Mithilfe eines Anzeigenamens können Sie das Zertifikat und den Zweck schnell identifizieren. Wenn Sie das Feld leer lassen, wird automatisch ein Name generiert. Legen Sie die **Bit-Länge** des Schlüssels fest, oder übernehmen Sie den Standardwert von 2048 Bits. Wählen Sie den **privaten Schlüssel des Zertifikats als exportierbar kennzeichnen** aus, wenn Sie feststellen, dass das Zertifikat und der private Schlüssel verschoben oder auf andere Systeme kopiert werden müssen, und klicken Sie dann auf **weiter**.
    
    > [!NOTE]
    > Skype for Business Server hat minimale Anforderungen an einen exportierbaren privaten Schlüssel. Eine solche Stelle befindet sich auf den Edgeservern in einem Pool, in dem der Mediarelay-Authentifizierungsdienst Kopien des Zertifikats anstelle einzelner Zertifikate für jede Instanz im Pool verwendet. 
  
9. Geben Sie auf der Seite **Organisationsinformationen** optional Informationen zu Ihrer Organisation an, und klicken Sie dann auf **Weiter**.
    
10. Geben Sie auf der Seite **Geografische Informationen** optional geografische Informationen an, und klicken Sie dann auf **Weiter**.
    
11. Überprüfen Sie auf der Seite **Antragstellername/Alternative Antragstellernamen** die alternativen Antragstellernamen, die hinzugefügt werden, und klicken Sie dann auf **Weiter**.
    
12. Aktivieren Sie auf der Seite **SIP-Domäneneinstellung** die Option **SIP-Domäne**, und klicken Sie dann auf **Weiter**.
    
13. Geben Sie auf der Seite **Weitere alternative Antragstellernamen konfigurieren** zusätzlich erforderliche alternative Antragstellernamen an, und klicken Sie auf **Weiter**.
    
14. Überprüfen Sie auf der Seite **Zusammenfassung über Zertifikatsanforderungen** die Informationen in der Zusammenfassung. Wenn alle Informationen richtig angegeben sind, klicken Sie auf **Weiter**. Wenn Sie eine Einstellung korrigieren oder ändern müssen, klicken Sie auf **Zurück**, um zur entsprechenden Seite zu gelangen und die Korrektur oder Änderung durchzuführen.
    
15. Klicken Sie auf der Seite **Befehle werden ausgeführt** auf **Weiter**.
    
16. Überprüfen Sie auf der Seite **Status der Onlinezertifikatsanforderung** die angezeigten Informationen. Das Zertifikat sollte ausgegeben und in den lokalen Zertifikatspeicher installiert worden sein. Wenn das Zertifikat als ausgestellt und installiert gemeldet wird, es jedoch nicht gültig ist, stellen Sie sicher, dass das Zertifizierungsstellen-Stammzertifikat im vertrauenswürdigen Stammzertifizierungsstellen-Speicher des Servers installiert wurde. Informationen zum Anfordern des Zertifikats einer vertrauenswürdigen Stammzertifizierungsstelle finden Sie in der Dokumentation der Zertifizierungsstelle. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das angeforderte Zertifikat anzeigen möchten. Standardmäßig ist das Kontrollkästchen **Zertifikat Skype for Business Server Zertifikat Verwendungen zuweisen** ausgewählt. Wenn Sie das Zertifikat manuell zuweisen möchten, deaktivieren Sie das Kontrollkästchen, und klicken Sie dann auf **Fertig stellen**.
    
17. Wenn Sie das Kontrollkästchen zum **Zuweisen des Zertifikats zu Skype for Business Server Zertifikat Verwendungen** auf der vorherigen Seite deaktiviert haben, wird die Seite **zertifikatzuweisung** angezeigt. Klicken Sie auf **Weiter**.
    
18. Wählen Sie auf der Seite **Zertifikatspeicher** das von Ihnen angeforderte Zertifikat aus. Klicken Sie auf **Zertifikatdetails anzeigen**, wenn Sie das Zertifikat anzeigen möchten, und klicken Sie zum Fortfahren auf **Weiter**.
    
    > [!NOTE]
    > Wenn auf der Seite **Status der Online Zertifikatanforderung** ein Problem mit dem Zertifikat gemeldet wurde, beispielsweise das Zertifikat ist ungültig, zeigen Sie das tatsächliche Zertifikat an, um Hilfe beim Beheben des Problems zu erhalten. Zwei häufige Ursachen dafür, dass ein Zertifikat als ungültig angezeigt wird, sind das zuvor erwähnte fehlende Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle und ein fehlender privater Schlüssel, der dem Zertifikat zugeordnet ist. Informationen zur Lösung dieser beiden Probleme finden Sie in der Dokumentation der Zertifizierungsstelle.
  
19. Überprüfen Sie auf der Seite **Zusammenfassung der zertifikatzuweisung** die angezeigten Informationen, um sicherzustellen, dass es sich um das Zertifikat handelt, das zugewiesen werden soll, und klicken Sie dann auf **weiter**.
    
20. Überprüfen Sie auf der Seite **Befehle werden ausgeführt** die Befehlsausgabe. Klicken Sie auf **Protokoll anzeigen**, um zu überprüfen, ob bei der Zuweisung Fehler oder Warnungen ausgegeben wurden. Klicken Sie nach der Überprüfung auf **Fertig stellen**.
    
21. Vergewissern Sie sich auf der Seite **Zertifikat-Assistent** , dass alle Dienste über eine grüne Überprüfung verfügen, um anzugeben, dass allen Diensten ein Zertifikat zugewiesen wurde, einschließlich der OAuthTokenIssuer, wie in der Abbildung dargestellt, und klicken Sie dann auf **Schließen**.
    
     ![Zertifikate wurden installiert und ordnungsgemäß zugewiesen.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Wenn Sie in einer Testumgebung installieren und die Zertifizierungsstelle nur mit Active Directory Zertifikatdiensten eingerichtet haben, müssen Sie sowohl den Server mit den Zertifikatdiensten als auch den Front-End-Server vor dem Zertifikat neu starten. die Zuordnung kann erfolgreich durchlaufen werden. 
  
    > [!TIP]
    >  Weitere Informationen zu Zertifikaten in Active Directory Zertifikatdiensten finden Sie unter [Active Directory Certificate Services](https://technet.microsoft.com/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Schritt 4: Starten von Diensten

1. Überprüfen Sie die Voraussetzungen für **Schritt 4: Dienste starten**.
    
2. Wenn es sich um eine Enterprise Edition-Front-End-Pool mit mindestens drei Servern handelt, wird Windows Fabric verwendet, und Sie müssen das Cmdlet **Start-CsPool** verwenden. Wenn ein einzelner Server verwendet wird, was bei Standard Edition immer der Fall ist, verwenden Sie Muse das Cmdlet **Start-CsWindowsService** . In diesem Beispiel verwenden wir Enterprise Edition mit drei Front-End-Servern im Pool, öffnen Sie die **Skype for Business Server-Verwaltungsshell** , und führen Sie das Cmdlet **Start-CsPool** aus, wie in der Abbildung dargestellt. Für alle anderen Rollen, einschließlich Standard Edition-Server, müssen Sie **Start-CsWindowsService**verwenden. Informationen zum Bereitstellen anderer Rollen als der Front-End-Rolle finden Sie in der Dokumentation zu diesen bestimmten Rollen.
    
     ![Starten Sie Skype for Business Dienste.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. Klicken Sie nach dem erfolgreichen Start aller Dienste auf der Seite **Befehle ausführen** auf **Fertig stellen**.
    
    > [!IMPORTANT]
    > Der Befehl zum Starten der Dienste auf dem Server ist eine Methode mit dem besten Aufwand, um zu berichten, dass die Dienste tatsächlich gestartet wurden. Diese Anzeige spiegelt jedoch möglicherweise nicht den tatsächlichen Status des Diensts wider. Es wird empfohlen, den Schritt **Dienst Status (optional)** zum Öffnen der Microsoft Management Console (MMC) zu verwenden und sicherzustellen, dass die Dienste erfolgreich gestartet wurden, wie in der Abbildung dargestellt. Wenn Skype for Business Server Dienst noch nicht gestartet wurde, können Sie in der MMC mit der rechten Maustaste auf diesen Dienst klicken, und klicken Sie dann auf **starten**. 
  
     ![Überprüfen, ob Dienste gestartet wurden.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

