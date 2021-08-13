---
title: Bereitstellen des Skype for Business-Clients in Microsoft 365 oder Office 365
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 8c563b81-22c9-4024-9efe-9fe28c7bbc96
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Hier erfahren Sie, wie Sie Skype for Business in kleinen, mittleren und großen Organisationen planen und bereitstellen und sie Ihren Benutzern zur Verfügung stellen. '
ms.openlocfilehash: e503455827759966af675ff186f3d72568df613ea407f372450691511a9a6ee5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300491"
---
# <a name="deploy-the-skype-for-business-client-in-microsoft-365-or-office-365"></a>Bereitstellen des Skype for Business-Clients in Microsoft 365 oder Office 365

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

In diesem Artikel werden Optionen **[](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504)** erläutert, wie Sie als Administrator die App Skype for Business Personen in Ihrer Organisation bereitstellen können.
  
Bevor Sie die Skype for Business für Ihre Benutzer bereitstellen, stellen Sie sicher, dass Sie die Schritte 1 bis 3 im Artikel Einrichten Skype for Business [Online durchgeführt haben.](set-up-skype-for-business-online.md) Auf diese Weise wird Skype for Business für Ihre Domäne eingerichtet, jeder Benutzer erhält eine Lizenz und Sie haben Chats sowie[Konfigurieren der Anwesenheit in Skype for Business Online](configure-presence-in-skype-for-business-online.md) für Ihre Organisation konfiguriert.
  
> [!NOTE]
> Benutzer, die die Skype for Business-App installieren möchten, müssen lokale Administratoren ihres PCs oder Geräts sein. Alternativ können sie auch Mitglieder einer lokalen Gruppe sein, die über die Berechtigung zum Installieren von Anwendungen auf ihrem PC oder Gerät verfügt. Wenn Ihre Benutzer keine Software auf ihren Geräten installieren dürfen, müssen Sie die App Skype for Business installieren. 
  
