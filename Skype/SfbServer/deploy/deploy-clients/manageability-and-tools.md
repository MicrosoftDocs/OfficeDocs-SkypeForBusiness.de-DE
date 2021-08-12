---
title: Skype Raumsystemverwaltung und Tools
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Lesen Sie dieses Thema, um mehr über Verwaltungstools für Skype Room System zu erfahren.
ms.openlocfilehash: cdf7430ecc155526cc560832f58f00a6119ce8ab8e777bbb592cba205c0407f9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310074"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Raumsystemverwaltung und Tools
 
Lesen Sie dieses Thema, um mehr über Verwaltungstools für Skype Room System zu erfahren.
  
## <a name="administrative-portal"></a>Verwaltungsportal

Für Skype for Business Server lokalen Bereitstellungen können Sie das Skype Raumsystem-Verwaltungsportal verwenden, um Skype Raumsystembereitstellungen innerhalb Ihrer Organisation aktiv zu verwalten und zu überwachen.
  
Weitere Informationen finden Sie im folgenden Artikel:
  
- [Bereitstellen des Webportals für die Verwaltung von SRS v1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange Checkliste

- Vergewissern Sie sich, dass die AutoErmittlung eingerichtet ist und ein interner DNS A/CNAME RECORD für autodiscover.domain.com verfügbar ist.
    
- Ping-AutoErmittlung (z. B. Ping Autodiscover.contoso.com).
    
- Testen Sie den AutoErmittlungsdienst mit dem Microsoft Connectivity Analyzer-Tool. Wählen Sie den ersten Test aus: "Ich kann mich nicht mit Office Outlook anmelden."
    
- Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, erweitern Sie dieses Konto für die Skype Raumsystem (Beispielskript unten auf der Seite).
    
## <a name="skype-for-business-checklist"></a>Skype for Business Checkliste

- Führen Sie die folgenden Tools aus:
    
  - Skype for Business Best Practices Analyzer     
  - Skype for Business Health Analysis Tool (Excel)    
  - Skype for Business Connectivity Analyzer 32-Bit oder 64-Bit
    
- Lesen Sie [die nützlichen neuen Problembehandlungs- und Analysetools für Office 365.](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365) Vergewissern Sie sich, dass Sie über einen Skype for Business Pool und einen Office Web Apps-Server verfügen und ein PowerPoint Deck mithilfe des Skype for Business-Clients freigeben können.
    
- Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, aktivieren Sie es für Skype for Business.
    
- Fordern Sie bei Bedarf eine DID (Telefonnummer) für das Besprechungsraum System an, und aktualisieren Sie das Feld "Telefon allgemein" im Active Directory-Tool.
    
## <a name="network"></a>Netzwerk

- Stellen Sie sicher, dass Sie über eine kabelgebundene Netzwerkverbindung für das Skype Room System verfügen.
    
- Lesen Sie das Netzwerkplanungshandbuch für Skype for Business.
    
- Fordern Sie eine Skype for Business Netzwerkbewertung von einem Skype for Business Partner an.
    
- Lesen Sie die im Skype for Business Health Analysis Tool (Excel) erfassten Leistungsdaten.
    
- Führen Sie das Netzwerkanalysetool aus.
    
- Führen Sie das Diagnosetool vor dem Anruf aus.
    
## <a name="skype-room-system-security"></a>Skype Raumsystemsicherheit

Skype Room System ist ein eingebettetes System, das vollständig in eine Windows Bereitstellung mithilfe des Skype for Business-Sicherheitsmodells, der Rechteverwaltung und der Verwaltungstools wie SCOM integriert werden kann. Zu den Features gehören:
  
- Ein Schreibfilter zum Verhindern von Datenträgerschreibvorgängen im Benutzermodus 
    
- App-Schließfach, um zu verhindern, dass nicht autorisierte Apps ausgeführt werden. Alle USB-Anschlüsse sind im Benutzermodus deaktiviert.
    
  - Auf der Skype Room System-Hardware befinden sich keine Standard-Apps oder -Viewer. Alle Inhalte werden über HTTP- oder RDP-Protokolle gerendert.
    
  - Auf dem Appliance-PC wird das Windows Embedded Standard 7-Betriebssystem ausgeführt. Die gesamte Hardware, einschließlich Der Geräte, wird von OEM-Partnern bereitgestellt.
    
  - Optionaler Domänenbeitritt zu Active Directory Domain Services (AD DS), wodurch lokale Sicherheitskontoverwaltung und -steuerung aktiviert wird.
    
- Sie können das lokale Administratorkonto auch über das Skype for Business Admin Center verwalten.
    
- Skype Room System wird durch standardmäßige Microsoft Update-Prozesse aktualisiert.
    
- Skype Das Raumsystem stellt eine Verbindung mit Skype for Business her.
    
  - Skype for Business verwendet End-to-End-Verschlüsselung und Autorisierung für alle Kommunikationsmodi.
    
  - Skype Room System unterstützt Skype for Business Sicherheits- und Compliancestandards. Weitere Informationen finden Sie [unter Plan for security in Skype For Business Server.](../../plan-your-deployment/security/security.md)
    
## <a name="license"></a>Lizenz

Stellen Sie sicher, dass Sie eine KMS zum Aktivieren von Software verwenden. Wenn ja, müssen Sie möglicherweise den Skype for Business Client-KMS-Schlüssel überprüfen oder hinzufügen. Wenn Sie KMS nicht verwenden, fordern Sie den Volumenlizenzschlüssel für den Skype for Business Client-MAK an.
  
## <a name="license-keys"></a>Lizenzschlüssel

Skype Room System führt den Skype for Business-Desktopclient im Hintergrund aus. Wenn Skype Room System Domänenmitglied ist, wird Ihr KMS ermittelt. (und wenn er über die Volumenlizenzierung KMS Schlüssel verfügt, wird er automatisch aktiviert).) Die Volumenlizenzierung bietet auch einen MAK, den Sie eingeben, wenn xxxxx-xxxxx-xxxxx-xxxxx-xxxxx angezeigt wird. (Sie benötigen Internetzugriff, um mithilfe von MAK zu aktivieren, aber nicht KMS). Weitere Informationen finden Sie unter Volumenaktivierung von Office 2013.
  
