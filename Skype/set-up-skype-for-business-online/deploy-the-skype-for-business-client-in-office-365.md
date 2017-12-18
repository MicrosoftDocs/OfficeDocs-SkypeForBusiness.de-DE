---
title: "Den Skype for Business-Client in Office 365 bereitstellen"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/21/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- httpsfix
- LeftNav_IT_O365
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
description: "Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. "
---

# Den Skype for Business-Client in Office 365 bereitstellen

> [!IMPORTANT]
> Dieser Artikel wurde maschinell übersetzt. Bitte beachten Sie den [Haftungsausschluss](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#MT_Footer).  
  
In diesem Artikel wird beschrieben, wie Sie als **[Zuweisen von Administratorrollen in Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** die Skype for Business-App für die Personen Ihrer Organisation bereitstellen können.
  
Vergewissern Sie sich vor Sie Ihren Benutzern Skype for Business bereitstellen, Sie haben die Schritte 1-3 im Artikel [Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)fertig. Auf diese Weise Skype for Business wird eingerichtet werden mit Ihrer Domäne, jeder kann ihre Lizenzen sind und Sie werden konfiguriert haben IM und [Konfigurieren der Anwesenheit in Skype for Business Online](configure-presence-in-skype-for-business-online.md) für Ihre Organisation.
  
> [!NOTE]
> Für Benutzer, die Skype for Business app zu installieren müssen sie lokale Administratoren auf ihrem Computer oder Gerät sein. Oder sie müssen Teil einer lokalen Gruppe werden, die apps auf ihrem Computer oder Geräte installieren können. Wenn Ihre Benutzer Software auf ihren Geräten installieren darf nicht zur Verfügung, müssen Sie die app Skype for Business für diese Benutzer installieren. 
  
## Für die meisten kleinen und mittleren Unternehmen

 **Schrittweise Installationsanleitung**: Wenn Sie ein kleines oder mittleres Unternehmen haben, empfehlen wir, die Benutzer einfach zu bitten, die Skype for Business-App auf ihrem PC zu installieren. Verweisen Sie sie auf diese Anleitung:[Installieren von Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Wenn sie einen Mac verwenden, verweisen Sie sie auf [Einrichten von Skype for Business (Lync) für Mac 2011 für Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). Die Skype for Business-App wird getrennt von den anderen Office-Apps installiert.
  
 **Office 365 ProPlus-Kunden**: Wenn Ihr Unternehmen einen Office 365-Plan verwendet, in dem Office 365 ProPlus enthalten ist (zum Beispiel den E3-Plan), wird die Skype for Business-App zusammen mit Word, Excel, PowerPoint usw. installiert. Dies bedeutet außerdem, dass die Benutzer Skype for Business nur durch die Deinstallation des gesamten Office-Pakets deinstallieren können.
  
### Wählen, ob Skype for Business für Ihre Benutzer zur Verfügung stehen soll

Als [Zuweisen von Administratorrollen in Office 365](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) können Sie auswählen, ob Ihre Benutzer die app Skype for Business zur Verfügung stellen.
  
- **So steuern Sie, ob alle Benutzer in Ihrem Unternehmen werden die Software**: Melden Sie sich in auf die Office 365 Admin Center, wechseln Sie zu **Meine Software installieren**, und wählen Sie die Software für Benutzer verfügbar sein sollen.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Steuern, ob bestimmte Personen in Ihrem Unternehmen Aufrufen die Software**: Melden Sie sich bei der Office 365 Admin Center, wechseln Sie zu **Benutzer** > **aktive Benutzer**, wählen Sie die Person, die Sie Zugriff auf die Software gewähren möchten, und klicken Sie dann auf **Bearbeiten** neben ** Lizenzen für Product**, und aktivieren Sie die Lizenz, aktivieren oder deaktivieren.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Wenn Sie sehen, welche Pläne an Personen in Ihrer Organisation zugewiesen werden müssen, melden Sie sich bei der neuen Office 365 Admin Center > **Benutzer** > **aktive Benutzer**. Wählen Sie die Person aus der Liste aus, und klicken Sie dann unter **Produktlizenzen** aussehen. Wenn Sie die klassische Office 365 Admin Center verwenden, suchen Sie unter **Lizenz zugewiesen**. 
  
### Manuelle Bereitstellung von Skype for Business für Ihre Benutzer
<a name="bkmk_manual_1"> </a>

Wenn die Benutzer die Skype for Business-App nicht über das Internet, sondern aus einem Speicherort in Ihrem Netzwerk installieren sollen, können Sie die Setupdateien herunterladen. Navigieren Sie dazu im zum Abschnitt Office 365 Admin CenterManually deploy user software (Benutzersoftware manuell bereitstellen). Dann können Sie **Installieren** auswählen und die Datei „setup.exe" unter einer Netzwerkadresse speichern.
  
Eine weitere Möglichkeit ist, das grundlegende Skype for Business-app für Ihre Benutzer herunterzuladen. Sie können [Microsoft Skype für grundlegende Business (32 oder 64-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=49440)herunterladen.
  
Sowohl für die vollständige als auch für die Basic-Version der Skype for Business-App müssen Sie nach dem Herunterladen der Setupdateien den Netzwerkpfad manuell an die Benutzer senden (zum Beispiel per E-Mail). Dann können sie das Setupprogramm ausführen, um die App auf ihrem Computer zu installieren.
  
Sie können diese Downloads auch zum Bereitstellen der Skype for Business-App für Ihre Benutzer mithilfe Ihrer vorhandenen Softwarebereitstellungstools und -prozesse verwenden.
  
## Für größere und sehr große Unternehmen

> [!NOTE]
>  Dieser Abschnitt betrifft nur die in Office 365-Plänen verfügbare Skype for Business-App. Wenn Ihre Organisation eine Volumenlizenzversion der Skype for Business-App verwendet, die auf Windows Installer (MSI) basiert, lesen Sie[Anpassen von Windows-Client-Installation in Skype für Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
In vielen Großunternehmen haben Benutzer nicht die Berechtigung zum Installieren von Software auf ihren Computern. Stattdessen wird die Software von den IT-Abteilungen auf den Computern bereitgestellt. IT-Abteilungen möchten unter Umständen auch die in der Organisation verwendete Internet- oder Netzwerkbandbreite steuern und Software daher von einem Speicherort im lokalen Netzwerk aus statt über das Internet oder das Unternehmensnetzwerk installieren.
  
Mit Office 365 haben Sie mehrere Optionen für die Bereitstellung von der app Skype for Business, wenn Sie möchten, können Sie steuern, von dem es installiert ist. Einige dieser Optionen umfassen Folgendes:
  
- Laden Sie die Skype for Business-App vom Office 365 Admin Center wie in [Manuelle Bereitstellung von Skype for Business für Ihre Benutzer](8c563b81-22c9-4024-9efe-9fe28c7bbc96.md#bkmk_manual) in Ihr lokales Netzwerk herunter.
    
- Verwenden Sie das **[Office-Bereitstellungstool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** zum Herunterladen von Office 365 ProPlus oder der Skype for Business-App in ihr lokales Netzwerk. Verwenden Sie das Office-Bereitstellungstool anschließend zum Bereitstellen der App für Ihre Benutzer. Mit dem Office-Bereitstellungstool können Sie unterschiedliche Aspekte der Bereitstellung festlegen, wie etwa Sprachen oder Version (32 Bit oder 64 Bit).
    
- Verwenden Sie Ihre vorhandenen Software-Bereitstellungstools und -Prozesse, wie z. B. System Center Configuration Manager, zum Bereitstellen von Office 365 ProPlus oder der Skype for Business-App für Ihre Benutzer. Sie können Ihre vorhandenen Tools und Prozesse mit dem [Office-Bereitstellungstool](https://go.microsoft.com/fwlink/p/?LinkID=626065) oder der Software verwenden, die Sie aus dem Office 365 Admin Center heruntergeladen haben.
    
### Zusätzliche Informationen zur Verwendung des Office-Bereitstellungstools

Details zum Herunterladen des Office-Bereitstellungstools und zusätzliche Informationen zur Installation der Skype for Business-App sowie weiterer Office 365-Client-Apps finden Sie unter [Verwalten von Benutzersoftware in Office 365](https://support.office.com/article/365-c13051e6-f75c-4737-bc0d-7685dcedf360.aspx).
  
Verwenden des Office-Bereitstellungstools für eine app bereitgestellt hier eine Übersicht über die Schritte:
  
1. **[Laden Sie die aktuellste Version des Office-Bereitstellungstools](https://go.microsoft.com/fwlink/p/?LinkID=626065)** aus dem Microsoft Download Center herunter.
    
2. Erstellen Sie die configuration.xml-Datei zur Verwendung mit dem Office-Bereitstellungstool mit den von Ihnen gewünschten Client-App-Einstellungen, wie zum Beispiel der Version (32-Bit oder 64-Bit), der Installationssprache usw.
    
3. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Setupdateien vom Office Content Delivery Network (CDN) in Ihr lokales oder internes Netzwerk herunterzuladen.
    
4. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Office-Client-Apps einschließlich der Skype for Business-App zu installieren.
    
Details zur Verwendung des Office-Bereitstellungstools und zur configuration.xml-Datei finden Sie hier:
  
- [Office-Bereitstellungstool - Überblick](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml - Einstellungen](https://technet.microsoft.com/library/jj219426.aspx)
    
### Weitere Informationen zur Verwendung von System Center Configuration Manager

Sie können Ihre vorhandenen Software-Bereitstellungstools und -Prozesse, wie etwa System Center Configuration Manager, zur Bereitstellung der Skype for Business-App verwenden. Sie können diese Tools und Prozesse mit der Software, die Sie vom Office 365 Admin Center herunterladen, oder mit dem Office-Bereitstellungstool verwenden.
  
Weitere Informationen zur Bereitstellung von Software mit Configuration Manager finden Sie in den folgenden Artikeln:
  
- [So erstellen Sie Anwendungen im Configuration Manager](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [So stellen Sie Anwendungen im Configuration Manager bereit](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Wenn Sie die Skype for Business-App als Teil der Bereitstellung von Office 365 ProPlus verwenden, lesen Sie [Bereitstellen von Office 365 ProPlus mithilfe von System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## Planen von Updates der Skype for Business-App

Im Rahmen der Bereitstellung der Skype for Business-App müssen Sie auch festlegen, wie Updates nach der Installation von Skype for Business durchgeführt werden sollen. Diese Updates können z. B. neue Funktionen, verbesserte Sicherheit oder aber Updates, die Verbesserungen der Stabilität oder Leistung bieten, enthalten. Sie müssen sich dabei folgende zwei Hauptfragen stellen:
  
- Woher möchten Sie die Updates erhalten?
    
- Wie oft möchten Sie Funktionsupdates erhalten?
    
Sie können zwar festlegen, woher Sie die Updates beziehen und wie oft Sie Funktionsupdates erhalten möchten, nicht jedoch, welche konkreten Sicherheitsupdates oder allgemeine Updates Sie erhalten.
  
 **Bezugsquelle der Updates**
  
Standardmäßig werden Updates nach Installation der Skype for Business-App aus dem Internet heruntergeladen, sobald Sie von Microsoft bereitgestellt werden. Wenn Sie mehr Kontrolle über den Zeitpunkt oder die Installationsquelle der Updates haben möchten, können Sie dies mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren
  
Viele Organisationen etwa möchten Updates vor der Bereitstellung im gesamten Unternehmen zunächst an einer Gruppe von Benutzern testen. Sie können dies tun, indem Sie die Skype for Business-App mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie so konfigurieren, dass Updates von einem bestimmten Speicherort in Ihrem Netzwerk statt automatisch über das Internet bezogen werden Anschließend können Sie die Updates mit dem Office-Bereitstellungstool monatlich in ihr lokales Netzwerk herunterladen.
  
Weitere Informationen zur Funktionsweise von Updates für Office 365-Software finden Sie in den folgenden Artikeln:
  
- [Übersicht zum Aktualisierungsvorgang für Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Wählen Sie zum Verwalten von Updates für Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Konfigurieren von Update-Einstellungen für Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **Bezug von Funktionsupdates planen**
  
Zusätzlich zur Bezugsquelle von Updates können Sie auch steuern, wie oft Sie neue Funktionen für den Skype for Business-Client erhalten. Folgende zwei Möglichkeiten stehen zur Verfügung:
  
- Funktionsupdates jeden Monat erhalten, sofern neue Funktionen zur Verfügung stehen
    
- Funktionsupdates alle sechs Monate erhalten
    
Manche Organisationen möchten Zeit haben, um neue Funktionen zu testen, und Funktionsupdates daher nur zweimal im Jahr statt monatlich erhalten.
  
Sie können steuern, wie oft Sie Funktionsupdates erhalten, indem Sie den Updatekanal mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren. Über den monatlichen Kanal erhalten Sie Funktionsupdates (ungefähr) monatlich, über den halbjährlichen Kanal dagegen alle sechs Monate. Weitere Informationen zu Kanälen finden Sie unter [Übersicht über die Updatekanäle für Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## Verwandte Themen

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Haftungsausschluss für maschinelle Übersetzungen**: Dieser Artikel wurde mithilfe eines Computersystems und ohne jegliche Bearbeitung durch Personen übersetzt. Microsoft bietet solche maschinellen Übersetzungen als Hilfestellung für Benutzer ohne Englischkenntnisse an, damit Sie von den Informationen zu Produkten, Diensten und Technologien von Microsoft profitieren können. Da es sich bei diesem Artikel um eine maschinelle Übersetzung handelt, enthält er möglicherweise Fehler in Bezug auf (Fach-)Terminologie, Syntax und/oder Grammatik. 
  