## <a name="for-most-small-and-medium-sized-businesses"></a>Für die meisten kleinen und mittleren Unternehmen

 **Schrittweise Installationsanleitung**: Wenn Sie ein kleines oder mittleres Unternehmen haben, empfehlen wir, die Benutzer einfach zu bitten, die Skype for Business-App auf ihrem PC zu installieren. Verweisen Sie sie auf die folgenden Anweisungen: [Installieren Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb). Wenn sie einen Mac verwenden, verweisen Sie sie auf [Einrichten von Skype for Business (Lync) für Mac 2011 für Office 365](https://support.office.com/article/ae3ebd0e-a1a7-48cf-9350-36b144dc5f88). Die Skype for Business-App wird getrennt von den anderen Office-Apps installiert.
  
 **Microsoft 365 Apps for Enterprise Kunden:** Wenn Ihr Unternehmen einen Office 365-Plan verwendet, der Microsoft 365 Apps for Enterprise umfasst, z. B. den E3-Plan, wird die Skype for Business-App gleichzeitig installiert, während die Benutzer Word, Excel, PowerPoint usw. herunterladen und installieren. Dies bedeutet auch, dass Benutzer ihre Skype for Business können, es sei denn, sie deinstallieren alle Office.
  
### <a name="choose-whether-to-make-skype-for-business-available-to-your-users"></a>Wählen, ob Skype for Business für Ihre Benutzer zur Verfügung stehen soll

Als Administrator [können](https://support.office.com/article/eac4d046-1afd-4f1a-85fc-8219c79e1504) Sie auswählen, ob die App Skype for Business Benutzern zur Verfügung stehen soll.
  
- **Um zu** steuern, ob jeder in Ihrem Unternehmen die Software erhält: Melden Sie sich beim Microsoft 365 Admin Center an, wechseln Sie zu Installieren meiner **Software**, und wählen Sie dann die Software aus, die für Benutzer verfügbar sein soll.
    
    ![Wählen Sie die Software aus, die Sie den Personen in Ihrem Unternehmen zur Verfügung stellen möchten.](../images/5eb9e9d4-6ea2-4cc1-a61d-8a1af5a7c121.png)
  
- Um zu steuern, ob bestimmte Personen **in** Ihrem Unternehmen die Software erhalten: Melden Sie sich beim Microsoft 365 Admin Center an, wechseln Sie zu Benutzer aktive Benutzer , wählen Sie die Person aus, die Zugriff auf die Software erhalten soll, klicken Sie dann neben Produktlizenzen auf Bearbeiten, und aktivieren oder deaktivieren Sie die  >  Lizenz.  
    
    ![Choose which software you want the user to access.](../images/91f6f422-2c85-4afd-944f-0021b2f6f109.png)
  
> [!NOTE]
> Wenn Sie sehen möchten, welche Pläne Personen in Ihrer Organisation zugewiesen sind, melden Sie sich beim Microsoft 365 Admin Center >  >  **Aktive Benutzer an.** Wählen Sie die Person aus der Liste aus, und sehen Sie dann unter **Produktlizenzen nach.** Wenn Sie das klassische Admin Center verwenden, sehen Sie unter **Zugewiesene Lizenz nach.** 
  
### <a name="manually-deploying-skype-for-business-to-your-users"></a>Manuelle Bereitstellung von Skype for Business für Ihre Benutzer
<a name="bkmk_manual_1"> </a>

Wenn Sie möchten, dass die Benutzer die Skype for Business-App von einem Speicherort in Ihrem Netzwerk statt aus dem Internet installieren, können Sie die Setupdateien herunterladen. Wechseln Sie dazu im Abschnitt **Benutzersoftware manuell bereitstellen** des Microsoft 365 Admin Center. Anschließend können Sie Installieren **auswählen** und die Setup-.exe an einem Netzwerkspeicherort speichern.
  
Sie haben auch die Möglichkeit, die Skype for Business Basic-App für die Benutzer herunterzuladen. Sie können [Microsoft Skype for Business Basic (32- oder 64-Bit) herunterladen.](https://www.microsoft.com/download/details.aspx?id=49440)
  
Sowohl für die vollständige als auch für die Basic-Version der Skype for Business-App müssen Sie nach dem Herunterladen der Setupdateien den Netzwerkpfad manuell an die Benutzer senden (zum Beispiel per E-Mail). Dann können sie das Setupprogramm ausführen, um die App auf ihrem Computer zu installieren.
  
Sie können diese Downloads auch zum Bereitstellen der Skype for Business-App für Ihre Benutzer mithilfe Ihrer vorhandenen Softwarebereitstellungstools und -prozesse verwenden.
  
## <a name="for-larger-and-enterprise-organizations"></a>Für größere und sehr große Unternehmen

> [!NOTE]
> Dieser Abschnitt betrifft nur die in Office 365-Plänen verfügbare Skype for Business-App. Wenn Ihre Organisation eine Volumenlizenzversion der Skype for Business-App verwendet, die auf Windows Installer basiert (MSI), finden Sie Informationen unter Anpassen der Windows-Clientinstallation [in Skype for Business Server.](../../SfbServer/deploy/deploy-clients/customize-windows-client-installation.md)
  
In vielen Großunternehmen haben Benutzer nicht die Berechtigung zum Installieren von Software auf ihren Computern. Stattdessen wird die Software von den IT-Abteilungen auf den Computern bereitgestellt. IT-Abteilungen möchten unter Umständen auch die in der Organisation verwendete Internet- oder Netzwerkbandbreite steuern und Software daher von einem Speicherort im lokalen Netzwerk aus statt über das Internet oder das Unternehmensnetzwerk installieren.
  
Mit Office 365 haben Sie mehrere Optionen für die Bereitstellung der Skype for Business-App, wenn Sie steuern möchten, woher die App installiert werden soll. Zu diesen Optionen gehören die folgenden:
  
- Laden Sie Skype for Business-App aus dem Microsoft 365 Admin Center in Ihr lokales Netzwerk herunter, wie unter Manuelles Bereitstellen von Skype for Business [Benutzern beschrieben.](deploy-the-skype-for-business-client-in-office-365.md#bkmk_manual_1)
    
- Verwenden Sie **[Office-Bereitstellungstool,](https://go.microsoft.com/fwlink/p/?LinkID=626065)** um Microsoft 365 Apps for Enterprise oder die Skype for Business-App in Ihr lokales Netzwerk herunterzuladen. Verwenden Sie das Office-Bereitstellungstool anschließend zum Bereitstellen der App für Ihre Benutzer. Mit dem Office-Bereitstellungstool können Sie unterschiedliche Aspekte der Bereitstellung festlegen, wie etwa Sprachen oder Version (32 Bit oder 64 Bit).
    
- Verwenden Sie Ihre vorhandenen Softwarebereitstellungstools und -prozesse, z. B. Microsoft Endpoint Configuration Manager, um Microsoft 365 Apps for Enterprise oder die Skype for Business-App für Ihre Benutzer zu implementieren. Sie können Ihre vorhandenen Tools und Prozesse mit dem [Office-Bereitstellungstool](https://go.microsoft.com/fwlink/p/?LinkID=626065) oder mit der Software verwenden, die Sie aus dem Microsoft 365 Admin Center.
    
### <a name="more-info-on-using-the-office-deployment-tool"></a>Zusätzliche Informationen zur Verwendung des Office-Bereitstellungstools

Details zum Herunterladen des Office-Bereitstellungstools und weitere Informationen zum Installieren der Skype for Business-App und anderer Office 365-Client-Apps finden Sie unter Verwalten von Einstellungen für den Softwaredownload [in Office 365.](https://support.office.com/article/c13051e6-f75c-4737-bc0d-7685dcedf360)
  
Im Folgenden finden Sie eine Übersicht über die Schritte zur Verwendung des Office Bereitstellungstools zum Bereitstellen einer App:
  
1. **[Laden Sie die aktuellste Version des Office-Bereitstellungstools](https://www.microsoft.com/download/details.aspx?id=49117)** aus dem Microsoft Download Center herunter.
    
2. Erstellen Sie die configuration.xml-Datei zur Verwendung mit dem Office-Bereitstellungstool mit den von Ihnen gewünschten Client-App-Einstellungen, wie zum Beispiel der Version (32-Bit oder 64-Bit), der Installationssprache usw.
    
3. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Setupdateien vom Office Content Delivery Network (CDN) in Ihr lokales oder internes Netzwerk herunterzuladen.
    
4. Verwenden Sie das Office-Bereitstellungstool und die Datei „configuration.xml", um die Office-Client-Apps einschließlich der Skype for Business-App zu installieren.
    
Details zur Verwendung des Office-Bereitstellungstools und zur configuration.xml-Datei finden Sie hier:
  
- [Office-Bereitstellungstool - Überblick](/deployoffice/overview-office-deployment-tool)
    
- [Configuration.xml - Einstellungen](/deployoffice/office-deployment-tool-configuration-options)
    
### <a name="more-info-on-using-microsoft-endpoint-configuration-manager"></a>Weitere Informationen zur Verwendung von Microsoft Endpoint Configuration Manager

Sie können Ihre vorhandenen Softwarebereitstellungstools und -prozesse, z. B. Microsoft Endpoint Configuration Manager, verwenden, um die App Skype for Business bereitstellen. Sie können diese Tools und Prozesse entweder mit der Software, die Sie vom Microsoft 365 Admin Center herunterladen, oder mit dem Office verwenden.
  
Weitere Informationen zur Bereitstellung von Software mit Configuration Manager finden Sie in den folgenden Artikeln:
  
- [Erstellen von Anwendungen in Configuration Manager](/configmgr/apps/deploy-use/create-applications)
    
- [Bereitstellen von Anwendungen mit Configuration Manager](/configmgr/apps/deploy-use/deploy-applications)
    
Wenn Sie die App Skype for Business im Rahmen der Microsoft 365 Apps for Enterprise bereitstellen, lesen Sie Verwalten Microsoft 365 Apps for Enterprise [mit Configuration Manager.](/configmgr/sum/deploy-use/manage-office-365-proplus-updates)
  
## <a name="planning-for-updates-to-the-skype-for-business-app"></a>Planen von Updates der Skype for Business-App

Im Rahmen der Bereitstellung der Skype for Business-App müssen Sie auch festlegen, wie Updates nach der Installation von Skype for Business durchgeführt werden sollen. Diese Updates können z. B. neue Funktionen, verbesserte Sicherheit oder aber Updates, die Verbesserungen der Stabilität oder Leistung bieten, enthalten. Sie müssen sich dabei folgende zwei Hauptfragen stellen:
  
- Woher möchten Sie die Updates erhalten?
    
- Wie oft möchten Sie Funktionsupdates erhalten?
    
Sie können zwar festlegen, woher Sie die Updates beziehen und wie oft Sie Funktionsupdates erhalten möchten, nicht jedoch, welche konkreten Sicherheitsupdates oder allgemeine Updates Sie erhalten.
  
 **Bezugsquelle der Updates**
  
Standardmäßig werden Updates nach Installation der Skype for Business-App aus dem Internet heruntergeladen, sobald Sie von Microsoft bereitgestellt werden. Wenn Sie mehr Kontrolle über den Zeitpunkt oder die Installationsquelle der Updates haben möchten, können Sie dies mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren
  
Viele Organisationen etwa möchten Updates vor der Bereitstellung im gesamten Unternehmen zunächst an einer Gruppe von Benutzern testen. Sie können dies tun, indem Sie die Skype for Business-App mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie so konfigurieren, dass Updates von einem bestimmten Speicherort in Ihrem Netzwerk statt automatisch über das Internet bezogen werden Anschließend können Sie die Updates mit dem Office-Bereitstellungstool monatlich in ihr lokales Netzwerk herunterladen.
  
Weitere Informationen zur Funktionsweise von Updates für Office 365-Software finden Sie in den folgenden Artikeln:
  
- [Übersicht über den Updateprozess für Microsoft 365 Apps for Enterprise](/deployoffice/overview-update-process-microsoft-365-apps)
    
- [Wählen Sie aus, wie Updates verwaltet werden Microsoft 365 Apps for Enterprise](/deployoffice/choose-how-manage-updates-microsoft-365-apps)
    
- [Konfigurieren von Updateeinstellungen für Microsoft 365 Apps for Enterprise](/deployoffice/configure-update-settings-microsoft-365-apps)
    
  **Bezug von Funktionsupdates planen**
  
Zusätzlich zur Bezugsquelle von Updates können Sie auch steuern, wie oft Sie neue Funktionen für den Skype for Business-Client erhalten. Folgende zwei Möglichkeiten stehen zur Verfügung:
  
- Funktionsupdates jeden Monat erhalten, sofern neue Funktionen zur Verfügung stehen
    
- Funktionsupdates alle sechs Monate erhalten
    
Manche Organisationen möchten Zeit haben, um neue Funktionen zu testen, und Funktionsupdates daher nur zweimal im Jahr statt monatlich erhalten.
  
Sie können steuern, wie oft Sie Funktionsupdates erhalten, indem Sie den Updatekanal mithilfe des Office-Bereitstellungstools oder einer Gruppenrichtlinie konfigurieren. Über den monatlichen Kanal erhalten Sie Funktionsupdates (ungefähr) monatlich, über den halbjährlichen Kanal dagegen alle sechs Monate. Weitere Informationen zu Kanälen finden Sie unter [Übersicht über die Updatekanäle für Microsoft 365 Apps for Enterprise.](https://support.office.com/article/9ccf0f13-28ff-4975-9bd2-7e4ea2fefef4)
  
## <a name="related-topics"></a>Verwandte Themen

[Einrichten von Skype for Business Online](set-up-skype-for-business-online.md)
  
[Add-On-Lizenzierung für Skype for Business und Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