- Um den MAK-Schlüssel einzugeben, wechseln Sie zum OEM Einstellungen \> SRS-Lizenzierungstool. Klicken Sie auf Status überprüfen. Wenn der Status "Produkt ist nicht aktiviert" angezeigt wird, geben Sie den Schlüssel ein.
    
- Wenn während der Aktivierung ein Fehler angezeigt wird, der besagt: "Der Softwarelizenzierungsdienst hat gemeldet, dass der Product Key ungültig ist", überprüfen Sie Folgendes:
    
  - Der Schlüssel wurde richtig eingegeben.
    
  - Sie haben die Skype for Business MAK-Taste und keine andere Taste eingegeben.
    
  - Das System hat Internetzugriff.
    
- Sie können die Aktivierung per Telefon ausführen, müssen aber zuerst versucht haben, die Aktivierung mit dem SRS-Lizenzierungstool zu starten. Um per Telefon zu aktivieren, starten Sie eine Testbesprechung (kein Testanruf, da dies zu kurz ist). Wählen Sie im Office Aktivierungs-Assistenten die Telefonaktivierung aus, rufen Sie Microsoft auf, geben Sie die lange Nummer ein, und geben Sie eine Antwort ein.
    
## <a name="certificate-authority"></a>Zertifizierungsstelle

Vergewissern Sie sich, dass die Zum Ausstellen des Office Web Apps Server 2013-Zertifikats verwendete Zertifizierungsstelle über einen HTTP-Pfad verfügt, der in der Eigenschaft "Zertifikatsperrliste" enthalten ist.
  
Importieren Sie die Zertifikatdatei (CRT) in das Skype Raumsystem, wenn Sie Skype for Business Server verwenden. Sie kann ganz einfach von der CertEnroll-Freigabe des Zertifizierungsstellenservers oder im Ordner "Vertrauenswürdiger Stamm" eines beliebigen in die Domäne eingebundenen PCs abgerufen werden.
  
## <a name="certificates"></a>Zertifikate

Stellen Sie sicher, dass Ihre Zertifizierungsstelle über einen HTTP-Pfad für die Zertifikatsperrliste verfügt. Falls nicht, aktualisieren Sie Ihre Zertifizierungsstelle so, dass sie eine einschließt.
  
Installieren Sie Zertifikate im Administratorsetup des Skype Room System unter System Einstellungen \> Certificate Manager. Sie benötigen die Enterprise Stammzertifizierungsstelle für Ihr internes Zertifikat.
  
Eine Möglichkeit zum Abrufen der benötigten Zertifikate besteht darin, die Zertifizierungsstelle zu ermitteln, die Ihre Zertifikate ausgestellt hat. For Skype for Business Server, on a PC in Skype for Business, click Einstellungen \> Tools \> Dial-in Conference Einstellungen. Dadurch wird eine Webseite geöffnet, die durch die Zertifizierungsstelle gesichert ist, die die internen Zertifikate ausgestellt hat. Klicken Sie auf das Symbol "Sperren" in der Adressleiste des Browsers, um einen Sicherheitsbericht anzuzeigen. Klicken Sie auf "Zertifikate anzeigen", und überprüfen Sie die CRL-Verteilungspunkteigenschaft. Der zweite CN-Parameter sollte der Servername der Zertifizierungsstelle sein. Öffnen Sie nun Windows Explorer für diese Adresse \\ \< CA Server Name \> \CertEnroll. Kopieren Sie die beiden CRL-Dateien und die CRT-Datei auf ein Flashlaufwerk, und platzieren Sie sie auf der linken Seite des SMART Board.
  
Importieren Sie die CRT-Datei in das Skype Raumsystem im Ordner "Vertrauenswürdige Raumzertifizierungsstelle".
  
Importieren Sie die CRL-Dateien im Skype Raumsystem im Ordner "Zwischenzertifizierungsstellen". (Sie müssen den Dateierweiterungsfilter im Zertifikat-Manager in CRL ändern, um die Dateien anzuzeigen).
  
Hinweis: Der Office Web Apps 2013-Server kann dieselbe Zertifizierungsstelle wie Skype for Business verwenden. Wenn dies nicht der Fall ist, können Sie PowerPoint in einer Besprechung nicht freigeben. Wenden Sie sich an die IT-Abteilung, und rufen Sie die CRT- und CRL-Dateien aus der Zertifizierungsstellen-Netzwerkfreigabe "CertEnroll" ab, wie oben erläutert. 
  
Die Domänenmitgliedschaft kann einige Dinge vereinfachen, da Sie das Skype Raumsystem als Windows System behandeln können und sich bei einigen Zertifikataspekten auf Active Directory verlassen können. Es empfiehlt sich jedoch, dies manuell zu verwalten.
