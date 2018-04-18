---
title: Den Skype for Business-Client in Office 365 bereitstellen
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'Learn how to plan and deploy Skype for Business in small, medium, and large organizations and making it available to your users. '
ms.openlocfilehash: 83c2b0060f7edbb39c24709db2880b8aed014553
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="deploy-the-skype-for-business-client-in-office-365"></a>Den Skype for Business-Client in Office 365 bereitstellen

In diesem Artikel werden die Optionen für, wie Sie die **[Admin](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US)**, der Skype für Geschäfts-app an die Personen in Ihrer Organisation bereitstellen können.
  
Vor der Bereitstellung von Skype Business für die Benutzer, vergewissern Sie sich für haben Sie die Schritte 1 bis 3 im Artikel [Einrichten von Skype für Business Online](set-up-skype-for-business-online.md)durchgeführt. Auf diese Weise wird Skype for Business für Ihre Domäne eingerichtet, jeder Benutzer erhält eine Lizenz und Sie haben Chats sowie[Konfigurieren der Anwesenheit in Skype for Business Online](configure-presence-in-skype-for-business-online.md) für Ihre Organisation konfiguriert.
  
> [!NOTE]
> Benutzer, die die Skype for Business-App installieren möchten, müssen lokale Administratoren ihres PCs oder Geräts sein. Alternativ können sie auch Mitglieder einer lokalen Gruppe sein, die über die Berechtigung zum Installieren von Anwendungen auf ihrem PC oder Gerät verfügt. Wenn Ihre Benutzer unzulässige Software auf ihren Geräten installieren, müssen Sie die Skype für Geschäfts-app für diese Benutzer installieren. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Für die meisten kleinen und mittleren Unternehmen

 **Schrittweise Installationsanleitung**: Wenn Sie ein kleines oder mittleres Unternehmen haben, empfehlen wir, die Benutzer einfach zu bitten, die Skype for Business-App auf ihrem PC zu installieren. Zeigen sie auf diese Anweisungen: [Installieren von Skype für Unternehmen](https://support.office.com/en-us/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb?ui=en-US&rs=en-US&ad=US). Wenn sie einen Mac verwenden, verweisen Sie sie auf [Einrichten von Skype for Business (Lync) für Mac 2011 für Office 365](https://support.office.com/en-us/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88?ui=en-US&rs=en-US&ad=US). Die Skype for Business-App wird getrennt von den anderen Office-Apps installiert.
  
 **Office 365 ProPlus-Kunden**: Wenn Ihr Unternehmen einen Office 365-Plan verwendet, in dem Office 365 ProPlus enthalten ist (zum Beispiel den E3-Plan), wird die Skype for Business-App zusammen mit Word, Excel, PowerPoint usw. installiert. Dies bedeutet außerdem, dass die Benutzer Skype for Business nur durch die Deinstallation des gesamten Office-Pakets deinstallieren können.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Wählen, ob Skype for Business für Ihre Benutzer zur Verfügung stehen soll

Als [Administrator](https://support.office.com/en-us/article/eac4d046-1afd-4f1a-85fc-8219c79e1504?ui=en-US&rs=en-US&ad=US) können Sie auswählen, ob die Skype für Geschäfts-app für Ihre Benutzer verfügbar machen.
  
- **Ruft ab, ob alle Personen in Ihrem Unternehmen steuern die Software**: Melden Sie sich bei der Office 365 Administrationscenter, wechseln Sie zum **Installieren der Software**, und wählen Sie die Software für Benutzer verfügbar sein soll.
    
    ![Choose the software you want to make available to the people in your company.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- **Steuern, ob bestimmte Personen in Ihrem Unternehmen erhalten möchten die Software**: Melden Sie sich bei der Office 365 Administrationscenter, fahren Sie mit der **Benutzer** > **aktive Benutzer**, wählen Sie die Person, die Sie Zugriff auf die Software zu gewähren möchten, und klicken Sie dann auf **Bearbeiten** neben **Lizenzen** und aktivieren oder Deaktivieren der Lizenz.
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Wenn Sie sehen, welche Pläne an Personen in Ihrer Organisation zugewiesen werden müssen, melden Sie sich das neue Office 365 Administrationscenter > **Benutzer** > **aktive Benutzer**. Wählen Sie die Person aus der Liste aus, und klicken Sie dann unter **Lizenzen**zu suchen. Wenn Sie das klassische Office 365 Administrationscenter verwenden, suchen Sie unter **Lizenz zugewiesen**. 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Manuelle Bereitstellung von Skype for Business für Ihre Benutzer
<a name="bkmk_manual_1"> </a>

If you want your users to install the Skype for Business app from a location on your network instead of from the Internet, you can download the setup files. To do this go to the **Manually deploy user software** section of the Office 365 admin center. You can then select **Install** and save the setup .exe file to a network location.
  
Sie haben auch die Möglichkeit, die Skype for Business Basic-App für die Benutzer herunterzuladen. Sie können [Microsoft Skype für Business Basic (32- oder 64-Bit)](https://www.microsoft.com/en-us/download/details.aspx?id=49440)herunterladen.
  
Sowohl für die vollständige als auch für die Basic-Version der Skype for Business-App müssen Sie nach dem Herunterladen der Setupdateien den Netzwerkpfad manuell an die Benutzer senden (zum Beispiel per E-Mail). Dann können sie das Setupprogramm ausführen, um die App auf ihrem Computer zu installieren.
  
Sie können diese Downloads auch zum Bereitstellen der Skype for Business-App für Ihre Benutzer mithilfe Ihrer vorhandenen Softwarebereitstellungstools und -prozesse verwenden.
  
## <a name="for-larger-and-enterprise-organizations"></a>Für größere und sehr große Unternehmen

> [!NOTE]
> Dieser Abschnitt betrifft nur die in Office 365-Plänen verfügbare Skype for Business-App. Wenn Ihre Organisation eine Volumenlizenzversion der Skype for Business-App verwendet, die auf Windows Installer (MSI) basiert, lesen Sie[Anpassen von Windows-Client-Installation in Skype für Business Server 2015](https://technet.microsoft.com/en-us/library/jj204934.aspx). 
  
In vielen Großunternehmen haben Benutzer nicht die Berechtigung zum Installieren von Software auf ihren Computern. Stattdessen wird die Software von den IT-Abteilungen auf den Computern bereitgestellt. IT-Abteilungen möchten unter Umständen auch die in der Organisation verwendete Internet- oder Netzwerkbandbreite steuern und Software daher von einem Speicherort im lokalen Netzwerk aus statt über das Internet oder das Unternehmensnetzwerk installieren.
  
Mit Office 365 haben Sie mehrere Optionen für die Bereitstellung der Skype für Geschäfts-app, wenn Sie möchten steuern, auf dem er installiert ist. Einige dieser Optionen umfassen Folgendes:
  
- Laden Sie die Skype for Business-App vom Office 365 Admin Center wie in [Manuelle Bereitstellung von Skype for Business für Ihre Benutzer](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1) in Ihr lokales Netzwerk herunter.
    
- Verwenden Sie das **[Office-Bereitstellungstool](https://go.microsoft.com/fwlink/p/?LinkID=626065)** zum Herunterladen von Office 365 ProPlus oder der Skype for Business-App in ihr lokales Netzwerk. Verwenden Sie das Office-Bereitstellungstool anschließend zum Bereitstellen der App für Ihre Benutzer. Mit dem Office-Bereitstellungstool können Sie unterschiedliche Aspekte der Bereitstellung festlegen, wie etwa Sprachen oder Version (32 Bit oder 64 Bit).
    
- Verwenden Sie Ihre vorhandenen Software-Bereitstellungstools und -Prozesse, wie z. B. System Center Configuration Manager, zum Bereitstellen von Office 365 ProPlus oder der Skype for Business-App für Ihre Benutzer. Sie können Ihre vorhandenen Tools und Prozesse mit dem [Office-Bereitstellungstool](https://go.microsoft.com/fwlink/p/?LinkID=626065) oder der Software verwenden, die Sie aus dem Office 365 Admin Center heruntergeladen haben.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Zusätzliche Informationen zur Verwendung des Office-Bereitstellungstools

Details zum Herunterladen des Office-Bereitstellungstools und zusätzliche Informationen zur Installation der Skype for Business-App sowie weiterer Office 365-Client-Apps finden Sie unter [Verwalten von Benutzersoftware in Office 365](https://support.office.com/en-us/article/c13051e6-f75c-4737-bc0d-7685dcedf360).
  
Nachfolgend finden Sie eine Übersicht über die Schritte für die Verwendung des Office-Bereitstellungstools zum Bereitstellen einer app:
  
1. **[Laden Sie die aktuellste Version des Office-Bereitstellungstools](https://www.microsoft.com/en-us/download/details.aspx?id=49117)** aus dem Microsoft Download Center herunter.
    
2. Erstellen Sie die configuration.xml-Datei zur Verwendung mit dem Office-Bereitstellungstool mit den von Ihnen gewünschten Client-App-Einstellungen, wie zum Beispiel der Version (32-Bit oder 64-Bit), der Installationssprache usw.
    
3. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Setupdateien vom Office Content Delivery Network (CDN) in Ihr lokales oder internes Netzwerk herunterzuladen.
    
4. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Office-Client-Apps einschließlich der Skype for Business-App zu installieren.
    
Details zur Verwendung des Office-Bereitstellungstools und zur configuration.xml-Datei finden Sie hier:
  
- [Office-Bereitstellungstool - Überblick](https://technet.microsoft.com/library/jj219422.aspx)
    
- [Configuration.xml - Einstellungen](https://technet.microsoft.com/library/jj219426.aspx)
    
### <a name="more-info-on-using-system-center-configuration-manager"></a>Weitere Informationen zur Verwendung von System Center Configuration Manager

Sie können Ihre vorhandenen Software-Bereitstellungstools und -Prozesse, wie etwa System Center Configuration Manager, zur Bereitstellung der Skype for Business-App verwenden. Sie können diese Tools und Prozesse mit der Software, die Sie vom Office 365 Admin Center herunterladen, oder mit dem Office-Bereitstellungstool verwenden.
  
Weitere Informationen zur Bereitstellung von Software mit Configuration Manager finden Sie in den folgenden Artikeln:
  
- [So erstellen Sie Anwendungen im Configuration Manager](https://technet.microsoft.com/en-us/library/gg682159.aspx)
    
- [So stellen Sie Anwendungen im Configuration Manager bereit](https://technet.microsoft.com/en-us/library/gg682082.aspx)
    
Wenn Sie die Skype for Business-App als Teil der Bereitstellung von Office 365 ProPlus verwenden, lesen Sie [Bereitstellen von Office 365 ProPlus mithilfe von System Center Configuration Manager](https://technet.microsoft.com/en-us/library/dn708063.aspx).
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planen von Updates der Skype for Business-App

Im Rahmen der Bereitstellung der Skype for Business-App müssen Sie auch festlegen, wie Updates nach der Installation von Skype for Business durchgeführt werden sollen. Diese Updates können z. B. neue Funktionen, verbesserte Sicherheit oder aber Updates, die Verbesserungen der Stabilität oder Leistung bieten, enthalten. Sie müssen sich dabei folgende zwei Hauptfragen stellen:
  
- Woher möchten Sie die Updates erhalten?
    
- Wie oft möchten Sie Funktionsupdates erhalten?
    
Sie können zwar festlegen, woher Sie die Updates beziehen und wie oft Sie Funktionsupdates erhalten möchten, nicht jedoch, welche konkreten Sicherheitsupdates oder allgemeine Updates Sie erhalten.
  
 **Bezugsquelle der Updates**
  
Standardmäßig werden Updates nach Installation der Skype for Business-App aus dem Internet heruntergeladen, sobald Sie von Microsoft bereitgestellt werden. Wenn Sie mehr Kontrolle über den Zeitpunkt oder die Installationsquelle der Updates haben möchten, können Sie dies mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren
  
Viele Organisationen etwa möchten Updates vor der Bereitstellung im gesamten Unternehmen zunächst an einer Gruppe von Benutzern testen. Sie können dies tun, indem Sie die Skype for Business-App mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie so konfigurieren, dass Updates von einem bestimmten Speicherort in Ihrem Netzwerk statt automatisch über das Internet bezogen werden Anschließend können Sie die Updates mit dem Office-Bereitstellungstool monatlich in ihr lokales Netzwerk herunterladen.
  
Weitere Informationen zur Funktionsweise von Updates für Office 365-Software finden Sie in den folgenden Artikeln:
  
- [Übersicht zum Aktualisierungsvorgang für Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761709.aspx)
    
- [Wählen Sie, wie zum Verwalten von Updates für Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761707.aspx)
    
- [Konfigurieren von Update-Einstellungen für Office 365 ProPlus](https://technet.microsoft.com/en-us/library/dn761708.aspx)
    
 **Bezug von Funktionsupdates planen**
  
Zusätzlich zur Bezugsquelle von Updates können Sie auch steuern, wie oft Sie neue Funktionen für den Skype for Business-Client erhalten. Folgende zwei Möglichkeiten stehen zur Verfügung:
  
- Funktionsupdates jeden Monat erhalten, sofern neue Funktionen zur Verfügung stehen
    
- Funktionsupdates alle sechs Monate erhalten
    
Manche Organisationen möchten Zeit haben, um neue Funktionen zu testen, und Funktionsupdates daher nur zweimal im Jahr statt monatlich erhalten.
  
Sie können steuern, wie oft Sie Funktionsupdates erhalten, indem Sie den Updatekanal mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren. Über den monatlichen Kanal erhalten Sie Funktionsupdates (ungefähr) monatlich, über den halbjährlichen Kanal dagegen alle sechs Monate. Weitere Informationen zu Kanälen finden Sie unter [Übersicht über die Updatekanäle für Office 365 ProPlus](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4).
  
## <a name="related-topics"></a>See Also

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
