---
title: Verwaltbarkeit und Tools für Skype Room System
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
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805795"
---
# <a name="skype-room-system-manageability-and-tools"></a>Verwaltbarkeit und Tools für Skype Room System
 
Lesen Sie dieses Thema, um mehr über Verwaltungstools für Skype Room System zu erfahren.
  
## <a name="administrative-portal"></a>Verwaltungsportal

Für lokale Skype for Business Server-Bereitstellungen können Sie das Verwaltungsportal von Skype Room System verwenden, um Skype Room System-Bereitstellungen in Ihrer Organisation aktiv zu verwalten und zu überwachen.
  
Weitere Informationen finden Sie im folgenden Artikel:
  
- [Bereitstellen des Webportals für die Verwaltung von SRS v1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Prüfliste für Exchange

- Vergewissern Sie sich, dass die AutoErmittlung eingerichtet ist und ein interner DNS-A/CNAME-EINTRAG für die autodiscover.domain.com.
    
- Ping autoermittlung (z. B. Ping-Autodiscover.contoso.com).
    
- Testen Sie Ihren AutoErmittlungsdienst mit dem Microsoft Connectivity Analyzer-Tool. Wählen Sie den ersten Test aus: "Ich kann mich nicht bei Office Outlook anmelden".
    
- Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, erweitern Sie dieses Konto für Skype Room System (Beispielskript am unteren Rand der Seite).
    
## <a name="skype-for-business-checklist"></a>Skype for Business Checkliste

- Führen Sie die folgenden Tools aus:
    
  - Skype for Business Best Practices Analyzer     
  - Skype for Business Health Analysis Tool (Excel)    
  - Skype for Business Connectivity Analyzer 32-Bit oder 64-Bit
    
- Lesen [Sie nützliche neue Tools zur Problembehandlung und Analyse für Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/) Vergewissern Sie sich, dass Sie über einen Skype for Business-Pool und einen Office Web Apps-Server verfügen und ein PowerPoint-Deck über den Skype for Business-Client freigeben können.
    
- Wenn der Besprechungsraum bereits über ein Ressourcenpostfach verfügt, aktivieren Sie es für Skype for Business.
    
- Fordern Sie bei Bedarf eine DID (Telefonnummer) für das Besprechungsraumsystem an, und aktualisieren Sie das Feld "Allgemeines Telefon" im Active Directory-Tool.
    
## <a name="network"></a>Netzwerk

- Stellen Sie sicher, dass Sie über eine kabelgebundene Netzwerkverbindung für das Skype Room System verfügen.
    
- Lesen Sie das Netzwerkplanungshandbuch für Skype for Business.
    
- Fordern Sie eine Skype for Business-Netzwerkbewertung von einem Skype for Business-Partner an.
    
- Lesen Sie die im Skype for Business Health Analysis Tool (Excel) erfassten Leistungsdaten durch.
    
- Führen Sie das Netzwerkanalysetool aus.
    
- Führen Sie das Diagnosetool vor dem Aufruf aus.
    
## <a name="skype-room-system-security"></a>Skype Room System Security

Skype Room System ist ein eingebettetes System, das vollständig in eine Windows-Bereitstellung integriert werden kann, indem das Skype for Business-Sicherheitsmodell, die Rechteverwaltung und Verwaltungstools wie SCOM verwendet werden. Zu den Features gehören:
  
- Ein Schreibfilter zum Verhindern von Schreibvorgängen im Benutzermodus 
    
- App-Schließfach, um zu verhindern, dass nicht autorisierte Apps ausgeführt werden. Alle USB-Ports sind im Benutzermodus deaktiviert.
    
  - Auf der Skype Room System-Hardware befinden sich keine Standard-Apps oder -Viewer. Alle Inhalte werden über HTTP- oder RDP-Protokolle gerendert.
    
  - Auf dem Appliance-PC wird das Betriebssystem Windows Embedded Standard 7 ausgeführt. Alle Hardware, einschließlich Geräte, wird von OEM-Partnern bereitgestellt.
    
  - Optionaler Domänen beitritt zu Active Directory Domain Services (AD DS), wodurch die Verwaltung und Kontrolle lokaler Sicherheitskontos aktiviert wird.
    
- Sie können das lokale Administratorkonto auch über das Skype for Business Admin Center verwalten.
    
- Skype Room System wird über standardmäßige Microsoft Update-Prozesse aktualisiert.
    
- Skype Room System stellt eine Verbindung mit Skype for Business zur Verfügung.
    
  - Skype for Business verwendet End-to-End-Verschlüsselung und Autorisierung für alle Kommunikationsmodi
    
  - Skype Room System unterstützt Skype for Business-Sicherheits- und Compliancestandards. Weitere [Informationen finden Sie unter "Planen der Sicherheit in Skype for Business Server".](../../plan-your-deployment/security/security.md)
    
## <a name="license"></a>Lizenz

Stellen Sie sicher, dass Sie einen KMS zum Aktivieren von Software verwenden. Wenn ja, müssen Sie möglicherweise den Skype for Business-Client-KMS-Schlüssel überprüfen oder hinzufügen. Wenn Sie kmS nicht verwenden, fordern Sie den Volumenlizenzierungsschlüssel für den Skype for Business-Client-MAK an.
  
## <a name="license-keys"></a>Lizenzschlüssel

Skype Room System führt den Skype for Business-Desktopclient im Hintergrund aus. Wenn Skype Room System ein Domänenmitglied ist, wird Ihr KMS ermittelt. (und wenn er über den Volumenlizenzierungs-KMS-Schlüssel verfügt, wird er automatisch aktiviert). Die Volumenlizenzierung bietet auch einen MAK, den Sie bei der Anzeige von xxxxx-xxxxx-xxxxx-xxxxx eingeben. (Sie benötigen Internetzugriff, um mit MAK, aber nicht mit KMS aktiviert zu werden.) Weitere Informationen finden Sie unter Volumenaktivierung von Office 2013.
  
- Wenn Sie den MAK-Schlüssel eingeben möchten, wechseln Sie zum OEM Settings \> SRS Licensing Tool. Klicken Sie auf Status überprüfen. Wenn der Status "Produkt ist nicht aktiviert" angezeigt wird, geben Sie den Schlüssel ein.
    
- Wenn während der Aktivierung eine Fehlermeldung mit der Fehlermeldung "Der Softwarelizenzierungsdienst hat gemeldet, dass der Product Key ungültig ist" angezeigt wird, stellen Sie sicher, dass:
    
  - Der Schlüssel wurde richtig eingegeben.
    
  - Sie haben den Skype for Business-MAK-Schlüssel und keinen weiteren Schlüssel eingegeben.
    
  - Das System hat Internetzugriff.
    
- Sie können die Aktivierung per Telefon durchführen, müssen jedoch zuerst versucht haben, die Aktivierung mit dem SRS-Lizenzierungstool zu versuchen. Um telefonisch zu aktivieren, starten Sie eine Testsitzung (kein Testanruf, da dieser zu kurz ist). Wählen Sie im Assistenten für die Office-Aktivierung die Telefonaktivierung aus, rufen Sie Microsoft an, geben Sie die lange Nummer ein, und geben Sie eine Antwort ein.
    
## <a name="certificate-authority"></a>Zertifizierungsstelle

Vergewissern Sie sich, dass die zum Aus ausgestellte Office Web Apps Server 2013-Zertifikat verwendete Zertifizierungsstelle über einen in der Eigenschaft "Zertifikatsperrliste" enthaltenen HTTP-Pfad verfügt.
  
Importieren Sie die Zertifikatsdatei (CRT) in das Skype Room System, wenn Sie Skype for Business Server verwenden. Sie kann ganz einfach aus der #A0 des Zertifizierungsstellenservers oder im vertrauenswürdigen Stammordner eines beliebigen in die Domäne angeschlossenen PCs erworben werden.
  
## <a name="certificates"></a>Zertifikate

Stellen Sie sicher, dass Ihre Zertifizierungsstelle über einen Http-Pfad für die Zertifikatsperrliste verfügt. Falls nicht, aktualisieren Sie Ihre Zertifizierungsstelle so, dass sie eine enthält.
  
Installieren Sie Zertifikate in der Administratoreinrichtung von Skype Room System unter \> "Systemeinstellungen-Zertifikat-Manager". Sie benötigen die Unternehmensstammzertifizierungsstelle für Ihr internes Zertifikat.
  
Eine Möglichkeit, die benötigten Zertifikate zu erhalten, besteht in der Ermitteln der Zertifizierungsstelle, von der Die Zertifikate ausgestellt wurden. Klicken Sie für Skype for Business Server auf einem PC in Skype for Business auf \> einstellungentools \> für Einwahlkonferenzeinstellungen. Dadurch wird eine Webseite geöffnet, die durch die Zertifizierungsstelle gesichert ist, von der die internen Zertifikate ausgestellt wurden. Klicken Sie auf das Symbol "Sperren" in der Adressleiste des Browsers, um einen Sicherheitsbericht anzuzeigen. Klicken Sie auf "Zertifikate anzeigen", und überprüfen Sie die Eigenschaft "CRL Distribution Point". Der zweite #A0 sollte der Servername der Zertifizierungsstelle sein. Öffnen Sie jetzt Windows Explorer für diese Adresse \\ \< CA Server Name \> \CertEnroll. Kopieren Sie die beiden CRL- und die CRT-Datei auf ein Flashlaufwerk, und legen Sie sie auf der linken Seite des SMART Board ab.
  
Importieren Sie die .crt-Datei in das Skype Room System unter dem Ordner "Vertrauenswürdige Raumzertifizierungsstelle".
  
Importieren Sie die .crl-Dateien im Skype Room System unter dem Ordner "Zwischenzertifikate". (Sie müssen den Dateierweiterungsfilter im Zertifikat-Manager in ".crl" ändern, um die Dateien zu sehen).
  
Hinweis: Der Office Web Apps 2013-Server kann dieselbe Zertifizierungsstelle wie Skype for Business verwenden. Andern falls nicht, können Sie PowerPoint in einer Besprechung nicht freigeben. Überprüfen Sie die IT, und rufen Sie die CRT- und #A0 aus der #A1 CertEnroll ab, wie oben erläutert. 
  
Die Domänenmitgliedschaft kann einige Dinge vereinfachen, da Sie das Skype Room System als Ein-Windows-System behandeln können und sich für einige der Zertifikataspekte auf Active Directory verlassen können. Es ist jedoch am besten, dies manuell zu verwalten.
  

