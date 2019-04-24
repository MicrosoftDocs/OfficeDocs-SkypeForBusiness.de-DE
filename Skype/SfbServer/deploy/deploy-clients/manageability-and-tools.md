---
title: Skype Room System – Verbesserte Verwaltung und Tools
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lesen Sie dieses Thema und erfahren Sie mehr über Verwaltungstools für Skype Room System.
ms.openlocfilehash: 9be385030ad09e73608b461c5a0c05cea70987c0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219402"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Room System – Verbesserte Verwaltung und Tools
 
Lesen Sie dieses Thema und erfahren Sie mehr über Verwaltungstools für Skype Room System.
  
## <a name="administrative-portal"></a>Verwaltungsportal

Skype für lokale Bereitstellungen Business Server können Sie für die administrative Portal Skype Raum System aktiv verwalten und Überwachen von Skype Raum System Bereitstellungen in Ihrer Organisation.
  
Finden Sie weitere Informationen im folgenden Artikel:
  
- [Bereitstellen von SRS v1 Administrative Webportal in Skype für Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Skype-Chatroom-System kann über die System Center Operations Manager (SCOM) durch das [Skype Raum System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) herunterladen und installieren es auf Ihrem SCOM-Server überwacht werden. SCOM können Sie Warnungen festlegen, Überwachen des Zustands der Skype Raum System, generieren Sie Berichte Betriebszeit und vieles mehr. Skype-Raum System umfasst einen vorinstallierte monitoring Agent, der konfiguriert werden kann, um SCOM-Server zu verweisen. Finden Sie im Installationshandbuch vom Hersteller Ihres Skype Raum System wissen, wie Sie überwachen den Agent Skype Raum System zu konfigurieren.
  
## <a name="exchange-checklist"></a>Exchange-Checkliste

- Stellen Sie sicher, dass der AutoErmittlungsdienst eingerichtet ist und dass ein interner DNS-A/CNAME-Eintrag für „autodiscover.domain.com“ verfügbar ist.
    
- Senden Sie ein Pingsignal an den AutoErmittlungsdienst (z. B. „ping autodiscover.contoso.com“).
    
- Testen Sie Ihren AutoErmittlungsdienst mithilfe des Tools Microsoft Connectivity Analyzer. Wählen Sie den ersten Test "Ich kann nicht mit Office Outlook anmelden."
    
- Wenn Besprechungsraum bereits ein Ressourcenpostfach verfügt, erweitern Sie dieses Konto für Skype Raum System (Beispielskript am unteren Rand der Seite).
    
## <a name="skype-for-business-checklist"></a>Skype für Business-Prüfliste

- Führen Sie die folgenden Tools aus:
    
  - Skype für Business Best Practices Analyzer     
  - Skype für Business Health Analysetool (Excel)    
  - Skype für Business Connectivity Analyzer, 32-Bit oder 64-Bit
    
- Überprüfen Sie [nützliche neue Problembehandlung und Analysetools für Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Vergewissern Sie sich, Sie haben einen Skype für Business-Pool und einen Office Web Apps-Server und ein PowerPoint-Deck mithilfe der Skype für Business-Client freigeben können.
    
- Wenn Besprechungsraum bereits ein Ressourcenpostfach verfügt, aktivieren Sie es für Skype für Unternehmen.
    
- Falls erforderlich, fordern Sie eine DID-Telefonnummer (direkte Durchwahl) für das Konferenzraumsystem an und aktualisieren Sie das Feld für die allgemeine Telefonnummer im Active Directory-Tool.
    
## <a name="network"></a>Netzwerk

- Stellen Sie sicher, dass Sie eine verkabeltes Netzwerk-Verbindung für das Skype Raum System verfügen.
    
- Lesen Sie das Netzwerk für Skype Planungshandbuch für Unternehmen.
    
- Anfordern einer Skype für Business Netzwerk Bewertung aus einer Skype für Geschäftspartner.
    
- Lesen Sie die Leistungsdaten für Business Health Analysetool (Excel) in die Skype erfasst.
    
- Führen Sie das Netzwerkanalysetool aus.
    
- Führen Sie das Vor-Anruf-Diagnosetool aus.
    
## <a name="skype-room-system-security"></a>Skype-Raum System Sicherheit

Skype Raum System ist ein eingebettetes System, das in einer Windows-Bereitstellung vollständig integriert werden kann mithilfe der Skype für Business-Sicherheitsmodell, Verwaltung von Informationsrechten und Verwaltungstools wie SCOM. Folgende Features:
  
- Ein Schreibfilter, um zu verhindern, dass im Benutzermodus auf Datenträger geschrieben wird 
    
- Eine App-Sperre, um zu vermeiden, dass nicht autorisierte Apps ausgeführt werden. Im Benutzermodus sind alle USB-Anschlüsse deaktiviert.
    
  - Keine standard apps oder Viewer befinden sich in der Hardware Skype Raum. Alle Inhalte werden über das HTTP- oder das RDP-Protokoll wiedergegeben.
    
  - Der Anwendungs-PC führt das Betriebssystem „Windows Embedded Standard 7“ aus. Sämtliche Hardware, einschließlich der Geräte, wird von OEM-Partnern bereitgestellt.
    
  - Optionale „Domain Join to Active Directory Domain“-Dienste (AD DS) ermöglichen die lokale Sicherheitskontenverwaltung und -steuerung.
    
- Sie können auch das lokale Administratorkonto mithilfe der Skype für Business-Verwaltungskonsole verwalten.
    
- Skype Raum System wird durch standard Microsoft Update-Prozesse aktualisiert.
    
- Skype Raum System stellt eine Verbindung mit Skype für Unternehmen.
    
  - End-to-End-Verschlüsselung und Autorisierung verwendet für alle Kommunikationsmodi Skype für Unternehmen
    
  - Skype Raum System unterstützt Skype für Sicherheit und Compliance-Standards Business an. Weitere Informationen finden Sie unter [Planen der Sicherheit in Skype für Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Lizenz

Stellen Sie sicher, dass Sie für die Aktivierung von Software einen KMS verwenden. In diesem Fall müssen Sie überprüfen oder die Skype für KMS-Clientschlüssel Business hinzugefügt. Wenn Sie keine KMS verwenden, klicken Sie dann fordern Sie das Volume licensing Schlüssel für die Skype für Business Client MAK an.
  
## <a name="license-keys"></a>Lizenzschlüssel

Skype Raum System wird die Skype für Business desktop Client im Hintergrund ausgeführt. Wenn Skype Raum System Mitglied einer Domäne ist, wird Ihre KMS fest. (und weist dem Volume Licensing KMS-Schlüssel wird es automatisch aktiviert). Die Volumenlizenzierung bietet auch einen MAK, die Sie eingeben, da es Xxxxx-Xxxxx-Xxxxx-Xxxxx anzeigt. (Sie benötigen Internetzugriff zum Aktivieren von MAK, aber nicht KMS). Weitere Informationen finden Sie unter Volume Activation of Office 2013.
  
- Um den MAK-Schlüssel einzugeben, wechseln Sie zu OEM-Einstellungen \> SRS Lizenzierungsprogramm. Klicken Sie auf „Status überprüfen“. Wenn der Status lautet "Produkt ist nicht aktiviert", geben Sie den Schlüssel.
    
- Wenn während der Aktivierung einen Fehler, die besagt auftritt, "' der Software Lizenzierungsdienst gemeldet, dass der Product Key ungültig ist" Überprüfen Sie Folgendes:
    
  - der Schlüssel korrekt eingegeben wurde.
    
  - Sie haben die Skype für Business MAK-Schlüssel und nicht um einen anderen Schlüssel eingegeben.
    
  - das System Zugang zum Internet hat.
    
- Sie können per Telefon aktivieren, müssen aber zunächst versucht haben, mit dem SRS Licensing Tool zu aktivieren. Um per Telefon zu aktivieren, starten Sie eine Testbesprechung (nicht einen Testanruf, denn der wäre zu kurz). Aktivierungs-Assistenten wählen Sie Aktivierung per Telefon, rufen Sie den Microsoft, geben Sie die lange Nummer ein, und geben Sie eine Antwort.
    
## <a name="certificate-authority"></a>Zertifizierungsstelle

Überprüfen Sie, ob die für die Ausgabe des Zertifikats für Office Web Apps Server 2013 verwendete Zertifizierungsstelle über einen HTTP-Pfad verfügt, der in der Eigenschaft „Certificate Revocation List“ enthalten ist.
  
Importieren Sie die Zertifikatdatei (CRT) mit dem Skype Raum System Wenn Skype für Business Server verwenden. Sie kann ganz einfach aus dem CertEnroll-Kontingent des CA-Servers oder aus dem Trusted Root-Ordner jedes an die Domäne angeschlossenen PCs bezogen werden.
  
## <a name="certificates"></a>Zertifikate

Stellen Sie sicher, dass Ihre Zertifizierungsstelle über einen HTTP-Pfad für die Zertifikatssperrliste (Certificate Revocation List; CRL) verfügt. Sollte das nicht der Fall sein, aktualisieren Sie Ihre CA, damit ein HTTP-Pfad vorhanden ist.
  
Installieren von Zertifikaten in der Admin-Einrichtung des Systems Raum Skype unter Systemeinstellungen \> Zertifikat-Manager. Sie benötigen die Stammzertifizierungsstelle (Enterprise Root CA) für Ihr internes Zertifikat.
  
Eine Möglichkeit zum Abrufen der erforderlichen Zertifikate ist die Ermittlung der Zertifizierungsstelle, die Ihre Zertifikate ausgestellt hat. Skype für Business Server auf einem PC in Skype für Unternehmen, klicken Sie auf Einstellungen \> Tools \> Konferenz Einwähleinstellungen. Daraufhin wird eine Webseite, die von der Zertifizierungsstelle, die die interne Zertifikate ausgestellt gesichert. Klicken Sie auf das Sperren-Symbol in der Adressleiste des Browsers, damit ein Sicherheitsbericht angezeigt wird. Klicken Sie auf „Zertifikate anzeigen“ und überprüfen Sie die Eigenschaft „CRL Distribution Point“. Der zweite CN-Parameter sollte der Servername der Zertifizierungsstelle sein. Öffnen Sie Windows Explorer jetzt für die Adresse \\ \< CA-Servernamen \>\CertEnroll. Kopieren Sie die beiden .crl-Dateien und die .crt-Datei auf einen Speicherstick und stecken Sie diesen auf der linken Seite des SmartBoards ein.
  
Die CRT-Datei in das Skype Raum System unter Vertrauenswürdige Raum Zertifizierungsstelle Ordner importiert.
  
Importieren Sie die CRL-Dateien auf dem System Skype Raum, unter dem Ordner Zwischenzertifizierungsstellen. (Sie müssen den Filter für Dateierweiterungen im Zertifikat-Manager zu „.crl“ ändern, damit die Dateien angezeigt werden).
  
Hinweis: Der Office Web Apps 2013-Server kann die gleiche Zertifizierungsstelle als Skype für Business freigeben. Ist dies nicht der Fall, können Sie PowerPoint in einer Besprechung nicht gemeinsam nutzen. Erkundigen Sie sich bei der IT-Abteilung und besorgen Sie sich die .crt- und .crl-Dateien aus dem CA-Netzwerkkontingent CertEnroll, wie oben beschrieben. 
  
Domänenmitgliedschaft kann beachtet werden, da Sie das Skype Raum System, als ein Windows-System behandelt können und es auf Active Directory für einige der Aspekte Zertifikat basieren zu vereinfachen. Es ist jedoch sollten Sie dies manuell verwaltet werden.
  

