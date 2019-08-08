---
title: Skype Room System – Verbesserte Verwaltung und Tools
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lesen Sie dieses Thema und erfahren Sie mehr über Verwaltungstools für Skype Room System.
ms.openlocfilehash: ce33307babac88f6a0e3145988d0ea8519f86110
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234218"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Room System – Verbesserte Verwaltung und Tools
 
Lesen Sie dieses Thema und erfahren Sie mehr über Verwaltungstools für Skype Room System.
  
## <a name="administrative-portal"></a>Verwaltungsportal

Bei lokalen Bereitstellungen von Skype for Business Server können Sie das administrative Portal für das Skype Room-System nutzen, um die Bereitstellung von Skype Room-Systemen in Ihrer Organisation aktiv zu verwalten und zu überwachen.
  
Weitere Informationen finden Sie im folgenden Artikel:
  
- [Bereitstellen des Administrator-Web-Portals für SRS V1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Das Skype Room-System kann über das System Center Operations Manager (SCOM) überwacht werden, indem Sie das [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) herunterladen und auf Ihrem SCOM-Server installieren. Sie können SCOM zum Festlegen von Benachrichtigungen, zum Überwachen der Integrität des Skype-Raumsystems, zur Generierung von Uptime-Berichten und vielem mehr verwenden. Das Skype Room-System verfügt über einen vorinstallierten Überwachungsagenten, der so konfiguriert werden kann, dass er auf den SCOM-Server verweist. Informationen zum Konfigurieren des Überwachungs-Agents auf dem Skype Room-System finden Sie im Installationshandbuch Ihres Skype Room System-Herstellers.
  
## <a name="exchange-checklist"></a>Exchange-Checkliste

- Stellen Sie sicher, dass der AutoErmittlungsdienst eingerichtet ist und dass ein interner DNS-A/CNAME-Eintrag für „autodiscover.domain.com“ verfügbar ist.
    
- Senden Sie ein Pingsignal an den AutoErmittlungsdienst (z. B. „ping autodiscover.contoso.com“).
    
- Testen Sie Ihren AutoErmittlungsdienst mithilfe des Tools Microsoft Connectivity Analyzer. Wählen Sie den ersten Test "Ich kann mich nicht mit Office Outlook anmelden" aus.
    
- Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, erweitern Sie dieses Konto für das Skype-Raum System (Beispielskript unten auf der Seite).
    
## <a name="skype-for-business-checklist"></a>Skype for Business-Checkliste

- Führen Sie die folgenden Tools aus:
    
  - Skype for Business Best Practices Analyzer     
  - Skype for Business-Integritätsanalyse Tool (Excel)    
  - Skype for Business Connectivity Analyzer 32-Bit oder 64-Bit
    
- Überprüfen Sie [hilfreiche neue Problem Behandlungs-und Analysetools für Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Bestätigen Sie, dass Sie über einen Skype for Business-Pool und einen Office Web Apps-Server verfügen und eine PowerPoint-Plattform über den Skype for Business-Client freigeben können.
    
- Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, aktivieren Sie es für Skype for Business.
    
- Falls erforderlich, fordern Sie eine DID-Telefonnummer (direkte Durchwahl) für das Konferenzraumsystem an und aktualisieren Sie das Feld für die allgemeine Telefonnummer im Active Directory-Tool.
    
## <a name="network"></a>Netzwerk

- Stellen Sie sicher, dass Sie über eine kabelgebundene Netzwerkverbindung für das Skype Room-System verfügen.
    
- Lesen Sie das Netzwerk Planungshandbuch für Skype for Business.
    
- Fordern Sie eine Skype for Business-Netzwerkbewertung von einem Skype for Business-Partner an.
    
- Lesen Sie die Leistungsdaten, die im Skype for Business-Integritätsanalyse Tool (Excel) erfasst wurden.
    
- Führen Sie das Netzwerkanalysetool aus.
    
- Führen Sie das Vor-Anruf-Diagnosetool aus.
    
## <a name="skype-room-system-security"></a>Skype Room-System Sicherheit

Skype Room System ist ein eingebettetes System, das vollständig in eine Windows-Bereitstellung mit dem Skype for Business-Sicherheitsmodell, Rechteverwaltung und Verwaltungstools wie SCOM integriert werden kann. Zu den Features gehören:
  
- Ein Schreibfilter, um zu verhindern, dass im Benutzermodus auf Datenträger geschrieben wird 
    
- Eine App-Sperre, um zu vermeiden, dass nicht autorisierte Apps ausgeführt werden. Im Benutzermodus sind alle USB-Anschlüsse deaktiviert.
    
  - Auf der System Hardware von Skype Room befinden sich keine Standard-Apps oder-Viewer. Alle Inhalte werden über das HTTP- oder das RDP-Protokoll wiedergegeben.
    
  - Der Anwendungs-PC führt das Betriebssystem „Windows Embedded Standard 7“ aus. Sämtliche Hardware, einschließlich der Geräte, wird von OEM-Partnern bereitgestellt.
    
  - Optionale „Domain Join to Active Directory Domain“-Dienste (AD DS) ermöglichen die lokale Sicherheitskontenverwaltung und -steuerung.
    
- Sie können das lokale Administratorkonto auch über das Skype for Business Admin Center verwalten.
    
- Das Skype Room-System wird über standardmäßige Microsoft Update-Prozesse aktualisiert.
    
- Skype Room System stellt eine Verbindung mit Skype for Business her.
    
  - Skype for Business verwendet End-to-End-Verschlüsselung und-Autorisierung für alle Kommunikationsmodi
    
  - Skype Room System unterstützt Skype for Business-Sicherheits-und Compliance-Standards. Weitere Informationen finden Sie unter [Planen der Sicherheit in Skype for Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Lizenz

Stellen Sie sicher, dass Sie für die Aktivierung von Software einen KMS verwenden. In diesem Fall müssen Sie möglicherweise den Skype for Business-Client-KMS-Schlüssel überprüfen oder hinzufügen. Wenn Sie KMS nicht verwenden, fordern Sie den Volumen Lizenzierungsschlüssel für den Skype for Business-Client MAK an.
  
## <a name="license-keys"></a>Lizenzschlüssel

Skype Room System führt den Skype for Business-Desktop-Client im Hintergrund aus. Wenn Skype Room System ein Domänenmitglied ist, wird es ihren KMS entdecken. (und wenn Sie über den KMS-Schlüssel für die Volumenlizenzierung verfügt, wird Sie automatisch aktiviert). Die Volumenlizenzierung bietet auch einen MAK, den Sie beim Anzeigen von XXXXX-XXXXX-XXXXX-XXXXX eingeben. (Sie benötigen Internet Zugriff, um die Verwendung von MAK, aber nicht KMS) zu aktivieren. Weitere Informationen finden Sie unter Volumenaktivierung von Office 2013.
  
- Zum Eingeben des MAK-Schlüssels wechseln Sie zu OEM \> -Einstellungen SRS-Lizenzierungs Tool. Klicken Sie auf „Status überprüfen“. Wenn der Status "Produkt ist nicht aktiviert" lautet, geben Sie den Schlüssel ein.
    
- Wenn während der Aktivierung eine Fehlermeldung angezeigt wird, die besagt, dass der Software Lizenzierungsdienst gemeldet hat, dass der Product Key ungültig ist, überprüfen Sie Folgendes:
    
  - der Schlüssel korrekt eingegeben wurde.
    
  - Sie haben den Skype for Business-MAK-Schlüssel und nicht einen anderen Schlüssel eingegeben.
    
  - das System Zugang zum Internet hat.
    
- Sie können per Telefon aktivieren, müssen aber zunächst versucht haben, mit dem SRS Licensing Tool zu aktivieren. Um per Telefon zu aktivieren, starten Sie eine Testbesprechung (nicht einen Testanruf, denn der wäre zu kurz). Wählen Sie im Office-Aktivierungs-Assistententelefon Aktivierung aus, rufen Sie Microsoft an, geben Sie die lange Nummer ein, und geben Sie eine Antwort ein.
    
## <a name="certificate-authority"></a>Zertifizierungsstelle

Überprüfen Sie, ob die für die Ausgabe des Zertifikats für Office Web Apps Server 2013 verwendete Zertifizierungsstelle über einen HTTP-Pfad verfügt, der in der Eigenschaft „Certificate Revocation List“ enthalten ist.
  
Importieren Sie die Zertifikatsdatei (. CRT) in das Skype Room-System, wenn Sie Skype for Business Server verwenden. Sie kann ganz einfach aus dem CertEnroll-Kontingent des CA-Servers oder aus dem Trusted Root-Ordner jedes an die Domäne angeschlossenen PCs bezogen werden.
  
## <a name="certificates"></a>Zertifikate

Stellen Sie sicher, dass Ihre Zertifizierungsstelle über einen HTTP-Pfad für die Zertifikatssperrliste (Certificate Revocation List; CRL) verfügt. Sollte das nicht der Fall sein, aktualisieren Sie Ihre CA, damit ein HTTP-Pfad vorhanden ist.
  
Installieren Sie Zertifikate in der Administrator Einrichtung des Skype Room-Systems unter System \> Einstellungen Zertifikat-Manager. Sie benötigen die Stammzertifizierungsstelle (Enterprise Root CA) für Ihr internes Zertifikat.
  
Eine Möglichkeit zum Abrufen der erforderlichen Zertifikate ist die Ermittlung der Zertifizierungsstelle, die Ihre Zertifikate ausgestellt hat. Klicken Sie bei Skype for Business Server auf einem PC in Skype for Business auf Einstellungen \> Tools \> Einwahlkonferenzeinstellungen. Dadurch wird eine Webseite geöffnet, die von der Zertifizierungsstelle, die die internen Zertifikate ausgestellt hat, gesichert wurde. Klicken Sie auf das Sperren-Symbol in der Adressleiste des Browsers, damit ein Sicherheitsbericht angezeigt wird. Klicken Sie auf „Zertifikate anzeigen“ und überprüfen Sie die Eigenschaft „CRL Distribution Point“. Der zweite CN-Parameter sollte der Servername der Zertifizierungsstelle sein. Öffnen Sie nun den Windows-Explorer \\ \< für diesen Adress \>-ca-Server Namen \CertEnroll. Kopieren Sie die beiden .crl-Dateien und die .crt-Datei auf einen Speicherstick und stecken Sie diesen auf der linken Seite des SmartBoards ein.
  
Importieren Sie die CRT-Datei in das Skype Room-System unter Trusted Room Certification Authority-Ordner.
  
Importieren Sie die CRL-Dateien im Skype Room-System unter dem Ordner Zwischenzertifizierungsstellen. (Sie müssen den Filter für Dateierweiterungen im Zertifikat-Manager zu „.crl“ ändern, damit die Dateien angezeigt werden).
  
Hinweis: der Office Web Apps 2013-Server hat möglicherweise dieselbe Zertifizierungsstelle wie Skype for Business. Ist dies nicht der Fall, können Sie PowerPoint in einer Besprechung nicht gemeinsam nutzen. Erkundigen Sie sich bei der IT-Abteilung und besorgen Sie sich die .crt- und .crl-Dateien aus dem CA-Netzwerkkontingent CertEnroll, wie oben beschrieben. 
  
Die Domänenmitgliedschaft kann einige Dinge vereinfachen, da Sie das Skype Room-System als Windows-System behandeln können und es sich auf Active Directory für einige der Zertifikat Aspekte verlassen kann. Es empfiehlt sich jedoch, diese manuell zu verwalten.
  

